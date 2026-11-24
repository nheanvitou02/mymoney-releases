# Changelog — MyMoney (លុយខ្ញុំ)

## [1.1.0] — 2026-11-24

### Added
- **Category Management UI (F-01):**
  - Full management of expense and income categories with bilingual support (Khmer & English).
  - 27 curated icons and 16 color choices tailored for Cambodian daily life.
  - Safe category deletion (D-04): default category protection and mandatory transaction reassignment before deleting in-use categories.
- **Transaction Full Edit & Duplicate (F-02):**
  - Full-field editing of amount, type, currency, category, date, and notes from transaction details.
  - One-tap duplicate action pre-filling details with today's date in Cambodia timezone (`Asia/Phnom_Penh`).

### Fixed
- **Global Android Safe Area Insets:** Mounted root `SafeAreaProvider` and implemented dynamic top status bar insets to prevent status bar overlap on notched and punch-hole displays.
- **Responsive Category Icon Grid:** Dynamically scales between 4 and 5 columns to eliminate empty horizontal space, with enhanced 2-line label wrapping for long Khmer titles.

### Technical & Platform Specifications
- **Package Identifier:** `com.mymoney.app`
- **Version Code:** `3`
- **Target SDK:** Android 15 / 16 (API Level 36)
- **Minimum SDK:** Android 7.0 Nougat (API Level 24)
- **Engine:** Hermes JavaScript Bytecode (`.hbc`)
- **Architectures:** Multi-ABI Universal (`arm64-v8a`, `armeabi-v7a`, `x86`, `x86_64`)
- **Signing:** APK Signature Scheme v2 (Production Keystore)
- **Verification Notice:** Physical Device UAT status: NOT COMPLETED / NOT VERIFIED.

All notable public releases of **MyMoney (លុយខ្ញុំ)** are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [1.0.1] — 2026-11-23

### Added
- **Global Button Shape Consistency Tokens:**
  - Standardized all button elements to use uniform corner radius tokens (`radius.button`, `radius.buttonSm`, `radius.buttonIcon`, `radius.buttonPill`).
  - All primary, secondary, outline, and destructive action buttons now strictly adhere to a consistent capsule geometry.
  - All icon-only buttons (navigation arrows, modal close buttons, search clear, deletion triggers) now strictly render as uniform circular controls.
  - All filter chips, category selectors, and segmented control pills share a dedicated pill geometry token.
- **Enhanced Screen Reader & Accessibility Metadata:**
  - Added explicit localized English and Khmer `accessibilityLabel` attributes to all icon-only buttons, navigation controls, and chips.
  - Added semantic `accessibilityRole="button"` and `accessibilityState` attributes across interactive elements.
- **Automated Button & Accessibility Test Suites:**
  - Added comprehensive native testing suites (`button.test.tsx`, `accessibilityPhase2.test.tsx`, `buttonConsistencyPhase3.test.tsx`, `buttonConsistencyPhase4.test.tsx`) covering variant rendering, touch target areas, and screen reader labels.

### Changed
- **Emerald Quick Add Visual Alignment:**
  - Aligned all Primary Action Buttons across Settings, Savings Goals, and modals to match the approved Quick Add visual reference: vibrant emerald gradient (`#10B981` to `#059669`), specular top rim highlight, subtle emerald ambient glow, and high-contrast white typography.
  - Removed artificial 3D bevels, plastic gradients, and thick neon outlines.
  - Preserved distinct visual styling for Secondary (frosted glass) and Destructive (crimson danger) actions.
- **DatePicker & Touch Target Calibration:**
  - Expanded interactive calendar day cell touch targets to 44x44dp minimum while keeping visible day circle indicators visually compact and preventing neighboring cell overlap.
  - Enforced 44x44dp hitSlop boundaries on month and year navigation controls, eliminating accidental double-taps.
  - Upgraded Savings Goals management buttons (Edit, Archive, Delete) and History search clear to meet the 44x44dp touch target guideline.
- **Form & Selection Semantics:**
  - Replaced custom pressable currency toggles in Savings Goals with `<SegmentedControl>` for appropriate selection semantics rather than masquerading as primary submit buttons.
  - Unified month navigation chevrons on Dashboard and Reports with standardized circular glass styling.

### Fixed
- Fixed overlapping hitSlop regions on DatePicker navigation controls.
- Prevented potential animation timer leaks when `useReducedMotion` is active.

### Technical & Platform Specifications
- **Package Identifier:** `com.mymoney.app`
- **Version Code:** `2`
- **Target SDK:** Android 15 / 16 (API Level 36)
- **Minimum SDK:** Android 7.0 Nougat (API Level 24)
- **Engine:** Hermes JavaScript Bytecode (`.hbc`)
- **Architectures:** Multi-ABI Universal (`arm64-v8a`, `armeabi-v7a`, `x86`, `x86_64`)
- **Signing:** APK Signature Scheme v2 (Production Keystore)

