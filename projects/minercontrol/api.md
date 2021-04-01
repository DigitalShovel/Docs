---
description: MinerControl API
---

# API

## Description

MinerControl API is designed in OpenAPI 3.0 format, which is both machine and human-readable. This provides a simple way for users to control Smart PDU.

## Link

All Smart PDU comes with APIs. Check API url in`Setting` -&gt; `About` -&gt; `Documentation`

{% api-method method="get" host="http://demo.shovel.digital" path="/api/miners/" %}
{% api-method-summary %}
Get Miner Info
{% endapi-method-summary %}

{% api-method-description %}
Return all miners
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

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

