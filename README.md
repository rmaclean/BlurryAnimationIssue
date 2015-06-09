# Testing Markdown

## Powershell
### Tabs
    Configuration ContosoWeb
    {
        # A Configuration block can have zero or more Node blocks
        Node "Server001"
        {
            # Next, specify one or more resource blocks
            # WindowsFeature is one of the built-in resources you can use in a Node block
            # This example ensures the Web Server (IIS) role is installed
            WindowsFeature IIS
            {
                Ensure = "Present" # To uninstall the role, set Ensure to "Absent"
                Name = "Web-Server"
            }
            WindowsFeature ASP
            {
                Ensure = "Present" # To uninstall the role, set Ensure to "Absent"
                Name = "Web-Asp-Net45"
            }
            # File is a built-in resource you can use to manage files and directories
            # This example ensures files from the source directory are present in the destination directory
            File SiteCatalog
            {
                Ensure = "Present"  # You can also set Ensure to "Absent"
                Type = "Directory" # Default is "File"
                Recurse = $true
                SourcePath = $WebsiteFilePath # This is a path that has web files
                DestinationPath = "C:\inetpub\wwwroot"
                # The path where we want to ensure the web files are present
                DependsOn = "[WindowsFeature]ASP"
                # This ensures that MyRoleExample completes successfully before this block runs
            }
        }
    }

### Just Back marks

```
Configuration ContosoWeb
{
    # A Configuration block can have zero or more Node blocks
    Node "Server001"
    {
        # Next, specify one or more resource blocks
        # WindowsFeature is one of the built-in resources you can use in a Node block
        # This example ensures the Web Server (IIS) role is installed
        WindowsFeature IIS
        {
            Ensure = "Present" # To uninstall the role, set Ensure to "Absent"
            Name = "Web-Server"
        }
        WindowsFeature ASP
        {
            Ensure = "Present" # To uninstall the role, set Ensure to "Absent"
            Name = "Web-Asp-Net45"
        }
        # File is a built-in resource you can use to manage files and directories
        # This example ensures files from the source directory are present in the destination directory
        File SiteCatalog
        {
            Ensure = "Present"  # You can also set Ensure to "Absent"
            Type = "Directory" # Default is "File"
            Recurse = $true
            SourcePath = $WebsiteFilePath # This is a path that has web files
            DestinationPath = "C:\inetpub\wwwroot"
            # The path where we want to ensure the web files are present
            DependsOn = "[WindowsFeature]ASP"
            # This ensures that MyRoleExample completes successfully before this block runs
        }
    }
}
```

### Annotated  Back marks

```powershell
Configuration ContosoWeb
{
    # A Configuration block can have zero or more Node blocks
    Node "Server001"
    {
        # Next, specify one or more resource blocks
        # WindowsFeature is one of the built-in resources you can use in a Node block
        # This example ensures the Web Server (IIS) role is installed
        WindowsFeature IIS
        {
            Ensure = "Present" # To uninstall the role, set Ensure to "Absent"
            Name = "Web-Server"
        }
        WindowsFeature ASP
        {
            Ensure = "Present" # To uninstall the role, set Ensure to "Absent"
            Name = "Web-Asp-Net45"
        }
        # File is a built-in resource you can use to manage files and directories
        # This example ensures files from the source directory are present in the destination directory
        File SiteCatalog
        {
            Ensure = "Present"  # You can also set Ensure to "Absent"
            Type = "Directory" # Default is "File"
            Recurse = $true
            SourcePath = $WebsiteFilePath # This is a path that has web files
            DestinationPath = "C:\inetpub\wwwroot"
            # The path where we want to ensure the web files are present
            DependsOn = "[WindowsFeature]ASP"
            # This ensures that MyRoleExample completes successfully before this block runs
        }
    }
}
```

