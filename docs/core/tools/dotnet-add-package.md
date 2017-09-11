---
title: "Paketbefehl „dotnet-add“ – .NET Core-CLI"
description: "Der Paketbefehl „dotnet-add“ bietet eine praktische Option zum Hinzufügen von NuGet-Paketverweisen zu einem Projekt."
keywords: dotnet-add, CLI, CLI-Befehl, .NET Core
author: spboyer
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 88e0da69-a5ea-46cc-8b46-5493242b7af9
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 40ee7cac969d4752ede66ba8df6ff6cb3f439aec
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-add-package"></a><span data-ttu-id="1c520-104">Paket dotnet-add</span><span class="sxs-lookup"><span data-stu-id="1c520-104">dotnet-add package</span></span>

## <a name="name"></a><span data-ttu-id="1c520-105">Name</span><span class="sxs-lookup"><span data-stu-id="1c520-105">Name</span></span>

<span data-ttu-id="1c520-106">`dotnet-add package`: Fügt einen Paketverweis zu einer Projektdatei hinzu.</span><span class="sxs-lookup"><span data-stu-id="1c520-106">`dotnet-add package` - Adds a package reference to a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="1c520-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="1c520-107">Synopsis</span></span>

`dotnet add [<PROJECT>] package <PACKAGE_NAME> [-v|--version] [-f|--framework] [-n|--no-restore] [-s|--source] [--package-directory] [-h|--help]`

## <a name="description"></a><span data-ttu-id="1c520-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1c520-108">Description</span></span>

<span data-ttu-id="1c520-109">Der `dotnet add package`-Befehl bietet eine praktische Option zum Hinzufügen von Paketverweisen zu einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="1c520-109">The `dotnet add package` command provides a convenient option to add a package reference to a project file.</span></span> <span data-ttu-id="1c520-110">Nach dem Ausführen des Befehls wird die Kompatibilität überprüft, um sicherzustellen, dass das Paket mit den Frameworks im Projekt kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="1c520-110">After running the command, there's a compatibility check to ensure the package is compatible with the frameworks in the project.</span></span> <span data-ttu-id="1c520-111">Wenn die Überprüfung erfolgreich ist, wird ein `<PackageReference>`-Element zur Projektdatei hinzugefügt, und [dotnet restore](dotnet-restore.md) wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1c520-111">If the check passes, a `<PackageReference>` element is added to the project file and [dotnet restore](dotnet-restore.md) is run.</span></span>

<span data-ttu-id="1c520-112">Beispielsweise wird durch Hinzufügen von `Newtonsoft.Json` zu *ToDo.csproj* eine Ausgabe ähnlich der folgenden erzeugt:</span><span class="sxs-lookup"><span data-stu-id="1c520-112">For example, adding `Newtonsoft.Json` to *ToDo.csproj* produces output similar to the following:</span></span>

```
Microsoft (R) Build Engine version 15.1.545.13942
Copyright (C) Microsoft Corporation. All rights reserved.

Writing /var/folders/gj/1mgg_4jx7mbdqbhw1kgcpcjr0000gn/T/tmpm0kTMD.tmp
info : Adding PackageReference for package 'Newtonsoft.Json' into project 'ToDo.csproj'.
log  : Restoring packages for ToDo.csproj...
info :   GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json
info :   OK https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json 119ms
info :   GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/9.0.1/newtonsoft.json.9.0.1.nupkg
info :   OK https://api.nuget.org/v3-flatcontainer/newtonsoft.json/9.0.1/newtonsoft.json.9.0.1.nupkg 27ms
info : Package 'Newtonsoft.Json' is compatible with all the specified frameworks in project 'ToDo.csproj'.
info : PackageReference for package 'Newtonsoft.Json' version '9.0.1' added to file 'ToDo.csproj'.
```

<span data-ttu-id="1c520-113">Die *ToDo.csproj*-Datei enthält nun ein [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files)-Element für das Paket, auf das verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="1c520-113">The *ToDo.csproj* file now contains a [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) element for the referenced package.</span></span>

```xml
<PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
```

## <a name="arguments"></a><span data-ttu-id="1c520-114">Argumente</span><span class="sxs-lookup"><span data-stu-id="1c520-114">Arguments</span></span>

`PROJECT`

<span data-ttu-id="1c520-115">Gibt die Projektdatei an.</span><span class="sxs-lookup"><span data-stu-id="1c520-115">Specifies the project file.</span></span> <span data-ttu-id="1c520-116">Wenn keine angegeben ist, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="1c520-116">If not specified, the command searches the current directory for one.</span></span>

`PACKAGE_NAME`

<span data-ttu-id="1c520-117">Hinzuzufügender Paketverweis.</span><span class="sxs-lookup"><span data-stu-id="1c520-117">The package reference to add.</span></span>

## <a name="options"></a><span data-ttu-id="1c520-118">Optionen</span><span class="sxs-lookup"><span data-stu-id="1c520-118">Options</span></span>

`-h|--help`

<span data-ttu-id="1c520-119">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="1c520-119">Prints out a short help for the command.</span></span>

`-v|--version <VERSION>`

<span data-ttu-id="1c520-120">Die Version des Pakets.</span><span class="sxs-lookup"><span data-stu-id="1c520-120">Version of the package.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="1c520-121">Fügt Paketverweise nur hinzu, wenn ein bestimmtes [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="1c520-121">Adds a package reference only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

`-n|--no-restore`

<span data-ttu-id="1c520-122">Fügt Paketverweise hinzu, ohne eine Vorschau der Wiederherstellung und eine Kompatibilitätsüberprüfung durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="1c520-122">Adds a package reference without performing a restore preview and compatibility check.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="1c520-123">Verwendet während des Wiederherstellungsvorgangs eine bestimmte NuGet-Paketquelle.</span><span class="sxs-lookup"><span data-stu-id="1c520-123">Uses a specific NuGet package source during the restore operation.</span></span>

`--package-directory <PACKAGE_DIRECTORY>`

<span data-ttu-id="1c520-124">Stellt das Paket im angegebenen Verzeichnis wieder her.</span><span class="sxs-lookup"><span data-stu-id="1c520-124">Restores the package to the specified directory.</span></span>

## <a name="examples"></a><span data-ttu-id="1c520-125">Beispiele</span><span class="sxs-lookup"><span data-stu-id="1c520-125">Examples</span></span>

<span data-ttu-id="1c520-126">Fügen Sie das `Newtonsoft.Json`-NuGet-Pakets zu einem Projekt hinzu:</span><span class="sxs-lookup"><span data-stu-id="1c520-126">Add `Newtonsoft.Json` NuGet package to a project:</span></span>

`dotnet add package Newtonsoft.Json`

<span data-ttu-id="1c520-127">Fügen Sie eine bestimmte Version eines Pakets zu einem Projekt hinzu:</span><span class="sxs-lookup"><span data-stu-id="1c520-127">Add a specific version of a package to a project:</span></span>

`dotnet add ToDo.csproj package Microsoft.Azure.DocumentDB.Core -v 1.0.0`

<span data-ttu-id="1c520-128">Fügen Sie ein Paket mit einer bestimmten NuGet-Quelle hinzu:</span><span class="sxs-lookup"><span data-stu-id="1c520-128">Add a package using a specific NuGet source:</span></span>

`dotnet add package Microsoft.AspNetCore.StaticFiles -s https://dotnet.myget.org/F/dotnet-core/api/v3/index.json`

