# IPS Design System — Complete Reference

**Source:** `@ips/design-system` — import everything from this package.
**Storybook:** `http://localhost:6007` (when running locally)
**Tokens source:** `src/styles/tokens.scss`
**Text styles source:** `src/components/text_styles/text_styles.stories.tsx`

> **Rule: use only what is in this file.** Do not invent colours, font sizes, icon names, or component props not listed here. If something is not listed, it does not exist in the system.

---

## 1 — Screens

Every screen is pre-built. When the user uploads a screenshot or names a screen, match it to the table below **first**. Read the story source and adapt it — do not rebuild from scratch.

| Screen | Story file | Variants |
|---|---|---|
| **Workflow** | `src/screens/workflow/workflow.stories.tsx` | `Engagements`, `Roles` |
| **Role** | `src/screens/role/role.stories.tsx` | `Overview`, `Matches`, `Vacancies`, `History`, `Shortlist` |
| **Engagement** | `src/screens/engagement/engagement.stories.tsx` | `Default` |
| **Booking Engine** | `src/screens/booking_engine/booking_engine.stories.tsx` | `ProjectsEngagementsGantt`, `ProjectsRolesGantt`, `ProjectsEngagementsGrid`, `ProjectsRolesGrid`, `WorkforceBookings`, `WorkforceGrid` |
| **Analytics** | `src/screens/analytics/analytics.stories.tsx` | `Reports`, `CreateDetails`, `CreateFields`, `CreateFilters`, `CreateGenerate` |
| **Audit Planner** | `src/screens/audit_planner/audit_planner.stories.tsx` | `Default` |
| **Marketplace** | `src/screens/marketplace/marketplace.stories.tsx` | `Home`, `WorkOpportunities` |
| **My Profile** | `src/screens/my_profile/my_profile.stories.tsx` | `Default`, `Narrow` |
| **Profiles Directory** | `src/screens/profiles_directory/profiles_directory.stories.tsx` | `Cards`, `TableView`, `SearchingCards`, `SearchingTable` |
| **Admin — Skills** | `src/screens/admin/admin.stories.tsx` | `SkillsFrameworks` |
| **Admin — Manage Roles** | `src/screens/admin/manage_roles.stories.tsx` | `DTT`, `EngagementRoles` |

**How to adapt a screen story:**
1. Read the full story file
2. Copy the screen component function + all helpers + all data constants
3. Change `../../components/X` imports → `@ips/design-system`
4. Remove `import type { Meta, StoryObj }`, `export default meta`, `type Story = StoryObj`
5. Keep all screen component functions and data — wire into `App.tsx`

---

## 2 — Tokens

**These are the only permitted values. Do not use hardcoded hex colours or pixel sizes not in this list.**

### 2a — Colours

All available as CSS custom properties via `@ips/design-system/styles/components`.

#### Primary
| Token | Hex | Use |
|---|---|---|
| `--palette-primary-0` | `#2358F8` | Primary blue — buttons, links, active states |
| `--palette-primary-1` | `#1531B8` | Primary hover/dark |
| `--palette-primary-2` | `#4B75FF` | Primary light |
| `--palette-primary-3` | `#E7F9FE` | Row selected background |
| `--palette-primary-5` | `#436FB6` | Active badge background |
| `--palette-primary-action` | `#6EF29C` | Action green (shortlisting pill) |

#### Blue
| Token | Hex | Use |
|---|---|---|
| `--palette-blue-0` | `#0D2976` | Body text, headings — default text colour |
| `--palette-blue-1` | `#0C1457` | Navbar, dark backgrounds |
| `--palette-blue-2` | `#5C6E9E` | Secondary/muted text, inactive icons |
| `--palette-blue-3` | `#31A2CE` | Accent |

#### Neutral
| Token | Hex | Use |
|---|---|---|
| `--palette-neutral-0` | `#CFDAF7` | Borders, dividers |
| `--palette-neutral-1` | `#E7EAF8` | Selected backgrounds, inactive badges |
| `--palette-neutral-2` | `#F8F9FD` | Page background |
| `--palette-neutral-3` | `#8F9ED1` | Disabled text |

