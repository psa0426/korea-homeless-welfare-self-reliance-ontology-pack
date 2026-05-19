# OpenCrab Ingest Configuration

## Required Settings
- branch: `main`
- path: `docs`
- document_limit: `200`
- scan_all_readable_documents: `ON`

## Recommended Sequence
1. Connect GitHub repo
2. Set branch/path as above
3. Run full scan
4. Build ontology pack from scanned docs
5. Review extracted entities/relations
6. Iterate docs in GitHub and rescan
