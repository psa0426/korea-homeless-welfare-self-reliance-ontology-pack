# 다문화·이주민 복지 온톨로지 팩 v0.1

## 0. 팩 메타
- pack_title: 다문화·이주민 복지 온톨로지 팩 v0.1
- english_title: Multicultural and Migrant Welfare Ontology Pack
- category: general
- visibility: private
- intended_use: OpenCrab, GraphRAG, 이주민 사례관리, 다기관 연계, 서비스 접근성 개선
- pii_policy: 실제 대상자/가구 식별정보 금지

## 1. 목적과 범위
대한민국 다문화가족, 결혼이민자, 외국인주민, 이주노동자, 난민, 중도입국청소년 지원 체계를 구조화한다.

## 2. 설계 원칙
1. 인권·비차별·접근권 중심으로 설계한다.
2. 언어·체류·노동·의료·교육·가족관계 욕구를 통합 사정한다.
3. 위험요인과 보호요인을 동시 모델링한다.
4. 통번역·법률·의료·교육의 다기관 연계를 기본 구조로 둔다.
5. 개인정보 없이 구조화 지식 중심으로 작성한다.

## 3. 상위 클래스 체계
- Migrant, ForeignResident, MarriageMigrant, MigrantWorker, Refugee
- MulticulturalFamily, MidEntryYouth, ChildOfMulticulturalFamily
- ResidenceStatus, LanguageNeed, InterpretationNeed, EducationNeed, LaborRightsNeed, MedicalAccessNeed, FamilyRelationshipNeed, LegalNeed
- DiscriminationRisk, SocialIsolationRisk, ServiceAccessRisk, RiskFactor, ProtectiveFactor
- MigrantWelfareCase, Assessment, ServicePlan, Referral, Monitoring, FollowUp
- FamilyCenter, MulticulturalFamilySupportCenter, ForeignWorkerSupportCenter, LegalAidOrganization, HealthcareProvider, School, PublicAgency, ImmigrationOffice
- Outcome, ServiceAccessOutcome, SocialIntegrationOutcome, RightsProtectionOutcome

## 4. 핵심 엔티티
Migrant, ForeignResident, MarriageMigrant, MigrantWorker, Refugee, MulticulturalFamily, MidEntryYouth, ChildOfMulticulturalFamily, ResidenceStatus, LanguageNeed, InterpretationNeed, EducationNeed, LaborRightsNeed, MedicalAccessNeed, FamilyRelationshipNeed, LegalNeed, DiscriminationRisk, SocialIsolationRisk, RiskFactor, ProtectiveFactor, MigrantWelfareCase, Assessment, ServicePlan, Referral, Monitoring, FamilyCenter, MulticulturalFamilySupportCenter, ForeignWorkerSupportCenter, LegalAidOrganization, HealthcareProvider, School, PublicAgency, ImmigrationOffice, Outcome

## 5. 핵심 관계
- Migrant --hasResidenceStatus--> ResidenceStatus
- Migrant --hasNeed--> LanguageNeed
- Migrant --hasNeed--> InterpretationNeed
- Migrant --hasNeed--> LegalNeed
- Migrant --hasNeed--> MedicalAccessNeed
- Migrant --exposedTo--> DiscriminationRisk
- Migrant --subjectOf--> MigrantWelfareCase

- MulticulturalFamily --hasNeed--> FamilySupportNeed
- MidEntryYouth --hasNeed--> EducationNeed
- MigrantWorker --hasNeed--> LaborRightsNeed

- MigrantWelfareCase --hasAssessment--> Assessment
- MigrantWelfareCase --hasServicePlan--> ServicePlan
- MigrantWelfareCase --hasReferral--> Referral
- MigrantWelfareCase --monitoredBy--> Monitoring
- MigrantWelfareCase --followedBy--> FollowUp

- ServicePlan --targets--> LanguageNeed
- ServicePlan --targets--> LegalNeed
- ServicePlan --targets--> MedicalAccessNeed
- ServicePlan --mitigates--> DiscriminationRisk
- ServicePlan --mitigates--> SocialIsolationRisk

- Referral --connectsTo--> FamilyCenter
- Referral --connectsTo--> MulticulturalFamilySupportCenter
- Referral --connectsTo--> ForeignWorkerSupportCenter
- Referral --connectsTo--> LegalAidOrganization
- Referral --connectsTo--> HealthcareProvider
- Referral --connectsTo--> School
- Referral --connectsTo--> ImmigrationOffice

- InterpretationSupport --supports--> ServiceAccess
- Organization --provides--> Service
- Service --produces--> Outcome

