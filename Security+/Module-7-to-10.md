# Module 7 - Resiliency and Site Security Concepts 

## Asset Management

### Asset Tracking

Assets, asset specs, as well as asset ownership needs to be tracked. 

If an asset goes missing, we need to be able to see exactly what is missing as well as understand the overall context of that asset. Tracking is how we do so.

It can be done manually by logging each asset or by using network scanners like NMAP.

Asset management software solutions that handle all of this are also offered, such as Lansweeper or ManageEngine

**Configuration Management Database(CMDB):** This is essentially service that provides a platform that acts as a repo for assets, configurations, infrastructure layout, etc. 

**Mobile Device Management(MDM):** Intune, Hexnode, etc. 

**Cloud Asset Discovery:** Asset discovery, tracking, and management specifically for cloud environments, such as AWS Config or Azure Resource Graph

### Backups

Backups are absolutely imperative for protecting against unexpected events or the accidental loss/destruction of data. They achieve availability as well as integrity of the CIA triad. 

At scale, data requires continuous, recurring, and automatic backups. On top of this, they require the following:

* Backups need to be quickly recoverable to restore data in case of data failure at any moments notice
* Support for backups of various environments including on-prem servers, the cloud, VMs, etc.
* Optimization of storage space of the backups through data deduplication as well as data compression.
* Ransomware protection and data encryption
* Alerts, monitoring, and management tools for these data backups(For example, alerts of systems not being backed up in X days)

#### Snapshots:

To review, snapshots are just "pictures" of a system that can be rolled back to. 

We have: 

* VM Snapshots
* File System Snapshots such as a ZFS or BTRFS Snapshot
* Storage Area Network(SAN) Snapshots

A SAN is a network which connects to a centralized storage to use as a disk. For example, we may have 3 servers running. A SAN would have all those 3 servers connected to a centralized storage system allowing those servers to access that storage and store their data onto it. 

They use "Block-level storage" meaning that the storage allocated to each server are allocated with fixed sized units called blocks. These blocks of storage appear as a virtual hard drive to each server to access and use as they please. The identifier for an aggregated amount of blocks, creating a disk would be called a LUN(Logical Unit Number).

### Secure Data Destruction

There is:

1) Asset Disposal/Decomissioning
2) Sanitization - Just deleting data does not destroy it. Forensics can still recover it. A software is used to securely wipe the disk and ensure it is unrecoverable.
3) Destruction - 4 types: Incinerate, Shred, Drilling, and Degaussing(Eliminating the magnetic field of a disk) alongside sanitation. 

There can also be a certification that may be obtained to display that confidential data has been securely destroyed and disposed of. 

## Redundancy Strategies 

Have 2 of everything as well as backups of everything so that operations can continue or quickly resume in case anything critical is disrupted.

**Hot Standby vs Cold Standby Backups:** 

Hot standbys are actively running and are ready at any point in case of an immediate failure. However they are more expensive.

Cold standbys are cheaper but are powered down and only kicks in when the failure actively occurs. 

Continuity of Operations Plans(COOP): Plans to ensure that operations can continue after there is a disruption. Backups play a critical role in this. 

**Capacity Planning:** The assessment of current and future resource requirements to ensure they meet the needed amounts for their business objectives. 

### Capacity Planning Risks

The following are some of the risks of not properly planning for capacity. 

* People Risks - Need to plan for the amount of people in your company. Could be budget, machines, licenses, bandwidth, firewall, etc. 
* Cross-Training - Requires Staff members to understand or have a general idea of the other staff's jobs and responsibilities. If other people are suddenly no longer in the company or unavailable, you need to have other people be able to fill in so their responsibilities can be adapted or filled in. 
* Remote work Plans - Have some sort of plan so that staff can work from home in case of an emergency like Covid-19
* Alternative Reporting Structures - Need to plan to have staff be able to report to someone in case their main reporting manager is unavailable.
* Changes in Workforce Capacity - Need to plan for rapid sudden changes in workforce whether it be a reduction or increase
* Rapid Hiring - Hiring occuring too rapidly can be an issue. For example, who will train them all? Who will they be shadowing?
* Layoffs - This is also an issue especially in regards to access control and identity management. They all needed to be offboarded correctly to ensure they do not have access to things they should not have access to anymore

# Module 8 - Vulnerability Management 




# Module 9 - Evaluate Network Security Capabilities 




# Module 10 - Assess Endpoint Security Capabilities







