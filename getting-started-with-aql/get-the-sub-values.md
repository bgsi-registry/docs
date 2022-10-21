# Get the sub values

Rather than getting the EHR object as the result, we could specify which values to get and we could trim the big JSON result. We will improve the previous query to only get the EHR id value instead of retrieving the entire document.

The query will select the EHR id with the path `e/ehr_id/value` and named it as `ehr_id`

```aql
SELECT e/ehr_id/value AS ehr_id FROM EHR e
```

The request body:

```json
{
    "q": "SELECT e/ehr_id/value AS ehr_id FROM EHR e"
}
```

The response example:

```json
{
    "q": "SELECT e/ehr_id/value FROM EHR e",
    "columns": [
        {
            "path": "/ehr_id/value",
            "name": "ehr_id"
        }
    ],
    "rows": [
        [
            "3ac40935-7364-4fa8-a48d-98d0a8e581e8"
        ],
        [
            "44b17c8d-6f35-428c-92e9-a5ccd12aca04"
        ],
        [
            "4b1c368a-b24f-4c02-bcdb-37bc41a02296"
        ]
    ]
}
```
