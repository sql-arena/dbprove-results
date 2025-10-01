# Results of `dbprove` runs

This repo can be used to publish results of `dbprove` runs for public
consumption.

## Submission Process

Submitting a new result follows this process:

Let:

- `[user]` := your github username.
- `[engine]` := the Canonical name of the database engine you are testing (see below)
- `[version]` := Full version string of `[engine]` under test

Process:

- Download and run `dbprove` against your database.
  - The run will generate a `data/` folder.
- Fill out the `template.md` file and name it `submission.md`
- File a PR against this repo - putting the `submission.md` file
  and the contents of your `data/` folder into the folder:
  `engine/[engine]/[version]/[user]`
  - **Optionally:** If you test more than one configuration, add a
    subfolder under your username for each configuration tested and make sure to fill out a `submission.md` file for each tested configuration.

## Canonical Database Names

The following are the canonical names of database under test

- "PostgreSQL"
- "MySQL" - includes all versioned managed by Oracle
- "MariaDB" - forks of MySQL handled by the MariaDB foundation
- "SQLite"
- "DuckDB"
- "ClickHouse" - The on-premise version of ClickHouse
- "Databricks" - The SQL engine for Databricks
- "Trino" - The open source Trino on any infrastructure
- "Starburst" - The Hosted Trino
- "Snowflake"
- "BigQuery"
- "Redshift"
- "SQL Server" - The on-premise version of SQL Server.
  - Version string shoudl contain the edition (Enterprise, Standard, etc)
- "Azure Fabric" - The hosted version of Fabric
- "Oracle"
- "Db2"

### New Canonical Names

If you are missing a canonical engine name in the list above - please file a PR against this repo.

### New Database Drivers

Adding support for a new database engine is relatively simple task if you know how to write C++ code against the engine.

Support for new engines can be added by filing a PR against the `dbprove` repo. Before doing so, please add a new canonical name in this file.

- [dbprove repo](https://github.com/thomaskejser/dbprove)

## Disclaimer

All benchmark results in this repository are contributed by community members and reflect the specific configurations, data sets, software versions, and hardware environments used during those runs.

They do not represent definitive or universally applicable performance or accuracy characteristics of any database system.

Results should not be interpreted as endorsements, certifications, or official statements from the maintainers of this repository or from any database vendor.

Users are encouraged to reproduce benchmarks in their own environments and evaluate results independently.
