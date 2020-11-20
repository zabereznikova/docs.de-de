---
title: Befehl „dotnet add package“
description: Der Paketbefehl „dotnet add“ bietet eine praktische Option zum Hinzufügen von NuGet-Paketverweisen zu einem Projekt.
ms.date: 11/11/2020
ms.openlocfilehash: 10373b3b69c669323674b192d54cd277a5828f24
ms.sourcegitcommit: f99115e12a5eb75638abe45072e023a3ce3351ac
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2020
ms.locfileid: "94556874"
---
# <a name="dotnet-add-package"></a><span data-ttu-id="ed979-103">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="ed979-103">dotnet add package</span></span>

<span data-ttu-id="ed979-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.x SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="ed979-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="ed979-105">name</span><span class="sxs-lookup"><span data-stu-id="ed979-105">Name</span></span>

<span data-ttu-id="ed979-106">`dotnet add package`: Fügt einen Paketverweis zu einer Projektdatei hinzu.</span><span class="sxs-lookup"><span data-stu-id="ed979-106">`dotnet add package` - Adds a package reference to a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="ed979-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="ed979-107">Synopsis</span></span>

```dotnetcli
dotnet add [<PROJECT>] package <PACKAGE_NAME>
    [-f|--framework <FRAMEWORK>] [--interactive]
    [-n|--no-restore] [--package-directory <PACKAGE_DIRECTORY>]
    [--prerelease] [-s|--source <SOURCE>] [-v|--version <VERSION>]

dotnet add package -h|--help
```

## <a name="description"></a><span data-ttu-id="ed979-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ed979-108">Description</span></span>

<span data-ttu-id="ed979-109">Der `dotnet add package`-Befehl bietet eine praktische Option zum Hinzufügen von Paketverweisen zu einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="ed979-109">The `dotnet add package` command provides a convenient option to add a package reference to a project file.</span></span> <span data-ttu-id="ed979-110">Nach dem Ausführen des Befehls wird die Kompatibilität überprüft, um sicherzustellen, dass das Paket mit den Frameworks im Projekt kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="ed979-110">After running the command, there's a compatibility check to ensure the package is compatible with the frameworks in the project.</span></span> <span data-ttu-id="ed979-111">Wenn die Überprüfung erfolgreich ist, wird ein `<PackageReference>`-Element zur Projektdatei hinzugefügt, und [dotnet restore](dotnet-restore.md) wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ed979-111">If the check passes, a `<PackageReference>` element is added to the project file and [dotnet restore](dotnet-restore.md) is run.</span></span>

<span data-ttu-id="ed979-112">Beispielsweise wird durch Hinzufügen von `Newtonsoft.Json` zu *ToDo.csproj* eine Ausgabe ähnlich der folgenden erzeugt:</span><span class="sxs-lookup"><span data-stu-id="ed979-112">For example, adding `Newtonsoft.Json` to *ToDo.csproj* produces output similar to the following example:</span></span>

```console
Writing C:\Users\me\AppData\Local\Temp\tmp95A8.tmp
info : Adding PackageReference for package 'Newtonsoft.Json' into project 'C:\projects\ToDo\ToDo.csproj'.
log  : Restoring packages for C:\Temp\projects\consoleproj\consoleproj.csproj...
info :   GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json
info :   OK https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json 79ms
info :   GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/12.0.1/newtonsoft.json.12.0.1.nupkg
info :   OK https://api.nuget.org/v3-flatcontainer/newtonsoft.json/12.0.1/newtonsoft.json.12.0.1.nupkg 232ms
log  : Installing Newtonsoft.Json 12.0.1.
info : Package 'Newtonsoft.Json' is compatible with all the specified frameworks in project 'C:\projects\ToDo\ToDo.csproj'.
info : PackageReference for package 'Newtonsoft.Json' version '12.0.1' added to file 'C:\projects\ToDo\ToDo.csproj'.
```

<span data-ttu-id="ed979-113">Die *ToDo.csproj*-Datei enthält nun ein [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files)-Element für das Paket, auf das verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="ed979-113">The *ToDo.csproj* file now contains a [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) element for the referenced package.</span></span>

```xml
<PackageReference Include="Newtonsoft.Json" Version="12.0.1" />
```

### <a name="implicit-restore"></a><span data-ttu-id="ed979-114">Implizite Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="ed979-114">Implicit restore</span></span>

