# Setup checklist

Everything in this folder is meant to live in a **public** repo named exactly
`xinshuoliu/xinshuoliu`. GitHub treats a repo named after your username as your
profile README and renders it on <https://github.com/xinshuoliu>.

## 1. Create the repo

```bash
cd xinshuoliu
git init
git add .
git commit -m "feat: profile readme"
git branch -M main
git remote add origin https://github.com/xinshuoliu/xinshuoliu.git
git push -u origin main
```

If you create the repo through the GitHub web UI first, make sure it is **public**
and that you do **not** let GitHub add a README, otherwise the push will conflict.

## 2. Contact links

Both contact badges at the top of `README.md` are filled in: the mailto points at
`xinshuoliu88@gmail.com` and the LinkedIn button at `xin-shuo-liu-67234b189`.

## 3. Let the Actions run once

Three workflows live in `.github/workflows/`. The generated SVGs are already committed,
so the page is complete the moment you push. The workflows exist to keep them fresh:
the snake runs on push and nightly, the other two run nightly or when you trigger them
from the Actions tab.

| Workflow | What it produces | Where it lands |
|:--|:--|:--|
| `snake.yml` | Snake eating your contribution graph, light and dark | `output` branch |
| `3d-contrib.yml` | Isometric 3D calendar of the last year | `profile-3d-contrib/` on `main` |
| `summary-cards.yml` | Language, commit and productive time cards | `profile-summary-card-output/` on `main` |

> Nothing is blank on first push: the summary cards, the 3D calendar and both snake
> SVGs are committed in this repo already. The workflows only refresh them.

If Actions are disabled on a brand new repo, enable them under
**Settings → Actions → General → Allow all actions**. Nothing here needs a personal
access token; the built in `GITHUB_TOKEN` is enough.

## 4. Optional polish

* Your GitHub profile still has no **bio** or **location** set. The README does not
  fill in the sidebar, so set those under <https://github.com/settings/profile>.
* `Movie_App` has a README whose entire contents are `,,,`. Worth fixing, since the
  profile now points people at it.
* None of your five repos have a **description** or **topics**. Those show up in
  search and on the repo cards.

## What is in the README, and where each piece comes from

| Feature | Source | Needs an Action | Checked live |
|:--|:--|:--|:--|
| Waving gradient header and footer | capsule render | no | 200 |
| Animated typing subtitle | readme typing svg | no | 200 |
| Profile view counter | komarev ghpvc | no | 200 |
| Contact and follower badges | shields.io | no | 200 |
| Skill icon rows | skillicons.dev | no | 200 |
| Two column project table | plain HTML | no | n/a |
| Mermaid flowchart of the Finance cascade | GitHub native mermaid | no | n/a |
| Collapsible sections | HTML `<details>` | no | n/a |
| Five summary cards | vn7n24fzkq action | **yes** | self hosted |
| Commit streak | streak stats on demolab | no | 200 |
| 3D contribution calendar | yoshi389111 action | **yes** | self hosted |
| Snake animation, theme aware | Platane/snk action | **yes** | self hosted |

Every external URL above was requested before this README shipped, and every one
returned a real SVG.

## Three popular widgets are deliberately missing

While checking the links, three of the widgets that show up in almost every profile
README turned out to be **down right now**, not slow or rate limited but returning
hard errors:

| Widget | Status |
|:--|:--|
| `github-readme-stats.vercel.app` | `503 DEPLOYMENT_PAUSED` |
| `github-profile-trophy.vercel.app` | `402 DEPLOYMENT_DISABLED` |
| `github-readme-activity-graph.vercel.app` | `402 DEPLOYMENT_DISABLED` |

They are free Vercel deployments that have hit their limits. Any profile using them is
currently showing broken image icons. That is exactly why the stats section here uses
the Action generated cards committed into your own repo instead: nobody else's billing
can take them offline.

If those services come back and you want the classic stats card, add:

```markdown
<img src="https://github-readme-stats.vercel.app/api?username=xinshuoliu&show_icons=true&theme=tokyonight&hide_border=true&include_all_commits=true" />
```

Working community mirrors also exist today, for example
`githubreadmestats.vercel.app`, but they are somebody else's free tier too, so treat
them as temporary.

## The rarest trick in here

The snake block uses a `<picture>` element with `prefers-color-scheme`, so it swaps
palette automatically when a visitor is in GitHub dark mode:

```html
<picture>
  <source media="(prefers-color-scheme: dark)"  srcset="...github-snake-dark.svg" />
  <source media="(prefers-color-scheme: light)" srcset="...github-snake.svg" />
  <img src="...github-snake.svg" />
</picture>
```

That works in any GitHub README and almost nobody uses it. The mermaid flowchart is
the second one: GitHub renders `mermaid` code fences natively, so the diagram is live text
in the file rather than a screenshot that goes stale.
