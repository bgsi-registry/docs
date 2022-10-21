# Filter by EHR ID

We'll find the EHR & Composition data of a specific EHR ID. The given EHR ID is `9762e3ab-84b1-4a06-86ca-04648947f689`

The Body Parameter:

```json
{
    "q": "SELECT e/ehr_id/value as ehr_id, c/name/value as composition_name FROM EHR e CONTAINS COMPOSITION c WHERE e/ehr_id/value = '9762e3ab-84b1-4a06-86ca-04648947f689'"
}
```

The Response example:

```json
{
    "q": "SELECT e/ehr_id/value as ehr_id, c/name/value as composition_name FROM EHR e CONTAINS COMPOSITION c WHERE e/ehr_id/value = '9762e3ab-84b1-4a06-86ca-04648947f689'",
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
            "9762e3ab-84b1-4a06-86ca-04648947f689",
            "Blood Pressure"
        ]
    ]
}
```
