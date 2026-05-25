# 노인복지·돌봄 온톨로지 팩 v0.1

## 0. 팩 메타

- pack_title: 노인복지·돌봄 온톨로지 팩 v0.1
- english_title: Korea Elderly Welfare and Care Ontology Pack
- category: general
- visibility: private
- intended_use: OpenCrab, GraphRAG, 노인복지 질의응답, 사례관리 구조화, 서비스 매칭, 정책·지침 분석
- pii_policy: 실제 노인, 보호자, 종사자, 시설 이용자, 가구의 식별정보 금지
- update_policy: 법령, 지침, 사업, 시설 유형, 장기요양 기준 변경 시 날짜가 포함된 업데이트로 관리

## 1. 목적과 범위

이 팩은 대한민국 노인복지, 장기요양, 지역사회 돌봄, 치매지원, 노인학대 대응, 노인복지시설, 재가서비스, 사례관리 체계를 구조화하기 위한 실무형 온톨로지 팩이다.

핵심 목적은 OlderPerson, Caregiver, Household, WelfareNeed, CareNeed, RiskFactor, ProtectiveFactor, ElderlyWelfareFacility, LongTermCareInstitution, DementiaSupportService, ElderAbuse, CaseManagement, ServicePlan, Organization, LegalFramework, Outcome 간의 관계를 일관되게 표현하여 검색, 질의응답, 사례 분류, 서비스 매칭, 정책 분석에 활용하는 것이다.

## 2. 설계 원칙

1. 노인의 존엄성과 자기결정권을 중심에 둔다.
2. 신체, 인지, 정신건강, 사회관계, 경제, 주거, 돌봄 환경을 통합적으로 본다.
3. 위험요인과 보호요인을 함께 모델링한다.
4. 가족돌봄, 공적돌봄, 지역사회 자원을 함께 연결한다.
5. 장기요양, 노인복지, 치매지원, 학대대응, 사례관리를 분리하되 연결 가능한 체계로 둔다.
6. 실제 사례 식별정보는 포함하지 않는다.

## 3. 상위 클래스 체계

### 3.1 Person

- OlderPerson: 노인 또는 노년기 대상자
- Caregiver: 가족돌봄자, 보호자, 주돌봄자
- FamilyMember: 가족 구성원
- CaseWorker: 사례관리자
- CareWorker: 요양보호사, 생활지원사 등 돌봄 인력
- HealthcareProfessional: 의사, 간호사, 물리치료사, 작업치료사 등 보건의료 인력
- SocialWorker: 사회복지사
- Guardian: 후견인 또는 법정대리인

### 3.2 Household and Living Environment

- Household: 가구
- LivingArrangement: 독거, 부부가구, 자녀동거, 시설거주 등 생활형태
- HousingEnvironment: 주거환경
- CommunityEnvironment: 지역사회 환경
- SocialNetwork: 가족, 이웃, 친구, 종교·지역 모임 등 사회적 관계망

### 3.3 Need and Risk

- WelfareNeed: 복지욕구
- CareNeed: 돌봄욕구
- HealthNeed: 건강욕구
- MentalHealthNeed: 정신건강욕구
- DementiaCareNeed: 치매 관련 욕구
- NutritionNeed: 영양 욕구
- HousingNeed: 주거 욕구
- EconomicNeed: 경제 욕구
- SafetyNeed: 안전 욕구
- MobilityNeed: 이동 욕구
- SocialParticipationNeed: 사회참여 욕구
- LegalNeed: 법률·후견 욕구

- RiskFactor: 위험요인
- ProtectiveFactor: 보호요인
- Frailty: 허약
- FallRisk: 낙상위험
- CognitiveDecline: 인지저하
- DepressionRisk: 우울위험
- SuicideRisk: 자살위험
- SocialIsolation: 사회적 고립
- SelfNeglect: 자기방임
- CaregiverBurden: 돌봄자 부담
- HousingInstability: 주거불안
- PovertyRisk: 경제취약
- MedicationRisk: 약물관리 위험

### 3.4 Elder Abuse and Protection

- ElderAbuse: 노인학대
- PhysicalAbuse: 신체적 학대
- EmotionalAbuse: 정서적 학대
- SexualAbuse: 성적 학대
- FinancialExploitation: 경제적 착취
- Neglect: 방임
- SelfNeglect: 자기방임
- Abandonment: 유기
- ElderProtectionIntervention: 노인보호 개입
- EmergencyProtection: 긴급보호
- SafetyPlanning: 안전계획