#### White / Black
| Token | Hex |
|---|---|
| `--palette-white-0` | `#FFFFFF` |
| `--palette-white-1` | `#F7F7F8` |
| `--palette-white-2` | `#ECECEC` |
| `--palette-white-3` | `#D5D5D5` |
| `--palette-black-0` | `#000000` |
| `--palette-black-1` | `#333333` |

#### Semantic
| Token | Hex | Use |
|---|---|---|
| `--palette-red-0` | `#D42A36` | Error, destructive actions |
| `--palette-red-1` | `#A30013` | Error dark |
| `--palette-red-2` | `#FFE2E2` | Error background |
| `--palette-red-3` | `#FF0000` | — |
| `--palette-green-0` | `#248E61` | Success, approved |
| `--palette-green-1` | `#1F6648` | Success dark |
| `--palette-green-2` | `#C8EEDE` | Success background |
| `--palette-orange-0` | `#FFCD38` | Warning |
| `--palette-orange-1` | `#9B5A01` | Warning text |
| `--palette-orange-2` | `#FFE8AD` | Warning background |
| `--palette-orange-3` | `#FF6B00` | — |
| `--palette-orange-4` | `#FFE606` | — |

#### Reserved (teal/slate)
| Token | Hex |
|---|---|
| `--palette-reserved-0` | `#1F363D` |
| `--palette-reserved-1` | `#5E7A83` |
| `--palette-reserved-2` | `#40798C` |
| `--palette-reserved-3` | `#70A9A1` |

#### Echarts (charts only)
| Token | Hex |
|---|---|
| `--palette-echarts-0` | `#5470C6` |
| `--palette-echarts-1` | `#91CC75` |
| `--palette-echarts-2` | `#FAC858` |
| `--palette-echarts-3` | `#EE6666` |
| `--palette-echarts-4` | `#73C0DE` |
| `--palette-echarts-5` | `#3BA272` |
| `--palette-echarts-6` | `#FC8452` |
| `--palette-echarts-7` | `#9A60B4` |

#### Transparency
| Token | Value |
|---|---|
| `--palette-trans-0` | `rgba(0,0,0,0.04)` — hover backgrounds |
| `--palette-trans-1` | `rgba(0,0,0,0.08)` |
| `--palette-trans-2` | `rgba(0,0,0,0.12)` |
| `--palette-trans-light-0` | `rgba(255,255,255,0.04)` |

---

### 2b — Text Styles

**Font family: `"Mulish"` — always. Never use system fonts.**

All text styles as CSS variables:

| Token | Value |
|---|---|
| `--font-family` | `"Mulish", sans-serif` |
| `--font-size-label-small` | `10px` |
| `--font-size-label` | `12px` |
| `--font-size-body` | `14px` |
| `--font-size-h6` | `15px` |
| `--font-size-h5` | `16px` |
| `--font-size-h4` | `20px` |
| `--font-size-h3` | `24px` |
| `--font-size-h2` | `28px` |
| `--font-size-h1` | `32px` |
| `--font-weight-regular` | `400` |
| `--font-weight-semibold` | `600` |
| `--font-weight-bold` | `700` |
| `--line-height-small` | `115%` |
| `--line-height-medium` | `125%` |
| `--line-height-big` | `150%` |

Named text styles (size / weight / line-height / use):

| Name | Size | Weight | LH | Use |
|---|---|---|---|---|
| `label-small-regular` | 10px | 400 | 115% | Chart labels |
| `label-small-bold` | 10px | 700 | 115% | Breadcrumbs |
| `label-regular` | 12px | 400 | 150% | Secondary text, input labels |
| `label-bold` | 12px | 700 | 150% | Secondary text emphasized |
| `label-selected` | 12px | 700 | 115% | Small button labels |
| `label-unselected` | 12px | 400 | 115% | Small button labels (inactive) |
| `body-regular` | 14px | 400 | 150% | Body text, unselected tabs |
| `body-bold` | 14px | 700 | 150% | Body text emphasized |
| `body-selected` | 14px | 700 | 115% | Button labels, selected tabs |
| `body-unselected` | 14px | 400 | 115% | Button labels (inactive) |
| `heading-6` | 15px | 600 | 125% | Tertiary titles |
| `heading-5` | 16px | 600 | 125% | Section titles |
| `heading-4` | 20px | 600 | 125% | Secondary titles |
| `heading-3` | 24px | 600 | 125% | Section content titles |
| `heading-2` | 28px | 600 | 125% | Page section titles |
| `heading-1` | 32px | 600 | 125% | Page titles |

