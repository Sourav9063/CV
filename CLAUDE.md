# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

CV/Resume repository with multiple formats optimized for tech companies. **Primary file: `index.html`** (Sourav Ahmed). Also serves as a shared template repository for other resumes (e.g., `sayma.html` for Sayma Sultana).

## Quick Reference

**Common Tasks:**
- **Update resume**: Edit `index.html` (always update this first)
- **Generate PDF**: Open `index.html` → Click 🖨️ or Ctrl/Cmd+P → Save as PDF (A4, background graphics enabled)
- **Build LaTeX**: `cd "Sourav Ahmed" && make all`
- **Preview**: Use Live Server at `http://127.0.0.1:5500/index.html`

**File Priority:**
1. `index.html` - Production resume
2. `README.md` / `README_S.md` - Optional reference
3. `resume.tex` (in LaTeX dirs) - If maintaining variants

## Repository Structure

- **Root**: `index.html` (primary), `sayma.html` (Sayma Sultana's resume), markdown/PDF variants, `README.html` (legacy)
- **LaTeX dirs**: `Sourav Ahmed/` (standard), `Sourav Ahmed S/` (short), `Sourav Ahmed All/` (complete)
  - Each has: `resume.tex`, `simple_style.cls`, `Makefile`, `qr/`
- **STUDY/**: Academic variant
- **File suffixes**: `_S` (short), `_All` (complete), `_f` (alt format)

## LaTeX Build

```bash
cd "Sourav Ahmed"  # or "Sourav Ahmed S" / "Sourav Ahmed All"
make all           # Compile and open in evince
make clean         # Remove .latexmk artifacts
# Manual: latexmk -xelatex -output-directory='.latexmk' resume.tex
```

## Styling (index.html)

**Design Specs:**
- Font: Roboto Slab, 9.5pt body, line-height 1.3
- Padding: 0.2in top, 0.4in sides, 0.3in bottom
- Colors: `--color-heading` #0D0D0D, `--color-subheading` #364959, `--color-text` #5A6473, `--color-light` rgba(90,100,115,0.7), `--color-border` #DEDEDE
- Layout: Single-page A4, CSS Grid for Projects/Achievements (1fr 1fr)
- Typography: Reduced font weights (600 for headings/emphasis instead of 700) for refined appearance

**CSS Architecture:**
- CSS variables in `:root`, semantic HTML5 tags, minimal classes (`.grid`, `.gpa` for education)
- Selectors: `header a`, `section > div:has(strong:first-child)`, `#education`, `.grid article`
- Print button: Fixed position top-left with SVG icon, hidden in print mode

**Content Structure:**
1. Header (name, 22pt) → 2. Contact (• separated) → 3. Summary → 4. Experience → 5. Education → 6. Projects → 7. Publications → 8. Achievements

## Content Guidelines

**Formatting:**
- **Bullet separator**: `•` everywhere (contact, tech stacks, dates)
- **Tech stacks**: `using • NextJs • Go • PostgreSQL` (start with `•`)
- **Dates**: In `<em>` tags with `--color-light`
- **Project format**: **Bold name:** description with inline `<span>` tech stack
- **Job format**: Overview paragraph, then project bullets with links
 - **Education format**: Degree on one line `Bachelor of Science in Software Engineering • CGPA: 3.64/4.00`

**Style:**
- Use metrics (40%, 100K+ users, 500+ installs)
- Action verbs: Architected, Engineered, Built, Developed
- Link everything: repos, live projects, publications
- One-page A4, emphasize AI/ML, microservices, real-time systems

## Update Workflow

1. Edit `index.html` (semantic HTML, no inline styles except overrides)
2. Follow `•` separator rules for tech stacks
3. Keep dates in `<em>` tags
4. Optionally sync markdown/LaTeX variants
5. Generate PDF via browser print (🖨️ button or Ctrl/Cmd+P, A4, background graphics on)

## Current Tech Stack & Projects

**Tech**: LLMs (Claude, GPT-4), MCP, NextJs, ReactJs, VueJs, Flutter, Go, Node.js, GraphQL, MongoDB, Socket.IO, Docker, AWS

**Current Roles:**
- **Pathao Ltd** (Dec'24-Present): Dashboard Foundation (NextJs + OpenAPI + Zod + shadcn + RBAC + AI guardrails), Pathao Map (100K+ users), Mission (gamification), Resto Web, Loop, GariKoi
- **ShellBeeHaken** (Aug'23-Nov'24): Mapage, UUORK, Honnemir, KriyaKarak
- **Open Source**: Flash VSCode (500+ installs, 5-star)

## Important Links

**Pathao**: https://maps.pathao.io/, https://restoweb.p-stageenv.xyz/
**ShellBeeHaken**: https://mapage.net/stylist/landing-page, https://shellbeehaken.com/portfolio/8, https://shellbeehaken.com/portfolio/6, https://kriyakarak.com/
**Projects**: https://github.com/Sourav9063/uBookSharing, https://github.com/Sourav9063/flash-vscode, https://sourav9063.github.io/hall_management_rf/, https://github.com/Sourav9063/watchtogether, https://searchftp.vercel.app/
**Publications**: https://arxiv.org/abs/2403.20084
**Contact**: https://www.linkedin.com/in/sourav-ahmed/, https://sourav9063.github.io/, https://github.com/Sourav9063

## Design Best Practices

**Typography & Visual Hierarchy:**
- Use font-weight 600 for headings and emphasis (not 700) to maintain refined appearance
- Use font-weight 500 for secondary text (degree names in education)
- Use font-weight 700 only for critical emphasis (GPAs, key metrics)
- Maintain consistent color usage: headings (#364959), body text (default), light text (rgba(90,100,115,0.7))

**Print Optimization:**
- Include `@page { size: A4; margin: 0; }` for proper PDF generation
- Use `page-break-after: avoid` on headings to prevent orphaned sections
- Hide interactive elements (print button) with `@media print`
- Enable background graphics in browser print settings for colors/borders

**Content Enhancement:**
- Use action verbs: Architected, Engineered, Built, Developed, Conducted, Achieved
- Include quantifiable metrics and achievements
- Link to live projects, GitHub repos, publications
- Emphasize modern tech stack (AI/ML, cloud, microservices)
- Your are an Associate Software Engineer. Try to learn the best practice and knowledge needed to implement the given instruction. You are trying to impress Senior Software Engineer who is verifying your code.