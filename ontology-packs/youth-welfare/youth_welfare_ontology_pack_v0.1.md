# 청소년복지·학교밖청소년 온톨로지 팩 v0.1

## 0. 팩 메타

- pack_title: 청소년복지·학교밖청소년 온톨로지 팩 v0.1
- english_title: Youth Welfare and Out-of-School Youth Ontology Pack
- category: general
- visibility: private
- intended_use: OpenCrab, GraphRAG, 위기청소년 사례관리, 다기관 연계, 서비스 매칭, 정책 분석
- pii_policy: 실제 청소년/보호자/종사자 식별정보 금지
- update_policy: 법령/지침/사업 변경 시 버전·날짜 기반 갱신

## 1. 목적과 범위

본 팩은 대한민국 청소년복지, 학교밖청소년 지원, 위기청소년 보호, 청소년상담, 청소년쉼터, 청소년안전망, 진로·자립지원 체계를 구조화한다.
핵심 목적은 Youth, OutOfSchoolYouth, RiskFactor, ServicePlan, Referral, Organization, Outcome 간 관계를 일관되게 표현하여 사례 분류, 위험사정, 연계 의사결정, 질의응답 품질을 높이는 것이다.

## 2. 설계 원칙

1. 청소년의 안전·권리·자기결정권을 우선한다.
2. 교육·진로·주거·정서·가족관계를 통합적으로 사정한다.
3. 위험요인과 보호요인을 동시 모델링한다.
4. 단일기관 개입보다 다기관 협력(청소년안전망)을 기본으로 둔다.
5. 개인 식별정보 없이 구조화 지식 중심으로 작성한다.

## 3. 상위 클래스 체계

### 3.1 Person and Group
- Youth
- OutOfSchoolYouth
- CrisisYouth
- RunawayYouth
- AtRiskYouth
- Caregiver
- FamilyMember
- CaseWorker

### 3.2 Need and Risk
- WelfareNeed
- EducationNeed
- CareerNeed
- HousingNeed
- SafetyNeed
- MentalHealthNeed
- FamilyRelationshipNeed
- RiskFactor
- ProtectiveFactor

### 3.3 Case and Process
- YouthWelfareCase
- Intake
- Screening
- RiskAssessment
- SafetyAssessment
- CounselingPlan
- ServicePlan
- Referral
- Monitoring
- FollowUp
- CaseClosure

### 3.4 Service and Organization
- CounselingService
- EducationSupport
- CareerSupport
- EmergencyProtection
- FamilyCounseling
- MentalHealthSupport
- SelfRelianceSupport
- MultiAgencySupport
- YouthSupportOrganization
- YouthCounselingWelfareCenter
- OutOfSchoolYouthSupportCenter
- YouthShelter
- YouthSafetyNet
- YouthCompanionProgram
- School
- PoliceAgency
- MentalHealthWelfareCenter

### 3.5 Policy and Outcome
- LegalFramework
- YouthWelfareSupportAct
- Outcome
- SafetyOutcome
- EducationContinuationOutcome
- SocialParticipationOutcome
- SelfRelianceOutcome

## 4. 핵심 엔티티

- Youth
- OutOfSchoolYouth
- CrisisYouth
- RunawayYouth
- AtRiskYouth
- SchoolDropoutRisk
- FamilyConflict
- PeerConflict
- SchoolViolenceExposure
- MentalHealthConcern
- CareerNeed
- EducationNeed
- HousingNeed
- SafetyNeed
- WelfareNeed
- RiskFactor
- ProtectiveFactor
- YouthWelfareCase
- RiskAssessment
- SafetyAssessment
- CounselingPlan
- ServicePlan
- Referral
- Monitoring
- FollowUp
- YouthCounselingWelfareCenter
- OutOfSchoolYouthSupportCenter
- YouthShelter
- YouthSafetyNet
- YouthCompanionProgram
- School
- PoliceAgency
- MentalHealthWelfareCenter
- YouthWelfareSupportAct
- Outcome

## 5. 핵심 관계

- Youth --hasNeed--> WelfareNeed
- Youth --hasNeed--> EducationNeed
- Youth --hasNeed--> CareerNeed
- Youth --hasNeed--> SafetyNeed
- Youth --exposedTo--> RiskFactor
- Youth --protectedBy--> ProtectiveFactor
- Youth --subjectOf--> YouthWelfareCase

- OutOfSchoolYouth --hasNeed--> EducationNeed
- OutOfSchoolYouth --hasNeed--> CareerNeed
- CrisisYouth --exposedTo--> SchoolDropoutRisk
- RunawayYouth --exposedTo--> HousingNeed
- AtRiskYouth --exposedTo--> MentalHealthConcern

