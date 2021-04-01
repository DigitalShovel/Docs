---
description: MinerControl API
---

# API

## Description

MinerControl API is designed in OpenAPI 3.0 format, which is both machine and human-readable. This provides a simple way for users to control Smart PDU.

All Smart PDU comes with APIs. Check more details of API, please go to local device MinerControl Dashboard `Setting` -&gt; `About` -&gt; `Ducumentation`

Or check out on Demo page here:

* API Documentation: [http://demo.shovel.digital/api/docs](http://demo.shovel.digital/api/docs/)
* Interactive API: [http://demo.shovel.digital/api/](http://demo.shovel.digital/api/)

Since we following OpenAPI 3.0 format, there are other format docs available:

* Redoc: [http://demo.shovel.digital/api/docs/redoc](http://demo.shovel.digital/api/docs/redoc)
* Coreapi: [http://demo.shovel.digital/api/docs/drf](http://demo.shovel.digital/api/docs/drf)

{% api-method method="get" host="http://demo.shovel.digital" path="/api/miners/" %}
{% api-method-summary %}
Get Miner Info
{% endapi-method-summary %}

{% api-method-description %}
Return all miners
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="cons\_min" type="number" required=false %}
Min Current Consumption
{% endapi-method-parameter %}

{% api-method-parameter name="cons\_max" type="number" required=false %}
Max Current Consumption
{% endapi-method-parameter %}

{% api-method-parameter name="otherType" type="boolean" required=false %}
If true, only return records with type!='miner'
{% endapi-method-parameter %}

{% api-method-parameter name="search" type="string" required=false %}
Search in Label & Notes
{% endapi-method-parameter %}

{% api-method-parameter name="ordering" type="string" required=false %}
Ordering by which field, eg. id, curCons, updateTime
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
[
  {
    "id": 1,
    "label": "Default Label1",
    "notes": "Notes for Miner1",
    "status": false,
    "curCons": 1,
    "warning": false,
    "autoReset": true,
    "minThreshold": 2000,
    "maxThreshold": 12002,
    "maxReset": 5,
    "attempts": 0,
    "resetDelay": 5,
    "minResetDelay": 5,
    "maxResetDelay": 10,
    "total": 7996,
    "lastOnTime": "2021-03-31T15:05:00+01:00",
    "active": true,
    "addTime": "2021-03-23T22:16:15.726346Z",
    "updateTime": "2021-04-01T17:49:25.506803+01:00",
    "type": 2
  },
  {
    "id": 2,
    "label": "Default Label",
    "notes": "Note",
    "status": false,
    "curCons": 0,
    "warning": false,
    "autoReset": false,
    "minThreshold": 0,
    "maxThreshold": 0,
    "maxReset": 5,
    "attempts": 0,
    "resetDelay": 5,
    "minResetDelay": 0,
    "maxResetDelay": 0,
    "total": 78184,
    "lastOnTime": "2021-03-31T20:04:17.194000+01:00",
    "active": true,
    "addTime": "2021-03-23T22:16:15.731676Z",
    "updateTime": "2021-04-01T17:48:56.723997+01:00",
    "type": 2
  },
  .
  .
  ...
  {
    "id": 48,
    "label": "Default Label",
    "notes": "Note",
    "status": false,
    "curCons": 0,
    "warning": false,
    "autoReset": false,
    "minThreshold": 0,
    "maxThreshold": 0,
    "maxReset": 5,
    "attempts": 0,
    "resetDelay": 5,
    "minResetDelay": 0,
    "maxResetDelay": 0,
    "total": 78184,
    "lastOnTime": "2021-03-31T20:04:17.194000+01:00",
    "active": true,
    "addTime": "2021-03-23T22:16:15.731676Z",
    "updateTime": "2021-04-01T17:48:56.723997+01:00",
    "type": 2
  },
]
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="put" host="http://demo.shovel.digital" path="/api/miners/:id" %}
{% api-method-summary %}
Update Miner
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="number" required=true %}
Port ID
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
JWT ey6DigitalShovelVsiJ9.tvgyuwifvk.fgbsdemojsrb
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="label" type="string" required=false %}
Miner Label
{% endapi-method-parameter %}

{% api-method-parameter name="notes" type="string" required=false %}
Notes / Comments
{% endapi-method-parameter %}

{% api-method-parameter name="minThreshold" type="number" required=false %}
min Threshold value for Auto Reset
{% endapi-method-parameter %}

{% api-method-parameter name="maxThreshold" type="number" required=false %}
max Threshold value for Auto Reset
{% endapi-method-parameter %}

{% api-method-parameter name="autoReset" type="boolean" required=false %}
Auto Reset
{% endapi-method-parameter %}

{% api-method-parameter name="status" type="boolean" required=false %}
Miner on/off status
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Return updated miner info.
{% endapi-method-response-example-description %}

```
{
    "id": 1,
    "label": "Miner",
    "notes": "Default Notes",
    "status": true,
    "curCons": 1712.0,
    "warning": false,
    "autoReset": false,
    "minThreshold": 2000,
    "maxThreshold": 12002,
    "maxReset": 5,
    "attempts": 0,
    "resetDelay": 5,
    "minResetDelay": 5,
    "maxResetDelay": 10,
    "total": 6969,
    "lastOnTime": "2021-04-01T17:27:47.050448+01:00",
    "active": true,
    "addTime": "2021-03-23T22:16:15.726346Z",
    "updateTime": "2021-04-01T19:00:06.175163+01:00",
    "type": 1
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