**Inline style shorthand (copy-paste pattern used in all screens):**
```tsx
const bodyBold: React.CSSProperties = { fontFamily: "var(--font-family)", fontSize: 14, fontWeight: 700, color: "var(--palette-blue-0)", lineHeight: "115%" };
const body:     React.CSSProperties = { fontFamily: "var(--font-family)", fontSize: 14, fontWeight: 400, color: "var(--palette-blue-0)", lineHeight: "150%" };
const label:    React.CSSProperties = { fontFamily: "var(--font-family)", fontSize: 12, fontWeight: 400, color: "var(--palette-blue-2)", lineHeight: "150%" };
const link:     React.CSSProperties = { fontFamily: "var(--font-family)", fontSize: 12, fontWeight: 400, color: "var(--palette-primary-0)", textDecoration: "none" };
```

---

### 2c — Spacing
| Token | Value |
|---|---|
| `--spacing-xs` | `2px` |
| `--spacing-sm` | `4px` |
| `--spacing-md` | `8px` |
| `--spacing-md2` | `12px` |
| `--spacing-lg` | `16px` |
| `--spacing-xl` | `24px` |
| `--spacing-2xl` | `32px` |
| `--spacing-3xl` | `40px` |

### 2d — Radii
| Token | Value |
|---|---|
| `--radius-xs` | `2px` |
| `--radius-sm` | `4px` |
| `--radius-md` | `8px` |
| `--radius-lg` | `12px` |
| `--radius-xl` | `16px` |
| `--radius-2xl` | `32px` |
| `--radius-full` | `9999px` |

### 2e — Shadows
| Token | Value |
|---|---|
| `--tile-shadow-card` | `0px 0px 8px 0px rgba(203,225,242,0.8)` |
| `--tile-shadow-interactive` | `0px 4px 8px 0px rgba(203,225,242,0.8)` |

### 2f — Tile padding (use via `padding` prop — never inline)
| Prop value | Token | px |
|---|---|---|
| `"panel"` | `--tile-padding-panel` | `8px` |
| `"content"` | `--tile-padding-content` | `16px` |
| `"screen"` | `--tile-padding-screen` | `24px` |

---

### 2g — Icons

**These are the only valid `name` values for `<Icon>`. Do not invent icon names.**

```
activity-feed  add  add-profile  admin  ai  ai-agent
arrow-2-directions  arrow-2-directions-vertical  arrow-4-directions
arrow-down  arrow-left  arrow-right  arrow-up
audit-planner  availability  baby  bag  bell  book  booking
bubbles  bug  bulk  bulk-move
calendar  calendar-clash  calendar-delete  calendar-misaligned
car  caret-down  caret-left  caret-right  caret-up
certificate  chat  check  chevron-down  chevron-left  chevron-right  chevron-up
clock  close-role  collapse  compare  copy  core  cost  created  cross
department  development  dot  dot-big  down  duplicate
edit  engagement  engagement-audit  error
expand  expand-all  expanded-all  export  extend
face-smile  facebook  filter  filter-applied  filter-clean  filter2
fire  flower-spa  folder  forbidden
ghost  head-heart  heart  heatmap  help  hidden  hierarchical  history  home
hourglass-empty  hourglass-half  house-laptop  house-user
import  industry  info  insights  instagram
key  keyboard  learning  link  linkedin  links  list  location  locked  logout
mail  manage-roles  mandatory  marketplace
menu-horizontal  menu-vertical  merge  missing  mobile  money  mouse-cursor  move
non-demand  note  notifications
open  overbooking  overbooking-acknowledged  owner
palm-tree  paper-clip  paper-plane  path  pen  person-minus  pf-logo
phone  pin  placeholder-profile  plane  play  postpone  preferences
profile  profile-field  profiles  question
reassign  refresh  refresh-clean  refresh-warning  remove  remove-all
reports  role  role-audit  rollforward
save  save-add  save-remove  search  sector  segment  share  shown
skills-framework  skype  skype-for-business  smart-allocation  snooze
soft-exception  sort  split  split2
substitute-child  substitute-parent  substitute-parent-child  subtract  suggested
table  tag  target-allocation  task  teams  timeline  twitter
undo  unpin  unseen  up  user-filled  user-interest
verified  verified-credly  verified-others
warning  web  wine-glass  work  workflow  zoom-in  zoom-out
```

