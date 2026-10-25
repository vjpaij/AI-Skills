# AI-Skills

A comprehensive, curated repository of **854 modular Agent Skills** for modern AI coding assistants, unified across **Claude Code** and **Antigravity**.

## 📁 Structure

```text
AI-Skills/
├── Claude/                  # 854 Skills for Claude Code (~/.claude/skills/)
├── Antigravity/             # 854 Skills for Antigravity (~/.gemini/config/skills/)
├── CATALOGUE.md             # Categorized directory of all 854 skills with descriptions
└── README.md
```

## 🚀 Installation & Setup

### For Claude Code
Copy or symlink the `Claude` folder into your global Claude skills directory:
```bash
# Windows PowerShell
Copy-Item -Path .\Claude\* -Destination "$env:USERPROFILE\.claude\skills\" -Recurse -Force

# macOS / Linux
cp -r ./Claude/* ~/.claude/skills/
```

### For Antigravity
Copy or symlink the `Antigravity` folder into your global Antigravity config directory:
```bash
# Windows PowerShell
Copy-Item -Path .\Antigravity\* -Destination "$env:USERPROFILE\.gemini\config\skills\" -Recurse -Force

# macOS / Linux
cp -r ./Antigravity/* ~/.gemini/config/skills/
```

## 📖 Catalogue & Index

Browse the complete categorized library in [CATALOGUE.md](./CATALOGUE.md), covering:
- AI, Agents & LLM Systems
- Architecture & System Design
- Backend & Microservices
- Frontend, Mobile & Accessibility
- Database & Data Pipelines
- Testing, QA & Reliability
- Security & Compliance
- DevOps, Cloud & CI/CD
- Product, Project & Business Strategy
- Research, Content & Office Automation
