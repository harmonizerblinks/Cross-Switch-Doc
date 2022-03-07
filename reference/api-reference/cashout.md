---
coverY: 0
---

# Cashout

## Creating a MoMo Payment

{% swagger baseUrl="https://api.myapi.com/v1" method="post" path="/pet" summary="Create MoMo Payment" %}
{% swagger-description %}
Creates a new payment
{% endswagger-description %}

{% swagger-parameter in="body" name="App_Id" required="true" type="string" %}
The Merchant Id Provided for you
{% endswagger-parameter %}

{% swagger-parameter in="body" name="App_Key" required="false" type="string" %}
The Merchant 

`API_Key`

 Provided for you
{% endswagger-parameter %}

{% swagger-parameter in="body" name="name" required="false" type="string" %}
The species of the pet
{% endswagger-parameter %}

{% swagger-parameter in="body" name="breed" required="false" type="string" %}
The breed of the pet
{% endswagger-parameter %}

{% swagger-response status="200" description="successfully created" %}
```javascript
{
    status_code: 1,
    status_message: "Transaction Successful",
    trans_ref_no: "46574HJ"
}
```
{% endswagger-response %}

{% swagger-response status="401" description="Permission denied" %}

{% endswagger-response %}
{% endswagger %}

{% hint style="info" %}
**Good to know:** This API method was created using the API Method block, it's how you can build out an API method documentation from scratch. Have a play with the block and you'll see you can do some nifty things like add and reorder parameters, document responses, and give your methods detailed descriptions.
{% endhint %}

## Callback

{% swagger src="https://petstore.swagger.io/v2/swagger.json" path="/pet" method="put" %}
[https://petstore.swagger.io/v2/swagger.json](https://petstore.swagger.io/v2/swagger.json)
{% endswagger %}

{% hint style="info" %}
**Good to know:** This API method was auto-generated from an example Swagger file. You'll see that it's not editable – that's because the contents are synced to an URL! Any time the linked file changes, the documentation will change too.
{% endhint %}
