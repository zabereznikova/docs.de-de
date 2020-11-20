---
title: Befehl „dotnet tool search“
description: Der Befehl „dotnet tool search“ durchsucht die .NET-Tools, die auf NuGet.org veröffentlicht wurden.
ms.date: 11/11/2020
ms.openlocfilehash: e0289e651ec4a439c791c8c948bef2d85d9c3794
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634141"
---
# <a name="dotnet-tool-search"></a><span data-ttu-id="f6c16-103">dotnet tool search</span><span class="sxs-lookup"><span data-stu-id="f6c16-103">dotnet tool search</span></span>

<span data-ttu-id="f6c16-104">**Dieser Artikel gilt für:** ✔️ .NET 5.0 SDK und höhere Versionen</span><span class="sxs-lookup"><span data-stu-id="f6c16-104">**This article applies to:** ✔️ .NET 5.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="f6c16-105">Name</span><span class="sxs-lookup"><span data-stu-id="f6c16-105">Name</span></span>

<span data-ttu-id="f6c16-106">`dotnet tool search`: Der Befehl durchsucht alle [.NET-Tools](global-tools.md), die auf NuGet veröffentlicht wurden.</span><span class="sxs-lookup"><span data-stu-id="f6c16-106">`dotnet tool search` - Searches all [.NET tools](global-tools.md) that are published to NuGet.</span></span>

## <a name="synopsis"></a><span data-ttu-id="f6c16-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="f6c16-107">Synopsis</span></span>

```dotnetcli
dotnet tool search [--detail]  [--prerelease]
    [--skip <NUMBER>] [--take <NUMBER>] <SEARCH TERM>

dotnet tool search -h|--help
```

## <a name="description"></a><span data-ttu-id="f6c16-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f6c16-108">Description</span></span>

<span data-ttu-id="f6c16-109">Der Befehl `dotnet tool search` bietet Ihnen die Möglichkeit, NuGet nach Tools zu durchsuchen, die als globale, tool-path- oder lokale .NET-Tools verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="f6c16-109">The `dotnet tool search` command provides a way for you to search NuGet for tools that can be used as .NET global, tool-path, or local tools.</span></span> <span data-ttu-id="f6c16-110">Der Befehl durchsucht die Toolnamen und Metadaten, z. B. Titel, Beschreibungen und Tags.</span><span class="sxs-lookup"><span data-stu-id="f6c16-110">The command searches the tool names and metadata such as titles, descriptions, and tags.</span></span>

