---
title: Configuration defaults
---

### Configuration file

The main configuration for the Auth extension is done in the file
`./app/config/extensions/auth.boltauth.yml`

You can override settings that you don't want to appear in the main
configuration in `./app/config/extensions/auth.boltauth_local.yml`. This
is useful if you want to keep secret keys out of your _git_ repository
or if your production site has differen credentials from your test site.


### Default values

#### Debug

Enable or disable [debugging](debugging.md).

The default value is:
```yml
debug: false
```

#### Registration

Enable or disable registration by visitors.

Registration is disabled by default:
```yml
registration:
   enabled: false
```

#### Notification email addresses

Enable notifications and set a working email address.
This is required for outgoing email to work on some servers.

```yml
notification:
    name: Site Admin              # Display name used as the sender name
    email: no-reply@example.com   # Email address as the sender address
    format: mixed                 # html, plain or mixed
```

#### Redirects

With the redirects you can set up pages or paths where the user is sent
to after completing one of the actions.

The path or page has to be available and published for this to work.

The default values are:

```yml
redirects:
    login: null                   # Redirect after succesfull login
    logout: null                  # Redirect after logout
    register: null                # Redirect after registration
    reset: null                   # Redirect after password reset
    verify: null                  # Redirect after verification
    delete: null                  # Redirect after account deletion
```

#### Urls

If you want to have different paths for logging in you can override the
authenticate url.

The default values are:

```yml
urls:
    authenticate: authentication
    auth: auth
```

This means the path http://example.com/authenticate/login is used for login.
And the path http://example.com/auth/profile/edit is used for the profile page.

#### Access Control


See [Access control](access-control.md) for more information.

The default values are:

```yml
roles:
    auth:
        admin: Administrator
        moderator: Moderator
        participant: Participant
```

#### Authentication & OAuth2 Providers

Configuration for the different ways people can authenticate.

See [Authentication providers](authentication-providers.md) for details about how to configure OAuth2 providers.

#### Form Configuration

Default values for the forms are set to the following templates and labels.

See [Form display](form-display.md) for more information.