## Console
### Tabs

    PS C:\windows\system32> find-module x*

    Version         Name                   DateUpdated               Description                         
    -------         ----                   -----------               -----------                         
    2.0             xActiveDirectory       7/29/2014 1:42:57 AM      The xActiveDirectory module is a ...
    0.1.1           xAzure                 7/27/2014 10:12:51 AM     The xAzure module is a set of DSC...
    1.2.1           xComputerManagement    7/29/2014 1:42:57 AM      The xComputerManagement module is...
    1.1.2           xDatabase              7/27/2014 10:37:52 PM     The xDatabase module is a part of...
    1.1             xDhcpServer            7/29/2014 1:42:57 AM      The xDhcpServer module is a part ...
    1.0             xDnsServer             7/27/2014 10:12:51 AM     The xDnsServer module is a part o...
    2.0             xDscDiagnostics        7/28/2014 9:37:54 AM      Module to help in reading details...
    1.1.1.1         xDSCResourceDesigner   7/29/2014 12:37:59 PM     The xDscResourceDesigner module i...
    2.6.0.0         xEXOUserAvailability   7/27/2014 10:12:51 AM     xEXOUserAvailability can help you...
    1.1.1           xFailOverCluster       7/27/2014 10:12:51 AM     The xFailOverCluster module is a ...
    2.1.1           xHyper-V               7/29/2014 1:42:57 AM      The xHyper-V module is a part of ...
    0.2.16.1        xJea                   7/29/2014 4:12:59 PM      Module with DSC Resources for Jus...
    1.0.0.0         xMySql                 7/29/2014 4:08:00 PM      The xMySql module is a part of th... 
    
### Plain back ticks

```
PS C:\windows\system32> find-module x*

Version         Name                   DateUpdated               Description                         
-------         ----                   -----------               -----------                         
2.0             xActiveDirectory       7/29/2014 1:42:57 AM      The xActiveDirectory module is a ...
0.1.1           xAzure                 7/27/2014 10:12:51 AM     The xAzure module is a set of DSC...
1.2.1           xComputerManagement    7/29/2014 1:42:57 AM      The xComputerManagement module is...
1.1.2           xDatabase              7/27/2014 10:37:52 PM     The xDatabase module is a part of...
1.1             xDhcpServer            7/29/2014 1:42:57 AM      The xDhcpServer module is a part ...
1.0             xDnsServer             7/27/2014 10:12:51 AM     The xDnsServer module is a part o...
2.0             xDscDiagnostics        7/28/2014 9:37:54 AM      Module to help in reading details...
1.1.1.1         xDSCResourceDesigner   7/29/2014 12:37:59 PM     The xDscResourceDesigner module i...
2.6.0.0         xEXOUserAvailability   7/27/2014 10:12:51 AM     xEXOUserAvailability can help you...
1.1.1           xFailOverCluster       7/27/2014 10:12:51 AM     The xFailOverCluster module is a ...
2.1.1           xHyper-V               7/29/2014 1:42:57 AM      The xHyper-V module is a part of ...
0.2.16.1        xJea                   7/29/2014 4:12:59 PM      Module with DSC Resources for Jus...
1.0.0.0         xMySql                 7/29/2014 4:08:00 PM      The xMySql module is a part of th... 
```

### Annotated back ticks (this time `console`)

```console
PS C:\windows\system32> find-module x*

Version         Name                   DateUpdated               Description                         
-------         ----                   -----------               -----------                         
2.0             xActiveDirectory       7/29/2014 1:42:57 AM      The xActiveDirectory module is a ...
0.1.1           xAzure                 7/27/2014 10:12:51 AM     The xAzure module is a set of DSC...
1.2.1           xComputerManagement    7/29/2014 1:42:57 AM      The xComputerManagement module is...
1.1.2           xDatabase              7/27/2014 10:37:52 PM     The xDatabase module is a part of...
1.1             xDhcpServer            7/29/2014 1:42:57 AM      The xDhcpServer module is a part ...
1.0             xDnsServer             7/27/2014 10:12:51 AM     The xDnsServer module is a part o...
2.0             xDscDiagnostics        7/28/2014 9:37:54 AM      Module to help in reading details...
1.1.1.1         xDSCResourceDesigner   7/29/2014 12:37:59 PM     The xDscResourceDesigner module i...
2.6.0.0         xEXOUserAvailability   7/27/2014 10:12:51 AM     xEXOUserAvailability can help you...
1.1.1           xFailOverCluster       7/27/2014 10:12:51 AM     The xFailOverCluster module is a ...
2.1.1           xHyper-V               7/29/2014 1:42:57 AM      The xHyper-V module is a part of ...
0.2.16.1        xJea                   7/29/2014 4:12:59 PM      Module with DSC Resources for Jus...
1.0.0.0         xMySql                 7/29/2014 4:08:00 PM      The xMySql module is a part of th... 
```
