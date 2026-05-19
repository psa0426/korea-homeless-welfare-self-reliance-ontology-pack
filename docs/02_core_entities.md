# Core Entities for Korea Homeless Welfare & Self-Reliance Ontology

> Version: `0.1-r1`  
> Language: `ko-KR` with English labels  
> Source policy: public sources only  
> Safety policy: no personal data, no internal facility records, no donor data, no accounting records, no individual case notes

## 1. Purpose

This document defines the **core entity classes and seed entity candidates** for the Korea Homeless Welfare & Self-Reliance Ontology Pack.

The purpose of this file is to make OpenCrab retrieval stronger for questions such as:

- What are the core entities in the homelessness welfare ontology?
- Which facility types are represented?
- Which services and actors are represented?
- Which public evidence sources should support each concept family?
- What data should be excluded?

This document is not a legal opinion, clinical guideline, or facility operation manual. It is a public-source ontology seed document.

---

## 2. Entity Class Overview

| Entity Class | Korean Label | English Label | Purpose |
|---|---|---|---|
| `PersonGroup` | 대상자·인구집단 | Person Group | Groups described in public homeless welfare policy and services |
| `FacilityType` | 시설유형 | Facility Type | Types of homeless welfare facilities or support centers |
| `Service` | 서비스 | Service | Welfare, protection, health, self-reliance, housing, and referral services |
| `Actor` | 수행주체 | Actor | Public or private institutions involved in service delivery |
| `LegalSource` | 법령·제도 근거 | Legal Source | Laws, enforcement decrees, rules, plans, and public guidance |
| `PublicDataset` | 공개 데이터셋 | Public Dataset | Publicly available facility, policy, or statistical datasets |
| `Indicator` | 지표 | Indicator | Public outcome, input, output, or quality indicators |
| `LifecycleEvent` | 지원 단계·생애주기 이벤트 | Lifecycle Event | Events in the service journey from discovery to follow-up |
| `NeedDomain` | 욕구·지원영역 | Need Domain | Needs such as housing, income, medical care, mental health, identity recovery |
| `EvidenceSource` | 근거 출처 | Evidence Source | Source records used to verify concept families |

---

## 3. PersonGroup Entities

| Node ID | Korean Label | English Label | Entity Class | Definition / Retrieval Hints | Evidence Policy |
|---|---|---|---|---|---|
| `person_group:homeless_person` | 노숙인 | Homeless Person | `PersonGroup` | A public-policy person group related to homelessness welfare and self-reliance support in Korea. | Verify against current law and public guidance. |
| `person_group:street_homeless_person` | 거리노숙인 | Street Homeless Person | `PersonGroup` | Person group associated with street outreach, emergency protection, temporary shelter, and referral pathways. | Use public policy, survey, or municipal guidance only. |
| `person_group:facility_homeless_person` | 시설노숙인 | Facility Homeless Person | `PersonGroup` | Person group associated with residential or facility-based homeless welfare services. | Use public statistics and policy documents only. |
| `person_group:unsheltered_person` | 비주거·불안정 거처 이용자 | Unsheltered or Precariously Housed Person | `PersonGroup` | Broader housing vulnerability concept used for service navigation; must not be used as a personal label without evidence. | Public sources only. |
| `person_group:jjokbang_resident` | 쪽방주민 | Jjokbang Resident | `PersonGroup` | Person group associated with jjokbang counseling centers and housing-related support. | Use public source catalog and local government sources. |
| `person_group:at_risk_of_homelessness` | 노숙위기자 | Person at Risk of Homelessness | `PersonGroup` | Person group at risk due to housing loss, income loss, family disconnection, debt, illness, or discharge from institution. | Use public policy and support program documents. |
| `person_group:self_reliance_participant` | 자립지원 참여자 | Self-Reliance Support Participant | `PersonGroup` | Person participating in self-reliance, employment, housing, or community reintegration support. | Use public program descriptions only. |

**Do not model personally identifiable individuals.**  
The ontology must not include resident names, registration numbers, phone numbers, addresses, case notes, medical diagnoses, donor information, accounting data, or internal facility records.

---

## 4. FacilityType Entities

