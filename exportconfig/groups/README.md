# Groups

* [Group Rules](./rules)

## Groups

| Group | `group_id` | Config File |
| :---      |:---  |:--- |
{{#each data}}
| _{{this.profile.name}}_       | `{{this.id}}`         | [`{{this._name}}.json`]({{this._name}}.json) |
{{/each}}

## API
### Get Group

```
curl --request GET 'https://{{apiDomain}}/api/v1/groups/<< group_id >>' \
     --header 'Accept: application/json' \
     --header 'Content-Type: application/json' \
	 --header 'Authorization: SSWS << api_token >>' \
```
