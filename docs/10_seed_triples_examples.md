# Seed Triples Examples (v0.1-r1)

Format: `subject | predicate | object | evidence_note`

1. Homeless Person | DEFINED_BY | Act | Public legal definition required
2. Street Homeless Person | DEFINED_BY | Act | Public legal definition required
3. Sheltered Homeless Person | DEFINED_BY | Administrative Guideline | Public guideline definition
4. Self-Reliance Transition Candidate | DEFINED_BY | Administrative Guideline | Program eligibility text
5. Homeless Welfare Facility | REGULATED_BY | Act | Facility legal basis
6. Rehabilitation Facility | REGULATED_BY | Enforcement Rule | Facility operation requirements
7. Self-Reliance Facility | REGULATED_BY | Administrative Guideline | Self-reliance support scope
8. Emergency Shelter | REGULATED_BY | Local Ordinance | Local emergency shelter operations
9. Temporary Protection Facility | REGULATED_BY | Local Ordinance | Temporary accommodation governance
10. Self-Reliance Support Center | REGULATED_BY | Administrative Guideline | Service delivery framework
11. Homeless Welfare Facility | OPERATED_BY | Facility Operating Organization | Publicly disclosed operator role
12. Rehabilitation Facility | OPERATED_BY | Local Government | Public administration/contract model
13. Self-Reliance Facility | OPERATED_BY | Facility Operating Organization | Publicly disclosed operator role
14. Emergency Shelter | OPERATED_BY | Partner NGO | Public partnership arrangement
15. Street Outreach Counseling | TARGETS | Street Homeless Person | Outreach target group
16. Emergency Protection | TARGETS | Homeless Person | Immediate safety target
17. Meal Support | TARGETS | Homeless Person | Basic living support target
18. Employment Linkage | TARGETS | Self-Reliance Transition Candidate | Transition support target
19. Housing Transition Support | TARGETS | Self-Reliance Transition Candidate | Housing transition target
20. Mental Health Referral | TARGETS | Homeless Person | Public health linkage target
21. Self-Reliance Facility | PROVIDES | Employment Linkage | Service provision relation
22. Rehabilitation Facility | PROVIDES | Mental Health Referral | Referral support in facility
23. Emergency Shelter | PROVIDES | Emergency Protection | Core emergency function
24. Homeless Welfare Facility | PROVIDES | Meal Support | Basic support function
25. Self-Reliance Support Center | PROVIDES | Housing Transition Support | Transition-oriented service
26. Program Enrollment | PART_OF_FLOW | Self-Reliance Transition Event Flow | Lifecycle step mapping
27. Crisis Contact | PART_OF_FLOW | Outreach-to-Protection Flow | Entry-point step mapping
28. Emergency Admission | PART_OF_FLOW | Outreach-to-Protection Flow | Immediate protection step
29. Service Completion | PART_OF_FLOW | Stabilization-to-Transition Flow | Mid-lifecycle step
30. Housing Transition Event | PART_OF_FLOW | Stabilization-to-Transition Flow | Transition step
31. Follow-up Review | PART_OF_FLOW | Post-Transition Monitoring Flow | Recurrence monitoring step
32. Employment Linkage | MEASURED_BY | Employment Linkage Rate | Aggregate indicator basis
33. Housing Transition Support | MEASURED_BY | Housing Transition Rate | Aggregate indicator basis
34. Street Outreach Counseling | MEASURED_BY | Outreach Contacts Count | Public reporting metric
35. Emergency Protection | MEASURED_BY | Shelter Admissions Count | Public reporting metric
36. Self-Reliance Transition Program | MEASURED_BY | Self-Reliance Transition Rate | Program performance metric
37. Housing Transition Rate | REFERS_TO | National Statistics Dataset | Public dataset reference
38. Employment Linkage Rate | REFERS_TO | Local Government Open Statistics | Local dataset reference
39. Outreach Contacts Count | REFERS_TO | Public Program Indicators | Administrative indicator reference
40. Shelter Admissions Count | REFERS_TO | Public Data Portal Dataset | Public data source reference

## Usage Notes

- Keep triples conceptual and public-evidence oriented.
- Do not include internal documents, personal data, donor data, accounting data, or case-management records.
- Replace labels with namespace IRIs during package finalization.
