# Testing Markdown

## Tabs
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

## Just Back marks

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

## Annotated  Back marks

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
