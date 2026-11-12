# Data Release Registry

Central registry for curated datasets published by the data curation group.

## Layout

- `catalog/manifests/` - one JSON manifest per planned release. Manifests are
  owned by the release curator and must not be edited during compliance work.
- `compliance/license_policy.md` - the license clearance policy that every release must follow.
- `compliance/THIRD_PARTY_LICENSES.md` - published third-party attribution notices, written
  during license audits.
- `compliance/blocks/` - publication block notices for releases that cannot ship.

## Release workflow

1. A curator files a release manifest.
2. Compliance audits the licenses of the upstream source corpus and generator
   model, then applies the actions required by the policy.
3. Only releases cleared by compliance may be published.

Repository: `knobbyintens/huggingface_github_terminal_fetch_1748_data_release_k7m2q9`
