---
layout: page
title: Repositories
permalink: /repos/
---

Code I've written. Pulled live from GitHub, so it stays current without me
having to remember to update it. Still a work in progress — expect some rough
edges.

<div class="repo-toolbar" id="repo-toolbar" hidden>
  <input type="search" id="repo-filter" placeholder="Filter repositories…" aria-label="Filter repositories">
  <span class="repo-count" id="repo-count"></span>
</div>

<div class="repo-grid" id="repos">
  <div class="repo-card is-skeleton"></div>
  <div class="repo-card is-skeleton"></div>
  <div class="repo-card is-skeleton"></div>
  <div class="repo-card is-skeleton"></div>
</div>

<script>
(function () {
  var user = "{{ site.github_username }}";
  var target = document.getElementById("repos");
  var toolbar = document.getElementById("repo-toolbar");
  var filterBox = document.getElementById("repo-filter");
  var countEl = document.getElementById("repo-count");

  // Repos you'd rather not show. Add names here, e.g. ["dotfiles", "scratch"].
  var hide = [];

  // Repos to pin at the top, in order.
  var pinned = ["arxave", "QDarts"];

  // Colours roughly matching GitHub's language dots. Anything missing falls
  // back to the accent colour.
  var langColor = {
    Python: "#3572A5", Jupyter: "#DA5B0B", "Jupyter Notebook": "#DA5B0B",
    JavaScript: "#f1e05a", TypeScript: "#3178c6", HTML: "#e34c26",
    CSS: "#563d7c", SCSS: "#c6538c", Rust: "#dea584", Go: "#00ADD8",
    C: "#555555", "C++": "#f34b7d", Julia: "#a270ba", MATLAB: "#e16737",
    Shell: "#89e051", TeX: "#3D6117", Ruby: "#701516", Java: "#b07219",
    Fortran: "#4d41b1", "Mathematica": "#dd1100"
  };

  if (!user || user === "CHANGEME") {
    target.innerHTML = '<p class="post-excerpt">Set <code>github_username</code> in <code>_config.yml</code> to populate this list.</p>';
    return;
  }

  function esc(s) {
    return String(s == null ? "" : s).replace(/[&<>"']/g, function (c) {
      return { "&": "&amp;", "<": "&lt;", ">": "&gt;", '"': "&quot;", "'": "&#39;" }[c];
    });
  }

  // "3 days ago" / "5 months ago", so freshness reads at a glance.
  function ago(iso) {
    var days = Math.floor((Date.now() - new Date(iso)) / 86400000);
    if (days < 1) return "today";
    if (days < 30) return days + (days === 1 ? " day ago" : " days ago");
    var months = Math.round(days / 30.4);
    if (months < 18) return months + (months === 1 ? " month ago" : " months ago");
    var years = Math.round(days / 365);
    return years + (years === 1 ? " year ago" : " years ago");
  }

  function card(r, isPinned) {
    var meta = [];
    if (r.language) {
      meta.push('<span class="repo-lang"><i style="background:' +
        esc(langColor[r.language] || "var(--accent)") + '"></i>' + esc(r.language) + '</span>');
    }
    if (r.stargazers_count) meta.push('<span>★ ' + r.stargazers_count + '</span>');
    if (r.forks_count) meta.push('<span>⑂ ' + r.forks_count + '</span>');
    meta.push('<span class="repo-updated">' + esc(ago(r.pushed_at)) + '</span>');

    var topics = (r.topics || []).slice(0, 4).map(function (t) {
      return '<span class="tag">' + esc(t) + '</span>';
    }).join("");

    return '<a class="repo-card' + (isPinned ? ' is-pinned' : '') + '" href="' + esc(r.html_url) + '">' +
             '<h3>' + esc(r.name) + (isPinned ? '<span class="repo-pin" title="Pinned">★</span>' : '') + '</h3>' +
             (r.description ? '<p>' + esc(r.description) + '</p>' : '') +
             (topics ? '<div class="repo-topics">' + topics + '</div>' : '') +
             '<div class="repo-meta">' + meta.join('') + '</div>' +
           '</a>';
  }

  fetch("https://api.github.com/users/" + encodeURIComponent(user) + "/repos?per_page=100&sort=updated", {
    headers: { Accept: "application/vnd.github.mercy-preview+json" }
  })
    .then(function (r) {
      if (!r.ok) throw new Error("GitHub returned " + r.status);
      return r.json();
    })
    .then(function (repos) {
      repos = repos.filter(function (r) {
        return !r.fork && !r.archived && hide.indexOf(r.name) === -1;
      });

      repos.sort(function (a, b) {
        var ia = pinned.indexOf(a.name), ib = pinned.indexOf(b.name);
        if (ia !== -1 || ib !== -1) return (ia === -1 ? 999 : ia) - (ib === -1 ? 999 : ib);
        return b.stargazers_count - a.stargazers_count ||
               new Date(b.pushed_at) - new Date(a.pushed_at);
      });

      if (!repos.length) {
        target.innerHTML = '<p class="post-excerpt">No public repositories yet.</p>';
        return;
      }

      function render(query) {
        var q = (query || "").trim().toLowerCase();
        var shown = repos.filter(function (r) {
          if (!q) return true;
          return (r.name + " " + (r.description || "") + " " + (r.language || "") +
                  " " + (r.topics || []).join(" ")).toLowerCase().indexOf(q) !== -1;
        });
        target.innerHTML = shown.length
          ? shown.map(function (r) { return card(r, pinned.indexOf(r.name) !== -1); }).join("")
          : '<p class="post-excerpt">Nothing matches “' + esc(query) + '”.</p>';
        countEl.textContent = shown.length + " of " + repos.length;
      }

      toolbar.hidden = false;
      filterBox.addEventListener("input", function () { render(filterBox.value); });
      render("");
    })
    .catch(function (err) {
      target.innerHTML = '<p class="post-excerpt">Could not load repositories (' + esc(err.message) +
        '). See <a href="https://github.com/' + esc(user) + '?tab=repositories">github.com/' + esc(user) + '</a>.</p>';
    });
})();
</script>

<noscript>
  <p>See <a href="https://github.com/{{ site.github_username }}?tab=repositories">github.com/{{ site.github_username }}</a>.</p>
</noscript>
