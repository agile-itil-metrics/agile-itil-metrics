# Contributing to Agile ITIL Metrics

Thanks for helping improve this project.

## Ways to contribute

- **Report a problem:** open an issue describing what is wrong, unclear, or missing.
- **Fix or improve something:** open a pull request. Small fixes can go straight to a pull request; for larger changes, please open an issue first so we can agree on the approach.

## Layout

- `locales/<locale>/topics/<slug>/index.md`: one topic in one locale. The source text is `en-001`.
- `spec/`: the governing specification and manifest (`spec/topics.tsv`). Read `spec/index.md` before editing a topic.
- `agile-itil-metrics.github.io/`: the SvelteKit reading site.

## Checks

See [INSTALL.md](INSTALL.md). In short:

```sh
python3 -I bin/check --strict          # structure, template, and style rules
python3 -I bin/check --strict --links  # also resolves every Wikipedia link
python3 bin/check-locales              # every locale is complete
bin/build-readme                       # regenerate the README table of contents
bin/build-llms                         # regenerate llms.txt and llms.json
```

AI agents should also read [AGENTS.md](AGENTS.md).

## Code of conduct

Participation is governed by our [Code of Conduct](CODE_OF_CONDUCT.md).

## License

By contributing, you agree that your contribution is offered under the terms in [LICENSE.md](LICENSE.md).
