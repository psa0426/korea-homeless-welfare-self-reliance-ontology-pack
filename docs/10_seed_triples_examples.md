# Seed Triples Examples for Korea Homeless Welfare & Self-Reliance Ontology

> Version: `0.1-r1`  
> Language: `ko-KR` with English labels  
> Source policy: public sources only  
> Safety policy: no personal data, no internal facility records, no donor data, no accounting records, no individual case notes

## 1. Purpose

This document provides seed triple examples for bootstrapping the Korea Homeless Welfare & Self-Reliance Ontology Pack.

These triples are designed to make OpenCrab retrieval stronger for questions about:

- core entities
- facility types
- service taxonomy
- relationship predicates
- service delivery flow
- public evidence and governance
- exclusion rules

The triples are **ontology seed examples**, not final legal determinations. Legal, policy, and local implementation details must be verified against the latest public source before operational use.

---

## 2. Triple Format

| Field | Meaning |
|---|---|
| `subject` | Source node ID or label |
| `predicate` | Relationship type |
| `object` | Target node ID or label |
| `evidence_note` | Public source or verification instruction |

---

## 3. Core Entity Class Triples

| subject | predicate | object | evidence_note |
|---|---|---|---|
| `pack:kr_homeless_welfare_selfreliance_ontology` | `HAS_ENTITY_CLASS` | `PersonGroup` | Core entity class for target groups. |
| `pack:kr_homeless_welfare_selfreliance_ontology` | `HAS_ENTITY_CLASS` | `FacilityType` | Core entity class for facilities and service sites. |
| `pack:kr_homeless_welfare_selfreliance_ontology` | `HAS_ENTITY_CLASS` | `Service` | Core entity class for public service functions. |
| `pack:kr_homeless_welfare_selfreliance_ontology` | `HAS_ENTITY_CLASS` | `Actor` | Core entity class for institutions and service actors. |
| `pack:kr_homeless_welfare_selfreliance_ontology` | `HAS_ENTITY_CLASS` | `LegalSource` | Core entity class for laws and official guidance. |
| `pack:kr_homeless_welfare_selfreliance_ontology` | `HAS_ENTITY_CLASS` | `PublicDataset` | Core entity class for public data sources. |
| `pack:kr_homeless_welfare_selfreliance_ontology` | `HAS_ENTITY_CLASS` | `Indicator` | Core entity class for aggregate public indicators. |
| `pack:kr_homeless_welfare_selfreliance_ontology` | `HAS_ENTITY_CLASS` | `LifecycleEvent` | Core entity class for service journey events. |

---

## 4. Legal and Policy Grounding Triples

| subject | predicate | object | evidence_note |
|---|---|---|---|
| `person_group:homeless_person` | `DEFINED_BY` | `legal_source:homeless_welfare_act` | Verify against current public legal text. |
| `facility_type:temporary_protection_facility` | `REGULATED_BY` | `legal_source:homeless_welfare_act` | Verify legal classification and current terminology. |
| `facility_type:self_reliance_facility` | `REGULATED_BY` | `legal_source:homeless_welfare_act` | Verify legal classification and current terminology. |
| `facility_type:rehabilitation_facility` | `REGULATED_BY` | `legal_source:homeless_welfare_act` | Verify legal classification and current terminology. |
| `facility_type:care_facility` | `REGULATED_BY` | `legal_source:homeless_welfare_act` | Verify legal classification and current terminology. |
| `facility_type:comprehensive_support_center` | `REGULATED_BY` | `legal_source:homeless_welfare_act` | Verify current legal or public guidance source. |
| `facility_type:jjokbang_counseling_center` | `REGULATED_BY` | `legal_source:homeless_welfare_act` | Verify current legal or public guidance source. |
| `service:income_support_linkage` | `REFERS_TO` | `legal_source:national_basic_livelihood_security_act` | Use only for public income support linkage context. |
| `service:emergency_protection` | `REFERS_TO` | `legal_source:emergency_welfare_support_act` | Use only for emergency support linkage context. |
| `service:mental_health_referral` | `REFERS_TO` | `legal_source:mental_health_welfare_act` | Linkage only; do not infer diagnosis. |
| `service:medical_referral` | `REFERS_TO` | `legal_source:medical_aid_act` | Linkage only; verify current eligibility rules separately. |

---

## 5. Facility-Service Triples

