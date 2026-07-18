<p align="center">
  <a href="https://letsplay.cafe"><img src="assets/banner.png" alt="Letsplay Cafe — play together anywhere, instantly" width="830"></a>
</p>

<p align="center">
  <a href="https://letsplay.cafe"><b>▶&nbsp; Play now at letsplay.cafe</b></a>
  &nbsp;·&nbsp;
  <a href="https://letsplay.cafe/about">About</a>
</p>

---

**Letsplay Cafe** is home to tabletop and party games you can play digitally with any group of friends (or foes!). No apps, no downloads, no signups — start a game and send out invite links. It runs great on phones, tablets, PCs, and even Chromecast to a smart TV for that around-the-table feel.

<p align="center">
  <a href="https://letsplay.cafe"><img src="assets/home.png" alt="The Letsplay Cafe lobby" width="720"></a>
</p>

## 🎲 The games

| | |
|---|---|
| **Peer Review** | A party card game that brings out the worst in everyone. Answer prompts, get judged, and find out who is the most horrible among you. |
| **Millenial Madness** | Be the first of your friends to own a house, or drink your sorrows away trying. A board game for up to 4 players! |

More games are always brewing ☕

## ⚙️ Under the hood

Letsplay is a real-time multiplayer platform built end-to-end in this org:

![Svelte](https://img.shields.io/badge/Svelte_5-FF3E00?logo=svelte&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?logo=typescript&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?logo=fastapi&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?logo=redis&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?logo=kubernetes&logoColor=white)
![AWS](https://img.shields.io/badge/AWS_EKS-232F3E?logo=amazonwebservices&logoColor=white)
![Playwright](https://img.shields.io/badge/Playwright-2EAD33?logo=playwright&logoColor=white)

```mermaid
flowchart LR
    B["🧑‍🤝‍🧑 Players' browsers"]
    subgraph EKS["☸️ Kubernetes (EKS)"]
        A["App<br/>Svelte 5 + FastAPI"]
        G["Game server pods<br/>websocket framework"]
    end
    DB[("PostgreSQL")]
    B -- "accounts, lobbies, records" --> A
    B == "live game state (websockets)" ==> G
    G -- "session results" --> A
    A --- DB
```

The app owns accounts, matchmaking, and game records; each live session runs on a game-server pod that syncs state to every player over websockets. Every branch gets its own auto-expiring preview environment of the full stack, and Playwright drives end-to-end browser tests of real multiplayer sessions in CI.

---

<p align="center">
  <sub>Our repos are private — this page is the public face. Come play instead: <a href="https://letsplay.cafe"><b>letsplay.cafe</b></a> ☕</sub>
</p>
