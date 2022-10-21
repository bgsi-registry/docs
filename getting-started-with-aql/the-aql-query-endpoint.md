# The AQL Query Endpoint

The `EHRbase` has an endpoint to interact with the data using `Archetype Query Language (AQL)`. Here is the specification of the endpoint:&#x20;

{% swagger method="post" path="/rest/openehr/v1/query/aql" baseUrl="https://ehr.portalkoding.com/ehrbase" summary="Execute ad-hoc (Non-stored) AQL Query" %}
{% swagger-description %}


[https://specifications.openehr.org/releases/ITS-REST/latest/query.html#query-execute-query-post](https://specifications.openehr.org/releases/ITS-REST/latest/query.html#query-execute-query-post)


{% endswagger-description %}

{% swagger-parameter in="body" name="q" required="true" %}
The AQL query
{% endswagger-parameter %}
{% endswagger %}

Although there is an `HTTP` `GET` version of the endpoint, the `POST` one is preferred for the readability purpose. The body request has `q` parameter to insert a query. Here is an example of inserting a query into `q` parameter:

```json
{
    "q": "SELECT e FROM EHR e"
}
```

We'll get an in-depth explanation of the above query in the next section.
