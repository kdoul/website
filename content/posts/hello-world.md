---
title: "Hello world, again"
date: 2026-07-22
tags: ["meta"]
description: "The old site is gone, long live the new site."
---

The old version of this site was a single static HTML page on a VM
that no longer exists. This one is built with Hugo and lives in a Git repository. It deploys
itself to GitHub Pages on every push.

Writing a new post is now just:

```bash
hugo new content posts/my-new-post.md
git add . && git commit -m "post: my new post" && git push
```

That's it. No server to maintain.
