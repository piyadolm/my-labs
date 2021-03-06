# Optimize storage performance

## 1. Optimize virtual machine storage performance

Type of Virtual Machine's disk:

1. Local SSD storage

    * This SSD is local to the virtual machine
    * Performance is high
    * Data could be lost during a maintenance event or a redeployment of the VM
    * Suitable for temporary storage of data
    * Great for the VM's page or swap file
    * No charge for this storage. It's included in the cost of the VM

2. Standard storage HDD
    * Spindle disk storage
    * Inconsistent latency
    * Lower levels of throughput
    * For dev/test workload

3. Standard storage SSD
    * Spindle disk storage
    * Low latency of an SSD
    * Lower levels of throughput
    * For non-production web server

4. Premium storage SSD
    * For production workloads (recommended for all Prod workload)
    * Greatest reliability
    * Low latency
    * High level of throughput and IOPS
    * Can attach only to specific VM size

### Premium disk option

Premium storage-capable sizes are designated with an "s" in the name. Examples are D2s_v3 or Standard_F2s_v2. Any virtual machine type (with or without an "s" in the name) can attach standard storage HDD or SSD drives.

### Disk striped

Striping increases the throughput and IOPS by spreading disk activity across multiple disks.
You can use disk striping to push the limits of performance for disks.

## 2. Optimize storage performance for your application

### 2.1 Caching

Integrate a caching layer between your application and your data store.
A cache typically stores data in memory and allows for fast retrieval.

By colocating this cache in the same region as your application and database, you reduce the overall latency between the two.

Azure Cache for Redis is a caching service on Azure that stores data in memory.

### 2.2 Polyglot persistence

Polyglot persistence is the use of different data storage technologies to handle your storage requirements.

Eventual consistency means that replica data stores eventually converge if there are no further writes.
If a write is made to one of the data stores, reads from another data store might provide slightly out-of-date data. enables higher scale because there's a low latency for reads and writes, instead of waiting to check if information is consistent across all stores.
