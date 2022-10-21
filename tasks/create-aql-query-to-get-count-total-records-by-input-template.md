# Create AQL Query to get count total records by input template

To get all total records, we could use the previous task query and modify it.

```aql
SELECT 
    COUNT(e/ehr_id/value) AS records_count 
FROM EHR e 
    CONTAINS COMPOSITION c [openEHR-EHR-COMPOSITION.encounter.v1] 
    CONTAINS OBSERVATION o [openEHR-EHR-OBSERVATION.blood_pressure.v2]
```

The get the count of the records we only need one column to represent the count aggregation value. We just wrap the `e/ehr_id/value` with `COUNT()` function and the result will be just one row containing the value.

The request body:

```json
{
    "q": "SELECT COUNT(e/ehr_id/value) AS records_count FROM EHR e CONTAINS COMPOSITION c [openEHR-EHR-COMPOSITION.encounter.v1] CONTAINS OBSERVATION o [openEHR-EHR-OBSERVATION.blood_pressure.v2]"
}
```

The response body example:

```json
{
    "q": "SELECT COUNT(e/ehr_id/value) AS records_count FROM EHR e CONTAINS COMPOSITION c [openEHR-EHR-COMPOSITION.encounter.v1] CONTAINS OBSERVATION o [openEHR-EHR-OBSERVATION.blood_pressure.v2]",
    "columns": [
        {
            "path": "/COUNT(e/ehr_id/value)",
            "name": "records_count"
        }
    ],
    "rows": [
        [
            10
        ]
    ]
}
```

