# Master Frontend Blueprint & Prompt Template: Enterprise Admin Panel UI/UX

> **How to use this document:**
> - **As an AI Generation Prompt:** Copy and paste the prompt in **Section 1** into any advanced AI model (Antigravity, Claude, ChatGPT, v0) to generate this complete, professional admin panel frontend from scratch.
> - **As a Frontend Architectural Specification:** Use **Sections 2 through 8** as your comprehensive design system, component catalog, UI/UX specification, and layout guide whenever building modern dashboard applications.
> - **Scope:** 100% Frontend (UI, UX, styling, design tokens, layout hierarchy, interactive flow canvas, components, data tables, modals, charts, and client-side mocks). Zero backend code or database logic included.

---

## Section 1: The Master AI Generation Prompt

*Copy everything in the box below to prompt an AI model to generate this complete admin panel frontend.*

```markdown
You are an expert Principal Frontend Engineer and Design System Architect.

Your objective is to build a modern, high-density, enterprise-grade Admin Panel & Tournament/Platform Operations Dashboard in React (TypeScript) and Tailwind CSS.

### 1. Visual Aesthetics & Design System
- **Theme:** Default to a "Carbon Obsidian Minimalist" Dark Theme with seamless Light Mode toggle.
  - Dark Mode: Pure deep obsidian background (`#0a0a0a`), carbon cards (`#161616`), 1px precision borders (`#2a2a2a`), royal sapphire blue primary accents (`#2563eb`), crisp platinum typography (`#fafafa`), and neutral muted text (`#a3a3a3`).
  - Light Mode: Clean crisp white background (`#ffffff`), subtle off-white cards (`#ffffff`), light grey borders (`#e5e7eb`), dark slate text (`#0f172a`).
- **Typography:** Inter / SF Pro font family with balanced letter-spacing, tabular numbers for monetary/metric figures (`tabular-nums`), and clean hierarchy.
- **Scrollbars & Polish:** Minimalist 6px translucent scrollbars, fluid micro-interactions, smooth hover transitions (150ms-200ms), and zero layout shift.

### 2. Core Layout Architecture
- **Viewport Layout:** Full viewport height (`h-screen overflow-hidden`) with a flexible shell.
- **Collapsible Sidebar:**
  - Expanded width: 240px (`w-60`). Collapsed width: 56px (`w-14`).
  - Categorized navigation groups with muted uppercase labels:
    - `PLATFORM`: Dashboard, Notifications
    - `MARKETING`: Home Banners
    - `MANAGEMENT`: Games, Quick Contests, Tournaments & Canvas Builder, Leaderboards, Users, KYC Approvals
    - `FINANCE`: Transactions, Withdrawals, Bank & IFSC Master, TDS
    - `SUPPORT`: Support Tickets, FAQ
    - `SYSTEM`: Settings, Policies, Admin Team & RBAC
    - `OBSERVABILITY`: Audit Logs, Error Tracker, User Analytics, Worker Health
  - Active nav item pill with sapphire accent and subtle glow.
  - Mobile responsive drawer with dark backdrop overlay for `<1024px` screens.
- **Topbar:**
  - Sidebar collapse/expand toggle button.
  - Dynamic hierarchical Breadcrumbs with path auto-truncation for narrow viewports.
  - Right-aligned Action Bar slot for contextual page buttons (e.g., "Export PDF", "Refresh", "Create Contest").
  - Desktop-integrated Notification Center bell with red unread count badge and flyout popover.
  - Dark/Light mode toggle switch.
  - User profile menu button with avatar and role badge.
- **Page Canvas:**
  - Standard routes: Scrollable container with padding (`px-4 py-4 sm:px-6`).
  - Canvas routes (e.g., Tournament Node Builder): Full-bleed viewport container (`p-0 overflow-hidden`).

