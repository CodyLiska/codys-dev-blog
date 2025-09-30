---
layout: post
title: "Falling Down the Dotfiles + Devcontainer Rabbit Hole"
date: 2025-09-30
tags: [dotfiles, devcontainers, vscode, macos, wsl]
excerpt_separator: <!--more-->
---

I didn’t plan on spending my evening building a complete cross-platform dev environment — but here we are.

It started with a simple frustration: switching between **macOS** and **Windows (via WSL)** for development. Both work fine individually, but the little differences — path quirks, shell defaults, git configs, VS Code behaving slightly differently — were creating a steady drip of friction. Every switch meant more mental overhead.

<!--more-->

## First Attempts

My first thought was: _“Can I just standardize around WSL on Windows?”_ That got me halfway there — a Linux environment on Windows smooths over some platform-specific rough edges. But I still had macOS in the mix, and I didn’t want to keep remembering what worked where.

I wanted **one setup, one mental model**.

That’s when the rabbit hole really opened.

## The Solution: Dotfiles + Devcontainers

The answer turned out to be a combination of two tools:

- **Dotfiles repo** → central home for `.zshrc`, `.bashrc`, `.gitconfig`, aliases, Starship prompt config, etc.
- **Devcontainers** → reproducible development environments defined in `devcontainer.json`, fully supported by VS Code.

By combining these, I now have:

- **Consistent shells** on both platforms (zsh on macOS, bash/zsh in WSL).
- **Shared git config & aliases** so I don’t forget shortcuts.
- **Starship prompt** for consistency and style (with optional Powerlevel10k if I want to go fancier).
- **Bootstrap script** to set up Homebrew (macOS) or apt (WSL), Starship, NVM, Python, etc.
- **Setup script** to symlink dotfiles in place.

And the cherry on top: a **VS Code devcontainer** that automatically applies the same environment (Python 3.11 + Node.js 20) with synced settings and recommended extensions.

## Repo Structure

```plaintext
dotfiles-devcontainer/
├── .gitignore
├── LICENSE
├── README.md
├── FIRST_RUN.md
├── dotfiles/
│   ├── .aliases
│   ├── .zshrc
│   ├── .bashrc
│   ├── .gitconfig
│   ├── bootstrap.sh
│   ├── setup.sh
│   └── .config/starship.toml
├── .devcontainer/
│   └── devcontainer.json
└── .vscode/
    ├── settings.json
    └── extensions.json
```

## First Run

To bootstrap a new machine:

```bash
./dotfiles/bootstrap.sh
./dotfiles/setup.sh
```

Then open the repo in VS Code — it applies the settings, suggests extensions, and asks if I want to reopen in the devcontainer. From there, I’m coding with **the same environment everywhere**.

## Reflections

What started as “I just want fewer workarounds between macOS and Windows” turned into a polished setup:

- Dotfiles that are clean, modular, and portable.
- Devcontainers that lock in my stack.
- A README + First Run guide so future-me doesn’t forget the steps.

This evening’s rabbit hole paid off. Next time I spin up a new machine, it won’t take me hours to remember how to configure things. It’ll be one `git clone` and a couple shell scripts.

And honestly? That feels like a win.
