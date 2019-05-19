---
title: Befehl „dotnet list reference“
description: Der Verweisbefehl „dotnet-list“ bietet eine praktische Option zum Listen von Verweisen zwischen Projekten.
ms.date: 12/03/2018
ms.openlocfilehash: c0b88c4a0af4469d7ddc9e0a9368bb1b2d9d20b6
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632412"
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="74a98-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="74a98-103">dotnet list reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="74a98-104">name</span><span class="sxs-lookup"><span data-stu-id="74a98-104">Name</span></span>

<span data-ttu-id="74a98-105">`dotnet list reference`: Listet Projekt-zu-Projekt-Verweise auf.</span><span class="sxs-lookup"><span data-stu-id="74a98-105">`dotnet list reference` - Lists project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="74a98-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="74a98-106">Synopsis</span></span>

`dotnet list [<PROJECT>] reference [-h|--help]`

## <a name="description"></a><span data-ttu-id="74a98-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="74a98-107">Description</span></span>

<span data-ttu-id="74a98-108">Der `dotnet list reference`-Befehl bietet eine praktische Option zum Listen von Projektverweisen auf ein bestimmtes Projekt oder eine Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="74a98-108">The `dotnet list reference` command provides a convenient option to list project references for a given project or solution.</span></span>

## <a name="arguments"></a><span data-ttu-id="74a98-109">Argumente</span><span class="sxs-lookup"><span data-stu-id="74a98-109">Arguments</span></span>

* **`PROJECT`**

  <span data-ttu-id="74a98-110">Gibt die Projektdatei an, die für die Auflistung von Verweisen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="74a98-110">Specifies the project file to use for listing references.</span></span> <span data-ttu-id="74a98-111">Ist dieses Argument nicht angegeben, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="74a98-111">If not specified, the command searches the current directory for a project file.</span></span>

## <a name="options"></a><span data-ttu-id="74a98-112">Optionen</span><span class="sxs-lookup"><span data-stu-id="74a98-112">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="74a98-113">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="74a98-113">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="74a98-114">Beispiele</span><span class="sxs-lookup"><span data-stu-id="74a98-114">Examples</span></span>

* <span data-ttu-id="74a98-115">Listen Sie die Projektverweise für das angegebene Projekt:</span><span class="sxs-lookup"><span data-stu-id="74a98-115">List the project references for the specified project:</span></span>

  ```console
  dotnet list app/app.csproj reference
  ```

* <span data-ttu-id="74a98-116">Listen Sie die Projektverweise für das Projekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="74a98-116">List the project references for the project in the current directory:</span></span>

  ```console
  dotnet list reference
  ```
