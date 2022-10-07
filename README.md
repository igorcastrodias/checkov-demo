# Checkov

Checkov is a static code analysis tool for scanning infrastructure as code (IaC) files for misconfigurations that may lead to security or compliance problems

[bridgecrewio/checkov](https://github.com/bridgecrewio/checkov)
 
## Usage

``` bash
terraform init
terraform plan -out tf.plan
terraform show -json tf.plan  > tf.json
checkov -f tf.json
````

Terminal Output

```` bash
terraform_plan scan results:

Passed checks: 9, Failed checks: 6, Skipped checks: 0

Check: CKV_AZURE_118: "Ensure that Network Interfaces disable IP forwarding"
        PASSED for resource: azurerm_network_interface.example
        File: /tf.json:0-0
        Guide: https://docs.bridgecrew.io/docs/ensure-that-network-interfaces-disable-ip-forwarding
Check: CKV_AZURE_59: "Ensure that Storage accounts disallow public access"
        PASSED for resource: azurerm_storage_account.example
        File: /tf.json:0-0
        Guide: https://docs.bridgecrew.io/docs/ensure-that-storage-accounts-disallow-public-access
Check: CKV_AZURE_43: "Ensure Storage Accounts adhere to the naming rules"
        PASSED for resource: azurerm_storage_account.example
        File: /tf.json:0-0
        Guide: https://docs.bridgecrew.io/docs/ensure-storage-accounts-adhere-to-the-naming-rules
Check: CKV_AZURE_60: "Ensure that storage account enables secure transfer"
        PASSED for resource: azurerm_storage_account.example
        File: /tf.json:0-0
        Guide: https://docs.bridgecrew.io/docs/ensure-that-storage-account-enables-secure-transfer
Check: CKV_AZURE_44: "Ensure Storage Account is using the latest version of TLS encryption"
        PASSED for resource: azurerm_storage_account.example
        File: /tf.json:0-0
        Guide: https://docs.bridgecrew.io/docs/bc_azr_storage_2
Check: CKV_AZURE_36: "Ensure 'Trusted Microsoft Services' is enabled for Storage Account access"
        PASSED for resource: azurerm_storage_account.example
        File: /tf.json:0-0
        Guide: https://docs.bridgecrew.io/docs/enable-trusted-microsoft-services-for-storage-account-access
Check: CKV_AZURE_3: "Ensure that 'Secure transfer required' is set to 'Enabled'"
        PASSED for resource: azurerm_storage_account.example
        File: /tf.json:0-0
        Guide: https://docs.bridgecrew.io/docs/ensure-azure-secure-transfer-required-feature-is-set-to-enabled
Check: CKV_AZURE_92: "Ensure that Virtual Machines use managed disks"
        PASSED for resource: azurerm_windows_virtual_machine.example
        File: /tf.json:0-0
        Guide: https://docs.bridgecrew.io/docs/ensure-that-virtual-machines-use-managed-disks
Check: CKV_AZURE_119: "Ensure that Network Interfaces don't use public IPs"
        PASSED for resource: azurerm_network_interface.example
        File: /tf.json:0-0
        Guide: https://docs.bridgecrew.io/docs/ensure-that-network-interfaces-dont-use-public-ips
Check: CKV_AZURE_33: "Ensure Storage logging is enabled for Queue service for read, write and delete requests"
        FAILED for resource: azurerm_storage_account.example
        File: /tf.json:0-0
        Guide: https://docs.bridgecrew.io/docs/enable-requests-on-storage-logging-for-queue-service
Check: CKV_AZURE_35: "Ensure default network access rule for Storage Accounts is set to deny"
        FAILED for resource: azurerm_storage_account.example
        File: /tf.json:0-0
        Guide: https://docs.bridgecrew.io/docs/set-default-network-access-rule-for-storage-accounts-to-deny
Check: CKV_AZURE_151: "Ensure Windows VM enables encryption"
        FAILED for resource: azurerm_windows_virtual_machine.example
        File: /tf.json:0-0
        Guide: https://docs.bridgecrew.io/docs/ensure-azure-windows-vm-enables-encryption
Check: CKV_AZURE_50: "Ensure Virtual Machine Extensions are not Installed"
        FAILED for resource: azurerm_windows_virtual_machine.example
        File: /tf.json:0-0
        Guide: https://docs.bridgecrew.io/docs/bc_azr_general_14
Check: CKV2_AZURE_1: "Ensure storage for critical data are encrypted with Customer Managed Key"
        FAILED for resource: azurerm_storage_account.example
        File: /tf.json:0-0
        Guide: https://docs.bridgecrew.io/docs/ensure-storage-for-critical-data-are-encrypted-with-customer-managed-key
Check: CKV2_AZURE_18: "Ensure that Storage Accounts use customer-managed key for encryption"
        FAILED for resource: azurerm_storage_account.example
        File: /tf.json:0-0
        Guide: https://docs.bridgecrew.io/docs/ensure-that-storage-accounts-use-customer-managed-key-for-encryption
````