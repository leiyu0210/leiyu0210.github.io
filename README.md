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

Open `index.html` and find the `<!-- PUBLICATIONS -->` section.

**Step 1 — Choose the right year group**

Each year is wrapped in a `pub-year-group` block:

```html
<div class="pub-year-group reveal">
  <div class="pub-year-label">2026</div>
  <!-- papers go here -->
</div>
```

If the year doesn't exist yet, copy the block above, change the label, and paste it before the nearest older year.

**Step 2 — Copy this template and fill it in**

```html
<div class="pub-item">
  <div class="pub-index"></div>   <!-- number is auto-generated, leave empty -->
  <div class="pub-body">
    <div class="pub-meta">
      <span class="badge badge-venue">KDD 2027</span>   <!-- venue badge -->
      <!-- optional badges — add or remove as needed: -->
      <span class="badge badge-oral">Oral</span>
      <span class="badge badge-cofirst">Co-first Author</span>
      <span class="badge badge-journal">Nature</span>
      <span class="badge badge-preprint">Under Review</span>
    </div>
    <p class="pub-title">
      <a href="https://arxiv.org/abs/xxxx.xxxxx" target="_blank" rel="noopener">
        Paper Title Here
      </a>
    </p>
    <p class="pub-authors">
      <strong>Yu Lei</strong>, Co-author One, Co-author Two
    </p>
  </div>
</div>
```

- **Numbering** is automatic — no need to touch `pub-index`.
- For **co-first authors**, append `*` to each name and add the `badge-cofirst` badge:
  `<strong>Yu Lei*</strong>, Shuzheng Si*, ...`
- To **hide a paper temporarily** without deleting it, wrap the `pub-item` block in `<!-- ... -->` and it will be ignored by the browser.

**Step 3 — Push to GitHub**

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
| `badge-venue` | Blue | Conference / workshop name |
| `badge-oral` | Amber | Oral presentation |
| `badge-journal` | Green | Journal publication |
| `badge-cofirst` | Purple | Co-first authorship |
| `badge-preprint` | Grey | Under review / preprint |

---

## Restore a hidden paper

Search for `HIDDEN` in `index.html`, then remove the `<!--` and `-->` lines surrounding the block.
