# ansible-role-ad_member

Join a Linux host to an Active Directory domain.

Starting with Samba 4.8.0, winbind must be installed to resolve users and security groups from AD. Typically winbind and sssd are mutually exclusive, but sssd is preferred for , mapping ids. This role uses the winbind NSS backend to allow sssd and winbind to coexist.

## Variables
```
# Required
ad_domain           # e.g. "my.domain"
ad_workgroup        # e.g. "MYDOMAIN"
ad_kerberos_user    # user capable of joining host to domain
ad_kerberos_pass

# Optional
ad_test_user        # user name to test join was successful
ad_test_user_uid    # user id to test

# Defaults
ad_kerberos_method: "secrets and keytab"
ad_winbind_domain_backend: nss
ad_winbind_domain_range: "200000-2147483647"
ad_winbind_default_backend: tdb
ad_winbind_default_range: "10000-199999"
```
