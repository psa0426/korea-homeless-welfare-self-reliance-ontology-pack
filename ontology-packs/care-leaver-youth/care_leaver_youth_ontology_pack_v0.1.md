# 자립준비청년·보호종료아동 온톨로지 팩 v0.1

## 0. 팩 메타
- pack_title: 자립준비청년·보호종료아동 온톨로지 팩 v0.1
- english_title: Care Leaver and Transition Youth Ontology Pack
- category: general
- visibility: private
- intended_use: OpenCrab, GraphRAG, 전환기 자립지원 사례관리, 사후관리 표준화
- pii_policy: 실제 대상자/보호자 식별정보 금지

## 1. 목적과 범위
대한민국 자립준비청년, 보호종료아동, 아동양육시설 퇴소, 공동생활가정 퇴소, 가정위탁 종료, 자립수당, 자립정착금, 주거·교육·취업·심리정서 지원, 사후관리 체계를 구조화한다.

## 2. 설계 원칙
1. 보호종료 전후 전환기 연속성을 중심으로 설계한다.
2. 주거·교육·취업·정서·금융·생활기술 욕구를 통합 사정한다.
3. 위험요인과 보호요인을 동시 모델링한다.
4. 시설·위탁·사후관리기관의 연계 책임을 명시한다.
5. 개인정보 없이 구조화 지식 중심으로 작성한다.

## 3. 상위 클래스 체계
- CareLeaver, ProtectedChild, OutOfHomeCareYouth, ResidentialCareLeaver, GroupHomeLeaver, FosterCareLeaver
- TransitionNeed, HousingNeed, EducationNeed, EmploymentNeed, MentalHealthNeed, FinancialNeed, LifeSkillNeed, SocialSupportNeed
- RiskFactor, ProtectiveFactor, ServiceDisconnectionRisk, HousingInstabilityRisk, UnemploymentRisk
- CareLeaverCase, TransitionAssessment, SelfReliancePlan, AftercarePlan, ServicePlan, Referral, Monitoring, FollowUp
- SelfRelianceAllowance, SettlementGrant, HousingSupport, MentoringService, EducationSupport, EmploymentSupport
- AftercareSupportCenter, ChildWelfareFacility, FosterCareAgency, LocalGovernment
- Outcome, IndependentLivingOutcome, StabilityOutcome, SocialIntegrationOutcome

## 4. 핵심 엔티티
CareLeaver, ProtectedChild, OutOfHomeCareYouth, ResidentialCareLeaver, GroupHomeLeaver, FosterCareLeaver, TransitionNeed, HousingNeed, EducationNeed, EmploymentNeed, MentalHealthNeed, FinancialNeed, LifeSkillNeed, SocialSupportNeed, RiskFactor, ProtectiveFactor, CareLeaverCase, TransitionAssessment, SelfReliancePlan, AftercarePlan, ServicePlan, Referral, Monitoring, FollowUp, SelfRelianceAllowance, SettlementGrant, HousingSupport, MentoringService, AftercareSupportCenter, ChildWelfareFacility, FosterCareAgency, Outcome

## 5. 핵심 관계
- CareLeaver --hasNeed--> TransitionNeed
- CareLeaver --hasNeed--> HousingNeed
- CareLeaver --hasNeed--> EmploymentNeed
- CareLeaver --hasNeed--> MentalHealthNeed
- CareLeaver --subjectOf--> CareLeaverCase

- CareLeaverCase --hasTransitionAssessment--> TransitionAssessment
- CareLeaverCase --hasSelfReliancePlan--> SelfReliancePlan
- CareLeaverCase --hasAftercarePlan--> AftercarePlan
- CareLeaverCase --hasServicePlan--> ServicePlan
- CareLeaverCase --hasReferral--> Referral
- CareLeaverCase --monitoredBy--> Monitoring
- CareLeaverCase --followedBy--> FollowUp

- SelfReliancePlan --targets--> LifeSkillNeed
- SelfReliancePlan --targets--> EmploymentNeed
- AftercarePlan --supports--> FollowUp
- ServicePlan --targets--> HousingNeed
- ServicePlan --targets--> EducationNeed
- ServicePlan --targets--> FinancialNeed
- ServicePlan --mitigates--> RiskFactor

- Referral --connectsTo--> AftercareSupportCenter
- Referral --connectsTo--> ChildWelfareFacility
- Referral --connectsTo--> FosterCareAgency
- Referral --connectsTo--> LocalGovernment

- SettlementGrant --supports--> FinancialNeed
- SelfRelianceAllowance --supports--> TransitionNeed
- HousingSupport --targets--> HousingNeed
- MentoringService --supports--> SocialSupportNeed
- Intervention --produces--> IndependentLivingOutcome

