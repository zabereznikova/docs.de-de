---
title: dotnet add reference-Befehl
description: Der dotnet add-Verweisbefehl bietet eine praktische Option zum Hinzufügen von Projekt-zu-Projekt-Verweisen.
ms.date: 06/26/2019
ms.openlocfilehash: c97975e11410cfaad18ca68832957d75a4a2fd09
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73100816"
---
# <a name="dotnet-add-reference"></a><span data-ttu-id="e89cc-103">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="e89cc-103">dotnet add reference</span></span>

<span data-ttu-id="e89cc-104">**Dieser Artikel gilt für: ✓**.NET Core 1.x SDK und spätere Versionen</span><span class="sxs-lookup"><span data-stu-id="e89cc-104">**This article applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="e89cc-105">name</span><span class="sxs-lookup"><span data-stu-id="e89cc-105">Name</span></span>

<span data-ttu-id="e89cc-106">`dotnet add reference`: Fügt Projekt-zu-Projekt (P2P)-Verweise hinzu.</span><span class="sxs-lookup"><span data-stu-id="e89cc-106">`dotnet add reference` - Adds project-to-project (P2P) references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="e89cc-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="e89cc-107">Synopsis</span></span>

`dotnet add [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help] [--interactive]`

## <a name="description"></a><span data-ttu-id="e89cc-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e89cc-108">Description</span></span>

<span data-ttu-id="e89cc-109">Der `dotnet add reference`-Befehl bietet eine praktische Option zum Hinzufügen von Projektverweisen auf ein Projekt.</span><span class="sxs-lookup"><span data-stu-id="e89cc-109">The `dotnet add reference` command provides a convenient option to add project references to a project.</span></span> <span data-ttu-id="e89cc-110">Nachdem Sie den Befehl ausgeführt haben, werden die `<ProjectReference>`-Elemente zur Projektdatei hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e89cc-110">After running the command, the `<ProjectReference>` elements are added to the project file.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a><span data-ttu-id="e89cc-111">Argumente</span><span class="sxs-lookup"><span data-stu-id="e89cc-111">Arguments</span></span>

- **`PROJECT`**

  <span data-ttu-id="e89cc-112">Gibt die Projektdatei an.</span><span class="sxs-lookup"><span data-stu-id="e89cc-112">Specifies the project file.</span></span> <span data-ttu-id="e89cc-113">Wenn keine angegeben ist, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="e89cc-113">If not specified, the command searches the current directory for one.</span></span>

- **`PROJECT_REFERENCES`**

  <span data-ttu-id="e89cc-114">Hinzuzufügende Projekt-zu-Projekt (P2P)-Verweise.</span><span class="sxs-lookup"><span data-stu-id="e89cc-114">Project-to-project (P2P) references to add.</span></span> <span data-ttu-id="e89cc-115">Geben Sie ein oder mehrere Projekte an.</span><span class="sxs-lookup"><span data-stu-id="e89cc-115">Specify one or more projects.</span></span> <span data-ttu-id="e89cc-116">[Globmuster](https://en.wikipedia.org/wiki/Glob_(programming)) werden auf Unix/Linux-basierten Systemen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e89cc-116">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux-based systems.</span></span>

## <a name="options"></a><span data-ttu-id="e89cc-117">Optionen</span><span class="sxs-lookup"><span data-stu-id="e89cc-117">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="e89cc-118">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="e89cc-118">Prints out a short help for the command.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e89cc-119">Fügt Projektverweise nur hinzu, wenn auf ein bestimmtes [Framework](../../standard/frameworks.md) abgezielt wird.</span><span class="sxs-lookup"><span data-stu-id="e89cc-119">Adds project references only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

- **`--interactive`**

  <span data-ttu-id="e89cc-120">Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten (z.B. um die Authentifizierung abzuschließen).</span><span class="sxs-lookup"><span data-stu-id="e89cc-120">Allows the command to stop and wait for user input or action (for example, to complete authentication).</span></span> <span data-ttu-id="e89cc-121">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="e89cc-121">Available since .NET Core 3.0 SDK.</span></span>

## <a name="examples"></a><span data-ttu-id="e89cc-122">Beispiele</span><span class="sxs-lookup"><span data-stu-id="e89cc-122">Examples</span></span>

- <span data-ttu-id="e89cc-123">Projektverweis hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="e89cc-123">Add a project reference:</span></span>

  ```dotnetcli
  dotnet add app/app.csproj reference lib/lib.csproj
  ```

- <span data-ttu-id="e89cc-124">Fügen Sie dem Projekt im aktuellen Verzeichnis mehrere Projektverweise hinzu:</span><span class="sxs-lookup"><span data-stu-id="e89cc-124">Add multiple project references to the project in the current directory:</span></span>

  ```dotnetcli
  dotnet add reference lib1/lib1.csproj lib2/lib2.csproj
  ```

- <span data-ttu-id="e89cc-125">Mehrere Projektverweise mithilfe eines Globmusters unter Linux/Unix hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="e89cc-125">Add multiple project references using a globbing pattern on Linux/Unix:</span></span>

  ```dotnetcli
  dotnet add app/app.csproj reference **/*.csproj
  ```