### 3. Key Complex UI Components to Build
1. **Interactive Node-Based Tournament Flow Canvas (`@xyflow/react`):**
   - Infinite pan-and-zoom node graph canvas with minimap and controls toolbar.
   - Custom node types:
     - `StageNode`: Stage banner, format tag (Battle Royale, Single Elim), stage status badge, qualified team counter, action menu.
     - `GroupNode`: Group header, lobby assignment slot, match schedule count.
     - `MatchNode`: Team vs Team pairing cards with score slots, live status indicators, and match start time.
     - `WinnerNode`: Podium trophy visual, reward prize tag, champion team display.
   - Slide-over Inspector Drawer for live node configuration.
   - Interactive modals for: Lobby assignments, manual match score overrides, and spectator preview.
2. **High-Density Data Tables (`@tanstack/react-table`):**
   - Search filter bar, multi-select filters, sortable column headers.
   - Status badge pills (Success/Emerald, Warning/Amber, Danger/Rose, Info/Sky).
   - Sticky action columns with three-dot dropdown menus.
   - Export buttons (CSV download and formatted PDF generator).
   - Pagination controls with items-per-page selector and total count display.
3. **Executive KPI Dashboard:**
   - Stat Cards featuring: Main metric value, 24h/30d trend indicator (+12.4% with green up-arrow), sparkline icon background, and tooltip subtext.
   - Time-series Area Charts and Comparative Bar Charts (`recharts`).
   - Live Activity Timeline feed with user avatars and timestamp chips.
   - System Health status grid showing green pulsing indicators for services/workers.
4. **Rich Content & Rules Editor:**
   - Dual-pane layout: Rich text / Markdown editor on left, real-time live preview prose renderer on right.
5. **Modals & Drawers System:**
   - Accessible Radix Dialogs with backdrop blur (`backdrop-blur-sm`).
   - KYC verification inspector with side-by-side ID card photo zoom, masked PII display, and Approve/Reject buttons with reason selector.

### 4. Technical Constraints
- Pure Frontend only: Do NOT connect to external live databases or backend routes.
- Use mock datasets and Zustand / React state hooks to make the UI completely interactive, functional, and self-contained.
- Build clean, reusable component primitives in `src/components/ui/` following Shadcn/Radix conventions.
```

---

## Section 2: Frontend Tech Stack & Library Specifications

Below is the verified dependency roster for building this high-performance admin interface.

### Core Framework & Build Tooling
| Library | Version | Purpose |
| :--- | :--- | :--- |
| **React** | `^19.0.0` | Core UI engine |
| **Vite** | `^6.0.0` | Ultra-fast HMR and bundle compilation |
| **TypeScript** | `^5.5.0` | Strict type safety across all props and mock schemas |
| **React Router** | `^7.0.0` or `^6.28.0` | Client-side routing with nested layouts and active navigation |

### Styling & Design System
| Library | Version | Purpose |
| :--- | :--- | :--- |
| **Tailwind CSS** | `^4.0.0` | Modern CSS-variable-driven utility engine (`@theme`) |
| **Lucide React** | `^0.500.0` | Consistent, lightweight SVG icon system |
| **clsx** & **tailwind-merge** | Latest | Dynamic class concatenation without Tailwind specificity conflicts |
| **class-variance-authority (CVA)** | `^0.7.0` | Strongly typed UI component variants (buttons, badges) |

### UI Primitives (Radix UI)
| Library | Version | Purpose |
| :--- | :--- | :--- |
| `@radix-ui/react-dialog` | `^1.1.0` | Accessible modals, confirmation dialogs, and slide-over sheets |
| `@radix-ui/react-popover` | `^1.1.0` | Floating menus, notification drawers, date pickers |
| `@radix-ui/react-select` | `^2.1.0` | Custom-styled accessible select dropdowns |
| `@radix-ui/react-progress` | `^1.1.0` | Visual progress bars (capacity meters, KYC steps) |
| `@radix-ui/react-slot` | `^1.1.0` | Polymorphic component rendering (`asChild` pattern) |

### Advanced Interactive Features
| Library | Version | Purpose |
| :--- | :--- | :--- |
| **`@xyflow/react` (React Flow)** | `^12.11.0` | Interactive canvas for stage nodes, bracket builders, and match flows |
| **`@tanstack/react-table`** | `^8.20.0` | Headless, virtualized, sortable, filterable enterprise data grids |
| **`recharts`** | `^2.15.0` | Declarative SVG charting (Area, Bar, Pie, Sparklines) |
| **`sonner`** | `^2.0.0` | Rich, animated toast notifications with action buttons |
| **`@tiptap/react`** / **Quill** | Latest | WYSIWYG rich text authoring for announcements and rules |
| **`@uiw/react-md-editor`** | Latest | Markdown authoring with live split-screen preview |
| **`jspdf`** & **`jspdf-autotable`** | Latest | Client-side automated PDF report generation |
| **`xlsx`** | Latest | Client-side Excel/CSV spreadsheet export |
| **`date-fns`** | `^3.4.0` | Lightweight UTC and local date formatting |

---

## Section 3: Design System Tokens & Global Styling

Save this configuration into `src/styles/global.css`. It provides the exact **Carbon Obsidian Minimalist** color palette with full light/dark mode support.

```css
@import "tailwindcss";

