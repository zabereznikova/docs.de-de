---
title: Befehl „dotnet list reference“
description: Der Verweisbefehl „dotnet-list“ bietet eine praktische Option zum Listen von Verweisen zwischen Projekten.
ms.date: 02/14/2020
ms.openlocfilehash: 43c4dbc94b33e717c6ba0a1c1c5317ac006f5bba
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503717"
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="c2b39-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="c2b39-103">dotnet list reference</span></span>

<span data-ttu-id="c2b39-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.x SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="c2b39-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="c2b39-105">name</span><span class="sxs-lookup"><span data-stu-id="c2b39-105">Name</span></span>

<span data-ttu-id="c2b39-106">`dotnet list reference`: Listet Projekt-zu-Projekt-Verweise auf.</span><span class="sxs-lookup"><span data-stu-id="c2b39-106">`dotnet list reference` - Lists project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c2b39-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="c2b39-107">Synopsis</span></span>

`dotnet list [<PROJECT>|<SOLUTION>] reference [-h|--help]`

## <a name="description"></a><span data-ttu-id="c2b39-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c2b39-108">Description</span></span>

<span data-ttu-id="c2b39-109">Der `dotnet list reference`-Befehl bietet eine praktische Option zum Listen von Projektverweisen auf ein bestimmtes Projekt oder eine Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="c2b39-109">The `dotnet list reference` command provides a convenient option to list project references for a given project or solution.</span></span>

## <a name="arguments"></a><span data-ttu-id="c2b39-110">Argumente</span><span class="sxs-lookup"><span data-stu-id="c2b39-110">Arguments</span></span>

* **`PROJECT | SOLUTION`**

  <span data-ttu-id="c2b39-111">Gibt die Projekt- oder Projektmappendatei an, die für die Auflistung von Verweisen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c2b39-111">Specifies the project or solution file to use for listing references.</span></span> <span data-ttu-id="c2b39-112">Ist dieses Argument nicht angegeben, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="c2b39-112">If not specified, the command searches the current directory for a project file.</span></span>

## <a name="options"></a><span data-ttu-id="c2b39-113">Optionen</span><span class="sxs-lookup"><span data-stu-id="c2b39-113">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="c2b39-114">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="c2b39-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="c2b39-115">Beispiele</span><span class="sxs-lookup"><span data-stu-id="c2b39-115">Examples</span></span>

* <span data-ttu-id="c2b39-116">Listen Sie die Projektverweise für das angegebene Projekt:</span><span class="sxs-lookup"><span data-stu-id="c2b39-116">List the project references for the specified project:</span></span>

  ```dotnetcli
  dotnet list app/app.csproj reference
  ```

* <span data-ttu-id="c2b39-117">Listen Sie die Projektverweise für das Projekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="c2b39-117">List the project references for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet list reference
  ```
