# 보훈·국가유공자 복지 온톨로지 팩 v0.1

## 0. 팩 메타
- pack_title: 보훈·국가유공자 복지 온톨로지 팩 v0.1
- english_title: Veterans and National Merit Welfare Ontology Pack
- category: document_upload
- visibility: private
- intended_use: OpenCrab, GraphRAG, 보훈대상자 복지서비스 질의응답, 급여·의료·요양 연계 검증
- pii_policy: 실제 보훈대상자/가구 식별정보 금지

## 1. 목적과 범위
국가유공자, 보훈대상자, 참전유공자, 상이군경, 유족지원, 보훈급여, 의료지원, 요양지원, 재가복지, 보훈병원, 보훈복지시설 체계를 구조화한다.

## 2. 설계 원칙
1. 예우와 생활안정을 함께 고려한다.
2. 급여·의료·요양·주거·심리정서·이동지원 욕구를 통합 모델링한다.
3. 자격사정과 서비스계획의 연결을 명시한다.
4. 보훈병원·보훈복지시설·지방보훈관서 협력 흐름을 반영한다.
5. 개인정보 없이 구조화 지식 중심으로 설계한다.

## 3. 상위 클래스 체계
### 3.1 Person and Household
- Veteran
- PersonOfNationalMerit
- WarVeteran
- DisabledVeteran
- BereavedFamily
- VeteransHousehold

### 3.2 Need and Benefit
- HonoraryNeed
- IncomeNeed
- MedicalNeed
- CareNeed
- HousingNeed
- MobilityNeed
- MentalHealthNeed
- LegalNeed
- Benefit
- VeteransBenefit
- BereavedFamilySupport

### 3.3 Case Management
- VeteransWelfareCase
- Intake
- Assessment
- EligibilityAssessment
- ServicePlan
- Referral
- Monitoring
- FollowUp

### 3.4 Service and Organization
- MedicalSupport
- CareSupport
- HomeCareSupport
- FacilityCareSupport
- HousingSupport
- EmploymentSupport
- VeteransHospital
- VeteransWelfareFacility
- LocalVeteransOffice
- MinistryOfPatriotsAndVeteransAffairs

### 3.5 Legal and Outcome
- VeteransSupportAct
- LegalFramework
- Outcome
- WelfareOutcome
- MedicalOutcome
- CareOutcome
- HousingStabilityOutcome

## 4. 핵심 엔티티
Veteran, PersonOfNationalMerit, WarVeteran, DisabledVeteran, BereavedFamily, VeteransHousehold, HonoraryNeed, IncomeNeed, MedicalNeed, CareNeed, HousingNeed, MobilityNeed, MentalHealthNeed, LegalNeed, Benefit, VeteransBenefit, VeteransWelfareCase, Assessment, EligibilityAssessment, ServicePlan, Referral, Monitoring, FollowUp, MedicalSupport, CareSupport, HomeCareSupport, FacilityCareSupport, HousingSupport, EmploymentSupport, VeteransHospital, VeteransWelfareFacility, LocalVeteransOffice, MinistryOfPatriotsAndVeteransAffairs, VeteransSupportAct, Outcome

## 5. 핵심 관계
- Veteran --hasNeed--> HonoraryNeed
- Veteran --hasNeed--> IncomeNeed
- Veteran --hasNeed--> MedicalNeed
- Veteran --hasNeed--> CareNeed
- Veteran --hasNeed--> HousingNeed
- Veteran --hasNeed--> MobilityNeed
- Veteran --hasNeed--> MentalHealthNeed
- Veteran --eligibleFor--> Benefit
- BereavedFamily --eligibleFor--> BereavedFamilySupport
- Veteran --subjectOf--> VeteransWelfareCase

- VeteransWelfareCase --hasAssessment--> Assessment
- VeteransWelfareCase --hasEligibilityAssessment--> EligibilityAssessment
- VeteransWelfareCase --hasServicePlan--> ServicePlan
- VeteransWelfareCase --hasReferral--> Referral
- VeteransWelfareCase --monitoredBy--> Monitoring
- VeteransWelfareCase --followedBy--> FollowUp

- ServicePlan --targets--> MedicalNeed
- ServicePlan --targets--> CareNeed
- ServicePlan --targets--> HousingNeed
- ServicePlan --targets--> MobilityNeed
- ServicePlan --targets--> MentalHealthNeed

- Referral --connectsTo--> VeteransHospital
- Referral --connectsTo--> VeteransWelfareFacility
- Referral --connectsTo--> LocalVeteransOffice

- VeteransHospital --provides--> MedicalSupport
- VeteransWelfareFacility --provides--> CareSupport
- Benefit --governedBy--> LegalFramework
- Intervention --produces--> WelfareOutcome

