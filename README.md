# WinCC Unified Module Template

[![Repo](https://img.shields.io/badge/GitHub-wincc--unified--module--template-24292f?logo=github)](https://github.com/GepElectric/wincc-unified-module-template)
[![Release](https://img.shields.io/github/v/release/GepElectric/wincc-unified-module-template)](https://github.com/GepElectric/wincc-unified-module-template/releases)

This repository is a clean starting template for a new `WinCC Unified Companion` module.

It is structured so the same module can run:

- standalone
- as a hosted Companion module
- as a packaged `.exe` module for the host `modules/` folder

## Repository Contents

- `main.py`: hosted and standalone entrypoint
- `hosted_runtime.py`: minimal Companion runtime helper
- `example_module/app.py`: starter UI and business logic
- `module.json`: module manifest used by the host
- `build_module_exe.bat`: PyInstaller build script and package output flow
- `MODULE_TEMPLATE_MEMORY.md`: extra implementation notes

## Getting Started

1. Copy this folder to a new location for your module.
2. Rename the following placeholders:
   - `example_module`
   - `ExampleModule`
   - `example_module` inside `module.json`
3. Implement your UI and logic in `example_module/app.py`.
4. Run locally:

```powershell
python main.py
```

5. Build the packaged module:

```powershell
.\build_module_exe.bat
```

6. Install the result in the host:

```text
modules/<your_module_id>/
```

Or use the packaged ZIP from `dist/` with the host `Install Module` flow.

## Notes

- this repository is meant to stay clean and reusable as a base template
- build output folders are ignored by git
- line endings and editor behavior are already standardized for Windows-based development
