---
title: Migrating from Members
---

The Auth extension was previously called Members. If you used members you will
need to migrate database tables, config files, twig functions and any php use
of events/namespaces to the new name.

## Database

To rename the database tables run the following:

### MySQL

```
ALTER TABLE `bolt_members_account` RENAME TO  `bolt_auth_account` ;
ALTER TABLE `bolt_members_account_meta` RENAME TO  `bolt_auth_account_meta` ;
ALTER TABLE `bolt_members_oauth` RENAME TO  `bolt_auth_oauth` ;
ALTER TABLE `bolt_members_provider` RENAME TO  `bolt_auth_provider` ;
ALTER TABLE `bolt_members_token` RENAME TO  `bolt_auth_token` ;
```

### PostgreSQL

```
ALTER TABLE bolt_members_account RENAME TO bolt_auth_account;
ALTER TABLE bolt_members_account_meta RENAME TO bolt_auth_account_meta;
ALTER TABLE bolt_members_oauth RENAME TO bolt_auth_oauth;
ALTER TABLE bolt_members_provider RENAME TO bolt_auth_provider;
ALTER TABLE bolt_members_token RENAME TO bolt_auth_token;

ALTER SEQUENCE bolt_members_account_id_seq RENAME TO bolt_auth_account_id_seq;
ALTER SEQUENCE bolt_members_account_meta_id_seq RENAME TO bolt_auth_account_meta_id_seq;
ALTER SEQUENCE bolt_members_oauth_id_seq RENAME TO bolt_auth_oauth_id_seq;
ALTER SEQUENCE bolt_members_provider_id_seq RENAME TO bolt_auth_provider_id_seq;
ALTER SEQUENCE bolt_members_token_id_seq RENAME TO bolt_auth_token_id_seq;
```

### SQLite

Not tried yet, but should be the same as MySQL. Let me know if you tried it!

## Config file

The Members config file was called members.bolt.yml. Rename that file to 
auth.boltauth.yml.

## Twig functions

Any twig functions that were called anything with member should be renamed to
the equivalent with auth. For example `is_member()` is now `is_auth`()`.

## PHP usage

Any other extensions that used the old name will need to be updated. As an
example you can look at [this commit in AuthFields](https://github.com/BoltAuth/AuthFields/commit/0e3e699455702a47de6430739dfa5a4e87a99460)
or [this commit in the Bolt market](https://github.com/bolt/site-market-bolt-cm/commit/1189cfcd60fe2189d90204fdd47d7d296ca927a7)
