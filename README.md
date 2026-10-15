# ansible-epel

Configures the EPEL package repository on Red Hat-family systems, using EPEL 10
by default. On CentOS and Rocky Linux versions newer than 8, the role also enables
the CRB repository. It makes no service changes and skips repository setup on
other OS families.

## Variables

- `epel_rpm_key`: string containing the signing-key URL or managed-host file path.
  Defaults to `https://dl.fedoraproject.org/pub/epel/RPM-GPG-KEY-EPEL-10`.
- `epel_url`: string containing the release RPM URL or managed-host file path.
  Defaults to `https://dl.fedoraproject.org/pub/epel/epel-release-latest-10.noarch.rpm`.

Gather facts and run with root privileges. When targeting a different EPEL major
version, set both inputs to a matching release RPM and signing key. The caller
provides the distribution's prerequisite repositories; this role enables CRB only
on the distributions listed above.