@theme {
  --color-background: hsl(var(--background));
  --color-foreground: hsl(var(--foreground));
  --color-card: hsl(var(--card));
  --color-card-foreground: hsl(var(--card-foreground));
  --color-popover: hsl(var(--popover));
  --color-popover-foreground: hsl(var(--popover-foreground));
  --color-primary: hsl(var(--primary));
  --color-primary-foreground: hsl(var(--primary-foreground));
  --color-secondary: hsl(var(--secondary));
  --color-secondary-foreground: hsl(var(--secondary-foreground));
  --color-muted: hsl(var(--muted));
  --color-muted-foreground: hsl(var(--muted-foreground));
  --color-accent: hsl(var(--accent));
  --color-accent-foreground: hsl(var(--accent-foreground));
  --color-destructive: hsl(var(--destructive));
  --color-destructive-foreground: hsl(var(--destructive-foreground));
  --color-border: hsl(var(--border));
  --color-input: hsl(var(--input));
  --color-ring: hsl(var(--ring));

  --color-success: hsl(var(--success));
  --color-success-foreground: hsl(var(--success-foreground));
  --color-warning: hsl(var(--warning));
  --color-warning-foreground: hsl(var(--warning-foreground));
  --color-danger: hsl(var(--danger));
  --color-danger-foreground: hsl(var(--danger-foreground));
  --color-info: hsl(var(--info));
  --color-info-foreground: hsl(var(--info-foreground));

  --radius: 0.5rem;
}