### 3.5 Facility and Service

- ElderlyWelfareFacility: 노인복지시설
- SeniorWelfareCenter: 노인복지관
- SeniorCommunityCenter: 경로당 또는 노인여가복지시설
- LongTermCareInstitution: 장기요양기관
- ResidentialCareFacility: 노인의료복지시설 또는 생활시설
- NursingHome: 노인요양시설
- GroupHomeForOlderPersons: 노인요양공동생활가정
- HomeCareServiceProvider: 재가서비스 제공기관
- DayNightCareCenter: 주야간보호기관
- ShortTermCareFacility: 단기보호기관
- DementiaCareCenter: 치매안심센터 또는 치매지원기관
- ElderProtectionAgency: 노인보호전문기관
- PublicHealthCenter: 보건소
- CommunityResource: 지역사회 자원

### 3.6 Service Domains

- LongTermCareService: 장기요양서비스
- HomeVisitCare: 방문요양
- HomeVisitBathing: 방문목욕
- HomeVisitNursing: 방문간호
- DayNightCare: 주야간보호
- ShortTermCare: 단기보호
- FacilityCare: 시설급여 또는 시설돌봄
- AssistiveDeviceSupport: 복지용구 또는 보조기기 지원
- MealSupport: 식사·영양지원
- TransportationSupport: 이동지원
- HealthManagementService: 건강관리
- DementiaScreening: 치매선별검사
- DementiaCaseManagement: 치매사례관리
- MentalHealthService: 정신건강지원
- SocialParticipationProgram: 사회참여 프로그램
- EmploymentSupport: 노인일자리 또는 사회활동 지원
- HousingSupport: 주거지원
- EconomicSupport: 경제지원
- LegalSupport: 법률·후견지원
- FamilyCaregiverSupport: 가족돌봄자 지원
- AftercareService: 사후관리

### 3.7 Case Management

- ElderlyWelfareCase: 노인복지 사례
- Intake: 접수
- Screening: 초기 선별
- Assessment: 사정
- NeedsAssessment: 욕구사정
- CareNeedsAssessment: 돌봄필요도 사정
- SafetyAssessment: 안전사정
- RiskAssessment: 위험사정
- CognitiveAssessment: 인지기능 사정
- ADLAssessment: 일상생활수행능력 사정
- IADLAssessment: 도구적 일상생활수행능력 사정
- CarePlan: 돌봄계획
- ServicePlan: 서비스계획
- Referral: 의뢰·연계
- CaseConference: 통합사례회의
- Monitoring: 점검
- CaseClosure: 사례종결
- FollowUp: 사후관리

### 3.8 Organization and Governance

- PublicAgency: 지자체 및 공공기관
- Ministry: 중앙부처
- NationalHealthInsuranceService: 국민건강보험공단
- LocalGovernment: 지방자치단체
- PublicHealthCenter: 보건소
- SeniorWelfareOrganization: 노인복지기관
- LongTermCareProvider: 장기요양기관
- DementiaSupportOrganization: 치매지원기관
- ElderProtectionAgency: 노인보호전문기관
- HealthcareProvider: 의료기관
- MentalHealthWelfareCenter: 정신건강복지센터
- CommunityCareNetwork: 지역사회 돌봄 네트워크
- NGO: 민간기관

### 3.9 Legal and Policy Framework

- LegalFramework: 법·제도
- ElderlyWelfareAct: 노인복지법
- LongTermCareInsuranceAct: 노인장기요양보험법
- DementiaManagementAct: 치매관리법
- BasicLivelihoodSecurityAct: 국민기초생활 보장 관련 법제
- AdultGuardianshipFramework: 성년후견 관련 제도
- PolicyProgram: 정책사업
- LongTermCareInsuranceSystem: 노인장기요양보험 제도
- DementiaNationalResponsibilityPolicy: 치매 국가책임제 또는 치매정책
- CommunityIntegratedCare: 지역사회 통합돌봄 또는 재가·지역 기반 돌봄 정책

### 3.10 Outcome and Indicator

- Outcome: 결과
- SafetyOutcome: 안전성과
- CareContinuityOutcome: 돌봄연속성 성과
- HealthOutcome: 건강성과
- FunctionalOutcome: 기능상태 성과
- CognitiveOutcome: 인지기능 성과
- SocialParticipationOutcome: 사회참여 성과
- QualityOfLifeOutcome: 삶의 질 성과
- CaregiverBurdenOutcome: 돌봄자 부담 완화 성과
- ServiceUtilizationIndicator: 서비스 이용 지표
- RiskReductionIndicator: 위험 감소 지표
- CaseProgressIndicator: 사례 진행 지표

