# Troubleshooting

## Attribute Statements Not Available During Initial SAML Configuration

### Issue

During creation of the custom SAML application, the expected Attribute Statements section was not available on the initial Configure SAML page.

### Investigation

The Advanced Settings section was reviewed, but it contained signing, encryption, authentication context, and other SAML configuration options rather than profile attribute statements.

### Resolution

The SAML application was completed using the required Service Provider settings.

After creation, the application's Sign On configuration page exposed the Profile Attribute Statements section.

The required mappings were then configured:

- firstName → user.firstName
- lastName → user.lastName
- email → user.email

### Lesson Learned

Okta administrative interfaces can differ between releases and environments. When expected configuration options are not available during initial application creation, reviewing the completed application's Sign On settings may expose additional configuration options.
