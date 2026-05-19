# OpenCrab Ingest Validation Report Addendum

> Version: `0.1-r1`  
> Date: 2026-05-19  
> Target Repository: `https://github.com/psa0426/korea-homeless-welfare-self-reliance-ontology-pack`

## 1. Current Validation Status

| Check Item | Status | Notes |
|---|---|---|
| GitHub repository ingest | `PASS` | OpenCrab GitHub ingest succeeded. |
| Document count | `PASS` | 13 documents were detected after ingest. |
| Node generation | `PASS` | 169 nodes were generated. |
| Edge generation | `PASS` | 156 edges were generated. |
| Retrieval quality | `PARTIAL` | The pack overview and exclusion policy were retrieved, but core entity and relationship documents were not strongly retrieved in initial query testing. |
| Marketplace readiness | `NOT READY` | Do not publish before re-ingest and retrieval quality check. |

## 2. Observed Issue

The initial OpenCrab query was able to retrieve:

- `README.md`
- `docs/00_pack_manifest.md`
- `docs/01_scope_and_policy.md`

However, it did not strongly retrieve:

- `docs/02_core_entities.md`
- `docs/03_relationships.md`
- `docs/10_seed_triples_examples.md`

This means the pack is structurally ingested but needs stronger retrieval signals for entity and relationship questions.

## 3. Remediation

The following documents were strengthened in version `0.1-r1`:

1. `docs/02_core_entities.md`
   - Added explicit bilingual labels.
   - Added entity classes: `PersonGroup`, `FacilityType`, `Service`, `Actor`, `LegalSource`, `PublicDataset`, `Indicator`, `LifecycleEvent`, `NeedDomain`, `EvidenceSource`.
   - Added retrieval keywords and exclusion rules.

2. `docs/03_relationships.md`
   - Added relationship predicates: `DEFINED_BY`, `REGULATED_BY`, `PROVIDES`, `REFERS_TO`, `MEASURED_BY`, `PART_OF_FLOW`, `TARGETS`, `OPERATED_BY`, `USES_SOURCE`, `HAS_ENTITY_CLASS`, `HAS_SEED_TRIPLE`.
   - Added domain/range tables.
   - Added examples and anti-patterns.

3. `docs/10_seed_triples_examples.md`
   - Added seed triples for legal grounding, facility-service links, service-target links, actor-service links, lifecycle flow, indicators, and governance exclusions.
   - Added compact retrieval-focused triple list.

## 4. Required Next Action

After committing these changes to GitHub:

1. Re-run OpenCrab GitHub ingest with the same settings:
   - repository: `https://github.com/psa0426/korea-homeless-welfare-self-reliance-ontology-pack`
   - branch: `main`
   - path: `docs`
   - document limit: `200`
   - scan all readable documents: `ON`

2. Run retrieval tests:

```text
노숙인 복지 온톨로지의 핵심 엔티티는 무엇인가?
노숙인복지시설과 서비스는 어떤 관계로 연결되는가?
DEFINED_BY, REGULATED_BY, PROVIDES, REFERS_TO 관계는 무엇인가?
이 팩에서 사용하면 안 되는 자료는 무엇인가?
노숙인 서비스 전달체계의 주요 단계는 무엇인가?
```

3. Expected result:
   - `02_core_entities.md`, `03_relationships.md`, and `10_seed_triples_examples.md` should appear in evidence.
   - OpenCrab answer should mention the relationship predicates explicitly.
   - OpenCrab answer should mention exclusion rules: no PII, no internal facility documents, no case records, no donor data, no accounting records.
   - Core entities should include `PersonGroup`, `FacilityType`, `Service`, `Actor`, `LegalSource`, `PublicDataset`, `Indicator`, and `LifecycleEvent`.

## 5. Publication Gate

Do not publish the pack to marketplace until:

- Retrieval quality is `PASS`.
- Source catalog is traceable.
- Legal and policy sources are checked against current public sources.
- The pack clearly states it is not legal advice, clinical guidance, or a substitute for official administrative judgment.
