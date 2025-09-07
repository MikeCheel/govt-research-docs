# 📘 Project Best Practices

## 1. Project Purpose
A static, research-focused website documenting historical and governmental analysis. The project curates timelines, sources, and analysis with verifiable citations, emphasizing readability, mobile usability, and print-friendly layouts. Pages are standalone HTML files with inline CSS/JS for portability and zero-build deployment.

## 2. Project Structure
- Root directory contains standalone HTML documents and the landing page:
  - `index.html` — site hub with links to major documents and shared visual style (theme/style toggles, responsive navbar)
  - `US_Constitutional_Subversion.html` — interactive timeline with actor filtering, aggregated source links, print styles
  - `Ratification_Counterrevolution.html`, `Trump_Ideology_Analysis.html`, `DUI_Prevention_Analysis.html` — additional analysis pages
- `ai-research/` — source markdown research files grouped by domain (presidential, congressional, judiciary, etc.)
- `images/` — favicon and any static images
- `.github/` — GitHub configuration (actions/workflows if present)
- `.gitignore`, `LICENSE`, `ai-todos.md` — repository metadata and task tracking

Notes:
- Each document is self-contained: styles and scripts are embedded in the HTML. Shared behaviors (theme toggles, responsive nav) are implemented similarly per page.
- No build system or package manager; deployment is a simple static host or local file open.

## 3. Test Strategy
Given the static nature of the site, testing focuses on correctness, rendering, links, and UX:
- Manual cross-device QA:
  - Breakpoints: ≤480px, ≤768px, ≤1024px, desktop ≥1025px
  - Check navbar: hamburger toggle, menu layout, no horizontal scroll, title not covered
  - Verify theme toggle and style selector persist via `localStorage`
  - Verify print styles (print preview) for content density and source visibility
- Link integrity:
  - Validate all external links (HTTP 200/3xx) and add `rel="noopener noreferrer"` for `target="_blank"`
- Accessibility:
  - Semantic headings and landmarks, color contrast, focus states on interactive elements
- Validation/tools (recommended):
  - HTML validator (W3C), CSS validator
  - Lighthouse for accessibility/performance checks

## 4. Code Style
- HTML/CSS
  - Use CSS custom properties (variables) for theme, colors, borders, and spacing (see `:root` and `[data-theme="dark"]` patterns)
  - Keep page-specific CSS scoped within the document; reuse variable names for consistency
  - Prefer semantic elements (section, nav, header, footer, details/summary) as used in the timeline
  - Maintain print styles with `@media print` for readability and citation visibility
- JavaScript
  - Vanilla JS only; attach listeners in `DOMContentLoaded`
  - Persist user preferences via `localStorage` (`theme`, `style`), set attributes (`data-theme`, `data-style`)
  - Use clear, page-local function names (e.g., `gotoSection`, `filterTimeline`) and stable element IDs/classes (e.g., `hamburgerMenu`, `navButtons`)
  - Keep DOM queries narrowly scoped to the page’s structure; avoid global pollution
- Naming
  - Files: prefer consistency with existing convention using underscores in titles (e.g., `Topic_Analysis.html`)
  - IDs/classes: kebab-case for classes (e.g., `.nav-buttons`), lowerCamelCase for JS variables/functions
- Error handling
  - Guard optional elements with null checks before adding listeners
  - Fail gracefully if optional features are absent on a page

## 5. Common Patterns
- Responsive navigation
  - Sticky `.navbar` with left brand + center menu (hidden on mobile) + right controls
  - Mobile hamburger (`#hamburgerMenu`) toggles `.nav-buttons.show`; mobile menu uses column layout and vertical scroll (no horizontal scroll)
  - Keep brand/title readable on mobile; ensure hamburger does not overlap it
- Theming & styles
  - `data-theme` for light/dark; `data-style` for visual theme (default/glassmorphism/neumorphism)
  - Theme toggle updates `localStorage` and UI icon; style selector syncs mobile/desktop selectors
- Timelines and filtering (Constitutional Subversion page)
  - Timeline entries use `<details>` for collapsible content and source links
  - `filterTimeline()` shows only relevant entries/cards, auto-expands matching timeline items, hides unrelated sections, and keeps nav buttons in sync
  - Aggregated sources section (`#filtered-sources`) lists verifiable links for the selected actor (timeline, cards, visible references)
- Print support
  - `@media print` hides interactive nav controls, compacts layout, and maintains citation visibility

## 6. Do's and Don'ts
- Do
  - Reuse existing CSS variables and attribute-based theme/style approach
  - Keep mobile nav discoverable: hamburger on right, two-column menu or compact list, vertical scroll only
  - Ensure external links with `target="_blank"` include `rel="noopener noreferrer"`
  - Maintain section IDs stable to keep `gotoSection()` and nav buttons working
  - Add/extend print styles when introducing new content structures
  - Keep pages self-contained (inline CSS/JS) to preserve zero-dependency portability