## 6. 시드 트리플
1. Migrant --hasResidenceStatus--> ResidenceStatus
2. Migrant --hasNeed--> LanguageNeed
3. Migrant --hasNeed--> InterpretationNeed
4. Migrant --hasNeed--> LegalNeed
5. Migrant --hasNeed--> MedicalAccessNeed
6. Migrant --exposedTo--> DiscriminationRisk
7. Migrant --exposedTo--> SocialIsolationRisk
8. Migrant --subjectOf--> MigrantWelfareCase
9. MarriageMigrant --hasNeed--> FamilyRelationshipNeed
10. MigrantWorker --hasNeed--> LaborRightsNeed
11. Refugee --hasNeed--> LegalNeed
12. MidEntryYouth --hasNeed--> EducationNeed
13. MigrantWelfareCase --hasAssessment--> Assessment
14. MigrantWelfareCase --hasServicePlan--> ServicePlan
15. ServicePlan --targets--> LanguageNeed
16. ServicePlan --targets--> LegalNeed
17. ServicePlan --targets--> MedicalAccessNeed
18. ServicePlan --mitigates--> DiscriminationRisk
19. ServicePlan --mitigates--> SocialIsolationRisk
20. Referral --connectsTo--> FamilyCenter
21. Referral --connectsTo--> ForeignWorkerSupportCenter
22. Referral --connectsTo--> LegalAidOrganization
23. Referral --connectsTo--> HealthcareProvider
24. Referral --connectsTo--> School
25. Referral --connectsTo--> ImmigrationOffice
26. MulticulturalFamilySupportCenter --provides--> FamilySupportService
27. ForeignWorkerSupportCenter --provides--> LaborRightsCounseling
28. LegalAidOrganization --provides--> LegalSupport
29. InterpretationSupport --supports--> ServiceAccess
30. Service --produces--> SocialIntegrationOutcome
31. Monitoring --tracks--> ServiceAccessOutcome

## 7. 사례관리 또는 서비스 흐름
Intake -> Screening -> Assessment -> ServicePlan -> Referral -> Monitoring -> FollowUp -> CaseClosure

## 8. 위험요인 분류
- LanguageBarrierRisk
- LegalStatusInstabilityRisk
- LaborExploitationRisk
- MedicalAccessBarrierRisk
- EducationDiscontinuityRisk
- DiscriminationRisk
- SocialIsolationRisk
- ServiceDisconnectionRisk

## 9. 보호요인 분류
- InterpretationSupportAccess
- StableResidenceStatus
- CommunitySupportNetwork
- LegalAidAccess
- SchoolAdaptationSupport
- HealthcareLinkage
- FamilySupportEngagement

## 10. 추론 규칙
1. LanguageNeed + InterpretationNeed가 있으면 통번역지원을 우선 제안한다.
2. LegalNeed가 있고 체류불안정이면 ImmigrationOffice + LegalAidOrganization 동시 연계를 제안한다.
3. MigrantWorker의 LaborRightsNeed가 있으면 노동권 상담과 법률지원을 함께 제안한다.
4. MidEntryYouth 사례는 EducationNeed가 있으면 학교적응지원과 언어지원을 결합한다.
5. DiscriminationRisk가 높으면 심리사회지원과 권리옹호 연계를 강화한다.

## 11. 검증 규칙
1. 모든 MigrantWelfareCase는 최소 1개의 Assessment를 가져야 한다.
2. ServicePlan은 최소 1개의 Need를 targets 해야 한다.
3. LegalNeed 사례는 LegalAidOrganization 또는 ImmigrationOffice 연계가 있어야 한다.
4. LanguageNeed 사례는 InterpretationSupport 또는 언어교육 연계가 있어야 한다.
5. Monitoring이 있으면 최소 1개의 Outcome 추적 링크가 있어야 한다.
6. 개인 식별정보를 포함하지 않는다.

## 12. 질의 템플릿
- 다문화·이주민 복지 온톨로지 팩의 핵심 엔티티와 관계를 요약해줘.
- 결혼이민자의 언어욕구와 가족관계 욕구와 법률욕구는 어떤 서비스와 연결되는가?
- 이주노동자 사례에서 노동권 지원과 의료접근성 지원은 어떻게 연결되는가?
- 중도입국청소년에게 필요한 한국어교육과 학교적응 지원은 무엇인가?
- 가족센터와 외국인노동자지원기관과 출입국기관의 역할 차이를 설명해줘.
- ServicePlan이 LanguageNeed와 LegalNeed에 제대로 연결되었는지 검증해줘.

## 13. 권장 소스 그룹
- 국가법령정보센터: 다문화·이주민 관련 법령
- 여성가족부/고용노동부/법무부: 관련 정책·지침
- 지자체 다문화가족지원센터 안내자료
- 공공데이터포털/KOSIS 이주민 통계

## 14. 개인정보·민감정보 제외 원칙
실제 이름, 주소, 연락처, 외국인등록 식별정보, 체류 관련 민감 식별값, 내부 사례기록을 포함하지 않는다.

## 15. 향후 확장 후보
- 체류자격 변동 타임라인 모델
- 이주노동자 산업별 위험요인 세분화
- 다문화가족 아동 교육성과 지표 확장
