# 자립준비청년·보호종료아동 온톨로지 팩 v0.1

## 0. 팩 메타

- pack_title: 자립준비청년·보호종료아동 온톨로지 팩 v0.1
- english_title: Korea Care Leaver and Transition Youth Ontology Pack
- category: document_upload
- visibility: private
- intended_use: OpenCrab, GraphRAG, 자립준비청년 지원 질의응답, 전환기 사례관리, 서비스 매칭, 정책·지침 분석
- pii_policy: 실제 자립준비청년, 보호종료아동, 보호자, 종사자, 가구의 식별정보 금지
- update_policy: 법령, 지침, 자립지원 사업, 급여 기준, 전달체계 변경 시 버전과 날짜를 포함해 업데이트

## 1. 목적과 범위

이 팩은 대한민국 자립준비청년, 보호종료아동, 아동양육시설 퇴소, 공동생활가정 퇴소, 가정위탁 종료, 자립수당, 자립정착금, 주거·교육·취업·심리정서 지원, 사후관리 체계를 구조화하기 위한 실무형 온톨로지 팩이다.

핵심 목적은 CareLeaver, ProtectedChild, OutOfHomeCareYouth, TransitionNeed, HousingNeed, EducationNeed, EmploymentNeed, MentalHealthNeed, FinancialNeed, SelfReliancePlan, AftercarePlan, ServicePlan, Referral, AftercareSupportCenter, Organization, LegalFramework, Outcome 간의 관계를 일관되게 표현하여 OpenCrab 검색, GraphRAG 질의응답, 서비스 매칭, 정책 분석, 전환기 사례관리 검증에 활용하는 것이다.

## 2. 설계 원칙

1. 보호종료 이후의 자립과 안전을 함께 본다.
2. 주거, 교육, 취업, 재정, 심리정서, 사회적 지지망을 통합적으로 모델링한다.
3. 아동복지에서 청년복지로 넘어가는 전환기 사례관리 구조를 강조한다.
4. 자립수당, 자립정착금, 주거지원, 멘토링, 사후관리를 연결한다.
5. 실제 개인 식별정보와 내부 사례기록은 포함하지 않는다.

## 3. 상위 클래스 체계

### 3.1 Person

- CareLeaver: 자립준비청년 또는 보호종료 이후 자립지원 대상
- ProtectedChild: 보호대상아동
- OutOfHomeCareYouth: 원가정 외 보호 경험 청소년
- ResidentialCareLeaver: 아동양육시설 퇴소자
- GroupHomeLeaver: 공동생활가정 퇴소자
- FosterCareLeaver: 가정위탁 종료자
- CaseWorker: 사례관리자
- Mentor: 멘토
- Caregiver: 과거 보호자 또는 지원 보호자
- Guardian: 후견인 또는 법정대리인

### 3.2 Need and Risk

- TransitionNeed: 전환기 자립 욕구
- HousingNeed: 주거 욕구
- EducationNeed: 교육 욕구
- EmploymentNeed: 취업 욕구
- MentalHealthNeed: 심리정서 욕구
- FinancialNeed: 경제·재정 욕구
- LifeSkillNeed: 생활기술 욕구
- SocialSupportNeed: 사회적 지지 욕구
- LegalNeed: 법률·권리 지원 욕구
- HealthNeed: 건강 욕구
- RiskFactor: 위험요인
- ProtectiveFactor: 보호요인
- HousingInstabilityRisk: 주거불안 위험
- UnemploymentRisk: 실업 위험
- DebtRisk: 부채 위험
- SocialIsolationRisk: 사회적 고립 위험
- MentalHealthRisk: 정신건강 위험
- ServiceGapRisk: 서비스 공백 위험

### 3.3 Case Management

- CareLeaverCase: 자립준비청년 사례
- Intake: 접수
- Screening: 초기 선별
- TransitionAssessment: 전환기 사정
- NeedsAssessment: 욕구사정
- RiskAssessment: 위험사정
- SafetyAssessment: 안전사정
- SelfReliancePlan: 자립계획
- AftercarePlan: 사후관리계획
- ServicePlan: 서비스계획
- Referral: 의뢰·연계
- CaseConference: 통합사례회의
- Monitoring: 점검
- CaseClosure: 사례종결
- FollowUp: 사후관리

### 3.4 Service and Organization

