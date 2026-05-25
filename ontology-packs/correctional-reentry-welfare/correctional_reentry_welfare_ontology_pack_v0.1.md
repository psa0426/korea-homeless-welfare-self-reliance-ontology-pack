# 교정복지·출소자 자립지원 온톨로지 팩 v0.1

## 0. 팩 메타
- pack_title: 교정복지·출소자 자립지원 온톨로지 팩 v0.1
- english_title: Correctional Welfare and Reentry Support Ontology Pack
- category: document_upload
- visibility: private
- intended_use: OpenCrab, GraphRAG, 출소자 전환기 사례관리, 재범위험 완화, 사회복귀 서비스 매칭
- pii_policy: 실제 출소자/가족/종사자 식별정보 금지

## 1. 목적과 범위
교정복지, 출소자 자립지원, 보호관찰, 갱생보호, 주거·고용·가족관계 회복, 중독·정신건강 연계, 법률지원, 사회복귀 체계를 구조화한다.

## 2. 설계 원칙
1. 사회복귀와 안전을 동시 고려한다.
2. 주거·고용·가족관계·정신건강·중독지원 욕구를 통합 사정한다.
3. 재범위험과 보호요인을 동시 모델링한다.
4. 보호관찰·갱생보호·고용·의료·복지 다기관 연계를 명시한다.
5. 개인정보 없이 구조화 지식 중심으로 설계한다.

## 3. 상위 클래스 체계
### 3.1 Person
- ReentryPerson
- FormerlyIncarceratedPerson
- ProbationClient
- ProtectedPerson
- FamilyMember
- CaseWorker

### 3.2 Need and Risk
- ReentryNeed
- HousingNeed
- EmploymentNeed
- FamilyRelationshipNeed
- MentalHealthNeed
- AddictionSupportNeed
- LegalNeed
- IdentityRecoveryNeed
- RecidivismRisk
- SocialStigmaRisk
- HousingInstability
- UnemploymentRisk
- RiskFactor
- ProtectiveFactor

### 3.3 Case Management
- CorrectionalWelfareCase
- Intake
- Screening
- ReentryAssessment
- RiskAssessment
- ReentryPlan
- ServicePlan
- Referral
- Monitoring
- FollowUp
- CaseClosure

### 3.4 Service and Organization
- ReentrySupportService
- HousingSupport
- EmploymentSupport
- FamilyMediationService
- MentalHealthService
- AddictionTreatmentService
- LegalSupport
- IdentityRecoverySupport
- ProbationOffice
- KoreaRehabilitationAgency
- EmploymentCenter
- HousingSupportOrganization
- MentalHealthWelfareCenter
- AddictionSupportCenter
- LegalAidOrganization

### 3.5 Legal and Outcome
- LegalFramework
- PolicyProgram
- Outcome
- CommunityReintegrationOutcome
- RecidivismReductionOutcome
- EmploymentStabilityOutcome
- HousingStabilityOutcome

## 4. 핵심 엔티티
ReentryPerson, FormerlyIncarceratedPerson, ProbationClient, ProtectedPerson, ReentryNeed, HousingNeed, EmploymentNeed, FamilyRelationshipNeed, MentalHealthNeed, AddictionSupportNeed, LegalNeed, IdentityRecoveryNeed, RecidivismRisk, SocialStigmaRisk, HousingInstability, UnemploymentRisk, RiskFactor, ProtectiveFactor, CorrectionalWelfareCase, ReentryAssessment, RiskAssessment, ReentryPlan, ServicePlan, Referral, Monitoring, FollowUp, ProbationOffice, KoreaRehabilitationAgency, EmploymentCenter, HousingSupportOrganization, MentalHealthWelfareCenter, AddictionSupportCenter, LegalAidOrganization, Outcome

## 5. 핵심 관계
- ReentryPerson --hasNeed--> ReentryNeed
- ReentryPerson --hasNeed--> HousingNeed
- ReentryPerson --hasNeed--> EmploymentNeed
- ReentryPerson --hasNeed--> FamilyRelationshipNeed
- ReentryPerson --hasNeed--> MentalHealthNeed
- ReentryPerson --hasNeed--> AddictionSupportNeed
- ReentryPerson --hasNeed--> LegalNeed
- ReentryPerson --exposedTo--> RecidivismRisk
- ReentryPerson --exposedTo--> SocialStigmaRisk
- ReentryPerson --subjectOf--> CorrectionalWelfareCase

- CorrectionalWelfareCase --hasReentryAssessment--> ReentryAssessment
- CorrectionalWelfareCase --hasRiskAssessment--> RiskAssessment
- CorrectionalWelfareCase --hasReentryPlan--> ReentryPlan
- CorrectionalWelfareCase --hasServicePlan--> ServicePlan
- CorrectionalWelfareCase --hasReferral--> Referral
- CorrectionalWelfareCase --monitoredBy--> Monitoring
- CorrectionalWelfareCase --followedBy--> FollowUp

- ReentryPlan --targets--> HousingNeed
- ReentryPlan --targets--> EmploymentNeed
- ReentryPlan --targets--> FamilyRelationshipNeed
- ServicePlan --mitigates--> RecidivismRisk
- ServicePlan --mitigates--> UnemploymentRisk

- Referral --connectsTo--> ProbationOffice
- Referral --connectsTo--> KoreaRehabilitationAgency
- Referral --connectsTo--> EmploymentCenter
- Referral --connectsTo--> HousingSupportOrganization
- Referral --connectsTo--> MentalHealthWelfareCenter
- Referral --connectsTo--> AddictionSupportCenter
- Referral --connectsTo--> LegalAidOrganization

