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


# Module 8 - Vulnerability Management 




# Module 9 - Evaluate Network Security Capabilities 




# Module 10 - Assess Endpoint Security Capabilities