- CareLeaverSupportService: 자립준비청년 지원서비스
- SelfRelianceAllowance: 자립수당
- SettlementGrant: 자립정착금
- HousingSupport: 주거지원
- EducationSupport: 교육지원
- EmploymentSupport: 취업지원
- MentalHealthService: 심리정서지원
- FinancialEducation: 금융교육
- LifeSkillTraining: 생활기술훈련
- MentoringService: 멘토링
- LegalSupport: 법률지원
- AftercareService: 사후관리서비스
- AftercareSupportCenter: 자립지원전담기관 또는 자립지원센터
- ChildWelfareFacility: 아동복지시설
- FosterCareAgency: 가정위탁지원기관
- YouthCenter: 청년지원기관
- HousingWelfareCenter: 주거복지기관
- EmploymentCenter: 고용센터
- MentalHealthWelfareCenter: 정신건강복지센터
- PublicAgency: 공공기관
- NGO: 민간기관

### 3.5 Legal and Outcome

- LegalFramework: 법·제도
- ChildWelfareAct: 아동복지 관련 법제
- CareLeaverSupportPolicy: 자립준비청년 지원정책
- PolicyProgram: 정책사업
- Outcome: 성과
- IndependentLivingOutcome: 자립생활 성과
- HousingStabilityOutcome: 주거안정 성과
- EducationOutcome: 교육성과
- EmploymentOutcome: 고용성과
- MentalHealthOutcome: 심리정서 성과
- FinancialStabilityOutcome: 재정안정 성과
- SocialSupportOutcome: 사회적 지지 성과

## 4. 핵심 엔티티

- CareLeaver
- ProtectedChild
- OutOfHomeCareYouth
- ResidentialCareLeaver
- GroupHomeLeaver
- FosterCareLeaver
- TransitionNeed
- HousingNeed
- EducationNeed
- EmploymentNeed
- MentalHealthNeed
- FinancialNeed
- LifeSkillNeed
- SocialSupportNeed
- RiskFactor
- ProtectiveFactor
- CareLeaverCase
- TransitionAssessment
- NeedsAssessment
- RiskAssessment
- SafetyAssessment
- SelfReliancePlan
- AftercarePlan
- ServicePlan
- Referral
- Monitoring
- FollowUp
- SelfRelianceAllowance
- SettlementGrant
- HousingSupport
- EducationSupport
- EmploymentSupport
- MentalHealthService
- FinancialEducation
- LifeSkillTraining
- MentoringService
- AftercareSupportCenter
- ChildWelfareFacility
- FosterCareAgency
- YouthCenter
- HousingWelfareCenter
- EmploymentCenter
- MentalHealthWelfareCenter
- LegalFramework
- Outcome

## 5. 핵심 관계

- CareLeaver --hasNeed--> TransitionNeed
- CareLeaver --hasNeed--> HousingNeed
- CareLeaver --hasNeed--> EducationNeed
- CareLeaver --hasNeed--> EmploymentNeed
- CareLeaver --hasNeed--> MentalHealthNeed
- CareLeaver --exposedTo--> RiskFactor
- CareLeaver --protectedBy--> ProtectiveFactor
- CareLeaver --subjectOf--> CareLeaverCase
- CareLeaver --receives--> CareLeaverSupportService
- CareLeaver --hasOutcome--> Outcome
- ProtectedChild --transitionsTo--> CareLeaver
- OutOfHomeCareYouth --transitionsTo--> CareLeaver
- ResidentialCareLeaver --subclassOf--> CareLeaver
- GroupHomeLeaver --subclassOf--> CareLeaver
- FosterCareLeaver --subclassOf--> CareLeaver
- CareLeaverCase --hasTransitionAssessment--> TransitionAssessment
- CareLeaverCase --hasNeedsAssessment--> NeedsAssessment
- CareLeaverCase --hasRiskAssessment--> RiskAssessment
- CareLeaverCase --hasSafetyAssessment--> SafetyAssessment
- CareLeaverCase --hasSelfReliancePlan--> SelfReliancePlan
- CareLeaverCase --hasAftercarePlan--> AftercarePlan
- CareLeaverCase --hasServicePlan--> ServicePlan
- CareLeaverCase --hasReferral--> Referral
- CareLeaverCase --monitoredBy--> Monitoring
- CareLeaverCase --followedBy--> FollowUp
- SelfReliancePlan --targets--> TransitionNeed
- SelfReliancePlan --targets--> LifeSkillNeed
- AftercarePlan --supports--> FollowUp
- ServicePlan --targets--> HousingNeed
- ServicePlan --targets--> EmploymentNeed
- ServicePlan --mitigates--> RiskFactor
- Referral --connectsTo--> AftercareSupportCenter
- Referral --connectsTo--> HousingWelfareCenter
- Referral --connectsTo--> EmploymentCenter
- Referral --connectsTo--> MentalHealthWelfareCenter
- SelfRelianceAllowance --supports--> FinancialNeed
- SettlementGrant --supports--> FinancialNeed
- HousingSupport --targets--> HousingNeed
- MentoringService --supports--> SocialSupportNeed
- Intervention --produces--> Outcome

