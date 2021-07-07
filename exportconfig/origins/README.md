# Origins
## Trusted Origins

| Origin          | `origin_id`       | Config File                              |
|:---                  |:---                    |:---                                      |
{{#each data}}
| _{{this.name}}_       | `{{this.id}}`         | [`{{this._name}}.json`]({{this._name}}.json) |
{{/each}}

## API
### Get Trusted Origin

```
curl --request GET 'https://{{apiDomain}}/api/v1/trustedOrigins' \
     --header 'Accept: application/json' \
     --header 'Content-Type: application/json' \
	 --header 'Authorization: SSWS << api_token >>' \
```
