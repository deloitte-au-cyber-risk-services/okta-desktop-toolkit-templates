# Policies

* [Policy Rules](./rules)

## Password Policies
| Type             | Policy | `policy_id` | Config File |
| :---             | :---        |:---    |:---         |
{{#each passwords}}
| _{{this.type}}_       | _{{this.name}}_       | `{{this.id}}`         | [`{{this._name}}.json`]({{this._name}}.json) |
{{/each}}

{{passwordPoliciesTable}}

## Sign On Policies
| Type             | Policy | `policy_id` | Config File |
| :---             | :---        |:---    |:---         |
{{#each signon}}
| _{{this.type}}_       | _{{this.name}}_       | `{{this.id}}`         | [`{{this._name}}.json`]({{this._name}}.json) |
{{/each}}

## MFA Enrollment Policies
| Type             | Policy | `policy_id` | Config File |
| :---             | :---        |:---    |:---         |
{{#each mfaEnroll}}
| _{{this.type}}_       | _{{this.name}}_       | `{{this.id}}`         | [`{{this._name}}.json`]({{this._name}}.json) |
{{/each}}

| | 1 | 2 | 3 | 4 |
| :--- | :--- | :--- | :--- | :--- |
| minLength | 8 | 8 | 8 | 8 |
| minLowerCase | 1 | 1 | 1 | 1 |
| minUpperCase | 1 | 1 | 1 | 1 |
| minNumber | 1 | 1 | 1 | 1 |
| minSymbol | 0 | 0 | 0 | 0 |
| excludeUsername | true | true | true | true |
| dictionary.common.exclude | true | true | true | true |
| excludeAttributes | firstName,lastName | firstName,lastName | firstName,lastName | firstName,lastName |

name: ADVISOR
Priority: 1
Minimum length
Complexity requirements
Lowercase letter</td>
Uppercase letter</td>
Number (0-9)</td>
Symbol (e.g. <code>!@#$%^&amp;*</code> )
Does not contain part of username</td>
Does not contain first name</td>
Does not contain last name</td>
Common password check*</th>
Restrict use of common passwords</td>
Password age</p>
Enforce password history for last&nbsp;passwords</td>
Minimum password age is</td>
Password expires after 
Prompt user&nbsp; &nbsp;days before password expires
Lockout</p>
Lock out user after  &nbsp;unsuccessful attempts
Account is automatically unlocked after  &nbsp;minutes
Show lock out failures</td>
Send lockout email to user</td>
Rule</th>
Exclude Users</th>
Rule</th>
          <code>&nbsp;User's IP is</code>
          <span >ANYWHERE</span>
            <strong>THEN</strong>
             User can
          </code>
          <span >CHANGE PASSWORD</span>

## API
### Get Sign On Policies

```
curl --request GET 'https://{{apiDomain}}/api/v1/policies?type=OKTA_SIGN_ON' \
     --header 'Accept: application/json' \
     --header 'Content-Type: application/json' \
	 --header 'Authorization: SSWS << api_token >>' \
```

### Get Password Policies

```
curl --request GET 'https://{{apiDomain}}/api/v1/policies?type=PASSWORD' \
     --header 'Accept: application/json' \
     --header 'Content-Type: application/json' \
	 --header 'Authorization: SSWS << api_token >>' \
```

### Get MFA Enroll Policies

```
curl --request GET 'https://{{apiDomain}}/api/v1/policies?type=MFA_ENROLL' \
     --header 'Accept: application/json' \
     --header 'Content-Type: application/json' \
	 --header 'Authorization: SSWS << api_token >>' \
```
