# NerdKit-Config

Remote parameter-driven configuration for the **NerdKit** Android application.

## Automatic Publishing to Cloudflare R2

Whenever you edit and save `nerdkit-main-config.toml` on GitHub (either on your computer or through the GitHub Mobile App), an automated GitHub Action triggers immediately:

1. **Syntax Validation**: Checks the TOML formatting using Python `tomllib` to prevent mobile typos from publishing corrupted data.
2. **JSON Auto-Generation**: Automatically generates `nerdkit-main-config.json` alongside the TOML file.
3. **Instant Cloudflare R2 Deployment**: Uploads both `nerdkit-main-config.toml` and `nerdkit-main-config.json` directly to your Cloudflare R2 bucket:
   * **Bucket**: `nerdkit`
   * **Folder**: `config-cfg/`

---

## Required One-Time GitHub Secrets Setup

To allow GitHub Actions to upload to your Cloudflare R2 bucket, add the following 3 repository secrets at:  
👉 **Settings** $\rightarrow$ **Secrets and variables** $\rightarrow$ **Actions** $\rightarrow$ **New repository secret**:

| Secret Name | Where to find in Cloudflare |
| :--- | :--- |
| `CLOUDFLARE_ACCOUNT_ID` | In your Cloudflare dashboard URL or on the right side of the main Account overview page. |
| `R2_ACCESS_KEY_ID` | Cloudflare Dashboard $\rightarrow$ **R2** $\rightarrow$ **Manage R2 API Tokens** $\rightarrow$ **Create API Token** (Permissions: *Object Read & Write* on bucket `nerdkit`). |
| `R2_SECRET_ACCESS_KEY` | Displayed when the R2 API token is created. |

---

## Mobile Editing (How to change settings while traveling)

1. Open the **GitHub Mobile App** on your phone (or browse to [github.com/GistSwoonie/NerdKit-Config](https://github.com/GistSwoonie/NerdKit-Config)).
2. Tap `nerdkit-main-config.toml`.
3. Tap the **Pencil icon (Edit)**.
4. Make your desired adjustments:
   * To disable a screen: set it to `false` (e.g. `quantum_compass = false`).
   * To enable a screen: set it to `true`.
   * To edit promotion text: modify the string inside quotes `"..."`.
5. Tap **Commit changes...**.
6. The GitHub Action runs immediately (~10 seconds) and publishes the changes to your Cloudflare R2 bucket.