## 4. 핵심 관계

- OlderPerson --livesIn--> Household
- OlderPerson --hasLivingArrangement--> LivingArrangement
- OlderPerson --hasNeed--> WelfareNeed
- OlderPerson --hasCareNeed--> CareNeed
- OlderPerson --exposedTo--> RiskFactor
- OlderPerson --protectedBy--> ProtectiveFactor
- OlderPerson --subjectOf--> ElderlyWelfareCase
- OlderPerson --receives--> Service
- OlderPerson --assessedBy--> Assessment
- OlderPerson --hasOutcome--> Outcome

- Caregiver --caresFor--> OlderPerson
- Caregiver --hasBurden--> CaregiverBurden
- Caregiver --participatesIn--> FamilyCaregiverSupport
- Household --hasRiskFactor--> RiskFactor
- Household --hasProtectiveFactor--> ProtectiveFactor

- ElderlyWelfareCase --hasIntake--> Intake
- ElderlyWelfareCase --includesAssessment--> Assessment
- ElderlyWelfareCase --hasNeedsAssessment--> NeedsAssessment
- ElderlyWelfareCase --hasSafetyAssessment--> SafetyAssessment
- ElderlyWelfareCase --hasRiskAssessment--> RiskAssessment
- ElderlyWelfareCase --hasCarePlan--> CarePlan
- ElderlyWelfareCase --hasServicePlan--> ServicePlan
- ElderlyWelfareCase --hasReferral--> Referral
- ElderlyWelfareCase --discussedIn--> CaseConference
- ElderlyWelfareCase --monitoredBy--> Monitoring
- ElderlyWelfareCase --closedBy--> CaseClosure
- ElderlyWelfareCase --followedBy--> FollowUp

- Assessment --identifies--> WelfareNeed
- RiskAssessment --identifies--> RiskFactor
- SafetyAssessment --identifies--> SafetyNeed
- CognitiveAssessment --identifies--> CognitiveDecline
- ADLAssessment --identifies--> CareNeed
- ServicePlan --targets--> WelfareNeed
- ServicePlan --mitigates--> RiskFactor
- CarePlan --coordinates--> Service
- Referral --connectsTo--> Organization
- Organization --provides--> Service
- Organization --governedBy--> LegalFramework
- Service --produces--> Outcome
- Intervention --produces--> Outcome

- ElderAbuse --includes--> PhysicalAbuse
- ElderAbuse --includes--> EmotionalAbuse
- ElderAbuse --includes--> SexualAbuse
- ElderAbuse --includes--> FinancialExploitation
- ElderAbuse --includes--> Neglect
- ElderAbuse --requires--> SafetyAssessment
- ElderAbuse --requires--> ElderProtectionIntervention

- LongTermCareService --providedBy--> LongTermCareInstitution
- LongTermCareService --targets--> CareNeed
- DementiaSupportService --targets--> DementiaCareNeed
- MealSupport --targets--> NutritionNeed
- TransportationSupport --targets--> MobilityNeed
- SocialParticipationProgram --targets--> SocialParticipationNeed

## 5. 시드 트리플

