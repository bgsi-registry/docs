# Select data as multiple column

We could get nested values as a column from EHR and Composition data. We will select `e/ehr_id/value` as `ehr_id` and `c/name/value` as `composition_name`

```aql
SELECT 
    e/ehr_id/value as ehr_id, 
    c/name/value as composition_name 
FROM EHR e 
    CONTAINS COMPOSITION c
```

The Body Parameter:

```json
{
    "q": "SELECT e/ehr_id/value as ehr_id, c/name/value as composition_name FROM EHR e CONTAINS COMPOSITION c"
}
```

The Response example:

```json
{
    "q": "SELECT e/ehr_id/value as ehr_id, c/name/value as composition_name FROM EHR e CONTAINS COMPOSITION c",
    "columns": [
        {
            "path": "/ehr_id/value",
            "name": "ehr_id"
        },
        {
            "path": "/name/value",
            "name": "composition_name"
        }
    ],
    "rows": [
        [
            "4b1c368a-b24f-4c02-bcdb-37bc41a02296",
            "Blood Pressure"
        ],
        [
            "5a2c333e-dfe6-4764-99da-27ea941908f1",
            "Blood Pressure"
        ],
        [
            "8b50006b-f232-4a7a-b364-a74822c71084",
            "Blood Pressure"
        ]
    ]
}
```
