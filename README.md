# Postgresql from zero to hero

- [Postgresql from zero to hero](#postgresql-from-zero-to-hero)
  - [Installation](#installation)
  - [Postgresql cheatsheet](#postgresql-cheatsheet)
    - [Create new DB](#create-new-db)
    - [Create admin role for new DB](#create-admin-role-for-new-db)
    - [Role membership](#role-membership)
    - [Connect](#connect)
    - [Creating a New Table](#creating-a-new-table)
- [References](#references)
    - [DB Management Tools](#db-management-tools)

  - [DB Management Tools](#db-management-tools)

- [x] Installation
- [x] Postgresql Cheatsheet

## Installation

```bash
sudo apt update
sudo apt install postgresql postgresql-contrib
```

**Switching Over to the postgres Account**

```bash
sudo -i -u postgres
psql
\q
```

**Accessing a Postgresq Prompt without switching accounts**

```bash
sudo -u postgres psql
```

## Postgresql cheatsheet

**Specification**

> Design a system to allow user create course for personal improvement

Todo:

- [ ] Create new DB
- [ ] Create admin role for DB
- [ ] Create readonly role for DB
- [ ] Define entity in system
- [ ] Create tables and relations
- [ ] Create procedures
- [ ] DB Management Tools
- [ ] Benchmark tools

### Create new DB

```bash
CREATE DATABASE mycourse
WITH ENCODING='UTF8'
OWNER=postgres
TEMPLATE=template1
CONNECTION LIMIT=-1
TABLESPACE=pg_default;

COMMENT ON DATABASE mycourse
IS 'a system to allow user create course for personal improvement';
```

### Create admin role for new DB

```bash
CREATE ROLE mycourse LOGIN CREATEDB CREATEROLE;
ALTER ROLE mycourse WITH PASSWORD '123456';
```

### Role membership

| Command             | Purpose                  |
| ------------------- | ------------------------ |
| sudo -i -u postgres | Access postgresql prompt |

['Cheat Sheet'](./cheatsheet.md);

### Connect

> psql postgresql://{role}:{password}@{host}:{port}/{db}

```bash
psql postgresql://mycourse:123456@localhost:5432/mycourse
```

### Creating a New Table

- [Datatypes](https://www.postgresql.org/docs/12/datatype.html)

# References

- https://www.postgresql.org/docs/12/index.html
- https://www.digitalocean.com/community/tutorials/how-to-install-and-use-postgresql-on-ubuntu-18-04
- https://www.postgresqltutorial.com/

### DB Management Tools

- [pgadmin4](https://www.pgadmin.org/download/pgadmin-4-python/)
