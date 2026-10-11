# Install and use

You do not need to install anything to read the book: go to <https://agile-itil-metrics.github.io>, or read the Markdown in `locales/en-001/topics/` on GitHub.

## Read locally

```sh
git clone git@github.com:agile-itil-metrics/agile-itil-metrics.git
cd agile-itil-metrics
open README.md
```

## Run the checks

You need Python 3.

```sh
python3 -I bin/check --strict          # structure, template, and style rules
python3 -I bin/check --strict --links  # also resolves every Wikipedia link
python3 bin/check-locales              # every locale is complete
python3 bin/localize --check           # derived English locales are current
```

## Run the website

You need Node.js and pnpm.

```sh
cd agile-itil-metrics.github.io
pnpm install
./scripts/sync-content.sh   # copy content from the book
pnpm dev                    # http://localhost:5173
```

## Use the AI skills

Copy `skills/agile-itil-metrics-skill/` into your own Claude Code skills folder. The maintainer skill in `skills/agile-itil-metrics-maintainer-skill/` is for people editing this book.
