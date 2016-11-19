---
layout: default
title: Setup for Local Code Execution
---
## Setup for Local Code Execution

You can execute code on your local computer and push the computations to the SQL Server on the VM  that was created by the Cortana Intelligence Gallery. But first you must perform the following steps. 

## On the VM: Configure VM for Remote Access

Connect to the VM to perform the following steps.

You must open the Windows firewall on the VM to allow a connection to the SQL Server. To open the firewall, execute the following command in a PowerShell window on the VM:

    netsh advfirewall firewall add rule name="SQLServer" dir=in action=allow protocol=tcp localport=1433 

If you wish to run the PowerShell script from your local computer, you also need to disable a default rule by executing the following: 

    Import-Module NetSecurity
    Get-NetFirewallRule –displayname "Block network access for R local user accounts in SQL Server instance MSSQLSERVER"| Set-NetFirewallRule -Enabled False -Direction Outbound 

If you would later like to reverse this change, execute the following:

    Get-NetFirewallRule –displayname "Block network access for R local user accounts in SQL Server instance MSSQLSERVER"| Set-NetFirewallRule -Enabled True -Direction Outbound


SQL Server on the VM has been set up with a user `rdemo` and a default password of `D@tascience`.  Once you open the firewall, you may also want to also change the password, as anyone who knows the IP address can now access the server.  To do so, log into SSMS with Windows Authentication and execute the following query:
    
        ALTER LOGIN rdemo WITH PASSWORD = 'newpassword';  
       
## On your local computer:  Install R Client and Obtain Code

Perform these steps on your local computer.

If you use your local computer you will need to have a copy of [R Client](https://msdn.microsoft.com/en-us/microsoft-r/install-r-client-windows) on your local machine, installed and configured for your IDE. 

Also, on your local computer you will need a copy of the solution code.  Open a PowerShell window, navigate to the directory of your choice, and execute the following command:  

    git clone https://github.com/Microsoft/r-server-campaign-optimization.git

This will create a folder **r-server-campaign-optimization** containing the full solution package.

<a href="CIG_Workflow.html#step2">Return to Typical Workflow for Cortana Intelligence Gallery Deployment<a>