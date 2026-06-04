# WHMCS setup (install/update)

### Support by Time module **[WHMCS](https://puqcloud.com/link.php?id=77)**
#####  [Order now](https://puqcloud.com/whmcs-module-support-by-time.php) | [Download](https://download.puqcloud.com/WHMCS/servers/PUQ_WHMCS-Support-by-time/) | [Community](https://community.puqcloud.com/)

## System requirements & compatibility

The module supports **PHP 7.4, 8.1 and 8.2+** and is published as a separate ionCube build per PHP version. **Download the build that matches the PHP version your WHMCS server actually runs on.**

| WHMCS version | PHP version | Module build to download |
|---------------|-------------|--------------------------|
| **WHMCS 8.x** | PHP 7.4 | `php74` |
| **WHMCS 8.x** | PHP 8.1 | `php81` |
| **WHMCS 8.x** | PHP 8.2 | `php82` |
| **WHMCS 9.x** | PHP 8.2 | `php82` |

- **WHMCS 8** runs on PHP 7.4 / 8.1 / 8.2 — pick the build matching your PHP (`php74`, `php81` or `php82`).
- **WHMCS 9** runs on PHP 8.2 — use the `php82` build.
- **PHP 8.2 and any newer PHP** (8.3, 8.4, …): always use the `php82` build.
- **ionCube Loader** v13 or newer (v14, v15) must be installed and active.

> **Note:** The module uses ionCube encoding. Make sure the ionCube Loader for your PHP version is installed and active on your server.

---

## Download

The module can be ordered and downloaded from PUQ Cloud:

- **Order / Download:** [https://puqcloud.com/whmcs-module-support-by-time.php](https://puqcloud.com/whmcs-module-support-by-time.php)
- **All versions and builds (browse everything):** [https://download.puqcloud.com/WHMCS/servers/PUQ_WHMCS-Support-by-time/](https://download.puqcloud.com/WHMCS/servers/PUQ_WHMCS-Support-by-time/) — contains the `php74` / `php81` / `php82` directories, each with the latest archive and all previous versions.
- **Community:** [https://community.puqcloud.com/](https://community.puqcloud.com/)
- **Direct download — choose the build that matches your PHP version:**

```
# PHP 7.4 (WHMCS 8 on PHP 7.4)
wget https://download.puqcloud.com/WHMCS/servers/PUQ_WHMCS-Support-by-time/php74/PUQ_WHMCS-Support-by-time-latest.zip

# PHP 8.1 (WHMCS 8 on PHP 8.1)
wget https://download.puqcloud.com/WHMCS/servers/PUQ_WHMCS-Support-by-time/php81/PUQ_WHMCS-Support-by-time-latest.zip

# PHP 8.2 and newer (WHMCS 8 on PHP 8.2, or WHMCS 9) — use php82
wget https://download.puqcloud.com/WHMCS/servers/PUQ_WHMCS-Support-by-time/php82/PUQ_WHMCS-Support-by-time-latest.zip
```

> **Which build?** Match the build to your server's PHP version, not to WHMCS: PHP 7.4 → `php74`, PHP 8.1 → `php81`, PHP 8.2 or newer → `php82`.

After downloading, extract the archive:

```
unzip PUQ_WHMCS-Support-by-time-latest.zip
```

---

## Installation

### Step 1: Upload files

Extract the module archive and copy the `puqSupportByTime` directory to the WHMCS servers module directory:

```
WHMCS_WEB_DIR/modules/servers/puqSupportByTime
```

### Step 2: Create product

Navigate to **System Settings** → **Products/Services** → **Create a New Product**:

1. Select the **PUQ Support by Time** module in the **Module settings** section
2. Configure the product parameters (see [Product Configuration](#))

> The Support by Time module is a **server module without a server**: no server entry is required in WHMCS *System Settings → Servers* — the module does not connect to any external system.

---

## Update

### Step 1: Backup

Before updating, it is recommended to back up:
- WHMCS database
- Module files in `modules/servers/puqSupportByTime/`

### Step 2: Upload new files

Download and extract the new version, then overwrite all files in:

```
WHMCS_WEB_DIR/modules/servers/puqSupportByTime/
```

### Step 3: Verification

1. Log in to the WHMCS admin panel
2. Verify the home screen has no license warnings for your products
3. Open one of your support products and verify all configuration values are still set

> **Important (v3.0):** The product configuration form was redesigned. After updating to v3.0, open every Support by Time product and re-save its settings to migrate existing values into the new structured storage format.