1. OlderPerson --hasNeed--> WelfareNeed
2. OlderPerson --hasCareNeed--> CareNeed
3. OlderPerson --exposedTo--> RiskFactor
4. OlderPerson --protectedBy--> ProtectiveFactor
5. OlderPerson --subjectOf--> ElderlyWelfareCase
6. OlderPerson --receives--> LongTermCareService
7. OlderPerson --receives--> MealSupport
8. OlderPerson --receives--> DementiaSupportService
9. Caregiver --caresFor--> OlderPerson
10. Caregiver --hasBurden--> CaregiverBurden
11. Household --hasRiskFactor--> SocialIsolation
12. Household --hasRiskFactor--> PovertyRisk
13. Frailty --increasesRiskOf--> FallRisk
14. CognitiveDecline --relatedTo--> DementiaCareNeed
15. ElderAbuse --includes--> PhysicalAbuse
16. ElderAbuse --includes--> EmotionalAbuse
17. ElderAbuse --includes--> FinancialExploitation
18. ElderAbuse --includes--> Neglect
19. ElderAbuse --requires--> SafetyAssessment
20. ElderlyWelfareCase --hasNeedsAssessment--> NeedsAssessment
21. ElderlyWelfareCase --hasSafetyAssessment--> SafetyAssessment
22. ElderlyWelfareCase --hasRiskAssessment--> RiskAssessment
23. ElderlyWelfareCase --hasCarePlan--> CarePlan
24. ElderlyWelfareCase --hasServicePlan--> ServicePlan
25. ServicePlan --targets--> WelfareNeed
26. ServicePlan --mitigates--> RiskFactor
27. CarePlan --coordinates--> LongTermCareService
28. Referral --connectsTo--> ElderProtectionAgency
29. Referral --connectsTo--> DementiaCareCenter
30. Referral --connectsTo--> PublicHealthCenter
31. SeniorWelfareCenter --provides--> SocialParticipationProgram
32. LongTermCareInstitution --provides--> LongTermCareService
33. HomeCareServiceProvider --provides--> HomeVisitCare
34. DayNightCareCenter --provides--> DayNightCare
35. NursingHome --provides--> FacilityCare
36. DementiaCareCenter --provides--> DementiaScreening
37. DementiaCareCenter --provides--> DementiaCaseManagement
38. ElderProtectionAgency --provides--> ElderProtectionIntervention
39. LegalFramework --governs--> Organization
40. ElderlyWelfareAct --governs--> ElderlyWelfareFacility
41. LongTermCareInsuranceAct --governs--> LongTermCareInsuranceSystem
42. DementiaManagementAct --governs--> DementiaSupportService
43. Service --produces--> Outcome
44. Monitoring --tracks--> Outcome
45. FollowUp --supports--> CareContinuityOutcome

## 6. 사례관리 흐름

Intake -> Screening -> NeedsAssessment -> RiskAssessment -> SafetyAssessment -> CareNeedsAssessment -> ServicePlan -> CarePlan -> Referral -> CaseConference -> Monitoring -> CaseClosure -> FollowUp

## 7. 위험요인 분류

- HealthRisk: 만성질환, 복합질환, 약물관리 위험, 영양위험
- FunctionalRisk: ADL 저하, IADL 저하, 이동제한, 낙상위험
- CognitiveRisk: 인지저하, 치매의심, 의사결정 어려움
- MentalHealthRisk: 우울, 불안, 자살위험
- SocialRisk: 독거, 사회적 고립, 관계 단절
- EconomicRisk: 빈곤, 의료비 부담, 생계불안
- HousingRisk: 주거불안, 주거환경 위험, 화재·낙상 위험
- AbuseRisk: 학대, 착취, 방임, 자기방임
- CaregiverRisk: 돌봄자 부담, 돌봄자 부재, 가족갈등
- SystemRisk: 서비스 단절, 기관 간 연계 부족, 사후관리 미흡

## 8. 보호요인 분류

- StableCaregiver: 안정적 돌봄자
- FamilySupport: 가족 지지
- CommunitySupport: 지역사회 지지
- ServiceEngagement: 서비스 참여
- MedicalContinuity: 의료 연속성
- SafeHousing: 안전한 주거
- EconomicStability: 경제 안정
- SocialParticipation: 사회참여
- CognitiveSupport: 인지지원
- AssistiveTechnology: 보조기기·복지용구
- AdvanceCarePlanning: 사전돌봄계획 또는 의사결정 지원

## 9. 추론 규칙

1. OlderPerson exposedTo FallRisk이고 MobilityNeed가 있으면 HomeSafetyAssessment와 AssistiveDeviceSupport를 후보 서비스로 제안한다.
2. OlderPerson hasNeed DementiaCareNeed이면 CognitiveAssessment, DementiaScreening, FamilyCaregiverSupport를 함께 고려한다.
3. ElderAbuse가 확인되면 SafetyAssessment, ElderProtectionIntervention, LegalSupport를 우선 연결한다.
4. SocialIsolation과 DepressionRisk가 함께 있으면 MentalHealthService와 SocialParticipationProgram을 후보로 제안한다.
5. CaregiverBurden이 높으면 FamilyCaregiverSupport와 RespiteCare 성격의 서비스를 검토한다.
6. LongTermCareService가 연결되면 CarePlan과 Monitoring이 함께 있어야 한다.
7. FacilityCare가 발생하면 CareContinuityOutcome과 FollowUp을 연결한다.
8. MedicationRisk가 확인되면 HealthcareProvider 또는 PublicHealthCenter 연계를 검토한다.
9. EconomicNeed와 HousingNeed가 함께 있으면 EconomicSupport와 HousingSupport를 함께 검토한다.
10. SelfNeglect가 확인되면 SafetyAssessment, MentalHealthService, CommunityCareNetwork 연계를 검토한다.

