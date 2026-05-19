# Seed Triples Examples (Turtle-style pseudocode)

```ttl
:SelfRelianceProgram a :Program .
:MOHW a :Agency .
:SelfRelianceProgram :operatedBy :MOHW .

:EmergencyShelterService a :Service .
:ShelterFacility a :FacilityType .
:ShelterFacility :delivers :EmergencyShelterService .

:HousingTransitionRate a :OutcomeIndicator .
:HousingTransition :measuredBy :HousingTransitionRate .
```

## Implementation Note
Replace pseudocode IRIs with your namespace policy during OpenCrab pack finalization.
