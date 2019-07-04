---
title: Befehl „dotnet list reference“
description: Der Verweisbefehl „dotnet-list“ bietet eine praktische Option zum Listen von Verweisen zwischen Projekten.
ms.date: 06/26/2019
ms.openlocfilehash: 1f87ff89997cdaa6d0095a4db9f28a2e7cb7e6a9
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2019
ms.locfileid: "67421832"
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="5253d-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="5253d-103">dotnet list reference</span></span>

<span data-ttu-id="5253d-104">**Dieses Thema gilt für: ✓**.NET Core 1.x SDK und spätere Versionen</span><span class="sxs-lookup"><span data-stu-id="5253d-104">**This topic applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="5253d-105">name</span><span class="sxs-lookup"><span data-stu-id="5253d-105">Name</span></span>

<span data-ttu-id="5253d-106">`dotnet list reference`: Listet Projekt-zu-Projekt-Verweise auf.</span><span class="sxs-lookup"><span data-stu-id="5253d-106">`dotnet list reference` - Lists project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="5253d-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="5253d-107">Synopsis</span></span>

`dotnet list [<PROJECT>|<SOLUTION>] reference [-h|--help]`

## <a name="description"></a><span data-ttu-id="5253d-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5253d-108">Description</span></span>

<span data-ttu-id="5253d-109">Der `dotnet list reference`-Befehl bietet eine praktische Option zum Listen von Projektverweisen auf ein bestimmtes Projekt oder eine Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="5253d-109">The `dotnet list reference` command provides a convenient option to list project references for a given project or solution.</span></span>

## <a name="arguments"></a><span data-ttu-id="5253d-110">Argumente</span><span class="sxs-lookup"><span data-stu-id="5253d-110">Arguments</span></span>

* **`PROJECT | SOLUTION`**

  <span data-ttu-id="5253d-111">Gibt die Projekt- oder Projektmappendatei an, die für die Auflistung von Verweisen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5253d-111">Specifies the project or solution file to use for listing references.</span></span> <span data-ttu-id="5253d-112">Ist dieses Argument nicht angegeben, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="5253d-112">If not specified, the command searches the current directory for a project file.</span></span>

## <a name="options"></a><span data-ttu-id="5253d-113">Optionen</span><span class="sxs-lookup"><span data-stu-id="5253d-113">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="5253d-114">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="5253d-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="5253d-115">Beispiele</span><span class="sxs-lookup"><span data-stu-id="5253d-115">Examples</span></span>

* <span data-ttu-id="5253d-116">Listen Sie die Projektverweise für das angegebene Projekt:</span><span class="sxs-lookup"><span data-stu-id="5253d-116">List the project references for the specified project:</span></span>

  ```console
  dotnet list app/app.csproj reference
  ```

* <span data-ttu-id="5253d-117">Listen Sie die Projektverweise für das Projekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="5253d-117">List the project references for the project in the current directory:</span></span>

  ```console
  dotnet list reference
  ```
