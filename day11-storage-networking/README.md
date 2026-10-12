# Day 11 — Docker Storage & Networking

## Objective

Deploy PostgreSQL with persistent storage and demonstrate
Docker networking, DNS, port mapping, and volume backup.

## Environment

- OS: Linux
- Docker:
- PostgreSQL: postgres:16-alpine
- Network: app-net
- Volume: pgdata

## 1. Persistent Storage

Created named volume:

pgdata

PostgreSQL was mounted using:

-v pgdata:/var/lib/postgresql/data

### Persistence Test

Inserted:

I survive!

Removed the PostgreSQL container and recreated it
using the same pgdata volume.

The original row was still present.

## 2. Custom Bridge Network

Created:

app-net

PostgreSQL was connected to app-net.

A second PostgreSQL client successfully connected using:

db

instead of an IP address.

## 3. DNS Test

Default bridge:

db was not resolved.

User-defined bridge:

db resolved successfully.

This demonstrates Docker's internal DNS behavior
on user-defined bridge networks.

## 4. Port Mapping

First container:

18080 -> 80

A second container attempted to use:

18080 -> 80

This produced a host-port allocation conflict.

The second container was then configured as:

18081 -> 80

The nginx service responded successfully.

## 5. Volume Backup

PostgreSQL was stopped before creating the file-level archive.

Backup:

pgdata-backup.tgz

The archive was verified using tar and its file size
was recorded.

PostgreSQL was restarted successfully afterward.

## 6. Lessons Learned

- Containers are ephemeral.
- Named volumes provide persistent storage.
- User-defined bridge networks provide container DNS.
- Host ports must be unique for simultaneous bindings.
- A volume is live storage; a backup is a separate recovery copy.
- Raw database files should not be copied while PostgreSQL
  is actively modifying them.

## Evidence

Screenshots are available in the evidence/ directory.
