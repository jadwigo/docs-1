---
title: Redirection
---

### Setting Custom Redirects

URLs that the visitor will be redirected to after login, logout, account
registration, email verification and password reset can be set in the
extension configuration file via the `redirects:` key.

If not set, auth will be redirected to the referring page after login,
and the homepage after logout.

#### Configuration

The `redirects:` key has five optional parameters, `login`, `logout`,
`register`, `verify` & `reset`. Each take either a relative or absolute
URL.

```yaml
redirects:
    login: /auth/profile
    logout: /authentication/login
    register: /page/thanks-for-registering  # example path for a page redirect
    verify: /page/verification-complete     # example path for a page redirect
    reset: /page/your-passord-is-reset      # example path for a page redirect
```
