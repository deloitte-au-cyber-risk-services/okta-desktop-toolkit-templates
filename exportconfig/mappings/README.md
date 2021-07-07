<< api_token >># Mappings
## Core Mappings

| Mapping | `mapping_id` | Config File |
| :---        |:---    |:---         |
{{#each data}}
| _{{this.source.name}}:{{this.source.type}} -> {{this.target.name}}:{{this.target.type}}_       | `{{this.id}}`         | [`{{this._name}}.json`]({{this._name}}.json) |
{{/each}}

# APIs
## List Application Mappings
Used to retreive list of application mappings.

```
curl --request GET 'https://{{apiDomain}}/api/v1/mappings' \
     --header 'Accept: application/json' \
     --header 'Content-Type: application/json' \
	 --header 'Authorization: SSWS << api_token >>' \
```

## Get Application Mapping
Used to retreive details of the application mapping.

```
curl --request GET 'https://{{apiDomain}}/api/v1/mappings/<< mapping_id >>' \
     --header 'Accept: application/json' \
     --header 'Content-Type: application/json' \
	 --header 'Authorization: SSWS << api_token >>' \
```

## Update Application Mapping
Update API can be used in subsequent updates to application mapping.

```
curl --request PUT 'https://{{apiDomain}}/api/v1/mappings/<< mapping_id >>' \
     --header 'Accept: application/json' \
     --header 'Content-Type: application/json' \
	 --header 'Authorization: SSWS << api_token >>' \
 	 --data '{{ json }}'
```