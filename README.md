# Yu Lei — Personal Homepage

Personal academic homepage built with plain HTML + CSS. No framework, no build step — edit `index.html` directly and push.

Live site: https://leiyu0210.github.io

---

## Files

```
index.html   — the entire page
you.jpg      — profile photo
README.md    — this file
```

---

## How to add a new paper

Open `index.html` and find the `Research & Publications` section.

Papers are grouped by research direction inside `focus-item` blocks. Choose the matching direction, then add a new `li.pub` inside that direction's `ol.pub-list`.

```html
<li class="pub">
  <div class="pub-badges">
    <span class="badge role">First Author</span>
    <span class="badge venue">KDD 2027</span>
  </div>
  <div>
    <p class="pub-title">
      <a href="https://arxiv.org/abs/xxxx.xxxxx" target="_blank" rel="noopener">Paper Title Here</a>
    </p>
    <p class="authors"><strong>Yu Lei</strong>, Co-author One, Co-author Two.</p>
  </div>
</li>
```

- For **co-first authors**, append `*` to each name and use the `role` badge:
  `<strong>Yu Lei*</strong>, Shuzheng Si*, ...`
- To mark a submission, use `badge submitted` instead of `badge venue`.
- To hide a paper temporarily without deleting it, wrap the `li.pub` block in `<!-- ... -->`.

Then push to GitHub:

```bash
git add index.html
git commit -m "add paper: <short title>"
git push
```

GitHub Pages updates automatically within ~1 minute.

---

## Badge reference

| Badge class | Color | When to use |
|---|---|---|
| `badge role` | Green | Authorship role, e.g. First Author / Co-first |
| `badge venue` | Blue | Accepted conference, workshop, or journal |
| `badge submitted` | Grey | Under review / submission status |

---

## Restore a hidden paper

Search for `HIDDEN` in `index.html`, then remove the `<!--` and `-->` lines surrounding the block.