| Node ID | Korean Label | English Label | Entity Class | Definition / Retrieval Hints | Evidence Policy |
|---|---|---|---|---|---|
| `facility_type:temporary_protection_facility` | 노숙인일시보호시설 | Temporary Protection Facility | `FacilityType` | Facility type associated with emergency or short-term protection and immediate safety support. | Verify against current law, rule, or public guidance. |
| `facility_type:self_reliance_facility` | 노숙인자활시설 | Self-Reliance Facility | `FacilityType` | Facility type associated with self-reliance, community return, work, income, and independence support. | Verify with public legal and policy sources. |
| `facility_type:rehabilitation_facility` | 노숙인재활시설 | Rehabilitation Facility | `FacilityType` | Facility type associated with rehabilitation-oriented support and daily living stabilization. | Verify with public legal and policy sources. |
| `facility_type:care_facility` | 노숙인요양시설 | Care Facility | `FacilityType` | Facility type associated with care support for people requiring long-term or intensive care support. | Verify with current public sources. |
| `facility_type:comprehensive_support_center` | 노숙인종합지원센터 | Comprehensive Support Center | `FacilityType` | Center type associated with outreach, consultation, emergency support, service coordination, and referral. | Verify with national or local public guidance. |
| `facility_type:jjokbang_counseling_center` | 쪽방상담소 | Jjokbang Counseling Center | `FacilityType` | Center associated with consultation and welfare linkage for jjokbang residents. | Verify with public source catalog and local government materials. |
| `facility_type:emergency_sleeping_place` | 응급잠자리 | Emergency Sleeping Place | `FacilityType` | Public-service facility or program concept for emergency overnight protection; local names can vary. | Treat as service/facility hybrid; verify local source. |
| `facility_type:meal_support_site` | 급식지원 장소 | Meal Support Site | `FacilityType` | Public or nonprofit food support location; not always a legal facility type. | Mark as service site, not necessarily statutory facility. |

**Important distinction:**  
A `FacilityType` in this ontology may represent either a statutory facility type or a public service site. When a term is not a statutory facility type, mark it as a public-service site and cite the relevant public source.

---

## 5. Service Entities

| Node ID | Korean Label | English Label | Entity Class | Definition / Retrieval Hints |
|---|---|---|---|---|
| `service:street_outreach` | 거리상담 | Street Outreach | `Service` | Field contact, discovery, engagement, and initial service linkage. |
| `service:initial_assessment` | 초기상담 | Initial Assessment | `Service` | Basic consultation to identify urgent needs and referral options. |
| `service:emergency_protection` | 응급보호 | Emergency Protection | `Service` | Immediate safety support, temporary protection, or emergency sleeping place linkage. |
| `service:temporary_shelter` | 일시보호 | Temporary Shelter | `Service` | Short-term shelter or protection support. |
| `service:meal_support` | 급식지원 | Meal Support | `Service` | Meals or food assistance. |
| `service:hygiene_support` | 위생지원 | Hygiene Support | `Service` | Bathing, laundry, clothing, hygiene supplies, or related support. |
| `service:medical_referral` | 의료연계 | Medical Referral | `Service` | Linkage to public health center, hospital, emergency care, or medical aid system. |
| `service:mental_health_referral` | 정신건강 연계 | Mental Health Referral | `Service` | Linkage to mental health welfare center or public mental health resources. |
| `service:addiction_support_referral` | 중독지원 연계 | Addiction Support Referral | `Service` | Linkage to public addiction, alcohol, or substance-use support resources where available. |
| `service:identity_recovery_support` | 신분회복 지원 | Identity Recovery Support | `Service` | Support for restoring or confirming identity-related administrative access. |
| `service:income_support_linkage` | 소득지원 연계 | Income Support Linkage | `Service` | Linkage to public income support, benefits, emergency support, or livelihood schemes. |
| `service:housing_support_linkage` | 주거지원 연계 | Housing Support Linkage | `Service` | Linkage to housing welfare, temporary housing, rental support, or community settlement support. |
| `service:employment_support` | 취업지원 | Employment Support | `Service` | Job counseling, training linkage, work opportunity linkage, or employment service coordination. |
| `service:self_reliance_planning` | 자립계획 수립 | Self-Reliance Planning | `Service` | Planning for income, housing, health, relationships, community return, and follow-up. |
| `service:case_management` | 사례관리 | Case Management | `Service` | Coordinated support planning and service linkage using non-identifiable public model terms only. |
| `service:community_reintegration` | 지역사회 복귀 지원 | Community Reintegration Support | `Service` | Support for moving from facility or street homelessness toward community living. |
| `service:follow_up_support` | 사후관리 | Follow-Up Support | `Service` | Post-exit or post-linkage monitoring and support; do not include private case notes. |

---

## 6. Actor Entities

