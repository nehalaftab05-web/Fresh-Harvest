# Fresh-Harvest
# 🌿 FreshHarvest — Farm Management System

> **UI Prototype · Assignment 03 — Software Design and Analysis**
> FAST-NUCES Chiniot-Faisalabad Campus · Computer Science · Section 4E

---

## 📋 Table of Contents

- [Project Overview](#project-overview)
- [System Actors](#system-actors)
- [Design System](#design-system)
- [Screen Inventory](#screen-inventory)
- [Navigation Flow](#navigation-flow)
- [SRS Requirements Mapping](#srs-requirements-mapping)
- [Technology Stack](#technology-stack)
- [Submission Links](#submission-links)
- [Team](#team)

---

## Project Overview

**FreshHarvest** is a desktop-based farm management system built for fruit farmers in Pakistan, particularly in Punjab and Sindh. The system digitalizes the complete fruit production lifecycle — from plantation and seasonal tracking, through batch processing, grading, and packaging, to order management, payments, shipment scheduling, and seasonal analytics.

This repository documents the **interactive UI prototype** for Assignment 03, covering 5 key screens built with HTML/CSS/JS. The prototype demonstrates the complete navigation flow, role-based layout, and core functional interactions defined in the SRS (Assignment 01).

| Property | Value |
|---|---|
| System Name | FreshHarvest — Farm Management System |
| Platform | Desktop Application (JavaFX / Windows) |
| Prototype Tool | HTML/CSS/JS Interactive Prototype |
| Screens | 5 screens with full navigation |
| Color Scheme | White & Green (`#2E7D32`, `#1B5E20`, `#9BBB59`, `#F1F8E9`) |

---

## System Actors

| Actor | Primary Responsibilities |
|---|---|
| **Farm Owner / Farmer** | Plantation management, batch creation, seasonal reports |
| **Factory Manager** | Batch processing, grading, packaging (UC-04, UC-05) |
| **Warehouse Manager** | Assigns packaged batches to warehouse locations (UC-06) |
| **Sales Manager** | Product listings and order management (UC-07, UC-08) |
| **Accountant** | Payment recording and credit ledger (UC-09) |
| **Logistics Manager** | Shipment scheduling and delivery tracking (UC-10) |

---

## Design System

### Color Palette

| Token | Hex | Usage |
|---|---|---|
| Primary Green | `#2E7D32` | Buttons, table headers, topbar, sidebar links |
| Dark Green | `#1B5E20` | Sidebar background, page headings |
| Olive Accent | `#9BBB59` | Active nav state, badge highlights, chart peaks |
| Light Green | `#F1F8E9` | Form backgrounds, card fills, table row alternates |
| White | `#FFFFFF` | Primary page background, card surfaces |
| Muted Gray | `#777777` | Secondary labels, placeholder text, descriptions |

### Typography

- **Font:** Segoe UI / System-UI
- **Scale:** 9–18px
- **Weights:** 700–800 for headings and section titles; 400–600 for body text
- **Hierarchy:** Dark green for primary labels → muted gray for secondary info

### Layout Patterns

**Authenticated Screens** — Fixed left sidebar (200px dark green) + scrollable white main content area

**Auth Screens** — Split two-column: green left panel with branding · white right panel with form

### Component Standards

| Component | Specification |
|---|---|
| Buttons | Primary: solid green + white text. Outline: white bg + green border. Danger: light red. 6–8px border-radius |
| Inputs | `#F1F8E9` background, green border, 11px bold dark green labels, muted gray placeholder |
| Tables | `#2E7D32` header row, alternating row shading (`#FFF` / `#F1F8E9`), pale green hover |
| Status Tags | Green (complete/dispatched), olive (packaged/graded), amber (rework), red (rejected), blue (in-progress) |
| Spacing Grid | 8px base; 10–24px component gaps; 22px main padding; 16px card padding |

---

## Screen Inventory

### Screen 1 — Login

**Actors:** All roles  
**SRS Reference:** NFR 3.3.3 (Security — Role-Based Access Control)

Split-panel authentication screen. Left panel carries FreshHarvest brand identity; right panel contains the role-gated login form.

| # | Element | Description |
|---|---|---|
| 1 | Brand Panel | Dark green background with logo, tagline, and 4 feature highlights |
| 2 | Role Selector | Dropdown: Farm Owner, Factory Manager, Warehouse Manager, Sales Manager, Accountant, Logistics Manager |
| 3 | Email Input | Light green background; validates format before submission |
| 4 | Password Input | Masked field with right-aligned 'Forgot password?' link |
| 5 | Remember Me | Session persistence checkbox with green accent |
| 6 | Sign In Button | Full-width primary green → Dashboard |
| 7 | Sign Up Link | Footer text link → Sign Up screen |
| 8 | Security Footer | 'Role-based access control · Secure JDBC connection' info card |

**Navigation:** Sign In → Dashboard · Sign up → Sign Up

---

### Screen 2 — Sign Up / Registration

**Actors:** System Administrator / Farm Owner  
**SRS Reference:** NFR 3.3.3 (Security — User Registration)

New account registration screen. Same split-panel layout as Login for visual consistency. Left panel explains role groups; right panel contains the registration form.

| # | Element | Description |
|---|---|---|
| 1 | Role Overview Panel | 3 role groups with icon, name, and module responsibilities |
| 2 | Name Fields | Two-column grid (First Name / Last Name) |
| 3 | Email Field | Full-width; used as login credential |
| 4 | Role Assignment | Dropdown matching login options; sets module permissions |
| 5 | Farm Name | Captures farm/organization name for system records |
| 6 | Password Fields | Two-column grid with confirmation field |
| 7 | Create Account | Full-width primary green → Dashboard |
| 8 | Sign In Link | Footer link → Login screen |

**Navigation:** Create Account → Dashboard · Sign in here → Login

---

### Screen 3 — Landing / Home Page

**Actors:** Public visitors (no authentication required)  
**SRS Reference:** Section 2.2 (Business Opportunity)

Public-facing marketing page communicating the system's value proposition. Features a hero section with 3 key statistics and a 3×2 feature grid covering all 10 core system modules.

| # | Element | Description |
|---|---|---|
| 1 | Top Navigation Bar | Dark green topbar: logo, nav links (Features, About, Contact), Sign In button, Get Started button |
| 2 | Hero Section | Green panel with watermark, badge label, headline, subtitle, CTA buttons, and 3 statistics |
| 3 | Statistics | 360° Lifecycle · 10+ Modules · 8 User Roles |
| 4 | Hero CTAs | White button → Sign Up · Outline button → Dashboard demo |
| 5 | Feature Grid (3×2) | Plantation Records 🌱, Batch Management 📦, Processing & Grading 🏭, Inventory 🏪, Orders 🧾, Analytics 📊 |
| 6 | Feature Cards | White card, 1.5px green border, 10px radius, green icon container, dark green title, gray description |
| 7 | Bottom CTA Banner | 'Start Managing Your Farm Today →' centered full-width button |

**Navigation:** Get Started Free → Sign Up · View Dashboard → Dashboard · Sign In → Login

---

### Screen 4 — Dashboard

**Actors:** Farm Owner / Farmer (primary); all authenticated roles  
**SRS Reference:** FR-3.5, FR-11.1–11.4

The main authenticated hub. Displays complete seasonal operations at a glance — plantation counts, batch pipeline status, pending orders, revenue, recent batch activity, monthly yield chart, and system notifications.

| # | Element | Description |
|---|---|---|
| 1 | Sidebar Navigation | 200px dark green sidebar; grouped links (Farm Operations / Warehouse & Sales / Reports); active item with olive left-border accent and pending badge |
| 2 | User Profile | Sidebar footer: avatar initials, name, and role |
| 3 | Page Title | Season name, region, and last-updated timestamp |
| 4 | Statistics Row | 4-column grid: Active Plantations (12), Batches (47), Pending Orders (5), Season Revenue (₨4.2M) |
| 5 | Recent Batches Table | 5 columns: Batch ID · Crop · Field · Status · Grade. Color-coded status tags; context-sensitive action buttons per row |
| 6 | Monthly Yield Chart | 6-bar chart (Oct–Mar); green bars with olive peak highlight |
| 7 | Notifications Panel | 3 recent alerts: ⚠️ Overdue invoice · ✅ Dispatch confirmed · 🏭 Batches awaiting grading |

**Navigation:** Batch Management (sidebar) → Screen 5 · View All (batches) → Screen 5

---

### Screen 5 — Batch Management

**Actors:** Farm Owner (create), Factory Manager (grade/process), Warehouse Manager (assign), Logistics Manager (track)  
**SRS Reference:** FR-3.1–3.7 (UC-03), FR-4.1–4.7 (UC-04)

Core batch lifecycle screen. Supports batch creation with auto-generated IDs, plantation validation, duplicate detection, status progression, and contextual role-based actions on each record.

| # | Element | Description |
|---|---|---|
| 1 | Lifecycle Progress Bar | 6-step bar: Harvested → Processing → Grading → Packaged → In Warehouse → Dispatched. Color encodes current stage |
| 2 | New Batch Button | Primary green toggle → expands inline creation form |
| 3 | Batch Creation Form | 3-column grid: Field ID, Crop Type, Harvest Date · Estimated Yield, Auto-ID (BATCH-YYYY-NNNN, read-only), Notes |
| 4 | Validation Banner | Explains plantation check (FR-3.3) and duplicate prevention (FR-3.4) rules |
| 5 | Filter Controls | Status dropdown · Crop Type dropdown for table filtering |
| 6 | Batch Data Table | 8 columns: Batch ID · Crop · Field · Harvest Date · Yield (kg) · Status · Grade · Action |
| 7 | Context Actions | View · Grade · Assign WH · Reprocess · Track · Report — rendered based on batch status and user role |
| 8 | Pagination Footer | '6 of 47 batches' count with 'Load more' link |

**Navigation:** Dashboard (sidebar) → Screen 4

---

## Navigation Flow

| Interaction | From | To |
|---|---|---|
| Click **Sign In** button | Login | Dashboard |
| Click **Sign up** link | Login | Sign Up |
| Click **Create Account** | Sign Up | Dashboard |
| Click **Sign in here** link | Sign Up | Login |
| Click **Get Started Free** | Landing | Sign Up |
| Click **Sign In** (navbar) | Landing | Login |
| Click **View Dashboard** | Landing | Dashboard |
| Click **Batch Management** (sidebar) | Dashboard | Batch Management |
| Click **View All** (batch table) | Dashboard | Batch Management |
| Click **Dashboard** (sidebar) | Batch Management | Dashboard |
| Click tab bar | Any Screen | Any Screen |

---

## SRS Requirements Mapping

| Screen | SRS Reference | Requirements Addressed |
|---|---|---|
| Screen 1 — Login | NFR 3.3.3 | Role-based access control; module visibility scoped to authenticated role; secure JDBC connection |
| Screen 2 — Sign Up | NFR 3.3.3 | New user registration with role assignment; supports all 6 actor types from Section 2.6 |
| Screen 3 — Landing | Section 2.2 | System value proposition; all 10 core features from Section 3.1 surfaced |
| Screen 4 — Dashboard | FR-3.5, FR-11.1–11.4 | Batch status overview; seasonal yield chart; pending order alerts; overdue invoice notifications; KPIs |
| Screen 5 — Batch Mgmt | FR-3.1–3.7 (UC-03), FR-4.1–4.7 (UC-04) | Batch creation with auto-ID (FR-3.2); plantation validation (FR-3.3); duplicate prevention (FR-3.4); lifecycle status (FR-3.5); draft saving (FR-3.7); grade assignment (FR-4.4) |

---

## Technology Stack

| Layer | Technology |
|---|---|
| Prototype | HTML / CSS / JavaScript |
| Production Frontend | Java with JavaFX (desktop GUI) |
| Backend | SQL via JDBC |
| Platform | Windows 10 / Windows 11 |
| Architecture | MVC (Model-View-Controller) |
| Reports Export | PDF and Excel (`.xlsx`) |

---

## Submission Links

| Item | Link |
|---|---|
| Figma Prototype | `https://www.figma.com/proto/[FILE-ID]/FreshHarvest-UI-Prototype` |
| Figma Access Level | Public — Anyone with the link can view |
| LinkedIn Post | `https://www.linkedin.com/posts/[USERNAME]/freshharvest-ui-prototype` |

> Replace all placeholder URLs with actual links before submission. In Figma, set share settings to **"Anyone with the link can view"** before copying the prototype URL.

---

## Team

| Name | Student ID | Role |
|---|---|---|
| Nehal Aftab | 24F-0518 | UI Design & Prototype Development |
| Minahil Younas | 24F-0522 | UI Design & Documentation |

**Supervisor:** Miss Ayesha Masood  
**Course:** Software Design and Analysis  
**Department:** Computer Science · Section 4E  
**Campus:** FAST-NUCES Chiniot-Faisalabad · May 2026

---

*🌿 FreshHarvest — From Orchards to Opportunities*
