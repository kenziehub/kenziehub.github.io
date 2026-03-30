# Project Context

Project is a Hugo site using the Blowfish theme at `/Users/kenziew/projects/kenziehub.github.io`.

## Current Live Content Structure

- [`content/_index.md`](/Users/kenziew/projects/kenziehub.github.io/content/_index.md): homepage intro copy
- [`content/about.md`](/Users/kenziew/projects/kenziehub.github.io/content/about.md)
- [`content/resume.md`](/Users/kenziew/projects/kenziehub.github.io/content/resume.md)
- [`content/contact.md`](/Users/kenziew/projects/kenziehub.github.io/content/contact.md)
- [`content/projects/_index.md`](/Users/kenziew/projects/kenziehub.github.io/content/projects/_index.md): projects section page
- [`content/projects/project-one.md`](/Users/kenziew/projects/kenziehub.github.io/content/projects/project-one.md)
- [`content/projects/project-two.md`](/Users/kenziew/projects/kenziehub.github.io/content/projects/project-two.md)
- [`content/projects/project-three.md`](/Users/kenziew/projects/kenziehub.github.io/content/projects/project-three.md)

## Menu Config

- [`config/_default/menus.en.toml`](/Users/kenziew/projects/kenziehub.github.io/config/_default/menus.en.toml)
- Main nav is `Projects`, `About`, `Resume`, `Contact`
- `/admin` was removed from live content

## Blowfish And Site Config

- [`config/_default/params.toml`](/Users/kenziew/projects/kenziehub.github.io/config/_default/params.toml)
- `mainSections = ["projects"]`
- homepage uses `layout = "profile"`
- homepage project cards are enabled with `showRecent = true`, `cardView = true`
- `showRecentItems = 12` so homepage shows all current project pages
- `showMoreLink = false`
- article meta disabled:
  - `showDate = false`
  - `showReadingTime = false`
  - `showWordCount = false`
  - `showAuthor = false`
  - `showTableOfContents = false`
  - `sharingLinks = []`
- footer theme attribution already off

## Homepage Recent Cards Override

- [`layouts/partials/recent-articles/main.html`](/Users/kenziew/projects/kenziehub.github.io/layouts/partials/recent-articles/main.html)
- This custom override removes the Blowfish heading and the `Show More` button while still rendering the project cards

## Language And Profile Config

- [`config/_default/languages.en.toml`](/Users/kenziew/projects/kenziehub.github.io/config/_default/languages.en.toml)
- Author/profile text changed from Blowfish defaults to Kenzie-specific content
- Profile still uses `img/avatar.png`

## Extra Override

- [`i18n/en.yaml`](/Users/kenziew/projects/kenziehub.github.io/i18n/en.yaml)
- Contains `shortcode.recent_articles: "Recent Projects"`, but this label is effectively unused now because the recent-articles partial override removed the heading

## Important History

- `About`, `Resume`, and `Contact` were converted from section-style files to single markdown pages
- `Projects` remains a section because it owns child pages
- `content/admin/index.md` was deleted and `content/admin/` removed
- `content/resume/_index.md` was deleted and replaced by `content/resume.md`
- empty leftover dirs for old section pages were removed
- there is still a non-live `portfolio/` folder with old imported migration markdown; it is not used by Hugo
- `public/` contains stale generated output from earlier states until rebuilt, but live source is correct
- `hugo list all` currently shows only home, about, contact, resume, projects, and the three project pages

## Known Issue

- Hugo warns about a Blowfish module compatibility mismatch with the local Hugo version (`0.141.0/0.157.0 extended` mentioned by the theme vs local `0.159.1`). Builds still work, but if rendering looks strange this is the next thing to investigate.

## Likely Next Tasks

- replace placeholder project content in the three project markdown files
- add project images or front matter for better cards
- clean or delete the unused `portfolio/` folder
- clean stale `public/` output if desired
