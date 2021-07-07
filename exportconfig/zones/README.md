# Zones
## Network Zones

| Zone | `zone_id` | Config File |
| :---        |:---    |:---         |
{{#each data}}
| _{{this.name}}_       | `{{this.id}}`         | [`{{this._name}}.json`]({{this._name}}.json) |
{{/each}}

## API
### Get Zones

```
curl --request GET 'https://{{apiDomain}}/api/v1/zones \
     --header 'Accept: application/json' \
     --header 'Content-Type: application/json' \
	 --header 'Authorization: SSWS << api_token >>' \
```
