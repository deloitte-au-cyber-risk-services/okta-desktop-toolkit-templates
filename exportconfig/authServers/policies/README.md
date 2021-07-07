# Authorization
## Authorization Policies

| Policy | `policy_id` | Config File |
| :---        |:---    |:---         |
{{#each data}}
| _{{this.name}}_       | `{{this.id}}`         | [`{{this._name}}.json`]({{this._name}}.json) |
{{/each}}


## API
### Get Authorization Server

```
curl --request GET 'https://{{api.domain}}/api/v1/authorizationServers/default/policies' \
     --header 'Accept: application/json' \
     --header 'Content-Type: application/json' \
	 --header 'Authorization: SSWS << api_token >>' \
```
