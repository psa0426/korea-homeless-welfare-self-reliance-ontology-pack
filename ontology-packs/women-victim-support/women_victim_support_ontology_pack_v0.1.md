# 여성복지·폭력피해지원 온톨로지 팩 v0.1

## 0. 팩 메타
- pack_title: 여성복지·폭력피해지원 온톨로지 팩 v0.1
- english_title: Women Welfare and Violence Victim Support Ontology Pack
- category: general
- visibility: private
- intended_use: OpenCrab, GraphRAG, 위기개입·보호연계·법률지원 사례관리
- pii_policy: 실제 피해자/가족/종사자 식별정보 금지

## 1. 목적과 범위
대한민국 여성복지, 가정폭력·성폭력·스토킹·디지털성범죄 피해지원, 긴급피난, 상담, 보호시설, 의료·법률지원, 자립지원 체계를 구조화한다.

## 2. 설계 원칙
1. 피해자 안전과 자기결정권을 최우선으로 한다.
2. 안전·의료·법률·주거·심리 지원을 통합 사정한다.
3. 2차 피해 예방과 비밀보장을 기본 원칙으로 둔다.
4. 다기관 협력(상담소-보호시설-경찰-법원-법률구조) 구조를 명시한다.
5. 개인정보 없이 구조화 지식 중심으로 작성한다.

## 3. 상위 클래스 체계
- Woman, VictimSurvivor, FamilyViolenceVictim, SexualViolenceVictim, StalkingVictim, DigitalSexCrimeVictim, SexTradeVictim
- ViolenceType, SafetyNeed, MedicalNeed, LegalNeed, HousingNeed, PsychologicalSupportNeed, EconomicNeed, RiskFactor, ProtectiveFactor
- WomenSupportCase, CrisisAssessment, SafetyAssessment, ProtectionPlan, ServicePlan, Referral, Monitoring, FollowUp
- EmergencyShelter, CounselingService, MedicalSupport, LegalSupport, InvestigationSupport, CourtSupport, SelfRelianceSupport
- WomenEmergencyHotline1366, CounselingCenter, ProtectionFacility, PoliceAgency, Court, LegalAidOrganization
- Outcome, SafetyOutcome, RecoveryOutcome, SelfRelianceOutcome

## 4. 핵심 엔티티
Woman, VictimSurvivor, FamilyViolenceVictim, SexualViolenceVictim, StalkingVictim, DigitalSexCrimeVictim, SexTradeVictim, ViolenceType, SafetyNeed, MedicalNeed, LegalNeed, HousingNeed, PsychologicalSupportNeed, EconomicNeed, RiskFactor, ProtectiveFactor, WomenSupportCase, CrisisAssessment, SafetyAssessment, ProtectionPlan, ServicePlan, EmergencyShelter, CounselingService, MedicalSupport, LegalSupport, InvestigationSupport, CourtSupport, SelfRelianceSupport, WomenEmergencyHotline1366, CounselingCenter, ProtectionFacility, PoliceAgency, Court, LegalAidOrganization, Outcome

## 5. 핵심 관계
- VictimSurvivor --affectedBy--> ViolenceType
- VictimSurvivor --hasNeed--> SafetyNeed
- VictimSurvivor --hasNeed--> MedicalNeed
- VictimSurvivor --hasNeed--> LegalNeed
- VictimSurvivor --hasNeed--> HousingNeed
- VictimSurvivor --subjectOf--> WomenSupportCase

- WomenSupportCase --hasCrisisAssessment--> CrisisAssessment
- WomenSupportCase --hasSafetyAssessment--> SafetyAssessment
- WomenSupportCase --hasProtectionPlan--> ProtectionPlan
- WomenSupportCase --hasServicePlan--> ServicePlan
- WomenSupportCase --hasReferral--> Referral
- WomenSupportCase --monitoredBy--> Monitoring
- WomenSupportCase --followedBy--> FollowUp

- ServicePlan --targets--> SafetyNeed
- ServicePlan --targets--> MedicalNeed
- ServicePlan --targets--> LegalNeed
- ServicePlan --targets--> PsychologicalSupportNeed
- ServicePlan --mitigates--> RiskFactor

- Referral --connectsTo--> WomenEmergencyHotline1366
- Referral --connectsTo--> ProtectionFacility
- Referral --connectsTo--> CounselingCenter
- Referral --connectsTo--> PoliceAgency
- Referral --connectsTo--> LegalAidOrganization
- Referral --connectsTo--> Court

- CounselingCenter --provides--> CounselingService
- ProtectionFacility --provides--> EmergencyShelter
- LegalAidOrganization --provides--> LegalSupport
- PoliceAgency --supports--> InvestigationSupport
- Court --supports--> CourtSupport
- Intervention --produces--> SafetyOutcome