Icon sizes: `14 | 16 | 20 | 24` (px)

---

## 3 — Components

**All imported from `@ips/design-system`. Never use raw HTML where an IPS component exists. Never guess prop names — use only what is listed here.**

### 3a — Layout

#### `Navbar`
```tsx
<Navbar activeId="workflow" />
```
| Prop | Type |
|---|---|
| `activeId` | `"search"` `"create"` `"marketplace"` `"workflow"` `"audit-planner"` `"insights"` `"reports"` `"activity-feed"` `"profiles"` `"booking"` `"notifications"` `"links"` `"admin"` `"chat"` `"help"` `"profile"` |
| `onSelect` | `(id: string) => void` |
| `avatarInitials` | `string` |
| `avatarSrc` | `string` |

#### `Page`
```tsx
<Page navbar={<Navbar activeId="workflow" />} variant="1280">
  {children}
</Page>
```
| Prop | Type |
|---|---|
| `navbar` | `ReactNode` |
| `variant` | `"full"` `"1280"` `"profile-regular"` `"profile-summary"` |
| `sidebar` | `ReactNode` — 280px left column (profile variants) |
| `rightPanel` | `ReactNode` — 500px right column (profile-summary only) |

#### `Tile`
```tsx
<Tile tileStyle="highlight" padding="content">...</Tile>
```
| Prop | Type |
|---|---|
| `tileStyle` | `"highlight"` `"selected"` `"interactive"` `"default"` `"object-dark"` `"object-light"` `"dark"` |
| `padding` | `"panel"` `"content"` `"screen"` |
| `onClick` | `() => void` — makes it a button |
| `style` | safe: `width` `flex` `minWidth` `maxWidth` `alignSelf` `margin*` only |

| tileStyle | Background | Border/Shadow |
|---|---|---|
| `highlight` | `#FFFFFF` | card shadow |
| `selected` | `#E7EAF8` | flat |
| `interactive` | `#FFFFFF` | hover shadow |
| `default` | `#F8F9FD` | flat |
| `object-dark` | `#F8F9FD` | `1px #CFDAF7` |
| `object-light` | `#FFFFFF` | `1px #CFDAF7` |
| `dark` | `#0C1457` | shadow |

**Hard rule: never set `style={{ padding }}` or `style={{ background }}` on a Tile.**

#### `Header`
| Prop | Type |
|---|---|
| `size` | `"page"` `"section"` `"content"` |
| `title` | `string` |
| `subtitle` | `string` |
| `leftIcon` | `IconName` |
| `rightIcon` | `IconName` |
| `actions` | `{ label, variant: "primary"\|"secondary", onClick }[]` |

#### `PageHeader`
| Prop | Type |
|---|---|
| `breadcrumbs` | `{ label, href? }[]` |
| `title` | `string` |
| `wfState` | `WFState` |
| `subtitleItems` | `{ label, value }[]` |
| `actions` | `HeaderAction[]` |

#### `Navigation`
| Prop | Type |
|---|---|
| `orientation` | `"horizontal"` `"vertical"` |
| `tabs` | `{ id, label, badge?, subtitle?, showIcon?, disabled? }[]` |
| `activeId` | `string` |
| `onChange` | `(id: string) => void` |
| `fillWidth` | `boolean` |

#### `Accordion`
| Prop | Type |
|---|---|
| `title` | `string` |
| `size` | `"body"` `"heading5"` `"heading4"` |
| `defaultExpanded` | `boolean` |
| `children` | `ReactNode` |

