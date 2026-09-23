# Lab 03 - VPC Networking

**Google Skills lab:** CBL057 - Create and Configure VPC Networks  
**Main services:** Virtual Private Cloud (VPC), Compute Engine, Identity-Aware Proxy (IAP), Cloud Shell, Google Cloud CLI  
**Status:** In progress

## Objective

This lab focuses on Google Cloud VPC administration and connectivity.

The work includes:

- inspecting the default VPC, routes, and firewall rules;
- creating an auto mode VPC;
- configuring firewall rules;
- using IAP for SSH access;
- converting an auto mode VPC to custom mode;
- creating custom VPC networks and regional subnets;
- creating Compute Engine VM instances;
- using `gcloud` to inspect and configure networking resources; and
- testing connectivity within and across VPC networks.

## Key Concepts

### VPC and Subnet Scope

A Google Cloud VPC is a global resource. Subnets are regional resources.

A VM receives an internal address from the subnet attached to its network interface.

### Routes vs Firewall Rules

A route answers:

> Where should this packet go?

A firewall rule answers:

> Is this traffic permitted?

A valid route does not by itself permit the connection. The applicable firewall rules must also allow the traffic.

### Default Firewall Behavior

Google Cloud VPC networks include implied firewall behavior:

- ingress traffic is denied unless an applicable rule allows it;
- egress traffic is allowed unless an applicable higher-priority rule denies it.

### Firewall Rule Priorities

Lower numerical values have higher priority.

For example, a rule with priority `500` is evaluated before a rule with priority `1000`.

## Planned Lab Work

### 1. Inspect the Default VPC

Document:

- automatically created subnets;
- subnet CIDR ranges;
- subnet routes;
- the `0.0.0.0/0` default internet route; and
- default firewall rules.

### 2. Create an Auto Mode VPC

Create the training VPC and inspect the automatically created regional subnets.

### 3. Configure IAP SSH Access

Create an ingress firewall rule for IAP TCP/22 access.

Important fields to document:

```text
Direction: INGRESS
Action: ALLOW
Source range: 35.235.240.0/20
Target tag: iap-gce
Protocol/port: tcp:22
```

### 4. Create VM Instances

Deploy VM instances in different regions and verify their internal and external addressing.

### 5. Convert Auto Mode to Custom Mode

Convert the VPC after the initial tests and record the reason custom mode provides more deliberate control of subnet creation and IP planning.

### 6. Create Custom VPC Networks

Create additional custom networks and non-overlapping subnet ranges.

Use both the Cloud console and `gcloud` so that the lab demonstrates GUI and CLI administration.

### 7. Create Firewall Rules with `gcloud`

Record the firewall configuration and verify:

- direction;
- priority;
- action;
- source range;
- protocol and port; and
- target scope.

### 8. Test Connectivity

Test and document:

- external IP connectivity where explicitly allowed;
- internal connectivity between VMs in the same VPC;
- internal connectivity between VMs in different regions of the same VPC; and
- expected failure between separate VPC networks without an interconnection mechanism.

## Security Considerations

Some training rules allow SSH, RDP, or ICMP from `0.0.0.0/0` so that firewall behavior can be demonstrated.

That is not a production recommendation.

A production design should prefer least-privilege controls such as:

- restricted source CIDR ranges;
- IAP or another controlled administrative access path;
- workload-specific targets;
- network tags or service accounts where appropriate;
- narrowly scoped protocols and ports; and
- firewall logging when useful for operations and troubleshooting.

## Screenshot Plan

Add screenshots for:

1. default VPC and regional subnets;
2. route table and default internet route;
3. default firewall rules;
4. auto mode VPC;
5. IAP SSH firewall rule;
6. custom VPCs and subnet CIDRs;
7. `gcloud compute networks list`;
8. `gcloud compute networks subnets list --sort-by=NETWORK`;
9. firewall rule listing;
10. successful internal ping across regions in the same VPC; and
11. failed internal ping between separate VPC networks.

## Commands

Commands will be added here as the lab is completed.

## Result

This section will be completed after the connectivity tests and final verification.
