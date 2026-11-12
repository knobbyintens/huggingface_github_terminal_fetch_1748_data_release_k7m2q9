# License Clearance Policy

Every curated release bundles two upstream components: a **source corpus** (a
public dataset) and a **generator model** (an open model used for synthesis).
Before a release can ship, the license of *both* components must be resolved
from their public dataset/model cards.

## License tiers

Classify each individual component license into one of four tiers:

| Tier | Licenses |
| --- | --- |
| PERMISSIVE | `apache-2.0`, `mit`, `bsd-2-clause`, `bsd-3-clause`, `odc-by`, `cc0-1.0`, `cc-by-4.0` |
| SHAREALIKE | `cc-by-sa-3.0`, `cc-by-sa-4.0` |
| NONCOMMERCIAL | `cc-by-nc-4.0`, `cc-by-nc-sa-4.0` |
| REVIEW | any other value, including `other`, `llama3.1`, `gemma`, `openrail`, or a missing/unknown license |

## Release decision

The release-level decision combines both component tiers using the highest
priority tier, in this order:

1. NONCOMMERCIAL component -> `BLOCKED`
2. REVIEW component -> `ESCALATED`
3. SHAREALIKE component -> `SHAREALIKE`
4. otherwise -> `CLEARED`

## Required actions

- `CLEARED` and `SHAREALIKE` releases: add an entry to
  `compliance/THIRD_PARTY_LICENSES.md` that contains the release ID, the derived
  dataset name, the source corpus license, and the generator model license. A
  `SHAREALIKE` entry must also state that redistribution must remain under the
  same share-alike license.
- `BLOCKED` releases: must not be published. Create
  `compliance/blocks/<release_id>.md` stating that publication is blocked
  because of a non-commercial component license.
- `ESCALATED` releases: open a separate issue titled
  `License review escalation - <release_id>` for legal review before publication.
- Always post a summary comment on the audit request issue that lists every
  release ID with its final decision.
- Close the audit request issue only when no release is `BLOCKED` and no release
  is `ESCALATED`.
