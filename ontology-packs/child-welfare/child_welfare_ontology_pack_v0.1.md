# 아동복지 온톨로지 팩 v0.1

## 0. 팩 메타
- pack_title: 아동복지 온톨로지 팩 v0.1
- english_title: Korea Child Welfare Ontology Pack
- category: general
- visibility: private
- intended_use: GraphRAG, 사례관리 질의응답, 서비스 매칭, 정책·지침 구조화, 기관 협업 지식베이스
- pii_policy: 실제 아동·보호자·종사자·가구 식별정보 금지
- update_policy: 법령·지침·사업 변경 시 날짜가 포함된 event update로 관리

## 1. 목적과 범위
이 팩은 기존 노숙인 온톨로지 팩과 같은 실무형 복지 도메인 구조를 아동복지 영역에 적용한 것이다.  
아동, 보호자, 가구, 위험요인, 보호요인, 아동학대, 보호조치, 사례관리, 서비스, 기관, 법·제도, 성과지표 간의 관계를 구조화하여 검색, 질의응답, 사례 분류, 서비스 매칭, 정책 분석, 데이터 통합에 활용한다.

범위는 대한민국 아동복지 체계를 중심으로 하되, 국제적으로 통용되는 아동권리 원칙, 위험·보호요인 프레임, 사례관리 프레임을 함께 반영한다.

## 2. 설계 원칙
1. 아동 최선의 이익: 모든 개념과 관계는 아동의 안전, 발달, 권리, 복지를 중심으로 해석한다.
2. 권리 기반 접근: 아동은 보호 대상일 뿐 아니라 권리 주체이다.
3. 생태체계 관점: 아동 문제는 개인, 가족, 학교, 지역사회, 제도 환경의 상호작용으로 본다.
4. 위험·보호요인 균형: 위험요인뿐 아니라 회복탄력성, 지지망, 보호요인을 함께 모델링한다.
5. 현장 활용성: 사례관리, 서비스 연계, 기관 협업, 정책 모니터링에 필요한 질의를 우선한다.
6. 비식별성: 실제 인물명, 주민등록번호, 주소, 연락처 등 개인정보성 속성은 팩에 포함하지 않는다.

## 3. 상위 클래스 체계

### 3.1 Person
- Child: 아동
- Caregiver: 보호자·양육자
- Parent: 부모
- Guardian: 법정대리인·후견인
- FosterParent: 위탁부모
- CaseWorker: 사례관리자
- ChildProtectionOfficer: 아동보호전담공무원
- Professional: 의료·심리·교육·사법 등 전문인력

### 3.2 Household and Environment
- Household: 가구
- FamilySystem: 가족체계
- SchoolEnvironment: 학교환경
- CommunityEnvironment: 지역사회환경
- DigitalEnvironment: 디지털환경

### 3.3 Need, Risk, Protection
- WelfareNeed: 복지욕구
- SafetyNeed: 안전욕구
- CareNeed: 돌봄욕구
- EconomicNeed: 경제욕구
- HousingNeed: 주거욕구
- HealthNeed: 건강욕구
- MentalHealthNeed: 정신건강욕구
- EducationNeed: 교육욕구
- LegalNeed: 법률지원욕구
- RiskFactor: 위험요인
- ProtectiveFactor: 보호요인
- SafetyConcern: 안전우려
- DevelopmentalConcern: 발달우려
- TraumaExposure: 외상경험

### 3.4 Maltreatment
- ChildMaltreatment: 아동학대·방임 상위개념
- PhysicalAbuse: 신체학대
- EmotionalAbuse: 정서학대
- SexualAbuse: 성학대
- Neglect: 방임
- MedicalNeglect: 의료적 방임
- EducationalNeglect: 교육적 방임
- SupervisoryNeglect: 보호·감독 방임
- DomesticViolenceExposure: 가정폭력 노출
- Exploitation: 착취

### 3.5 Intervention and Service
- Intervention: 개입
- EmergencyProtection: 응급보호
- ProtectivePlacement: 보호배치
- FosterCare: 가정위탁
- ResidentialCare: 시설보호
- GroupHomeCare: 공동생활가정
- FamilyPreservationService: 원가정 기능회복 서비스
- CounselingService: 상담서비스
- MentalHealthService: 정신건강서비스
- MedicalService: 의료서비스
- EducationalSupport: 교육지원
- EconomicSupport: 경제지원
- LegalSupport: 법률지원
- AftercareService: 사후관리

