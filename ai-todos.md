# AI Task Management

## Archived Tasks

### TASK 12: Resume Previous Work and Organize MD Files
**Status**: COMPLETED
**Description**: Resume interrupted task and move all .md files to ai-research folder for better organization
**Completion Date**: 2025-09-07
**Files Moved**: 
- Congressional_Constitutional_Violations_Research.md
- Constitutional_Violations_Integration_Analysis.md
- Corporate_Cronyism_Constitutional_Commerce_Violations.md
- Federal_Agency_Bureaucracy_Violations_Research.md
- Federal_Judiciary_Violations_Research.md
- Presidential_Constitutional_Violations_Research.md
- State_Government_Violations_Federal_System_Breakdown.md
**Notes**: Task successfully resumed and completed after system crash interruption. All MD files have been organized into the ai-research folder.

## Current Task: Mobile Menu Optimization for Constitutional Research Document

### TASK 14: Optimize Mobile Menu and Actor Filtering System
**Status**: APPROVED - IN PROGRESS
**Description**: Improve mobile menu usability and actor filtering functionality for US_Constitutional_Subversion.html
**Requirements**:
- Fix hamburger menu button covering the title
- Prevent need for users to swipe to see full menu
- Shorten mobile menu display to fit screen better
- Ensure actor filtering shows only relevant content and verifiable links
- Improve mobile user experience and discoverability
- Test on various mobile devices and screen sizes

**Implementation Steps**:
- [x] Analyze current mobile menu CSS and JavaScript functionality
- [x] Fix hamburger menu button positioning to avoid covering title
- [x] Redesign mobile menu layout to eliminate horizontal scrolling/swiping
- [x] Optimize mobile menu height and content spacing
- [x] Enhance actor filter to prominently show verifiable links when filtering
- [x] Ensure filtered content clearly displays source citations
- [x] Add always-visible mobile quick-controls bar (actor filter + style selector + dark-mode toggle) on ≤1024px
- [x] Improve glassmorphism title readability (text-shadow, color tweaks)
- [x] Tighten actor filter matching to avoid nickname bleed (e.g., James ≠ Jimmy)
- [ ] Test mobile menu on various screen sizes (iPhone, Android, tablets)
- [ ] Test actor filtering functionality and link display
- [ ] Verify all navigation elements work properly on mobile

**Implementation Notes (2025-09-07)**:
- Prevented hamburger overlap with the title on mobile; title now wraps on small screens (no ellipsis), avoiding overlap and truncation.
- Fixed overflow clipping on mobile navbar containers so the dropdown renders fully below the bar.
- Mobile menu opens as a full-width vertical list; no horizontal swiping; retains max-height with vertical scroll.
- Added an always-visible mobile quick-controls bar (≤1024px) under the navbar with: Actor filter, Style selector, and Dark-mode toggle. Controls are synced with the menu and persist via localStorage.
- Filter auto-expands matching timeline entries and aggregates verifiable "Sources for [actor]" at the bottom of the References section during filtering; the top intro aggregation is hidden while filtering.
- Tightened actor filter matching: removed bare-surname matching and bare nickname aliases to avoid false positives (e.g., James Monroe no longer surfaces Jimmy Carter content).
- Temporarily disabled in-text mention highlighting to stabilize scripts; will reintroduce a minimal, safe implementation after validation.
- Navigation buttons hide/show based on visible sections after filtering.

**Note**: This builds upon the existing navigation system in US_Constitutional_Subversion.html to improve mobile user experience.

**Note**: Task 12 (organizing MD files) has been successfully completed. All .md files have been moved to the ai-research folder as requested.

## Archived Tasks

### TASK 1: Presidential Constitutional Violations Research and Documentation
**Status**: COMPLETED
**Description**: Comprehensive research and documentation of presidential constitutional violations from 1789 to present
**Completion Date**: 2025-09-01
**Document**: ai-research/Presidential_Constitutional_Violations_Research.md
**Next Phase**: Await approval for subsequent tasks in comprehensive constitutional violations project

### TASK 2: Congressional Constitutional Violations Research and Documentation
**Status**: COMPLETED
**Description**: Comprehensive research and documentation of congressional constitutional violations from 1789 to present
**Completion Date**: 2025-09-01
**Document**: ai-research/Congressional_Constitutional_Violations_Research.md
**Next Phase**: Await approval for subsequent tasks in comprehensive constitutional violations project

### TASK 8: Federal Judiciary Violations Research and Documentation
**Status**: IN PROGRESS
**Description**: Research and documentation of federal judiciary constitutional violations
**Document**: ai-research/Federal_Judiciary_Violations_Research.md
**Next Phase**: Complete research and documentation

### TASK 9: Federal Agency and Bureaucracy Violations Research
**Status**: IN PROGRESS
**Description**: Research and documentation of federal agency and bureaucracy constitutional violations
**Document**: ai-research/Federal_Agency_Bureaucracy_Violations_Research.md
**Next Phase**: Complete research and documentation

### TASK 10: State Government Violations and Federal System Breakdown
**Status**: IN PROGRESS
**Description**: Research and documentation of state government constitutional violations and federal system breakdown
**Document**: ai-research/State_Government_Violations_Federal_System_Breakdown.md
**Next Phase**: Complete research and documentation

### TASK 11: Corporate Cronyism and Constitutional Commerce Violations
**Status**: IN PROGRESS
**Description**: Research and documentation of corporate cronyism and constitutional commerce clause violations
**Document**: ai-research/Corporate_Cronyism_Constitutional_Commerce_Violations.md
**Next Phase**: Complete research and documentation
