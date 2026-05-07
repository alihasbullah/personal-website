# Instructions for Claude Code

This file gives you context for working in this repository. Read `PROJECT.md` for fuller project background.

## Quick Context

This is a personal website built with Hugo + PaperMod theme, deployed on Cloudflare Pages. Bilingual (Bahasa Indonesia default, English secondary). Owner: Ali Hasbullah.

## Working Style Preferences

- **Be concise.** Skip unnecessary preamble. Get to the point.
- **Show your reasoning briefly.** When making non-obvious decisions, explain why in 1-2 sentences—not paragraphs.
- **Ask before large refactors.** For multi-file changes affecting structure, propose first then execute after confirmation.
- **One concern per commit.** Don't bundle unrelated changes.
- **Respect existing conventions.** If the codebase uses a pattern, continue it. Don't introduce new patterns without discussion.

## Hard Rules

- **Never modify files inside `themes/PaperMod/`.** It's a Git submodule. To override theme behavior, create files in root-level `layouts/` instead.
- **Never commit content with `draft: true`.** Cloudflare build will skip them, but they shouldn't be in version control either.
- **Never run `hugo --cleanDestinationDir`.** Cleanup happens automatically; this flag has caused issues in the past.
- **Never bypass the bilingual structure.** Every primary page should consider whether it needs both `.md` and `.en.md` versions.
- **No new dependencies without discussion.** No npm packages, no Hugo modules, no external libraries unless we agree first.

## Common Tasks Reference

### Add a new blog post (Indonesian)

```bash
hugo new content content/posts/judul-artikel.md
```

Edit file, set `draft: false`, write content, commit, push.

### Add English version of existing post

```bash
hugo new content content/posts/article-title.en.md
```

### Preview locally

```bash
hugo server
```

Available at `http://localhost:1313`. Use `--buildDrafts` flag to include drafts.

### Production build (rarely needed locally; Cloudflare handles this)

```bash
hugo
```

Output goes to `public/` (gitignored).

## File Naming Convention

- Indonesian content: `nama-file.md` (no language suffix)
- English content: `name-file.en.md`
- Use kebab-case (lowercase, hyphens), not snake_case or camelCase

## Frontmatter Template

```yaml
---
title: "Judul Artikel"
date: 2026-05-07
draft: false
tags: ["tag1", "tag2"]
categories: ["kategori"]
summary: "Ringkasan singkat untuk listing dan SEO."
---
```

## When Suggesting Changes to `hugo.toml`

The config is significant and bilingual setup is non-obvious. Before modifying:

1. Explain what change you're proposing and why
2. Show the diff
3. Wait for confirmation before applying
4. Test by mentally walking through what `hugo server` would output

## Git Commit Message Format

Use imperative mood, English, focused on the **what** and **why**:

- ✅ `Add article on Pascal nostalgia`
- ✅ `Fix language switcher misalignment on mobile`
- ✅ `Update PaperMod to latest version`
- ❌ `updated stuff`
- ❌ `Added a new article about my thoughts on Pascal which I used a lot back in college`

## When in Doubt

Default to: minimal change, ask before assuming, prefer reading existing code over generating new.