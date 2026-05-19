# Relationship Types (v0.1-r1)

This table defines explicit predicates for OpenCrab retrieval.

## Canonical Relationship Table

| Predicate | Korean Label | Domain | Range | Meaning |
|---|---|---|---|---|
| `DEFINED_BY` | ~에 의해 정의됨 | Entity Concept | LegalSource | Entity definition is grounded in law/guideline text |
| `REGULATED_BY` | ~에 의해 규율됨 | Program/FacilityType/Service | LegalSource | Operational scope is regulated by legal/administrative source |
| `PROVIDES` | 제공함 | FacilityType/Program/Actor | Service | Facility/program/actor provides a service |
| `REFERS_TO` | 참조함 | Policy/Guideline/Indicator Spec | Entity/LegalSource/PublicDataset | Document or spec references another concept/source |
| `MEASURED_BY` | ~로 측정됨 | Program/Service/Outcome | Indicator | Performance or outcome is measured by indicator |
| `PART_OF_FLOW` | 흐름의 일부임 | LifecycleEvent/Service | Lifecycle Flow Stage/Event | Step belongs to service/lifecycle flow |
| `TARGETS` | 대상임 | Service/Program/Policy | PersonGroup | Program/service targets a specific person group |
| `OPERATED_BY` | ~에 의해 운영됨 | FacilityType/Program | Actor | Program/facility is operated by actor |

## Retrieval-Oriented Examples

- `Self-Reliance Facility` `PROVIDES` `Employment Linkage`
- `Emergency Shelter` `PROVIDES` `Emergency Protection`
- `Housing Transition Support` `TARGETS` `Self-Reliance Transition Candidate`
- `Housing Transition Support` `MEASURED_BY` `Housing Transition Rate`
- `Homeless Welfare Facility` `OPERATED_BY` `Facility Operating Organization`
- `Street Outreach Counseling` `PART_OF_FLOW` `Crisis Contact`
- `Self-Reliance Facility` `REGULATED_BY` `Administrative Guideline`
- `Street Homeless Person` `DEFINED_BY` `Act`

## Evidence Rule

- Each relationship instance should be attachable to at least one public evidence source.
- Internal facility documents, accounting records, donor files, and case-management records are prohibited.
