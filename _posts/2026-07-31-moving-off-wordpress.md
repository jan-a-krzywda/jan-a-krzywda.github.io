---
layout: post
title: "Moving off WordPress"
date: 2026-07-31 09:00:00 +0000
excerpt: "This site now runs on plain text files in a Git repository."
categories: ["Meta"]
tags: ["jekyll", "wordpress"]
---

This is a sample post so you can see what a published entry looks like. Delete
it once your real posts are in place.

Everything here is a Markdown file in `_posts/`. The filename carries the date
and the URL slug:

```
_posts/2026-07-31-moving-off-wordpress.md
        └── date ──┘ └────── slug ──────┘
```

The block at the top of the file — between the `---` lines — is *front matter*.
It's how you set the title, the date, and any categories or tags.

## Writing a new post

1. Create a file in `_posts/` named `YYYY-MM-DD-some-slug.md`.
2. Copy the front matter block from this file and change the values.
3. Write in Markdown below it.
4. Commit and push. The site rebuilds itself within a minute or two.

## Things Markdown gives you

**Bold**, *italic*, `inline code`, and [links](https://github.com).

> Blockquotes look like this.

- Bulleted lists
- Are straightforward

Images go in `assets/images/` and are referenced with a leading slash:

```markdown
![Alt text]({% raw %}{{ site.baseurl }}{% endraw %}/assets/images/photo.jpg)
```

That's the whole system. No database, no plugin updates, no renewal notice.
