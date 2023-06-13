The Hybrid Flow combines steps from the Implicit Flow with Form Post and Authorization Code Flow:

    1. User selects Login within application.

    2. Application redirects user to Auth0 Authorization Server (/authorize endpoint)
     passing along response_type parameter indicating type of requested credential
     (ID token and authorization code), and response_mode parameter of form_post to ensure security.

    3. Auth0 Authorization Server redirects user to login and authorization prompt.

    4. User authenticates using one of the configured login options, and may see a consent prompt
     listing the permissions Auth0 will give to the application.

    5. Auth0 Authorization Server redirects user back to application with single-use authorization code,
     and ID token, access token, or both, depending on provided response_type.

    6. Application sends authorization code, application's client ID, and application's credentials,
     such as Client Secret or Private Key JWT, to Auth0 Authorization Server (/oauth/token endpoint).

    7. Auth0 Authorization Server verifies authorization code, application's client ID, and application's credentials.

    8. Auth0 Authorization Server responds with second ID token and access token (and optionally, a refresh token).

    9. Application can use second access token to call an API to access information about user.

    10. API responds with requested data.