<span data-ttu-id="f6c16-111">Der Befehl verwendet die [NuGet-Such-API](/nuget/api/search-query-service-resource#search-for-packages).</span><span class="sxs-lookup"><span data-stu-id="f6c16-111">The command uses the [NuGet Search API](/nuget/api/search-query-service-resource#search-for-packages).</span></span> <span data-ttu-id="f6c16-112">Er filtert nach `packageType=dotnettool`, um nur .NET-Toolpakete auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="f6c16-112">It filters on `packageType=dotnettool` to select only .NET tool packages.</span></span>

## <a name="options"></a><span data-ttu-id="f6c16-113">Optionen</span><span class="sxs-lookup"><span data-stu-id="f6c16-113">Options</span></span>

- **`--detail`**

  <span data-ttu-id="f6c16-114">Zeigt detaillierte Ergebnisse der Abfrage an</span><span class="sxs-lookup"><span data-stu-id="f6c16-114">Shows detailed results from the query.</span></span>

- **`--prerelease`**

  <span data-ttu-id="f6c16-115">Enthält Vorabversionen von Paketen</span><span class="sxs-lookup"><span data-stu-id="f6c16-115">Includes pre-release packages.</span></span>

- **`--skip <NUMBER>`**

  <span data-ttu-id="f6c16-116">Gibt die Anzahl der zu überspringenden Abfrageergebnisse an</span><span class="sxs-lookup"><span data-stu-id="f6c16-116">Specifies the number of query results to skip.</span></span> <span data-ttu-id="f6c16-117">Wird für die Paginierung verwendet</span><span class="sxs-lookup"><span data-stu-id="f6c16-117">Used for pagination.</span></span>

- **`--take <NUMBER>`**

  <span data-ttu-id="f6c16-118">Gibt die Anzahl der anzuzeigenden Abfrageergebnisse an</span><span class="sxs-lookup"><span data-stu-id="f6c16-118">Specifies the number of query results to show.</span></span> <span data-ttu-id="f6c16-119">Wird für die Paginierung verwendet</span><span class="sxs-lookup"><span data-stu-id="f6c16-119">Used for pagination.</span></span>

- **`-h|--help`**

  <span data-ttu-id="f6c16-120">Zeigt die Hilfe für die Befehlszeile an.</span><span class="sxs-lookup"><span data-stu-id="f6c16-120">Shows command-line help.</span></span>

## <a name="examples"></a><span data-ttu-id="f6c16-121">Beispiele</span><span class="sxs-lookup"><span data-stu-id="f6c16-121">Examples</span></span>

- <span data-ttu-id="f6c16-122">Suchen Sie auf NuGet.org nach .NET-Tools, deren Paketname oder Beschreibung „format“ enthält:</span><span class="sxs-lookup"><span data-stu-id="f6c16-122">Search NuGet.org for .NET tools that have "format" in their package name or description:</span></span>

  ```dotnetcli
  dotnet tool search format
  ```

  <span data-ttu-id="f6c16-123">Die Ausgabe sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="f6c16-123">The output looks like the following example:</span></span>

  ```output
  Package ID                              Latest Version      Authors                                                                     Downloads      Verified
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------
  dotnet-format                           4.1.131201          Microsoft                                                                   496746
  bsoa.generator                          1.0.0               Microsoft                                                                   533
  ```

- <span data-ttu-id="f6c16-124">Suchen Sie NuGet.org nach .NET-Tools, deren Paketname oder Metadaten „format“ enthält, zeigen Sie nur das erste Ergebnis an, und rufen Sie eine detaillierte Ansicht auf.</span><span class="sxs-lookup"><span data-stu-id="f6c16-124">Search NuGet.org for .NET tools that have "format" in their package name or metadata, show only the first result, and show a detailed view.</span></span>

  ```dotnetcli
  dotnet tool search format --take 1 --detail
  ```

  <span data-ttu-id="f6c16-125">Die Ausgabe sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="f6c16-125">The output looks like the following example:</span></span>

  ```output
  ----------------
  dotnet-format
  Latest Version: 4.1.131201
  Authors: Microsoft
  Tags:
  Downloads: 496746
  Verified: False
  Description: Command line tool for formatting C# and Visual Basic code files based on .editorconfig settings.
  Versions:
          3.0.2 Downloads: 1973
          3.0.4 Downloads: 9064
          3.1.37601 Downloads: 114730
          3.2.107702 Downloads: 13423
          3.3.111304 Downloads: 131195
          4.0.130203 Downloads: 78610
          4.1.131201 Downloads: 145927
  ```

## <a name="see-also"></a><span data-ttu-id="f6c16-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f6c16-126">See also</span></span>

- [<span data-ttu-id="f6c16-127">.NET-Tools</span><span class="sxs-lookup"><span data-stu-id="f6c16-127">.NET tools</span></span>](global-tools.md)
- [<span data-ttu-id="f6c16-128">Tutorial: Installieren und Verwenden eines globalen .NET-Tools mithilfe der .NET-CLI</span><span class="sxs-lookup"><span data-stu-id="f6c16-128">Tutorial: Install and use a .NET global tool using the .NET CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="f6c16-129">Tutorial: Installieren und Verwenden eines lokalen .NET-Tools mithilfe der .NET-CLI</span><span class="sxs-lookup"><span data-stu-id="f6c16-129">Tutorial: Install and use a .NET local tool using the .NET CLI</span></span>](local-tools-how-to-use.md)
