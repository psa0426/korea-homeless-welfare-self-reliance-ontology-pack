# 가족복지·한부모가족 온톨로지 팩 v0.1

## 0. 팩 메타
- pack_title: 가족복지·한부모가족 온톨로지 팩 v0.1
- english_title: Family Welfare and Single-Parent Family Ontology Pack
- category: general
- visibility: private
- intended_use: OpenCrab, GraphRAG, 가족복지 사례관리, 돌봄공백 대응, 서비스 연계
- pii_policy: 실제 가족/아동/보호자 식별정보 금지

## 1. 목적과 범위
대한민국 가족복지, 한부모가족, 조손가족, 청소년부모, 미혼모·미혼부, 가족상담, 양육비, 아이돌봄, 가족기능 회복 체계를 구조화한다.

## 2. 설계 원칙
1. 아동 최선의 이익과 가족기능 회복을 함께 고려한다.
2. 양육·돌봄·경제·주거·법률 욕구를 통합 사정한다.
3. 위험요인과 보호요인을 동시 모델링한다.
4. 공공·민간 연계를 표준화한다.
5. 개인정보 없이 구조 지식 중심으로 설계한다.

## 3. 상위 클래스 체계
- Family, Household, SingleParentFamily, GrandparentGrandchildFamily, TeenParentFamily, UnmarriedParentFamily
- Child, Caregiver, FamilyMember, CaseWorker
- ParentingNeed, ChildCareNeed, EconomicNeed, HousingNeed, LegalNeed, FamilyRelationshipNeed
- CareGap, FamilyConflict, ChildSupportPaymentIssue, RiskFactor, ProtectiveFactor
- FamilyWelfareCase, FamilyAssessment, ParentingAssessment, ServicePlan, Referral, Monitoring, FollowUp
- FamilyCenter, SingleParentFamilySupportService, ChildCareService, ChildSupportAgency, LegalAidOrganization
- SingleParentFamilySupportAct, Outcome

## 4. 핵심 엔티티
Family, Household, SingleParentFamily, GrandparentGrandchildFamily, TeenParentFamily, UnmarriedParentFamily, Caregiver, Child, ParentingNeed, ChildCareNeed, EconomicNeed, HousingNeed, LegalNeed, FamilyRelationshipNeed, CareGap, FamilyConflict, ChildSupportPaymentIssue, RiskFactor, ProtectiveFactor, FamilyWelfareCase, FamilyAssessment, ParentingAssessment, ServicePlan, Referral, Monitoring, FamilyCenter, SingleParentFamilySupportService, ChildCareService, ChildSupportAgency, LegalAidOrganization, SingleParentFamilySupportAct, Outcome

## 5. 핵심 관계
- Family --hasMember--> Person
- Family --hasNeed--> FamilyNeed
- SingleParentFamily --hasNeed--> ParentingNeed
- SingleParentFamily --hasNeed--> EconomicNeed
- FamilyWelfareCase --hasAssessment--> FamilyAssessment
- FamilyWelfareCase --hasParentingAssessment--> ParentingAssessment
- FamilyWelfareCase --hasServicePlan--> ServicePlan
- ServicePlan --targets--> ParentingNeed
- ServicePlan --targets--> ChildCareNeed
- ServicePlan --targets--> EconomicNeed
- ServicePlan --mitigates--> FamilyConflict
- ServicePlan --mitigates--> CareGap
- Referral --connectsTo--> FamilyCenter
- Referral --connectsTo--> ChildSupportAgency
- Referral --connectsTo--> LegalAidOrganization
- FamilyCenter --provides--> FamilyCounseling
- ChildCareService --supports--> CareGap
- Intervention --produces--> Outcome

