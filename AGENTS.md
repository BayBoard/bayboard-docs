# BayBoard help documentation

This is a public Mintlify help site. Treat every change as customer-facing
publication material. See [README.md](README.md) for the local preview,
validation, writing, and screenshot conventions.

## Public-safe content

- Do not add internal host paths, private identifiers, employee or customer
  information, private repository content, or non-public operating details.
- Do not open, copy, or publish environment files, credentials, or tokens.
- Describe only customer-visible behavior that is released now. Verify a new
  feature claim against an approved current source. If that source is not
  available, ask for the smallest confirmation needed rather than guessing.
- Screenshots must be real captures of the app with fictional or demo data.
  Do not create product UI imagery or publish identifiable information.

## Change and publication boundary

- A wording correction supported by the current app may be edited and checked.
- Treat a new or changed feature claim as unverified until its current release
  status is confirmed.
- Work on a branch and open a pull request. Never commit or push directly to
  `main`. Stop at PR-ready unless the repository owner explicitly approves
  merging or publishing; a delegated editing task is not that approval.
- Use `mint validate` and `mint broken-links` for documentation changes.
  A pull request may provide a preview. Merging `main` publishes the help site
  and requires explicit authorization.