### 3.6 Case Management
- ChildWelfareCase: 아동복지 사례
- Intake: 접수
- Screening: 초기 선별
- Assessment: 사정
- SafetyAssessment: 안전 사정
- RiskAssessment: 위험 사정
- ServicePlan: 서비스 계획
- CaseConference: 통합사례회의
- Referral: 의뢰·연계
- Monitoring: 점검
- CaseClosure: 사례 종결
- FollowUp: 사후관리

### 3.7 Organization and Governance
- PublicAgency: 지자체·공공기관
- ChildProtectionAgency: 아동보호전문기관
- ChildWelfareFacility: 아동복지시설
- FosterCareAgency: 가정위탁지원기관
- School: 학교
- HealthcareProvider: 의료기관
- PoliceAgency: 경찰
- Court: 법원
- NGO: 민간기관
- CommunityResource: 지역사회 자원

### 3.8 Law, Policy, Program
- LegalFramework: 법·제도
- ChildWelfareAct: 아동복지법
- ChildAbuseCrimeAct: 아동학대범죄 관련 특례 법제
- UNCRC: 유엔아동권리협약 원칙
- PolicyProgram: 정책사업
- ChildProtectionSystem: 아동보호체계
- DreamStartProgram: 드림스타트 등 취약계층 아동 통합서비스

### 3.9 Outcome and Indicator
- Outcome: 성과
- SafetyOutcome: 안전 성과
- PermanencyOutcome: 안정적 보호환경·영구성 성과
- WellbeingOutcome: 건강·발달·교육·심리정서 성과
- ServiceUtilizationIndicator: 서비스 이용 지표
- CaseProgressIndicator: 사례 진행 지표
- RiskReductionIndicator: 위험 감소 지표

## 4. 핵심 속성

### Child
- age_group
- legal_status
- developmental_stage
- school_status
- disability_status
- primary_needs
- safety_level
- case_status

### Household
- household_type
- economic_vulnerability
- housing_stability
- caregiving_capacity
- support_network_strength

### RiskFactor
- risk_domain
- severity
- chronicity
- immediacy
- evidence_type

### Service
- service_domain
- eligibility
- delivery_mode
- intensity
- duration
- provider_type

## 5. 핵심 관계
- Child --livesIn--> Household
- Child --memberOf--> FamilySystem
- Child --attends--> School
- Child --hasNeed--> WelfareNeed
- Child --exposedTo--> RiskFactor
- Child --protectedBy--> ProtectiveFactor
- Child --subjectOf--> ChildWelfareCase
- Child --affectedBy--> ChildMaltreatment
- Child --receives--> Service
- Child --placedIn--> ProtectivePlacement
- Child --hasOutcome--> Outcome
- Caregiver --caresFor--> Child
- Caregiver --hasRiskFactor--> RiskFactor
- Caregiver --participatesIn--> Service
- Household --hasRiskFactor--> RiskFactor
- Household --hasProtectiveFactor--> ProtectiveFactor
- Household --receives--> EconomicSupport
- ChildWelfareCase --hasIntake--> Intake
- ChildWelfareCase --includesAssessment--> Assessment
- ChildWelfareCase --hasSafetyAssessment--> SafetyAssessment
- ChildWelfareCase --hasRiskAssessment--> RiskAssessment
- ChildWelfareCase --hasServicePlan--> ServicePlan
- ChildWelfareCase --discussedIn--> CaseConference
- ChildWelfareCase --hasReferral--> Referral
- ChildWelfareCase --monitoredBy--> Monitoring
- ChildWelfareCase --closedBy--> CaseClosure
- ChildWelfareCase --followedBy--> FollowUp
- RiskAssessment --identifies--> RiskFactor
- SafetyAssessment --identifies--> SafetyConcern
- ServicePlan --targets--> WelfareNeed
- ServicePlan --mitigates--> RiskFactor
- ServicePlan --leverages--> ProtectiveFactor
- Referral --connectsTo--> Organization
- Organization --provides--> Service
- Organization --governedBy--> LegalFramework
- Intervention --produces--> Outcome

