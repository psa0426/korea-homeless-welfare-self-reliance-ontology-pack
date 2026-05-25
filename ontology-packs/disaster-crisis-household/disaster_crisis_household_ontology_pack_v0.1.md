# 재난·위기가구·긴급지원 대상자 온톨로지 팩 v0.1

## 0. 팩 메타
- pack_title: 재난·위기가구·긴급지원 대상자 온톨로지 팩 v0.1
- english_title: Disaster, Crisis Household, and Emergency Support Ontology Pack
- category: document_upload
- visibility: private
- intended_use: OpenCrab, GraphRAG, 위기가구 발굴, 긴급지원 의사결정, 재난복지 사례관리
- pii_policy: 실제 가구/개인 식별정보 금지

## 1. 목적과 범위
재난피해, 화재·수해·폭염·한파 취약가구, 갑작스러운 실직·질병·사망·가구해체, 긴급생계·긴급의료·긴급주거, 위기가구 발굴, 복지사각지대 대응 체계를 구조화한다.

## 2. 설계 원칙
1. 위기 징후 탐지와 긴급개입 연결을 중심으로 설계한다.
2. 생계·의료·주거·안전 욕구를 통합적으로 모델링한다.
3. 재난 사건과 비재난 위기 사건을 동일한 케이스 흐름에서 다룬다.
4. 지자체·민간구호·보건·주거기관 연계를 명시한다.
5. 개인정보 없이 구조화 지식 중심으로 작성한다.

## 3. 상위 클래스 체계
### 3.1 Household and Person
- CrisisHousehold
- DisasterVictim
- FireDamageHousehold
- FloodDamageHousehold
- HeatwaveVulnerableHousehold
- ColdWaveVulnerableHousehold
- SuddenUnemploymentHousehold
- SevereIllnessHousehold
- BereavedHousehold
- HouseholdBreakdown

### 3.2 Need and Risk
- EmergencyNeed
- EmergencyLivelihoodNeed
- EmergencyMedicalNeed
- EmergencyHousingNeed
- FoodNeed
- SafetyNeed
- RiskFactor
- ProtectiveFactor
- CrisisRisk
- ServiceGapRisk

### 3.3 Case Management
- EmergencyWelfareCase
- CrisisScreening
- EmergencyAssessment
- EligibilityAssessment
- EmergencySupportPlan
- ServicePlan
- Referral
- Monitoring
- FollowUp

### 3.4 Service and Organization
- EmergencyWelfareSupport
- EmergencyLivelihoodSupport
- EmergencyMedicalSupport
- EmergencyHousingSupport
- DisasterReliefService
- LocalGovernment
- CommunityServiceCenter
- DisasterReliefOrganization
- PublicHealthCenter
- HousingSupportOrganization

### 3.5 Legal and Outcome
- EmergencyWelfareSupportAct
- LegalFramework
- Outcome
- StabilizationOutcome
- SafetyOutcome
- RecoveryOutcome

## 4. 핵심 엔티티
CrisisHousehold, DisasterVictim, FireDamageHousehold, FloodDamageHousehold, HeatwaveVulnerableHousehold, ColdWaveVulnerableHousehold, SuddenUnemploymentHousehold, SevereIllnessHousehold, BereavedHousehold, HouseholdBreakdown, EmergencyNeed, EmergencyLivelihoodNeed, EmergencyMedicalNeed, EmergencyHousingNeed, FoodNeed, SafetyNeed, RiskFactor, ProtectiveFactor, EmergencyWelfareCase, CrisisScreening, EmergencyAssessment, EligibilityAssessment, EmergencySupportPlan, ServicePlan, Referral, Monitoring, FollowUp, EmergencyWelfareSupport, LocalGovernment, CommunityServiceCenter, DisasterReliefOrganization, PublicHealthCenter, HousingSupportOrganization, Outcome

## 5. 핵심 관계
- CrisisHousehold --hasNeed--> EmergencyNeed
- CrisisHousehold --hasNeed--> EmergencyLivelihoodNeed
- CrisisHousehold --hasNeed--> EmergencyMedicalNeed
- CrisisHousehold --hasNeed--> EmergencyHousingNeed
- DisasterVictim --affectedBy--> DisasterEvent
- CrisisHousehold --subjectOf--> EmergencyWelfareCase

- EmergencyWelfareCase --hasCrisisScreening--> CrisisScreening
- EmergencyWelfareCase --hasEmergencyAssessment--> EmergencyAssessment
- EmergencyWelfareCase --hasEligibilityAssessment--> EligibilityAssessment
- EmergencyWelfareCase --hasEmergencySupportPlan--> EmergencySupportPlan
- EmergencyWelfareCase --hasServicePlan--> ServicePlan
- EmergencyWelfareCase --hasReferral--> Referral
- EmergencyWelfareCase --monitoredBy--> Monitoring
- EmergencyWelfareCase --followedBy--> FollowUp

- EmergencySupportPlan --targets--> EmergencyLivelihoodNeed
- EmergencySupportPlan --targets--> EmergencyMedicalNeed
- EmergencySupportPlan --targets--> EmergencyHousingNeed
- ServicePlan --mitigates--> CrisisRisk

- Referral --connectsTo--> LocalGovernment
- Referral --connectsTo--> CommunityServiceCenter
- Referral --connectsTo--> DisasterReliefOrganization
- Referral --connectsTo--> PublicHealthCenter
- Referral --connectsTo--> HousingSupportOrganization

- EmergencyWelfareSupport --mitigates--> CrisisRisk
- Intervention --produces--> StabilizationOutcome

