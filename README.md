# GEV Design System v3.0

> **Genius Eco Visionaries** — Small Changes, Big Impact
> Reference document for Claude Code when building the GEV platform (web + mobile).
> Last updated: February 2026

---

## Platform Overview

GEV is a **single Rails 8 codebase** serving three surfaces:

| Surface | Technology | Users | Purpose |
|---|---|---|---|
| **Public Website** | Rails 8 + Turbo + Tailwind | Everyone | Marketing, pricing, blog, booking form |
| **Mobile Booking App** | Turbo Native (iOS + Android) | Customers | Book pickups, track status, view earnings, get notifications |
| **Admin Dashboard** | Rails 8 + Turbo + Tailwind | Owner / Admin | Manage bookings, customers, rates, payments, blog |

All three surfaces share the same controllers, models, and business logic. Views are differentiated using Turbo Native request detection and responsive Tailwind classes. The mobile app is a native shell wrapping the Rails views — NOT a separate SPA or React Native project.

---

## Table of Contents

**Foundation**
1. [Brand Identity](#1-brand-identity)
2. [Logo System](#2-logo-system)
3. [Colour Palette](#3-colour-palette)
4. [Typography](#4-typography)
5. [Spacing Scale](#5-spacing-scale)
6. [Border Radius](#6-border-radius)
7. [Shadows / Elevation](#7-shadows--elevation)
8. [Transitions & Motion](#8-transitions--motion)

**Components**
9. [Buttons](#9-buttons)
10. [Badges](#10-badges)
11. [Alerts & Toasts](#11-alerts--toasts)
12. [Form Elements](#12-form-elements)
13. [Cards](#13-cards)
14. [Tables](#14-tables)
15. [Avatars](#15-avatars)

**Layout & Navigation**
16. [Navigation — Web](#16-navigation--web)
17. [Navigation — Mobile App](#17-navigation--mobile-app)
18. [Page Layout — Web](#18-page-layout--web)
19. [Page Layout — Mobile App](#19-page-layout--mobile-app)

**Mobile App**
20. [Turbo Native Architecture](#20-turbo-native-architecture)
21. [Mobile Booking Flow](#21-mobile-booking-flow)
22. [Mobile Customer Dashboard](#22-mobile-customer-dashboard)
23. [Mobile-Specific Components](#23-mobile-specific-components)
24. [Push Notifications](#24-push-notifications)
25. [Native Bridge & Platform Features](#25-native-bridge--platform-features)
26. [App Store Presence](#26-app-store-presence)

**Guidelines**
27. [Voice & Tone](#27-voice--tone)
28. [Accessibility](#28-accessibility)
29. [Currency & Number Formatting](#29-currency--number-formatting)
30. [Icon System](#30-icon-system)
31. [Responsive Breakpoints](#31-responsive-breakpoints)

**Implementation**
32. [Tailwind CSS Configuration](#32-tailwind-css-configuration)
33. [CSS Custom Properties](#33-css-custom-properties)
34. [Google Fonts Import](#34-google-fonts-import)

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

GEV is a **recycling company** that operates a recycling plant in Edo State. GEV **pays customers** for their recyclable materials (plastics, aluminium cans / UBC), collects them via scheduled pickups, and processes them at their plant into usable recycled raw materials. These recycled materials are sold as feedstock to manufacturing companies — particularly plastics manufacturers — completing the circular economy loop. The key differentiator for customers: they earn money from materials they'd otherwise throw away.

### Mission

Sustainable waste management through recycling — collecting recyclable materials from the community, processing them at our plant into reusable raw materials (feedstock), and supplying them to manufacturers. This creates a circular economy that extracts economic value from materials that would otherwise end up in landfills and waterways.

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
| Primary | "Turn Your Waste Into Cash" | Hero headlines, ads, app store listing |
| Secondary | "Small Changes, Big Impact" | Tagline, footer, environmental messaging |
| Supporting | "We come to you" | Convenience messaging, booking flow |
| Supporting | "We pay you" | Value prop, pricing page, app onboarding |
| Supporting | "Free pickup" | Booking CTA, onboarding |
| App-specific | "Book. Weigh. Get Paid." | App store description, mobile onboarding |

---

## 2. Logo System

### Logo Files

- **Transparent PNG:** `GEV_Logo_Transparent.png` (1024x1024, RGBA)
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
| Desktop navbar | 32-40px icon | Icon only, or icon + wordmark at 120px+ wide |
| Mobile navbar | 28-32px icon | Icon only |
| Mobile app splash screen | 96-120px icon | Centred, on gray-900 background |
| Mobile app tab bar header | 24-28px icon | Top-left corner, icon only |
| App icon (iOS/Android) | 1024x1024 source | Rounded corners applied by OS |
| Favicon | 16px | Simplified icon mark |
| Footer | 48px icon | Icon above company name |
| Email signature | 40px icon | Inline with company name |
| Print (minimum) | 15mm | Icon mark |

### App Icon

The app icon uses the full logo mark on a `gray-900` (#141919) background with slight padding (18% each side). The OS applies rounded corners automatically — do NOT pre-round the icon.

### Clear Space

Maintain minimum clear space equal to 1x the height of one leaf element on all sides.

### Logo Don'ts

- Do NOT stretch or distort proportions
- Do NOT rotate the logo
- Do NOT reduce opacity below 100%
- Do NOT place on clashing or busy backgrounds
- Do NOT recolour the leaves
- Do NOT add drop shadows or effects
- Do NOT separate the two leaves
- Do NOT use the old JPEG with black background

---

## 3. Colour Palette

### Blue (Primary)

Used for: navigation, links, interactive elements, headers, info states, active tab bar items.

| Token | Hex | Tailwind Class | Usage |
|---|---|---|---|
| blue-50 | `#E8F4F8` | `bg-blue-50` | Info backgrounds, card tints |
| blue-100 | `#C5E4EE` | `bg-blue-100` | Hover backgrounds |
| blue-200 | `#8DC9DD` | `bg-blue-200` | Borders, dividers |
| blue-300 | `#55AECC` | `text-blue-300` | Secondary links, outline borders |
| blue-400 | `#35A4C8` | `text-blue-400` | Focus rings, active borders |
| **blue-500** | **`#28A0C8`** | **`bg-blue-500`** | **PRIMARY — buttons, nav, links, mobile tab active** |
| blue-600 | `#2290B5` | `bg-blue-600` | Button hover / pressed |
| blue-700 | `#1B7A99` | `text-blue-700` | Headings on light bg, badge text |
| blue-800 | `#15647D` | `text-blue-800` | Alert text on info bg |
| blue-900 | `#0E4457` | `text-blue-900` | Dark mode text |

### Green (Secondary / CTA)

Used for: calls-to-action, money/earnings displays, eco messaging, success accents.

| Token | Hex | Tailwind Class | Usage |
|---|---|---|---|
| green-50 | `#F0F7E6` | `bg-green-50` | CTA section backgrounds, earnings card bg |
| green-100 | `#D9EDBE` | `bg-green-100` | Highlight boxes |
| green-200 | `#BCE293` | `bg-green-200` | Borders |
| green-300 | `#A0D768` | `text-green-300` | Accents |
| **green-400** | **`#8CC83C`** | **`bg-green-400`** | **SECONDARY — CTA buttons, "ECO" in wordmark, earnings** |
| green-500 | `#7DB835` | `bg-green-500` | CTA hover, pricing numbers |
| green-600 | `#6FA52F` | `bg-green-600` | Pressed state |
| green-700 | `#5C8D27` | `text-green-700` | Dark text on green bg |
| green-800 | `#49751F` | `text-green-800` | — |
| green-900 | `#365413` | `text-green-900` | — |

### Neutrals

| Token | Hex | Tailwind Class | Usage |
|---|---|---|---|
| gray-50 | `#F7FAFA` | `bg-gray-50` | Page backgrounds, mobile screen bg |
| gray-100 | `#EEF2F3` | `bg-gray-100` | Card backgrounds, mobile list separators |
| gray-200 | `#DCE1E3` | `border-gray-200` | Borders, dividers, card strokes |
| gray-300 | `#B8C0C4` | `text-gray-300` | Disabled text, placeholder icons |
| gray-400 | `#8B969C` | `text-gray-400` | Placeholder text, inactive tab icons |
| gray-500 | `#657078` | `text-gray-500` | Secondary text, descriptions |
| gray-600 | `#4A545B` | `text-gray-600` | Body text (alternate) |
| gray-700 | `#353D42` | `text-gray-700` | Body text (default in some contexts) |
| gray-800 | `#232A2E` | `text-gray-800` | **Default body text colour** |
| gray-900 | `#141919` | `bg-gray-900` | Headings, footer bg, hero bg, app splash |

### Semantic Colours

| Name | Colour | Light BG | Usage |
|---|---|---|---|
| Success | `#2ECC71` | `#E8F8F0` | Completed pickups, payment confirmed |
| Warning | `#F39C12` | `#FEF5E7` | Pending actions, rate changes |
| Error | `#E74C3C` | `#FDEDEC` | Failed actions, validation errors |
| Info | `#28A0C8` | `#E8F4F8` | System updates, tips |

### Colour Usage Rules

- **Blue-500** is the primary interactive colour (buttons, links, nav, active tab bar items)
- **Green-400** is reserved for CTAs related to money/eco actions
- Never use Blue and Green as equal-weight CTAs on the same view
- Red is ONLY for errors and destructive actions
- Use light tints (50/100) for section and card backgrounds
- WCAG AA contrast minimum (4.5:1 for text)
- On mobile tab bar: `blue-500` for active, `gray-400` for inactive

---

## 4. Typography

### Font Families

| Role | Font | Fallback | Used For |
|---|---|---|---|
| Display | Plus Jakarta Sans | system sans-serif | Headings, buttons, labels, nav, badges |
| Body | DM Sans | system sans-serif | Paragraphs, descriptions |
| Mono | JetBrains Mono | system monospace | Prices, weights, refs, code, data |

### Type Scale — Web

| Name | Size | Weight | Font | Letter Spacing | Line Height | Use Case |
|---|---|---|---|---|---|---|
| Display | 48px (3rem) | 800 | Display | -0.04em | 1.05 | Hero headlines only |
| H1 | 36px (2.25rem) | 800 | Display | -0.02em | 1.15 | Page titles |
| H2 | 28px (1.75rem) | 700 | Display | -0.02em | 1.2 | Section headings |
| H3 | 22px (1.375rem) | 700 | Display | -0.01em | 1.3 | Card headers, subsections |
| H4 | 18px (1.125rem) | 600 | Display | 0 | 1.4 | Widget titles |
| Body | 16px (1rem) | 400 | Body | 0 | 1.6 | Default paragraph text |
| Body Small | 14px (0.875rem) | 400 | Body | 0 | 1.5 | Secondary text, table cells |
| Caption | 12px (0.75rem) | 500 | Body | 0 | 1.4 | Timestamps, metadata |
| Label | 12px (0.75rem) | 600 | Display | 0.06em | 1.2 | Form labels, uppercase tags |
| Data | 14px (0.875rem) | 500 | Mono | 0 | 1.4 | Prices, weights, refs |
| Data Large | 2.2rem+ | 700 | Mono | 0 | 1 | Dashboard stats, pricing cards |

### Type Scale — Mobile App

Mobile views use a tighter scale. Apply via `turbo-native` body class or responsive utilities.

| Name | Web Size | Mobile Size | Notes |
|---|---|---|---|
| Display | 48px | NOT USED | Mobile largest heading is H1 |
| H1 | 36px | 28px (1.75rem) | Screen titles |
| H2 | 28px | 22px (1.375rem) | Section headers |
| H3 | 22px | 18px (1.125rem) | Card titles |
| H4 | 18px | 16px (1rem) | Widget labels |
| Body | 16px | 16px | **Same — never below 16px on mobile** |
| Body Small | 14px | 14px | Same |
| Caption | 12px | 12px | Absolute minimum |
| Data | 14px | 14px | Same |
| Data Large | 2.2rem | 1.75rem | Earnings total, rate cards |

### Typography Rules

- All headings: `font-display` (Plus Jakarta Sans)
- All body text: `font-body` (DM Sans)
- All numeric data: `font-mono` (JetBrains Mono)
- Negative letter-spacing on headings H2 and above
- Labels: always uppercase with `letter-spacing: 0.06em`
- Never below 12px for any text on any surface
- **Mobile: never below 16px for body/input text** — prevents iOS auto-zoom
- Never bold entire paragraphs
- Never mix font families within the same element

---

## 5. Spacing Scale

4px base unit.

| Token | Value | Tailwind | Common Use |
|---|---|---|---|
| sp-1 | 4px | `p-1` | Tight inner spacing, badge padding |
| sp-2 | 8px | `p-2` | Input padding, small gaps |
| sp-3 | 12px | `p-3` | Label-input gap, nav link padding |
| sp-4 | 16px | `p-4` | Card padding, **mobile screen horizontal padding** |
| sp-5 | 20px | `p-5` | Alert padding, form group spacing |
| sp-6 | 24px | `p-6` | Card body padding (web) |
| sp-7 | 32px | `p-8` | Large card padding |
| sp-8 | 40px | `p-10` | Component padding |
| sp-9 | 48px | `p-12` | Section inner spacing |
| sp-10 | 56px | — | — |
| sp-11 | 64px | `p-16` | Section title to content |
| sp-12 | 80px | `p-20` | Between subsections |
| sp-13 | 96px | `py-24` | Section vertical padding (web) |
| sp-14 | 128px | `py-32` | Hero vertical padding (web) |

### Mobile Spacing Notes

- Horizontal screen padding: always `px-4` (16px)
- Vertical section spacing: `py-6` (24px) on mobile vs `py-24` on web
- Card padding: `p-4` (16px) on mobile vs `p-6` (24px) on web
- Bottom clearance: minimum `pb-[100px]` to clear tab bar

---

## 6. Border Radius

| Token | Value | Tailwind | Usage |
|---|---|---|---|
| r-sm | 6px | `rounded-sm` | Small buttons, compact badges |
| r-md | 10px | `rounded-md` | **Default** — buttons, inputs, alerts |
| r-lg | 16px | `rounded-lg` | Cards, modals, dropdowns |
| r-xl | 24px | `rounded-xl` | Hero cards, mobile bottom sheets (top corners) |
| r-full | 9999px | `rounded-full` | Avatars, pills, badges, FABs |

### Rules

- Interactive elements: `r-md` (10px)
- Container elements: `r-lg` (16px)
- Never sharp corners (0px) — brand is warm and approachable
- Bottom sheets: `rounded-t-xl` (24px top corners only)

---

## 7. Shadows / Elevation

| Token | Value | Tailwind | Usage |
|---|---|---|---|
| sh-xs | `0 1px 2px rgba(20,25,25,0.05)` | `shadow-xs` | Inputs, swatches |
| sh-sm | `0 1px 3px rgba(20,25,25,0.08), 0 1px 2px rgba(20,25,25,0.04)` | `shadow-sm` | Cards at rest |
| sh-md | `0 4px 6px -1px rgba(20,25,25,0.08), 0 2px 4px -2px rgba(20,25,25,0.04)` | `shadow-md` | Dropdowns, mobile headers |
| sh-lg | `0 10px 15px -3px rgba(20,25,25,0.08), 0 4px 6px -4px rgba(20,25,25,0.04)` | `shadow-lg` | Hover cards, modals, bottom sheets |
| sh-xl | `0 20px 25px -5px rgba(20,25,25,0.08), 0 8px 10px -6px rgba(20,25,25,0.04)` | `shadow-xl` | Toasts, FABs |

### Rules

- Shadows use `rgba(20,25,25,...)` NOT pure black
- Web cards: `shadow-sm` rest, `shadow-lg` hover
- Mobile: no hover shadows — use `shadow-sm` consistently
- Mobile tab bar: `shadow-[0_-1px_3px_rgba(20,25,25,0.06)]` (upward)
- Buttons use coloured shadows matching their background

---

## 8. Transitions & Motion

### Web

| Duration | Easing | Usage |
|---|---|---|
| 150ms | `cubic-bezier(0.4, 0, 0.2, 1)` | Button hover, input focus |
| 250ms | `cubic-bezier(0.4, 0, 0.2, 1)` | Card hover, dropdown |
| 400ms | `cubic-bezier(0.4, 0, 0.2, 1)` | Modal, accordion |

### Mobile

| Animation | Duration | Easing | Notes |
|---|---|---|---|
| Screen push/pop | 300/250ms | Native | Turbo Native handles this |
| Bottom sheet slide | 350ms | `cubic-bezier(0.32, 0.72, 0, 1)` | iOS spring-like |
| Pull to refresh | 300ms | Native | Turbo Native handles this |
| Toast slide in | 300ms | ease-out | From top, 3s auto-dismiss |
| Skeleton shimmer | 1.5s | linear infinite | Loading placeholders |
| FAB press | 100ms | ease-in-out | Scale to 0.95 |

### Rules

- Respect `prefers-reduced-motion`
- Turbo Native handles screen transitions natively — don't duplicate in CSS
- Use Turbo Frame loading indicators, not custom spinners

---

## 9. Buttons

### Variants

| Variant | Classes | Use Case |
|---|---|---|
| Primary | `bg-blue-500 text-white` | Navigation, general actions |
| CTA | `bg-green-400 text-white` | Money/eco actions ("Book", "Sell", "Earn") |
| Outline | `bg-transparent text-blue-500 border border-blue-300` | Secondary actions |
| Ghost | `bg-transparent text-gray-600` | Tertiary ("Cancel", "Dismiss") |
| White | `bg-white text-gray-800 border border-gray-200` | On coloured backgrounds |
| Danger | `bg-error text-white` | Destructive — use sparingly |

### Sizes

| Size | Padding | Font | Min Height | Usage |
|---|---|---|---|---|
| sm | `7px 14px` | 0.8rem | 32px | Table actions, compact UI |
| md | `10px 20px` | 0.875rem | 40px | **Default** |
| lg | `14px 28px` | 1rem | 48px | Hero CTAs, form submit |
| xl | `16px 28px` | 1rem | 52px | **Mobile full-width CTAs** |

### Mobile Button Rules

- All primary CTAs on mobile: **full-width** (`w-full`)
- Minimum touch target: **48x48px** (Apple HIG)
- Use `active:scale-[0.98]` instead of hover states
- Disabled: 50% opacity, `pointer-events-none`
- CTA buttons include right arrow: `Schedule Free Pickup →`

### Sticky Bottom CTA (Mobile)

```html
<div class="fixed bottom-0 inset-x-0 p-4 bg-white border-t border-gray-200
            safe-area-bottom native-only">
  <button class="w-full bg-green-400 text-white font-display font-semibold
                 rounded-md px-7 py-4 text-base min-h-[52px]
                 active:bg-green-500 active:scale-[0.98]
                 transition-all duration-150">
    Schedule Free Pickup →
  </button>
</div>
```

### ERB Pattern

```erb
<%# Primary button %>
<%= link_to "Schedule Pickup", new_booking_path,
    class: "inline-flex items-center justify-center gap-2 font-display font-semibold
           bg-blue-500 text-white rounded-md px-5 py-2.5 text-sm
           hover:bg-blue-600 hover:-translate-y-px
           active:bg-blue-600 active:scale-[0.98]
           shadow-[0_1px_2px_rgba(40,160,200,0.3)]
           transition-all duration-150" %>
```

---

## 10. Badges

| Status | Background | Text | Dot | Labels |
|---|---|---|---|---|
| Success | `#E8F8F0` | `#1a8a4a` | `#2ECC71` | Completed, Paid, Published |
| Warning | `#FEF5E7` | `#9a6b0b` | `#F39C12` | Pending, Scheduled, Draft |
| Error | `#FDEDEC` | `#a93226` | `#E74C3C` | Cancelled, Failed |
| Info | `#E8F4F8` | `#1B7A99` | `#28A0C8` | Confirmed, Assigned, Active |
| Neutral | `#EEF2F3` | `#4A545B` | `#8B969C` | Draft, Inactive |

### Booking Status Flow

`pending` → `confirmed` → `assigned` → `in_progress` → `completed` / `cancelled`

| Status | Badge | Mobile Label |
|---|---|---|
| pending | Warning | "Awaiting Confirmation" |
| confirmed | Info | "Confirmed" |
| assigned | Info | "Driver Assigned" |
| in_progress | Info | "Pickup In Progress" |
| completed | Success | "Completed — ₦X Paid" |
| cancelled | Error | "Cancelled" |

On mobile, badges may include more descriptive labels since screen space is dedicated to one booking.

---

## 11. Alerts & Toasts

### Alerts (Inline — Web & Admin)

| Variant | Border | Background | Text | Icon |
|---|---|---|---|---|
| Success | `border-success` | `bg-success-light` | `#1a6b3a` | ✓ |
| Warning | `border-warning` | `bg-warning-light` | `#7a5509` | ⚠ |
| Error | `border-error` | `bg-error-light` | `#8a2a20` | ✗ |
| Info | `border-blue-500` | `bg-blue-50` | `#15647D` | ℹ |

### Toasts (Mobile)

Slide-down toasts for action confirmations on mobile.

| Property | Value |
|---|---|
| Position | Top, below safe area |
| Background | `gray-900` at 95% opacity |
| Text | White, `font-body`, 0.875rem |
| Icon | Left-aligned, coloured by type |
| Radius | `r-lg` (16px) |
| Shadow | `sh-xl` |
| Margin | 16px horizontal |
| Animation | Slide down 300ms, auto-dismiss 3s |
| Dismiss | Swipe up or tap |
| Max lines | 2 |

---

## 12. Form Elements

### Input Styling

```html
<div class="flex flex-col gap-2">
  <label class="font-display text-sm font-semibold text-gray-700">Full Name *</label>
  <input type="text"
    class="font-body text-base px-3.5 py-3 border-[1.5px] border-gray-200 rounded-md
           text-gray-800 bg-white outline-none transition-all duration-150
           focus:border-blue-400 focus:ring-[3px] focus:ring-blue-500/12
           placeholder:text-gray-400"
    placeholder="e.g., John Okafor" />
  <span class="text-xs text-gray-400">Helper text</span>
</div>
```

### Input States

| State | Border | Ring | Text |
|---|---|---|---|
| Default | `gray-200` | none | `gray-800` |
| Focus | `blue-400` | `ring-blue-500/12` | `gray-800` |
| Error | `error` | none | `gray-800` |
| Disabled | `gray-200`, `bg-gray-50` | none | `gray-400` |

### Mobile Form Rules

- **Font size minimum 16px** on all inputs — prevents iOS auto-zoom
- Input height: minimum 48px
- Use native input types: `type="tel"`, `type="email"`, `inputmode="decimal"`
- Use `autocomplete` attributes: `name`, `tel`, `email`, `street-address`
- **Stack all fields vertically on mobile** — no side-by-side
- Full-width submit button fixed to bottom on long forms

### Booking Form Fields

**Required:**

| Field | Type | Mobile Keyboard | Placeholder |
|---|---|---|---|
| Full Name * | text | default | "e.g., John Okafor" |
| WhatsApp Number * | tel | phone pad | "+234..." |
| Pickup Address * | text | default | "e.g., 15 Akpakpava Road, Benin City" |

**Optional:**

| Field | Type | Mobile Keyboard | Options |
|---|---|---|---|
| Waste Type | select | native picker | Plastics, Aluminium Cans (UBC) |
| Est. Weight (kg) | number | decimal pad | "e.g., 25" |
| Email | email | email keyboard | "your@email.com" |
| Preferred Date | date | native date picker | — |
| Landmark | text | default | "Near..." |
| Special Instructions | textarea | default | "Any access notes..." |

---

## 13. Cards

### Default Card

```html
<div class="bg-white border border-gray-200 rounded-lg overflow-hidden
            transition-all duration-250 hover:shadow-lg hover:border-gray-300">
  <div class="p-6 max-md:p-4">
    <!-- Content -->
  </div>
</div>
```

### Buy Rate Card

```html
<div class="bg-white border border-gray-200 rounded-lg p-7 max-md:p-5 text-center">
  <div class="font-mono text-[2.2rem] max-md:text-[1.75rem] font-bold text-blue-500 mb-2">₦350</div>
  <div class="font-display text-sm font-semibold text-gray-700">Plastics</div>
  <div class="text-xs text-gray-400 mt-0.5">per kilogram</div>
</div>
```

### Mobile Booking Card

```html
<div class="bg-white border border-gray-200 rounded-lg p-4">
  <div class="flex items-center justify-between mb-2">
    <span class="font-mono text-xs text-blue-500">GEV-20260215-003</span>
    <span class="badge badge-success">Completed</span>
  </div>
  <div class="text-sm text-gray-800 mb-1">Plastics · 12.5 kg</div>
  <div class="text-xs text-gray-400 mb-3">15 Feb 2026, 2:30 PM</div>
  <div class="font-mono text-lg font-bold text-green-500">₦4,375 paid</div>
</div>
```

### Mobile Earnings Summary Card

```html
<div class="bg-gradient-to-br from-green-400 to-green-600 rounded-xl p-6 text-white">
  <div class="text-sm font-display font-medium opacity-80 mb-1">Total Earnings</div>
  <div class="font-mono text-3xl font-bold mb-3">₦47,350</div>
  <div class="flex justify-between text-sm opacity-80">
    <span>12 pickups</span>
    <span>Since Jan 2026</span>
  </div>
</div>
```

---

## 14. Tables

Used in admin dashboard only. On mobile customer app, replace tables with card lists.

### Admin Table

```html
<table class="w-full text-sm border-collapse">
  <thead>
    <tr>
      <th class="font-display font-semibold text-xs uppercase tracking-wider
                 text-gray-500 bg-gray-50 px-4 py-3 text-left border-b-2 border-gray-200">
        Reference
      </th>
    </tr>
  </thead>
  <tbody>
    <tr class="hover:bg-blue-50 transition-colors">
      <td class="px-4 py-3 border-b border-gray-100 font-mono text-xs">GEV-20260215-001</td>
    </tr>
  </tbody>
</table>
```

### Column Types

| Column | Font | Alignment |
|---|---|---|
| Reference / ID | `font-mono`, 0.78rem | Left |
| Names | `font-body` | Left |
| Weight | `font-mono` | Right |
| Amount | `font-mono`, weight 500 | Right |
| Date | `font-mono`, 0.78rem | Left |
| Status | Badge component | Centre |
| Actions | Ghost buttons (sm) | Right |

Tables on mobile admin: `overflow-x-auto` for horizontal scroll.

---

## 15. Avatars

Initials-based.

| Size | Dimensions | Font | Usage |
|---|---|---|---|
| sm | 32px | 0.75rem | Compact lists |
| md | 40px | 0.85rem | Default — nav, tables |
| lg | 48px | 1rem | Profile screen, headers |

Default: `bg-blue-500`. Alternate: `bg-green-400`. Initials: first + last name uppercase.

---

## 16. Navigation — Web

### Public Navbar

```
[Logo 32px] [Home] [About] [Services] [Pricing] [Blog] [Contact]     [Schedule Pickup →]
```

- Sticky, white bg, `backdrop-filter: blur(14px)`, `border-bottom: 1px solid gray-200`
- Links: `font-display`, 0.85rem, weight 600, `text-gray-600`
- Active: `text-blue-500`
- Mobile (<md): hamburger menu

### Admin Sidebar

256px fixed on `lg`+, collapsible below. Items: Dashboard, Bookings, Customers, Payments, Waste Types, Buy Rates, Blog Posts, Post Categories, Settings.

---

## 17. Navigation — Mobile App

### Bottom Tab Bar

```
┌────┬─────────┬──────────┬──────┬───────┐
│ 🏠 │   📋    │    ➕     │  💰  │  👤   │
│Home │Bookings │  Book    │Earn  │Profile│
└────┴─────────┴──────────┴──────┴───────┘
```

| Tab | Icon (Lucide) | Label | Destination |
|---|---|---|---|
| Home | `home` | Home | Dashboard: rates + recent bookings |
| Bookings | `clipboard-list` | Bookings | Booking history list |
| Book | `plus-circle` | Book | New booking form (elevated centre tab) |
| Earnings | `banknote` | Earnings | Earnings history + total |
| Profile | `user` | Profile | Account settings |

### Tab Bar Styling

| Property | Value |
|---|---|
| Background | White |
| Border top | `1px solid gray-200` |
| Shadow | `0 -1px 3px rgba(20,25,25,0.06)` |
| Height | 56px + safe area bottom |
| Active colour | `blue-500` |
| Inactive colour | `gray-400` |
| Icon size | 24px |
| Label font | `font-display`, 10px, weight 600 |

### Centre "Book" Tab (Elevated)

```html
<div class="relative -top-4 w-14 h-14 rounded-full bg-green-400 flex items-center justify-center
            shadow-[0_4px_12px_rgba(140,200,60,0.4)]">
  <svg class="w-7 h-7 text-white"><!-- plus icon --></svg>
</div>
```

### Screen Header

Turbo Native renders native navigation bars. Rails provides title via `<title>` tag.

| Property | Value |
|---|---|
| Height | 56px + safe area top |
| Title | `font-display`, 17px, weight 700, centred |
| Back button | `blue-500`, `chevron-left` 24px |
| Right action | Optional icon or text link |

---

## 18. Page Layout — Web

### Public Pages

- Max width: 1100px, centred
- Horizontal padding: 24px
- Section vertical padding: 96px
- Section separator: 1px solid gray-200

### Admin Dashboard

- Sidebar: 256px fixed
- Content: fluid, max-width 1200px
- Padding: 24-32px
- Card gap: 20-24px

---

## 19. Page Layout — Mobile App

### Screen Structure

```
┌──────────────────────────────┐
│ ▓▓▓ Safe Area Top ▓▓▓▓▓▓▓▓  │  OS status bar
├──────────────────────────────┤
│ ← Back       Title     [⋯]  │  Native nav (56px)
├──────────────────────────────┤
│                              │
│     Scrollable content       │  px-4, bg: gray-50 or white
│     (Turbo Frame)            │
│                              │
│                              │  pb-[100px] to clear tab bar
├──────────────────────────────┤
│  🏠  📋  ➕  💰  👤         │  Tab bar (56px + safe area)
├──────────────────────────────┤
│ ▓▓▓ Safe Area Bottom ▓▓▓▓▓  │  Home indicator
└──────────────────────────────┘
```

### Safe Areas

```css
.safe-area-bottom { padding-bottom: env(safe-area-inset-bottom, 0px); }
.safe-area-top { padding-top: env(safe-area-inset-top, 0px); }
```

### Key Screens

| Screen | Background | Fixed Elements |
|---|---|---|
| Home | `gray-50` | None |
| New Booking | White | Sticky bottom CTA |
| Booking Detail | White | None |
| Bookings List | `gray-50` | None (pull to refresh) |
| Earnings | `gray-50` | None (pull to refresh) |
| Profile | `gray-50` | None |

---

## 20. Turbo Native Architecture

### Request Detection

```ruby
# app/controllers/application_controller.rb
class ApplicationController < ActionController::Base
  helper_method :turbo_native_app?

  def turbo_native_app?
    request.user_agent&.match?(/Turbo Native/)
  end

  before_action :set_variant
  def set_variant
    request.variant = :phone if turbo_native_app?
  end
end
```

### View Strategy

| Approach | When |
|---|---|
| Same view + responsive Tailwind | Most screens — layout only needs CSS changes |
| View variant (`+phone.erb`) | Fundamentally different structure (home dashboard, nav) |
| Shared partials | Forms, cards, badges — always share |

### CSS Platform Classes

```ruby
# In layout:
<body class="<%= 'turbo-native' if turbo_native_app? %>">
```

```css
.turbo-native .web-only { display: none !important; }
body:not(.turbo-native) .native-only { display: none !important; }
```

### View Variants

```
app/views/bookings/
  index.html.erb          # Web (default)
  index.html+phone.erb    # Mobile app
  show.html.erb           # Shared
  _form.html.erb          # Shared partial
```

### What Native Shell Handles

| Native (don't build in Rails) | Rails (build in views) |
|---|---|
| Navigation bar + transitions | Page title via `<title>` |
| Tab bar | Tab URLs |
| Status bar | — |
| Safe area insets | `env(safe-area-inset-*)` CSS |
| Push notification display | Notification content + delivery |
| Pull to refresh | Turbo reload |
| Splash screen | — |
| App icon | — |
| Camera picker | `<input type="file">` |

### Path Configuration

```json
{
  "settings": {
    "tabs": [
      { "title": "Home", "path": "/", "icon": "home" },
      { "title": "Bookings", "path": "/bookings", "icon": "clipboard-list" },
      { "title": "Book", "path": "/bookings/new", "icon": "plus-circle", "style": "accent" },
      { "title": "Earnings", "path": "/earnings", "icon": "banknote" },
      { "title": "Profile", "path": "/profile", "icon": "user" }
    ]
  },
  "rules": [
    { "patterns": ["/bookings/new"], "properties": { "presentation": "modal" } },
    { "patterns": ["/bookings/\\d+/cancel"], "properties": { "presentation": "sheet" } },
    { "patterns": [".*"], "properties": { "presentation": "push" } }
  ]
}
```

---

## 21. Mobile Booking Flow

### Flow

```
Home → Tap "Book" tab / CTA
  → New Booking (stacked form, sticky CTA)
    → Fill: name, WhatsApp, address (+ optional fields)
    → Tap "Schedule Free Pickup →"
      → Confirmation Screen
        → Ref displayed prominently
        → "We'll confirm within 30 minutes via WhatsApp"
        → [View Booking] → Detail screen
        → [Book Another] → New Booking
```

### Booking Detail Screen

Shows: booking ref (mono, blue-500), status badge, vertical status timeline, details section (type, weight, address, date), payment section (rate, actual weight, amount in green-500 mono bold), WhatsApp CTA button.

---

## 22. Mobile Customer Dashboard

### Home Screen

Top to bottom: small logo lockup → earnings summary card (green gradient, total in mono 3xl) → today's rates (two rate cards side by side) → recent bookings (card list, "See All →" link) → CTA button → 100px bottom clearance.

### Earnings Screen

Earnings summary card (with monthly breakdown) → filter pills (All, Plastics, UBC) → transaction list grouped by month → each row shows date, type, weight, amount.

### Profile Screen

Avatar (lg) → name → phone → settings list (Edit Profile, Saved Addresses, Notifications, Chat WhatsApp, About GEV) → Log Out ghost button → app version caption.

---

## 23. Mobile-Specific Components

### Status Timeline

Vertical timeline for booking progress.

| State | Dot | Line | Text |
|---|---|---|---|
| Completed | Solid `success` | Solid `success` | `gray-800` + timestamp |
| Current | Solid `blue-500` + pulse | Dashed `gray-300` | `gray-800` + "In progress" |
| Future | Hollow `border-gray-300` | Solid `gray-200` | `gray-400` |

### Filter Pills

Horizontal scrollable chips.

| State | Background | Text |
|---|---|---|
| Active | `blue-500` | White |
| Inactive | `gray-100` | `gray-600` |

### Skeleton Loading

```html
<div class="animate-pulse">
  <div class="h-32 bg-gray-200 rounded-xl mb-4"></div>
  <div class="h-5 bg-gray-200 rounded w-32 mb-3"></div>
  <div class="h-20 bg-gray-200 rounded-lg mb-3"></div>
  <div class="h-20 bg-gray-200 rounded-lg mb-3"></div>
</div>
```

### Empty States

Large icon + H3 title (`gray-800`) + body description (`gray-500`) + CTA button. Examples:
- Bookings: "No bookings yet. Schedule your first pickup and start earning."
- Earnings: "No earnings yet. Book your first pickup to start earning."

### Settings List Row

```html
<div class="flex items-center justify-between px-4 py-4 bg-white border-b border-gray-100
            active:bg-gray-50">
  <div class="flex items-center gap-3">
    <svg class="w-5 h-5 text-gray-500"><!-- icon --></svg>
    <span class="text-base text-gray-800">Edit Profile</span>
  </div>
  <svg class="w-5 h-5 text-gray-400"><!-- chevron-right --></svg>
</div>
```

### Bottom Sheet

- Overlay: black, 50% opacity
- Sheet: white, `rounded-t-xl` (24px), `shadow-xl`
- Handle bar: 32x4px, `gray-300`, centred, `rounded-full`
- Slide up 350ms, spring easing
- Dismiss: swipe down or tap overlay

---

## 24. Push Notifications

| Event | Title | Body |
|---|---|---|
| Booking confirmed | "Pickup Confirmed ✓" | "Your pickup for {date} confirmed. Ref: {ref}" |
| Driver assigned | "Driver On The Way" | "Driver headed to {address}. ETA: {time}" |
| Pickup completed | "You Earned ₦{amount}!" | "{weight}kg of {type} collected." |
| Rate change | "New Buy Rates" | "Plastics: ₦{rate}/kg. Sell today!" |
| Reminder | "Pickup Tomorrow" | "We're coming to {address} at {time}." |

### Delivery

```ruby
{
  title: "You Earned ₦4,375!",
  body: "12.5kg of Plastics collected.",
  data: { url: "/bookings/#{booking.id}", type: "booking_completed" }
}
```

Turbo Native opens the deep-link URL when notification is tapped.

---

## 25. Native Bridge & Platform Features

| Feature | Implementation |
|---|---|
| Push token | Native registers FCM/APNs, posts to `POST /api/devices` |
| Camera (future) | Standard `<input type="file" accept="image/*">` |
| Location (future) | Native GPS, bridge sends coords to web view |
| Share | JS bridge: `window.NativeBridge.share(url, title)` |
| Biometrics (future) | Native Face ID / fingerprint, keychain session token |
| App version | User-Agent: `Turbo Native iOS/1.0.0` |

---

## 26. App Store Presence

### Names

- App name: **Genius Eco Visionaries**
- Subtitle: "Turn Your Waste Into Cash"

### Description

```
Book. Weigh. Get Paid.

Schedule a free pickup and we'll come to you — weigh your plastics
or aluminium cans, and pay you at the current market rate.

✓ Free pickup — we come to your location
✓ Get paid for plastics and aluminium cans
✓ Track bookings and earnings
✓ Live market rates updated daily
✓ Serving Edo South, expanding across Edo State

Small changes, big impact.
```

### Keywords (iOS)

`recycling, waste, sell recyclables, plastics, aluminium, cans, pickup, Edo, Nigeria, earn money, scrap, green`

### Category

Primary: Lifestyle. Secondary: Business.

### Screenshots (5)

1. Home with earnings + rates
2. Booking form
3. Confirmation with ref
4. Earnings history
5. Booking detail with timeline

### App Icon

Logo on `gray-900` bg, 18% padding, 1024x1024. OS handles rounding.

---

## 27. Voice & Tone

### Public Website

- Lead with benefit: "Turn your waste into cash"
- Emphasise free: "Schedule a free pickup"
- Direct value prop: "We pay you ₦350/kg"
- Warm, community-first, eco-conscious

### Mobile App

- Ultra-concise: "Book Pickup" not "Schedule a Free Pickup"
- Celebration on earnings: "You earned ₦4,375!"
- Reassuring: "We'll confirm via WhatsApp within 30 minutes"
- Friendly notifications: "You earned ₦4,375!" not "Payment processed"

### Admin Dashboard

- Concise, action-oriented: "Assign Driver"
- Data-driven: always show numbers
- No exclamation marks
- Error messages explain what to do

### Common Copy

| Context | Copy |
|---|---|
| Empty bookings | "No bookings yet. New pickups will appear here." |
| Empty earnings | "No earnings yet. Book your first pickup to start earning." |
| Toast (mobile) | "Pickup booked! Ref: GEV-20260215-003" |
| Hero CTA | "Schedule Free Pickup →" |
| App onboarding | "Book. Weigh. Get Paid." |
| Rate notification | "New rates! Plastics: ₦350/kg" |

---

## 28. Accessibility

### Contrast

| Pair | Ratio | Result |
|---|---|---|
| gray-800 on white | 12.6:1 | ✅ AAA |
| gray-500 on white | 5.1:1 | ✅ AA |
| white on blue-500 | 4.6:1 | ✅ AA |
| white on green-400 | 3.2:1 | ⚠️ Large only |
| white on gray-900 | 18.1:1 | ✅ AAA |

### Touch Targets (Mobile)

- Minimum: **48x48px** (Apple HIG / Material Design)
- Tab bar icons: 48px area
- List rows: min 48px height
- Buttons: min 48px on mobile
- Inputs: min 48px height
- Gap between tappable elements: min 8px

### General

- All images: `alt` text
- Inputs: associated `<label>`
- Buttons: descriptive text or `aria-label`
- Badges: text + colour (not colour alone)
- Mobile screens: set `<title>` for VoiceOver/TalkBack
- Support Dynamic Type / font scaling
- Respect `prefers-reduced-motion`

---

## 29. Currency & Number Formatting

| Type | Format | Font | Example |
|---|---|---|---|
| Currency | `₦{amount}` no space, comma thousands | `font-mono` | ₦4,375 |
| Weight | `{n} kg` one decimal, space before unit | `font-mono` | 12.5 kg |
| Rate | `₦{n}/kg` no space around slash | `font-mono` | ₦350/kg |
| Booking ref | `GEV-YYYYMMDD-NNN` | `font-mono` | GEV-20260215-003 |
| Phone (display) | `0803 620 5243` | `font-body` | — |
| Phone (storage) | `+2348036205243` (E.164) | — | — |
| Date | `15 Feb 2026` | `font-body` | — |
| Time | `2:30 PM` | `font-body` | — |
| Relative (mobile) | "2 min ago", "Yesterday" | `font-body` | — |

---

## 30. Icon System

Lucide Icons (`lucide-rails` gem or CDN).

| Context | Icon | Size |
|---|---|---|
| Home tab | `home` | 24px |
| Bookings tab | `clipboard-list` | 24px |
| Book tab | `plus-circle` | 28px |
| Earnings tab | `banknote` | 24px |
| Profile tab | `user` | 24px |
| WhatsApp | `message-circle` | 20px |
| Phone | `phone` | 20px |
| Calendar | `calendar` | 20px |
| Weight | `scale` | 20px |
| Location | `map-pin` | 20px |
| Truck | `truck` | 20px |
| Edit | `pencil` | 18px |
| Delete | `trash-2` | 18px |
| View | `eye` | 18px |
| Back | `chevron-left` | 24px |
| Forward | `chevron-right` | 20px |
| Close | `x` | 24px |
| Search | `search` | 20px |
| Settings | `settings` | 20px |
| Bell | `bell` | 20px |
| Filter | `sliders-horizontal` | 20px |
| Share | `share-2` | 20px |
| Refresh | `refresh-cw` | 20px |
| Check | `check-circle` | 16-20px |
| Warning | `alert-triangle` | 16-20px |
| Error | `x-circle` | 16-20px |
| Info | `info` | 16-20px |

Stroke width: 2 (inline/buttons), 1.5 (cards/tabs/features).

---

## 31. Responsive Breakpoints

| Name | Width | Usage |
|---|---|---|
| default | 0px | Mobile app, mobile web |
| sm | 640px | Mobile landscape |
| md | 768px | Tablets |
| lg | 1024px | Laptops, admin sidebar |
| xl | 1280px | Desktop |

### Platform Behaviour

| Range | Public Site | Admin | Mobile App |
|---|---|---|---|
| <640px | 1 col, hamburger | Stacked | Full Turbo Native |
| 640-767px | 1 col | Stacked | — |
| 768-1023px | 2 col | Collapsible sidebar | — |
| 1024+ | Full layout | Fixed sidebar | — |

Mobile app always renders at phone width. Use `turbo-native` class to hide web elements (header, footer, cookie banner). No hover states — `active:` only. Fixed CTAs need `safe-area-bottom`.

---

## 32. Tailwind CSS Configuration

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
          50: "#E8F4F8", 100: "#C5E4EE", 200: "#8DC9DD",
          300: "#55AECC", 400: "#35A4C8", 500: "#28A0C8",
          600: "#2290B5", 700: "#1B7A99", 800: "#15647D",
          900: "#0E4457",
        },
        green: {
          50: "#F0F7E6", 100: "#D9EDBE", 200: "#BCE293",
          300: "#A0D768", 400: "#8CC83C", 500: "#7DB835",
          600: "#6FA52F", 700: "#5C8D27", 800: "#49751F",
          900: "#365413",
        },
        gray: {
          50: "#F7FAFA", 100: "#EEF2F3", 200: "#DCE1E3",
          300: "#B8C0C4", 400: "#8B969C", 500: "#657078",
          600: "#4A545B", 700: "#353D42", 800: "#232A2E",
          900: "#141919",
        },
        success: { DEFAULT: "#2ECC71", light: "#E8F8F0" },
        warning: { DEFAULT: "#F39C12", light: "#FEF5E7" },
        error: { DEFAULT: "#E74C3C", light: "#FDEDEC" },
      },
      fontFamily: {
        display: ["Plus Jakarta Sans", ...defaultTheme.fontFamily.sans],
        body: ["DM Sans", ...defaultTheme.fontFamily.sans],
        mono: ["JetBrains Mono", ...defaultTheme.fontFamily.mono],
      },
      borderRadius: {
        sm: "6px", md: "10px", lg: "16px", xl: "24px",
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

## 33. CSS Custom Properties

```css
:root {
  --blue-50: #E8F4F8;  --blue-100: #C5E4EE;  --blue-200: #8DC9DD;
  --blue-300: #55AECC;  --blue-400: #35A4C8;  --blue-500: #28A0C8;
  --blue-600: #2290B5;  --blue-700: #1B7A99;  --blue-800: #15647D;
  --blue-900: #0E4457;

  --green-50: #F0F7E6;  --green-100: #D9EDBE;  --green-200: #BCE293;
  --green-300: #A0D768;  --green-400: #8CC83C;  --green-500: #7DB835;
  --green-600: #6FA52F;  --green-700: #5C8D27;  --green-800: #49751F;
  --green-900: #365413;

  --gray-50: #F7FAFA;  --gray-100: #EEF2F3;  --gray-200: #DCE1E3;
  --gray-300: #B8C0C4;  --gray-400: #8B969C;  --gray-500: #657078;
  --gray-600: #4A545B;  --gray-700: #353D42;  --gray-800: #232A2E;
  --gray-900: #141919;

  --success: #2ECC71;      --success-light: #E8F8F0;
  --warning: #F39C12;      --warning-light: #FEF5E7;
  --error: #E74C3C;        --error-light: #FDEDEC;

  --font-display: 'Plus Jakarta Sans', sans-serif;
  --font-body: 'DM Sans', sans-serif;
  --font-mono: 'JetBrains Mono', monospace;
  --ease: cubic-bezier(0.4, 0, 0.2, 1);
}
```

---

## 34. Google Fonts Import

### HTML head (recommended)

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&family=DM+Sans:ital,wght@0,400;0,500;0,600;0,700;1,400&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">
```

### Base Stylesheet

```css
@tailwind base;
@tailwind components;
@tailwind utilities;

@layer base {
  body { @apply font-body text-gray-800 antialiased; }
  h1, h2, h3, h4, h5, h6 { @apply font-display; }
}

/* Platform visibility */
.turbo-native .web-only { display: none !important; }
body:not(.turbo-native) .native-only { display: none !important; }

/* Safe areas */
.safe-area-top { padding-top: env(safe-area-inset-top, 0px); }
.safe-area-bottom { padding-bottom: env(safe-area-inset-bottom, 0px); }
```

---

*End of GEV Design System v3.0*
*Reference this document when implementing any UI component across web, mobile app, or admin dashboard for the Genius Eco Visionaries platform.*