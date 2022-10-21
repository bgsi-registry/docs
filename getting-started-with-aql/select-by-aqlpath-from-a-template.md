# Select by AQLpath from a template

We could select data by a defined aqlpath from a template. The AQLpath example is `/content[openEHR-EHR-OBSERVATION.blood_pressure.v2]/protocol[at0011]/items[at0013]/value`

The aqlpath was acquired from the \`/ehrbase/rest/ecis/v1/template/dto.blood\_pressure.v1\` template detail endpoint.

The Body Parameter:

```json
{
    "q": "SELECT c/content[openEHR-EHR-OBSERVATION.blood_pressure.v2]/data[at0001]/events[at0006]/data[at0003]/items[at0004]/value as systolic FROM EHR e CONTAINS COMPOSITION c"
}
```

The Response example:

```json
{
    "q": "SELECT c/content[openEHR-EHR-OBSERVATION.blood_pressure.v2]/data[at0001]/events[at0006]/data[at0003]/items[at0004]/value as systolic FROM EHR e CONTAINS COMPOSITION c",
    "columns": [
        {
            "path": "/content[openEHR-EHR-OBSERVATION.blood_pressure.v2]/data[at0001]/events[at0006]/data[at0003]/items[at0004]/value",
            "name": "systolic"
        }
    ],
    "rows": [
        [
            {
                "_type": "DV_QUANTITY",
                "units": "mm[Hg]",
                "magnitude": 1.0
            }
        ],
        [
            {
                "_type": "DV_QUANTITY",
                "units": "mm[Hg]",
                "magnitude": 100.0
            }
        ],
        [
            {
                "_type": "DV_QUANTITY",
                "units": "mm[Hg]",
                "magnitude": 120.0
            }
        ],
        [
            {
                "_type": "DV_QUANTITY",
                "units": "mm[Hg]",
                "magnitude": 397.1
            }
        ],
        [
            {
                "_type": "DV_QUANTITY",
                "units": "mm[Hg]",
                "magnitude": 6.0
            }
        ]
    ]
}
```
