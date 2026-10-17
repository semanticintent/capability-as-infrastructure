# Releasing a new version

Zenodo builds each version record from the repo files at the release tag, from `.zenodo.json` (which takes precedence over `CITATION.cff`). Edits made by hand on zenodo.org apply to one version record only and do not carry forward.

Before tagging `vX.Y.Z`:

1. **`.zenodo.json`:** set `"version": "vX.Y.Z"`. If the abstract, keywords or related papers changed, update them here.
2. **`CITATION.cff`:** set `version` and `date-released`, and keep the title and abstract in step with `.zenodo.json` (this file drives GitHub's "Cite this repository").
3. Commit, then `gh release create vX.Y.Z`.
4. After Zenodo mints the version, check that `related_identifiers` came through:
   `curl -s https://zenodo.org/api/records/<new-id> | python3 -m json.tool | grep -A3 related_identifiers`

The concept DOI, **10.5281/zenodo.23438908**, never changes. The badge, `CITATION.cff` and the paper header always use it, never a version DOI.
