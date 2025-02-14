## Installing .NET

If you followed the setup guide
[Setting Up Your Workstation for C# and Unity API Training](../../../00%20-%20Resources/Setup%20Documents/Setting%20Up%20Your%20Workstation%20for%20C#%20and%20Unity%20API%20Training.pdf), ,NET will have installed along with Visual Studio.

If not, you can find installers at
[[www.dot.net](https://dotnet.microsoft.com/en-us/download)](https://dotnet.microsoft.com/en-us/download)

As of these notes, the two supported versions a .NET 8 and .NET 9  
\* .NET 6 reached EOL in November 2024

Since it is a long-term release, I recommend installing .NET 8.

Don't worry about the book targeting .NET 6. All the information in this
book is also applicable to .NET 8.

---

### .NET Validation

There are several command-lie switches you can use to validate that you 
have the correct version of .NET installed.

#### .NET Version

```powershell
dotnet --version
```

Output:

```
8.0.405
```

---

#### .NET Information

```powershell
dotnet --info
```

Output:

```
.NET SDK:
 Version:           8.0.405
 Commit:            fb1830d421
 Workload version:  8.0.400-manifests.4a0c9b73
 MSBuild version:   17.11.9+a69bbaaf5

Runtime Environment:
 OS Name:     Windows
 OS Version:  10.0.26100
 OS Platform: Windows
 RID:         win-x64
 Base Path:   C:\Program Files\dotnet\sdk\8.0.405\

.NET workloads installed:
Configured to use loose manifests when installing new manifests.
 [aspire]
   Installation Source: VS 17.11.35303.130
   Manifest Version:    8.1.0/8.0.100
   Manifest Path:       C:\Program Files\dotnet\sdk-manifests\8.0.100\microsoft.net.sdk.aspire\8.1.0\WorkloadManifest.json
   Install Type:        FileBased

Host:
  Version:      8.0.12
  Architecture: x64
  Commit:       89ef51c5d8

.NET SDKs installed:
  8.0.400 [C:\Program Files\dotnet\sdk]
  8.0.405 [C:\Program Files\dotnet\sdk]

.NET runtimes installed:
  Microsoft.AspNetCore.App 8.0.8 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
  Microsoft.AspNetCore.App 8.0.12 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
  Microsoft.NETCore.App 8.0.8 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
  Microsoft.NETCore.App 8.0.12 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
  Microsoft.WindowsDesktop.App 8.0.8 [C:\Program Files\dotnet\shared\Microsoft.WindowsDesktop.App]
  Microsoft.WindowsDesktop.App 8.0.12 [C:\Program Files\dotnet\shared\Microsoft.WindowsDesktop.App]

Other architectures found:
  x86   [C:\Program Files (x86)\dotnet]
    registered at [HKLM\SOFTWARE\dotnet\Setup\InstalledVersions\x86\InstallLocation]

Environment variables:
  Not set

global.json file:
  Not found

Learn more:
  https://aka.ms/dotnet/info

Download .NET:
  https://aka.ms/dotnet/download
```

---

#### .NET Runtime Versions

```powershell
dotnet --list-runtimes
```

Output:

```
Microsoft.AspNetCore.App 8.0.8 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 8.0.12 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.NETCore.App 8.0.8 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 8.0.12 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.WindowsDesktop.App 8.0.8 [C:\Program Files\dotnet\shared\Microsoft.WindowsDesktop.App]
Microsoft.WindowsDesktop.App 8.0.12 [C:\Program Files\dotnet\shared\Microsoft.WindowsDesktop.App]
```

---

#### .NET SDK Versions

```powershell
dotnet --list-sdks
```

Output:

```
8.0.400 [C:\Program Files\dotnet\sdk]
8.0.405 [C:\Program Files\dotnet\sdk]
```

---

#### Check for SDK Updates

```powershell
dotnet sdk check
```

Output:

```
.NET SDKs:
Version      Status
----------------------------------------
8.0.400      Patch 8.0.405 is available.
8.0.405      Up to date.

Try out the newest .NET SDK features with .NET 9.0.102.

.NET Runtimes:
Name                              Version      Status
-------------------------------------------------------------------------
Microsoft.AspNetCore.App          8.0.8        Patch 8.0.12 is available.
Microsoft.NETCore.App             8.0.8        Patch 8.0.12 is available.
Microsoft.WindowsDesktop.App      8.0.8        Patch 8.0.12 is available.
Microsoft.AspNetCore.App          8.0.12       Up to date.
Microsoft.NETCore.App             8.0.12       Up to date.
Microsoft.WindowsDesktop.App      8.0.12       Up to date.


The latest versions of .NET can be installed from https://aka.ms/dotnet-core-download. For more information about .NET lifecycles, see https://aka.ms/dotnet-core-support.
```

---

### Use an Older SDK Version

If you need to use an older version of the .NET SDK, provided it is
installed on your machine, you can use the following command:

```powershell
dotnet new globaljson --sdk 6.0.400
```

This will create a `global.json` file in the current directory that
specifies the version of the .NET SDK to use.

```json
{
    "sdk": {
        "version": "6.0.400"
    }
}
```

---
