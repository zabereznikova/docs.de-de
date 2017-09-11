---
title: "Verweisbefehl „dotnet-add“ – .NET Core-CLI"
description: "Der dotnet-add-Verweisbefehl bietet eine praktische Option zum Hinzufügen von Projekt-zu-Projekt-Verweisen."
keywords: dotnet-add, CLI, CLI-Befehl, .NET Core
author: spboyer
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 5e2a3efd-443c-4f23-a1b1-a662a5387879
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 98491efc183ad62f47275d0832a32dde5899373d
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-add-reference"></a><span data-ttu-id="8466d-104">dotnet-add-Verweis</span><span class="sxs-lookup"><span data-stu-id="8466d-104">dotnet-add reference</span></span>

## <a name="name"></a><span data-ttu-id="8466d-105">Name</span><span class="sxs-lookup"><span data-stu-id="8466d-105">Name</span></span>

<span data-ttu-id="8466d-106">`dotnet-add reference`: Fügt Projekt-zu-Projekt (P2P)-Verweise hinzu.</span><span class="sxs-lookup"><span data-stu-id="8466d-106">`dotnet-add reference` - Adds project-to-project (P2P) references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="8466d-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="8466d-107">Synopsis</span></span>

`dotnet add [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a><span data-ttu-id="8466d-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8466d-108">Description</span></span>

<span data-ttu-id="8466d-109">Der `dotnet add reference`-Befehl bietet eine praktische Option zum Hinzufügen von Projektverweisen auf ein Projekt.</span><span class="sxs-lookup"><span data-stu-id="8466d-109">The `dotnet add reference` command provides a convenient option to add project references to a project.</span></span> <span data-ttu-id="8466d-110">Nach dem Ausführen des Befehls werden die [`<ProjectReference>`](/visualstudio/msbuild/common-msbuild-project-items)-Elemente zur Projektdatei hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="8466d-110">After running the command, the [`<ProjectReference>`](/visualstudio/msbuild/common-msbuild-project-items) elements are added to the project file.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a><span data-ttu-id="8466d-111">Argumente</span><span class="sxs-lookup"><span data-stu-id="8466d-111">Arguments</span></span>

`PROJECT`

<span data-ttu-id="8466d-112">Gibt die Projektdatei an.</span><span class="sxs-lookup"><span data-stu-id="8466d-112">Specifies the project file.</span></span> <span data-ttu-id="8466d-113">Ist dieses Argument nicht angegeben, sucht der Befehl im aktuellen Verzeichnis nach einer Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="8466d-113">If not specified, the command will search the current directory for one.</span></span>

`PROJECT_REFERENCES`

<span data-ttu-id="8466d-114">Hinzuzufügende Projekt-zu-Projekt (P2P)-Verweise.</span><span class="sxs-lookup"><span data-stu-id="8466d-114">Project-to-project (P2P) references to add.</span></span> <span data-ttu-id="8466d-115">Geben Sie ein oder mehrere Projekte an.</span><span class="sxs-lookup"><span data-stu-id="8466d-115">Specify one or more projects.</span></span> <span data-ttu-id="8466d-116">[Globmuster](https://en.wikipedia.org/wiki/Glob_(programming)) werden auf Unix/Linux-basierten Systemen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8466d-116">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux-based systems.</span></span>

## <a name="options"></a><span data-ttu-id="8466d-117">Optionen</span><span class="sxs-lookup"><span data-stu-id="8466d-117">Options</span></span>

`-h|--help`

<span data-ttu-id="8466d-118">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="8466d-118">Prints out a short help for the command.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="8466d-119">Fügt Projektverweise nur hinzu, wenn auf ein bestimmtes [Framework](../../standard/frameworks.md) abgezielt wird.</span><span class="sxs-lookup"><span data-stu-id="8466d-119">Adds project references only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

## <a name="examples"></a><span data-ttu-id="8466d-120">Beispiele</span><span class="sxs-lookup"><span data-stu-id="8466d-120">Examples</span></span>

<span data-ttu-id="8466d-121">Projektverweis hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="8466d-121">Add a project reference:</span></span>

`dotnet add app/app.csproj reference lib/lib.csproj`

<span data-ttu-id="8466d-122">Mehrere Projektverweise hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="8466d-122">Add multiple project references:</span></span>

`dotnet add reference lib1/lib1.csproj lib2/lib2.csproj`

<span data-ttu-id="8466d-123">Mehrere Projektverweise mithilfe eines Globmusters unter Linux/Unix hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="8466d-123">Add multiple project references using a globbing pattern on Linux/Unix:</span></span>

`dotnet add app/app.csproj reference **/*.csproj`

