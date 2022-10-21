---
description: WIP
---

# Get all composition records (blood\_pressure)

After we all have the sample compositions in the template, now we can perform a query to get the data using AQL. The below query is an example of getting `blood pressure` data according to the properties of \`blood pressure\` template.

```aql
SELECT 
    e/ehr_id/value AS ehr_id, 
    c/content[openEHR-EHR-OBSERVATION.blood_pressure.v2]/data[at0001]/events[at0006]/data[at0003]/items[at0004]/value/magnitude AS systolic, 
    c/content[openEHR-EHR-OBSERVATION.blood_pressure.v2]/data[at0001]/events[at0006]/data[at0003]/items[at0005]/value/magnitude AS diastolic, 
    c/content[openEHR-EHR-OBSERVATION.blood_pressure.v2]/data[at0001]/events[at0006]/state[at0007]/items[at0008]/value/value AS position, 
    c/content[openEHR-EHR-OBSERVATION.blood_pressure.v2]/data[at0001]/events[at0006]/state[at0007]/items[at1043]/value/value AS sleep_status, 
    c/content[openEHR-EHR-OBSERVATION.blood_pressure.v2]/protocol[at0011]/items[at0013]/value/value AS cuff_size, 
    c/content[openEHR-EHR-OBSERVATION.blood_pressure.v2]/data[at0001]/events[at0006]/time/value AS time 
FROM EHR e 
    CONTAINS COMPOSITION c [openEHR-EHR-COMPOSITION.encounter.v1] 
        CONTAINS OBSERVATION o [openEHR-EHR-OBSERVATION.blood_pressure.v2]
```

The query has some of blood pressure aqlpath like 'c/content\[openEHR-EHR-OBSERVATION.blood\_pressure.v2]/data\[at0001]/events\[at0006]/data\[at0003]/items\[at0004]/value/magnitude' to get systolic magnitude value. Those all aqlpath can be acquired from the template content and you may want to get it from template detail endpoint. The \`CONTAINS COMPOSITION c \[openEHR-EHR-COMPOSITION.encounter.v1]\` indicates to filter only select composition with the given archetype node id and 'CONTAINS OBSERVATION o \[openEHR-EHR-OBSERVATION.blood\_pressure.v2]' indicates to filter only select observation from the given template archetype id.

The response body example:

```json
{
    "q": "SELECT e/ehr_id/value AS ehr_id, c/content[openEHR-EHR-OBSERVATION.blood_pressure.v2]/data[at0001]/events[at0006]/data[at0003]/items[at0004]/value/magnitude AS systolic, c/content[openEHR-EHR-OBSERVATION.blood_pressure.v2]/data[at0001]/events[at0006]/data[at0003]/items[at0005]/value/magnitude AS diastolic, c/content[openEHR-EHR-OBSERVATION.blood_pressure.v2]/data[at0001]/events[at0006]/state[at0007]/items[at0008]/value/value AS position, c/content[openEHR-EHR-OBSERVATION.blood_pressure.v2]/data[at0001]/events[at0006]/state[at0007]/items[at1043]/value/value AS sleep_status, c/content[openEHR-EHR-OBSERVATION.blood_pressure.v2]/protocol[at0011]/items[at0013]/value/value AS cuff_size, c/content[openEHR-EHR-OBSERVATION.blood_pressure.v2]/data[at0001]/events[at0006]/time/value AS time FROM EHR e CONTAINS COMPOSITION c [openEHR-EHR-COMPOSITION.encounter.v1] CONTAINS OBSERVATION o [openEHR-EHR-OBSERVATION.blood_pressure.v2]",
    "columns": [
        {
            "path": "/ehr_id/value",
            "name": "ehr_id"
        },
        {
            "path": "/content[openEHR-EHR-OBSERVATION.blood_pressure.v2]/data[at0001]/events[at0006]/data[at0003]/items[at0004]/value/magnitude",
            "name": "systolic"
        },
        {
            "path": "/content[openEHR-EHR-OBSERVATION.blood_pressure.v2]/data[at0001]/events[at0006]/data[at0003]/items[at0005]/value/magnitude",
            "name": "diastolic"
        },
        {
            "path": "/content[openEHR-EHR-OBSERVATION.blood_pressure.v2]/data[at0001]/events[at0006]/state[at0007]/items[at0008]/value/value",
            "name": "position"
        },
        {
            "path": "/content[openEHR-EHR-OBSERVATION.blood_pressure.v2]/data[at0001]/events[at0006]/state[at0007]/items[at1043]/value/value",
            "name": "sleep_status"
        },
        {
            "path": "/content[openEHR-EHR-OBSERVATION.blood_pressure.v2]/protocol[at0011]/items[at0013]/value/value",
            "name": "cuff_size"
        },
        {
            "path": "/content[openEHR-EHR-OBSERVATION.blood_pressure.v2]/data[at0001]/events[at0006]/time/value",
            "name": "time"
        }
    ],
    "rows": [
        [
            "bbd04f68-9214-4c2c-8586-ebbe8e97251a",
            1.0,
            1.0,
            "Standing",
            "Awake",
            "Adult Thigh",
            "2022-04-17T21:31:20.813Z"
        ],
        [
            "9762e3ab-84b1-4a06-86ca-04648947f689",
            120.0,
            124.0,
            "Sitting",
            "Awake",
            "Adult",
            "2022-04-20T13:36:50.592Z"
        ],
        [
            "f46c9163-70b7-4570-b3a3-5312bc68bed4",
            43.0,
            444.0,
            "Sitting",
            "Sleeping",
            "Infant",
            "2022-04-27T17:54:13.932Z"
        ],
        [
            "5a2c333e-dfe6-4764-99da-27ea941908f1",
            6.0,
            5.0,
            "Sitting",
            "Awake",
            "Infant",
            "2022-04-18T06:27:26.559Z"
        ],
        [
            "4b1c368a-b24f-4c02-bcdb-37bc41a02296",
            1.0,
            1.0,
            "Standing",
            "Awake",
            "Adult Thigh",
            "2022-04-17T21:31:20.813Z"
        ],
        [
            "b23652de-82e0-4edd-9d37-fcd54edaf6ce",
            100.0,
            120.0,
            "Standing",
            "Awake",
            "Adult Thigh",
            "2022-04-17T06:07:26.286Z"
        ],
        [
            "102d87b5-85c7-42ef-b4f4-0bb65e764b85",
            22.0,
            34.0,
            "Standing",
            "Awake",
            "Small Adult",
            "2022-05-18T02:39:47.883Z"
        ],
        [
            "6a8204d3-1638-4763-bb0e-6edb698f0187",
            111.0,
            111.0,
            "Standing",
            "Awake",
            "Paediatric/Child",
            "2022-04-27T15:07:00.561Z"
        ],
        [
            "8b50006b-f232-4a7a-b364-a74822c71084",
            397.1,
            813.6,
            "Standing",
            "Awake",
            "Adult Thigh",
            "2022-04-16T01:31:45.364Z"
        ],
        [
            "6b25d9e5-d863-4c0e-80b7-b779f5d7842f",
            22.0,
            22.0,
            "Standing",
            "Awake",
            "Paediatric/Child",
            "2022-05-18T02:41:15.454Z"
        ],
        [
            "8b50006b-f232-4a7a-b364-a74822c71084",
            22.0,
            22.0,
            "Standing",
            "Awake",
            "Paediatric/Child",
            "2022-05-18T02:41:15.454Z"
        ]
    ]
}
```

