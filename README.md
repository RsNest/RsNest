<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0d0d0d,40:001833,80:00264d,100:0d0d0d&height=180&section=header&text=%3E_%20RUSLAN&fontColor=00eeff&fontSize=58&fontAlignY=45&desc=DevOps+Engineer+%C2%B7+SRE+%C2%B7+Go+Developer&descFontColor=0099bb&descSize=18&descAlignY=68" width="100%"/>

<br/>

[![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=15&pause=900&color=00EEFF&background=00000000&center=true&vCenter=true&width=720&lines=%24+whoami+%E2%86%92+DevOps+%2F+SRE+%2F+Go+Dev;%24+kubectl+get+pods+-A+%7C+grep+-v+Running+%23+0+issues;%24+argocd+app+sync+production+--force+%E2%9C%94;%24+terraform+plan+%7C+grep+%220+to+destroy%22+%E2%9C%94;%24+./zeroproxy+--protocol+vless+--reality+on+%F0%9F%9F2;%24+go+build+-o+bin%2Fservice+.%2F...+%E2%9C%94;%24+echo+%22automate+everything.+monitor+relentlessly.%22)](https://git.io/typing-svg)

<br/>

![](https://img.shields.io/badge/CPU-12%25-00eeff?style=flat-square&labelColor=0d1117&logo=linux&logoColor=00eeff)
![](https://img.shields.io/badge/MEM-28%25-00eeff?style=flat-square&labelColor=0d1117)
![](https://img.shields.io/badge/NET-3.2_KB%2Fs-00eeff?style=flat-square&labelColor=0d1117)
![](https://img.shields.io/badge/UPTIME-99.97%25-00eeff?style=flat-square&labelColor=0d1117)
![](https://img.shields.io/badge/STATUS-nominal-00cc44?style=flat-square&labelColor=0d1117)

</div>

<br/>

---

<table width="100%">
<tr>
<td width="50%" valign="top">

## `> PROFILE`

```yaml
# /etc/ruslan/config.yaml
---
role:
  - DevOps Engineer
  - SRE
  - Go Developer

location   : "Helsinki / Remote"
experience : "Production @ scale"
learning   : "Go · Android"

focus:
  - Reliability
  - Automation
  - Anti-censorship tools

motto: >
  Automate everything.
  Monitor relentlessly.
```

</td>
<td width="50%" valign="top">

## `> SRE RUNBOOK`

```
╔══════════════════════════════════════╗
║  SLI / SLO    ▓▓▓▓▓▓▓▓▓▓  measure  ║
║  ERROR BUDGET ▓▓▓▓▓▓▓▓░░  balance  ║
║  TOIL →  /dev/null        automate  ║
║  BLAMELESS POSTMORTEM     learn     ║
║  CHAOS ENGINEERING        harden    ║
╠══════════════════════════════════════╣
║  UPTIME  ████████████████  99.97%  ║
║  DEPLOYS ██████████░░░░░░  12/day  ║
║  MTTR    █████░░░░░░░░░░░  < 5min  ║
╚══════════════════════════════════════╝
```

</td>
</tr>
</table>

<br/>

---

## `> WHAT I'M SHIPPING`

<div align="center">

| STATUS | PROJECT | STACK |
|:---:|---|---|
| 🟢 | **ZeroRoute** — Android VPN app | VLESS · REALITY · Anti-DPI · Jetpack Compose |
| 🟢 | **Proxy cascade** — RU → EU bypass | Xray-core · nginx SNI · BBR · iptables |
| 🟡 | **Telegram TLS hardening** | TlsSocket patch · Chrome 131 ClientHello |
| 🔵 | **Go OSINT toolkit** | Go · in progress |

</div>

<br/>

---

## `> TOOLSET`

<div align="center">

**ORCHESTRATION & DEPLOYMENT**

[![Skills](https://skillicons.dev/icons?i=kubernetes,docker,helm,ansible,terraform&theme=dark&perline=5)](https://skillicons.dev)

<br/>

**LANGUAGES & TOOLING**

[![Skills](https://skillicons.dev/icons?i=go,python,bash,git,gitlab,nginx,linux&theme=dark&perline=7)](https://skillicons.dev)

<br/>

**DATA & MESSAGING**

[![Skills](https://skillicons.dev/icons?i=redis,postgres,kafka,rabbitmq&theme=dark&perline=4)](https://skillicons.dev)

<br/>

**OBSERVABILITY**

[![Skills](https://skillicons.dev/icons?i=grafana,prometheus&theme=dark&perline=2)](https://skillicons.dev)

<br/>

[![ArgoCD](https://img.shields.io/badge/ArgoCD-EF7B4D?style=for-the-badge&logo=argo&logoColor=white&labelColor=0d1117)](https://argoproj.github.io)
[![Nomad](https://img.shields.io/badge/Nomad-00CA8E?style=for-the-badge&logo=hashicorp&logoColor=white&labelColor=0d1117)](https://www.nomadproject.io)
[![Loki](https://img.shields.io/badge/Loki-F5A623?style=for-the-badge&logo=grafana&logoColor=white&labelColor=0d1117)](https://grafana.com/oss/loki)
[![MinIO](https://img.shields.io/badge/MinIO-C72E49?style=for-the-badge&logo=minio&logoColor=white&labelColor=0d1117)](https://min.io)
[![Xray](https://img.shields.io/badge/Xray_Core-00eeff?style=for-the-badge&labelColor=0d1117)](#)

</div>

<br/>

---

## `> ARCHITECTURE`

<div align="center">

```
  ┌──────────┐     push      ┌──────────────┐    trigger    ┌───────────────────┐
  │  DEV     │ ────────────► │  GitLab CI   │ ────────────► │  Artifact Registry│
  └──────────┘               └──────────────┘               └────────┬──────────┘
                                                                      │ pull
                                                                      ▼
  ┌─────────────────────────────────────────────────────────────────────────────┐
  │                          ArgoCD  (GitOps)  🔁 continuous sync               │
  └────────────────────────────────┬────────────────────────────────────────────┘
                     ┌─────────────┴──────────────┐
                     ▼                            ▼
            ┌─────────────────┐         ┌──────────────────┐
            │  K8s Cluster    │         │  Nomad Cluster   │
            └────────┬────────┘         └────────┬─────────┘
                     └──────────────┬────────────┘
                                    ▼
                         ┌──────────────────────┐
                         │  Prometheus  ·  Loki  │
                         │  Grafana  ·  Alerts 🔔 │
                         └──────────────────────┘
```

```
  CLIENT → [RU Entry: nginx SNI · BBR] ──VLESS+REALITY──► [EU Xray: TUIC·Hysteria2] → 🌍
```

</div>

<br/>

---

## `> STATS`

<div align="center">

[![trophy](https://github-profile-trophy.vercel.app/?username=RsNest&theme=nord&no-frame=true&margin-w=8&column=7)](https://github.com/ryo-ma/github-profile-trophy)

<br/>

<img height="170em" src="https://github-readme-stats.vercel.app/api?username=RsNest&show_icons=true&theme=nord&include_all_commits=true&count_private=true&hide_border=true&bg_color=0d1117&title_color=00eeff&icon_color=00aaff&text_color=88aabb"/>
&nbsp;
<img height="170em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=RsNest&layout=compact&langs_count=8&theme=nord&hide_border=true&bg_color=0d1117&title_color=00eeff&text_color=88aabb"/>

<br/><br/>

<img src="https://streak-stats.demolab.com?user=RsNest&theme=nord&hide_border=true&background=0D1117&stroke=00aaff&ring=00eeff&fire=00ccff&currStreakLabel=00eeff&sideLabels=00aacc&dates=446677&currStreakNum=00eeff&sideNums=00ccff"/>

<br/><br/>

[![Activity Graph](https://github-readme-activity-graph.vercel.app/graph?username=RsNest&theme=react-dark&bg_color=0d1117&color=00eeff&line=0077cc&point=00eeff&area=true&hide_border=true)](https://github.com/ashutosh00710/github-readme-activity-graph)

</div>

<br/>

---

## `> CONTRIBUTIONS`

<div align="center">

![Snake animation](https://raw.githubusercontent.com/RsNest/RsNest/output/github-contribution-grid-snake-dark.svg)

</div>

<br/>

---

## `> CONTACT`

<div align="center">

[![Telegram](https://img.shields.io/badge/Telegram-nadzerateli-0d1117?style=for-the-badge&logo=telegram&logoColor=00eeff&labelColor=0d1117)](https://t.me/nadzerateli)
[![GitHub](https://img.shields.io/badge/GitHub-RsNest-0d1117?style=for-the-badge&logo=github&logoColor=00eeff&labelColor=0d1117)](https://github.com/RsNest)

</div>

<br/>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0d0d0d,40:00264d,80:001833,100:0d0d0d&height=100&section=footer&text=automate+%C2%B7+monitor+%C2%B7+iterate&fontColor=0077aa&fontSize=16&fontAlignY=65" width="100%"/>
