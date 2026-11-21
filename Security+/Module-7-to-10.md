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
* Alerts, monitering, and management tools for these data backups(For example, alerts of systems not being backed up in X days)


# Module 8 - Vulnerability Management 




# Module 9 - Evaluate Network Security Capabilities 




# Module 10 - Assess Endpoint Security Capabilities







