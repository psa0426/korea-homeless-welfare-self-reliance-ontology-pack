# Relationship Types for Korea Homeless Welfare & Self-Reliance Ontology

> Version: `0.1-r1`  
> Language: `ko-KR` with English labels  
> Source policy: public sources only  
> Safety policy: do not encode personally identifiable individuals, internal case records, donor records, or accounting records

## 1. Purpose

This document defines the **relationship predicates** used in the Korea Homeless Welfare & Self-Reliance Ontology Pack.

The purpose is to make OpenCrab retrieval stronger for questions such as:

- What relationships connect facilities, services, actors, laws, and indicators?
- Which service is provided by which facility type?
- Which concepts are defined or regulated by legal sources?
- Which lifecycle event is part of the service delivery flow?
- Which indicators measure public service outcomes?

---

## 2. Relationship Overview

| Predicate | Korean Label | English Label | Domain | Range | Meaning |
|---|---|---|---|---|---|
| `DEFINED_BY` | 정의 근거 | Defined By | `PersonGroup`, `FacilityType`, `Service`, `NeedDomain` | `LegalSource`, `EvidenceSource` | A concept is defined or explained by a public legal or policy source. |
| `REGULATED_BY` | 규율 근거 | Regulated By | `FacilityType`, `Service`, `Actor` | `LegalSource` | A facility, actor, or service is governed by a law, rule, public plan, or official guidance. |
| `PROVIDES` | 제공 | Provides | `FacilityType`, `Actor` | `Service` | A facility type or actor provides or may provide a service. |
| `REFERS_TO` | 연계 | Refers To | `Service`, `Actor`, `LifecycleEvent` | `Actor`, `Service`, `NeedDomain` | A service, actor, or event links a person/group to another service or actor. |
| `MEASURED_BY` | 지표로 측정 | Measured By | `Service`, `FacilityType`, `PolicyGoal`, `NeedDomain` | `Indicator`, `PublicDataset` | A public indicator or dataset measures a concept or outcome. |
| `PART_OF_FLOW` | 흐름에 포함 | Part of Flow | `LifecycleEvent`, `Service` | `LifecycleEvent`, `ServiceFlow` | An event or service belongs to a broader service delivery flow. |
| `TARGETS` | 지원대상 | Targets | `Service`, `PolicyGoal`, `FacilityType` | `PersonGroup`, `NeedDomain` | A service, facility, or policy goal targets a person group or need domain. |
| `OPERATED_BY` | 운영주체 | Operated By | `FacilityType`, `ServiceSite`, `PublicProgram` | `Actor` | A facility, service site, or program is operated or implemented by an actor. |
| `USES_SOURCE` | 출처 사용 | Uses Source | `EvidenceSource`, `Document`, `OntologyPack` | `LegalSource`, `PublicDataset`, `PublicDocument` | A document or pack uses a public source. |
| `HAS_ENTITY_CLASS` | 엔티티 클래스 포함 | Has Entity Class | `OntologyPack` | `EntityClass` | A pack includes a defined ontology entity class. |
| `HAS_SEED_TRIPLE` | 시드 트리플 포함 | Has Seed Triple | `OntologyPack` | `SeedTriple` | A pack contains example triples for bootstrapping the graph. |

---

## 3. Predicate Definitions and Examples

### 3.1 `DEFINED_BY` / 정의 근거

Use when a concept is defined, explained, or bounded by a public legal or policy source.

| Subject | Predicate | Object | Evidence Note |
|---|---|---|---|
| `person_group:homeless_person` | `DEFINED_BY` | `legal_source:homeless_welfare_act` | Verify definition against current law. |
| `facility_type:temporary_protection_facility` | `DEFINED_BY` | `legal_source:homeless_welfare_enforcement_rule` | Verify facility type and detailed standards. |
| `need:housing` | `DEFINED_BY` | `evidence_source:public_policy_guidance` | Use public policy context only. |

Retrieval keywords: `정의`, `법령상 정의`, `defined by`, `legal definition`, `public policy definition`.

---

### 3.2 `REGULATED_BY` / 규율 근거

Use when a public law, rule, plan, or administrative guidance regulates or structures a facility, service, or actor.