## 10. 검증 규칙

- 모든 ElderlyWelfareCase는 최소 하나의 NeedsAssessment를 가져야 한다.
- HighRisk 사례는 RiskAssessment와 SafetyAssessment를 모두 가져야 한다.
- ServicePlan은 최소 하나의 WelfareNeed 또는 RiskFactor를 대상으로 해야 한다.
- CarePlan은 최소 하나의 Service 또는 Organization과 연결되어야 한다.
- ElderAbuse 사례는 ElderAbuse subtype과 SafetyAssessment를 가져야 한다.
- DementiaCareNeed가 있는 사례는 CognitiveAssessment 또는 DementiaSupportService와 연결되어야 한다.
- LongTermCareService가 있는 사례는 CareNeedsAssessment와 Monitoring을 가져야 한다.
- Referral은 연결 대상 Organization 또는 Service를 가져야 한다.
- Outcome은 Service, Intervention, CarePlan 중 하나 이상과 연결되어야 한다.
- 실제 개인 식별정보는 노드 라벨 또는 속성값으로 포함하지 않는다.

## 11. 질의 템플릿

### 탐색 질의

- 노인복지·돌봄 온톨로지 팩의 핵심 엔티티와 관계를 요약해줘.
- OlderPerson, Caregiver, WelfareNeed, RiskFactor, ServicePlan, CarePlan, Organization, Outcome이 어떻게 연결되는가?
- 노인복지시설, 장기요양기관, 치매지원기관, 노인보호전문기관의 역할 차이를 설명해줘.
- 노인 사례관리 흐름을 Intake부터 FollowUp까지 단계별로 설명해줘.

### 서비스 매칭 질의

- 독거와 사회적 고립 위험이 있는 노인에게 필요한 서비스와 기관은 무엇인가?
- 치매 의심과 가족돌봄자 부담이 있는 사례에서 필요한 지원은 무엇인가?
- 낙상위험과 이동제한이 있는 노인에게 필요한 서비스는 무엇인가?
- 노인학대 의심 사례에서 필요한 안전사정, 보호개입, 법률지원은 무엇인가?
- 경제취약과 주거불안이 함께 나타나는 노인 가구에 필요한 지원은 무엇인가?

### 검증 질의

- 고위험 노인복지 사례에서 RiskAssessment와 SafetyAssessment가 누락되었는지 검증하는 기준은 무엇인가?
- LongTermCareService가 연결된 사례에 CarePlan과 Monitoring이 있는지 검증해줘.
- DementiaCareNeed가 있는 사례에 CognitiveAssessment와 DementiaSupportService가 연결되었는지 확인해줘.
- ElderAbuse 사례에 학대 유형과 SafetyAssessment가 누락되어 있지 않은지 확인해줘.
- ServicePlan이 WelfareNeed와 RiskFactor에 제대로 연결되어 있는지 검증해줘.

## 12. 권장 소스 그룹

- 국가법령정보센터: 노인복지법, 노인장기요양보험법, 치매관리법 등
- 보건복지부: 노인정책, 노인복지, 장기요양, 노인돌봄, 치매정책 관련 자료
- 국민건강보험공단 장기요양보험: 장기요양보험 제도, 급여, 기관 관련 공개자료
- 중앙치매센터 또는 치매안심센터 관련 공개자료
- 노인보호전문기관 및 노인학대 예방 관련 공개자료
- 지자체 노인복지 및 통합돌봄 사업 자료
- KOSIS 등 공공통계
- WHO, OECD 등 고령화·장기돌봄 관련 국제 자료

## 13. 개인정보·민감정보 제외 원칙

이 팩은 구조화 지식과 공개 가능한 개념 관계만 포함한다.

다음 자료는 포함하지 않는다.

- 실제 노인 이름
- 주민등록번호
- 주소
- 연락처
- 장기요양 인정번호
- 의료기록 식별정보
- 가족관계 식별정보
- 후원자 정보
- 내부 사례기록
- 회계자료
- 감사 대응 내부자료
- 시설 이용자를 식별할 수 있는 민감정보