@layer base {
  /* LIGHT MODE TOKENS */
  :root {
    color-scheme: light;
    --background: 0 0% 100%;
    --foreground: 0 0% 3.9%;
    --card: 0 0% 100%;
    --card-foreground: 0 0% 3.9%;
    --popover: 0 0% 100%;
    --popover-foreground: 0 0% 3.9%;
    --primary: 221.2 83.2% 53.3%;
    --primary-foreground: 0 0% 98%;
    --secondary: 0 0% 96.1%;
    --secondary-foreground: 0 0% 9%;
    --muted: 0 0% 96.1%;
    --muted-foreground: 0 0% 45.1%;
    --accent: 0 0% 96.1%;
    --accent-foreground: 0 0% 9%;
    --destructive: 0 84.2% 60.2%;
    --destructive-foreground: 0 0% 98%;
    --danger: 0 84.2% 60.2%;
    --danger-foreground: 0 0% 98%;
    --success: 142.1 76.2% 36.3%;
    --success-foreground: 0 0% 98%;
    --warning: 37.7 92.1% 50.2%;
    --warning-foreground: 0 0% 98%;
    --info: 217.2 91.2% 59.8%;
    --info-foreground: 0 0% 98%;
    --border: 0 0% 89.8%;
    --input: 0 0% 89.8%;
    --ring: 221.2 83.2% 53.3%;
  }

  /* CARBON OBSIDIAN DARK THEME (Signature Palette) */
  .dark {
    color-scheme: dark;
    --background: 0 0% 4%;            /* Deep Obsidian #0a0a0a */
    --foreground: 0 0% 98%;           /* Platinum Crisp #fafafa */
    --card: 0 0% 8.5%;               /* Carbon Card Surface #161616 */
    --card-foreground: 0 0% 98%;
    --popover: 0 0% 8.5%;
    --popover-foreground: 0 0% 98%;
    --primary: 221.2 83.2% 53.3%;     /* Royal Sapphire Blue #2563eb */
    --primary-foreground: 0 0% 100%;
    --secondary: 0 0% 13.5%;         /* Dark Secondary Surface #222222 */
    --secondary-foreground: 0 0% 98%;
    --muted: 0 0% 13.5%;
    --muted-foreground: 0 0% 63.9%;   /* Clean Secondary Text #a3a3a3 */
    --accent: 0 0% 13.5%;
    --accent-foreground: 0 0% 98%;
    --destructive: 0 84.2% 60.2%;
    --destructive-foreground: 0 0% 100%;
    --danger: 0 84.2% 60.2%;
    --danger-foreground: 0 0% 100%;
    --success: 142.1 70.6% 45.3%;     /* Emerald */
    --success-foreground: 0 0% 100%;
    --warning: 37.7 92.1% 50.2%;      /* Warm Amber */
    --warning-foreground: 0 0% 100%;
    --info: 217.2 91.2% 59.8%;        /* Sky Blue */
    --info-foreground: 0 0% 100%;
    --border: 0 0% 16.5%;            /* Precision 1px Border #2a2a2a */
    --input: 0 0% 16.5%;
    --ring: 221.2 83.2% 53.3%;
  }

  * {
    @apply border-border outline-ring/50;
    -webkit-tap-highlight-color: transparent;
  }

  body {
    @apply bg-background text-foreground antialiased;
    font-feature-settings: "cv02", "cv03", "cv04", "cv11";
  }

  /* Sleek 6px Translucent Custom Scrollbar */
  ::-webkit-scrollbar {
    width: 6px;
    height: 6px;
  }
  ::-webkit-scrollbar-track {
    background: transparent;
  }
  ::-webkit-scrollbar-thumb {
    background: rgba(156, 163, 175, 0.2);
    border-radius: 9999px;
  }
  ::-webkit-scrollbar-thumb:hover {
    background: rgba(156, 163, 175, 0.4);
  }
}
```

---

## Section 4: Shell Layout Architecture & Navigation System

### 1. Viewport Split Layout (`AdminLayout.tsx`)
```tsx
import { useState, useEffect } from "react";
import { Outlet, useLocation } from "react-router-dom";
import { AdminSidebar } from "./AdminSidebar";
import { AdminTopbar } from "./AdminTopbar";

