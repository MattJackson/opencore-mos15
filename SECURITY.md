# Security Policy

## Scope

This repository is a small fork-local overlay carrying **System KC loading
and cross-KC dependency resolution** patches against
[acidanthera/OpenCorePkg](https://github.com/acidanthera/OpenCorePkg).
The security policy below covers **only** the code and documentation in
this repository — that is, the overlay files under `Include/`, `Library/`,
and `Utilities/`, plus the staged submission package under `upstream-pr/`.

### Where to report what

- **Vulnerabilities in upstream OpenCore** — anything in code paths that
  exist unchanged in `acidanthera/OpenCorePkg` — should be reported to the
  upstream project directly, following their disclosure process at
  <https://github.com/acidanthera/OpenCorePkg>. Please do not file upstream
  issues here; they will be closed and redirected.
- **Vulnerabilities in the System KC loading patches specifically** —
  anything introduced by the overlay in this repository (for example
  memory-safety issues in `PrelinkedContextLoadSystemKC ()` or in the
  System-KC `LC_FILESET_ENTRY` walk) — should be reported here.

## Supported versions

Only the tip of `main` is supported. Tagged snapshots (for example the
`0.5.0` research snapshot) are not receiving security updates; they exist
as historical markers of the submission state.

| Version | Supported |
|---|---|
| `main` | yes |
| `0.5.x` | no — snapshot only |
| older | no |

## Reporting a vulnerability

Please file a private report through GitHub Security Advisories:

<https://github.com/MattJackson/mos-opencore/security/advisories/new>

Do **not** open a public issue for a suspected vulnerability.

When filing, include:

- A concise description of the issue and the component it affects (file,
  function, and patch number in `upstream-pr/patches/` if applicable).
- Reproduction steps — ideally a minimal OpenCore configuration and the
  staged `SystemKernelExtensions.kc` characteristics needed to trigger
  the behaviour.
- The OpenCore branch, commit, and build flags used.
- Any known impact assessment (local denial of service, memory disclosure,
  code execution, and so on).

## Response expectations

This is a small fork maintained on a best-effort basis. Expected
turnaround:

- Acknowledgement of receipt: within one week.
- Initial assessment: within two weeks.
- Fix or published mitigation: depends on severity and complexity; a
  reasonable target is 30 to 60 days from triage for high-severity
  findings.

If a vulnerability turns out to affect upstream OpenCore as well, we will
coordinate disclosure with acidanthera before any public release and
defer to their timeline.

## Disclosure

Once a fix is merged, the advisory will be published on GitHub and a
corresponding entry will be added to `CHANGELOG.md`. Credit will be given
to reporters who wish to be named.
