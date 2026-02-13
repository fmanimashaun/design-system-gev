# GEV Design System v2.0

> **Genius Eco Visionaries** — Small Changes, Big Impact
> Reference document for Claude Code when building the GEV waste booking platform.
> Last updated: February 2026

---

## Table of Contents

1. [Brand Identity](#1-brand-identity)
2. [Logo System](#2-logo-system)
3. [Colour Palette](#3-colour-palette)
4. [Typography](#4-typography)
5. [Spacing Scale](#5-spacing-scale)
6. [Border Radius](#6-border-radius)
7. [Shadows / Elevation](#7-shadows--elevation)
8. [Transitions](#8-transitions)
9. [Buttons](#9-buttons)
10. [Badges](#10-badges)
11. [Alerts](#11-alerts)
12. [Form Elements](#12-form-elements)
13. [Cards](#13-cards)
14. [Tables](#14-tables)
15. [Avatars](#15-avatars)
16. [Navigation](#16-navigation)
17. [Page Layout](#17-page-layout)
18. [Voice & Tone](#18-voice--tone)
19. [Accessibility](#19-accessibility)
20. [Tailwind CSS Configuration](#20-tailwind-css-configuration)
21. [CSS Custom Properties](#21-css-custom-properties)
22. [Google Fonts Import](#22-google-fonts-import)
23. [Icon System](#23-icon-system)
24. [Currency & Number Formatting](#24-currency--number-formatting)
25. [Responsive Breakpoints](#25-responsive-breakpoints)

---

## 1. Brand Identity

### Company

- **Legal name:** Genius Eco Visionaries
- **CAC Registration:** 8063542
- **Display name:** GENIUS ECO VISIONARIES
- **Tagline:** Small Changes, Big Impact
- **Domain:** geniusecovisionaries.com
- **Primary email:** info@geniusecovisionaries.com
- **Founded:** 2024
- **Location:** Edo State, Nigeria (Edo South, expanding to North & Central)

### Business Model

GEV is a **recyclable materials purchasing company** — NOT a waste collection service. GEV **pays customers** for their recyclable materials (plastics, aluminium cans / UBC). Revenue comes from buying at market rate, aggregating, and selling to processors at margin.

### Mission

Sustainable waste management that creates a circular economy — extracting economic value from materials that would otherwise end up in landfills and waterways.

### Vision

To become the leading force in recycling and environmental innovation across Nigeria.

### Core Values

1. Sustainability
2. Innovation
3. Community Impact
4. Integrity
5. Excellence
6. Environmental Responsibility

### Brand Personality

| Trait | Description | Design Expression |
|---|---|---|
| Earthy | Grounded, natural, organic | Soft greens, rounded corners, natural imagery |
| Trustworthy | Reliable, fair, honest | Clean layouts, consistent patterns, clear data |
| Innovative | Modern, forward-thinking | Crisp typography, responsive design, smart UX |
| Community | Local, accessible, warm | Friendly copy, WhatsApp integration, local context |
| Empowering | Turn waste into income | Green CTAs, earnings prominently displayed |

### Key Messages

| Priority | Message | Use Case |
|---|---|---|
| Primary | "Turn Your Waste Into Cash" | Hero headlines, ads, social media |
| Secondary | "Small Changes, Big Impact" | Tagline, footer, environmental messaging |
| Supporting | "We come to you" | Convenience messaging, booking flow |
| Supporting | "We pay you" | Value prop, pricing page |
| Supporting | "Free pickup" | Booking CTA, onboarding |

---

## 2. Logo System

### Logo Files

- **Transparent PNG:** `GEV_Logo_Transparent.png` (1024×1024, RGBA)
- The original uploaded file was a JPEG with black background — always use the transparent version

### Logo Description

Circular yin-yang motif with two leaf shapes containing open hands. Blue leaf (top-right) and green leaf (bottom-left). The hands are negative space (transparent cut-throughs). Represents recycling, sustainability, and community partnership (giving and receiving).

### Logo Colours (from the mark itself)

- Blue leaf: `#28A0C8`
- Green leaf: `#8CC83C`

### Wordmark Lockup

When combining logo + text, use this structure:

```
[Logo Icon] GENIUS ECO VISIONARIES
            Small Changes, Big Impact
```

- Company name: `font-display`, weight 800, `letter-spacing: -0.02em`
- "ECO" in the company name: coloured `green-400` (#8CC83C)
- Tagline: `font-display`, weight 300, `font-size: 0.7rem`, `letter-spacing: 0.22em`, uppercase

### Dark Background Lockup

- Company name: white (`#FFFFFF`)
- "ECO": `green-400` (#8CC83C)
- Tagline: `gray-500` (#657078)

### Light Background Lockup

- Company name: `gray-900` (#141919)
- "ECO": `green-400` (#8CC83C)
- Tagline: `gray-400` (#8B969C)

### Logo Placement Rules

| Context | Size | Notes |
|---|---|---|
| Desktop navbar | 32–40px icon | Icon only, or icon + wordmark at 120px+ wide |
| Mobile navbar | 28–32px icon | Icon only |
| Favicon | 16px | Simplified icon mark |
| Footer | 48px icon | Icon above company name |
| Email signature | 40px icon | Inline with company name |
| Print (minimum) | 15mm | Icon mark |

### Clear Space

Maintain minimum clear space equal to 1× the height of one leaf element on all sides. Never crowd the logo with text, UI elements, or graphics.

### Logo Don'ts

- Do NOT stretch or distort proportions
- Do NOT rotate the logo
- Do NOT reduce opacity below 100%
- Do NOT place on clashing or busy backgrounds
- Do NOT recolour the leaves
- Do NOT add drop shadows or effects (the logo design is self-contained)
- Do NOT separate the two leaves
- Do NOT use the old JPEG with black background

---

## 3. Colour Palette

### Blue (Primary)

Used for: navigation, links, interactive elements, headers, info states.

| Token | Hex | Tailwind Class | Usage |
|---|---|---|---|
| blue-50 | `#E8F4F8` | `bg-blue-50` | Info backgrounds, card tints |
| blue-100 | `#C5E4EE` | `bg-blue-100` | Hover backgrounds, spacing bars |
| blue-200 | `#8DC9DD` | `bg-blue-200` | Borders, dividers |
| blue-300 | `#55AECC` | `text-blue-300` | Secondary links, outline borders |
| blue-400 | `#35A4C8` | `text-blue-400` | Focus rings, active borders |
| **blue-500** | **`#28A0C8`** | **`bg-blue-500`** | **PRIMARY — buttons, nav, links** |
| blue-600 | `#2290B5` | `bg-blue-600` | Button hover |
| blue-700 | `#1B7A99` | `text-blue-700` | Headings on light bg, badge text |
| blue-800 | `#15647D` | `text-blue-800` | Alert text on info bg |
| blue-900 | `#0E4457` | `text-blue-900` | Dark mode text |

### Green (Secondary / CTA)

Used for: calls-to-action, money/earnings displays, eco messaging, success accents.

| Token | Hex | Tailwind Class | Usage |
|---|---|---|---|
| green-50 | `#F0F7E6` | `bg-green-50` | CTA section backgrounds |
| green-100 | `#D9EDBE` | `bg-green-100` | Highlight boxes |
| green-200 | `#BCE293` | `bg-green-200` | Borders |
| green-300 | `#A0D768` | `text-green-300` | Accents |
| **green-400** | **`#8CC83C`** | **`bg-green-400`** | **SECONDARY — CTA buttons, "ECO" in wordmark** |
| green-500 | `#7DB835` | `bg-green-500` | CTA hover, pricing numbers |
| green-600 | `#6FA52F` | `bg-green-600` | Pressed state |
| green-700 | `#5C8D27` | `text-green-700` | Dark text on green bg |
| green-800 | `#49751F` | `text-green-800` | — |
| green-900 | `#365413` | `text-green-900` | — |

### Neutrals

Used for: body text, borders, backgrounds, disabled states.

| Token | Hex | Tailwind Class | Usage |
|---|---|---|---|
| gray-50 | `#F7FAFA` | `bg-gray-50` | Page backgrounds, table header bg |
| gray-100 | `#EEF2F3` | `bg-gray-100` | Card backgrounds, section alt bg |
| gray-200 | `#DCE1E3` | `border-gray-200` | Borders, dividers, card strokes |
| gray-300 | `#B8C0C4` | `text-gray-300` | Disabled text, placeholder icons |
| gray-400 | `#8B969C` | `text-gray-400` | Placeholder text, captions, hints |
| gray-500 | `#657078` | `text-gray-500` | Secondary text, descriptions |
| gray-600 | `#4A545B` | `text-gray-600` | Body text (alternate) |
| gray-700 | `#353D42` | `text-gray-700` | Body text (default in some contexts) |
| gray-800 | `#232A2E` | `text-gray-800` | **Default body text colour** |
| gray-900 | `#141919` | `bg-gray-900` | Headings, footer bg, hero bg |

### Semantic Colours

| Name | Colour | Light BG | Usage |
|---|---|---|---|
| Success | `#2ECC71` | `#E8F8F0` | Completed pickups, payment confirmed, positive feedback |
| Warning | `#F39C12` | `#FEF5E7` | Pending actions, rate changes, low inventory |
| Error | `#E74C3C` | `#FDEDEC` | Failed actions, validation errors, cancellations |
| Info | `#28A0C8` | `#E8F4F8` | System updates, tips, neutral information |

### Colour Usage Rules

- **Blue-500** is the primary interactive colour (buttons, links, nav)
- **Green-400** is reserved for CTAs related to money/eco actions ("Sell", "Book Pickup", "Earn")
- Never use Blue and Green as equal-weight CTAs on the same view — one must be primary, the other secondary or outline
- Red is ONLY for errors and destructive actions
- Use light tints (50/100 shades) for section and card backgrounds
- Maintain WCAG AA contrast (4.5:1 minimum for text)
- Never introduce brand colours outside this palette

---

## 4. Typography

### Font Families

| Role | Font | Fallback | Used For |
|---|---|---|---|
| Display | Plus Jakarta Sans | system sans-serif | Headings, buttons, labels, nav items, badges |
| Body | DM Sans | system sans-serif | Paragraphs, descriptions, form descriptions |
| Mono | JetBrains Mono | system monospace | Prices, weights, booking refs, code, data values |

### Type Scale

| Name | Size | Weight | Font | Letter Spacing | Line Height | Use Case |
|---|---|---|---|---|---|---|
| Display | 48px (3rem) | 800 | Display | -0.04em | 1.05 | Hero headlines only |
| H1 | 36px (2.25rem) | 800 | Display | -0.02em | 1.15 | Page titles |
| H2 | 28px (1.75rem) | 700 | Display | -0.02em | 1.2 | Section headings |
| H3 | 22px (1.375rem) | 700 | Display | -0.01em | 1.3 | Card headers, subsections |
| H4 | 18px (1.125rem) | 600 | Display | 0 | 1.4 | Widget titles, sidebar headings |
| Body | 16px (1rem) | 400 | Body | 0 | 1.6 | Default paragraph text |
| Body Small | 14px (0.875rem) | 400 | Body | 0 | 1.5 | Secondary text, table cells |
| Caption | 12px (0.75rem) | 500 | Body | 0 | 1.4 | Timestamps, metadata, hints |
| Label | 12px (0.75rem) | 600 | Display | 0.06em | 1.2 | Form labels, table headers, all-caps tags |
| Data | 14px (0.875rem) | 500 | Mono | 0 | 1.4 | Prices, weights, booking refs, IDs |
| Data Large | 2.2rem+ | 700 | Mono | 0 | 1 | Dashboard stat numbers, pricing cards |

### Typography Rules

- All headings use `font-display` (Plus Jakarta Sans)
- All body text uses `font-body` (DM Sans)
- All numeric data, prices, weights, and references use `font-mono` (JetBrains Mono)
- Use negative letter-spacing on headings H2 and above
- Labels are always uppercase with `letter-spacing: 0.06em`
- Never go below 12px for any text
- Never use ALL CAPS for body text (only labels and the company name)
- Never bold entire paragraphs
- Never mix font families within the same element

---

## 5. Spacing Scale

4px base unit. Use these tokens for all padding, margin, and gap values.

| Token | Value | Tailwind | Common Use |
|---|---|---|---|
| sp-1 | 4px | `p-1` / `gap-1` | Tight inner spacing, badge padding |
| sp-2 | 8px | `p-2` / `gap-2` | Input padding, small gaps |
| sp-3 | 12px | `p-3` / `gap-3` | Between label and input, nav link padding |
| sp-4 | 16px | `p-4` / `gap-4` | Card internal padding, grid gaps |
| sp-5 | 20px | `p-5` / `gap-5` | Alert padding, form group spacing |
| sp-6 | 24px | `p-6` / `gap-6` | Card body padding, section inner padding |
| sp-7 | 32px | `p-8` / `gap-8` | Large card padding, form sections |
| sp-8 | 40px | `p-10` | Component preview padding |
| sp-9 | 48px | `p-12` | Section inner spacing |
| sp-10 | 56px | — | — |
| sp-11 | 64px | `p-16` | Between section title and content |
| sp-12 | 80px | `p-20` | Between subsections |
| sp-13 | 96px | `py-24` | Section vertical padding |
| sp-14 | 128px | `py-32` | Hero / page header vertical padding |

---

## 6. Border Radius

| Token | Value | Tailwind | Usage |
|---|---|---|---|
| r-sm | 6px | `rounded-sm` | Small buttons, compact badges, chips |
| r-md | 10px | `rounded-md` | **Default** — buttons, inputs, alerts, swatches |
| r-lg | 16px | `rounded-lg` | Cards, modals, dropdowns, image containers |
| r-xl | 24px | `rounded-xl` | Hero cards, featured sections |
| r-full | 9999px | `rounded-full` | Avatars, pills, badges, nav tags |

### Radius Rules

- All interactive elements (buttons, inputs) use `r-md` (10px) by default
- All container elements (cards, modals) use `r-lg` (16px)
- Never use sharp corners (0px radius) — the brand is warm and approachable
- Badges and pills always use `r-full`

---

## 7. Shadows / Elevation

| Token | Value | Tailwind | Usage |
|---|---|---|---|
| sh-xs | `0 1px 2px rgba(20,25,25,0.05)` | `shadow-xs` | Subtle lift — inputs, swatches |
| sh-sm | `0 1px 3px rgba(20,25,25,0.08), 0 1px 2px rgba(20,25,25,0.04)` | `shadow-sm` | Cards at rest, white buttons |
| sh-md | `0 4px 6px -1px rgba(20,25,25,0.08), 0 2px 4px -2px rgba(20,25,25,0.04)` | `shadow-md` | Dropdowns, popovers |
| sh-lg | `0 10px 15px -3px rgba(20,25,25,0.08), 0 4px 6px -4px rgba(20,25,25,0.04)` | `shadow-lg` | Cards on hover, modals |
| sh-xl | `0 20px 25px -5px rgba(20,25,25,0.08), 0 8px 10px -6px rgba(20,25,25,0.04)` | `shadow-xl` | Toast notifications, floating action buttons |

### Shadow Rules

- All shadows use `rgba(20,25,25,...)` — NOT pure black — for softer, warmer appearance
- Cards should elevate from `shadow-sm` to `shadow-lg` on hover
- Buttons use coloured shadows matching their background (e.g., `rgba(40,160,200,0.3)` for blue buttons)

---

## 8. Transitions

| Property | Duration | Easing | Usage |
|---|---|---|---|
| Fast | 150ms | `cubic-bezier(0.4, 0, 0.2, 1)` | Button hover, input focus, badge toggle |
| Normal | 250ms | `cubic-bezier(0.4, 0, 0.2, 1)` | Card hover, dropdown open, page transitions |
| Slow | 400ms | `cubic-bezier(0.4, 0, 0.2, 1)` | Modal enter/exit, accordion expand |

Tailwind: `transition-all duration-150 ease-out` for most interactions.

---

## 9. Buttons

### Variants

| Variant | Tailwind Classes | Use Case |
|---|---|---|
| Primary | `bg-blue-500 text-white hover:bg-blue-600 shadow-[0_1px_2px_rgba(40,160,200,0.3)]` | Navigation, general actions ("View", "Details", "Submit") |
| CTA | `bg-green-400 text-white hover:bg-green-500 shadow-[0_1px_2px_rgba(140,200,60,0.3)]` | Money/eco actions ("Schedule Pickup", "Sell Recyclables", "Book Now") |
| Outline | `bg-transparent text-blue-500 border-1.5 border-blue-300 hover:bg-blue-50 hover:border-blue-500` | Secondary actions ("View Details", "Learn More") |
| Ghost | `bg-transparent text-gray-600 hover:bg-gray-100 hover:text-gray-800` | Tertiary actions ("Cancel", "Dismiss") |
| White | `bg-white text-gray-800 border border-gray-200 shadow-xs hover:border-gray-300 hover:shadow-sm` | On coloured backgrounds ("Export CSV", toolbar actions) |
| Danger | `bg-error text-white hover:bg-[#c0392b]` | Destructive actions ("Delete", "Remove") — use sparingly |

### Sizes

| Size | Padding | Font Size | Radius | Usage |
|---|---|---|---|---|
| sm | `7px 14px` | 0.8rem (12.8px) | r-sm (6px) | Compact UI, table actions, badge-like buttons |
| md | `10px 20px` | 0.875rem (14px) | r-md (10px) | **Default** — most buttons |
| lg | `14px 28px` | 1rem (16px) | r-md (10px) | Hero CTAs, form submit, prominent actions |

### Button Rules

- All buttons use `font-display` (Plus Jakarta Sans), weight 600
- All buttons have `border-radius: r-md` (10px) except sm which uses `r-sm` (6px)
- Hover state: lift 1px (`transform: translateY(-1px)`) + increase shadow
- Active state: remove transform, reduce shadow
- Disabled: 50% opacity, `cursor: not-allowed`, no hover effects
- Full-width buttons in forms: `width: 100%`
- Never use more than 2 button variants in the same component
- CTA buttons should have a right arrow: `Schedule Free Pickup →`

### Button HTML/ERB Pattern

```erb
<%# Primary button %>
<%= link_to "Schedule Pickup", new_booking_path,
    class: "inline-flex items-center justify-center gap-2 font-display font-semibold
           bg-blue-500 text-white rounded-md px-5 py-2.5 text-sm
           hover:bg-blue-600 hover:-translate-y-px
           shadow-[0_1px_2px_rgba(40,160,200,0.3)]
           hover:shadow-[0_4px_12px_rgba(40,160,200,0.3)]
           transition-all duration-150" %>

<%# CTA button %>
<%= link_to "Sell Recyclables →", new_booking_path,
    class: "inline-flex items-center justify-center gap-2 font-display font-semibold
           bg-green-400 text-white rounded-md px-7 py-3.5 text-base
           hover:bg-green-500 hover:-translate-y-px
           shadow-[0_1px_2px_rgba(140,200,60,0.3)]
           hover:shadow-[0_4px_12px_rgba(140,200,60,0.3)]
           transition-all duration-150" %>
```

---

## 10. Badges

Used for booking status, payment status, and CMS post status.

| Status | Background | Text Colour | Dot Colour | Label |
|---|---|---|---|---|
| Success | `#E8F8F0` | `#1a8a4a` | `#2ECC71` | Completed, Paid, Published |
| Warning | `#FEF5E7` | `#9a6b0b` | `#F39C12` | Pending, Scheduled, Draft |
| Error | `#FDEDEC` | `#a93226` | `#E74C3C` | Cancelled, Failed, Rejected |
| Info | `#E8F4F8` | `#1B7A99` | `#28A0C8` | Confirmed, Assigned, Active |
| Neutral | `#EEF2F3` | `#4A545B` | `#8B969C` | Draft, Inactive |

### Badge Structure

```html
<span class="inline-flex items-center gap-1.5 font-display text-xs font-semibold px-2.5 py-1 rounded-full bg-success-light text-[#1a8a4a]">
  <span class="w-1.5 h-1.5 rounded-full bg-success"></span>
  Completed
</span>
```

### Booking Status Flow

`pending` → `confirmed` → `assigned` → `in_progress` → `completed` / `cancelled`

| Status | Badge Variant |
|---|---|
| pending | Warning |
| confirmed | Info |
| assigned | Info |
| in_progress | Info |
| completed | Success |
| cancelled | Error |

### Payment Status

| Status | Badge Variant |
|---|---|
| pending | Warning |
| paid | Success |
| failed | Error |

---

## 11. Alerts

Used for dashboard feedback, system messages, and form-level errors.

### Structure

```html
<div class="flex items-start gap-3 p-4 px-5 rounded-md border-l-4 border-success bg-success-light text-[#1a6b3a] text-sm">
  <span class="text-lg flex-shrink-0 mt-px">✓</span>
  <div>Pickup completed — ₦4,375 paid to Animashaun Olushola.</div>
</div>
```

### Variants

| Variant | Border | Background | Text | Icon |
|---|---|---|---|---|
| Success | `border-success` | `bg-success-light` | `#1a6b3a` | ✓ |
| Warning | `border-warning` | `bg-warning-light` | `#7a5509` | ⚠ |
| Error | `border-error` | `bg-error-light` | `#8a2a20` | ✗ |
| Info | `border-blue-500` | `bg-blue-50` | `#15647D` | ℹ |

### Example Messages

- Success: "Pickup completed — ₦4,375 paid to Animashaun Olushola."
- Warning: "Buy rate updated — Plastics now ₦350/kg (was ₦320/kg)."
- Error: "SMS delivery failed for +2348012345678. Retry?"
- Info: "3 pickups scheduled for tomorrow morning in Edo South."

---

## 12. Form Elements

### Input Fields

```html
<div class="flex flex-col gap-2">
  <label class="font-display text-sm font-semibold text-gray-700">Full Name *</label>
  <input type="text"
    class="font-body text-[0.9rem] px-3.5 py-2.5 border-[1.5px] border-gray-200 rounded-md
           text-gray-800 bg-white outline-none transition-all duration-150
           focus:border-blue-400 focus:ring-[3px] focus:ring-blue-500/12
           placeholder:text-gray-400"
    placeholder="e.g., John Okafor" />
  <span class="text-xs text-gray-400">Helper text goes here</span>
</div>
```

### Input States

| State | Border | Shadow / Ring | Text |
|---|---|---|---|
| Default | `border-gray-200` | none | `text-gray-800` |
| Focus | `border-blue-400` | `ring-[3px] ring-blue-500/12` | `text-gray-800` |
| Error | `border-error` | none | `text-gray-800` |
| Disabled | `border-gray-200 bg-gray-50` | none | `text-gray-400` |

### Error State

```html
<input class="... border-error" value="not-an-email" />
<span class="text-xs text-error">Please enter a valid email address</span>
```

### Form Labels

- Font: `font-display`, 0.8rem, weight 600, `text-gray-700`
- Required fields: append ` *` to label text
- Labels are always above the input, never inline

### Select Dropdowns

Same styling as text inputs. Use native `<select>` with Tailwind Forms plugin styling.

### Booking Form Fields (Quick Onboarding)

**Required (Phase 1):**

| Field | Type | Placeholder |
|---|---|---|
| Full Name * | text | "e.g., John Okafor" |
| WhatsApp Number * | tel | "+234..." |
| Pickup Address * | text | "e.g., 15 Akpakpava Road, Benin City" |

**Optional (Phase 1):**

| Field | Type | Placeholder/Options |
|---|---|---|
| Waste Type | select | Plastics, Aluminium Cans (UBC) |
| Estimated Weight (kg) | number | "e.g., 25" |
| Email | email | "your@email.com" |
| Preferred Pickup Date | date | — |
| Landmark | text | "Near..." |
| Special Instructions | textarea | "Any access notes..." |

---

## 13. Cards

### Default Card

```html
<div class="bg-white border border-gray-200 rounded-lg overflow-hidden
            transition-all duration-250 hover:shadow-lg hover:border-gray-300">
  <div class="p-6">
    <!-- Card content -->
  </div>
</div>
```

### Card with Header

```html
<div class="bg-white border border-gray-200 rounded-lg overflow-hidden">
  <div class="px-6 py-5 border-b border-gray-100 font-display font-bold text-[0.95rem]">
    Card Title
  </div>
  <div class="p-6">
    <!-- Content -->
  </div>
</div>
```

### Buy Rate Card (Pricing Page)

```html
<div class="bg-white border border-gray-200 rounded-lg p-7 text-center
            transition-all duration-250 hover:shadow-lg hover:border-gray-300">
  <div class="font-mono text-[2.2rem] font-bold text-blue-500 mb-2">₦350</div>
  <div class="font-display text-sm font-semibold text-gray-700">Plastics</div>
  <div class="text-xs text-gray-400 mt-0.5">per kilogram</div>
</div>
```

- Use `text-blue-500` for plastics price
- Use `text-green-500` for aluminium cans price
- Use `text-gray-300` with `opacity-50` for "coming soon" waste types

### Dashboard Stat Card

```html
<div class="bg-white border border-gray-200 rounded-lg p-6">
  <div class="font-display text-xs font-semibold uppercase tracking-wider text-gray-500 mb-2">
    Today's Purchases
  </div>
  <div class="font-mono text-2xl font-bold text-gray-900">₦47,350</div>
  <div class="text-xs text-gray-400 mt-1">12 pickups completed</div>
</div>
```

---

## 14. Tables

Used in admin dashboard for bookings, customers, payments, and reports.

### Structure

```html
<table class="w-full text-sm border-collapse">
  <thead>
    <tr>
      <th class="font-display font-semibold text-xs uppercase tracking-wider
                 text-gray-500 bg-gray-50 px-4 py-3 text-left border-b-2 border-gray-200">
        Reference
      </th>
      <!-- More headers -->
    </tr>
  </thead>
  <tbody>
    <tr class="hover:bg-blue-50 transition-colors">
      <td class="px-4 py-3 border-b border-gray-100 font-mono text-xs">
        GEV-20260215-001
      </td>
      <!-- More cells -->
    </tr>
  </tbody>
</table>
```

### Table Column Types

| Column | Font | Alignment | Notes |
|---|---|---|---|
| Reference / ID | `font-mono`, 0.78rem | Left | Always monospace |
| Customer name | `font-body`, default | Left | Regular text |
| Waste type | `font-body`, default | Left | Regular text |
| Weight | `font-mono` | Right | Format: "12.5 kg" |
| Amount / Price | `font-mono`, weight 500 | Right | Format: "₦4,375" |
| Date / Time | `font-mono`, 0.78rem | Left | Format: "15 Feb 2026" or "2:30 PM" |
| Status | Badge component | Centre | Use status badges |
| Actions | Buttons (sm ghost) | Right | "View", "Edit", icon buttons |

### Table Rules

- Always include hover state on rows (`hover:bg-blue-50`)
- Last row has no bottom border
- Header row: `bg-gray-50`, 2px bottom border
- All data columns use monospace for numeric values
- Empty values show `—` in `text-gray-400`

---

## 15. Avatars

Used for admin user display. Initials-based (no photos currently).

| Size | Dimensions | Font Size | Usage |
|---|---|---|---|
| sm | 32px | 0.75rem | Compact lists, comments |
| md | 40px | 0.85rem | Default — nav bar, table rows |
| lg | 48px | 1rem | Profile pages, headers |

### Structure

```html
<div class="w-10 h-10 rounded-full flex items-center justify-center
            font-display font-bold text-sm text-white bg-blue-500 flex-shrink-0">
  AO
</div>
```

- Use `bg-blue-500` as default
- Use `bg-green-400` as alternate
- Initials: first letter of first name + first letter of last name, uppercase

---

## 16. Navigation

### Public Website Navbar

```
[Logo 32px] [Home] [About] [Services] [Pricing] [Blog] [Contact]     [Schedule Pickup →] (CTA button)
```

- Background: white with `backdrop-filter: blur(14px)`, `border-bottom: 1px solid gray-200`
- Sticky: `position: sticky; top: 0; z-index: 100`
- Nav links: `font-display`, 0.85rem, weight 600, `text-gray-600`
- Active link: `text-blue-500`
- Hover: `text-blue-600`, `bg-blue-50`, `rounded-full`

### Admin Dashboard Sidebar

```
[Logo + "GEV Admin"]
─────────────────
📊 Dashboard
📋 Bookings
👥 Customers
💰 Payments
📦 Waste Types
💲 Buy Rates
📝 Blog Posts
📁 Post Categories
⚙️ Settings
```

- Background: `gray-900` or white depending on theme
- Active item: `bg-blue-500/10`, `text-blue-500`, left border accent
- Hover: `bg-gray-100` (light) or `bg-gray-800` (dark)

---

## 17. Page Layout

### Public Pages

```
Max width: 1100px, centered
Horizontal padding: 24px (sp-6)
Section vertical padding: 96px (sp-13)
Section separator: 1px solid gray-200
```

### Admin Dashboard

```
Sidebar: 256px fixed width
Main content: fluid, max-width 1200px
Content padding: 24px–32px
Card gap: 20px–24px
```

### Responsive Container

```erb
<div class="max-w-[1100px] mx-auto px-6">
  <!-- Content -->
</div>
```

---

## 18. Voice & Tone

### Public Website

| Principle | Example |
|---|---|
| Lead with customer benefit | "Turn your waste into cash" not "We buy recyclables" |
| Emphasise free service | "Schedule a free pickup" not "Request collection" |
| Be direct about payment | "We pay you ₦350/kg for plastics" |
| Warm, community-first | "Join thousands of Edo residents..." |
| Eco-conscious but not preachy | "Keeping waste out of landfills" not "Save the planet" |
| Simple language | "Book a pickup" not "Initiate a collection request" |

### Admin Dashboard

| Principle | Example |
|---|---|
| Concise, action-oriented | "Assign Driver" not "Click here to assign a driver" |
| Data-driven | Always show numbers: weights, amounts, counts |
| Clear confirmations | "Pickup completed — ₦4,375 paid to Ada Okonkwo" |
| Error messages explain what to do | "Enter a valid phone number (e.g., 08012345678)" not "Invalid input" |
| No exclamation marks | Keep admin tone professional and calm |
| Neutral, factual | "Rate updated: Plastics ₦350/kg" not "Great news! Rate changed!" |

### Common Copy Patterns

| Context | Copy |
|---|---|
| Empty state (bookings) | "No bookings yet. New pickups will appear here." |
| Empty state (customers) | "No customers found. They'll appear after their first booking." |
| Loading | "Loading..." (no spinner text needed beyond this) |
| Success toast | "[Action] completed successfully." |
| Booking CTA (hero) | "Schedule Free Pickup →" |
| Booking CTA (pricing) | "Sell Your Recyclables →" |
| Footer CTA | "Ready to earn from your waste?" |
| WhatsApp CTA | "Chat with us on WhatsApp" |

---

## 19. Accessibility

### Colour Contrast Requirements

All text must meet WCAG AA standards:

| Combination | Ratio | Pass? |
|---|---|---|
| gray-800 on white | 12.6:1 | ✅ AAA |
| gray-500 on white | 5.1:1 | ✅ AA |
| gray-400 on white | 3.5:1 | ❌ AA (captions only, use 500 for important text) |
| white on blue-500 | 4.6:1 | ✅ AA |
| white on green-400 | 3.2:1 | ⚠️ AA Large only (use green-600 for small text on white bg) |
| white on gray-900 | 18.1:1 | ✅ AAA |

### Focus States

All interactive elements must have visible focus indicators:

```css
:focus-visible {
  outline: 2px solid var(--blue-500);
  outline-offset: 2px;
}
```

Or use ring utility: `focus-visible:ring-2 focus-visible:ring-blue-500 focus-visible:ring-offset-2`

### General Rules

- All images must have `alt` text
- Form inputs must have associated `<label>` elements
- Buttons must have descriptive text (no icon-only buttons without `aria-label`)
- Links must be distinguishable from regular text (underline or colour + hover)
- Minimum touch target: 44×44px on mobile

---

## 20. Tailwind CSS Configuration

```js
// tailwind.config.js
const defaultTheme = require("tailwindcss/defaultTheme")

module.exports = {
  content: [
    "./app/views/**/*.{html,erb}",
    "./app/javascript/**/*.js",
    "./app/helpers/**/*.rb",
    "./app/components/**/*.{rb,erb}",
  ],
  theme: {
    extend: {
      colors: {
        blue: {
          50: "#E8F4F8",
          100: "#C5E4EE",
          200: "#8DC9DD",
          300: "#55AECC",
          400: "#35A4C8",
          500: "#28A0C8",
          600: "#2290B5",
          700: "#1B7A99",
          800: "#15647D",
          900: "#0E4457",
        },
        green: {
          50: "#F0F7E6",
          100: "#D9EDBE",
          200: "#BCE293",
          300: "#A0D768",
          400: "#8CC83C",
          500: "#7DB835",
          600: "#6FA52F",
          700: "#5C8D27",
          800: "#49751F",
          900: "#365413",
        },
        gray: {
          50: "#F7FAFA",
          100: "#EEF2F3",
          200: "#DCE1E3",
          300: "#B8C0C4",
          400: "#8B969C",
          500: "#657078",
          600: "#4A545B",
          700: "#353D42",
          800: "#232A2E",
          900: "#141919",
        },
        success: {
          DEFAULT: "#2ECC71",
          light: "#E8F8F0",
        },
        warning: {
          DEFAULT: "#F39C12",
          light: "#FEF5E7",
        },
        error: {
          DEFAULT: "#E74C3C",
          light: "#FDEDEC",
        },
      },
      fontFamily: {
        display: ["Plus Jakarta Sans", ...defaultTheme.fontFamily.sans],
        body: ["DM Sans", ...defaultTheme.fontFamily.sans],
        mono: ["JetBrains Mono", ...defaultTheme.fontFamily.mono],
      },
      borderRadius: {
        sm: "6px",
        md: "10px",
        lg: "16px",
        xl: "24px",
      },
      boxShadow: {
        xs: "0 1px 2px rgba(20,25,25,0.05)",
        sm: "0 1px 3px rgba(20,25,25,0.08), 0 1px 2px rgba(20,25,25,0.04)",
        md: "0 4px 6px -1px rgba(20,25,25,0.08), 0 2px 4px -2px rgba(20,25,25,0.04)",
        lg: "0 10px 15px -3px rgba(20,25,25,0.08), 0 4px 6px -4px rgba(20,25,25,0.04)",
        xl: "0 20px 25px -5px rgba(20,25,25,0.08), 0 8px 10px -6px rgba(20,25,25,0.04)",
      },
    },
  },
  plugins: [
    require("@tailwindcss/forms"),
    require("@tailwindcss/typography"),
  ],
}
```

---

## 21. CSS Custom Properties

For non-Tailwind contexts or component-level overrides:

```css
:root {
  /* Blue */
  --blue-50: #E8F4F8;  --blue-100: #C5E4EE;  --blue-200: #8DC9DD;
  --blue-300: #55AECC;  --blue-400: #35A4C8;  --blue-500: #28A0C8;
  --blue-600: #2290B5;  --blue-700: #1B7A99;  --blue-800: #15647D;
  --blue-900: #0E4457;

  /* Green */
  --green-50: #F0F7E6;  --green-100: #D9EDBE;  --green-200: #BCE293;
  --green-300: #A0D768;  --green-400: #8CC83C;  --green-500: #7DB835;
  --green-600: #6FA52F;  --green-700: #5C8D27;  --green-800: #49751F;
  --green-900: #365413;

  /* Gray */
  --gray-50: #F7FAFA;  --gray-100: #EEF2F3;  --gray-200: #DCE1E3;
  --gray-300: #B8C0C4;  --gray-400: #8B969C;  --gray-500: #657078;
  --gray-600: #4A545B;  --gray-700: #353D42;  --gray-800: #232A2E;
  --gray-900: #141919;

  /* Semantic */
  --success: #2ECC71;      --success-light: #E8F8F0;
  --warning: #F39C12;      --warning-light: #FEF5E7;
  --error: #E74C3C;        --error-light: #FDEDEC;

  /* Fonts */
  --font-display: 'Plus Jakarta Sans', sans-serif;
  --font-body: 'DM Sans', sans-serif;
  --font-mono: 'JetBrains Mono', monospace;

  /* Transitions */
  --ease: cubic-bezier(0.4, 0, 0.2, 1);
}
```

---

## 22. Google Fonts Import

### HTML `<head>` (recommended)

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&family=DM+Sans:ital,wght@0,400;0,500;0,600;0,700;1,400&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">
```

### CSS `@import` (fallback)

```css
@import url('https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&family=DM+Sans:ital,wght@0,400;0,500;0,600;0,700;1,400&family=JetBrains+Mono:wght@400;500;600&display=swap');
```

### Base Stylesheet

```css
/* app/assets/stylesheets/application.tailwind.css */
@tailwind base;
@tailwind components;
@tailwind utilities;

@layer base {
  body {
    @apply font-body text-gray-800 antialiased;
  }
  h1, h2, h3, h4, h5, h6 {
    @apply font-display;
  }
}
```

---

## 23. Icon System

Use **Lucide Icons** (included with Rails via `lucide-rails` gem or CDN).

### Recommended Icons

| Context | Icon | Lucide Name |
|---|---|---|
| Bookings | 📋 | `clipboard-list` |
| Customers | 👥 | `users` |
| Payments | 💰 | `banknote` |
| Dashboard | 📊 | `bar-chart-3` |
| Waste types | 📦 | `package` |
| Buy rates | 💲 | `badge-dollar-sign` |
| Blog | 📝 | `file-text` |
| Settings | ⚙️ | `settings` |
| WhatsApp | — | `message-circle` (or WhatsApp SVG) |
| Phone | — | `phone` |
| Calendar | — | `calendar` |
| Weight | — | `scale` |
| Location | — | `map-pin` |
| Truck/Driver | — | `truck` |
| Success | — | `check-circle` |
| Warning | — | `alert-triangle` |
| Error | — | `x-circle` |
| Info | — | `info` |
| Edit | — | `pencil` |
| Delete | — | `trash-2` |
| View | — | `eye` |
| Download | — | `download` |
| Search | — | `search` |

### Icon Sizing

| Context | Size | Stroke Width |
|---|---|---|
| Inline with text | 16px | 2 |
| Button icon | 18px | 2 |
| Card icon | 20px | 1.5 |
| Feature icon | 24px | 1.5 |
| Hero / stat icon | 32px+ | 1.5 |

---

## 24. Currency & Number Formatting

### Currency (Nigerian Naira)

- Symbol: `₦` (Unicode: U+20A6)
- Format: `₦1,234.56` — symbol, no space, comma-separated thousands, 2 decimal places for exact amounts
- Whole numbers: `₦4,375` — no decimal places when amount is whole
- Always display with the Naira symbol, never "NGN" in user-facing text
- Use `font-mono` for all currency values

### Weights

- Unit: `kg` (kilograms)
- Format: `12.5 kg` — one decimal place, space before unit
- Use `font-mono` for weight values
- Display `—` when weight is not yet recorded

### Rates

- Format: `₦350/kg` — no space around slash
- Use `font-mono` for rate values

### Booking References

- Format: `GEV-YYYYMMDD-NNN` (e.g., `GEV-20260215-003`)
- Always `font-mono`, 0.78rem
- Left-aligned in tables

### Phone Numbers

- Display format: `0803 620 5243` (grouped for readability) or `+234 803 620 5243`
- Storage format: `+2348036205243` (E.164)

### Dates

- Display: `15 Feb 2026` (day month year, abbreviated month)
- Time: `2:30 PM` (12-hour with AM/PM)
- Combined: `15 Feb 2026, 2:30 PM`
- Relative: "2 minutes ago", "Yesterday", "3 days ago"

---

## 25. Responsive Breakpoints

| Name | Min Width | Usage |
|---|---|---|
| sm | 640px | Mobile landscape |
| md | 768px | Tablets |
| lg | 1024px | Laptops, admin dashboard |
| xl | 1280px | Desktop |

### Key Responsive Rules

- **Mobile first:** Write base styles for mobile, add breakpoints for larger screens
- **Public site:** Single column on mobile, 2–3 columns on tablet+
- **Admin dashboard:** Stack sidebar below content on mobile, side-by-side at `lg`
- **Tables:** Horizontal scroll on mobile (`overflow-x-auto`), no column hiding
- **Font sizes:** Display drops from 48px to ~32px on mobile, H1 from 36px to ~28px
- **Spacing:** Section padding drops from sp-13 (96px) to sp-9 (48px) on mobile
- **Button sizes:** Full-width on mobile for primary CTAs
- **Navigation:** Hamburger menu on mobile for public site, collapsible sidebar for admin

---

*End of GEV Design System v2.0*
*Reference this document when implementing any UI component for the Genius Eco Visionaries platform.*
