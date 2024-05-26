# Adding Extra Storage in Microsoft Azure

As applications and data grow, the need for additional storage becomes critical for maintaining performance, scalability, and reliability. Microsoft Azure provides flexible options to add extra storage to Virtual Machines (VMs), ensuring that your applications can scale efficiently. This guide covers the steps to add extra storage, the benefits, considerations, and best practices for managing additional storage in Azure.

## How to Add Extra Storage in Microsoft Azure
### 1. Using the Azure Portal
1. **Navigate to the Virtual Machine**:
   - Go to the [Azure Portal](https://portal.azure.com) and select your VM.

2. **Stop the VM** (if necessary):
   - It’s often recommended to stop the VM before adding disks to avoid potential issues.

3. **Add Data Disk**:
   - Under the "Settings" section, click on "Disks."
   - Click on the "+ Add data disk" button.
   - Choose "Create disk" to create a new disk or select an existing disk.
   - Configure the disk settings (name, size, type).

4. **Attach the Disk**:
   - Once configured, attach the disk to the VM and save the changes.

5. **Initialize and Format the Disk** (within the VM):
   - Log in to the VM.
   - Use the OS’s disk management tools to initialize and format the new disk.

### 2. Using Azure CLI
```bash
# Create a new managed disk
az disk create --resource-group myResourceGroup --name myDataDisk --size-gb 1024 --sku Premium_LRS

# Attach the disk to the VM
az vm disk attach --resource-group myResourceGroup --vm-name myVM --name myDataDisk
```

### Using PowerShell

```powershell
# Create a new managed disk
$diskConfig = New-AzDiskConfig -AccountType Premium_LRS -Location "EastUS" -CreateOption Empty -DiskSizeGB 1024
$dataDisk = New-AzDisk -ResourceGroupName "myResourceGroup" -DiskName "myDataDisk" -Disk $diskConfig

# Attach the disk to the VM
Add-AzVMDataDisk -VM $vm -Name "myDataDisk" -ManagedDiskId $dataDisk.Id -Lun 1 -Caching ReadWrite -DiskSizeInGB 1024 -CreateOption Attach
Update-AzVM -ResourceGroupName "myResourceGroup" -VM $vm
```

## The Need for Extra Storage
1. **Increased Data Storage Requirements**: As applications and databases grow, the need for additional storage becomes imperative to accommodate more data.
2. **Performance Improvements**: Adding extra disks can help distribute data and I/O operations, thereby improving overall performance.
3. **Backup and Recovery**: Additional disks can be used for backup purposes, ensuring data protection and quick recovery in case of failures.
4. **Application Scaling**: When applications scale, more storage is needed to handle increased workloads and user demands.

## Benefits of Adding Extra Storage
1. **Scalability**: Easily scale your storage capacity to meet the growing data needs of your applications.
2. **Performance**: Enhanced performance by distributing I/O operations across multiple disks, reducing bottlenecks.
3. **Flexibility**: Customize your storage configurations to meet specific application requirements and performance needs.
4. **Cost Efficiency**: Optimize costs by selecting appropriate disk types (Standard, Premium, Ultra) based on performance requirements.

## When to Add Extra Storage
1. **Before Performance Bottlenecks**: Proactively add storage before encountering performance issues to ensure smooth operation.
2. **When Scaling Applications**: Add storage during the deployment of additional instances or scaling of existing applications to maintain performance.
3. **Data Growth**: Increase storage capacity when there is a significant rise in data volume that exceeds current storage limits.
4. **High I/O Workloads**: For applications requiring high IOPS (Input/Output Operations Per Second), adding more disks can significantly improve performance.

## Number of Disks That Can Be Added
- **Depends on VM Size**: The number of data disks that can be attached to a VM depends on the VM size. For example, a ``Standard_D2s_v3`` VM can support up to 8 data disks, while a ``Standard_D64s_v3`` VM can support up to 64 data disks.
- **Azure Limits**: Azure provides detailed documentation on the limits for each VM size, including the maximum number of data disks supported. Refer to Azure documentation for specific VM size limits.

## Understanding IOPS in a Disk

### What is IOPS?
IOPS (Input/Output Operations Per Second) is the measure of the performance of storage devices, indicating how many read and write operations a disk can perform in one second.

### Importance of IOPS
- **Performance Metric**: Higher IOPS indicates better performance, which is crucial for applications with high transactional workloads.
- **Workload Suitability**: Different applications have different IOPS requirements. For example, databases and large-scale web applications may require high IOPS for optimal performance.

### Factors Affecting IOPS
- **Disk Type**:
  - **Standard HDD**: Lower IOPS, suitable for less demanding workloads.
  - **Standard SSD**: Moderate IOPS, good for general-purpose use.
  - **Premium SSD**: High IOPS, ideal for performance-sensitive applications.
  - **Ultra Disk**: Very high IOPS, designed for mission-critical workloads.

- **Disk Size**:
  - Larger disks typically offer higher IOPS.

- **Caching Policies**:
  - Read-only or read/write caching can improve IOPS for specific workloads.

### Managing IOPS
- **Monitoring**:
  - Use Azure Monitor to track disk IOPS and identify performance bottlenecks.

- **Optimization**:
  - Distribute I/O operations across multiple disks to enhance performance.
  - Select the appropriate disk type and size based on performance requirements.