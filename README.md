# .github

Default [community health files](https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/creating-a-default-community-health-file) for [@aryaemami59](https://github.com/aryaemami59)'s repositories.

GitHub falls back to the files in this repository for any of my repositories that does not provide its own copy. Nothing here needs to be duplicated per project.

---

## What's here

| File                                                                     | Purpose                                                                                                                                              |
| ------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| [`.github/CODE_OF_CONDUCT.md`](./.github/CODE_OF_CONDUCT.md)             | [Contributor Covenant 3.0](https://www.contributor-covenant.org/version/3/0/), reproduced verbatim apart from the reporting and enforcement sections |
| [`.github/CONTRIBUTING.md`](./.github/CONTRIBUTING.md)                   | How to file issues and open pull requests                                                                                                            |
| [`.github/GOVERNANCE.md`](./.github/GOVERNANCE.md)                       | Who decides what, and how                                                                                                                            |
| [`.github/SECURITY.md`](./.github/SECURITY.md)                           | How to report a vulnerability                                                                                                                        |
| [`.github/SUPPORT.md`](./.github/SUPPORT.md)                             | Where to get help                                                                                                                                    |
| [`.github/FUNDING.yml`](./.github/FUNDING.yml)                           | Sponsor button                                                                                                                                       |
| [`.github/ISSUE_TEMPLATE/`](./.github/ISSUE_TEMPLATE)                    | Bug report and feature request templates, plus the chooser config                                                                                    |
| [`.github/pull_request_template.md`](./.github/pull_request_template.md) | Default pull request body                                                                                                                            |
| [`.github/DISCUSSION_TEMPLATE/`](./.github/DISCUSSION_TEMPLATE)          | Discussion category forms                                                                                                                            |

---

## Things worth remembering

**Keep every file repository-agnostic.** These files are read in the context of _other_ repositories, so anything project-specific is wrong by definition. Never name a particular repository, and never hardcode a link to one project's issue tracker. Prefer "this repository" over a concrete URL. This is not hypothetical - [`CONTRIBUTING.md`](./.github/CONTRIBUTING.md) once shipped a `git clone` line pointing at an unrelated project, and every repository inheriting it told contributors to clone the wrong thing.

**A repository's own file always wins.** GitHub looks in the consuming repository first ([`.github/`](./.github/), then the root, then `docs/`), and only falls back here if it finds nothing.

**Issue templates are all-or-nothing.** If a repository has _any_ file in its own [`.github/ISSUE_TEMPLATE/`](./.github/ISSUE_TEMPLATE/), none of the defaults here apply to it - not even the ones it lacks.

**Templates only work on the default branch.** Issue and pull request templates are read from this repository's default branch. On any other branch they are simply unavailable, so a change to a template does nothing until it lands on `main`.

**The pull request template must be a file, not a directory.** [`.github/pull_request_template.md`](./.github/pull_request_template.md) auto-populates the pull request body. Templates inside a `PULL_REQUEST_TEMPLATE/` directory are the multi-template form, reachable only through a `?template=` query parameter - and unlike issues, pull requests get no template chooser, so nothing in GitHub's UI ever offers them. In a defaults repository they are worse than useless: the `?template=` URL differs per inheriting repository, so it cannot be published from here without naming one. Filenames are case-insensitive and may be `.md` or `.txt`, so casing is never the problem - file versus directory is.

**Discussion form filenames must match category slugs.** [`.github/DISCUSSION_TEMPLATE/q-a.yml`](./.github/DISCUSSION_TEMPLATE/q-a.yml) applies to the category whose slug is `q-a`. A filename that matches no category is simply ignored.

**A license cannot be inherited.** GitHub does not support default license files. The [`LICENSE`](./LICENSE) here covers this repository's own contents only; every other repository needs its own.

**This repository must stay public** for any of the above to apply.

---

## License

The contents of this repository are [MIT licensed](./LICENSE), except [`.github/CODE_OF_CONDUCT.md`](./.github/CODE_OF_CONDUCT.md), which is adapted from the Contributor Covenant and distributed under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/).
