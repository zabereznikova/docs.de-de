---
title: Befehl „dotnet add package“
description: Der Paketbefehl „dotnet add“ bietet eine praktische Option zum Hinzufügen von NuGet-Paketverweisen zu einem Projekt.
ms.date: 02/14/2020
ms.openlocfilehash: cb44805f91ac4047dd50fd7e88d4eac5f15f2508
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503807"
---
# <a name="dotnet-add-package"></a><span data-ttu-id="744c9-103">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="744c9-103">dotnet add package</span></span>

<span data-ttu-id="744c9-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.x SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="744c9-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="744c9-105">name</span><span class="sxs-lookup"><span data-stu-id="744c9-105">Name</span></span>

<span data-ttu-id="744c9-106">`dotnet add package`: Fügt einen Paketverweis zu einer Projektdatei hinzu.</span><span class="sxs-lookup"><span data-stu-id="744c9-106">`dotnet add package` - Adds a package reference to a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="744c9-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="744c9-107">Synopsis</span></span>

`dotnet add [<PROJECT>] package <PACKAGE_NAME> [-h|--help] [-f|--framework] [--interactive] [-n|--no-restore] [--package-directory] [-s|--source] [-v|--version]`

## <a name="description"></a><span data-ttu-id="744c9-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="744c9-108">Description</span></span>

<span data-ttu-id="744c9-109">Der `dotnet add package`-Befehl bietet eine praktische Option zum Hinzufügen von Paketverweisen zu einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="744c9-109">The `dotnet add package` command provides a convenient option to add a package reference to a project file.</span></span> <span data-ttu-id="744c9-110">Nach dem Ausführen des Befehls wird die Kompatibilität überprüft, um sicherzustellen, dass das Paket mit den Frameworks im Projekt kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="744c9-110">After running the command, there's a compatibility check to ensure the package is compatible with the frameworks in the project.</span></span> <span data-ttu-id="744c9-111">Wenn die Überprüfung erfolgreich ist, wird ein `<PackageReference>`-Element zur Projektdatei hinzugefügt, und [dotnet restore](dotnet-restore.md) wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="744c9-111">If the check passes, a `<PackageReference>` element is added to the project file and [dotnet restore](dotnet-restore.md) is run.</span></span>

[!INCLUDE[DotNet Restore Note](../../../includes/dotnet-restore-note.md)]

<span data-ttu-id="744c9-112">Beispielsweise wird durch Hinzufügen von `Newtonsoft.Json` zu *ToDo.csproj* eine Ausgabe ähnlich der folgenden erzeugt:</span><span class="sxs-lookup"><span data-stu-id="744c9-112">For example, adding `Newtonsoft.Json` to *ToDo.csproj* produces output similar to the following example:</span></span>