| subject | predicate | object | evidence_note |
|---|---|---|---|
| `facility_type:temporary_protection_facility` | `PROVIDES` | `service:emergency_protection` | Public-service role; verify source. |
| `facility_type:temporary_protection_facility` | `PROVIDES` | `service:temporary_shelter` | Public-service role; verify source. |
| `facility_type:temporary_protection_facility` | `PROVIDES` | `service:initial_assessment` | Public-service role; verify source. |
| `facility_type:self_reliance_facility` | `PROVIDES` | `service:self_reliance_planning` | Public-service role; verify source. |
| `facility_type:self_reliance_facility` | `PROVIDES` | `service:employment_support` | Public-service role; verify source. |
| `facility_type:self_reliance_facility` | `PROVIDES` | `service:housing_support_linkage` | Public-service role; verify source. |
| `facility_type:rehabilitation_facility` | `PROVIDES` | `service:case_management` | General rehabilitation support concept; verify source. |
| `facility_type:rehabilitation_facility` | `PROVIDES` | `service:medical_referral` | Linkage concept only; verify facility-specific and public source. |
| `facility_type:rehabilitation_facility` | `PROVIDES` | `service:mental_health_referral` | Linkage concept only; do not infer clinical diagnosis. |
| `facility_type:care_facility` | `PROVIDES` | `service:case_management` | Care support concept; verify source. |
| `facility_type:comprehensive_support_center` | `PROVIDES` | `service:street_outreach` | Common service delivery concept; verify public guidance. |
| `facility_type:comprehensive_support_center` | `PROVIDES` | `service:initial_assessment` | Common service delivery concept; verify public guidance. |
| `facility_type:comprehensive_support_center` | `PROVIDES` | `service:service_referral` | Common service delivery concept; verify public guidance. |
| `facility_type:jjokbang_counseling_center` | `PROVIDES` | `service:initial_assessment` | Public support linkage concept. |
| `facility_type:jjokbang_counseling_center` | `PROVIDES` | `service:housing_support_linkage` | Public support linkage concept. |
| `facility_type:meal_support_site` | `PROVIDES` | `service:meal_support` | Service site concept; not necessarily a statutory facility type. |

---

## 6. Service-Target Triples

| subject | predicate | object | evidence_note |
|---|---|---|---|
| `service:street_outreach` | `TARGETS` | `person_group:street_homeless_person` | Public outreach target group. |
| `service:temporary_shelter` | `TARGETS` | `need:safety` | Emergency and safety need domain. |
| `service:emergency_protection` | `TARGETS` | `need:safety` | Emergency and safety need domain. |
| `service:meal_support` | `TARGETS` | `need:food_and_hygiene` | Food and daily living support. |
| `service:hygiene_support` | `TARGETS` | `need:food_and_hygiene` | Hygiene and daily living support. |
| `service:medical_referral` | `TARGETS` | `need:healthcare` | Medical linkage need domain. |
| `service:mental_health_referral` | `TARGETS` | `need:mental_health` | Mental health linkage; not diagnosis. |
| `service:addiction_support_referral` | `TARGETS` | `need:addiction_support` | Support linkage; not diagnosis. |
| `service:identity_recovery_support` | `TARGETS` | `need:identity_and_administration` | Administrative access and identity-related support. |
| `service:income_support_linkage` | `TARGETS` | `need:income` | Income support linkage. |
| `service:housing_support_linkage` | `TARGETS` | `need:housing` | Housing support linkage. |
| `service:employment_support` | `TARGETS` | `need:income` | Employment and income need domain. |
| `service:self_reliance_planning` | `TARGETS` | `person_group:self_reliance_participant` | Self-reliance planning participant group. |
| `service:community_reintegration` | `TARGETS` | `need:housing` | Community transition and housing stability. |
| `service:follow_up_support` | `TARGETS` | `need:social_relationship` | Follow-up and continuity support. |

---

## 7. Actor-Service and Referral Triples

| subject | predicate | object | evidence_note |
|---|---|---|---|
| `actor:ministry_of_health_and_welfare` | `PROVIDES` | `legal_source:public_policy_guidance` | National policy and guidance function. |
| `actor:metropolitan_government` | `OPERATED_BY` | `public_program:regional_homeless_welfare_plan` | Regional public implementation; verify local plan. |
| `actor:municipal_government` | `OPERATED_BY` | `public_program:local_homeless_welfare_service` | Local public implementation; verify local source. |
| `actor:homeless_welfare_facility` | `PROVIDES` | `service:case_management` | Facility-level service concept; public model only. |
| `actor:comprehensive_support_center` | `PROVIDES` | `service:street_outreach` | Public outreach and consultation. |
| `service:medical_referral` | `REFERS_TO` | `actor:public_health_center` | Medical and public health linkage. |
| `service:mental_health_referral` | `REFERS_TO` | `actor:mental_health_welfare_center` | Mental health service linkage. |
| `service:employment_support` | `REFERS_TO` | `actor:employment_center` | Employment service linkage. |
| `service:housing_support_linkage` | `REFERS_TO` | `actor:housing_welfare_center` | Housing welfare service linkage. |
| `service:income_support_linkage` | `REFERS_TO` | `actor:municipal_government` | Public assistance and local administration linkage. |
| `service:identity_recovery_support` | `REFERS_TO` | `actor:municipal_government` | Administrative access linkage; verify procedure. |

