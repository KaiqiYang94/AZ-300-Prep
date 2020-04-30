
# Designing for Azure High Availability


## Introduction
- ![](2020-04-30-09-34-18.png)

## Understanding the Azure Global Infrastructure
- Geographies
  - A region is a set of datacenters deployed within a latency-defined perimeter and connected through a dedicated regional low-latency network.
- Region
  - A geography is a discrete market, typically containing two or more regions, that preserves data residency and compliance boundaries.
- Availability zone
  - Availability Zones are physically separate locations within an Azure region. Each Availability Zone is made up of one or more datacenters equipped with independent power, cooling, and networking.
- ![](Azure%20global%20infrastructure.png)

## Working with Availability Sets
- For the redundancy within the same data center
  - Fault domain
  - Update domain
  - ![](Availability%20sets.png)
  - Demo
    - Create Availability set before the VMs
      - ![](New%20Availability%20set.png)
    - Select the number of fault domains
      - ![](Select%20the%20number%20of%20fault%20domains.png)
    - Pick the availability sets when deploy the availability sets
      - Create VM
        - Create VM with Availability Zone
          - ![](Create%20VM%20with%20availability%20zone.png)
        - Create VM with Availability set
          - Create VM with Availability set

## Architecting with Availability Zones
- Using Availability Zone to achieve a more robust architecture
  - ![](Availability%20Zone%20in%20use.png)
- [Official Doc](https://docs.microsoft.com/bs-cyrl-ba/azure/best-practices-availability-paired-regions)
  - An example of paired regions
    - ![](An%20example%20of%20paired%20regions.png)
### Cross-region activities
As referred to in figure 2.

1. **Azure Compute (IaaS)** – You must provision additional compute resources in advance to ensure resources are available in another region during a disaster. For more information, see [Azure resiliency technical guidance](https://github.com/uglide/azure-content/blob/master/articles/resiliency/resiliency-technical-guidance.md). 

2. **Azure Storage** - If you're using managed disks, learn about [cross-region backups](https://docs.microsoft.com/azure/architecture/resiliency/recovery-loss-azure-region#virtual-machines) with Azure Backup, and [replicating VMs](https://docs.microsoft.com/azure/site-recovery/azure-to-azure-tutorial-enable-replication) from one region to another with Azure Site Recovery. If you're using storage accounts, then geo-redundant storage (GRS) is configured by default when an Azure Storage account is created. With GRS, your data is automatically replicated three times within the primary region, and three times in the paired region. For more information, see [Azure Storage Redundancy Options](storage/common/storage-redundancy.md).

3. **Azure SQL Database** – With Azure SQL Database Geo-Replication, you can configure asynchronous replication of transactions to any region in the world; however, we recommend you deploy these resources in a paired region for most disaster recovery scenarios. For more information, see [Geo-Replication in Azure SQL Database](sql-database/sql-database-geo-replication-overview.md).

4. **Azure Resource Manager** - Resource Manager inherently provides logical isolation of components across regions. This means logical failures in one region are less likely to impact another.

### Benefits of paired regions

1. **Physical isolation** – When possible, Azure prefers at least 300 miles of separation between datacenters in a regional pair, although this isn't practical or possible in all geographies.

2. **Platform-provided replication** - Some services such as Geo-Redundant Storage provide automatic replication to the paired region.

3. **Region recovery order** – In the event of a broad outage, recovery of one region is prioritized out of every pair. Applications that are deployed across paired regions are guaranteed to have one of the regions recovered with priority.

4. **Sequential updates** – Planned Azure system updates are rolled out to paired regions sequentially (not at the same time) to minimize downtime, the effect of bugs, and logical failures in the rare event of a bad update.

5. **Data residency** – A region resides within the same geography as its pair (with the exception of Brazil South) to meet data residency requirements for tax and law enforcement jurisdiction purposes.
## Key Azure Services That Support High Availability
- Key Azure Services That Support multiple Availability Zone
  - ![](Key%20Azure%20Services%20Supporting%20multiple%20AZ.png)
## Working with Azure Paired Regions
- Designing with Azure paired regions
  - They are architect to work together for site recovery
  - Service can be duplicated easily between paired regions
    - ![](Azure%20paired%20regions.png)
- Benefits of paired regions
  - ![](Benefits%20of%20paired%20regions.png)
  - ![](Benefits%20of%20paired%20regions%202.png)

## Architecture Patterns for High Availability

## Module Summary

# Designing for Azure Autoscale


## Introduction

## Understanding Vertical and Horizontal Scaling

## Designing Autoscaling Rules

## Creating a Virtual Machine Scale Set

## Enabling Autoscale with Virtual Machine Scale Sets

## Autoscaling in Azure App Service

## Scalability with Azure Functions

## Module Summary

# Designing for Storage High Availability

## Introduction

## Understanding Azure Storage Replication

## Accessing Data During Regional Outages

## Working with Virtual Machine Managed Disks

## Taking Snapshots of Virtual Machine Disks

## Running Virtual Machine Backups

## Storage High Availability for SQL Databases

## Working with Azure SQL Database Geo-replication

## Building Globally Distributed Applications with Azure Cosmos DB

## Module Summary

# Designing for Network Redundancy


## Introduction

## Designing for High Availability with Azure Load Balancers

## Designing a Virtual Network from Scratch

## Placing Servers in Separate Availability Zones

## Load Balancing Across Availability Zones

## Architecting Multi-region Solutions

## Common Design Patterns for High Availability

## Module Summary

# Designing for Application Redundancy


## Introduction

## Azure App Service Resiliency

## Azure SQL Database Considerations

## Application Gateway High Availability

## Azure Redis Cache Geo-replication

## Asynchronous Messaging and High Availability

## Module Summary