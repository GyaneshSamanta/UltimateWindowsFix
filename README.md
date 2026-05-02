<div align="center">
  <img src="docs/assets/navlogo.png" height="120" />

# UltimateWindowsFix

**A personal Windows toolkit — fork of [ChrisTitusTech/winutil](https://github.com/ChrisTitusTech/winutil) for debloating, configuring, and fixing common Windows issues.**

[![Upstream](https://img.shields.io/badge/fork%20of-ChrisTitusTech%2Fwinutil-blue.svg)](https://github.com/ChrisTitusTech/winutil)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Made for Windows](https://img.shields.io/badge/Windows-10%20%7C%2011-0078d4.svg)](#)

<img src="docs/assets/images/Screen.png" width="80%" />

</div>

---

## About

> **This is a personal fork.** It is not a separate product. All the heavy engineering belongs to [Chris Titus and the upstream winutil contributors](https://github.com/ChrisTitusTech/winutil/graphs/contributors).

|        |                                                                                                  |
| ------ | ------------------------------------------------------------------------------------------------ |
| Who    | Maintained by [Gyanesh Samanta](https://github.com/GyaneshSamanta) as a personal toolkit.        |
| What   | A PowerShell-driven utility that bundles install, tweak, fix, and updates panels for Windows.    |
| When   | Forked off ChrisTitusTech/winutil — pulled in for personal use across reformats and fresh setups. |
| Where  | Runs locally on any Windows 10 / 11 box; one-liner via `irm` + `iex` in an admin PowerShell.     |
| Why    | I rebuild Windows machines often. This is the script I trust to make a fresh box mine in 5 min.   |

## The Story

Every Windows reformat used to be a half-day ritual — uninstalling Candy Crush, hunting checkbox tweaks across five Settings pages, copy-pasting `winget install` lines from old gists. The first time I ran ChrisTitusTech/winutil end-to-end and watched it batch-install my whole stack, kill telemetry, and surface MicroWin in one window, the ritual collapsed into a coffee break.

I forked it for two reasons. First, **pinning** — I wanted a known-good snapshot I could run during a reformat without depending on whatever upstream main happens to be that day. Second, **personalization** — preset selections and tweaks tuned to how I actually use my machines. The fork stays close to upstream; this isn't a rewrite, it's a bookmark with a few sticky notes.

If you're not me, **use upstream**. It's better maintained, better documented, and gets new features first.

## Gallery

<div align="center">
  <img src="docs/assets/images/Install-Tab-Dark.png" width="45%" />
  <img src="docs/assets/images/Tweaks-Tab-Dark.png" width="45%" />
  <br />
  <img src="docs/assets/images/Microwin-Dark.png" width="45%" />
  <img src="docs/assets/images/MicroWinScreen.png" width="45%" />
</div>

---

## Tech Stack

- **PowerShell 5.1+** — primary scripting surface.
- **WPF / XAML** — the UI defined under `xaml/`.
- **winget / Chocolatey** — package backends invoked under the hood.
- **Pester** — test harness in `pester/`.
- Build: `Compile.ps1` stitches `functions/`, `xaml/`, and `config/` into a single distributable script.

## Repo Structure

```
UltimateWindowsFix/
├── Compile.ps1     # Build script that produces the single-file release
├── config/         # JSON: app lists, tweak definitions, preset bundles
├── functions/      # PowerShell functions (private + public + event handlers)
├── xaml/           # WPF UI markup
├── scripts/        # Helper scripts (start, main entry)
├── overrides/      # Local overrides patched in during compile
├── pester/         # Test specs
├── lint/           # Linting helpers
├── docs/           # Documentation site assets (mirrors upstream)
└── releases/       # Compiled output
```

## Getting Started

The fastest path (admin PowerShell):

```powershell
irm "https://raw.githubusercontent.com/GyaneshSamanta/UltimateWindowsFix/main/winutil.ps1" | iex
```

Or build from source:

```powershell
git clone https://github.com/GyaneshSamanta/UltimateWindowsFix.git
cd UltimateWindowsFix
.\Compile.ps1
.\winutil.ps1
```

For full feature documentation, screenshots of every tab, and the development guide, see **[upstream docs](https://christitustech.github.io/winutil/)** — this fork inherits its behavior.

## Contributing

Please contribute upstream: [ChrisTitusTech/winutil](https://github.com/ChrisTitusTech/winutil). Issues filed on this fork will generally be redirected there unless they relate to a fork-specific change.

## License

[MIT](LICENSE) — inherited from upstream.

## Credits

- **Upstream:** [Chris Titus Tech](https://github.com/ChrisTitusTech) and every [winutil contributor](https://github.com/ChrisTitusTech/winutil/graphs/contributors).
- **Fork maintainer:** [Gyanesh Samanta](https://github.com/GyaneshSamanta).
