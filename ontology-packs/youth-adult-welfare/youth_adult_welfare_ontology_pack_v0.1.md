# 청년복지·고립은둔청년 온톨로지 팩 v0.1

## 0. 팩 메타
- pack_title: 청년복지·고립은둔청년 온톨로지 팩 v0.1
- english_title: Young Adult Welfare and Socially Isolated Youth Ontology Pack
- category: general
- visibility: private
- intended_use: OpenCrab, GraphRAG, 고립은둔청년 사례관리, 주거·고용·마음건강 연계
- pii_policy: 실제 청년/가구 식별정보 금지

## 1. 목적과 범위
대한민국 청년복지, 고립은둔청년, 위기청년, 가족돌봄청년, 청년주거, 청년마음건강, 취업지원, 부채·금융지원 체계를 구조화한다.

## 2. 설계 원칙
1. 청년의 자기결정권과 회복경로를 중심으로 설계한다.
2. 주거·고용·정신건강·금융·사회참여를 통합 사정한다.
3. 사회적 고립 위험과 보호요인을 동시 모델링한다.
4. 지역 청년지원 인프라 다기관 연계를 명시한다.
5. 개인정보 없이 구조화 지식 중심으로 작성한다.

## 3. 상위 클래스 체계
- YoungAdult, IsolatedYouth, HiddenYouth, AtRiskYoungAdult, FamilyCareYoungAdult, CareLeaverYoungAdult, NEETYouth
- HousingNeed, EmploymentNeed, MentalHealthNeed, DebtNeed, EducationNeed, SocialParticipationNeed
- FamilyCareBurden, SocialIsolationRisk, UnemploymentRisk, DebtRisk, HousingInstability, RiskFactor, ProtectiveFactor
- YoungAdultWelfareCase, Assessment, RiskAssessment, ServicePlan, Referral, Monitoring, FollowUp
- YouthCenter, EmploymentCenter, MentalHealthWelfareCenter, HousingWelfareCenter, DebtCounselingAgency
- Outcome, SocialParticipationOutcome, EmploymentStabilityOutcome, HousingStabilityOutcome

## 4. 핵심 엔티티
YoungAdult, IsolatedYouth, HiddenYouth, AtRiskYoungAdult, FamilyCareYoungAdult, CareLeaverYoungAdult, NEETYouth, HousingNeed, EmploymentNeed, MentalHealthNeed, DebtNeed, EducationNeed, SocialParticipationNeed, FamilyCareBurden, SocialIsolationRisk, UnemploymentRisk, DebtRisk, HousingInstability, RiskFactor, ProtectiveFactor, YoungAdultWelfareCase, Assessment, RiskAssessment, ServicePlan, Referral, Monitoring, YouthCenter, EmploymentCenter, MentalHealthWelfareCenter, HousingWelfareCenter, DebtCounselingAgency, Outcome

## 5. 핵심 관계
- YoungAdult --hasNeed--> HousingNeed
- YoungAdult --hasNeed--> EmploymentNeed
- YoungAdult --hasNeed--> MentalHealthNeed
- YoungAdult --hasNeed--> DebtNeed
- YoungAdult --exposedTo--> SocialIsolationRisk
- YoungAdult --exposedTo--> UnemploymentRisk
- YoungAdult --subjectOf--> YoungAdultWelfareCase

- IsolatedYouth --exposedTo--> SocialIsolationRisk
- FamilyCareYoungAdult --hasNeed--> FamilyCareSupportNeed
- NEETYouth --hasNeed--> EmploymentNeed

- YoungAdultWelfareCase --hasAssessment--> Assessment
- YoungAdultWelfareCase --hasRiskAssessment--> RiskAssessment
- YoungAdultWelfareCase --hasServicePlan--> ServicePlan
- YoungAdultWelfareCase --hasReferral--> Referral
- YoungAdultWelfareCase --monitoredBy--> Monitoring
- YoungAdultWelfareCase --followedBy--> FollowUp

- ServicePlan --targets--> HousingNeed
- ServicePlan --targets--> EmploymentNeed
- ServicePlan --targets--> MentalHealthNeed
- ServicePlan --targets--> DebtNeed
- ServicePlan --mitigates--> SocialIsolationRisk
- ServicePlan --mitigates--> UnemploymentRisk

- Referral --connectsTo--> YouthCenter
- Referral --connectsTo--> EmploymentCenter
- Referral --connectsTo--> MentalHealthWelfareCenter
- Referral --connectsTo--> HousingWelfareCenter
- Referral --connectsTo--> DebtCounselingAgency

- YouthCenter --provides--> YouthSupportService
- EmploymentCenter --provides--> EmploymentSupportService
- MentalHealthWelfareCenter --provides--> MentalHealthSupportService
- HousingWelfareCenter --provides--> HousingSupportService
- DebtCounselingAgency --provides--> DebtManagementSupport
- Intervention --produces--> SocialParticipationOutcome

