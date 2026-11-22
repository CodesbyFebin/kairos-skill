# Contributing to Kairos skill

Thanks for helping improve Kairos skill. Please discuss contract or release-policy changes with the maintainers before opening a pull request.

## Local checks

Python 3.10+ is recommended for development. Run the offline test suite from the repository root:

```bash
python3 -m unittest discover -s tests -p 'test_*.py' -v
```

The tests do not require a live Kairos API key. Do not include API keys, user data, or live market data in tests or issues.

## Pull requests

- Keep each change narrowly scoped and independently reviewable.
- Describe the observed behavior, reproduction steps, expected result, and checks performed.
- Distinguish offline fixture/contract tests from authorized live API tests.
- Do not change the owner-supplied `news-return.json` question, candidate IDs, or JSON escape conventions without maintainer approval.
- Coordinate API schema assumptions, response tolerances, release tags, and branch cleanup with maintainers first.

## Security reports

Please avoid posting credentials, sensitive user data, or exploit details in public issues. Contact the repository maintainers privately through an approved channel. A formal security reporting address or GitHub private vulnerability reporting workflow has not yet been confirmed.