export function AdminLayout() {
  const location = useLocation();
  const [collapsed, setCollapsed] = useState(() => {
    return localStorage.getItem("sidebar_collapsed") === "true";
  });
  const [mobileOpen, setMobileOpen] = useState(false);

  useEffect(() => {
    localStorage.setItem("sidebar_collapsed", String(collapsed));
  }, [collapsed]);

  // Auto-close mobile drawer on navigation
  useEffect(() => {
    setMobileOpen(false);
  }, [location.pathname]);

  const isFullScreenRoute = location.pathname.includes("/builder");

  return (
    <div className="flex h-screen bg-background text-foreground overflow-hidden">
      {/* Mobile Backdrop */}
      {mobileOpen && (
        <div
          className="fixed inset-0 bg-black/60 backdrop-blur-xs z-40 lg:hidden"
          onClick={() => setMobileOpen(false)}
        />
      )}

      {/* Sidebar */}
      <AdminSidebar
        collapsed={collapsed}
        mobileOpen={mobileOpen}
        onCloseMobile={() => setMobileOpen(false)}
      />

      {/* Main Viewport Container */}
      <div className="flex flex-col flex-1 min-w-0">
        <AdminTopbar
          toggleSidebar={() => {
            if (window.innerWidth < 1024) setMobileOpen((prev) => !prev);
            else setCollapsed((prev) => !prev);
          }}
        />

        <main
          className={`flex-1 h-full overflow-hidden flex flex-col ${
            isFullScreenRoute ? "p-0" : "px-4 py-4 sm:px-6 overflow-y-auto"
          }`}
        >
          <Outlet />
        </main>
      </div>
    </div>
  );
}
```

### 2. Collapsible Navigation Sidebar (`AdminSidebar.tsx`)
Key UX Specifications:
- **Collapsed Width:** `w-14` (56px) showing only centered Lucide icons with native HTML or Radix tooltips.
- **Expanded Width:** `w-60` (240px) showing category headers, icon, text labels, and count badges.
- **Group Structure:**
  - `PLATFORM`: Dashboard (`LayoutDashboard`), Notifications (`Bell`)
  - `MARKETING`: Home Banners (`Image`)
  - `MANAGEMENT`: Games (`Gamepad2`), Quick Contests (`Trophy`), Tournaments & Canvas Builder (`Layers`), Leaderboards (`Medal`), Test Simulator (`FlaskConical`), Users (`Users`), Pending KYC (`ShieldAlert`)
  - `FINANCE`: Transactions (`CreditCard`), Withdrawals (`Banknote`), Bank & IFSC Master (`Landmark`), TDS Reports (`FileText`)
  - `SUPPORT`: Tickets (`MessageSquare`), FAQ (`HelpCircle`)
  - `SYSTEM`: Settings (`Settings`), Policies (`ScrollText`), Admin Users & RBAC (`ShieldAlert`)
  - `OBSERVABILITY`: Audit Logs (`Shield`), Error Tracker (`Bug`), User Events (`BarChart3`), Worker Health (`Cpu`)
- **Active State:** `bg-primary/10 text-primary font-semibold border-r-2 border-primary`

### 3. Topbar with Dynamic Breadcrumbs & Actions (`AdminTopbar.tsx`)
- **Left Side:** Sidebar collapse button (`PanelLeft` icon) + Breadcrumbs trail (`Dashboard > Tournaments > Spring Invitational`). Long text must truncate cleanly (`truncate max-w-[200px]`).
- **Center/Right Action Slot:** Injected buttons from active route (e.g. `Export PDF`, `Save Draft`, `Refresh Data`).
- **Utility Items:**
  - **Notification Center:** Flyout dropdown showing unread count, tabbed categories, "Mark all as read", and instant clear.
  - **Theme Toggle:** Sun/Moon icon toggle with instant CSS class `.dark` toggle on `<html>`.
  - **Admin Avatar:** Circular avatar with online badge and dropdown for Profile / Sign Out.

---

## Section 5: Standard UI Primitives & Design System

Every admin screen relies on these consistent, accessible Radix-powered components.

### 1. Button Component (`button.tsx`)
```tsx
import { cva, type VariantProps } from "class-variance-authority";
import { Slot } from "@radix-ui/react-slot";
import { Loader2 } from "lucide-react";