## 6. 시드 트리플
1. Child --hasNeed--> WelfareNeed
2. Child --exposedTo--> RiskFactor
3. Child --protectedBy--> ProtectiveFactor
4. Child --affectedBy--> ChildMaltreatment
5. ChildMaltreatment --includes--> PhysicalAbuse
6. ChildMaltreatment --includes--> EmotionalAbuse
7. ChildMaltreatment --includes--> SexualAbuse
8. ChildMaltreatment --includes--> Neglect
9. Neglect --includes--> MedicalNeglect
10. Neglect --includes--> EducationalNeglect
11. Household --hasRiskFactor--> EconomicVulnerability
12. Household --hasRiskFactor--> HousingInstability
13. Caregiver --hasRiskFactor--> SubstanceUseProblem
14. Caregiver --hasRiskFactor--> MentalHealthConcern
15. Child --receives--> CounselingService
16. Child --receives--> MedicalService
17. Household --receives--> EconomicSupport
18. ChildWelfareCase --includesAssessment--> RiskAssessment
19. ChildWelfareCase --hasServicePlan--> ServicePlan
20. ServicePlan --targets--> WelfareNeed
21. ServicePlan --mitigates--> RiskFactor
22. ChildProtectionAgency --provides--> ChildProtectionService
23. PublicAgency --coordinates--> ChildProtectionSystem
24. School --reports--> SafetyConcern
25. HealthcareProvider --identifies--> MedicalNeglect
26. PoliceAgency --respondsTo--> EmergencyProtection
27. Court --issues--> ProtectiveOrder
28. ProtectivePlacement --includes--> FosterCare
29. ProtectivePlacement --includes--> ResidentialCare
30. AftercareService --supports--> PermanencyOutcome
31. Intervention --produces--> SafetyOutcome
32. Intervention --produces--> WellbeingOutcome
33. LegalFramework --governs--> Organization
34. ChildWelfareAct --governs--> ChildWelfareService
35. UNCRC --supportsPrinciple--> BestInterestsOfChild

## 7. 위험요인 분류
- ChildLevelRisk: 발달지연, 장애, 질병, 행동문제, 고립, 자해위험
- CaregiverLevelRisk: 양육기술 부족, 정신건강 문제, 중독, 폭력성, 방임 태도
- HouseholdLevelRisk: 빈곤, 주거불안, 가족갈등, 가정폭력, 보호자 부재
- SchoolLevelRisk: 장기결석, 학업중단, 학교폭력, 또래 고립
- CommunityLevelRisk: 지역자원 부족, 범죄·폭력 환경, 의료·돌봄 접근성 부족
- DigitalRisk: 사이버폭력, 온라인 그루밍, 유해콘텐츠, 디지털 성착취 위험
- SystemLevelRisk: 서비스 단절, 기관 간 정보 연계 부족, 사후관리 미흡

## 8. 보호요인 분류
- StableCaregiver
- PositiveAttachment
- SupportiveSchool
- PeerSupport
- CommunitySupportNetwork
- ServiceEngagement
- EconomicStabilization
- TraumaInformedCare
- ChildParticipation

## 9. 사례관리 흐름
1. Intake: 신고, 의뢰, 직접 신청, 기관 연계로 사례 접수
2. Screening: 긴급성, 아동 안전, 학대 의심, 기본 욕구 선별
3. Assessment: 아동·보호자·가구·학교·지역사회 수준의 위험·보호요인 사정
4. SafetyPlanning: 즉각 위험이 있으면 안전계획 수립
5. ServicePlanning: 욕구와 위험요인에 맞춰 서비스 계획 수립
6. Referral: 서비스 제공기관 연결
7. Monitoring: 서비스 이용, 위험 변화, 아동 상태 점검
8. CaseConference: 복합사례 통합사례회의 조정
9. Closure: 목표 달성, 위험 감소, 서비스 전환, 타 기관 이관 등으로 종결
10. FollowUp: 재위험, 서비스 공백, 보호환경 안정성 확인

## 10. 질의 템플릿

### 탐색 질의
- 특정 아동복지 사례에서 핵심 위험요인은 무엇인가?
- 위험요인이 높은 사례에 연결 가능한 서비스는 무엇인가?
- 방임과 관련된 하위 유형과 관련 서비스는 무엇인가?
- 아동의 교육 욕구와 연결된 기관 유형은 무엇인가?
- 가구 수준 위험요인과 보호요인을 함께 보여줘.

### 서비스 매칭 질의
- 정신건강 욕구가 있는 아동에게 필요한 서비스와 기관은 무엇인가?
- 주거불안과 경제취약성이 함께 나타나는 가구에 필요한 지원은 무엇인가?
- 성학대 피해 아동 사례에서 필요한 의료, 심리, 법률 서비스는 무엇인가?
- 장기결석 위험이 있는 아동에게 연계할 수 있는 교육지원은 무엇인가?

### 정책·운영 질의
- 아동보호체계에서 공공기관과 민간기관의 역할은 어떻게 연결되는가?
- 응급보호에서 보호배치까지 어떤 절차와 기관이 관여하는가?
- 사례 종결 이후 사후관리 지표는 무엇인가?
- 안전 성과, 영구성 성과, 웰빙 성과를 측정할 수 있는 지표는 무엇인가?

