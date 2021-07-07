<< api_token >># Groups
## Group Rules

| Group Rule | `group_rule_id` | Config File |
| :---       |:---             |:--- |
{{#each data}}
| _{{this.name}}_       | `{{this.id}}`         | [`{{this._name}}.json`]({{this._name}}.json) |
{{/each}}

## API
### Get Group Rule




# APIs
## List Group Rules
Used to retreive list of group rules.

```
curl --request GET 'https://{{apiDomain}}/api/v1/groups/rules' \
     --header 'Accept: application/json' \
     --header 'Content-Type: application/json' \
	 --header 'Authorization: SSWS << api_token >>'
```

## Get Group Rule
Used to retreive details of a group rule.

```
curl --request GET 'https://{{apiDomain}}/api/v1/groups/rules/<< group_rule_id >>' \
     --header 'Accept: application/json' \
     --header 'Content-Type: application/json' \
	 --header 'Authorization: SSWS << api_token >>'
```

## Update Application Mapping
Update API can be used in subsequent updates to group rules.

```
curl --request PUT 'https://{{apiDomain}}/api/v1/groups/rules/<< group_rule_id >>' \
     --header 'Accept: application/json' \
     --header 'Content-Type: application/json' \
	 --header 'Authorization: SSWS << api_token >>' \
 	 --data '<< json >>'
```