export const buttonVariants = cva(
  "inline-flex items-center justify-center gap-2 rounded-md text-sm font-medium transition-colors focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-ring disabled:pointer-events-none disabled:opacity-50 cursor-pointer",
  {
    variants: {
      variant: {
        default: "bg-primary text-primary-foreground shadow-xs hover:bg-primary/90",
        destructive: "bg-destructive text-destructive-foreground hover:bg-destructive/90",
        outline: "border border-border bg-background hover:bg-accent hover:text-accent-foreground",
        secondary: "bg-secondary text-secondary-foreground hover:bg-secondary/80",
        ghost: "hover:bg-accent hover:text-accent-foreground",
        link: "text-primary underline-offset-4 hover:underline",
      },
      size: {
        default: "h-9 px-4 py-2",
        sm: "h-8 rounded-md px-3 text-xs",
        lg: "h-10 rounded-md px-8",
        icon: "h-9 w-9",
      },
    },
    defaultVariants: {
      variant: "default",
      size: "default",
    },
  }
);
```

### 2. High-Density KPI Stat Card (`DashboardStatCard.tsx`)
- Displays an icon in a rounded tinted container: `bg-primary/10 text-primary`.
- Prominent metric value (e.g., `₹4,28,950` or `12,840`).
- Percentage change badge:
  - Positive: `text-emerald-500 bg-emerald-500/10` with `TrendingUp` icon.
  - Negative: `text-rose-500 bg-rose-500/10` with `TrendingDown` icon.
- Muted description subtext.

### 3. Enterprise Data Grid (`DataTable.tsx`)
Features to always implement on tables:
- **Global Search Input:** Instant debounced filter across name, ID, phone, or title.
- **Column Header Sorting:** Clickable header with `ArrowUpDown` icon.
- **Status Pills:** Standardized badges:
  - Active / Completed: `bg-emerald-500/10 text-emerald-500 border border-emerald-500/20`
  - Pending / In Review: `bg-amber-500/10 text-amber-500 border border-amber-500/20`
  - Rejected / Failed: `bg-rose-500/10 text-rose-500 border border-rose-500/20`
  - Draft / Neutral: `bg-muted text-muted-foreground border border-border`
- **Pagination Bar:** Shows `Showing 1 to 20 of 142 results`, Rows per page dropdown (`10, 20, 50, 100`), and Previous/Next buttons.

---

## Section 6: Specialized Complex Domain Interfaces

### 1. Interactive Node-Based Tournament Builder (`@xyflow/react`)
This is the flagship visual feature for esports / tournament management.

```
+------------------------------------------------------------------------+
| [Toolbar] Zoom In | Zoom Out | Auto-Layout | Add Stage | Auto-Assign   |
+------------------------------------------------------------------------+
|                                                                        |
|  [StageNode: Qualifier]        [StageNode: Semifinals]   [WinnerNode]  |
|  +--------------------+        +---------------------+   +-----------+ |
|  | Group A (16 Teams) | =====> | Group 1 (8 Teams)   | =>| CHAMPION  | |
|  | Group B (16 Teams) |   |    | Group 2 (8 Teams)   |   | ₹1,00,000 | |
|  +--------------------+   |    +---------------------+   +-----------+ |
|                           |                                            |
|  (Interactive Handles) ---+ (Custom Bezier Edges with Animated Flow)   |
|                                                                        |
+------------------------------------------------------------------------+
| [Minimap (Bottom-Right)]             [Slide-Over Node Inspector Panel] |
+------------------------------------------------------------------------+
```

#### Node Types Specification:
1. **`StageNode.tsx`**:
   - Header with custom stage order badge (`Stage 1`), Stage Name (`Qualifier`), and format tag (`Battle Royale` or `Single Elimination`).
   - Progress bar showing registered vs maximum capacity (`120 / 128 Teams`).
   - Status badge (`Draft`, `Open`, `In Progress`, `Completed`).
   - Source and Target connection handles for linking to subsequent stages.
2. **`MatchNode.tsx`**:
   - Two participant slots with team logos, seeds, score inputs, and winner checkmark.
   - Match time and room ID pill.
3. **`WinnerNode.tsx`**:
   - Gold/amber gradient border with trophy icon.
   - Displays 1st, 2nd, and 3rd place podium spots with associated cash/coin rewards.
4. **`CustomEdge.tsx`**:
   - Smooth curved SVG bezier edge with arrow marker.
   - Dynamic animated dashed stroke when a stage is active.
5. **Node Inspector Panel (`InspectorPanel.tsx`)**:
   - Slide-over drawer when a user clicks any node.
   - Form controls to modify Stage Name, Game Map, Match Type, Max Slots, Entry Fee, and Qualification Rule (e.g., "Top 4 advance to next stage").

### 2. Elimination Bracket Canvas
- Columns representing tournament rounds (`Round of 32`, `Sweet 16`, `Quarterfinals`, `Semifinals`, `Grand Finals`).
- Connecting orthogonal bracket connectors.
- Match score override drawer allowing admin to force-advance a team in case of technical issues.

### 3. Dual-Pane Content & Rules Live Preview (`RulesLivePreview.tsx`)
- Left Pane: Tabbed rich text editor or raw Markdown input.
- Right Pane: Clean prose renderer showing real-time formatted typography with headers, ordered lists, warning callouts, and prize tables.

---

## Section 7: UI/UX Guidelines & Component States

To guarantee a 10/10 experience, every screen must implement all 4 foundational states:

1. **Loading State:**
   - Never show a blank screen.
   - Use layout-shaped `Skeleton` cards and table row skeletons (`h-12 w-full animate-pulse`).
2. **Empty State:**
   - Display a clean centered container with a muted icon (e.g., `Inbox` or `Trophy`), a descriptive heading (e.g., `No Contests Found`), an explanatory sentence, and a primary CTA button (e.g., `Create First Contest`).
3. **Error State:**
   - Bounded error card with `AlertTriangle` icon, friendly error message, and a `Retry` button.
4. **Action Confirmation (Destructive UX):**
   - High-risk actions (e.g., rejecting KYC, banning a user, cancelling a contest, approving large withdrawal) must open a confirmation dialog requiring an explicit reason selector or confirmation typed input.

---

## Section 8: Standalone Mock Architecture (Zero-Backend Operation)

To develop or preview this frontend completely independently without running any backend API, organize mock state using Zustand stores:

### Example: Mock Notification Store (`notificationStore.ts`)
```ts
import { create } from "zustand";