```console
  Writing C:\Users\mairaw\AppData\Local\Temp\tmp95A8.tmp
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

<span data-ttu-id="744c9-113">Die *ToDo.csproj*-Datei enthält nun ein [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files)-Element für das Paket, auf das verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="744c9-113">The *ToDo.csproj* file now contains a [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) element for the referenced package.</span></span>

```xml
<PackageReference Include="Newtonsoft.Json" Version="12.0.1" />
```

## <a name="arguments"></a><span data-ttu-id="744c9-114">Argumente</span><span class="sxs-lookup"><span data-stu-id="744c9-114">Arguments</span></span>

- **`PROJECT`**

  <span data-ttu-id="744c9-115">Gibt die Projektdatei an.</span><span class="sxs-lookup"><span data-stu-id="744c9-115">Specifies the project file.</span></span> <span data-ttu-id="744c9-116">Wenn keine angegeben ist, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="744c9-116">If not specified, the command searches the current directory for one.</span></span>

- **`PACKAGE_NAME`**

  <span data-ttu-id="744c9-117">Hinzuzufügender Paketverweis.</span><span class="sxs-lookup"><span data-stu-id="744c9-117">The package reference to add.</span></span>

## <a name="options"></a><span data-ttu-id="744c9-118">Optionen</span><span class="sxs-lookup"><span data-stu-id="744c9-118">Options</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="744c9-119">Fügt Paketverweise nur hinzu, wenn ein bestimmtes [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="744c9-119">Adds a package reference only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

- **`-h|--help`**

  <span data-ttu-id="744c9-120">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="744c9-120">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="744c9-121">Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten (z.B. um die Authentifizierung abzuschließen).</span><span class="sxs-lookup"><span data-stu-id="744c9-121">Allows the command to stop and wait for user input or action (for example, to complete authentication).</span></span> <span data-ttu-id="744c9-122">Verfügbar ab .NET Core 2.1 SDK, Version 2.1.400 oder höher.</span><span class="sxs-lookup"><span data-stu-id="744c9-122">Available since .NET Core 2.1 SDK, version 2.1.400 or later.</span></span>

- **`-n|--no-restore`**

  <span data-ttu-id="744c9-123">Fügt Paketverweise hinzu, ohne eine Vorschau der Wiederherstellung und eine Kompatibilitätsüberprüfung durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="744c9-123">Adds a package reference without performing a restore preview and compatibility check.</span></span>

- **`--package-directory <PACKAGE_DIRECTORY>`**

  <span data-ttu-id="744c9-124">Das Verzeichnis, in dem die Pakete wiederhergestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="744c9-124">The directory where to restore the packages.</span></span> <span data-ttu-id="744c9-125">Der standardmäßige Wiederherstellungsort für Pakete ist `%userprofile%\.nuget\packages` unter Windows und `~/.nuget/packages` unter MacOS und Linux.</span><span class="sxs-lookup"><span data-stu-id="744c9-125">The default package restore location is `%userprofile%\.nuget\packages` on Windows and `~/.nuget/packages` on macOS and Linux.</span></span> <span data-ttu-id="744c9-126">Weitere Informationen finden Sie unter [Verwalten von globalen Pakete-, Cache- und temporären Ordnern in NuGet](https://docs.microsoft.com/nuget/consume-packages/managing-the-global-packages-and-cache-folders).</span><span class="sxs-lookup"><span data-stu-id="744c9-126">For more information, see [Managing the global packages, cache, and temp folders in NuGet](https://docs.microsoft.com/nuget/consume-packages/managing-the-global-packages-and-cache-folders).</span></span>

- **`-s|--source <SOURCE>`**

  <span data-ttu-id="744c9-127">Die NuGet-Paketquelle, die während des Wiederherstellungsvorgangs zu verwenden ist.</span><span class="sxs-lookup"><span data-stu-id="744c9-127">The NuGet package source to use during the restore operation.</span></span>

- **`-v|--version <VERSION>`**

  <span data-ttu-id="744c9-128">Die Version des Pakets.</span><span class="sxs-lookup"><span data-stu-id="744c9-128">Version of the package.</span></span> <span data-ttu-id="744c9-129">Weitere Informationen hierzu finden Sie unter [NuGet-Paketversionsverwaltung](https://docs.microsoft.com/nuget/reference/package-versioning).</span><span class="sxs-lookup"><span data-stu-id="744c9-129">See [NuGet package versioning](https://docs.microsoft.com/nuget/reference/package-versioning).</span></span>

## <a name="examples"></a><span data-ttu-id="744c9-130">Beispiele</span><span class="sxs-lookup"><span data-stu-id="744c9-130">Examples</span></span>

- <span data-ttu-id="744c9-131">Fügen Sie das `Newtonsoft.Json`-NuGet-Pakets zu einem Projekt hinzu:</span><span class="sxs-lookup"><span data-stu-id="744c9-131">Add `Newtonsoft.Json` NuGet package to a project:</span></span>

  ```dotnetcli
  dotnet add package Newtonsoft.Json
  ```

- <span data-ttu-id="744c9-132">Fügen Sie eine bestimmte Version eines Pakets zu einem Projekt hinzu:</span><span class="sxs-lookup"><span data-stu-id="744c9-132">Add a specific version of a package to a project:</span></span>

  ```dotnetcli
  dotnet add ToDo.csproj package Microsoft.Azure.DocumentDB.Core -v 1.0.0
  ```

- <span data-ttu-id="744c9-133">Fügen Sie ein Paket mit einer bestimmten NuGet-Quelle hinzu:</span><span class="sxs-lookup"><span data-stu-id="744c9-133">Add a package using a specific NuGet source:</span></span>

  ```dotnetcli
  dotnet add package Microsoft.AspNetCore.StaticFiles -s https://dotnet.myget.org/F/dotnet-core/api/v3/index.json
  ```

## <a name="see-also"></a><span data-ttu-id="744c9-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="744c9-134">See also</span></span>

- [<span data-ttu-id="744c9-135">Verwalten von globalen Pakete-, Cache- und temporären Ordnern in NuGet</span><span class="sxs-lookup"><span data-stu-id="744c9-135">Managing the global packages, cache, and temp folders in NuGet</span></span>](https://docs.microsoft.com/nuget/consume-packages/managing-the-global-packages-and-cache-folders)
- [<span data-ttu-id="744c9-136">NuGet-Paketversionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="744c9-136">NuGet package versioning</span></span>](https://docs.microsoft.com/nuget/reference/package-versioning)
