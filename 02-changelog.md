# Changelog

### Support by Time module **[WHMCS](https://puqcloud.com/link.php?id=77)**
#####  [Order now](https://puqcloud.com/whmcs-module-support-by-time.php) | [Download](https://download.puqcloud.com/WHMCS/servers/PUQ_WHMCS-Support-by-time/) | [Community](https://community.puqcloud.com/)

---

## v3.0 (2026-06-04)

- **Compatibility**: supports PHP **7.4 / 8.1 / 8.2+** and **WHMCS 8.x / 9.x**. Published as a separate ionCube build per PHP version — `php74`, `php81`, `php82` (use `php82` for PHP 8.2 and any newer PHP). WHMCS 8 runs on PHP 7.4 / 8.1 / 8.2; WHMCS 9 runs on PHP 8.2.
- Module rewritten on the new PUQ module skeleton:
  - License class moved into the main module file (`puqSupportByTime.php`)
  - New `puqSupportByTimeModuleSettings` class for product configuration with structured JSON in `configoption24`
  - Product configuration UI rendered through the `AdminAreaFooterOutput` hook
  - License alert added on the WHMCS admin homepage (`AdminHomepage` hook)
- **Schema versioning**: new `puq_module_versions` table + migration runner so updates apply schema changes automatically and idempotently on first load.
- Redesigned client area (cards, progress bar, modern stat panels)
- Redesigned ticket header (Bootstrap panels, icons)
- Redesigned admin product page (summary table, history navigator)
- **AJAX ticket header**: the entire time-logging header on the admin ticket page is now rendered and driven by AJAX. Save / Close+Save / Reopen / Start-Stop timer / Order service no longer reload the page.
- **Multi-entry per ticket**: every Save Time (and every timer stop) is recorded as its own entry instead of overwriting, so a ticket keeps a full breakdown of sessions. Each entry has its own note, operator and timestamp.
- **Per-entry notes + operator tracking**: every time entry can carry an optional note (shown to the client when *Show work log to client* is enabled) and stores the WHMCS admin who logged it. Columns on `puqSupportByTime_items`: `note`, `admin_id`, `created_at`, `ticket_record_id`.
- **Parent ticket records**: new `puqSupportByTime_tickets` table holds per-ticket billing state (one billable item per ticket) and a snapshot of package hours / hourly rate, while `puqSupportByTime_items` becomes a pure time log.
- **Live timer**: Start / Stop / Cancel on the ticket page with a server-anchored running clock. New table `puqSupportByTime_timers`. Stop rounds up to the nearest minute and saves a regular time entry. A floating widget on every admin page lists all of the operator's running timers.
- **Audit trail**: append-only log of every state change (time logged / updated / deleted, timer start / stop / cancel, service ordered, ticket billed). New table `puqSupportByTime_audit`. Shown on the ticket header and on the service page.
- **Operator report**: per-operator hours and entry counts for the current and previous month on the service page.
- **Cost calculator** in the client-area home screen — interactive "if I use ___ more hours" predictor.
- **Usage chart** in the client-area history tab — last 12 months as a Google ComboChart with a package line and bars coloured by overage status.
- **Usage notifications**: email the client when monthly usage crosses configured thresholds (e.g. 80 %, 100 %). New table `puqSupportByTime_notifications` for idempotent per-(month, threshold) tracking.
- **Show work log to client** toggle per product — reveals the operator name + note per ticket in the client area.
- Date filter rewritten to use `Y-m-t` instead of the literal `-31`
- Custom admin path now read from `configuration.php` consistently
- **Backward-compatible settings migration**: legacy values stored in `configoption3` (hours / invoice action / item name) and `configoption4` (per-currency hourly rate) are read transparently when the new `configoption24` slot is empty, so existing v2.x products keep working without any reconfiguration. The first save through the v3.0 form moves everything into `configoption24`.

> **Note:** No manual reconfiguration is required after updating to v3.0 — settings are migrated automatically on first read. Re-saving the product through the new form is recommended but not mandatory.

---

## v2.1 (2025-09-20)

- Support for custom admin path

---

## v2.0 (2024-09-23)

- Module coded with ionCube v13
- Supported PHP versions: 7.4, 8.1, 8.2
- Compatible with WHMCS 8.11.0+

---

## v1.3 (2023-10-19)

- Added the ability to delete reserved time positions from the admin panel
- One-Time package validation moved from daily cron to every cron run

---

## v1.2.5 (2023-10-11)

- WHMCS 8.8.0 support
- 25 language translations added/updated

---

## v1.2 (2023-08-02)

- One-Time support packages with hour limit
- Human-readable time display in client and admin areas
- Display and logic improvements

---

## v1.1 (2023-03-21)

- Client area redesign
- Translation support
- WHMCS 8.6, IonCube v12, PHP 8.1 and PHP 7.4 support
- Invoice item description field

---

## v1.0 (2022-10-01)

- First release