- Organization --provides--> Service
- Intervention --produces--> CommunityReintegrationOutcome

## 6. 시드 트리플
1. ReentryPerson --hasNeed--> ReentryNeed
2. ReentryPerson --hasNeed--> HousingNeed
3. ReentryPerson --hasNeed--> EmploymentNeed
4. ReentryPerson --hasNeed--> FamilyRelationshipNeed
5. ReentryPerson --hasNeed--> MentalHealthNeed
6. ReentryPerson --hasNeed--> AddictionSupportNeed
7. ReentryPerson --hasNeed--> LegalNeed
8. ReentryPerson --exposedTo--> RecidivismRisk
9. ReentryPerson --exposedTo--> SocialStigmaRisk
10. ReentryPerson --exposedTo--> HousingInstability
11. ReentryPerson --exposedTo--> UnemploymentRisk
12. ReentryPerson --subjectOf--> CorrectionalWelfareCase
13. CorrectionalWelfareCase --hasReentryAssessment--> ReentryAssessment
14. CorrectionalWelfareCase --hasRiskAssessment--> RiskAssessment
15. CorrectionalWelfareCase --hasReentryPlan--> ReentryPlan
16. ReentryPlan --targets--> HousingNeed
17. ReentryPlan --targets--> EmploymentNeed
18. ReentryPlan --targets--> FamilyRelationshipNeed
19. ServicePlan --mitigates--> RecidivismRisk
20. ServicePlan --mitigates--> UnemploymentRisk
21. Referral --connectsTo--> ProbationOffice
22. Referral --connectsTo--> KoreaRehabilitationAgency
23. Referral --connectsTo--> EmploymentCenter
24. Referral --connectsTo--> HousingSupportOrganization
25. Referral --connectsTo--> MentalHealthWelfareCenter
26. Referral --connectsTo--> AddictionSupportCenter
27. Referral --connectsTo--> LegalAidOrganization
28. Intervention --produces--> CommunityReintegrationOutcome
29. Monitoring --tracks--> RecidivismReductionOutcome
30. FollowUp --supports--> HousingStabilityOutcome

## 7. 사례관리 또는 서비스 흐름
Intake -> Screening -> ReentryAssessment -> RiskAssessment -> ReentryPlan -> ServicePlan -> Referral -> Monitoring -> FollowUp -> CaseClosure

## 8. 위험요인 분류
- RecidivismRisk
- SocialStigmaRisk
- HousingInstability
- UnemploymentRisk
- FamilyConflictRisk
- MentalHealthRisk
- AddictionRelapseRisk
- ServiceDisconnectionRisk

## 9. 보호요인 분류
- StableHousingAccess
- EmploymentPlacementSupport
- ProbationEngagement
- FamilySupportReconnection
- MentalHealthTreatmentContinuity
- AddictionRecoveryProgramParticipation
- LegalSupportAccess
- CommunityMentoring

## 10. 추론 규칙
1. HousingNeed + HousingInstability가 있으면 HousingSupportOrganization 연계를 우선 제안한다.
2. EmploymentNeed + UnemploymentRisk가 있으면 EmploymentCenter 연계를 우선 제안한다.
3. AddictionSupportNeed + AddictionRelapseRisk가 있으면 AddictionSupportCenter 연계를 강화한다.
4. MentalHealthNeed가 있으면 MentalHealthWelfareCenter 연계를 ServicePlan에 포함한다.
5. RecidivismRisk가 높으면 Monitoring 주기를 단축하고 ProbationOffice 협업을 강화한다.

## 11. 검증 규칙
1. 모든 CorrectionalWelfareCase는 ReentryAssessment를 포함해야 한다.
2. 고위험 사례는 RiskAssessment를 반드시 포함해야 한다.
3. ReentryPlan은 최소 1개 Need를 targets 해야 한다.
4. ServicePlan은 최소 1개 RiskFactor를 mitigates 해야 한다.
5. Referral은 최소 1개 Organization과 연결되어야 한다.
6. Monitoring이 있으면 최소 1개 Outcome 추적 링크가 있어야 한다.
7. 개인 식별정보를 포함하지 않는다.

## 12. 질의 템플릿
- 교정복지·출소자 자립지원 온톨로지 팩의 핵심 엔티티와 관계를 요약해줘.
- 출소자 자립지원에서 주거지원과 취업지원과 가족관계 회복은 어떻게 연결되는가?
- 보호관찰 대상자의 재범위험과 서비스계획은 어떤 관계로 연결되는가?
- 갱생보호기관과 고용센터와 정신건강복지센터의 역할 차이를 설명해줘.
- ReentryPlan이 HousingNeed와 EmploymentNeed와 RecidivismRisk에 제대로 연결되었는지 검증해줘.

## 13. 권장 소스 그룹
- 법무부/보호관찰 관련 공개자료
- 한국법무보호복지공단 공개자료
- 고용노동부 취업지원 자료
- 정신건강·중독지원 공공자료
- 국가법령정보센터 관련 법령

## 14. 개인정보·민감정보 제외 원칙
실제 이름, 주소, 연락처, 수형·사건 식별정보, 보호관찰 개인기록, 의료기록 식별정보, 내부 사례기록을 포함하지 않는다.

## 15. 향후 확장 후보
- 재범위험 조기경보 규칙 세분화
- 출소 후 6~24개월 추적지표 온톨로지
- 가족관계 회복 프로그램 성과모델 확장
