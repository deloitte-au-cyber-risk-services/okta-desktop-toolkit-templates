# Applications
This readme provides details on how to use the Okta APIs to make changes to the application instances.

| Application      | Client Id     | Logo                                                              | Type                  |Config File                                   |
|:---              |:---           |:---                                                               |:---                   |:---                                          |
{{#each data}}
| _{{this.label}}_ | `{{this.id}}` | ![`{{this._links.logo.[0].type}}`]({{this._links.logo.[0].href}}) | `{{this.signOnMode}}` | [`{{this._name}}.json`]({{this._name}}.json) |
{{/each}}

## Application Details
{{#each data}}
### _{{this.label}}_  
Application Id: `{{this.id}}`  
Application Type: `{{this.signOnMode}}`  
Status: `{{this.status}}`  
Created: `{{this.created}}`  
Updated: `{{this.lastUpdated}}`  
{{#if this.settings.oauthClient}}  
Initiate Login URI: `{{this.settings.oauthClient.initiate_login_uri}}`  
{{/if}}

{{#if this.groupAssignments}}  
### Group Assignments
{{#each this.groupAssignments}}
- `{{this.profile.name}}`  
{{/each}}
{{/if}}

{{#if this.settings.oauthClient}}  
#### Response Types
{{#each this.settings.oauthClient.response_types}}
- `{{this}}`
{{/each}}

#### Grant Types
{{#each this.settings.oauthClient.grant_types}}
- `{{this}}`
{{/each}}

#### Redirect URIs
{{#each this.settings.oauthClient.redirect_uris}}
- `{{this}}`
{{/each}}

#### Post Logout Redirect URIs
{{#each this.settings.oauthClient.post_logout_redirect_uris}}
- `{{this}}`
{{/each}}

{{/if}}
{{/each}}

# APIs
## Get Application
Used to retreive details of the application in Okta

```
curl --request GET 'https://{{apiDomain}}/api/v1/apps/${application_id}' \
     --header 'Accept: application/json' \
     --header 'Content-Type: application/json' \
	 --header 'Authorization: SSWS ${api_token}' \
```

## Create Application
Create API should be used on initial creation of application in Okta.

```
curl --request POST 'https://{{apiDomain}}/api/v1/apps' \
     --header 'Accept: application/json' \
     --header 'Content-Type: application/json' \
	 --header 'Authorization: SSWS ${api_token}' \
	 --data '${json}'
```

## Update Application
Update API can be used in subsequent updates to application in Okta.

```
curl --request PUT 'https://{{apiDomain}}/api/v1/apps/${application_id}' \
     --header 'Accept: application/json' \
     --header 'Content-Type: application/json' \
	 --header 'Authorization: SSWS ${api_token}' \
 	 --data '${json}'
```

## Assign Group to an Application
The below API call can be used to assign a group to an application. First groupId needs to be fetched from [`/groups`](../groups)
```
curl --request PUT 'https://{{apiDomain}}/api/v1/apps/${application_id}/groups/${group_id}' \
     --header 'Accept: application/json' \
     --header 'Content-Type: application/json' \
     --header 'Authorization: SSWS ${api_token}' \
     --data ''
```
_Please use Okta Administration UI console to assign group to a directory. The above API call is for assigning Group to an application not for directories._
