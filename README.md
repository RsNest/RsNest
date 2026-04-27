<div align="center">

<!-- Загрузи banner.svg в корень репо RsNest/RsNest -->
<img src="https://raw.githubusercontent.com/RsNest/RsNest/main/banner.svg" width="100%"/>

<br/>

[![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=15&pause=800&color=00FF41&background=00000000&center=true&vCenter=true&width=700&lines=%24+whoami+%E2%86%92+DevOps+%2F+SRE+%2F+Go+Dev;%24+kubectl+get+pods+-A+%7C+grep+-v+Running+%23+0+issues;%24+argocd+app+sync+production+--force+%E2%9C%94;%24+terraform+plan+%7C+grep+%220+to+destroy%22+%E2%9C%94;%24+./zeroproxy+--protocol+vless+--reality+on+%F0%9F%9F%A2;%24+go+build+-o+bin%2Fservice+.%2F...+%E2%9C%94;%24+echo+%22automate+everything.+monitor+relentlessly.%22)](https://git.io/typing-svg)

<br/>

![](https://img.shields.io/badge/CPU-12%25-00ff41?style=flat-square&labelColor=111111&logo=linux&logoColor=00ff41)
![](https://img.shields.io/badge/MEM-28%25-00ff41?style=flat-square&labelColor=111111)
![](https://img.shields.io/badge/NET-3.2_KB%2Fs-00ff41?style=flat-square&labelColor=111111)
![](https://img.shields.io/badge/UPTIME-99.97%25-00ff41?style=flat-square&labelColor=111111)
![](https://img.shields.io/badge/STATUS-nominal-00ff41?style=flat-square&labelColor=111111)

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

## `> WHAT I'M SHIPPING NOW`

```
╭─────────────────────────────────────────────────────────────────╮
│  🟢  ZeroRoute — Android VPN                                    │
│      VLESS / REALITY · TLS fingerprint · Anti-DPI · Compose UI │
│                                                                  │
│  🟢  Proxy cascade   RU entry ──VLESS──► EU backend             │
│      Xray-core · nginx SNI routing · BBR · iptables NAT         │
│                                                                  │
│  🟡  Telegram Desktop TLS hardening                             │
│      Patching TlsSocket · Chrome 131 ClientHello fingerprint    │
│                                                                  │
│  🔵  Go OSINT toolkit  [in progress...]                         │
╰─────────────────────────────────────────────────────────────────╯
```

<br/>

---

## `> TOOLSET`

<div align="center">

**`─── ORCHESTRATION & DEPLOYMENT ───`**

<br/>

[![My Skills](https://skillicons.dev/icons?i=kubernetes,docker,helm,ansible,terraform&theme=dark)](https://skillicons.dev)

<br/>

**`─── LANGUAGES & TOOLING ───`**

<br/>

[![My Skills](https://skillicons.dev/icons?i=go,python,bash,git,gitlab,nginx,linux&theme=dark)](https://skillicons.dev)

<br/>

**`─── DATABASES & MESSAGING ───`**

<br/>

[![My Skills](https://skillicons.dev/icons?i=redis,postgres,kafka,rabbitmq&theme=dark)](https://skillicons.dev)

<br/>

**`─── OBSERVABILITY ───`**

<br/>

[![My Skills](https://skillicons.dev/icons?i=grafana,prometheus&theme=dark)](https://skillicons.dev)

<br/>

**`─── ALSO WORK WITH ───`**

<br/>

[![ArgoCD](https://img.shields.io/badge/ArgoCD-EF7B4D?style=for-the-badge&logo=argo&logoColor=white&labelColor=111111)](https://argoproj.github.io)
[![Nomad](https://img.shields.io/badge/Nomad-00CA8E?style=for-the-badge&logo=hashicorp&logoColor=white&labelColor=111111)](https://www.nomadproject.io)
[![Xray](https://img.shields.io/badge/Xray_Core-00ff41?style=for-the-badge&labelColor=111111)](#)
[![Loki](https://img.shields.io/badge/Loki-F5A623?style=for-the-badge&logo=grafana&logoColor=white&labelColor=111111)](https://grafana.com/oss/loki)
[![MinIO](https://img.shields.io/badge/MinIO-C72E49?style=for-the-badge&logo=minio&logoColor=white&labelColor=111111)](https://min.io)

</div>

<br/>

---

## `> SYSTEM ARCHITECTURE`

<div align="center">

```
  ┌──────────┐     push      ┌──────────────┐    trigger    ┌───────────────────┐
  │  DEV     │ ────────────► │  GitLab CI   │ ────────────► │  Artifact Registry│
  └──────────┘               └──────────────┘               └────────┬──────────┘
                                                                      │ pull
                                                                      ▼
  ┌─────────────────────────────────────────────────────────────────────────────┐
  │                          ArgoCD  (GitOps)                                   │
  │   git diff → reconcile → apply                     🔁 continuous sync       │
  └────────────────────────────────┬────────────────────────────────────────────┘
                                   │ deploy
                     ┌─────────────┴──────────────┐
                     │                            │
                     ▼                            ▼
            ┌─────────────────┐         ┌──────────────────┐
            │  K8s Cluster    │         │  Nomad Cluster   │
            └────────┬────────┘         └────────┬─────────┘
                     └──────────────┬────────────┘
                                    │ metrics / logs
                                    ▼
                         ┌──────────────────────┐
                         │  Prometheus  ·  Loki  │
                         │  Grafana dashboards   │
                         │  Telegram alerts  🔔  │
                         └──────────────────────┘
```

</div>

<br/>

---

## `> PROXY CASCADE`

<div align="center">

```
  CLIENT
    │
    ▼
  ┌──────────────────────┐
  │  RU Entry Server     │  ← nginx stream · SNI routing
  │  Let's Encrypt TLS   │    BBR · conntrack tuning
  └──────────┬───────────┘
             │  VLESS + REALITY (xtls-rprx-vision)
             ▼
  ┌──────────────────────┐
  │  EU Backend (Xray)   │  ← TUIC v5 · Hysteria2
  └──────────────────────┘
             │
             ▼
         INTERNET  🌍
```

</div>

<br/>

---

## `> gh stats --user RsNest`

<div align="center">

[![trophy](https://github-profile-trophy.vercel.app/?username=RsNest&theme=matrix&no-frame=true&margin-w=6&rank=SECRET,SSS,SS,S,AAA,AA,A,B)](https://github.com/ryo-ma/github-profile-trophy)

<br/>

<img height="175em" src="https://github-readme-stats.vercel.app/api?username=RsNest&show_icons=true&theme=chartreuse-dark&include_all_commits=true&count_private=true&hide_border=true&bg_color=0d0d0d&title_color=00ff41&icon_color=00ff41&text_color=88bb88"/>
&nbsp;
<img height="175em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=RsNest&layout=compact&langs_count=8&theme=chartreuse-dark&hide_border=true&bg_color=0d0d0d&title_color=00ff41&text_color=88bb88"/>

<br/><br/>

<img src="https://streak-stats.demolab.com?user=RsNest&theme=dark&hide_border=true&background=0D0D0D&stroke=00ff41&ring=00ff41&fire=00cc33&currStreakLabel=00ff41&sideLabels=00ff41&dates=557755&currStreakNum=00ff41&sideNums=00ff41"/>

</div>

<br/>

---

## `> activity graph`

<div align="center">

[![Activity Graph](https://github-readme-activity-graph.vercel.app/graph?username=RsNest&theme=react-dark&bg_color=0d0d0d&color=00ff41&line=00cc33&point=00ff41&area=true&hide_border=true)](https://github.com/ashutosh00710/github-readme-activity-graph)

</div>

<br/>

---

## `> trace --route contributions`

<div align="center">

![Snake animation](https://raw.githubusercontent.com/RsNest/RsNest/output/github-contribution-grid-snake-dark.svg)

</div>

<br/>

---

## `> ping ruslan.dev`

<div align="center">

[![Telegram](https://img.shields.io/badge/t.me%2Fnadzerateli-Telegram-111111?style=for-the-badge&logo=telegram&logoColor=00ff41&labelColor=111111)](https://t.me/nadzerateli)
[![GitHub](https://img.shields.io/badge/RsNest-GitHub-111111?style=for-the-badge&logo=github&logoColor=00ff41&labelColor=111111)](https://github.com/RsNest)

<br/>

```
[ KEEP CALM AND AUTOMATE EVERYTHING ]
```

</div>
