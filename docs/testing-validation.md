# Testing and Validation

## Overview

The SAML integration was tested using both authorized and unauthorized test identities to validate authentication, attribute exchange, and group-based application access.

## Positive Access Test

A test user assigned to the Help Desk group was used to validate authorized application access.

### Expected Result

The Help Desk user should:

1. Authenticate successfully to Okta.
2. Receive access to the IAMShowcase SAML Test SP through group membership.
3. Launch the application from the Okta End-User Dashboard.
4. Federate successfully to the Service Provider.
5. Send the configured identity attributes in the SAML assertion.

### Result

**PASS**

The Help Desk test user successfully accessed the IAMShowcase SAML Test SP through Okta.

IAMShowcase confirmed successful federation and received the configured SAML attributes:

- firstName
- lastName
- email

## Okta System Log Validation

The authentication event was reviewed through the Okta System Log.

The log recorded:

- User single sign on to app: SUCCESS
- Evaluation of sign-on policy: ALLOW

This confirmed successful application access from the Identity Provider side.

## Negative Access Test

A separate test user outside the authorized Help Desk group was used to validate group-based access controls.

### Expected Result

The unauthorized user should be able to authenticate to Okta but should not receive the IAMShowcase application assignment.

### Result

**PASS**

The unauthorized test user successfully authenticated to Okta but the IAMShowcase SAML Test SP was not available on the user's End-User Dashboard.

This validated that application access was controlled through group-based assignment.

## Test Summary

| Test | Expected Result | Result |
|---|---|---|
| Help Desk application assignment | Application available | PASS |
| SAML federation | Successful authentication | PASS |
| SAML attribute transmission | Attributes received by SP | PASS |
| Okta System Log validation | SUCCESS / ALLOW | PASS |
| Unauthorized user | Application unavailable | PASS |
