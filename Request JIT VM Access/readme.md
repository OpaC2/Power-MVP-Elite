# Request-JITVMAccess.ps1
## Automate Just In Time VM Access Request With PowerShell 

This tool is written to automate the entire Just In Time VM Access process. The script will connect to Azure Security Center endpoint, and then will open the requested port temporarily. If Just in Time VM Access is not enabled for that VM, the script will enable it, and then request VM access on your behalf. Additionally, the script will automatically install Azure Resource Manager and Azure Security Center PowerShell modules if they are not installed on your machine.

You can run the script in multiple scenarios as follows:

### EXAMPLE -1-
.\Request-JITVMAccess.ps1 -VMName <VMName> -Credential <AzureUser@domain.com> -Port <Port> -Time <Hours> -Verbose

This example will enable Just in Time VM Access for a particular Azure VM from any source IP. The management port will be set as specified including the number of hours.
If Just in Time VM Access is not enabled, the tool will enable the policy and then request VM access.

### EXAMPLE -2-
.\Request-JITVMAccess.ps1 -VMName <VMName> -Credential <AzureUser@domain.com> -Port <Port> -AddressPrefix <AllowedSourceIP> -Time <Hours> -Verbose

This example will enable Just in Time VM Access for a particular Azure VM including the management port, source IP, and number of hours.
If Just in Time VM Access is not enabled, the tool will enable the policy for the VM and then request VM access.

### EXAMPLE -3-
.\Request-JITVMAccess.ps1 -VMName <VMName> -Credential <AzureUser@domain.com> -Port <Port> -AddressPrefix <AllowedSourceIP> -Verbose

This example will enable Just in Time VM Access for a particular Azure VM including the management port, and source IP address.
If Just in Time VM Access is not enabled, the tool will enable the policy for the VM, you need to provide the maximum requested time in hours.
If Just in Time VM Access is already enabled, the tool will automatically extract the maximum requested time set by the policy, and then request VM access.

### EXAMPLE -4-
.\Request-JITVMAccess.ps1 -VMName <VMName> -Credential <AzureUser@domain.com> -Port <Port> -Verbose
This example will enable Just in Time VM Access for a particular Azure VM from any source IP. The management port will be set as specified.

If Just in Time VM Access is not enabled, the tool will enable the policy for the VM, you need to provide the maximum requested time in hours.  
If Just in Time VM Access is already enabled, the tool will automatically extract the maximum requested time set by the policy, and then request VM access.

Here are a couple of screenshots showing how to use this tool.

### Output 1

### Output 2

### Output 3

### Output 4

---- Tested environment -----
- Windows Server 2016, Version 1607 / 1709 / 1803
- EN-US language OS

---- Tested environment -----
- Windows 10, Version 1607 / 1703 / 1709 / 1803
- EN-US language OS

If you have any feedback or changes that everyone should receive, please feel free to leave a comment, update the source code and create a pull request.

Thank You!

-Charbel Nemnom-