#### `Divider`
| Prop | Type |
|---|---|
| `orientation` | `"horizontal"` `"vertical"` |
| `type` | `"default"` `"draggable"` |
| `margins` | `boolean` |
| `style` | `React.CSSProperties` |

#### `Actions`
| Prop | Type |
|---|---|
| `variant` | `"content"` `"sticky-screen"` `"sticky-panel"` |
| `leftActions` | `{ label, variant, onClick, disabled? }[]` |
| `rightActions` | `{ label, variant, onClick, disabled? }[]` |

---

### 3b — Buttons

**Never use a raw `<button>` element. Always use `Button` from `@ips/design-system`.**

```tsx
<Button kind="primary" size="regular" onClick={...}>Label</Button>
```

| `kind` | Use for |
|---|---|
| `"primary"` | Main CTA |
| `"secondary"` | Secondary action |
| `"tertiary"` | Low-emphasis |
| `"destructive"` | Delete / reject |
| `"ghost"` | Minimal, no border |
| `"inverted"` | On dark backgrounds |
| `"link"` | Text link — "Show more", "Add Reviewer", breadcrumb links |
| `"icon"` | Square bordered icon button — toolbar actions |
| `"iconTertiary"` | Borderless icon button — inline card actions |
| `"iconGhost"` | Ghost icon button |

| Prop | Type |
|---|---|
| `kind` | see above |
| `size` | `"regular"` `"small"` |
| `disabled` | `boolean` |
| `onClick` | `(e) => void` |
| `title` | `string` — tooltip/aria |
| `type` | `"button"` `"submit"` `"reset"` |
| `style` | safe: layout props only |

#### `ButtonGroup` (split button)
| Prop | Type |
|---|---|
| `label` | `string` |
| `variant` | `"primary"` `"secondary"` |
| `onClick` | `() => void` |
| `onDropdownClick` | `() => void` |
| `fill` | `boolean` |
| `disabled` | `boolean` |

---

### 3c — Inputs

**Never use raw `<input>`, `<select>`, or `<textarea>` as the primary field — use IPS input components.**

#### `Input` (text field)
| Prop | Type |
|---|---|
| `label` | `string` |
| `value` | `string` |
| `onChange` | `(e: ChangeEvent<HTMLInputElement>) => void` |
| `placeholder` | `string` |
| `message` | `string` |
| `state` | `"default"` `"error"` `"warning"` `"instructions"` |
| `readOnly` | `boolean` |
| `disabled` | `boolean` |
| `mandatory` | `boolean` |
| `type` | `"text"` `"email"` `"password"` `"number"` `"tel"` `"url"` |

#### `InputSelect` (dropdown trigger)
Same as `Input` but no `onChange`/`onFocus`/`onBlur`. Has `onClick` instead.

#### `InputSearch`
| Prop | Type |
|---|---|
| `value` | `string` |
| `onChange` | `(e) => void` |
| `onClear` | `() => void` |
| `placeholder` | `string` |

#### `InputMultiselect`
| Prop | Type |
|---|---|
| `label` | `string` |
| `mandatory` | `boolean` |
| `tags` | `{ id, label }[]` |
| `onRemoveTag` | `(id: string) => void` |
| `onClearAll` | `() => void` |
| `showChevron` | `boolean` |

#### `InputBookingCategory`
| Prop | Type |
|---|---|
| `label` | `string` |
| `selectedLabel` | `string` |
| `selectedColor` | `string` |
| `mandatory` | `boolean` |
| `onClick` | `() => void` |

#### `InputInline`
| Prop | Type |
|---|---|
| `inlineLabel` | `string` |
| `value` | `string` |
| `mandatory` | `boolean` |
| `onClick` | `() => void` |

---

### 3d — Pills & Status

#### `PillSimple`
| Prop | Type |
|---|---|
| `label` | `string` |
| `size` | `"regular"` `"small"` |
| `bg` | `string` — CSS colour token |
| `color` | `string` — CSS colour token |
| `leftIcon` | `IconName` |

