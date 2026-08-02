# Security Considerations

## Group-Based Access Control

Application access was assigned through an Okta group rather than directly to individual users.

Group-based assignment provides a scalable method of managing application access and supports consistent access governance.

## Least Privilege

Only the Help Desk group was granted access to the SAML application.

Users outside the authorized group did not receive the application entitlement.

## Signed SAML Assertions

The integration was configured to use signed SAML assertions.

Digital signatures allow the Service Provider to validate that assertions originated from the trusted Identity Provider and were not modified in transit.

## SHA-256

RSA-SHA256 and SHA256 were used for SAML signing and digest operations.

## Attribute Minimization

Only attributes required for the lab were transmitted to the Service Provider:

- firstName
- lastName
- email

Limiting unnecessary attributes reduces the amount of identity information shared with applications.

## Logging and Monitoring

Authentication activity was validated using the Okta System Log.

Logging provides visibility into application access, authentication activity, and policy evaluation results.

## Portfolio Data Protection

Tenant-specific identifiers, IP addresses, administrative information, and other unnecessary environment details were redacted from public screenshots.