## 6. 시드 트리플
1. Veteran --hasNeed--> HonoraryNeed
2. Veteran --hasNeed--> IncomeNeed
3. Veteran --hasNeed--> MedicalNeed
4. Veteran --hasNeed--> CareNeed
5. Veteran --hasNeed--> HousingNeed
6. Veteran --hasNeed--> MobilityNeed
7. Veteran --hasNeed--> MentalHealthNeed
8. Veteran --eligibleFor--> VeteransBenefit
9. BereavedFamily --eligibleFor--> BereavedFamilySupport
10. Veteran --subjectOf--> VeteransWelfareCase
11. VeteransWelfareCase --hasAssessment--> Assessment
12. VeteransWelfareCase --hasEligibilityAssessment--> EligibilityAssessment
13. VeteransWelfareCase --hasServicePlan--> ServicePlan
14. ServicePlan --targets--> MedicalNeed
15. ServicePlan --targets--> CareNeed
16. ServicePlan --targets--> HousingNeed
17. ServicePlan --targets--> MobilityNeed
18. ServicePlan --targets--> MentalHealthNeed
19. Referral --connectsTo--> VeteransHospital
20. Referral --connectsTo--> VeteransWelfareFacility
21. Referral --connectsTo--> LocalVeteransOffice
22. VeteransHospital --provides--> MedicalSupport
23. VeteransWelfareFacility --provides--> CareSupport
24. HomeCareSupport --supports--> CareNeed
25. FacilityCareSupport --supports--> CareNeed
26. HousingSupport --targets--> HousingNeed
27. EmploymentSupport --targets--> IncomeNeed
28. Benefit --governedBy--> VeteransSupportAct
29. Monitoring --tracks--> WelfareOutcome
30. Intervention --produces--> HousingStabilityOutcome

## 7. 사례관리 또는 서비스 흐름
Intake -> Assessment -> EligibilityAssessment -> ServicePlan -> Referral -> Monitoring -> FollowUp

## 8. 위험요인 분류
- BenefitExclusionRisk
- MedicalAccessRisk
- CareGapRisk
- HousingInstabilityRisk
- MobilityBarrierRisk
- SocialIsolationRisk
- MentalHealthDeteriorationRisk
- ServiceDisconnectionRisk

## 9. 보호요인 분류
- BenefitEligibilitySupport
- VeteransHospitalAccess
- HomeCareContinuity
- FamilySupportNetwork
- LocalVeteransOfficeLinkage
- MobilityAidAccess
- MentalHealthSupportContinuity
- IntegratedCaseManagement

## 10. 추론 규칙
1. MedicalNeed가 있으면 VeteransHospital 연계를 우선 제안한다.
2. CareNeed가 있으면 HomeCareSupport 또는 FacilityCareSupport를 우선 검토한다.
3. HousingNeed가 있으면 HousingSupport와 LocalVeteransOffice 연계를 제안한다.
4. BereavedFamily가 지원대상일 경우 BereavedFamilySupport 자격사정을 우선 수행한다.
5. EligibilityAssessment가 완료되면 Benefit 및 ServicePlan 연결 여부를 검증한다.

## 11. 검증 규칙
1. 모든 VeteransWelfareCase는 EligibilityAssessment를 포함해야 한다.
2. ServicePlan은 최소 1개 Need를 targets 해야 한다.
3. Referral은 최소 1개 Organization과 연결되어야 한다.
4. Benefit 연결 사례는 LegalFramework 또는 VeteransSupportAct 참조를 가져야 한다.
5. Monitoring이 있으면 최소 1개 Outcome 추적 링크가 있어야 한다.
6. 개인 식별정보를 포함하지 않는다.

## 12. 질의 템플릿
- 보훈·국가유공자 복지 온톨로지 팩의 핵심 엔티티와 관계를 요약해줘.
- 국가유공자의 보훈급여와 의료지원과 요양지원은 어떤 욕구와 연결되는가?
- 보훈병원과 보훈복지시설과 지방보훈관서의 역할 차이를 설명해줘.
- 유족지원과 보훈급여 자격사정은 어떻게 연결되는가?
- ServicePlan이 MedicalNeed와 CareNeed와 Benefit에 제대로 연결되었는지 검증해줘.

## 13. 권장 소스 그룹
- 국가보훈부 공개자료
- 보훈병원/보훈복지시설 안내자료
- 지방보훈관서 서비스 안내
- 국가법령정보센터 보훈 관련 법령
- 공공통계 보훈대상자 지원지표

## 14. 개인정보·민감정보 제외 원칙
실제 이름, 주소, 연락처, 보훈번호, 의료식별정보, 개인 급여내역, 내부 사례기록을 포함하지 않는다.

## 15. 향후 확장 후보
- 보훈급여 세부유형 온톨로지 확장
- 의료·요양 연속돌봄 지표 모델 확장
- 지역별 보훈서비스 접근성 비교 온톨로지