## 6. 시드 트리플

1. CareLeaver --hasNeed--> TransitionNeed
2. CareLeaver --hasNeed--> HousingNeed
3. CareLeaver --hasNeed--> EmploymentNeed
4. CareLeaver --hasNeed--> MentalHealthNeed
5. CareLeaver --exposedTo--> HousingInstabilityRisk
6. CareLeaver --exposedTo--> SocialIsolationRisk
7. CareLeaver --protectedBy--> MentoringService
8. ProtectedChild --transitionsTo--> CareLeaver
9. ResidentialCareLeaver --subclassOf--> CareLeaver
10. GroupHomeLeaver --subclassOf--> CareLeaver
11. FosterCareLeaver --subclassOf--> CareLeaver
12. CareLeaverCase --hasTransitionAssessment--> TransitionAssessment
13. CareLeaverCase --hasSelfReliancePlan--> SelfReliancePlan
14. CareLeaverCase --hasAftercarePlan--> AftercarePlan
15. SelfReliancePlan --targets--> LifeSkillNeed
16. AftercarePlan --supports--> FollowUp
17. ServicePlan --targets--> HousingNeed
18. ServicePlan --targets--> EmploymentNeed
19. ServicePlan --mitigates--> ServiceGapRisk
20. Referral --connectsTo--> AftercareSupportCenter
21. Referral --connectsTo--> HousingWelfareCenter
22. Referral --connectsTo--> EmploymentCenter
23. Referral --connectsTo--> MentalHealthWelfareCenter
24. SelfRelianceAllowance --supports--> FinancialNeed
25. SettlementGrant --supports--> FinancialNeed
26. HousingSupport --targets--> HousingNeed
27. MentoringService --supports--> SocialSupportNeed
28. Monitoring --tracks--> Outcome
29. FollowUp --supports--> IndependentLivingOutcome
30. Intervention --produces--> HousingStabilityOutcome

## 7. 사례관리 또는 서비스 흐름

Intake -> Screening -> TransitionAssessment -> NeedsAssessment -> RiskAssessment -> SafetyAssessment -> SelfReliancePlan -> AftercarePlan -> ServicePlan -> Referral -> Monitoring -> CaseClosure -> FollowUp

## 8. 위험요인 분류

- HousingRisk: 주거불안, 임대료 부담, 퇴거위험, 주거정보 부족
- EmploymentRisk: 실업, 불안정 노동, 직업기술 부족
- EducationRisk: 학업중단, 진학정보 부족, 교육비 부담
- MentalHealthRisk: 우울, 불안, 외로움, 외상경험
- FinancialRisk: 자산관리 어려움, 부채위험, 금융사기 위험
- SocialRisk: 사회적 고립, 지지망 부족, 관계 단절
- LifeSkillRisk: 생활관리 미숙, 행정처리 어려움, 건강관리 부족
- SystemRisk: 서비스 공백, 사후관리 단절, 기관 간 연계 부족

## 9. 보호요인 분류

- StableHousing: 안정적 주거
- EmploymentReadiness: 취업준비도
- EducationEngagement: 교육 참여
- FinancialLiteracy: 금융역량
- LifeSkillCapacity: 생활기술역량
- MentoringRelationship: 멘토링 관계
- PeerSupport: 또래 지지
- AftercareEngagement: 사후관리 참여
- ServiceNavigationSupport: 서비스 탐색 지원
- CommunitySupport: 지역사회 지지

## 10. 추론 규칙

