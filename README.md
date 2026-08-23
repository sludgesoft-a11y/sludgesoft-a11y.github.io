# sludgesoft.github.io

The SludgeSoft site. Plain HTML plus one stylesheet — no build step, no
dependencies, no external requests, no JavaScript beyond setting the year in the
footer. Open any page in a browser to preview, or serve the folder:

```bash
python -m http.server 8765
```

## Pages

| File | Purpose |
|---|---|
| `index.html` | Studio landing page |
| `questgun.html` | QuestGun product page — **this is the URL given to the Meta Horizon Store as the app website** |
| `guide.html` | Player's guide (setup, controls, troubleshooting) |
| `compatibility.html` | What runs, what is too slow, what crashes |
| `support.html` | Support contact and bug-report guidance — **the store's support URL** |
| `privacy.html` | Privacy policy — **the store's privacy policy URL** |
| `terms.html` | Terms and conditions — **the store's terms of service URL** |
| `404.html` | Served by Pages for unknown paths |
| `style.css` | Every page's styling |

The HTML pages are the canonical copies. `PRIVACY.md`, `TERMS.md` and
`QuestGun/USER_GUIDE.md` are the markdown they were generated from; if you edit
one, edit the HTML too, or the published page and the source disagree.

**`QuestGun/USER_GUIDE.md` here is deliberately not identical to the one in the
QuestGun repo.** This copy has its example file names genericised — see the rule
below. Do not resync it from the app repo without re-applying that.

## No game titles on this site

Nothing published here names a specific game, in prose, in a table, in an
example file name or in a MAME short name. Compatibility is stated by **arcade
board** instead — which is also the more accurate unit, since the board and the
core decide whether something is playable.

This is deliberate. QuestGun supplies no content and endorses none, and a store
reviewer reading a list of titles next to performance figures will draw a
conclusion about what the app is for. Keep it that way when adding results:
"Namco System 22 holds full speed", never the name of the game that proved it.

## Publishing — read this before pushing

**There are two repos on the account and only one of them is the website.**

- `sludgesoft-a11y/sludgesoft-a11y.github.io` — **this is the live site**, at
  <https://sludgesoft-a11y.github.io/>. GitHub serves a user site only from a
  repo named exactly `<username>.github.io`.
- `sludgesoft-a11y/sludgesoft.github.io` — a misnamed spare. Pages is not
  enabled on it. Because the name does not match the account handle, Pages would
  serve it as a *project* site under `/sludgesoft.github.io/`, not at the root.

This working copy's `origin` points at the **misnamed** one. Repoint it before
pushing, or the site will not update:

```bash
git remote set-url origin https://github.com/sludgesoft-a11y/sludgesoft-a11y.github.io.git
```

Then push. The live repo already has a `main` with its own history, so the first
push from here needs reconciling — check `git log origin/main` before choosing
between a merge and a force push.

Pages settings for the live repo: **Settings → Pages** → Source *Deploy from a
branch*, branch `main`, folder `/ (root)`. Pushing to `main` redeploys within a
minute or two.

## Notes

- Colours and the reticle mark are lifted from QuestGun's own branding
  (`tools/make_icons.py` in that repo) so the site and the app agree.
- There is deliberately no link to a QuestGun source repo: none is public. Do
  not add one back until `github.com/sludgesoft-a11y/QuestGun` actually exists,
  or store reviewers will hit a 404.
- Status is written as "in development — not yet released" on `index.html`.
  Update that line when it ships.
- Support address is `sludgesoft@gmail.com`, and it appears on `index.html`,
  `questgun.html`, `support.html`, `privacy.html` and `terms.html`. Change it in
  all five.