---

## 8. Lifecycle Flow Triples

| subject | predicate | object | evidence_note |
|---|---|---|---|
| `event:discovery` | `PART_OF_FLOW` | `flow:homeless_service_delivery` | General public service flow. |
| `event:first_contact` | `PART_OF_FLOW` | `flow:homeless_service_delivery` | Outreach or first engagement. |
| `event:initial_consultation` | `PART_OF_FLOW` | `flow:homeless_service_delivery` | Initial consultation. |
| `event:urgent_risk_check` | `PART_OF_FLOW` | `flow:homeless_service_delivery` | Emergency risk check. |
| `event:temporary_protection` | `PART_OF_FLOW` | `flow:homeless_service_delivery` | Temporary protection stage. |
| `event:facility_admission_consideration` | `PART_OF_FLOW` | `flow:homeless_service_delivery` | Facility admission consideration; local procedures vary. |
| `event:service_referral` | `PART_OF_FLOW` | `flow:homeless_service_delivery` | Service linkage stage. |
| `event:self_reliance_planning` | `PART_OF_FLOW` | `flow:homeless_service_delivery` | Self-reliance planning stage. |
| `event:community_transition` | `PART_OF_FLOW` | `flow:homeless_service_delivery` | Community transition stage. |
| `event:follow_up` | `PART_OF_FLOW` | `flow:homeless_service_delivery` | Follow-up stage; no case records. |

---

## 9. Indicator and Dataset Triples

| subject | predicate | object | evidence_note |
|---|---|---|---|
| `facility_type:homeless_welfare_facility` | `MEASURED_BY` | `indicator:number_of_facilities` | Public aggregate count only. |
| `facility_type:homeless_welfare_facility` | `MEASURED_BY` | `indicator:facility_capacity` | Public aggregate capacity only. |
| `service:street_outreach` | `MEASURED_BY` | `indicator:street_outreach_contacts` | Public aggregate count only. |
| `service:temporary_shelter` | `MEASURED_BY` | `indicator:temporary_protection_use` | Public aggregate count only. |
| `service:housing_support_linkage` | `MEASURED_BY` | `indicator:housing_linkage_count` | Public aggregate count only. |
| `service:employment_support` | `MEASURED_BY` | `indicator:employment_linkage_count` | Public aggregate count only. |
| `policy_goal:self_reliance_support` | `MEASURED_BY` | `indicator:self_reliance_outcome` | Public aggregate outcome only. |
| `indicator:number_of_facilities` | `USES_SOURCE` | `dataset:homeless_facility_registry` | Public facility registry or official statistics. |
| `indicator:service_users` | `USES_SOURCE` | `dataset:facility_statistics` | Public facility statistics only. |
| `indicator:self_reliance_outcome` | `USES_SOURCE` | `dataset:public_policy_plan` | Public plan or report only. |

---

## 10. Governance and Exclusion Triples

| subject | predicate | object | evidence_note |
|---|---|---|---|
| `pack:kr_homeless_welfare_selfreliance_ontology` | `USES_SOURCE` | `source_policy:public_sources_only` | Pack must use public sources only. |
| `source_policy:public_sources_only` | `EXCLUDES` | `data_type:personal_resident_records` | No personal records. |
| `source_policy:public_sources_only` | `EXCLUDES` | `data_type:donor_records` | No donor information. |
| `source_policy:public_sources_only` | `EXCLUDES` | `data_type:accounting_ledgers` | No internal accounting records. |
| `source_policy:public_sources_only` | `EXCLUDES` | `data_type:case_management_logs` | No private case notes or logs. |
| `source_policy:public_sources_only` | `EXCLUDES` | `data_type:clinical_diagnosis_details` | No clinical diagnosis details. |
| `source_policy:public_sources_only` | `EXCLUDES` | `data_type:internal_facility_documents` | No unpublished internal documents. |
| `pack:kr_homeless_welfare_selfreliance_ontology` | `HAS_LIMITATION` | `limitation:not_legal_advice` | Must not be used as legal advice. |
| `pack:kr_homeless_welfare_selfreliance_ontology` | `HAS_LIMITATION` | `limitation:not_clinical_guidance` | Must not be used as clinical guidance. |
| `pack:kr_homeless_welfare_selfreliance_ontology` | `HAS_LIMITATION` | `limitation:requires_current_source_check` | Laws and policy guidance can change. |