[!INCLUDE[DotNet Restore Note](../../../includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="ed979-115">Argumente</span><span class="sxs-lookup"><span data-stu-id="ed979-115">Arguments</span></span>

- **`PROJECT`**

  <span data-ttu-id="ed979-116">Gibt die Projektdatei an.</span><span class="sxs-lookup"><span data-stu-id="ed979-116">Specifies the project file.</span></span> <span data-ttu-id="ed979-117">Wenn keine angegeben ist, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="ed979-117">If not specified, the command searches the current directory for one.</span></span>

- **`PACKAGE_NAME`**

  <span data-ttu-id="ed979-118">Hinzuzufügender Paketverweis.</span><span class="sxs-lookup"><span data-stu-id="ed979-118">The package reference to add.</span></span>

## <a name="options"></a><span data-ttu-id="ed979-119">Optionen</span><span class="sxs-lookup"><span data-stu-id="ed979-119">Options</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="ed979-120">Fügt Paketverweise nur hinzu, wenn ein bestimmtes [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ed979-120">Adds a package reference only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

- **`-h|--help`**

  <span data-ttu-id="ed979-121">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="ed979-121">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="ed979-122">Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten (z.B. um die Authentifizierung abzuschließen).</span><span class="sxs-lookup"><span data-stu-id="ed979-122">Allows the command to stop and wait for user input or action (for example, to complete authentication).</span></span> <span data-ttu-id="ed979-123">Verfügbar ab .NET Core 2.1 SDK, Version 2.1.400 oder höher.</span><span class="sxs-lookup"><span data-stu-id="ed979-123">Available since .NET Core 2.1 SDK, version 2.1.400 or later.</span></span>

- **`-n|--no-restore`**

  <span data-ttu-id="ed979-124">Fügt Paketverweise hinzu, ohne eine Vorschau der Wiederherstellung und eine Kompatibilitätsüberprüfung durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="ed979-124">Adds a package reference without performing a restore preview and compatibility check.</span></span>

- **`--package-directory <PACKAGE_DIRECTORY>`**

  <span data-ttu-id="ed979-125">Das Verzeichnis, in dem die Pakete wiederhergestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ed979-125">The directory where to restore the packages.</span></span> <span data-ttu-id="ed979-126">Der standardmäßige Wiederherstellungsort für Pakete ist `%userprofile%\.nuget\packages` unter Windows und `~/.nuget/packages` unter MacOS und Linux.</span><span class="sxs-lookup"><span data-stu-id="ed979-126">The default package restore location is `%userprofile%\.nuget\packages` on Windows and `~/.nuget/packages` on macOS and Linux.</span></span> <span data-ttu-id="ed979-127">Weitere Informationen finden Sie unter [Verwalten von globalen Pakete-, Cache- und temporären Ordnern in NuGet](/nuget/consume-packages/managing-the-global-packages-and-cache-folders).</span><span class="sxs-lookup"><span data-stu-id="ed979-127">For more information, see [Managing the global packages, cache, and temp folders in NuGet](/nuget/consume-packages/managing-the-global-packages-and-cache-folders).</span></span>

- **`--prerelease`**

  <span data-ttu-id="ed979-128">Ermöglicht die Installation von Paketen mit Vorabversionen</span><span class="sxs-lookup"><span data-stu-id="ed979-128">Allows prerelease packages to be installed.</span></span>

- **`-s|--source <SOURCE>`**

  <span data-ttu-id="ed979-129">Der URI der NuGet-Paketquelle, die während des Wiederherstellungsvorgangs zu verwenden ist.</span><span class="sxs-lookup"><span data-stu-id="ed979-129">The URI of the NuGet package source to use during the restore operation.</span></span>

- **`-v|--version <VERSION>`**

  <span data-ttu-id="ed979-130">Die Version des Pakets.</span><span class="sxs-lookup"><span data-stu-id="ed979-130">Version of the package.</span></span> <span data-ttu-id="ed979-131">Weitere Informationen hierzu finden Sie unter [NuGet-Paketversionsverwaltung](/nuget/reference/package-versioning).</span><span class="sxs-lookup"><span data-stu-id="ed979-131">See [NuGet package versioning](/nuget/reference/package-versioning).</span></span>

## <a name="examples"></a><span data-ttu-id="ed979-132">Beispiele</span><span class="sxs-lookup"><span data-stu-id="ed979-132">Examples</span></span>

- <span data-ttu-id="ed979-133">Fügen Sie das `Newtonsoft.Json`-NuGet-Pakets zu einem Projekt hinzu:</span><span class="sxs-lookup"><span data-stu-id="ed979-133">Add `Newtonsoft.Json` NuGet package to a project:</span></span>

  ```dotnetcli
  dotnet add package Newtonsoft.Json
  ```

- <span data-ttu-id="ed979-134">Fügen Sie eine bestimmte Version eines Pakets zu einem Projekt hinzu:</span><span class="sxs-lookup"><span data-stu-id="ed979-134">Add a specific version of a package to a project:</span></span>

  ```dotnetcli
  dotnet add ToDo.csproj package Microsoft.Azure.DocumentDB.Core -v 1.0.0
  ```

- <span data-ttu-id="ed979-135">Fügen Sie ein Paket mit einer bestimmten NuGet-Quelle hinzu:</span><span class="sxs-lookup"><span data-stu-id="ed979-135">Add a package using a specific NuGet source:</span></span>

  ```dotnetcli
  dotnet add package Microsoft.AspNetCore.StaticFiles -s https://dotnet.myget.org/F/dotnet-core/api/v3/index.json
  ```

## <a name="see-also"></a><span data-ttu-id="ed979-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ed979-136">See also</span></span>

- [<span data-ttu-id="ed979-137">Verwalten von globalen Pakete-, Cache- und temporären Ordnern in NuGet</span><span class="sxs-lookup"><span data-stu-id="ed979-137">Managing the global packages, cache, and temp folders in NuGet</span></span>](/nuget/consume-packages/managing-the-global-packages-and-cache-folders)
- [<span data-ttu-id="ed979-138">NuGet-Paketversionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="ed979-138">NuGet package versioning</span></span>](/nuget/reference/package-versioning)