## 6. 시드 트리플
1. CrisisHousehold --hasNeed--> EmergencyNeed
2. CrisisHousehold --hasNeed--> EmergencyLivelihoodNeed
3. CrisisHousehold --hasNeed--> EmergencyMedicalNeed
4. CrisisHousehold --hasNeed--> EmergencyHousingNeed
5. DisasterVictim --affectedBy--> DisasterEvent
6. FireDamageHousehold --subclassOf--> CrisisHousehold
7. FloodDamageHousehold --subclassOf--> CrisisHousehold
8. HeatwaveVulnerableHousehold --subclassOf--> CrisisHousehold
9. ColdWaveVulnerableHousehold --subclassOf--> CrisisHousehold
10. SuddenUnemploymentHousehold --subclassOf--> CrisisHousehold
11. SevereIllnessHousehold --subclassOf--> CrisisHousehold
12. BereavedHousehold --subclassOf--> CrisisHousehold
13. HouseholdBreakdown --subclassOf--> CrisisHousehold
14. EmergencyWelfareCase --hasCrisisScreening--> CrisisScreening
15. EmergencyWelfareCase --hasEmergencyAssessment--> EmergencyAssessment
16. EmergencyWelfareCase --hasEligibilityAssessment--> EligibilityAssessment
17. EmergencyWelfareCase --hasEmergencySupportPlan--> EmergencySupportPlan
18. EmergencySupportPlan --targets--> EmergencyLivelihoodNeed
19. EmergencySupportPlan --targets--> EmergencyMedicalNeed
20. EmergencySupportPlan --targets--> EmergencyHousingNeed
21. Referral --connectsTo--> LocalGovernment
22. Referral --connectsTo--> CommunityServiceCenter
23. Referral --connectsTo--> DisasterReliefOrganization
24. Referral --connectsTo--> PublicHealthCenter
25. Referral --connectsTo--> HousingSupportOrganization
26. EmergencyWelfareSupport --mitigates--> CrisisRisk
27. Monitoring --tracks--> StabilizationOutcome
28. Monitoring --tracks--> SafetyOutcome
29. FollowUp --supports--> RecoveryOutcome
30. Intervention --produces--> StabilizationOutcome

## 7. 사례관리 또는 서비스 흐름
CrisisDetection -> CrisisScreening -> EmergencyAssessment -> EligibilityAssessment -> EmergencySupportPlan -> ServicePlan -> Referral -> Monitoring -> FollowUp

## 8. 위험요인 분류
- DisasterExposureRisk
- HousingLossRisk
- FoodInsecurityRisk
- MedicalAccessRisk
- IncomeShockRisk
- FamilyBreakdownRisk
- ServiceGapRisk
- SecondaryTraumaRisk

## 9. 보호요인 분류
- RapidScreeningAccess
- EmergencyBenefitAccess
- CommunityReliefNetwork
- PublicHealthLinkage
- TemporaryHousingAccess
- CaseMonitoringContinuity
- LocalGovernmentCoordination
- FamilySupportReconnection

## 10. 추론 규칙
1. EmergencyLivelihoodNeed가 있으면 EmergencyLivelihoodSupport 우선 연계를 제안한다.
2. EmergencyMedicalNeed가 있으면 PublicHealthCenter 또는 의료기관 연계를 우선 제안한다.
3. EmergencyHousingNeed가 있으면 HousingSupportOrganization 연계를 우선 제안한다.
4. DisasterEvent 노출이 확인되면 DisasterReliefOrganization 연계를 강화한다.
5. CrisisRisk가 높으면 Monitoring 주기를 단축하고 FollowUp을 필수화한다.

## 11. 검증 규칙
1. 모든 EmergencyWelfareCase는 CrisisScreening을 포함해야 한다.
2. EmergencyWelfareCase는 EmergencyAssessment를 포함해야 한다.
3. EmergencySupportPlan은 최소 1개 EmergencyNeed를 targets 해야 한다.
4. ServicePlan은 최소 1개 RiskFactor를 mitigates 해야 한다.
5. Referral은 최소 1개 Organization과 연결되어야 한다.
6. Monitoring이 있으면 최소 1개 Outcome 추적 링크가 있어야 한다.
7. 개인 식별정보를 포함하지 않는다.

## 12. 질의 템플릿
- 재난·위기가구·긴급지원 대상자 온톨로지 팩의 핵심 엔티티와 관계를 요약해줘.
- 화재피해 가구에서 긴급주거와 긴급생계와 긴급의료는 어떻게 연결되는가?
- 갑작스러운 실직과 질병으로 위기가구가 된 사례에서 필요한 지원은 무엇인가?
- 위기가구 발굴 이후 초기선별과 긴급사정과 지원계획은 어떻게 연결되는가?
- EmergencySupportPlan이 EmergencyNeed와 CrisisRisk에 제대로 연결되었는지 검증해줘.

## 13. 권장 소스 그룹
- 보건복지부 긴급복지 관련 공개자료
- 행정안전부 재난대응 공개자료
- 지자체 위기가구 발굴·지원 지침
- 공공보건 및 주거지원 공개자료
- 국가법령정보센터 긴급복지 관련 법령

## 14. 개인정보·민감정보 제외 원칙
실제 이름, 주소, 연락처, 가구 식별번호, 재난피해 개인기록, 의료식별정보, 내부 사례기록을 포함하지 않는다.

## 15. 향후 확장 후보
- 재난유형별 대응 경로 세분화
- 긴급지원 종료 후 재위기 예측 규칙
- 민관협력 네트워크 성과지표 확장
