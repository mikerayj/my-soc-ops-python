🌐 [Português (BR)](README.pt_BR.md) | [Español](README.es.md)

<div align="center">

# 🎱 Soc Ops

**A hands-on GitHub Copilot Agent Lab — powered by Social Bingo**

*Mingle. Connect. Ship features with AI.*

[![Python](https://img.shields.io/badge/Python-3.13+-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.115+-009688?logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com/)
[![HTMX](https://img.shields.io/badge/HTMX-1.x-3D72D7?logo=htmx&logoColor=white)](https://htmx.org/)
[![GitHub Copilot](https://img.shields.io/badge/GitHub%20Copilot-Agent%20Mode-181717?logo=github&logoColor=white)](https://github.com/features/copilot)

</div>

---

## What is Soc Ops?

**Soc Ops** is a Social Bingo app for in-person mixers — find people who match the prompts on your board and get **5 in a row** to win. But that's just the starting point.

This repo is the foundation for a ~1 hour **GitHub Copilot Agent Mode** workshop where you'll transform this app into something genuinely impressive — using context engineering, design-first development, custom agents, and test-driven multi-agent workflows.

> **You're not just playing bingo. You're learning how to build with AI.**

---

## 🎯 What You'll Learn

| # | Skill | What you'll do |
|---|-------|----------------|
| 1 | **Context Engineering** | Teach Copilot your codebase with custom instructions |
| 2 | **Agentic Primitives** | Run CLI sessions, cloud agents & custom workflows |
| 3 | **Design-First Development** | Redesign the UI by guiding the AI's creative vision |
| 4 | **Test-Driven Development** | Ship new features with Red → Green → Refactor agents |

---

## 📚 Lab Guide

| Part | Title | Time |
|------|-------|------|
| [**00**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=00-overview) | Overview & Checklist | — |
| [**01**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=01-setup) | Setup & Context Engineering | 15 min |
| [**02**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=02-design) | Design-First Frontend | 15 min |
| [**03**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=03-quiz-master) | Custom Quiz Master | 10 min |
| [**04**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=04-multi-agent) | Multi-Agent Development | 20 min |

> 📝 Prefer offline reading? Lab guides are also in the [`workshop/`](workshop/) folder.

---

## 🚀 Getting Started

### Prerequisites

- VS Code **v1.107+**
- **GitHub Copilot** (Free, Pro, Business, or Enterprise)
- Git · Python 3.13+ · [uv](https://docs.astral.sh/uv/)

> 💡 Use the included **DevContainer** for a zero-setup environment — just open in Codespaces!

### Run Locally

```bash
uv sync
uv run uvicorn app.main:app --reload --host 0.0.0.0 --port 8000
```

Then open [http://localhost:8000](http://localhost:8000) and start the lab at **[Part 00: Overview](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=00-overview)**.

---

## 🛠 Tech Stack

| Layer | Technology |
|-------|-----------|
| Backend | [FastAPI](https://fastapi.tiangolo.com/) + Python 3.13 |
| Templating | [Jinja2](https://jinja.palletsprojects.com/) |
| Frontend interactivity | [HTMX](https://htmx.org/) |
| Dependency management | [uv](https://docs.astral.sh/uv/) |
| Testing | [pytest](https://pytest.org/) |

---

## 🔗 Resources

- [GitHub Copilot Docs](https://code.visualstudio.com/docs/copilot/overview)
- [Awesome Copilot](https://github.com/github/awesome-copilot)
- [VS Code on YouTube](https://www.youtube.com/code)