| Node ID | Korean Label | English Label | Entity Class | Typical Role |
|---|---|---|---|---|
| `actor:ministry_of_health_and_welfare` | 보건복지부 | Ministry of Health and Welfare | `Actor` | National policy, law-related guidance, public plans, statistical publications. |
| `actor:metropolitan_government` | 시·도 | Metropolitan/Provincial Government | `Actor` | Regional planning, facility support, local implementation. |
| `actor:municipal_government` | 시·군·구 | Municipal Government | `Actor` | Local service implementation, referral, public assistance linkage. |
| `actor:homeless_welfare_facility` | 노숙인복지시설 | Homeless Welfare Facility | `Actor` | Facility or service provider within public welfare delivery system. |
| `actor:comprehensive_support_center` | 노숙인종합지원센터 | Comprehensive Support Center | `Actor` | Outreach, consultation, referral, emergency support coordination. |
| `actor:public_health_center` | 보건소 | Public Health Center | `Actor` | Public health linkage and local health resources. |
| `actor:mental_health_welfare_center` | 정신건강복지센터 | Mental Health Welfare Center | `Actor` | Mental health consultation and linkage. |
| `actor:employment_center` | 고용센터 | Employment Center | `Actor` | Employment counseling and public labor service linkage. |
| `actor:housing_welfare_center` | 주거복지센터 | Housing Welfare Center | `Actor` | Housing consultation and public housing resource linkage. |
| `actor:nonprofit_provider` | 민간복지기관 | Nonprofit Welfare Provider | `Actor` | Service provision, outreach, meals, shelter, and linkage depending on region. |

---

## 7. LegalSource Entities

| Node ID | Korean Label | English Label | Entity Class | Use Rule |
|---|---|---|---|---|
| `legal_source:homeless_welfare_act` | 노숙인 등의 복지 및 자립지원에 관한 법률 | Act on Welfare and Self-Reliance Support for Homeless Persons, etc. | `LegalSource` | Use as a primary legal source; verify latest version before legal conclusion. |
| `legal_source:homeless_welfare_enforcement_decree` | 노숙인 등의 복지 및 자립지원에 관한 법률 시행령 | Enforcement Decree | `LegalSource` | Use for delegated legal structure; verify current text. |
| `legal_source:homeless_welfare_enforcement_rule` | 노숙인 등의 복지 및 자립지원에 관한 법률 시행규칙 | Enforcement Rule | `LegalSource` | Use for detailed standards; verify current text. |
| `legal_source:social_welfare_services_act` | 사회복지사업법 | Social Welfare Services Act | `LegalSource` | Use only for relevant facility or social welfare administration context. |
| `legal_source:national_basic_livelihood_security_act` | 국민기초생활 보장법 | National Basic Livelihood Security Act | `LegalSource` | Use only for income and public assistance linkage context. |
| `legal_source:emergency_welfare_support_act` | 긴급복지지원법 | Emergency Welfare Support Act | `LegalSource` | Use only for emergency support linkage context. |
| `legal_source:mental_health_welfare_act` | 정신건강복지법 | Mental Health Welfare Act | `LegalSource` | Use only for mental health linkage context; do not infer diagnosis. |
| `legal_source:medical_aid_act` | 의료급여법 | Medical Aid Act | `LegalSource` | Use only for public medical aid linkage context. |

---

## 8. PublicDataset Entities

| Node ID | Korean Label | English Label | Entity Class | Typical Fields |
|---|---|---|---|---|
| `dataset:homeless_facility_registry` | 노숙인복지시설 현황 | Homeless Welfare Facility Registry | `PublicDataset` | Facility name, type, region, operator, capacity, public contact information where available. |
| `dataset:homeless_survey` | 노숙인 실태조사 | Homelessness Survey | `PublicDataset` | Population estimates, service use, health, housing, economic activity, needs. |
| `dataset:local_welfare_resources` | 지역 복지자원 현황 | Local Welfare Resource Dataset | `PublicDataset` | Local service resources, centers, public programs, referral contacts. |
| `dataset:public_policy_plan` | 공공 정책계획 자료 | Public Policy Plan Dataset | `PublicDataset` | plan period, policy goals, tasks, target groups, indicators. |
| `dataset:facility_statistics` | 시설 통계 | Facility Statistics | `PublicDataset` | facility counts, capacity, occupancy, service volume, staffing indicators where public. |

---

## 9. Indicator Entities

| Node ID | Korean Label | English Label | Entity Class | Measurement Hint |
|---|---|---|---|---|
| `indicator:number_of_facilities` | 시설 수 | Number of Facilities | `Indicator` | Count of public facility registry entries by type and region. |
| `indicator:facility_capacity` | 입소정원 | Facility Capacity | `Indicator` | Capacity by facility type where publicly disclosed. |
| `indicator:service_users` | 서비스 이용자 수 | Number of Service Users | `Indicator` | Publicly reported service use count; never individual records. |
| `indicator:street_outreach_contacts` | 거리상담 접촉 건수 | Street Outreach Contacts | `Indicator` | Outreach contacts or consultation count where public. |
| `indicator:temporary_protection_use` | 일시보호 이용 건수 | Temporary Protection Use | `Indicator` | Emergency or temporary protection use count where public. |
| `indicator:housing_linkage_count` | 주거연계 건수 | Housing Linkage Count | `Indicator` | Housing support referrals or outcomes where public. |
| `indicator:employment_linkage_count` | 취업연계 건수 | Employment Linkage Count | `Indicator` | Employment support linkage count where public. |
| `indicator:self_reliance_outcome` | 자립지원 성과 | Self-Reliance Outcome | `Indicator` | Aggregated public outcome indicator; no personal performance data. |