- Don't
  - Introduce heavy JS frameworks or build tooling unless absolutely necessary
  - Break or rename shared IDs/classes used by nav, theme toggles, and filtering logic
  - Add horizontal scrolling to mobile menus
  - Remove or bypass verifiable source links; ensure new content includes citations

## 7. Tools & Dependencies
- No package manager or build framework; static HTML files
- External libraries (via CDN as needed per page):
  - `jspdf` and `html2canvas` on pages that may export/print or need capture
- Setup/Run
  - Open `.html` files directly in a browser or serve via any static server

## 8. Other Notes
- When creating new pages:
  - Copy the navbar/theme/selector patterns from `index.html` (or an existing analysis page) and adjust links
  - Keep CSS variables and theming sections consistent to ensure cross-page visual parity
  - Use the timeline + `<details>` pattern if adding chronology with citations
  - If adding filters, follow the `filterTimeline()` approach: filter visible items, sync nav visibility, auto-expand to expose sources, and aggregate sources in a dedicated section
- For long pages, consider sections with anchors and consistent button labels for nav
- Preserve accessibility (focus order, hit targets on mobile, adequate color contrast)

## Project Rules & Guidelines

**Mandatory Development Rules:**

### Task Approval & Management
- All design, coding, and security best practices must be used for this application
- No coding or task shall be started unless explicitly approved by me
- No task that causes changes should be performed without my approval, including git changes
- Keep a todo list of all commands I issue in a file called ai-todos.md in each project so you can remember when it crashes how to resume. Make sure to mark them off but DO NOT remove them unless instructed. Archive them in the same file. This ai-todos is not replacing other todo files I give you. This file is for you to remember where you are at and keep notes about individual tasks I give you
- Always keep track of your progress in the ai-todos.md file so if you crash or I stop your work, you can pick up where you left off
- If using the ai-todos.md, all questions should be answered by me before starting new tasks unless otherwise told

### AI Todos File Management
- You will always create this file if it does not already exist
- If asked to add a question section to ai-todos.md, make sure each question has a suggestion, and has a place marked for my answer. The place where my answer goes shouldn't use a placeholder for my answer, just leave that part blank
- If a suggestion you are offering me is multiple choice, include a number or letter for me to choose which suggested options I like. If it not possible or doesn't make sense to choose more than one or all, indicate that as well
- When you archive, make sure to move to an archived question section and retain what was answered along with the questions. This includes the questions number. Don't renumber questions

### Code Quality Standards
- All design, coding, and security best practices must be followed
- All libraries should be free to use for commercial purposes unless otherwise instructed
- At least 70% code coverage or better across the application
- All messages, warnings, and errors must be resolved (not suppressed)
- All tests should pass 100%
- Any existing suppression related to build or tests must be fixed
- Before any task is marked completed or considered done, there must be zero errors, warnings, or messages
- If something is broken and you fix it, you should write a unit test to make sure it doesn't happen again

### Environment & Tools
- Application artifacts should be structured like a GitHub repository
- PowerShell is used for all commands (PowerShell does not support `&&` in commands)
- If Docker is used, it must be run from WSL (Docker Desktop is not installed)
- I manage local Git operations unless otherwise instructed
- If an MCP server is configured for you that can help perform the task, you should use it

### Library & Documentation Rules
- All libraries should be free to use for commercial purposes unless otherwise instructed
- Do not create the vibe-docs folder and document structure unless instructed to

## Documentation Structure

### Questions Documentation
- **Location**: `vibe-docs/questions.md`
- **Purpose**: Track questions about the project with suggestions and recommendations
- **Format Requirements**:
  - If vibe-docs folder or questions.md does not exist, create it but only if instructed to. 
  - Questions should be numbered
  - Include one or more suggestions or recommendations
  - Questions should be categorized
  - Include a place for answers
  - Archive answered questions in the same document
  
### Todos Documentation
- **Location**: `vibe-docs/todos.md`
- **Purpose**: Track todo tasks based on answered questions
- **Format Requirements**:
  - If vibe-docs folder or todos.md does not exist, create it but only if instructed to. 
  - Todos should be categorized
  - Never begin a todo or task without approval
  - Todos should be comprehensive
  - Organized by category representing their general intention
  - Never marked completed until actually completed
  
### Implementation Documentation
- **Location**: `vibe-docs/implementation.md`
- **Purpose**: Track implementation tasks based on todos
- **Format Requirements**:
  - If vibe-docs folder or implementation.md does not exist, create it but only if instructed to.
  - Follow all development rules listed above
  - Tasks must be approved before starting
  - Tasks must be completed before marking as completed
  - Tasks must be categorized
  - Tasks must be comprehensive
  - Organized by category representing their general intention
  - Never marked completed until actually completed