---
title: Befehl „dotnet list reference“
description: Der Verweisbefehl „dotnet-list“ bietet eine praktische Option zum Listen von Verweisen zwischen Projekten.
ms.date: 02/14/2020
ms.openlocfilehash: b9b34c17102c6218f3d99f6e2620e99f70140284
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83802762"
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="1591d-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="1591d-103">dotnet list reference</span></span>

<span data-ttu-id="1591d-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.x SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="1591d-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="1591d-105">name</span><span class="sxs-lookup"><span data-stu-id="1591d-105">Name</span></span>

<span data-ttu-id="1591d-106">`dotnet list reference`: Listet Projekt-zu-Projekt-Verweise auf.</span><span class="sxs-lookup"><span data-stu-id="1591d-106">`dotnet list reference` - Lists project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="1591d-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="1591d-107">Synopsis</span></span>

```dotnetcli
dotnet list [<PROJECT>] reference

dotnet list -h|--help
```

## <a name="description"></a><span data-ttu-id="1591d-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1591d-108">Description</span></span>

<span data-ttu-id="1591d-109">Der `dotnet list reference`-Befehl bietet eine praktische Option zum Listen von Projektverweisen auf ein bestimmtes Projekt.</span><span class="sxs-lookup"><span data-stu-id="1591d-109">The `dotnet list reference` command provides a convenient option to list project references for a given project.</span></span>

## <a name="arguments"></a><span data-ttu-id="1591d-110">Argumente</span><span class="sxs-lookup"><span data-stu-id="1591d-110">Arguments</span></span>

* **`PROJECT`**

  <span data-ttu-id="1591d-111">Auszuführende Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="1591d-111">The project file to operate on.</span></span> <span data-ttu-id="1591d-112">Wenn keine Datei angegeben wird, sucht der Befehl im aktuellen Verzeichnis danach.</span><span class="sxs-lookup"><span data-stu-id="1591d-112">If a file is not specified, the command will search the current directory for one.</span></span>

## <a name="options"></a><span data-ttu-id="1591d-113">Optionen</span><span class="sxs-lookup"><span data-stu-id="1591d-113">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="1591d-114">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="1591d-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="1591d-115">Beispiele</span><span class="sxs-lookup"><span data-stu-id="1591d-115">Examples</span></span>

* <span data-ttu-id="1591d-116">Listen Sie die Projektverweise für das angegebene Projekt:</span><span class="sxs-lookup"><span data-stu-id="1591d-116">List the project references for the specified project:</span></span>

  ```dotnetcli
  dotnet list app/app.csproj reference
  ```

* <span data-ttu-id="1591d-117">Listen Sie die Projektverweise für das Projekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="1591d-117">List the project references for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet list reference
  ```
