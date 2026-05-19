# Core Entities (v0.1-r1)

This document strengthens retrieval by using explicit entity groups and bilingual labels (Korean/English).

## 1) PersonGroup (대상자 집단)

- 노숙인 / Homeless Person
- 거리노숙인 / Street Homeless Person
- 시설노숙인 / Sheltered Homeless Person
- 일시주거 이용자 / Temporary Shelter User
- 자립준비 대상자 / Self-Reliance Transition Candidate

## 2) FacilityType (시설 유형)

- 노숙인복지시설 / Homeless Welfare Facility
- 노숙인재활시설 / Rehabilitation Facility
- 노숙인자활시설 / Self-Reliance Facility
- 응급잠자리 / Emergency Shelter
- 일시보호시설 / Temporary Protection Facility
- 자활지원센터 / Self-Reliance Support Center

## 3) Service (서비스)

- 거리상담 / Street Outreach Counseling
- 긴급보호 / Emergency Protection
- 급식지원 / Meal Support
- 보건연계 / Health Linkage
- 정신건강연계 / Mental Health Referral
- 취업연계 / Employment Linkage
- 주거전환지원 / Housing Transition Support

## 4) Actor (수행 주체)

- 보건복지부 / Ministry of Health and Welfare (MOHW)
- 지방자치단체 / Local Government
- 노숙인복지시설 운영법인 / Facility Operating Organization
- 민간협력기관 / Partner NGO
- 지역고용기관 / Local Employment Agency

## 5) LegalSource (법·지침 근거)

- 법률 / Act
- 시행령 / Enforcement Decree
- 시행규칙 / Enforcement Rule
- 행정지침 / Administrative Guideline
- 지자체 조례 / Local Ordinance

## 6) PublicDataset (공개 데이터셋)

- 국가통계 / National Statistics Dataset
- 지자체 공개통계 / Local Government Open Statistics
- 정책사업 공개지표 / Public Program Indicators
- 공공데이터포털 자료 / Public Data Portal Dataset

## 7) Indicator (지표)

- 거리상담 건수 / Outreach Contacts Count
- 시설입소 건수 / Shelter Admissions Count
- 자립전환율 / Self-Reliance Transition Rate
- 주거전환율 / Housing Transition Rate
- 취업연계율 / Employment Linkage Rate

## 8) LifecycleEvent (생애주기 이벤트)

- 위기접촉 / Crisis Contact
- 응급입소 / Emergency Admission
- 사례연계 / Service Referral Event
- 프로그램등록 / Program Enrollment
- 서비스완료 / Service Completion
- 주거전환 / Housing Transition Event
- 사후점검 / Follow-up Review

## Entity Modeling Notes

- This ontology pack uses conceptual entities only (non-identifying).
- No personally identifiable information (PII) is modeled.
- Internal facility documents and case records are excluded by policy.