---

## [1.0.0] — 2026-11-18

### Added
- **Local-First Native SQLite Persistence:**
  - 100% offline data storage using sandboxed Expo SQLite (`mymoney.db`) with write-ahead logging (WAL) and foreign key enforcement.
  - Zero cloud dependencies, zero external tracking, and zero remote accounts required.
- **Dual-Currency Financial Precision Engine:**
  - Strict integer minor unit math (USD cents, KHR riels) eliminating JavaScript floating-point rounding errors.
  - Runtime dual-currency conversion with configurable exchange rate (default: 4,100 KHR per 1 USD) and selectable rounding modes (`EXACT` and `CASH_100`).
  - Total balance consolidation dynamically displaying secondary currency approximations (`≈`).
- **First-Time User Onboarding Guide:**
  - 5-step native bilingual carousel introducing income/expense tracking, dashboard reports, savings goals, and offline privacy.
  - Skip and completion tracking persisted in SQLite; re-accessible at any time from Settings.
- **Transaction Lifecycle & Management:**
  - Minimal-tap Quick Add modal accessible from anywhere via floating bottom action button.
  - Dual-currency toggle ($ / ៛) with positive amount validation.
  - 14 pre-seeded bilingual system categories (9 expense, 5 income) with dedicated icons and colors.
  - Interactive DatePicker supporting backdated transactions with quick shortcuts (`Today`, `Yesterday`) and Cambodia timezone (`Asia/Phnom_Penh`, UTC+7) enforcement. Future dates strictly rejected.
  - Full-text search and filter pills (`All`, `Income`, `Expense`) in History.
  - Category deletion safety guard blocking deletion of categories referenced by transactions, with atomic reassignment support.
- **Interactive Dashboard:**
  - Dynamic monthly summary cards (Net Balance, Income, Expense).
  - Native daily income and expense bar charts (`react-native-gifted-charts`).
  - Month navigation controls stepping month-by-month.
  - Quick action shortcuts (+ Income, - Expense, History).
  - Recent transactions list with direct navigation to detailed history.
- **Savings Goals & Contributions:**
  - Create savings goals with custom target amounts, currency locking (USD or KHR), deadlines, and notes.
  - Atomic contribution recording recalculating progress inside SQLite transactions.
  - Animated progress bars displaying percentage completion.
  - Active and Archived goal management tabs.
- **Reports & Analytics:**
  - Flexible date presets: This Month, Last Month, Last 3 Months, Last 6 Months, This Year, and Custom Range.
  - Interactive category breakdown donut chart with center totals.
  - Ranked expense and income category lists with percentage shares.
  - 6-month chronological trend chart comparing income and expenses side-by-side.
  - Period-over-period percentage delta comparison ($\Delta\%$).
- **Settings & Data Portability:**
  - Instant bilingual language switching between Khmer (`km`) and English (`en`) across all screens.
  - Configurable display currency and exchange rate.
  - Real-time SQLite database statistics (transaction count, categories, active goals, total savings).
  - Atomic full backup export and import in JSON format, supporting both `REPLACE` (full overwrite) and `MERGE` (non-destructive upsert) modes with Zod pre-validation and rollback guarantees.
  - CSV transaction export with UTF-8 Byte Order Mark (`\uFEFF`) for native Khmer script rendering in Microsoft Excel.
  - Safe factory reset with double confirmation.
- **Appearance & Design System A:**
  - "Soft Emerald" design language with calm, high-contrast visual tokens.
  - Dynamic Light Mode, Dark Mode (`#0B1220` canvas, `#151F2E` cards), and System Mode (automatically follows Android OS dark theme).
  - Native typography tuned for `Noto Sans Khmer` and `Inter` preventing subscript and vowel clipping.
- **Support MyMoney:**
  - Dedicated voluntary support screen with structured ABA Bakong KHQR container and reassurance regarding financial privacy.

### Technical & Platform Specifications
- **Package Identifier:** `com.mymoney.app`
- **Version Code:** `1`
- **Target SDK:** Android 15 / 16 (API Level 36)
- **Minimum SDK:** Android 7.0 Nougat (API Level 24)
- **Engine:** Hermes JavaScript Bytecode (`.hbc`)
- **Architectures:** Multi-ABI Universal (`arm64-v8a`, `armeabi-v7a`, `x86`, `x86_64`)
- **Signing:** APK Signature Scheme v2
- **Permissions:** Zero dangerous runtime permissions requested (`"permissions": []`)
