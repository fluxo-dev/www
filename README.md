<p align="center">
  <img src="/static/fluxo-banner.webp" width="300px" alt="" />

---

<p align="center">
  public website and blog

---

This repository contains the source code and contents of the public website and blog located at
https://fluxo.dev. Content created or updated in this repository automatically gets published.

To create a new post, you must:

- Become a collaborator on this repository.
- Clone the repository.
- Create a new Markdown file [1] in the `content` directory.
- Provide the necessary frontmatter in the new Markdown file.
- Provide the content of the new post.
- Validate [2] a draft of the new post.
- Commit and push the change to GitHub.

[1] The new Markdown file should have content that looks like the template below. Anything in braces
is a placeholder and must be replaced. You may have more than 1 author and any number of tags (even
zero).

```
+++
title = "{TITLE}"
date = {YYYY}-{MM}-{DD}
[taxonomies]
authors = ["{AUTHOR-1}", "{AUTHOR-2}"]
tags = ["{TAG-1}", "{TAG-2}"]
+++

{CONTENT}
```

[2] To validate a draft, you need to install [Zola](https://getzola.org) locally and run its server. On a macOS system, you can follow these steps:

- Run `brew install zola`.
- In the repository root, run `zola serve`.
