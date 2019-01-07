---
title: Befehl „dotnet list reference“
description: Der Befehl „dotnet list reference“ bietet eine praktische Option zum Listen von Verweisen zwischen Projekten.
ms.date: 12/03/2018
ms.openlocfilehash: d22ea27f8e8f6b94d763e44a6d8644f814663797
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53169832"
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="35a35-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="35a35-103">dotnet list reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="35a35-104">Name</span><span class="sxs-lookup"><span data-stu-id="35a35-104">Name</span></span>

<span data-ttu-id="35a35-105">`dotnet list reference`: Listet Projekt-zu-Projekt-Verweise auf.</span><span class="sxs-lookup"><span data-stu-id="35a35-105">`dotnet list reference` - Lists project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="35a35-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="35a35-106">Synopsis</span></span>

`dotnet list [<PROJECT>] reference [-h|--help]`

## <a name="description"></a><span data-ttu-id="35a35-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="35a35-107">Description</span></span>

<span data-ttu-id="35a35-108">Der `dotnet list reference`-Befehl bietet eine praktische Option zum Listen von Projektverweisen auf ein bestimmtes Projekt oder eine Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="35a35-108">The `dotnet list reference` command provides a convenient option to list project references for a given project or solution.</span></span>

## <a name="arguments"></a><span data-ttu-id="35a35-109">Argumente</span><span class="sxs-lookup"><span data-stu-id="35a35-109">Arguments</span></span>

* **`PROJECT`**

  <span data-ttu-id="35a35-110">Gibt die Projektdatei an, die für die Auflistung von Verweisen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="35a35-110">Specifies the project file to use for listing references.</span></span> <span data-ttu-id="35a35-111">Ist dieses Argument nicht angegeben, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="35a35-111">If not specified, the command searches the current directory for a project file.</span></span>

## <a name="options"></a><span data-ttu-id="35a35-112">Optionen</span><span class="sxs-lookup"><span data-stu-id="35a35-112">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="35a35-113">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="35a35-113">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="35a35-114">Beispiele</span><span class="sxs-lookup"><span data-stu-id="35a35-114">Examples</span></span>

* <span data-ttu-id="35a35-115">Listen Sie die Projektverweise für das angegebene Projekt:</span><span class="sxs-lookup"><span data-stu-id="35a35-115">List the project references for the specified project:</span></span>

  ```console
  dotnet list app/app.csproj reference
  ```

* <span data-ttu-id="35a35-116">Listen Sie die Projektverweise für das Projekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="35a35-116">List the project references for the project in the current directory:</span></span>

  ```console
  dotnet list reference
  ```