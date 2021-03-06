# Install-ChocolateyInstallPackage

This will run a native installer to perform an install/upgrade on your machine.

**NOTE:** This command will assert UAC/Admin privileges on the machine.

## Usage

```powershell
Install-ChocolateyInstallPackage $packageName $installType $silentArgs $file
```

## Examples

```powershell
Install-ChocolateyInstallPackage '7zip' 'exe' '/S' 'c:\somepath\7zipInstaller.msi'

Install-ChocolateyInstallPackage '7zip' 'exe' '/S' 'c:\somepath\7zipInstaller.msi' `
 -validExitCodes @(0,21,33)
```

## Parameters

* `-packageName`

    This is an arbitrary name.

    Example: `'7zip'`

* `-fileType` (in process of renaming to `installType`)

    Pick only one : 'exe' or 'msi'

    Example: `'exe'` or `'msi'`

* `-silentArgs`

    Silent and other arguments to pass to the native installer.

    Example: `'/S'`

    If there are no silent arguments, pass this as `''`

* `-file`

    This is the file to install. This is a full path to the file.

    Example: `'c:\somepath\someinstaller.msi'`

* `-validExitCodes` _(optional)_

    If there are other valid exit codes besides zero signifying a successful install, please pass `-validExitCodes` with the value, including 0 as long as it is still valid.

    Example: `-validExitCodes @(0,44)`

    Defaults to `@(0)`.

[[Function Reference|HelpersReference]]