---
title: Befehl „dotnet list reference“
description: Der Verweisbefehl „dotnet-list“ bietet eine praktische Option zum Listen von Verweisen zwischen Projekten.
ms.date: 06/26/2019
ms.openlocfilehash: b4b82ca1e7aeb2b73d9f99aff1c97452b2166770
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117671"
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="1b58a-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="1b58a-103">dotnet list reference</span></span>

<span data-ttu-id="1b58a-104">**Dieses Thema gilt für: ✓**.NET Core 1.x SDK und spätere Versionen</span><span class="sxs-lookup"><span data-stu-id="1b58a-104">**This topic applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="1b58a-105">NAME</span><span class="sxs-lookup"><span data-stu-id="1b58a-105">Name</span></span>

<span data-ttu-id="1b58a-106">`dotnet list reference`: Listet Projekt-zu-Projekt-Verweise auf.</span><span class="sxs-lookup"><span data-stu-id="1b58a-106">`dotnet list reference` - Lists project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="1b58a-107">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="1b58a-107">Synopsis</span></span>

`dotnet list [<PROJECT>|<SOLUTION>] reference [-h|--help]`

## <a name="description"></a><span data-ttu-id="1b58a-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1b58a-108">Description</span></span>

<span data-ttu-id="1b58a-109">Der `dotnet list reference`-Befehl bietet eine praktische Option zum Listen von Projektverweisen auf ein bestimmtes Projekt oder eine Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="1b58a-109">The `dotnet list reference` command provides a convenient option to list project references for a given project or solution.</span></span>

## <a name="arguments"></a><span data-ttu-id="1b58a-110">Argumente</span><span class="sxs-lookup"><span data-stu-id="1b58a-110">Arguments</span></span>

* **`PROJECT | SOLUTION`**

  <span data-ttu-id="1b58a-111">Gibt die Projekt- oder Projektmappendatei an, die für die Auflistung von Verweisen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="1b58a-111">Specifies the project or solution file to use for listing references.</span></span> <span data-ttu-id="1b58a-112">Ist dieses Argument nicht angegeben, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="1b58a-112">If not specified, the command searches the current directory for a project file.</span></span>

## <a name="options"></a><span data-ttu-id="1b58a-113">Optionen</span><span class="sxs-lookup"><span data-stu-id="1b58a-113">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="1b58a-114">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="1b58a-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="1b58a-115">Beispiele</span><span class="sxs-lookup"><span data-stu-id="1b58a-115">Examples</span></span>

* <span data-ttu-id="1b58a-116">Listen Sie die Projektverweise für das angegebene Projekt:</span><span class="sxs-lookup"><span data-stu-id="1b58a-116">List the project references for the specified project:</span></span>

  ```dotnetcli
  dotnet list app/app.csproj reference
  ```

* <span data-ttu-id="1b58a-117">Listen Sie die Projektverweise für das Projekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="1b58a-117">List the project references for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet list reference
  ```
