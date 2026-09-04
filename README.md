<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:0f2027,50:203a43,100:2c5364&height=210&section=header&text=Xin%20Shuo%20Liu&fontSize=52&fontColor=ffffff&animation=fadeIn&fontAlignY=34&desc=Software%20Engineering%20Student%20%C2%B7%20Montr%C3%A9al&descAlignY=54&descSize=16" alt="header" />

<p align="center">
  <a href="https://github.com/xinshuoliu">
    <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=500&size=21&duration=3400&pause=900&color=58A6FF&center=true&vCenter=true&width=640&lines=Data+in%2C+something+useful+out.;Python+%2F+Java+%2F+React+%2F+C;I+build+small+tools+end+to+end;Currently+deep+in+backend+%2B+LLM+evaluation" alt="typing" />
  </a>
</p>

<p align="center">
  <a href="mailto:xinshuoliu88@gmail.com"><img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="email" /></a>
  <a href="https://www.linkedin.com/in/xin-shuo-liu-67234b189/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="linkedin" /></a>
</p>

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=xinshuoliu&label=Profile%20views&color=0e75b6&style=flat-square" alt="views" />
  <a href="https://github.com/xinshuoliu?tab=followers"><img src="https://img.shields.io/github/followers/xinshuoliu?label=Followers&style=flat-square&color=0e75b6" alt="followers" /></a>
  <a href="https://urfinance.streamlit.app/"><img src="https://img.shields.io/badge/live%20demo-urfinance-FF4B4B?style=flat-square&logo=streamlit&logoColor=white" alt="live demo" /></a>
</p>

<br>

## 👋 whoami

|  |  |
|:--|:--|
| 🎓 | Software engineering student in Montréal, Québec |
| 🛠️ | I learn by building: finance tooling, aggregators, web apps |
| 🌱 | Going deeper on backend systems and data pipelines |
| 🧪 | Learning to *measure* LLM features instead of eyeballing them |
| 💬 | Français · English · 中文 |
| 🎯 | Open to internships and collaboration |

<br>

## 🧰 Toolbox

<p align="center">
  <img src="https://skillicons.dev/icons?i=python,java,c,js,react,php,mysql,sqlite&theme=dark" alt="stack row one" /><br>
  <img src="https://skillicons.dev/icons?i=docker,git,github,vite,maven,html,css&theme=dark" alt="stack row two" />
</p>

<br>

## 🚀 What I am building

<table>
<tr>
<td width="50%" valign="top">

### 💸 [Finance](https://github.com/xinshuoliu/Finance)

`Python` `Streamlit` `Anthropic API`

Personal finance dashboard. Drop in a bank CSV and every transaction gets categorized through a **cache → rules → LLM cascade**, so the cheap paths run first and the model only ever sees what the rules could not resolve. Budgets, recurring payment detection, plain English querying.

Ships with an eval harness, so accuracy is a number rather than a vibe.

**🔗 [urfinance.streamlit.app](https://urfinance.streamlit.app/)**

</td>
<td width="50%" valign="top">

### 🔍 [Job_Hunter](https://github.com/xinshuoliu/Job_Hunter)

`Java 21` `Maven` `SQLite` `Docker`

Multi source job aggregator. Polls Adzuna and Arbeitnow, filters by keyword, salary and location, deduplicates on normalized title plus company, then pushes matches to Discord, email or console.

New sources plug in behind a `JobProvider` interface. Rate limits persist across restarts, and nothing is marked delivered until every channel confirms.

<img src="https://github.com/xinshuoliu/Job_Hunter/actions/workflows/ci.yml/badge.svg" alt="ci status" />

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 🎬 [Movie_App](https://github.com/xinshuoliu/Movie_App)

`React 19` `Vite` `React Router`

Movie browser on a public API. Search, client side routing, context driven state, and a services layer that keeps fetch logic out of the components.

</td>
<td width="50%" valign="top">

### 🎟️ [TCH056_Travail_de_session](https://github.com/xinshuoliu/TCH056_Travail_de_session)

`PHP` `MySQL` `Docker`

Full stack event site with a hand rolled router, account creation and sessions, and a real SQL schema with seed data. No framework, on purpose.

</td>
</tr>
</table>

<details>
<summary><b>🧠 How the Finance categorizer actually decides (click to expand)</b></summary>

<br>

```mermaid
flowchart LR
    A["Bank CSV"] --> B["normalize"]
    B --> C{"seen before?"}
    C -->|hit| Z["category"]
    C -->|miss| D{"rule matches?"}
    D -->|yes| Z
    D -->|no| E["ask Claude"]
    E --> F["write to cache"]
    F --> Z
    Z --> G["budgets"]
    Z --> H["recurring"]
    Z --> I["ask in English"]

    style A fill:#1f6feb,stroke:#58a6ff,color:#fff
    style E fill:#d97757,stroke:#f0a58a,color:#fff
    style Z fill:#238636,stroke:#3fb950,color:#fff
```

Every transaction takes the cheapest path that can answer it. The cache catches repeats, hand written rules catch the obvious merchants, and only genuine unknowns cost an API call. Results are written back to the cache, so the expensive path keeps shrinking.

</details>

<details>
<summary><b>📚 Coursework worth a look</b></summary>

<br>

**[TP1_INF111](https://github.com/xinshuoliu/TP1_INF111)** · `Java`
<br>Client/server library management system, split into independent client and server modules.

</details>

<br>

## 📈 The numbers

<sub>These five cards are not hotlinked from somebody else's server. A GitHub Action
renders them nightly and commits the SVGs into this repo, so they cannot break when a
free hosting tier goes down.</sub>

<p align="center">
  <img width="86%" src="./profile-summary-card-output/tokyonight/0-profile-details.svg" alt="profile details" />
</p>

<p align="center">
  <img width="49%" src="./profile-summary-card-output/tokyonight/1-repos-per-language.svg" alt="repos per language" />
  <img width="49%" src="./profile-summary-card-output/tokyonight/2-most-commit-language.svg" alt="most committed language" />
</p>

<p align="center">
  <img width="49%" src="./profile-summary-card-output/tokyonight/3-stats.svg" alt="summary stats" />
  <img width="49%" src="./profile-summary-card-output/tokyonight/4-productive-time.svg" alt="productive time" />
</p>

<p align="center">
  <img src="https://streak-stats.demolab.com?user=xinshuoliu&theme=tokyonight&hide_border=true" alt="commit streak" />
</p>

<br>

## 🧊 A year of commits, in 3D

<p align="center">
  <img width="88%" src="./profile-3d-contrib/profile-night-rainbow.svg" alt="3d contribution calendar" />
</p>

<br>

## 🐍 Watch a snake eat my contributions

<div align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/xinshuoliu/xinshuoliu/output/github-snake-dark.svg" />
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/xinshuoliu/xinshuoliu/output/github-snake.svg" />
    <img alt="snake eating my contribution graph" src="https://raw.githubusercontent.com/xinshuoliu/xinshuoliu/output/github-snake.svg" />
  </picture>
</div>

<br>

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:2c5364,50:203a43,100:0f2027&height=130&section=footer" alt="footer" />