export interface AdminNotification {
  id: string;
  title: string;
  message: string;
  type: "kyc" | "withdrawal" | "contest" | "system";
  timestamp: string;
  read: boolean;
}

interface NotificationState {
  notifications: AdminNotification[];
  markAsRead: (id: string) => void;
  markAllAsRead: () => void;
  clearAll: () => void;
}

export const useNotificationStore = create<NotificationState>((set) => ({
  notifications: [
    {
      id: "n-1",
      title: "New High-Value Withdrawal",
      message: "User rahul_pro requested ₹25,000 withdrawal via IMPS.",
      type: "withdrawal",
      timestamp: "5m ago",
      read: false,
    },
    {
      id: "n-2",
      title: "KYC Approval Pending",
      message: "Aadhaar verification submitted for amit_99.",
      type: "kyc",
      timestamp: "18m ago",
      read: false,
    },
  ],
  markAsRead: (id) =>
    set((state) => ({
      notifications: state.notifications.map((n) =>
        n.id === id ? { ...n, read: true } : n
      ),
    })),
  markAllAsRead: () =>
    set((state) => ({
      notifications: state.notifications.map((n) => ({ ...n, read: true })),
    })),
  clearAll: () => set({ notifications: [] }),
}));
```

---

## Summary Checklist for Generating a New Admin Panel

- [ ] Initialize with **Vite + React 19 + TypeScript**.
- [ ] Configure **Tailwind CSS v4** with Carbon Obsidian Dark Theme tokens in `global.css`.
- [ ] Create `AdminLayout` with collapsible sidebar (`w-60` / `w-14`), responsive mobile drawer, and dynamic breadcrumbs topbar.
- [ ] Build core UI primitives in `src/components/ui/` (`Button`, `Input`, `Dialog`, `Select`, `Table`, `Badge`, `Card`, `Skeleton`).
- [ ] Implement `@tanstack/react-table` for sortable, searchable, paginated data grids.
- [ ] Implement `recharts` for executive metric analytics.
- [ ] Implement `@xyflow/react` for interactive stage/match node graphs.
- [ ] Add `sonner` for animated toast feedback.
- [ ] Wire all views to mock data stores so the application runs 100% standalone out of the box.
