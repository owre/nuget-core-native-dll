# ASP&#46;NET Core Dll NuGet wrapper - local feed

Simple guidance to make it possible to reference native dlls inside asp&#46;net core projects

For convenience download the latest [NuGet.exe](https://dist.nuget.org/index.html)

##### Create nuget package
  1. Create a new directory and put **nuget.exe** and the **.dll** file you like to reference inside
  2. Open a command prompt inside the new directory and write `nuget spec [filename].dll`
  3. Edit **.nuspec** file and fill in appropriate values
  4. Copy **[filename].dll** to a subdirectory named **lib**
  5. Create nuget package by issuing `nuget pack [filename].nuspec`
  6. Publish nuget package by issuing `nuget add [filename].nupkg -source [FOLDER]`
  7. Then add the [FOLDER] as a package source inside visual studio nuget package manager

The complete folder structure should look like:
```
New Directory
/-- lib
  /-- *.dll
/-- *.nupkg
/-- *.nuspec
/-- nuget.exe
```
***
Solution for: *.NET Core projects only support referencing .NET framework assemblies in this release. To reference other assemblies, they need to be included in a NuGet package and reference that package.*