### 품질검증 질의
- 서비스계획이 식별된 위험요인과 실제로 연결되어 있는가?
- 고위험 사례에 안전계획이 누락되어 있지 않은가?
- 보호배치 이후 사후관리 노드가 연결되어 있는가?
- 아동의 욕구와 제공 서비스 간 미스매치가 있는가?

## 11. 추론 규칙
1. Child affectedBy PhysicalAbuse이면 Child affectedBy ChildMaltreatment로 추론한다.
2. Child affectedBy Neglect이고 MedicalNeed가 미충족이면 MedicalNeglect 가능성을 검토한다.
3. Household hasRiskFactor HousingInstability이고 Child hasNeed SafetyNeed이면 ProtectivePlacement 또는 HousingSupport를 후보 서비스로 제안한다.
4. Caregiver hasRiskFactor MentalHealthConcern이고 Child hasNeed CareNeed이면 FamilyPreservationService와 MentalHealthService를 함께 고려한다.
5. Child hasRiskFactor LongTermAbsence이면 EducationalSupport 및 SchoolEnvironment 평가를 제안한다.
6. ChildWelfareCase hasRiskAssessment HighRisk이면 SafetyAssessment와 SafetyPlanning이 필수 연결되어야 한다.
7. ServicePlan targets WelfareNeed이고 ServicePlan mitigates RiskFactor이면 Monitoring을 통해 Outcome을 추적해야 한다.
8. ProtectivePlacement가 발생하면 PermanencyOutcome과 AftercareService를 연결해야 한다.
9. Child affectedBy SexualAbuse이면 MedicalService, CounselingService, LegalSupport, SafetyPlanning을 우선 후보로 제안한다.
10. DigitalRisk가 확인되면 CounselingService, LegalSupport, SchoolEnvironment 개입, PoliceAgency 연계를 검토한다.

## 12. 검증 규칙
- 모든 ChildWelfareCase는 최소 하나의 Assessment를 가져야 한다.
- HighRisk 사례는 SafetyAssessment와 ServicePlan을 모두 가져야 한다.
- ChildMaltreatment 사례는 Maltreatment subtype을 최소 하나 이상 가져야 한다.
- ServicePlan은 최소 하나의 WelfareNeed 또는 RiskFactor를 대상으로 해야 한다.
- Referral은 연결 대상 Organization 또는 Service를 가져야 한다.
- ProtectivePlacement는 배치 유형과 사후관리 계획을 가져야 한다.
- Outcome은 Intervention 또는 ServicePlan과 연결되어야 한다.
- 실제 개인 식별정보는 노드 라벨 또는 속성값으로 포함하지 않는다.

## 13. 권장 소스 그룹
- 대한민국 법령: 아동복지법, 아동학대범죄 관련 특례 법제, 아동·청소년 보호 관련 법령
- 보건복지부: 아동정책, 아동보호, 보호대상아동, 드림스타트, 취약계층 아동지원 자료
- 아동권리보장원: 아동보호체계, 아동학대 예방, 실무자료
- 지자체 아동보호 및 통합사례관리 자료
- 유엔아동권리협약 및 국제 아동권리 자료
- WHO, UNICEF 등 아동 안전·학대·복지 관련 국제 자료

## 14. 향후 확장 후보
- 보호대상아동 자립지원 온톨로지
- 아동학대 대응 절차 온톨로지
- 위탁·입양·시설보호 배치 온톨로지
- 드림스타트 통합서비스 온톨로지
- 학교 기반 아동위기 조기발견 온톨로지
- 디지털 성착취 및 온라인 위험 대응 온톨로지
- 장애아동 복지서비스 온톨로지

## 15. OpenCrab 인제스트용 메타
```json
{
  "title": "아동복지 온톨로지 팩 v0.1",
  "workspace_label": "사회복지 온톨로지",
  "create_pack": true,
  "pack_title": "아동복지 온톨로지 팩 v0.1",
  "pack_description": "노숙인 온톨로지 팩과 유사한 실무형 구조로 구성한 아동복지 도메인 온톨로지 팩. 아동, 보호자, 가구, 위험요인, 보호요인, 아동학대, 보호조치, 사례관리, 서비스, 기관, 법·제도, 성과지표를 중심으로 엔티티·관계·시드 트리플·검색질문·검증규칙을 포함한다.",
  "pack_category": "general",
  "pack_visibility": "private"
}
```
