# OPENCRAB_INGEST_VALIDATION_REPORT (v0.1-r1)

- Repository: `https://github.com/psa0426/korea-homeless-welfare-self-reliance-ontology-pack`
- Branch: `main`
- Path: `docs`
- Document limit: `200`
- package_id: `0500d163-69b5-47ec-92af-de0ede91aba8`

## Validation Summary

- **Ingest: PASS**
- **Retrieval Quality: PARTIAL**
- **Reason:** core entity and relationship docs were not strongly retrieved by OpenCrab query.
- **Next Action:** strengthen bilingual labels, explicit relationship table, and seed triples.

## Ingest Metrics (confirmed)

| Metric | Value |
|---|---:|
| documents | 13 |
| chunks | 16 |
| nodes | 169 |
| edges | 156 |

## Interpretation

- Ingest pipeline itself succeeded.
- Graph generation (nodes/edges) is active.
- However, retrieval did not consistently surface core ontology structure (entities/relations), so release status is **PASS-PARTIAL**, not full PASS.

## v0.1-r1 Reinforcement Scope

Updated files:
1. `docs/02_core_entities.md`
2. `docs/03_relationships.md`
3. `docs/10_seed_triples_examples.md`
4. `OPENCRAB_INGEST_VALIDATION_REPORT.md`

### What was strengthened

1. Core entities were restructured into explicit groups with bilingual labels:
   - PersonGroup
   - FacilityType
   - Service
   - Actor
   - LegalSource
   - PublicDataset
   - Indicator
   - LifecycleEvent

2. Relationship predicates were made explicit for retrieval:
   - `DEFINED_BY`
   - `REGULATED_BY`
   - `PROVIDES`
   - `REFERS_TO`
   - `MEASURED_BY`
   - `PART_OF_FLOW`
   - `TARGETS`
   - `OPERATED_BY`

3. Seed triple examples were expanded to 40 lines in tabular triple format:
   - `subject | predicate | object | evidence_note`

## Policy Guardrails (reconfirmed)

- No internal facility materials
- No personal information
- No Didimbil internal materials
- No accounting data / case-management records
- No mass copy of legal full-text

## Next Verification Recommendation

- Re-run OpenCrab query validation against the same package_id.
- Check whether the following prompts now retrieve `docs/02`, `docs/03`, `docs/10` with stronger relevance:
  1. 목적/제외 범위
  2. 핵심 엔티티
  3. 시설-서비스 관계
  4. 금지 자료
  5. 최신성 관리

If retrieval improves on items 2 and 3 with explicit doc grounding, promote status from PASS-PARTIAL to PASS.
