# Changelog — MyMoney (លុយខ្ញុំ)

All notable public releases of **MyMoney (លុយខ្ញុំ)** are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

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
