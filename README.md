# 🧳 Asset Packer Action

This GitHub Action runs a Windows-based asset packer (`asset_packer.exe`) to generate `.pak` files from a given folder and config file. It’s useful for packaging assets in projects like game mods or custom content.

## 📦 Features

- 💼 Packs any directory into a `.pak` file using a simple `.exe`
- ✅ Easy to reuse across multiple repositories
- 🪟 Runs on `windows-latest`

---

## ⚠️ Legal Notice

> **The `asset_packer.exe` tool is the property of [Chucklefish](https://www.chucklefish.org/) and is part of the official Starbound modding tools.**  
> This GitHub Action does not modify or claim ownership of this executable — it is simply included here for convenience and automation in asset packaging workflows.  
> Please ensure you comply with the Starbound EULA and modding terms when using this tool.

---

## 🚀 Usage

### Example workflow

```yaml
jobs:
  build:
    runs-on: windows-latest
    steps:
      - name: Checkout repository
        uses: actions/checkout@v2

      - name: Run Asset Packer
        uses: KrashV/asset-packer-action@v1
        with:
          input: .
          config: .github/tools/packing.config
          output: StarCustomChat.pak
