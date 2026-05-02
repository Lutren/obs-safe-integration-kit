# QA Results

Date: 2026-05-02

Scope: local source package only. No external publication, push, deploy, browser action or account action was performed.

## Commands

| check | command | result |
|---|---|---|
| tests | `PYTHONDONTWRITEBYTECODE=1 python -m pytest -q -p no:cacheprovider` | `4 passed in 0.11s` |
| compile | `python -c "import pathlib, py_compile, tempfile; ..."` | `py_compile ok` |
| CLI smoke | `python -c "from obs_safe_integration_kit ... main(['--help'])"` | import OK, gate returned `HUMAN_REVIEW`, CLI help rendered |
| package secret scan | `python tools\release\scan_secrets.py --path packages\open-dev\obs-safe-integration-kit --json` | `count_reported=0` |
| package path scrub | focused local/private path denylist over `packages\open-dev\obs-safe-integration-kit` | no matches |
| JSON ficha | `python -m json.tool docs\product\agent_product_fichas_2026-05-02.json` | `json ok` |
| cache check | search for `.pytest_cache` and `__pycache__` under package | no matches |

## Claim Scan Note

Claim keywords appear only in negative boundary language:

- `README.md` says the kit does not prove new physics.
- `CLAIMS.md` blocks guaranteed safety, autonomous public execution, consciousness, cosmology, medical diagnosis and cognitive diagnosis claims.
- `RELEASE_CHECKLIST.md` requires the same claim review before external release.

This is acceptable for local source promotion. External publication remains blocked until a destination-specific ActionGate passes.