- YouthWelfareCase --hasRiskAssessment--> RiskAssessment
- YouthWelfareCase --hasSafetyAssessment--> SafetyAssessment
- YouthWelfareCase --hasCounselingPlan--> CounselingPlan
- YouthWelfareCase --hasServicePlan--> ServicePlan
- YouthWelfareCase --hasReferral--> Referral
- YouthWelfareCase --monitoredBy--> Monitoring
- YouthWelfareCase --followedBy--> FollowUp

- ServicePlan --targets--> WelfareNeed
- ServicePlan --targets--> EducationNeed
- ServicePlan --targets--> CareerNeed
- ServicePlan --mitigates--> RiskFactor

- Referral --connectsTo--> YouthSupportOrganization
- Referral --connectsTo--> YouthCounselingWelfareCenter
- Referral --connectsTo--> OutOfSchoolYouthSupportCenter
- Referral --connectsTo--> YouthShelter
- Referral --connectsTo--> MentalHealthWelfareCenter
- Referral --connectsTo--> PoliceAgency

- YouthCounselingWelfareCenter --provides--> CounselingService
- OutOfSchoolYouthSupportCenter --provides--> EducationSupport
- YouthShelter --provides--> EmergencyProtection
- YouthSafetyNet --coordinates--> MultiAgencySupport
- YouthCompanionProgram --provides--> CounselingService
- School --coordinatesWith--> YouthSafetyNet

- Intervention --produces--> Outcome
- CounselingService --produces--> SafetyOutcome
- EducationSupport --produces--> EducationContinuationOutcome
- CareerSupport --produces--> SelfRelianceOutcome

## 6. 시드 트리플

1. Youth --hasNeed--> WelfareNeed
2. Youth --hasNeed--> EducationNeed
3. Youth --hasNeed--> CareerNeed
4. Youth --exposedTo--> SchoolDropoutRisk
5. Youth --exposedTo--> FamilyConflict
6. Youth --exposedTo--> PeerConflict
7. Youth --exposedTo--> SchoolViolenceExposure
8. Youth --exposedTo--> MentalHealthConcern
9. Youth --subjectOf--> YouthWelfareCase
10. OutOfSchoolYouth --hasNeed--> EducationNeed
11. OutOfSchoolYouth --hasNeed--> CareerNeed
12. RunawayYouth --hasNeed--> HousingNeed
13. CrisisYouth --hasNeed--> SafetyNeed
14. YouthWelfareCase --hasRiskAssessment--> RiskAssessment
15. YouthWelfareCase --hasSafetyAssessment--> SafetyAssessment
16. YouthWelfareCase --hasServicePlan--> ServicePlan
17. ServicePlan --targets--> WelfareNeed
18. ServicePlan --targets--> EducationNeed
19. ServicePlan --targets--> CareerNeed
20. ServicePlan --mitigates--> RiskFactor
21. Referral --connectsTo--> YouthCounselingWelfareCenter
22. Referral --connectsTo--> OutOfSchoolYouthSupportCenter
23. Referral --connectsTo--> YouthShelter
24. Referral --connectsTo--> MentalHealthWelfareCenter
25. YouthCounselingWelfareCenter --provides--> CounselingService
26. OutOfSchoolYouthSupportCenter --provides--> EducationSupport
27. YouthShelter --provides--> EmergencyProtection
28. YouthSafetyNet --coordinates--> MultiAgencySupport
29. CounselingService --produces--> SafetyOutcome
30. EducationSupport --produces--> EducationContinuationOutcome
31. CareerSupport --produces--> SelfRelianceOutcome
32. Monitoring --tracks--> Outcome

## 7. 사례관리 또는 서비스 흐름

Intake -> Screening -> RiskAssessment -> SafetyAssessment -> CounselingPlan -> ServicePlan -> Referral -> Monitoring -> FollowUp -> CaseClosure

## 8. 위험요인 분류

- EducationRisk: SchoolDropoutRisk, LearningDisconnection
- FamilyRisk: FamilyConflict, CareGap, FamilyViolenceExposure
- PeerRisk: PeerConflict, BullyingExposure, DelinquentPeerInfluence
- SafetyRisk: RunawayRisk, ExploitationRisk, ViolenceExposure
- MentalHealthRisk: DepressionConcern, AnxietyConcern, SelfHarmRisk
- HousingRisk: UnstableHousing, EmergencyShelterNeed
- EconomicRisk: PovertyRisk, ResourceAccessGap
- ServiceRisk: ServiceDisconnectionRisk, ReferralDelayRisk