#### `PillWFState`
| Prop | Type |
|---|---|
| `state` | `"new"` `"shortlisting"` `"in-review"` `"invited"` `"pending"` `"partially-filled"` `"filled"` `"partially-booked"` `"booked"` `"partially-confirmed"` `"confirmed"` `"not-filled"` `"exceptions"` `"technical-overlay"` `"accreditations"` |
| `size` | `"regular"` `"small"` |

WFState colours (for reference):
- `new` → `#E7EAF8` / `#0D2976`
- `shortlisting` → `#6EF29C` / `#0D2976`
- `confirmed` / `partially-confirmed` → `#0C1457` / white
- `booked` / `partially-booked` → `#1F78B4` / white
- `filled` / `partially-filled` → `#2358F8` / white
- `not-filled` → `#FFE8AD` / `#9B5A01`
- `exceptions` / `technical-overlay` / `accreditations` → `#FFE2E2` / `#A30013`

#### `PillRemovable`
| Prop | Type |
|---|---|
| `label` | `string` |
| `size` | `"regular"` `"small"` |
| `onRemove` | `() => void` |
| `bg` | `string` |
| `color` | `string` |
| `bordered` | `boolean` |

#### `PillKPI`
`type`: `"compliant"` `"approved"` `"exception"` `"rejected"` `"requested"` `"condition-not-met"`

#### `PillCustomValue`
`type`: `"approved"` `"awaiting"` `"blocked"` `"merged"`

#### `PillReportStatus`
`type`: `"ready"` `"no-data"` `"failed"` `"pending"` `"in-progress"`

#### `PillActivityTag`
| Prop | Type |
|---|---|
| `label` | `string` |
| `size` | `"regular"` `"small"` |

#### `PillCertificate`
| Prop | Type |
|---|---|
| `name` | `string` |
| `date` | `string` |
| `onRemove` | `() => void` |
| `size` | `"regular"` `"small"` |

#### `PillModifier`
| Prop | Type |
|---|---|
| `leftLabel` | `string` |
| `rightLabel` | `string` |
| `size` | `"regular"` `"small"` |
| `bg` | `string` |
| `rightIcon` | `IconName` |
| `onRemoveLeft` | `() => void` |
| `onClickRight` | `() => void` |

#### `PillFilter`
| Prop | Type |
|---|---|
| `field` | `string` |
| `value` | `string` |
| `onRemove` | `() => void` |

#### `PillSavedFilter`
| Prop | Type |
|---|---|
| `label` | `string` |
| `onRemove` | `() => void` |
| `onShare` | `() => void` |

#### `BookingPill`
| Prop | Type |
|---|---|
| `category` | `"booking-blue"` `"booking-red"` `"booking-purple"` `"engagement-booked"` `"engagement-partial"` `"role-booked"` `"role-partial"` `"pending"` `"hidden"` |
| `label` | `string` |
| `hours` | `string` — regular size only |
| `size` | `"regular"` `"small"` |
| `nonDemand` | `boolean` |
| `otherBookings` | `boolean` |
| `onClick` | `() => void` |

---

### 3e — People

#### `Avatar`
| Prop | Type |
|---|---|
| `initials` | `string` |
| `src` | `string` |
| `size` | `"small"` (30px) `"big"` (80px) |
| `showChat` | `boolean` |

#### `WorkforceMember`
| Prop | Type |
|---|---|
| `variant` | `"small-1line"` `"small-2lines"` `"small-3lines"` `"big"` `"card"` |
| `name` | `string` |
| `initials` | `string` |
| `avatarSrc` | `string` |
| `email` | `string` — 2lines/3lines/card |
| `jobTitle` | `string` — 3lines/card/big |
| `addedBy` | `string` — card variant |
| `hideAvatar` | `boolean` |
| `onClick` | `() => void` |
| Flag props | `placeholder` `suspended` `interest` `contractualTimeSlice` `suggested` `namedResource` — all `boolean` |

---

### 3f — Cards

