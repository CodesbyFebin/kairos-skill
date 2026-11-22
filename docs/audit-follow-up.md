# Independent audit follow-up (proposal, not maintainer approval)

This document tracks potential follow-up work from the independent repository audit. It does not represent an upstream roadmap, accepted findings, or approval to merge.

## Included in this preparation branch

- GitHub Actions workflow running offline Python unittest discovery on pushes and pull requests.
- Contributor guidance for scoped changes and offline validation.
- A maintainer-facing checklist of questions before further changes.

## Pending maintainer decisions

1. **Base URL policy:** The documented `KAIROS_BASE_URL` excludes `/v1`. Should callers reject that suffix explicitly, or should the curl example and integrations strip it? The observed issue is duplicate path construction, not a verified live HTTP failure.
2. **Release policy:** Should update checks continue to track `main`, or should a tagged/pinned release channel be introduced? No release mechanism is changed here.
3. **Security reporting:** Which private channel should be documented? Do not invent a contact address.
4. **Untrusted input:** Confirm preferred guidance for treating `news_text` as untrusted data rather than instructions. No exploit is claimed.
5. **Example fixture:** Ask permission before changing the owner-supplied news template.
6. **Contract-validation tests:** Confirm expected response answer IDs, optional metadata, numeric tolerances, and distribution-sum handling before merging new validators.
7. **Branch cleanup:** Obtain owner approval before deleting or merging divergent branches.

## Review and validation

Run `python3 -m unittest discover -s tests -p 'test_*.py' -v`. CI requires no secrets and performs no live API calls. Maintainers must configure any required branch-protection check separately.
