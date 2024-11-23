# Terminal Theme (with Oh My Posh)

## Preview

![Preview](preview.png)

## Install & Update Oh My Posh

- Install: `winget install JanDeDobbeleer.OhMyPosh -s winget`
- Update: `winget upgrade JanDeDobbeleer.OhMyPosh -s winget`

## Fonts

- Navigate to the Nerd Fonts GitHub repository, proceed to the "Releases" section, and select a font for downloading from the most recent release.
  - [Nerd Fonts](https://github.com/ryanoasis/nerd-fonts/releases)
- I use **CascadiaCode**
- Navigate to the right-pointing arrow next to the new tab icon in the terminal -> settings -> Defaults -> Appearance -> under "Font face," you can opt for "CaskaydiaCove Nerd Font Mono" if desired

### Note

- Please set the font in the VsCode terminal to 'CaskaydiaCove Nerd Font Mono' for all profiles to ensure that certain characters are not displayed incorrectly (any nerd font will do the job)

## Oh My Posh Custom Theme

Template which inspired me: [Github Link](https://github.com/JanDeDobbeleer/oh-my-posh/blob/main/themes/emodipt-extend.omp.json)

### Documentation

- `[{HEAD-name} S +A ~B -C !D | +E ~F -G !H W]`
- `≡` = The local branch in at the same commit level as the remote branch (BranchIdenticalStatus)
- `↑ <num>` = The local branch is ahead of the remote branch by the specified number of commits; a git push is required to update the remote branch (BranchAheadStatus)
- `↓ <num>` = The local branch is behind the remote branch by the specified number of commits; a git pull is required to update the local branch (BranchBehindStatus)

    `ABCD` represent the index; | (`DelimStatus`); `EFGH` represent the working directory
  
  - `+` = Added files
  - `?` = Not added files
  - `~` = Modified files
  - `!` = Conflicted files

  W represents the overall status of the working directory

  - `!` = There are unstaged changes in the working tree (`LocalWorkingStatusSymbol`)
  - `~` = There are uncommitted changes i.e. staged changes in the working tree waiting to be committed (`LocalStagedStatusSymbol`)
  - `None` = There are no unstaged or uncommitted changes to the working tree (`LocalDefaultStatusSymbol`)

#### Set The Theme

- `oh-my-posh init pwsh --config "$env:userprofile\Documents\TerminalThemes\oh-my-posh-theme.json" | Invoke-Expression`
- To ensure its persistence, append it to your profile file.

## Oh My Posh Default Themes

- `oh-my-posh init pwsh --config '$env:userprofile\emodipt-extend.omp.json' | Invoke-Expression`