## 6. 시드 트리플
1. Family --hasMember--> Child
2. SingleParentFamily --hasNeed--> ParentingNeed
3. SingleParentFamily --hasNeed--> EconomicNeed
4. TeenParentFamily --hasNeed--> ParentingNeed
5. UnmarriedParentFamily --hasNeed--> LegalNeed
6. Family --hasNeed--> FamilyRelationshipNeed
7. Family --hasNeed--> HousingNeed
8. Family --exposedTo--> FamilyConflict
9. Family --exposedTo--> CareGap
10. Family --exposedTo--> ChildSupportPaymentIssue
11. FamilyWelfareCase --hasAssessment--> FamilyAssessment
12. FamilyWelfareCase --hasParentingAssessment--> ParentingAssessment
13. FamilyWelfareCase --hasServicePlan--> ServicePlan
14. ServicePlan --targets--> ParentingNeed
15. ServicePlan --targets--> ChildCareNeed
16. ServicePlan --targets--> EconomicNeed
17. ServicePlan --targets--> HousingNeed
18. ServicePlan --mitigates--> FamilyConflict
19. ServicePlan --mitigates--> CareGap
20. Referral --connectsTo--> FamilyCenter
21. Referral --connectsTo--> ChildSupportAgency
22. Referral --connectsTo--> LegalAidOrganization
23. FamilyCenter --provides--> FamilyCounseling
24. ChildCareService --supports--> CareGap
25. ChildSupportAgency --provides--> ChildSupportPaymentEnforcement
26. LegalAidOrganization --provides--> LegalSupport
27. Monitoring --tracks--> Outcome
28. Intervention --produces--> FamilyStabilityOutcome

## 7. 사례관리 또는 서비스 흐름
Intake -> Screening -> FamilyAssessment -> ParentingAssessment -> ServicePlan -> Referral -> Monitoring -> FollowUp -> CaseClosure

## 8. 위험요인 분류
- ParentingRisk: 양육기술 부족, 돌봄과부하
- EconomicRisk: 소득불안, 채무위험
- HousingRisk: 주거불안, 주거환경 위험
- RelationshipRisk: 가족갈등, 양육갈등
- LegalRisk: 양육비 미이행, 법적 보호 공백
- CareRisk: 돌봄공백, 긴급돌봄 부재

## 9. 보호요인 분류
- StableCaregiver
- ExtendedFamilySupport
- ChildCareAccess
- FamilyCounselingEngagement
- IncomeSupportAccess
- LegalSupportAccess
- CommunitySupportNetwork

## 10. 추론 규칙
1. ParentingNeed + CareGap이면 ChildCareService 우선 연계.
2. EconomicNeed + HousingNeed 동시 발생 시 생계·주거지원 동시 검토.
3. ChildSupportPaymentIssue가 있으면 ChildSupportAgency + LegalAidOrganization 동시 연계.
4. FamilyConflict 고위험이면 FamilyCounseling과 Monitoring 주기 단축.
5. TeenParentFamily는 교육·양육 병행지원 항목을 ServicePlan에 포함.

## 11. 검증 규칙
1. 모든 FamilyWelfareCase는 최소 1개 FamilyAssessment를 가져야 한다.
2. ServicePlan은 최소 1개 Need와 연결되어야 한다.
3. CareGap 사례는 ChildCareService 또는 대체돌봄 연계가 있어야 한다.
4. ChildSupportPaymentIssue 사례는 ChildSupportAgency 연계가 있어야 한다.
5. Monitoring이 있으면 최소 1개 Outcome 추적이 있어야 한다.
6. 개인 식별정보를 포함하지 않는다.

## 12. 질의 템플릿
- 가족복지·한부모가족 온톨로지 팩의 핵심 엔티티와 관계를 요약해줘.
- 한부모가족의 양육욕구와 경제욕구와 주거욕구는 어떤 서비스와 연결되는가?
- 가족센터와 양육비 이행지원 기관과 아이돌봄서비스의 역할 차이를 설명해줘.
- 가족갈등과 돌봄공백이 함께 있는 사례에서 필요한 지원 절차를 설명해줘.
- 청소년부모 사례에서 교육지원과 양육지원과 경제지원은 어떻게 연결되는가?
- ServicePlan이 ParentingNeed와 EconomicNeed에 제대로 연결되었는지 검증해줘.

## 13. 권장 소스 그룹
- 국가법령정보센터: 한부모가족지원 관련 법령
- 여성가족부: 한부모·가족정책 지침
- 지자체 가족센터 운영 안내
- 아이돌봄서비스 공개자료
- 양육비 이행지원 제도 안내자료

## 14. 개인정보·민감정보 제외 원칙
실제 이름, 주소, 연락처, 주민등록번호, 사례기록 원문, 민감한 가족상황 식별정보를 포함하지 않는다.

## 15. 향후 확장 후보
- 이혼·별거 전환기 가족 지원 세부 온톨로지
- 가족돌봄자 번아웃 조기경보 지표
- 지역별 돌봄자원 접근성 지표 통합