## 9. 보호요인 분류

- StableCaregiverSupport
- SchoolAttachment
- PositivePeerNetwork
- TrustedAdultMentor
- CounselingEngagement
- MultiAgencyCoordination
- SafeHousingAccess
- CareerTrainingParticipation
- CommunityParticipation
- CrisisHotlineAccess

## 10. 추론 규칙

1. SchoolDropoutRisk와 EducationNeed가 함께 있으면 EducationSupport와 SchoolReturnPlan을 우선 제안한다.
2. RunawayRisk 또는 HousingNeed가 있으면 EmergencyProtection과 YouthShelter 연계를 우선 제안한다.
3. MentalHealthConcern이 있으면 RiskAssessment 이후 MentalHealthWelfareCenter 연계를 검토한다.
4. FamilyConflict가 높으면 FamilyCounseling과 CaregiverSupport를 동시 제안한다.
5. ServiceDisconnectionRisk가 있으면 YouthSafetyNet 기반 CaseConference를 활성화한다.
6. CrisisYouth 사례는 SafetyAssessment가 없으면 계획 수립 전 보완 경고를 생성한다.
7. OutOfSchoolYouth 사례는 CareerNeed와 EducationNeed 중 최소 하나를 계획에 포함해야 한다.
8. Referral이 2개 이상 기관으로 연결되면 Monitoring 주기를 단축한다.

## 11. 검증 규칙

1. 모든 YouthWelfareCase는 최소 1개의 RiskAssessment를 가져야 한다.
2. CrisisYouth 사례는 SafetyAssessment를 반드시 포함해야 한다.
3. ServicePlan은 최소 1개의 WelfareNeed 또는 RiskFactor를 대상으로 해야 한다.
4. OutOfSchoolYouth 사례는 EducationSupport 또는 CareerSupport 연결이 있어야 한다.
5. Referral은 최소 1개의 YouthSupportOrganization과 연결되어야 한다.
6. Monitoring이 있는 사례는 최소 1개의 Outcome 추적 링크를 가져야 한다.
7. EmergencyProtection이 있으면 YouthShelter 또는 PoliceAgency 연계 중 하나 이상이 필요하다.
8. FollowUp이 있는 사례는 선행 ServicePlan이 존재해야 한다.
9. 개인 식별정보는 노드/속성값에 포함하지 않는다.
10. 실제 사례 원문/내부기록/민감정보를 포함하지 않는다.

## 12. 질의 템플릿

- 청소년복지·학교밖청소년 온톨로지 팩의 핵심 엔티티와 관계를 요약해줘.
- 학교밖청소년에게 필요한 교육지원과 진로지원과 자립지원은 어떻게 연결되는가?
- 위기청소년 사례에서 위험사정과 안전사정과 서비스계획은 어떻게 연결되는가?
- 청소년쉼터와 청소년상담복지센터와 학교밖청소년지원센터의 역할 차이를 설명해줘.
- 가출청소년 사례에서 긴급보호와 상담과 가족관계 회복 지원은 어떻게 연결되는가?
- 청소년안전망에서 공공기관과 학교와 상담기관은 어떤 관계로 협력하는가?
- ServicePlan이 WelfareNeed와 RiskFactor에 제대로 연결되었는지 검증해줘.
- RiskAssessment가 누락된 사례를 탐지하는 기준을 알려줘.

## 13. 권장 소스 그룹

- 국가법령정보센터: 청소년복지지원법 등 관련 법령
- 여성가족부: 청소년정책·학교밖청소년 지원사업 지침
- 지방자치단체: 청소년상담복지센터/쉼터 운영 지침
- 공공데이터포털·KOSIS: 청소년 관련 통계
- 청소년안전망/1388 관련 공개 안내자료
- 교육부·교육청: 학업중단 예방/복귀 지원 자료

## 14. 개인정보·민감정보 제외 원칙

본 팩은 공개 가능한 구조화 지식과 개념 관계만 포함한다.
다음은 포함하지 않는다: 실제 이름, 주민등록번호, 주소, 연락처, 학교·시설의 개인식별 가능한 사례기록, 수사·의료 민감정보, 내부 업무문서 원문.

## 15. 향후 확장 후보

- 청소년 디지털 위험(온라인 그루밍/사이버폭력) 세부 온톨로지 확장
- 학교-복지-사법 연계의 사건 타임라인 모델 확장
- 지역별 서비스 접근성 지표와 대기기간 지표 통합
- 성과평가(재학복귀율, 상담지속률, 안전회복지표) 세분화
