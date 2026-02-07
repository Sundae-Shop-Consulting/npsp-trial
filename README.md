# NPSP Trial Configuration

This project helps Salesforce consulting partners replicate the previous NPSP trial experience by applying pre-built configurations to a Sales Cloud org using CumulusCI (cci).

## Background

Previously, Salesforce provided a dedicated NPSP trial org template with pre-configured settings, sample data, and customizations optimized for nonprofit demonstrations. This project packages those configurations so partners can apply them to any Sales Cloud org with NPSP installed.

## Prerequisites

- [CumulusCI](https://cumulusci.readthedocs.io/) installed and configured
- A Salesforce org with NPSP installed
- The org connected to cci via `cci org connect`

For CumulusCI installation and setup, see the [CumulusCI documentation](https://cumulusci.readthedocs.io/en/latest/get-started.html).

## Usage

To deploy the trial configuration to your org:

```bash
cci task run deploy_tso_config --org <your-org-alias>
```

> **Warning:** This task deploys metadata that can overwrite existing customizations including layouts, profiles, permission sets, and other configurations. Do not run this against an org that has already been customized. This is intended for fresh orgs or demonstration environments only.

## What Gets Deployed

The `deploy_tso_config` task deploys metadata from `config/trial_tso/`, which includes configurations designed to mirror the original NPSP trial experience.

The only modification to date is the replacement of legacy workflow rules with their [flow equivalents](https://github.com/Sundae-Shop-Consulting/npsp-workflows-to-flows).

## License

See [NOTICES](NOTICES) for third-party license information.
