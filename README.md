# Real World Rails

> Real World Rails applications and their open source codebases for developers to learn from

This is an actively maintained continuation of [eliotsykes/real-world-rails](https://github.com/eliotsykes/real-world-rails).

This project brings 200+ active, open source Rails apps and engines together in one repository. Having real production codebases aggregated in a single place has always been valuable for learning — but it's become dramatically more useful in the age of AI coding agents.

See [repos.md](repos.md) for the full list of included apps and engines with descriptions.

## Why this matters now

When this repo was created, you had to manually grep through code or use custom Ruby scripts to find patterns across apps. AI coding agents have changed that completely.

With all these codebases in one directory, you can point an agent at 200+ production Rails apps and ask questions like:

- "How do these apps implement background job retry logic?"
- "Show me every approach to multi-tenancy across these codebases"
- "What patterns do apps use for PDF generation?"
- "Find all the different ways these apps handle soft deletes"
- "Compare authentication implementations across apps using Devise vs. custom auth"

An agent can search, read, and cross-reference code across every app instantly — something that would have taken hours of manual work before. This makes real-world-rails one of the most practical resources for researching how production Rails apps actually solve problems.

### Storing your analyses

The `analyses/` directory is git-ignored — a safe place to store your own research:

- Markdown files, notes, pattern comparisons, or any documentation
- Won't be committed or show up in pull requests
- Keeps your workspace clean while working alongside the codebases

## Getting started

> [!NOTE]
> Running `bin/setup` clones all 200+ repositories as git submodules. This will use approximately **10 GB** of disk space. Use `bin/setup --full` for complete git history (~29 GB).

Ensure you have git-lfs installed: https://git-lfs.com

```bash
git clone git@github.com:steveclarke/real-world-rails.git
cd real-world-rails/
bin/setup
```

## Staying up to date

Submodules are updated automatically via a GitHub Action that runs weekly and opens a PR. Once merged, you just need to pull:

```bash
git pull
git submodule update
```

If you want to update all submodules to the absolute latest right now (without waiting for the weekly action), run `bin/update`.

## Scripts

- **`bin/setup`** — Initialize and download all submodules with shallow clone (run after first clone)
  - `--full` — Clone with complete git history (~29 GB instead of ~10 GB)
  - `--reset` — Re-download all submodules (use with default or `--full` to switch modes)
- **`bin/update`** — Pull latest changes and update all submodules to their latest remote commits
- **`bin/status`** — Show how many apps are initialized
- **`bin/add`** — Add a new app or engine by GitHub URL (e.g. `bin/add https://github.com/user/repo`)
- **`bin/verify`** — Check that each submodule repo still exists on GitHub and hasn't been moved or renamed (requires `gh` CLI)

## Contributing

Know of a great open source Rails app that should be in here? The easiest way is to [open an issue](https://github.com/steveclarke/real-world-rails/issues/new) with the GitHub URL and we'll add it.

If you already have the repo cloned, you can also submit a PR:

```bash
bin/add https://github.com/githubuser/foo
# then commit and open a pull request
```

#### Criteria for adding apps

Apps should:
- Be open source and publicly available on GitHub
- Be built with Ruby on Rails
- Be actively maintained or represent quality code worth studying
- Be real-world applications (not just demos or tutorials)

## Agent Skill

This repo includes a `/real-world-rails` skill for AI coding agents. It teaches your agent to search across all 200+ codebases to research how production apps solve architectural problems.

Install it with:

```bash
npx skills add steveclarke/real-world-rails
```

Then ask your agent things like "how do Rails apps handle multi-tenancy?" or "research background job patterns across real world rails apps" and it will search the actual source code.

## Other Real World Codebase Collections

- [Real World Nuxt](https://github.com/steveclarke/real-world-nuxt)
- [Real World Ruby Apps](https://github.com/jeromedalbert/real-world-ruby-apps)
- [Real World Sinatra](https://github.com/jeromedalbert/real-world-sinatra)
- [Real World Django](https://github.com/ckrybus/real-world-django)
