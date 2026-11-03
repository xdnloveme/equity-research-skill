# Contributing

Contributions that improve research quality, installation compatibility or documentation are welcome. Issues and pull requests may be written in English or Chinese; maintain the skill and reference files in English and keep both READMEs aligned when their content changes.

## Report a problem

[Open an issue](https://github.com/xdnloveme/equity-research-skill/issues) with the request, expected behavior and actual result. For research problems, include the agent/model, skill version or commit, information cutoff and a short relevant excerpt. For installation problems, include the operating system, command and error. Share only material you have permission to publish, with private information and credentials removed.

## Propose a change

Fork the repository, make a focused change on a branch, and open a pull request explaining the problem, the change and how you checked it. Small corrections can go straight to a PR; discuss substantial changes to the research approach in an issue first.

Follow the existing ownership in [SKILL.md](SKILL.md): references define the analysis requirements, the template captures their outputs, and the README explains setup and use. Refine the relevant source rather than repeat requirements across files. Preserve the 17-module and eight-capability coverage and keep the framework reusable; company facts, fixed valuation parameters and desired ratings belong outside its instructions.

## Check your work

- For documentation changes, check links, commands and relevant English/Chinese consistency. A full research run is unnecessary for copy-only edits.
- For installation changes, try the affected path in a temporary directory without replacing an existing personal installation.
- For research behavior changes, use a fresh conversation without earlier reports or ratings and inspect the affected report and workings against the existing acceptance checks in SKILL.md. Report the request, model, evidence cutoff, results and remaining limitations. A different target price alone does not prove improvement or regression.
- Run `git diff --check` and review the files being committed. Keep generated reports, downloaded source documents, temporary files and credentials out of the PR. The ignore file is a convenience, not a substitute for reviewing the diff.

## License

Contributions are submitted under the repository's [MIT License](LICENSE). Include only content you have the right to contribute; third-party materials retain their own terms.