## 6. 시드 트리플
1. YoungAdult --hasNeed--> HousingNeed
2. YoungAdult --hasNeed--> EmploymentNeed
3. YoungAdult --hasNeed--> MentalHealthNeed
4. YoungAdult --hasNeed--> DebtNeed
5. YoungAdult --exposedTo--> SocialIsolationRisk
6. YoungAdult --exposedTo--> UnemploymentRisk
7. YoungAdult --exposedTo--> DebtRisk
8. YoungAdult --subjectOf--> YoungAdultWelfareCase
9. IsolatedYouth --exposedTo--> SocialIsolationRisk
10. HiddenYouth --hasNeed--> SocialParticipationNeed
11. FamilyCareYoungAdult --hasNeed--> FamilyCareSupportNeed
12. NEETYouth --hasNeed--> EmploymentNeed
13. YoungAdultWelfareCase --hasAssessment--> Assessment
14. YoungAdultWelfareCase --hasRiskAssessment--> RiskAssessment
15. YoungAdultWelfareCase --hasServicePlan--> ServicePlan
16. ServicePlan --targets--> HousingNeed
17. ServicePlan --targets--> EmploymentNeed
18. ServicePlan --targets--> MentalHealthNeed
19. ServicePlan --targets--> DebtNeed
20. ServicePlan --mitigates--> SocialIsolationRisk
21. ServicePlan --mitigates--> UnemploymentRisk
22. Referral --connectsTo--> YouthCenter
23. Referral --connectsTo--> EmploymentCenter
24. Referral --connectsTo--> MentalHealthWelfareCenter
25. Referral --connectsTo--> HousingWelfareCenter
26. Referral --connectsTo--> DebtCounselingAgency
27. YouthCenter --provides--> YouthSupportService
28. EmploymentCenter --provides--> EmploymentSupportService
29. MentalHealthWelfareCenter --provides--> MentalHealthSupportService
30. HousingWelfareCenter --provides--> HousingSupportService
31. DebtCounselingAgency --provides--> DebtManagementSupport
32. Intervention --produces--> SocialParticipationOutcome

## 7. 사례관리 또는 서비스 흐름
Intake -> Screening -> Assessment -> RiskAssessment -> ServicePlan -> Referral -> Monitoring -> FollowUp -> CaseClosure

## 8. 위험요인 분류
- SocialIsolationRisk
- UnemploymentRisk
- DebtRisk
- HousingInstabilityRisk
- MentalHealthDeteriorationRisk
- FamilyCareOverloadRisk
- ServiceDisconnectionRisk

## 9. 보호요인 분류
- YouthCenterEngagement
- StableHousingAccess
- EmploymentTrainingParticipation
- MentalHealthSupportContinuity
- DebtCounselingEngagement
- PeerSupportNetwork
- FamilySupportAvailability

## 10. 추론 규칙
1. SocialIsolationRisk + MentalHealthNeed가 있으면 정신건강 연계를 우선 제안한다.
2. HousingNeed + UnemploymentRisk 동시 발생 시 주거지원과 취업지원을 병행 제안한다.
3. DebtNeed가 있으면 DebtCounselingAgency 연계를 필수 검토한다.
4. FamilyCareBurden이 높으면 돌봄부담 완화 서비스와 경제지원을 함께 검토한다.
5. NEETYouth 사례는 EmploymentNeed 또는 EducationNeed 중 하나 이상 계획에 포함한다.

## 11. 검증 규칙
1. 모든 YoungAdultWelfareCase는 최소 1개의 Assessment를 가져야 한다.
2. 고위험 사례는 RiskAssessment를 반드시 포함해야 한다.
3. ServicePlan은 최소 1개의 Need를 targets 해야 한다.
4. DebtNeed 사례는 DebtCounselingAgency 또는 금융지원 연계가 있어야 한다.
5. Monitoring이 있으면 최소 1개의 Outcome 추적 링크가 있어야 한다.
6. 개인 식별정보를 포함하지 않는다.

## 12. 질의 템플릿
- 청년복지·고립은둔청년 온톨로지 팩의 핵심 엔티티와 관계를 요약해줘.
- 고립은둔청년 사례에서 사회적 고립 위험과 정신건강 욕구는 어떤 서비스와 연결되는가?
- 가족돌봄청년에게 필요한 돌봄부담 완화와 경제지원과 상담지원은 무엇인가?
- 청년주거와 취업지원과 마음건강 서비스는 어떻게 연결되는가?
- 청년센터와 고용센터와 정신건강복지센터의 역할 차이를 설명해줘.
- ServicePlan이 HousingNeed와 EmploymentNeed와 MentalHealthNeed에 제대로 연결되었는지 검증해줘.

## 13. 권장 소스 그룹
- 보건복지부/고용노동부 청년정책 자료
- 지자체 청년센터 사업 안내
- 정신건강복지센터 공개자료
- 주거복지 관련 공공안내
- 금융·채무상담 공공기관 안내

## 14. 개인정보·민감정보 제외 원칙
실제 이름, 주소, 연락처, 주민등록번호, 채무식별정보, 의료식별정보, 내부 사례기록을 포함하지 않는다.

## 15. 향후 확장 후보
- 고립은둔 단계별 개입 경로 세분화
- 청년 금융취약성 지표 및 부채회복 성과지표 확장
- 지역별 청년지원 접근성 비교모델 추가
