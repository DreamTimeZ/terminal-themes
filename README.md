# Terminal Themes Collection

Two high-performance terminal themes with identical aesthetics: **Oh My Posh** and **Starship**.

## Preview

![Preview](preview.png)

## Quick Start

### 1. Install Theme Engine

**Oh My Posh:**
```PowerShell
winget install --id=JanDeDobbeleer.OhMyPosh -s winget -e --interactive
```

**Starship (alternative):**
```PowerShell
winget install --id=Starship.Starship -e --interactive
```

### 2. Install Nerd Font

Download [CascadiaCode Nerd Font](https://github.com/ryanoasis/nerd-fonts/releases) and configure:
- **Windows Terminal:** Settings → Defaults → Appearance → Font face → "CaskaydiaCove Nerd Font Mono"
- **VS Code:** Settings → Terminal → Integrated: Font Family → "CaskaydiaCove Nerd Font Mono"

### 3. Configure PowerShell Profile

Add to `$PROFILE`:

```PowerShell
# Oh My Posh - Prompt theme engine
#oh-my-posh init pwsh --config "$([Environment]::GetFolderPath('MyDocuments'))\TerminalThemes\oh-my-posh-theme.json" | Invoke-Expression

# Starship - Alternative prompt theme (comment out oh-my-posh above and uncomment below to use)
$ENV:STARSHIP_CONFIG = "$([Environment]::GetFolderPath('MyDocuments'))\TerminalThemes\starship-theme.toml"
Invoke-Expression (&starship init powershell)
function Invoke-Starship-TransientFunction {
  &starship module character  # Show "λ" for previous commands
}
Enable-TransientPrompt  # Simplify previous prompts to save screen space
```

**To switch themes:** Comment/uncomment the respective sections and restart your terminal.

## Theme Comparison

| Feature | Oh My Posh | Starship |
|---------|-----------|----------|
| **Startup Time** | ~194ms (Windows PowerShell) | **~86ms (2.3x faster)** |
| **Core Info** | Status, time, shell, user@host, git, path, root, λ | ✓ Same + jobs indicator |

## Design Philosophy

**Color Scheme (One Dark):**
- 🔴 `#E06C75` — Errors, shell, root, prompt (λ)
- 🟡 `#E5C07B` — Username, hostname, jobs
- 🟠 `#F3C267` — Git branch
- 🔵 `#61AFEF` — Directory path
- 🟢 `#b8ff75` — Execution time

**Performance Optimizations:**
- Git status/stash/upstream fetching disabled
- Execution time threshold: 2s
- Aggressive caching (oh-my-posh) / file-based detection (starship)
- Plain style (no powerline separators)

**Common Features:**
- Exit code display (✗ + code)
- Execution time (>2s)
- Git branch (20 char max)
- Admin indicator (!)
- Lambda (λ) prompt symbol
- Transient prompt support

## Recommendations

- **Choose Starship if:** You want the best performance (2.3x faster startup), more features, and context-aware info
- **Choose Oh My Posh if:** You prefer built-in transient prompt support or have specific oh-my-posh requirements

**Note:** Starship significantly outperforms Oh My Posh (86ms vs 194ms theme initialization on Windows PowerShell) while providing more features. Both themes share identical visual appearance with the One Dark color scheme.

## Updating

```PowerShell
# Oh My Posh
winget upgrade --id=JanDeDobbeleer.OhMyPosh -e

# Starship
winget upgrade --id=Starship.Starship -e
```

## References

- [Oh My Posh Documentation](https://ohmyposh.dev/)
- [Starship Documentation](https://starship.rs/)
- [Nerd Fonts](https://www.nerdfonts.com/)
- Original inspiration: [emodipt-extend theme](https://github.com/JanDeDobbeleer/oh-my-posh/blob/main/themes/emodipt-extend.omp.json)