## 6. 시드 트리플
1. CareLeaver --hasNeed--> TransitionNeed
2. CareLeaver --hasNeed--> HousingNeed
3. CareLeaver --hasNeed--> EducationNeed
4. CareLeaver --hasNeed--> EmploymentNeed
5. CareLeaver --hasNeed--> MentalHealthNeed
6. CareLeaver --hasNeed--> FinancialNeed
7. CareLeaver --hasNeed--> LifeSkillNeed
8. CareLeaver --subjectOf--> CareLeaverCase
9. ResidentialCareLeaver --hasNeed--> HousingNeed
10. GroupHomeLeaver --hasNeed--> EmploymentNeed
11. FosterCareLeaver --hasNeed--> SocialSupportNeed
12. CareLeaverCase --hasTransitionAssessment--> TransitionAssessment
13. CareLeaverCase --hasSelfReliancePlan--> SelfReliancePlan
14. CareLeaverCase --hasAftercarePlan--> AftercarePlan
15. CareLeaverCase --hasServicePlan--> ServicePlan
16. SelfReliancePlan --targets--> LifeSkillNeed
17. SelfReliancePlan --targets--> EmploymentNeed
18. ServicePlan --targets--> HousingNeed
19. ServicePlan --targets--> EducationNeed
20. ServicePlan --targets--> FinancialNeed
21. ServicePlan --mitigates--> HousingInstabilityRisk
22. ServicePlan --mitigates--> UnemploymentRisk
23. Referral --connectsTo--> AftercareSupportCenter
24. Referral --connectsTo--> ChildWelfareFacility
25. Referral --connectsTo--> FosterCareAgency
26. SettlementGrant --supports--> FinancialNeed
27. SelfRelianceAllowance --supports--> TransitionNeed
28. HousingSupport --targets--> HousingNeed
29. MentoringService --supports--> SocialSupportNeed
30. Monitoring --tracks--> IndependentLivingOutcome

## 7. 사례관리 또는 서비스 흐름
PreTransitionPlanning -> TransitionAssessment -> SelfReliancePlan -> ServicePlan -> Referral -> Monitoring -> AftercarePlan -> FollowUp -> CaseClosure

## 8. 위험요인 분류
- HousingInstabilityRisk
- UnemploymentRisk
- ServiceDisconnectionRisk
- FinancialVulnerabilityRisk
- MentalHealthDeteriorationRisk
- SocialIsolationRisk
- LifeSkillDeficitRisk

## 9. 보호요인 분류
- StableMentorRelationship
- EarlyAftercareEngagement
- HousingSupportAccess
- EducationContinuationSupport
- EmploymentTrainingParticipation
- FinancialCoachingSupport
- CommunitySupportNetwork

## 10. 추론 규칙
1. HousingNeed + HousingInstabilityRisk이면 HousingSupport를 우선 제안한다.
2. EmploymentNeed + UnemploymentRisk이면 직업훈련/고용연계를 우선 제안한다.
3. FinancialNeed가 있으면 SelfRelianceAllowance/SettlementGrant 연계를 필수 검토한다.
4. ServiceDisconnectionRisk가 있으면 AftercareSupportCenter 모니터링 주기 단축을 제안한다.
5. MentalHealthNeed가 있으면 심리지원/상담 연계를 SelfReliancePlan에 포함한다.

## 11. 검증 규칙
1. 모든 CareLeaverCase는 TransitionAssessment를 포함해야 한다.
2. SelfReliancePlan은 최소 1개 이상 LifeSkillNeed 또는 EmploymentNeed를 targets 해야 한다.
3. ServicePlan은 최소 1개 Need를 targets 해야 한다.
4. FinancialNeed 사례는 수당/정착금/금융지원 중 하나 이상과 연결되어야 한다.
5. Monitoring이 있으면 최소 1개 Outcome 추적 링크가 있어야 한다.
6. 개인 식별정보를 포함하지 않는다.

## 12. 질의 템플릿
- 자립준비청년·보호종료아동 온톨로지 팩의 핵심 엔티티와 관계를 요약해줘.
- 보호종료 이후 주거지원과 자립수당과 자립정착금은 어떤 욕구와 연결되는가?
- 자립준비청년의 자립계획과 사후관리계획은 어떻게 연결되는가?
- 아동양육시설 퇴소와 가정위탁 종료와 공동생활가정 퇴소 사례의 공통 지원은 무엇인가?
- AftercarePlan이 HousingNeed와 EmploymentNeed와 MentalHealthNeed에 제대로 연결되었는지 검증해줘.

## 13. 권장 소스 그룹
- 보건복지부 자립지원 정책·지침
- 아동권리보장원/지자체 사후관리 안내
- 자립수당·자립정착금 운영자료
- 주거/교육/고용 연계 공공안내

## 14. 개인정보·민감정보 제외 원칙
실제 이름, 주소, 연락처, 주민등록번호, 시설/위탁 식별번호, 내부 사례기록을 포함하지 않는다.

## 15. 향후 확장 후보
- 보호종료 전환시점 위험예측 규칙 강화
- 자립성과 지표(주거유지율/취업유지율) 세분화
- 멘토링 네트워크 품질지표 확장
