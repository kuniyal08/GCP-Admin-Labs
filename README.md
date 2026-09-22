# GCP Admin Labs

Hands-on Google Cloud administration labs focused on practical configuration, command-line administration, networking, IAM, troubleshooting, monitoring, and operational fundamentals.

I use this repository to document work completed in the Google Cloud console, Cloud Shell, and the `gcloud` CLI. The lab notes emphasize what I configured, how I verified it, and what I learned from the result.

## Lab Progress

| Lab | Main skills | Status |
| --- | --- | --- |
| [01 - Cloud Console and Cloud Shell](labs/01-cloud-console-cloud-shell/) | Cloud Storage, Cloud Shell, `gcloud`, shell persistence, service discovery, context checks | Complete |
| 02 - Compute Engine | VM administration, disks, images, snapshots | Planned |
| [03 - VPC Networking](labs/03-vpc-networking/) | VPCs, subnets, routes, firewall rules, IAP, connectivity testing | In progress |
| 04 - IAM | Roles, permissions, service accounts | Planned |
| 05 - Monitoring and Logging | Metrics, logs, alerts, Ops Agent | Planned |

## Repository Structure

```text
GCP-Admin-Labs/
├── README.md
└── labs/
    ├── 01-cloud-console-cloud-shell/
    │   ├── README.md
    │   └── screenshots/
    └── 03-vpc-networking/
        ├── README.md
        └── screenshots/
```

## Documentation Approach

Each completed lab records:

- the objective and services used;
- the important configuration choices;
- relevant `gcloud` commands;
- screenshots that verify the work;
- connectivity or troubleshooting tests;
- security considerations where applicable; and
- the main operational lessons from the lab.

The goal is to document administrative understanding rather than reproduce step-by-step course instructions.
