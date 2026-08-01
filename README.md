# marcinwalendowski/homebrew-tap

Homebrew formulae and casks for my projects.

```bash
brew tap marcinwalendowski/tap
```

## Email Local MCP

Connect every email account to your AI agent over IMAP/SMTP, locally.
Source: [MarcinWalendowski/email-local-mcp](https://github.com/MarcinWalendowski/email-local-mcp)

```bash
brew install email-local-mcp          # the CLI and MCP server
brew install --cask email-local-mcp   # the macOS menu-bar app
```

`brew install` with no flag resolves to the **formula**, so the app genuinely
needs `--cask`. Installing both is fine.

After the formula, register the server and add a mailbox:

```bash
claude mcp add email-local -- email-local-mcp
email-local-mcp add you@example.com --default
```

The cask does not remove the Gatekeeper step: the app is ad-hoc signed and not
notarized, so the first launch needs **Open Anyway** in System Settings >
Privacy & Security.

## Why a tap and not homebrew-core

homebrew-core does not take node CLIs without established usage, and
homebrew-cask requires apps signed and notarized by an identified developer.
Neither is true here yet.

## Do not edit these files here

They are generated. The source of truth is `packaging/homebrew/` in the
[upstream repo](https://github.com/MarcinWalendowski/email-local-mcp/tree/main/packaging/homebrew),
stamped by `scripts/brew-sync.sh`, which reads every checksum from the
published artifact rather than from a keyboard. Editing a copy here is how the
two drift.