---

## 10. LifecycleEvent Entities

| Node ID | Korean Label | English Label | Entity Class | Description |
|---|---|---|---|---|
| `event:discovery` | 발견 | Discovery | `LifecycleEvent` | A person or group is identified through outreach, report, or public service contact. |
| `event:first_contact` | 최초접촉 | First Contact | `LifecycleEvent` | Initial engagement by outreach worker, center, local government, or service provider. |
| `event:initial_consultation` | 초기상담 | Initial Consultation | `LifecycleEvent` | Non-identifying assessment of urgent need and service direction. |
| `event:urgent_risk_check` | 위기상황 확인 | Urgent Risk Check | `LifecycleEvent` | Check for emergency health, safety, shelter, food, or protection needs. |
| `event:temporary_protection` | 일시보호 | Temporary Protection | `LifecycleEvent` | Short-term protection or emergency shelter-related event. |
| `event:facility_admission_consideration` | 시설입소 검토 | Facility Admission Consideration | `LifecycleEvent` | Consideration of facility-based service; actual admission rules vary by source. |
| `event:service_referral` | 서비스 연계 | Service Referral | `LifecycleEvent` | Referral to medical, mental health, income, housing, employment, or other resources. |
| `event:self_reliance_planning` | 자립계획 | Self-Reliance Planning | `LifecycleEvent` | Planning for self-reliance support at a non-identifiable ontology level. |
| `event:community_transition` | 지역사회 전환 | Community Transition | `LifecycleEvent` | Transition toward community living or housing stability. |
| `event:follow_up` | 사후관리 | Follow-Up | `LifecycleEvent` | Post-service follow-up concept; do not include individual records. |

---

## 11. NeedDomain Entities

| Node ID | Korean Label | English Label | Entity Class | Linked Services |
|---|---|---|---|---|
| `need:housing` | 주거 | Housing | `NeedDomain` | `service:housing_support_linkage`, `service:community_reintegration` |
| `need:income` | 소득 | Income | `NeedDomain` | `service:income_support_linkage`, `service:employment_support` |
| `need:healthcare` | 의료 | Healthcare | `NeedDomain` | `service:medical_referral` |
| `need:mental_health` | 정신건강 | Mental Health | `NeedDomain` | `service:mental_health_referral` |
| `need:addiction_support` | 중독지원 | Addiction Support | `NeedDomain` | `service:addiction_support_referral` |
| `need:identity_and_administration` | 신분·행정 | Identity and Administration | `NeedDomain` | `service:identity_recovery_support` |
| `need:food_and_hygiene` | 식사·위생 | Food and Hygiene | `NeedDomain` | `service:meal_support`, `service:hygiene_support` |
| `need:safety` | 안전 | Safety | `NeedDomain` | `service:emergency_protection`, `service:temporary_shelter` |
| `need:social_relationship` | 사회관계 | Social Relationship | `NeedDomain` | `service:case_management`, `service:community_reintegration` |

---

## 12. Retrieval Keywords

Use these terms to improve OpenCrab retrieval:

- 노숙인 복지 핵심 엔티티
- 노숙인 자립지원 핵심 개념
- homeless welfare core entities
- homelessness self-reliance ontology entities
- PersonGroup FacilityType Service Actor LegalSource PublicDataset Indicator LifecycleEvent
- 노숙인일시보호시설 노숙인자활시설 노숙인재활시설 노숙인요양시설 노숙인종합지원센터 쪽방상담소
- 거리상담 초기상담 응급보호 일시보호 의료연계 정신건강연계 주거지원 자립계획 사후관리
- public sources only no PII no internal documents

---

## 13. Exclusion Rules

The following must not become ontology entities or evidence chunks:

| Excluded Item | Reason |
|---|---|
| Resident names | Personally identifiable information |
| Resident registration numbers | Sensitive personal data |
| Phone numbers and home addresses | Personal data |
| Case notes and counseling records | Private case-management records |
| Donor names and donation details | Private donor information |
| Accounting ledgers and settlement files | Internal accounting records |
| Facility internal personnel files | Internal staffing records |
| Clinical diagnosis details | Medical privacy and professional judgment area |
| Internal audit responses | Non-public institutional records |
| Facility-specific unpublished rules | Not a public ontology source |

---

## 14. Quality Notes

- This file defines ontology seed concepts, not final legal classification.
- Legal and policy terms must be checked against the latest public source before operational use.
- Local government implementation can differ by region.
- The ontology should distinguish statutory facility types from public service sites.
- The ontology should distinguish general service flow from facility-specific internal procedures.
