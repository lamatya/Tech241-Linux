Azure- Blob Storage

## Blob Storage

### Different ways to create portal; 

  a. Azure portal

  b. Azure CLI (command line interface)

  c. Azure PowerShell

## Commands to log in and create resource group.
```
- az storage account create --name tech241larishastorage --resource-group tech241 --location uksouth --sku Standard_LRS

- az storage account list --resource-group tech241

- az storage account list --resource-group tech241 --query "[].{Name:name, Location:location, Kind:kind}" --output table

- az storage container create \ --account-name tech241larishastorage \ --name testcontainer

- az storage container create --account-name tech241larishastorage --name testcontainer
```
```
- az storage blob upload \ 
  --account-name tech241larishastorage \ 
  --container-name testcontainer \ 
  --name newname.txt \ 
  --file test.txt \ 
  --auth-mode login
```
```commandline
- az storage blob list \ 
--account-name tech241larishastorage \ 
--container-name testcontainer \ 
--output table \ 
--auth-mode login
```
## What is Blob Storage

a. Blob storage refers to a type of storage service provided by cloud platforms like Azure that is optimized for storing large amounts of unstructured data, such as text or binary data. It is commonly used for storing files, images, videos, backups, and logs.

## Difference between blob storage and the file system of Linux/Windows/Mac (hierachical file storage)
The main difference between blob storage and the file system of Linux/Windows/Mac is the way they store and organize data.

In a hierarchical file system (such as those used in Linux, Windows, or macOS), data is organized in a hierarchical directory structure with folders and subfolders. Each file is stored in a specific location within this structure, and the file system provides methods for navigating and accessing the files based on their paths.

On the other hand, blob storage does not have a hierarchical structure. Instead, it uses a flat namespace, where data is stored as individual blobs identified by unique IDs or names. Blob storage does not have the concept of folders or subfolders, but it allows you to organize blobs by using container names and blob metadata.

## Advantages/disadvantages of blob storage

### Advantages of blob storage include:

- Scalability: Blob storage is highly scalable and can handle large amounts of data.

- Durability: Blob storage provides high durability, ensuring that your data is protected against hardware failures.

- Accessibility: Blob storage can be accessed from anywhere using various protocols like REST APIs, Azure SDKs, or tools specific to the cloud platform.

- Cost-effectiveness: Blob storage offers cost-effective pricing models, allowing you to pay for the storage you actually use.

- Integration: Blob storage integrates well with other Azure services and tools, making it easy to build complex applications.

### Disadvantages of blob storage include:

- Limited functionality: Blob storage is optimized for storing and retrieving unstructured data but lacks some of the advanced features provided by traditional file systems.

- Lack of hierarchical organization: The flat structure of blob storage can make it challenging to organize and manage large amounts of data if a hierarchical structure is required.

- Learning curve: Working with blob storage requires understanding its specific concepts and APIs, which may have a learning curve for those unfamiliar with it.

## Azure Blob Storage offers different tiers that provide varying levels of performance, durability, and cost. The available tiers are:

- Hot Access Tier: This tier is optimized for frequently accessed data and offers low access latency. It has a higher storage cost compared to other tiers but provides lower access costs. It is suitable for data that requires frequent access.

- Cool Access Tier: The Cool tier is designed for data that is accessed less frequently but still requires quick access when needed. It has lower storage costs compared to the Hot tier but higher access costs. It is suitable for data with moderate access patterns.

- Archive Access Tier: The Archive tier is intended for long-term archival storage. It has the lowest storage costs among the tiers but incurs higher access costs and longer retrieval times. It is suitable for data that is rarely accessed but needs to be retained for compliance or legal reasons.

### To determine the specific costs associated with each tier, you can use the Azure Pricing Calculator or refer to the Azure Storage pricing documentation, as pricing may vary based on region and storage capacity.

## In Azure Blob Storage, the components are related as follows:

- Account: An Azure Storage account serves as a top-level container for your blob storage resources. Within an account, you can have multiple containers.

- Container: A container is a logical grouping of blobs within an Azure Storage account. It is similar to a folder but exists within the flat namespace of blob storage. Containers help you organize and manage your blobs. Each container has a unique name within the storage account.

- Blobs: Blobs are the individual data objects stored within containers. They can represent files, images, videos, or any other unstructured data. Blobs are identified by their unique names or IDs.

The hierarchy is Account > Container > Blobs.


## There are several types of redundancy available. Here are the most common ones:

- LRS (Locally Redundant Storage): LRS ensures that your data is replicated within a single Azure data center in a specific region. It provides a cost-effective redundancy option by creating three copies of your data within the same data center. 

- ZRS (Zone-Redundant Storage): ZRS replicates your data across multiple Azure availability zones within a single region. It provides higher durability and availability compared to LRS by storing three copies of your data in three separate zones within the same region. ZRS is a good choice when you require higher availability for your data within a single region.

- GRS (Geo-Redundant Storage): GRS provides redundancy by replicating your data to a secondary region, which is typically hundreds of miles away from the primary region. It creates six copies of your data, three in the primary region and three in the secondary region. In the event of a regional outage, your data remains accessible from the secondary region. GRS offers better disaster recovery capabilities but may have higher data access latency due to the geographical distance.

- RA-GRS (Read-Access Geo-Redundant Storage): RA-GRS combines the features of GRS with the ability to read data from the secondary region. This redundancy option provides the same six copies of data as GRS but allows read access to the secondary region for improved availability and data access performance.

- GZ-RS (Geo-Zone-Redundant Storage): GZRS provides both local redundancy within a region (similar to ZRS) and geo-redundancy to a secondary region (similar to GRS). It creates six copies of data within three availability zones in the primary region and three copies in the secondary region. GZRS offers the highest level of durability and availability for block blob storage.

- RA-GZRS (Read-Access Geo-Zone-Redundant Storage): RA-GZRS combines the features of GZRS with the ability to read data from the secondary region, similar to RA-GRS. It provides the highest level of durability, availability, and data access performance by replicating data across availability zones in the primary region and secondary region.

Redundancy options allow you to choose the level of durability, availability, and disaster recovery capabilities that will suit your specific needs for block blob storage in Azure.



![img_1.png](img_1.png)