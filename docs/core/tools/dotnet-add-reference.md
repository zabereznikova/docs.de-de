---
title: Verweisbefehl „dotnet-add“ – .NET Core-CLI
description: Der dotnet add-Verweisbefehl bietet eine praktische Option zum Hinzufügen von Projekt-zu-Projekt-Verweisen.
author: mairaw
ms.author: mairaw
ms.date: 09/19/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: c82696eee2fbe4bbad86e59cf5de1c2e74d048f6
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-add-reference"></a><span data-ttu-id="064e3-103">dotnet-add-Verweis</span><span class="sxs-lookup"><span data-stu-id="064e3-103">dotnet-add reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="064e3-104">name</span><span class="sxs-lookup"><span data-stu-id="064e3-104">Name</span></span>

<span data-ttu-id="064e3-105">`dotnet add reference`: Fügt Projekt-zu-Projekt (P2P)-Verweise hinzu.</span><span class="sxs-lookup"><span data-stu-id="064e3-105">`dotnet add reference` - Adds project-to-project (P2P) references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="064e3-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="064e3-106">Synopsis</span></span>

`dotnet add [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a><span data-ttu-id="064e3-107">description</span><span class="sxs-lookup"><span data-stu-id="064e3-107">Description</span></span>

<span data-ttu-id="064e3-108">Der `dotnet add reference`-Befehl bietet eine praktische Option zum Hinzufügen von Projektverweisen auf ein Projekt.</span><span class="sxs-lookup"><span data-stu-id="064e3-108">The `dotnet add reference` command provides a convenient option to add project references to a project.</span></span> <span data-ttu-id="064e3-109">Nach dem Ausführen des Befehls werden die [`<ProjectReference>`](/visualstudio/msbuild/common-msbuild-project-items)-Elemente zur Projektdatei hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="064e3-109">After running the command, the [`<ProjectReference>`](/visualstudio/msbuild/common-msbuild-project-items) elements are added to the project file.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a><span data-ttu-id="064e3-110">Argumente</span><span class="sxs-lookup"><span data-stu-id="064e3-110">Arguments</span></span>

`PROJECT`

<span data-ttu-id="064e3-111">Gibt die Projektdatei an.</span><span class="sxs-lookup"><span data-stu-id="064e3-111">Specifies the project file.</span></span> <span data-ttu-id="064e3-112">Wenn keine angegeben ist, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="064e3-112">If not specified, the command searches the current directory for one.</span></span>

`PROJECT_REFERENCES`

<span data-ttu-id="064e3-113">Hinzuzufügende Projekt-zu-Projekt (P2P)-Verweise.</span><span class="sxs-lookup"><span data-stu-id="064e3-113">Project-to-project (P2P) references to add.</span></span> <span data-ttu-id="064e3-114">Geben Sie ein oder mehrere Projekte an.</span><span class="sxs-lookup"><span data-stu-id="064e3-114">Specify one or more projects.</span></span> <span data-ttu-id="064e3-115">[Globmuster](https://en.wikipedia.org/wiki/Glob_(programming)) werden auf Unix/Linux-basierten Systemen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="064e3-115">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux-based systems.</span></span>

## <a name="options"></a><span data-ttu-id="064e3-116">Optionen</span><span class="sxs-lookup"><span data-stu-id="064e3-116">Options</span></span>

`-h|--help`

<span data-ttu-id="064e3-117">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="064e3-117">Prints out a short help for the command.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="064e3-118">Fügt Projektverweise nur hinzu, wenn auf ein bestimmtes [Framework](../../standard/frameworks.md) abgezielt wird.</span><span class="sxs-lookup"><span data-stu-id="064e3-118">Adds project references only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

## <a name="examples"></a><span data-ttu-id="064e3-119">Beispiele</span><span class="sxs-lookup"><span data-stu-id="064e3-119">Examples</span></span>

<span data-ttu-id="064e3-120">Projektverweis hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="064e3-120">Add a project reference:</span></span>

`dotnet add app/app.csproj reference lib/lib.csproj`

<span data-ttu-id="064e3-121">Fügen Sie dem Projekt im aktuellen Verzeichnis mehrere Projektverweise hinzu:</span><span class="sxs-lookup"><span data-stu-id="064e3-121">Add multiple project references to the project in the current directory:</span></span>

`dotnet add reference lib1/lib1.csproj lib2/lib2.csproj`

<span data-ttu-id="064e3-122">Mehrere Projektverweise mithilfe eines Globmusters unter Linux/Unix hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="064e3-122">Add multiple project references using a globbing pattern on Linux/Unix:</span></span>

`dotnet add app/app.csproj reference **/*.csproj`
