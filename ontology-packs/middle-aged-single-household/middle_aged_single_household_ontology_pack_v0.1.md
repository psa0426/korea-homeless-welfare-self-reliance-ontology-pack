# 중장년·1인가구·고독사 예방 온톨로지 팩 v0.1

## 0. 팩 메타
- pack_title: 중장년·1인가구·고독사 예방 온톨로지 팩 v0.1
- english_title: Middle-Aged Single Household and Lonely Death Prevention Ontology Pack
- category: general
- visibility: private
- intended_use: OpenCrab, GraphRAG, 위기가구 발굴·안부확인·고독사 예방 사례관리
- pii_policy: 실제 대상자 식별정보 금지

## 1. 목적과 범위
대한민국 중장년 1인가구, 사회적 고립, 고독사 위험, 위기가구 발굴, 안부확인, 방문상담, 지역사회 관계망 형성, 긴급지원 연계 체계를 구조화한다.

## 2. 설계 원칙
1. 조기발굴-즉시개입-지속모니터링 흐름을 중심으로 설계한다.
2. 건강·정신건강·주거·소득·관계망을 통합 사정한다.
3. 사회적 고립 위험과 보호요인을 동시 모델링한다.
4. 행정복지센터-보건소-정신건강복지센터-민간기관 협업을 명시한다.
5. 개인정보 없이 구조화 지식 중심으로 작성한다.

## 3. 상위 클래스 체계
- MiddleAgedPerson, SinglePersonHousehold, SociallyIsolatedPerson
- LonelyDeathRisk, SocialIsolationRisk, HealthRisk, MentalHealthRisk, AlcoholRisk, EmploymentLossRisk, HousingInstability, RiskFactor, ProtectiveFactor
- EconomicNeed, HealthNeed, MentalHealthNeed, HousingNeed, SocialRelationshipNeed, EmergencyNeed
- CrisisHouseholdCase, Outreach, InitialContact, WelfareCheck, HomeVisit, Assessment, RiskAssessment, ServicePlan, Referral, Monitoring, FollowUp
- CommunityNetwork, LocalGovernment, CommunityServiceCenter, PublicHealthCenter, MentalHealthWelfareCenter, WelfareOrganization
- Outcome, RiskReductionOutcome, SocialConnectionOutcome, StabilityOutcome

## 4. 핵심 엔티티
MiddleAgedPerson, SinglePersonHousehold, SociallyIsolatedPerson, LonelyDeathRisk, SocialIsolationRisk, HealthRisk, MentalHealthRisk, AlcoholRisk, EmploymentLossRisk, HousingInstability, EconomicNeed, HealthNeed, MentalHealthNeed, HousingNeed, SocialRelationshipNeed, EmergencyNeed, RiskFactor, ProtectiveFactor, CrisisHouseholdCase, Outreach, InitialContact, WelfareCheck, HomeVisit, Assessment, RiskAssessment, ServicePlan, Referral, Monitoring, FollowUp, CommunityNetwork, LocalGovernment, CommunityServiceCenter, PublicHealthCenter, MentalHealthWelfareCenter, WelfareOrganization, Outcome

## 5. 핵심 관계
- SinglePersonHousehold --exposedTo--> SocialIsolationRisk
- SocialIsolationRisk --increasesRiskOf--> LonelyDeathRisk
- MiddleAgedPerson --hasNeed--> EconomicNeed
- MiddleAgedPerson --hasNeed--> HealthNeed
- MiddleAgedPerson --hasNeed--> HousingNeed
- MiddleAgedPerson --subjectOf--> CrisisHouseholdCase

- CrisisHouseholdCase --hasOutreach--> Outreach
- CrisisHouseholdCase --hasInitialContact--> InitialContact
- CrisisHouseholdCase --hasWelfareCheck--> WelfareCheck
- CrisisHouseholdCase --hasHomeVisit--> HomeVisit
- CrisisHouseholdCase --hasAssessment--> Assessment
- CrisisHouseholdCase --hasRiskAssessment--> RiskAssessment
- CrisisHouseholdCase --hasServicePlan--> ServicePlan
- CrisisHouseholdCase --hasReferral--> Referral
- CrisisHouseholdCase --monitoredBy--> Monitoring
- CrisisHouseholdCase --followedBy--> FollowUp

- ServicePlan --targets--> SocialRelationshipNeed
- ServicePlan --targets--> HousingNeed
- ServicePlan --targets--> EconomicNeed
- ServicePlan --mitigates--> LonelyDeathRisk
- ServicePlan --mitigates--> SocialIsolationRisk

- Referral --connectsTo--> CommunityServiceCenter
- Referral --connectsTo--> PublicHealthCenter
- Referral --connectsTo--> MentalHealthWelfareCenter
- Referral --connectsTo--> WelfareOrganization

- CommunityNetwork --provides--> WelfareCheck
- Monitoring --tracks--> RiskReductionOutcome
- Intervention --produces--> SocialConnectionOutcome

