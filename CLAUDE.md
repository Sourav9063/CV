# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This is a CV/Resume repository for Sourav Ahmed containing multiple resume formats and versions optimized for top tech companies (FAANG, startups) both abroad and locally. The primary production-ready resume is `index.html`.

## Repository Structure

- **Root directory**: Contains primary resume files in multiple formats
  - **`index.html`**: PRIMARY production resume - optimized single-page HTML for top tech companies
  - `README.md` / `README_S.md`: Markdown versions of the resume (reference/source)
  - `README.html`: Legacy single-column HTML resume with inline styles
  - `README.css` / `README_S.css`: Standalone CSS files for HTML resumes
  - `RESUME.pdf`: Compiled PDF version
  - Various PDF exports: `Sourav_Ahmed.pdf`, `Sourav_Ahmed_S.pdf`, `Sourav_Ahmed_All.pdf`, etc.

- **html/**: Alternative HTML resume layouts
  - `2col.html`: Two-column responsive layout optimized for A4 printing

- **LaTeX directories** (multiple variants):
  - `Sourav Ahmed/`: Standard version
  - `Sourav Ahmed S/`: Shortened version
  - `Sourav Ahmed All/`: Complete version with all projects
  - Each contains:
    - `resume.tex`: LaTeX resume source
    - `simple_style.cls`: Custom LaTeX class file
    - `Makefile`: Build automation
    - `qr/`: QR code assets

- **STUDY/**: Academic-focused resume variant
  - Contains separate markdown and PDF versions optimized for educational contexts

## Build Commands

### LaTeX Resume

Build any LaTeX resume variant:
```bash
cd "Sourav Ahmed"  # or "Sourav Ahmed S" or "Sourav Ahmed All"
make all           # Compiles LaTeX to PDF and opens in evince
make clean         # Removes build artifacts (.latexmk directory)
```

Or manually:
```bash
latexmk -xelatex -output-directory='.latexmk' resume.tex
```

### HTML to PDF

The markdown files can be converted to PDF using online tools. A comment in `README_S.md` indicates:
```
https://md-to-pdf.fly.dev/
```

## Resume Versions

Multiple versions exist for different contexts:

1. **Standard (`README.md`, `Sourav Ahmed/`)**: Full professional experience and projects
2. **Shortened (`README_S.md`, `Sourav Ahmed S/`)**: Condensed version with select projects
3. **All (`Sourav Ahmed All/`)**: Comprehensive version including all work and personal projects
4. **Study (`STUDY/`)**: Academic-focused variant

## Styling Guidelines (index.html)

### Current Design (Optimized for Tech Companies)
- **Font**: Roboto Slab (Google Fonts) - professional serif for readability
- **Base font size**: 9.5pt (body), optimized for A4 single-page fit
- **Line height**: 1.3 for readability
- **Padding**: 0.2in top, 0.4in sides, 0.3in bottom - minimal margins for content density
- **Color scheme** (Modern CSS variables):
  - `--color-heading`: `#0D0D0D` - Main heading (name)
  - `--color-subheading`: `#364959` - Section titles
  - `--color-text`: `#5A6473` - Body text and links
  - `--color-muted`: `#949BA6` - Contact links
  - `--color-light`: `#949BA6` - Dates, dividers, tech stacks
- **A4 optimization**: `@page` rules and print media queries ensure single-page PDF output
- **Two-column layout**: Projects and Achievements sections use CSS Grid (1fr 1fr) for space efficiency
- **Vertical spacing**: Aggressively minimized (1-2pt margins) to maximize content density while maintaining readability
- **Modern CSS approach**: Uses CSS variables, semantic HTML5 tags, minimal classes

### Content Structure (Current Order)
1. **Header**: Name only (centered, 22pt - reduced from 26pt for better spacing)
2. **Contact Info**: LinkedIn • Portfolio • GitHub • Email • Phone • Location (styled with `#949BA6`)
3. **Summary**: Bold professional identity followed by experience highlights with metrics
4. **Experience**: Job title/company with dates (right-aligned, italic, `#949BA6`), overview paragraph, then project bullets with links
5. **Education**: After Experience (standard for experienced professionals)
6. **Projects**: Two-column grid layout with inline tech stacks
7. **Publications**: Research papers with inline tech stack
8. **Achievements & Co-curricular**: Two-column combined section with inline dates

### Content Guidelines
- **Be concise**: Combine sentences, use metrics (40%, 100K+ users, 500+ installs)
- **Use action verbs**: Architected, Engineered, Built, Developed, Integrated
- **Add links**: All projects and companies should have working URLs
- **Overview vs bullets**: Job overview is paragraph text, specific projects are bullets
- **Tech keywords**: Emphasize modern stack (LLMs, microservices, real-time, AI/ML)
- **Bullet separators**: Use `•` (bullet) in all contexts:
  - Contact info: `LinkedIn • Portfolio • GitHub`
  - Tech stacks: Start with `•` then separate each item: `using • NextJs • Go • PostgreSQL`
  - Achievement dates: `teams. • Aug'22` (with space before bullet)
- **Project format**: Bold project names followed by colon, then description with inline tech stack
- **Inline tech stacks**: Projects section uses `<span>` for tech stack on same line as description

## Key Technologies & Experience Highlights

Resume content demonstrates expertise in:
- **AI/ML**: LLMs (Claude, GPT-4), Model Context Protocol (MCP), TensorFlow, NLP
- **Frontend**: NextJs, ReactJs, VueJs, NuxtJs, Flutter, ElectronJs, TypeScript
- **Backend**: GoLang, Node.js, ExpressJs, GraphQL, RESTful APIs
- **Databases**: MongoDB, MySQL, Firebase
- **Real-time**: Socket.IO, WebSocket
- **DevOps**: Docker, AWS Amplify, S3
- **Tools**: VSCode Extensions, Zod (validation)

### Current Roles & Projects (Keep Updated)
- **Pathao Ltd** (Dec'24 - Present): Dashboard Foundation, Pathao Map (100K+ users), Loop, Mission, Resto Web, GariKoi
- **ShellBeeHaken Ltd** (Aug'23 - Nov'24): Mapage, UUORK, Honnemir, KriyaKarak
- **Open Source**: Flash VSCode extension (500+ installs, 5-star rating)

**Recent additions**:
- **Dashboard Foundation**: Enterprise NextJs framework with OpenAPI-driven type generation, Zod validation, shadcn UI, centralized auth/RBAC, and AI guardrails
- **Mission**: Gamification platform with event-based listeners, dashboard for mission entry/phase goal management/analytics

## Modifying Resume Content

**PRIMARY FILE**: `index.html` is the production resume. Update this first.

### CSS Architecture
The resume uses modern CSS best practices:
- **CSS Variables** in `:root` for colors and spacing (easy theme changes)
- **Semantic HTML5**: `<header>`, `<section>`, `<article>` tags
- **Minimal classes**: Only `.grid` for layout; most styling uses element selectors
- **Modern selectors**:
  - `header a` for contact links
  - `section > div:has(strong:first-child)` for job headers
  - `#education`, `#publications` for specific sections
  - `.grid article` for project items

### When Updating Content
1. **Edit `index.html`** - this is the primary production resume
2. Follow bullet separator rules: Always start tech stacks with `•`
3. Use semantic HTML - avoid inline styles except for specific overrides
4. Keep all dates in `<em>` tags styled with `--color-light`
5. Optionally update markdown files (`README.md`) for reference
6. Rebuild LaTeX versions by editing `.tex` files in respective directories if needed
7. Maintain consistency across formats if creating variants
8. Keep dates and metrics synchronized

### Best Practices for Tech Company Resumes
- **Use metrics**: Quantify impact (40% improvement, 100K+ users, 500+ installs)
- **Be concise**: One-page A4 format, no fluff
- **Emphasize modern tech**: AI/ML, microservices, real-time systems, distributed systems
- **Show scale**: User numbers, system complexity, production impact
- **Link everything**: GitHub repos, live projects, publications
- **Overview + bullets**: Job overview as paragraph, projects as bullets
- **Recent first**: Experience in reverse chronological order
- **Education after experience**: For 2+ years experience

## File Naming Conventions

- `_S` suffix: Shortened version
- `_All` suffix: Complete version with all content
- `_f` suffix: Alternate formatting variant
- Spaces in directory names: Use quotes when referencing in commands

## Converting HTML to PDF

To create PDF from `index.html`:
1. Open `index.html` in a browser
2. Click the print button (🖨️) in the top right corner, or press Ctrl/Cmd + P
3. Select "Save as PDF"
4. Ensure "A4" paper size is selected
5. Margins: Default or Minimum
6. Background graphics: Enabled
7. Save as `Sourav_Ahmed.pdf`

The resume is designed to fit perfectly on one A4 page when printed/saved as PDF.

**Print button**:
- Fixed position floating button (🖨️ emoji) in top right
- Uses `all: unset` for clean styling
- Hidden in print/PDF output via `@media print`
- Triggers browser's native print dialog

**Print-specific styling**:
- Print button is hidden (`display: none`)
- Achievements section has additional top padding (0.2in) in print mode
- Page breaks are avoided after section titles and job headers
- Grid layouts prevent breaking across pages

**For live preview during development**:
- Use Live Server extension in VS Code or similar
- View at `http://127.0.0.1:5500/index.html`
- Use Playwright MCP to capture screenshots for validation

## Important Links to Include

When adding new projects, ensure these live links are maintained:
- **Pathao**: https://maps.pathao.io/, https://restoweb.p-stageenv.xyz/
- **ShellBeeHaken**: https://mapage.net/stylist/landing-page, https://shellbeehaken.com/portfolio/8, https://shellbeehaken.com/portfolio/6, https://kriyakarak.com/
- **Projects**: https://github.com/Sourav9063/uBookSharing, https://github.com/Sourav9063/flash-vscode, https://sourav9063.github.io/hall_management_rf/, https://github.com/Sourav9063/watchtogether, https://searchftp.vercel.app/
- **Publications**: https://arxiv.org/abs/2403.20084
- **Contact**: https://www.linkedin.com/in/sourav-ahmed/, https://sourav9063.github.io/, https://github.com/Sourav9063