1. CareLeaver가 HousingNeed와 HousingInstabilityRisk를 동시에 가지면 HousingSupport와 HousingWelfareCenter 연계를 우선 검토한다.
2. CareLeaver가 EmploymentNeed와 UnemploymentRisk를 가지면 EmploymentSupport와 EmploymentCenter 연계를 제안한다.
3. MentalHealthNeed와 SocialIsolationRisk가 함께 있으면 MentalHealthService와 MentoringService를 함께 검토한다.
4. FinancialNeed가 있으면 SelfRelianceAllowance, SettlementGrant, FinancialEducation을 후보 서비스로 제안한다.
5. ProtectedChild가 보호종료 예정이면 TransitionAssessment와 SelfReliancePlan이 필요하다.
6. SelfReliancePlan이 있으면 AftercarePlan과 FollowUp이 함께 연결되어야 한다.
7. ServiceGapRisk가 확인되면 Referral과 Monitoring을 강화한다.
8. HousingSupport가 연결되면 HousingStabilityOutcome을 추적해야 한다.
9. EmploymentSupport가 연결되면 EmploymentOutcome을 추적해야 한다.
10. AftercarePlan이 있으면 최소 하나의 ServicePlan 또는 Referral과 연결되어야 한다.

## 11. 검증 규칙

- 모든 CareLeaverCase는 최소 하나의 TransitionAssessment를 가져야 한다.
- 보호종료 예정 사례는 SelfReliancePlan을 가져야 한다.
- 보호종료 이후 사례는 AftercarePlan 또는 FollowUp을 가져야 한다.
- ServicePlan은 최소 하나의 TransitionNeed 또는 RiskFactor를 대상으로 해야 한다.
- HousingNeed가 있는 사례는 HousingSupport 또는 HousingWelfareCenter 연계를 검토해야 한다.
- EmploymentNeed가 있는 사례는 EmploymentSupport 또는 EmploymentCenter 연계를 검토해야 한다.
- FinancialNeed가 있는 사례는 SelfRelianceAllowance, SettlementGrant, FinancialEducation 중 하나 이상과 연결될 수 있어야 한다.
- Referral은 연결 대상 Organization 또는 Service를 가져야 한다.
- Outcome은 ServicePlan, SelfReliancePlan, AftercarePlan 중 하나 이상과 연결되어야 한다.
- 실제 개인 식별정보는 노드 라벨 또는 속성값으로 포함하지 않는다.

## 12. 질의 템플릿

- 자립준비청년·보호종료아동 온톨로지 팩의 핵심 엔티티와 관계를 요약해줘.
- 보호종료 이후 주거지원과 자립수당과 자립정착금은 어떤 욕구와 연결되는가?
- 자립준비청년의 자립계획과 사후관리계획은 어떻게 연결되는가?
- 아동양육시설 퇴소와 가정위탁 종료와 공동생활가정 퇴소 사례의 공통 지원은 무엇인가?
- 자립준비청년에게 필요한 주거지원과 취업지원과 심리정서지원은 어떻게 연결되는가?
- AftercarePlan이 HousingNeed와 EmploymentNeed와 MentalHealthNeed에 제대로 연결되었는지 검증해줘.
- ServicePlan이 TransitionNeed와 RiskFactor에 제대로 연결되었는지 검증해줘.

## 13. 권장 소스 그룹

- 보건복지부 자립준비청년 지원 공개자료
- 아동권리보장원 자립지원 공개자료
- 국가법령정보센터 아동복지 관련 법령
- 지자체 자립준비청년 지원사업 안내
- 자립지원전담기관 공개자료
- 주거복지센터 및 청년주거 지원 공개자료
- 고용노동부 청년 취업지원 공개자료
- 정신건강복지센터 및 청년마음건강 관련 공개자료

## 14. 개인정보·민감정보 제외 원칙

이 팩은 공개 가능한 구조화 지식과 개념 관계만 포함한다.

다음 자료는 포함하지 않는다.

- 실제 자립준비청년 이름
- 주민등록번호
- 주소
- 연락처
- 시설 입소·퇴소 식별 기록
- 가정위탁 이력의 식별정보
- 상담기록 원문
- 후원자 정보
- 내부 사례기록
- 회계자료
- 감사 대응 내부자료
- 개인을 특정할 수 있는 보호종료 사례 세부정보

## 15. 향후 확장 후보

- 자립수당·자립정착금 지원 온톨로지
- 자립준비청년 주거지원 온톨로지
- 보호종료 이후 사후관리 온톨로지
- 자립준비청년 멘토링 온톨로지
- 전환기 청년 정신건강 연계 온톨로지