| Subject | Predicate | Object | Evidence Note |
|---|---|---|---|
| `facility_type:rehabilitation_facility` | `REGULATED_BY` | `legal_source:homeless_welfare_act` | Verify current legal source before use. |
| `facility_type:self_reliance_facility` | `REGULATED_BY` | `legal_source:homeless_welfare_enforcement_rule` | Verify public facility standards. |
| `actor:homeless_welfare_facility` | `REGULATED_BY` | `legal_source:social_welfare_services_act` | Use only for relevant social welfare administration context. |

Retrieval keywords: `규율`, `근거 법령`, `regulated by`, `법적 근거`, `제도 근거`.

---

### 3.3 `PROVIDES` / 제공

Use when a facility type or actor provides a service.

| Subject | Predicate | Object | Evidence Note |
|---|---|---|---|
| `facility_type:temporary_protection_facility` | `PROVIDES` | `service:temporary_shelter` | Public-service concept; verify source. |
| `facility_type:comprehensive_support_center` | `PROVIDES` | `service:street_outreach` | Common public delivery role; verify local source. |
| `facility_type:jjokbang_counseling_center` | `PROVIDES` | `service:initial_assessment` | Public service linkage context. |
| `actor:public_health_center` | `PROVIDES` | `service:medical_referral` | Actor may provide or receive linkage; verify local role. |

Retrieval keywords: `제공`, `서비스 제공`, `provides`, `facility provides service`.

---

### 3.4 `REFERS_TO` / 연계

Use when a service or actor links to another service, actor, or need domain.

| Subject | Predicate | Object | Evidence Note |
|---|---|---|---|
| `service:medical_referral` | `REFERS_TO` | `actor:public_health_center` | Linkage to public health resources. |
| `service:mental_health_referral` | `REFERS_TO` | `actor:mental_health_welfare_center` | Linkage, not clinical diagnosis. |
| `service:employment_support` | `REFERS_TO` | `actor:employment_center` | Linkage to employment services. |
| `service:housing_support_linkage` | `REFERS_TO` | `actor:housing_welfare_center` | Linkage to housing welfare resources. |

Retrieval keywords: `연계`, `의뢰`, `referral`, `refers to`, `service linkage`.

---

### 3.5 `MEASURED_BY` / 지표로 측정

Use when a public dataset or indicator measures a concept, facility, service, or policy goal.

| Subject | Predicate | Object | Evidence Note |
|---|---|---|---|
| `facility_type:homeless_welfare_facility` | `MEASURED_BY` | `indicator:number_of_facilities` | Use aggregate public data only. |
| `service:street_outreach` | `MEASURED_BY` | `indicator:street_outreach_contacts` | Public aggregate indicator. |
| `service:housing_support_linkage` | `MEASURED_BY` | `indicator:housing_linkage_count` | Public aggregate indicator. |
| `policy_goal:self_reliance_support` | `MEASURED_BY` | `indicator:self_reliance_outcome` | Public outcome indicator only. |

Retrieval keywords: `지표`, `통계`, `측정`, `measured by`, `indicator`, `dataset`.

---

### 3.6 `PART_OF_FLOW` / 흐름에 포함

Use when a lifecycle event or service is part of a broader public service delivery flow.

| Subject | Predicate | Object | Evidence Note |
|---|---|---|---|
| `event:discovery` | `PART_OF_FLOW` | `flow:homeless_service_delivery` | General public service flow. |
| `event:first_contact` | `PART_OF_FLOW` | `flow:homeless_service_delivery` | Outreach or first engagement. |
| `event:initial_consultation` | `PART_OF_FLOW` | `flow:homeless_service_delivery` | Initial consultation. |
| `event:temporary_protection` | `PART_OF_FLOW` | `flow:homeless_service_delivery` | Temporary protection stage. |
| `event:follow_up` | `PART_OF_FLOW` | `flow:homeless_service_delivery` | Follow-up concept, no personal record. |

Retrieval keywords: `지원 흐름`, `서비스 전달체계`, `lifecycle`, `part of flow`, `service delivery flow`.

---

### 3.7 `TARGETS` / 지원대상