#### `Card`
```tsx
<Card
  variant="match"
  name="Spencer Harmon"
  initials="SH"
  matchPercent={74}
  availabilityPercent={100}
  skillGroups={[...]}
  expandedSkillGroups={[...]}
  actions={{ step: "not-shortlisted", onShortlist: () => {}, onFillBook: () => {} }}
/>
```

| Prop | Type |
|---|---|
| `variant` | `"match"` `"directory"` |
| `name` | `string` |
| `jobTitle` | `string` |
| `initials` | `string` |
| `avatarSrc` | `string` |
| `matchPercent` | `number` |
| `availabilityPercent` | `number` |
| `expanded` | `boolean` |
| `defaultExpanded` | `boolean` |
| `onExpandedChange` | `(expanded: boolean) => void` |
| `skillGroups` | `SkillGroup[]` |
| `expandedSkillGroups` | `SkillGroup[]` |
| `roleFields` | `RoleField[]` |
| `actions` | `CardActions` |

`CardActions.step` values: `"not-shortlisted"` `"shortlisted"` `"shortlisted-reviewer"` `"accepted-invite"` `"invited"` `"accepted-fillbook"` `"booked"` `"filled"` `"declined"`

`SkillGroup`: `{ label: string, count?: string, skills: SkillItem[] }`
`SkillItem`: `{ name, requiredProficiency?, profileProficiency?, missing?, tags? }`
`RoleField`: `{ label, value, matches? }`

---

### 3g — Data

#### `Table<T>`
| Prop | Type |
|---|---|
| `columns` | `TableColumn<T>[]` |
| `rows` | `T[]` |
| `compact` | `boolean` |
| `selectable` | `boolean` |
| `selectedRows` | `(string\|number)[]` |
| `onSelectionChange` | `(selected) => void` |
| `sortKey` | `string` |
| `sortDirection` | `"asc"` `"desc"` `"none"` |
| `onSort` | `(key, dir) => void` |

`TableColumn`: `{ key, header, sortable?, width?, sticky?, type?, renderCell?, align? }`
`type` values: `"text-primary"` `"text-regular"` `"pill"` `"wm"` `"number"` `"percentage"` `"button"` `"icon"` `"checkbox"` `"custom"`

#### `Pagination`
| Prop | Type |
|---|---|
| `total` | `number` |
| `current` | `number` |
| `onChange` | `(page: number) => void` |
| `size` | `"regular"` `"small"` |

#### `Checkbox`
| Prop | Type |
|---|---|
| `label` | `string` |
| `subLabel` | `string` |
| `checked` | `boolean` |
| `indeterminate` | `boolean` |
| `disabled` | `boolean` |
| `onChange` | `(checked: boolean) => void` |
| `layout` | `"horizontal"` `"vertical"` |

#### `Switch`
| Prop | Type |
|---|---|
| `checked` | `boolean` |
| `defaultChecked` | `boolean` |
| `onChange` | `(checked: boolean) => void` |
| `label` | `string` |
| `showLabel` | `boolean` |
| `layout` | `"vertical"` `"horizontal-left"` `"mobile-full"` |
| `disabled` | `boolean` |

#### `SliderNumber`
| Prop | Type |
|---|---|
| `value` | `number` |
| `min` | `number` |
| `max` | `number` |
| `step` | `number` |
| `onChange` | `(value: number) => void` |
| `showInput` | `boolean` |

#### `SliderRange`
| Prop | Type |
|---|---|
| `valueFrom` | `number` |
| `valueTo` | `number` |
| `min` | `number` |
| `max` | `number` |
| `onChangeFrom` | `(value: number) => void` |
| `onChangeTo` | `(value: number) => void` |

---

### 3h — Booking

#### `BookingCell`
| Prop | Type |
|---|---|
| `value` | `number\|null` |
| `category` | `"blue"` `"red"` `"purple"` `"empty"` |
| `readOnly` | `boolean` |
| `deadline` | `boolean` |
| `onChange` | `(value: number) => void` |

