You are picking up a project inside our organisation. Everything below was agreed
before any code was written. Treat it as the brief, not as suggestions.

## The project

**Harbour berth booking** — a web app

Beta dogfood: berth bookings for a small marina. Created by aiG8way launchpad end-to-end test on 2026-09-21.

- Started as: a new project
- Ships a model at runtime: no
- Security level: Standard · GDPR

## Where the code lives

Nothing has been created yet — the intended repository is `nxg8w-dogfood/harbour-berth-booking`.
Do not create it yourself; confirm first. Everything you need is in this brief.

## Guardrails — not negotiable

- **README with run instructions** — Every repository opens with a README that states what the project is, how to run it locally, and how to deploy it. A newcomer should be productive without asking anyone.
- **Automated tests run on every pull request** — A test suite exists and CI blocks a merge when it fails. Coverage targets are per-project; the non-negotiable part is that the suite runs unattended.
- **Protected default branch** — No direct pushes to the default branch. Changes land through a pull request with at least one review.
- **CI builds the project from a clean checkout** — The pipeline installs, lints, tests and builds from scratch. "Works on my machine" is not a build.
- **Deployment is automated per environment** — Deploys are triggered from the pipeline, not from a laptop, and each environment has its own configuration.
- **No secrets in source control** — Secrets live in Key Vault or environment configuration. The repository is scanned for committed credentials and the scan blocks the merge.
- **Dependency and vulnerability scanning** — Dependencies are scanned on a schedule, and known-vulnerable versions are patched inside the agreed window.
- **Authorisation checked server-side** — Permissions are enforced in the backend. Hiding a button in the UI is presentation, never protection.
- **License and ownership declared** — The repository states its licence and the owning team, so it is clear who maintains it and on what terms it may be reused.

If one of these cannot be met, say so and stop. It gets waived on the project, with a
reason, by a person. It does not get worked around in the code.

## Security controls that apply

Profile: Internal · Personal data · Open internet · Entra ID

- **Secrets in Key Vault, never in the repository** — Connection strings, keys and certificates live in Key Vault or environment configuration, injected at deploy time. The repository is scanned and the scan blocks the merge.
- **TLS 1.2 or better on every hop** — No plaintext anywhere, including between internal services. HTTP redirects to HTTPS and HSTS is set.
- **Authorisation enforced on the server** — Every request re-checks what the caller is allowed to do. Hiding a button in the UI is presentation, never protection.
- **Dependencies patched inside the agreed window** — Automated scanning on a schedule, with known-vulnerable versions upgraded before the window closes.

Each of these applies because of an answer someone gave about this project's data and
exposure. They are not a checklist to negotiate down.

## How we work here

- **Code review checklist** — The org playbook for reviewing a pull request: correctness first, then simplification, then style. Keeps reviews consistent between teams.
- **itm8 brand and design system** — Applies the NEXUS visual identity — Powerful Purple, Miriam Libre headlines, Fira Sans body — to anything user-facing.

## Who is responsible

- **Product owner** — Owns the problem and the priorities. Decides what ships and what waits, and is the single point of escalation for scope.
- **Tech lead** — Owns the technical direction and the definition of done. Makes the call when the team is split on an approach.

## Definition of done

- Lead time for changes — How long a commit takes to reach production. The clearest single signal of whether the delivery pipeline is healthy.
- Deployment frequency — How often the project ships. Rising frequency with a flat failure rate is the shape you want.

Beyond the metrics: every guardrail above is satisfied or explicitly waived, the tests
pass, and a newcomer can run the project from the README without asking anyone.

## Open questions — do not guess these

- _None. The record is complete._

Where this brief is silent, ask. A guess that looks like a decision is worse than a
question, because nobody can tell them apart afterwards.