Use when a service, facility, or policy goal targets a person group or need domain.

| Subject | Predicate | Object | Evidence Note |
|---|---|---|---|
| `service:street_outreach` | `TARGETS` | `person_group:street_homeless_person` | Public outreach target group. |
| `service:temporary_shelter` | `TARGETS` | `need:safety` | Safety and urgent protection need. |
| `service:housing_support_linkage` | `TARGETS` | `need:housing` | Housing support need domain. |
| `service:employment_support` | `TARGETS` | `need:income` | Income and work-related need domain. |

Retrieval keywords: `지원대상`, `대상`, `targets`, `target group`, `need domain`.

---

### 3.8 `OPERATED_BY` / 운영주체

Use when a facility, service site, or public program is operated or implemented by an actor.

| Subject | Predicate | Object | Evidence Note |
|---|---|---|---|
| `facility_type:homeless_welfare_facility` | `OPERATED_BY` | `actor:nonprofit_provider` | Facility operator can vary; verify public facility registry. |
| `facility_type:comprehensive_support_center` | `OPERATED_BY` | `actor:municipal_government` | Public implementation can vary by region. |
| `public_program:homeless_welfare_service` | `OPERATED_BY` | `actor:metropolitan_government` | Regional policy implementation. |

Retrieval keywords: `운영주체`, `위탁`, `운영`, `operated by`, `implemented by`.

---

## 4. Core Relationship Patterns

### Pattern A: Legal Grounding

```text
Concept or FacilityType -> DEFINED_BY -> LegalSource
FacilityType or Service -> REGULATED_BY -> LegalSource
```

Example:

```text
노숙인재활시설 / Rehabilitation Facility
REGULATED_BY
노숙인 등의 복지 및 자립지원에 관한 법률 / Homeless Welfare Act
```

### Pattern B: Service Delivery

```text
FacilityType or Actor -> PROVIDES -> Service
Service -> TARGETS -> PersonGroup or NeedDomain
Service -> REFERS_TO -> Actor
```

Example:

```text
노숙인종합지원센터 / Comprehensive Support Center
PROVIDES
거리상담 / Street Outreach
```

### Pattern C: Lifecycle Flow

```text
LifecycleEvent -> PART_OF_FLOW -> Homeless Service Delivery Flow
Service -> PART_OF_FLOW -> Homeless Service Delivery Flow
```

Example flow:

```text
발견 / Discovery
-> 최초접촉 / First Contact
-> 초기상담 / Initial Consultation
-> 위기상황 확인 / Urgent Risk Check
-> 일시보호 / Temporary Protection
-> 서비스 연계 / Service Referral
-> 자립계획 / Self-Reliance Planning
-> 지역사회 전환 / Community Transition
-> 사후관리 / Follow-Up
```

### Pattern D: Measurement

```text
Service or FacilityType -> MEASURED_BY -> Indicator
Indicator -> USES_SOURCE -> PublicDataset
```

Example:

```text
거리상담 / Street Outreach
MEASURED_BY
거리상담 접촉 건수 / Street Outreach Contacts
```

---

## 5. Anti-Patterns

Do not create relationships such as:

| Bad Pattern | Reason |
|---|---|
| Individual resident -> HAS_DIAGNOSIS -> Clinical condition | Personal medical data and clinical judgment area |
| Donor -> FUNDED -> Individual service | Donor/private accounting data |
| Facility staff member -> MANAGES -> Resident | Internal staffing and case record data |
| Resident name -> LIVES_AT -> Facility | Personally identifiable information |
| Case note -> EVIDENCE_FOR -> Service outcome | Private case-management record |
| Internal audit document -> REGULATES -> Facility type | Non-public source |

---

## 6. Retrieval Keywords

Use these terms to improve OpenCrab retrieval:

- 노숙인 복지 관계 타입
- 온톨로지 관계 정의
- relationship predicates homelessness welfare
- DEFINED_BY REGULATED_BY PROVIDES REFERS_TO MEASURED_BY PART_OF_FLOW TARGETS OPERATED_BY
- 시설 서비스 법령 지표 연계 흐름 운영주체
- service delivery flow homeless welfare Korea
- public sources only relationship model