#### `BookingSlideshow`
| Prop | Type |
|---|---|
| `tab` | `"details"` `"notes"` `"history"` |
| `onTabChange` | `(tab) => void` |
| `rules` | `{ startDate, endDate, value? }[]` |
| `showVisible` | `boolean` |
| `showPhase` | `boolean` |
| `phase` | `string` |
| `showDateCreated` | `boolean` |
| `dateCreated` | `string` |
| `category` | `string` |
| `title` | `string` |
| `description` | `string` |
| `notes` | `{ author, initials, date, text }[]` |
| `history` | discriminated union — see BookingSlideshowHistoryAction |
| `hidden` | `boolean` |
| `notesCount` | `number` |
| `width` | `number\|string` |

---

### 3i — Side Panels

#### `SidePanel` (base)
| Prop | Type |
|---|---|
| `open` | `boolean` |
| `onClose` | `() => void` |
| `children` | `ReactNode` |
| `width` | `number` — default 600 |

#### `BookingSidePanel`
| Prop | Type |
|---|---|
| `open` | `boolean` |
| `onClose` | `() => void` |
| `tab` | `"details"` `"notes"` `"history"` `"edit"` `"create-demand"` `"create-single"` `"create-repeated"` `"edit-repeated"` `"edit-hidden"` `"edit-not-editable"` |
| `data` | `BookingSidePanelData` — wmName, wmInitials, roleName, engagementName, duration, totalHours, bookingCategory, description, title, totalRules, notes, history, onEdit, onClone, onReassign, onRemove, onSave |

Also available: `ProfileSidePanel` (600px), `EngagementSidePanel` (400px), `RoleSidePanel` (400px), `BookingCategorySidePanel` (400px)

---

### 3j — Feedback

#### `Alert`
| Prop | Type |
|---|---|
| `type` | `"error"` `"warning"` `"success"` `"general"` `"ai"` `"bulk-banner"` |
| `layout` | `"inline"` `"with-header"` |
| `message` | `string` |
| `body` | `string` — with-header only |
| `actions` | `{ label, onClick }[]` — max 2 |

#### `Tooltip`
| Prop | Type |
|---|---|
| `content` | `ReactNode` |
| `children` | `ReactNode` — trigger |
| `placement` | `"down-center"` `"down-left"` `"down-right"` `"up-center"` `"up-left"` `"up-right"` `"left-center"` `"right-center"` `"no-arrow"` + variants |
| `maxWidth` | `number` |
| `disabled` | `boolean` |

#### `Toast` / `ToastProvider` / `useToast()`
```tsx
// Wrap app:
<ToastProvider>{children}</ToastProvider>
// Use:
const { showToast } = useToast();
showToast({ type: "success", message: "Saved!", duration: 5000 });
```
`type`: `"success"` `"warning"` `"error"`

#### `EmptyState`
| Prop | Type |
|---|---|
| `size` | `"big"` `"small-vertical"` `"small-horizontal"` |
| `title` | `string` |
| `subtitle` | `string` — big only |
| `illustration` | `ReactNode` — big only |
| `actions` | `{ label, kind: "primary"\|"secondary", onClick }[]` |
| `showIcon` | `boolean` |

#### `ProgressLinear`
| Prop | Type |
|---|---|
| `value` | `number` 0–100 |
| `showLabel` | `boolean` |
| `semantic` | `boolean` |

#### `ProgressRadial`
| Prop | Type |
|---|---|
| `value` | `number` 0–100 |
| `showLabel` | `boolean` |
| `semantic` | `boolean` |
| `size` | `number` px |

---

## 4 — CSS Verification Checklist

Run after every component placed:

- [ ] `@ips/design-system/styles/components` is the **first** import in `main.tsx`
- [ ] No `style={{ padding }}` on any `Tile` — use `padding` prop
- [ ] No `style={{ background }}` on any `Tile` — use `tileStyle` prop
- [ ] No raw `<button>` — always `Button` from `@ips/design-system`
- [ ] No raw `<div>` as content container — use `Tile`
- [ ] Icon toolbar buttons → `kind="icon"` (bordered) or `kind="iconTertiary"` (borderless)
- [ ] Link-style text buttons → `kind="link"`
- [ ] Only colours from section 2a used — no hardcoded hex
- [ ] Only icon names from section 2g used — no invented names
- [ ] Font is Mulish — `index.html` has Google Fonts `<link>`
