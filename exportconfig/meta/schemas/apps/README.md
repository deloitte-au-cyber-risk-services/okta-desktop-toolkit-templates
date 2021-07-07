# Application Schemas
This readme provides details on how to use the Okta APIs to make changes to the application schemas.

| Application | `schema_id` | Config File |
| :---        |:---    |:---         |

# APIs
## Get Application Schema
Used to retreive details of the application schema.

```
curl --request GET 'https://{{apiDomain}}/api/v1/meta/schemas/apps/<< schema_id >>' \
     --header 'Accept: application/json' \
     --header 'Content-Type: application/json' \
	 --header 'Authorization: SSWS << api_token >>' \
```

## Update Application Schema
Update API can be used in subsequent updates to application schema.

```
curl --request PUT 'https://{{apiDomain}}/api/v1/meta/schemas/apps/<< schema_id >>' \
     --header 'Accept: application/json' \
     --header 'Content-Type: application/json' \
	 --header 'Authorization: SSWS << api_token >>' \
 	 --data '<< json >>'
```