## 6. 시드 트리플
1. SinglePersonHousehold --exposedTo--> SocialIsolationRisk
2. SocialIsolationRisk --increasesRiskOf--> LonelyDeathRisk
3. MiddleAgedPerson --hasNeed--> EconomicNeed
4. MiddleAgedPerson --hasNeed--> HealthNeed
5. MiddleAgedPerson --hasNeed--> HousingNeed
6. MiddleAgedPerson --hasNeed--> SocialRelationshipNeed
7. MiddleAgedPerson --exposedTo--> EmploymentLossRisk
8. MiddleAgedPerson --exposedTo--> AlcoholRisk
9. MiddleAgedPerson --subjectOf--> CrisisHouseholdCase
10. CrisisHouseholdCase --hasOutreach--> Outreach
11. CrisisHouseholdCase --hasInitialContact--> InitialContact
12. CrisisHouseholdCase --hasWelfareCheck--> WelfareCheck
13. CrisisHouseholdCase --hasHomeVisit--> HomeVisit
14. CrisisHouseholdCase --hasAssessment--> Assessment
15. CrisisHouseholdCase --hasRiskAssessment--> RiskAssessment
16. CrisisHouseholdCase --hasServicePlan--> ServicePlan
17. ServicePlan --targets--> SocialRelationshipNeed
18. ServicePlan --targets--> HousingNeed
19. ServicePlan --targets--> EconomicNeed
20. ServicePlan --mitigates--> LonelyDeathRisk
21. ServicePlan --mitigates--> SocialIsolationRisk
22. Referral --connectsTo--> CommunityServiceCenter
23. Referral --connectsTo--> PublicHealthCenter
24. Referral --connectsTo--> MentalHealthWelfareCenter
25. Referral --connectsTo--> WelfareOrganization
26. CommunityNetwork --provides--> WelfareCheck
27. Monitoring --tracks--> RiskReductionOutcome
28. Intervention --produces--> StabilityOutcome

## 7. 사례관리 또는 서비스 흐름
Outreach -> InitialContact -> WelfareCheck -> HomeVisit -> Assessment -> RiskAssessment -> ServicePlan -> Referral -> Monitoring -> FollowUp -> CaseClosure

## 8. 위험요인 분류
- SocialIsolationRisk
- LonelyDeathRisk
- MentalHealthRisk
- AlcoholRisk
- EmploymentLossRisk
- HousingInstabilityRisk
- EconomicCrisisRisk
- ServiceDisconnectionRisk

## 9. 보호요인 분류
- CommunityNetworkConnection
- RegularWelfareCheck
- TrustedContactPerson
- HealthcareContinuity
- HousingStabilitySupport
- IncomeSupportAccess
- MentalHealthServiceEngagement

## 10. 추론 규칙
1. SocialIsolationRisk + SinglePersonHousehold이면 안부확인 주기 강화와 방문상담을 우선 제안한다.
2. LonelyDeathRisk가 높으면 CommunityNetwork와 긴급연계를 동시 활성화한다.
3. HousingInstability + EmploymentLossRisk 동시 발생 시 주거·생계 지원을 병행 제안한다.
4. AlcoholRisk + MentalHealthRisk 동시 발생 시 정신건강복지센터 연계를 우선 검토한다.
5. WelfareCheck 누락 사례는 Monitoring 단계 이전 보완 경고를 생성한다.

## 11. 검증 규칙
1. 모든 CrisisHouseholdCase는 최소 1개의 Assessment를 가져야 한다.
2. 고위험 사례는 RiskAssessment를 반드시 포함해야 한다.
3. ServicePlan은 최소 1개의 Need를 targets 해야 한다.
4. LonelyDeathRisk 사례는 최소 1개 이상 관계망 개입 또는 안부확인 개입이 있어야 한다.
5. Monitoring이 있으면 최소 1개의 Outcome 추적 링크가 있어야 한다.
6. 개인 식별정보를 포함하지 않는다.

## 12. 질의 템플릿
- 중장년·1인가구·고독사 예방 온톨로지 팩의 핵심 엔티티와 관계를 요약해줘.
- 사회적 고립 위험과 고독사 위험은 어떻게 연결되는가?
- 중장년 1인가구 사례에서 안부확인과 방문상담과 긴급지원은 어떻게 연결되는가?
- 실직과 건강위험과 주거불안이 함께 있는 위기가구에 필요한 서비스는 무엇인가?
- 행정복지센터와 보건소와 정신건강복지센터는 고독사 예방에서 어떤 역할을 하는가?
- ServicePlan이 SocialRelationshipNeed와 LonelyDeathRisk에 제대로 연결되었는지 검증해줘.

## 13. 권장 소스 그룹
- 보건복지부 고독사 예방 정책 자료
- 지자체 위기가구 발굴·안부확인 사업 안내
- 정신건강복지센터/보건소 공개자료
- 공공데이터포털/KOSIS 1인가구·고립 관련 통계

## 14. 개인정보·민감정보 제외 원칙
실제 이름, 주소, 연락처, 주민등록번호, 건강상태 식별정보, 내부 사례기록을 포함하지 않는다.

## 15. 향후 확장 후보
- 고독사 위험신호 조기탐지 규칙 확장
- 생활인프라 단절지표(전기/가스/통신) 연계 모델
- 지역관계망 회복 성과지표 세분화