## 6. 시드 트리플
1. VictimSurvivor --affectedBy--> FamilyViolence
2. VictimSurvivor --affectedBy--> SexualViolence
3. VictimSurvivor --affectedBy--> Stalking
4. VictimSurvivor --affectedBy--> DigitalSexCrime
5. VictimSurvivor --hasNeed--> SafetyNeed
6. VictimSurvivor --hasNeed--> MedicalNeed
7. VictimSurvivor --hasNeed--> LegalNeed
8. VictimSurvivor --hasNeed--> HousingNeed
9. VictimSurvivor --hasNeed--> PsychologicalSupportNeed
10. VictimSurvivor --subjectOf--> WomenSupportCase
11. WomenSupportCase --hasCrisisAssessment--> CrisisAssessment
12. WomenSupportCase --hasSafetyAssessment--> SafetyAssessment
13. WomenSupportCase --hasProtectionPlan--> ProtectionPlan
14. WomenSupportCase --hasServicePlan--> ServicePlan
15. ServicePlan --targets--> SafetyNeed
16. ServicePlan --targets--> LegalNeed
17. ServicePlan --targets--> PsychologicalSupportNeed
18. ServicePlan --mitigates--> RetaliationRisk
19. Referral --connectsTo--> WomenEmergencyHotline1366
20. Referral --connectsTo--> ProtectionFacility
21. Referral --connectsTo--> CounselingCenter
22. Referral --connectsTo--> PoliceAgency
23. Referral --connectsTo--> LegalAidOrganization
24. CounselingCenter --provides--> CounselingService
25. ProtectionFacility --provides--> EmergencyShelter
26. LegalAidOrganization --provides--> LegalSupport
27. PoliceAgency --supports--> InvestigationSupport
28. Court --supports--> CourtSupport
29. Intervention --produces--> SafetyOutcome
30. Monitoring --tracks--> RecoveryOutcome

## 7. 사례관리 또는 서비스 흐름
Intake -> CrisisAssessment -> SafetyAssessment -> ProtectionPlan -> ServicePlan -> Referral -> Monitoring -> FollowUp -> CaseClosure

## 8. 위험요인 분류
- ImmediateSafetyRisk: 보복위험, 재접촉위험, 신변위협
- LegalProcessRisk: 법적대응 지연, 증거확보 어려움
- HousingRisk: 긴급주거 부재, 안전주거 접근성 부족
- HealthRisk: 신체·정신건강 악화 위험
- SocialRisk: 고립, 낙인, 2차 피해 위험
- EconomicRisk: 생계중단, 소득상실

## 9. 보호요인 분류
- EmergencyShelterAccess
- HotlineAccess1366
- LegalSupportAccess
- TraumaInformedCounseling
- CoordinatedMultiAgencyResponse
- TrustedSupportNetwork
- FinancialStabilizationSupport

## 10. 추론 규칙
1. SafetyNeed + ImmediateSafetyRisk이면 EmergencyShelter와 경찰연계를 우선 제안한다.
2. LegalNeed가 있으면 LegalAidOrganization 연계를 필수 검토한다.
3. DigitalSexCrimeVictim이면 삭제지원·수사연계·심리지원을 동시 제안한다.
4. StalkingRisk가 높으면 접근금지 등 법적 보호조치 연계를 강화한다.
5. HousingNeed가 있으면 ProtectionFacility 또는 안전주거 연계를 포함한다.

## 11. 검증 규칙
1. 모든 WomenSupportCase는 최소 1개의 CrisisAssessment를 가져야 한다.
2. 고위험 사례는 SafetyAssessment를 반드시 포함해야 한다.
3. ProtectionPlan은 SafetyNeed 또는 LegalNeed와 연결되어야 한다.
4. ServicePlan은 최소 1개의 Need를 targets 해야 한다.
5. Referral은 최소 1개 지원기관과 연결되어야 한다.
6. Monitoring이 있으면 최소 1개 Outcome 추적 링크가 있어야 한다.
7. 개인 식별정보를 포함하지 않는다.

## 12. 질의 템플릿
- 여성복지·폭력피해지원 온톨로지 팩의 핵심 엔티티와 관계를 요약해줘.
- 가정폭력 피해지원에서 안전사정과 보호계획과 법률지원은 어떻게 연결되는가?
- 여성긴급전화 1366과 상담소와 보호시설의 역할 차이를 설명해줘.
- 스토킹 피해 사례에서 필요한 안전지원과 법률지원과 심리상담은 무엇인가?
- 디지털성범죄 피해지원에서 상담과 삭제지원과 수사연계는 어떻게 구조화되는가?
- ProtectionPlan이 SafetyNeed와 LegalNeed에 제대로 연결되었는지 검증해줘.

## 13. 권장 소스 그룹
- 국가법령정보센터: 여성폭력·피해자보호 관련 법령
- 여성가족부: 피해자 지원 지침/사업 안내
- 지자체: 상담소·보호시설 운영 안내
- 법률구조기관·경찰청 공개 안내자료

## 14. 개인정보·민감정보 제외 원칙
실제 피해자 이름, 주소, 연락처, 사건식별정보, 의료기록 식별정보, 수사기록 원문, 내부 사례기록을 포함하지 않는다.

## 15. 향후 확장 후보
- 디지털성범죄 삭제지원 세부 프로세스 모델
- 보호명령·사법절차 타임라인 온톨로지 확장
- 2차피해 예방 지표 및 재피해 위험 예측 규칙 확장
