# Quick Start

{% hint style="info" %}
**Good to know:** A quick start guide can be good to help folks get up and running with your API in a few steps. Some people prefer diving in with the basics rather than meticulously reading every page of documentation!
{% endhint %}

## Get your API keys

Your API requests are authenticated using API keys. Any request that doesn't include an API key will return an error.

You will receive an API Id & API key from your Dashboard at any time.

## Install the library

The best way to interact with our API is to use one of our official libraries:

{% tabs %}
{% tab title="Node" %}
```
# Install via NPM
npm install --save cross-switch
```
{% endtab %}

{% tab title="C#" %}
install from Nuget&#x20;

```
Install-Package cross-switch
```
{% endtab %}

{% tab title="Python" %}
```
# Install via pip
pip install --upgrade cross-switch
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
**Good to know:** Using tabs to separate out different languages is a great way to present technical examples or code documentation without cramming your docs with extra sections or pages per language.
{% endhint %}

## Make your first request

To make your first request, send an authenticated request to the pets endpoint. This will create a `pet`, which is nice.

{% swagger baseUrl="https://api.myapi.com/v1" method="post" path="/pet" summary="Create pet." %}
{% swagger-description %}
Creates a new pet.
{% endswagger-description %}

{% swagger-parameter in="body" name="name" required="true" type="string" %}
The name of the pet
{% endswagger-parameter %}

{% swagger-parameter in="body" name="owner_id" required="false" type="string" %}
The 

`id`

 of the user who owns the pet
{% endswagger-parameter %}

{% swagger-parameter in="body" name="species" required="false" type="string" %}
The species of the pet
{% endswagger-parameter %}

{% swagger-parameter in="body" name="breed" required="false" type="string" %}
The breed of the pet
{% endswagger-parameter %}

{% swagger-response status="200" description="Pet successfully created" %}
```javascript
{
    "name"="Wilson",
    "owner": {
        "id": "sha7891bikojbkreuy",
        "name": "Samuel Passet",
    "species": "Dog",}
    "breed": "Golden Retriever",
}
```
{% endswagger-response %}

{% swagger-response status="401" description="Permission denied" %}

{% endswagger-response %}
{% endswagger %}

{% hint style="info" %}
**Good to know:** You can use the API Method block to fully document an API method. You can also sync your API blocks with an OpenAPI file or URL to auto-populate them.
{% endhint %}

Take a look at how you might call this method using our official libraries, or via `curl`:

{% tabs %}
{% tab title="curl" %}
```
curl https://api.myapi.com/v1/pet  
    -u YOUR_API_KEY:  
    -d name='Wilson'  
    -d species='dog'  
    -d owner_id='sha7891bikojbkreuy'  
```
{% endtab %}

{% tab title="Node" %}
```javascript
// require the myapi module and set it up with your API key
const cross_switch = require('cross-switch')(YOUR_API_ID,YOUR_API_KEY);

const newPayment = away cross_switch.payment.create({
    name: 'Wilson Test',
    email: 'Wilson@test.com',
    mobile: '+233546000000',
    mobile_network: 'MTN',
    currency: 'GHC',
    order_id: 'sha7891bikojbkreuy',
    species: 'Dog',
    order_desc: 'Golden Retriever',
})
```
{% endtab %}

{% tab title="Python" %}
```python
// Set your API key before making the request
cross_switch.api_id = YOUR_API_ID
cross_switch.api_key = YOUR_API_KEY

cross_switch.Pet.create(
    name='Wilson Alabi',
    email: 'Wilson@test.com',
    mobile: '+233546000000',
    mobile_network: 'MTN',
    amount: 1,
    currency: 'GHC',
    order_id: 'sha7891bikojbkreuy',
    species: 'Dog',
    order_desc: 'Golden Retriever',
)
```
{% endtab %}
{% endtabs %}