---

## 11. Compact Triple List for Retrieval

This section repeats the most important triples in compact form to improve retrieval.

```text
노숙인 / Homeless Person -- DEFINED_BY -- 노숙인 등의 복지 및 자립지원에 관한 법률 / Homeless Welfare Act
거리노숙인 / Street Homeless Person -- TARGETS -- 거리상담 / Street Outreach
노숙인일시보호시설 / Temporary Protection Facility -- PROVIDES -- 응급보호 / Emergency Protection
노숙인일시보호시설 / Temporary Protection Facility -- PROVIDES -- 일시보호 / Temporary Shelter
노숙인자활시설 / Self-Reliance Facility -- PROVIDES -- 자립계획 / Self-Reliance Planning
노숙인자활시설 / Self-Reliance Facility -- PROVIDES -- 취업지원 / Employment Support
노숙인재활시설 / Rehabilitation Facility -- PROVIDES -- 사례관리 / Case Management
노숙인재활시설 / Rehabilitation Facility -- PROVIDES -- 의료연계 / Medical Referral
노숙인요양시설 / Care Facility -- PROVIDES -- 돌봄·요양지원 / Care Support
노숙인종합지원센터 / Comprehensive Support Center -- PROVIDES -- 거리상담 / Street Outreach
노숙인종합지원센터 / Comprehensive Support Center -- PROVIDES -- 서비스 연계 / Service Referral
쪽방상담소 / Jjokbang Counseling Center -- PROVIDES -- 주거지원 연계 / Housing Support Linkage
의료연계 / Medical Referral -- REFERS_TO -- 보건소 / Public Health Center
정신건강 연계 / Mental Health Referral -- REFERS_TO -- 정신건강복지센터 / Mental Health Welfare Center
취업지원 / Employment Support -- REFERS_TO -- 고용센터 / Employment Center
주거지원 연계 / Housing Support Linkage -- REFERS_TO -- 주거복지센터 / Housing Welfare Center
초기상담 / Initial Consultation -- PART_OF_FLOW -- 노숙인 서비스 전달체계 / Homeless Service Delivery Flow
일시보호 / Temporary Protection -- PART_OF_FLOW -- 노숙인 서비스 전달체계 / Homeless Service Delivery Flow
자립계획 / Self-Reliance Planning -- PART_OF_FLOW -- 노숙인 서비스 전달체계 / Homeless Service Delivery Flow
사후관리 / Follow-Up -- PART_OF_FLOW -- 노숙인 서비스 전달체계 / Homeless Service Delivery Flow
시설 수 / Number of Facilities -- USES_SOURCE -- 노숙인복지시설 현황 / Homeless Welfare Facility Registry
거리상담 접촉 건수 / Street Outreach Contacts -- MEASURED_BY -- 거리상담 / Street Outreach
주거연계 건수 / Housing Linkage Count -- MEASURED_BY -- 주거지원 연계 / Housing Support Linkage
공개자료만 사용 / Public Sources Only -- EXCLUDES -- 개인정보 / Personal Data
공개자료만 사용 / Public Sources Only -- EXCLUDES -- 내부자료 / Internal Facility Documents
공개자료만 사용 / Public Sources Only -- EXCLUDES -- 회계자료 / Accounting Records
```

---

## 12. Retrieval Test Questions

After re-ingesting these documents, test with:

1. What are the core entity classes in the Korea Homeless Welfare & Self-Reliance Ontology Pack?
2. 노숙인 복지 온톨로지의 핵심 엔티티는 무엇인가?
3. Which facility types provide which services?
4. 노숙인복지시설과 서비스는 어떤 관계로 연결되는가?
5. What relationship predicates are defined in this pack?
6. DEFINED_BY, REGULATED_BY, PROVIDES, REFERS_TO, MEASURED_BY, PART_OF_FLOW, TARGETS, OPERATED_BY 관계는 무엇인가?
7. What data types are excluded from this pack?
8. 이 팩에서 사용하면 안 되는 자료는 무엇인가?
