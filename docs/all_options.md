# All Options

vfxt.py - Create an Create an Avere vFXT cluster

usage:
```
vfxt.py [-h] [-d] [-v]
(--create|--destroy|--stop|--start|--add-nodes|--upgrade|--check|--telemetry|--interact)
--cloud-type {aws,azure,gce} 
[--on-instance] [--from-environment] [--image-id IMAGE_ID] 
[--s3-access-key S3_ACCESS_KEY] [--s3-secret-key S3_SECRET_KEY] [--s3-profile S3_PROFILE]
[--access-key ACCESS_KEY] [--secret-key SECRET_KEY] [--profile PROFILE]
[--security-group SECURITY_GROUP] [--region REGION]
[--iam-role IAM_ROLE] [--iam-host IAM_HOST] 
[--iam-role-principal-service IAM_ROLE_PRINCIPAL_SERVICE]  
[--arn ARN] [--ephemeral] [--placement-group PLACEMENT_GROUP]
[--dedicated-tenancy]
[--subnet SUBNET [SUBNET ...]] 
[--aws-tag AWS_TAG] [--govcloud] 
[--no-disk-encryption] [--no-ebs-optimized]


[--client-email CLIENT_EMAIL]
[--project PROJECT] [--network-project NETWORK_PROJECT]
[--zone ZONE [ZONE ...]] [--network NETWORK] [--subnetwork SUBNETWORK]
[--key-file KEY_FILE] [--local-ssd] [--metadata METADATA]
[--labels LABELS] [--gce-tag GCE_TAG]
[--service-account SERVICE_ACCOUNT]
[--scopes SCOPES [SCOPES ...]]
[--instance-addresses INSTANCE_ADDRESSES [INSTANCE_ADDRESSES ...]]
[--storage-class STORAGE_CLASS]

[--subscription-id SUBSCRIPTION_ID] [--storage-account STORAGE_ACCOUNT]
[--application-id AD_APPLICATION_ID] 
[--application-secret APPLICATION_SECRET]

    [--tenant-id TENANT_ID] [--resource-group RESOURCE_GROUP]
    [--network-resource-group NETWORK_RESOURCE_GROUP]
    [--storage-resource-group STORAGE_RESOURCE_GROUP]

[--network-security-group NETWORK_SECURITY_GROUP] xxx not described? xxx 

[--azure-role AZURE_ROLE] [--location LOCATION] 

    [--azurecontainer STORAGE ]   xxx not in help xxx 

[--azure-network AZURE_NETWORK] [--azure-subnet AZURE_SUBNET] 
[--azure-tag AZURE_TAG]
[--azure-instance-addresses INSTANCE_ADDRESSES [INSTANCE_ADDRESSES ...]]

[--enable-boot-diagnostics]
[--root-disk-caching {ReadOnly,ReadWrite}]
[--data-disk-caching {ReadOnly,ReadWrite}]
[--skip-cleanup] 
[--wait-for-state {red,yellow,green}] 
[--wait-for-state-duration WAIT_FOR_STATE_DURATION]
[--proxy-uri URL] [--cluster-proxy-uri URL] 
[--ssh-key SSH_KEY]
[--skip-check] [--log LOG]
[--cluster-name CLUSTER_NAME]
[--instance-type INSTANCE_TYPE] [--instances INSTANCES [INSTANCES ...]]
[--admin-password ADMIN_PASSWORD] [--management-address IP_ADDR] 
[--nodes NODES] 
[--node-cache-size NODE_CACHE_SIZE] [--data-disk-count DATA_DISK_COUNT]
[--data-disk-type DATA_DISK_TYPE] [--data-disk-iops DATA_DISK_IOPS] 
[--data-disk-nvme] [--data-disk-size DATA_DISK_SIZE] [--root-size ROOT_SIZE]
[--upgrade-url UPGRADE_URL] [--upgrade-non-ha]
[--cluster-range CLUSTER_RANGE]
[--trace-level TRACE_LEVEL]
[--timezone TIMEZONE]
[--join-wait JOIN_WAIT] 
[--quick-destroy]
[--no-corefiler] [--core-filer CORE_FILER] [--bucket STORAGE]
[--nfs-mount NFS_MOUNT] 
[--nfs-type {NetappNonClustered,NetappClustered,EmcIsilon}]
[--subdir SUBDIR] [--junction JUNCTION] 
[--vserver VSERVER] [--no-vserver]
```