---
title: Befehl „dotnet remove reference“
description: Der Befehl „dotnet remove reference“ bietet eine praktische Option zum Entfernen von Projekt-zu-Projekt-Verweisen.
ms.date: 05/29/2018
ms.openlocfilehash: bfac4721743babcf48fd8e86a50c8df136e1bfce
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53170612"
---
# <a name="dotnet-remove-reference"></a><span data-ttu-id="709f7-103">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="709f7-103">dotnet remove reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="709f7-104">Name</span><span class="sxs-lookup"><span data-stu-id="709f7-104">Name</span></span>

<span data-ttu-id="709f7-105">`dotnet remove reference`: Entfernt Projekt-zu-Projekt-Verweise.</span><span class="sxs-lookup"><span data-stu-id="709f7-105">`dotnet remove reference` - Removes project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="709f7-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="709f7-106">Synopsis</span></span>

`dotnet remove [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a><span data-ttu-id="709f7-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="709f7-107">Description</span></span>

<span data-ttu-id="709f7-108">Der `dotnet remove reference`-Befehl bietet eine praktische Option zum Entfernen von Projektverweisen von einem Projekt.</span><span class="sxs-lookup"><span data-stu-id="709f7-108">The `dotnet remove reference` command provides a convenient option to remove project references from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="709f7-109">Argumente</span><span class="sxs-lookup"><span data-stu-id="709f7-109">Arguments</span></span>

`PROJECT`

<span data-ttu-id="709f7-110">Zielprojektdatei.</span><span class="sxs-lookup"><span data-stu-id="709f7-110">Target project file.</span></span> <span data-ttu-id="709f7-111">Wenn keine angegeben ist, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="709f7-111">If not specified, the command searches the current directory for one.</span></span>

`PROJECT_REFERENCES`

<span data-ttu-id="709f7-112">Zu entfernende Projekt-zu-Projekt-Verweise (P2P).</span><span class="sxs-lookup"><span data-stu-id="709f7-112">Project-to-project (P2P) references to remove.</span></span> <span data-ttu-id="709f7-113">Sie können ein oder mehrere Projekte angeben.</span><span class="sxs-lookup"><span data-stu-id="709f7-113">You can specify one or multiple projects.</span></span> <span data-ttu-id="709f7-114">[Globmuster](https://en.wikipedia.org/wiki/Glob_(programming)) werden auf Unix/Linux-basierten Terminals unterstützt.</span><span class="sxs-lookup"><span data-stu-id="709f7-114">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

## <a name="options"></a><span data-ttu-id="709f7-115">Optionen</span><span class="sxs-lookup"><span data-stu-id="709f7-115">Options</span></span>

`-h|--help`

<span data-ttu-id="709f7-116">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="709f7-116">Prints out a short help for the command.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="709f7-117">Entfernt den Verweis nur, wenn auf ein bestimmtes [Framework](../../standard/frameworks.md) abgezielt wird.</span><span class="sxs-lookup"><span data-stu-id="709f7-117">Removes the reference only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

## <a name="examples"></a><span data-ttu-id="709f7-118">Beispiele</span><span class="sxs-lookup"><span data-stu-id="709f7-118">Examples</span></span>

<span data-ttu-id="709f7-119">Entfernen Sie einen Projektverweis aus dem angegebenen Projekt:</span><span class="sxs-lookup"><span data-stu-id="709f7-119">Remove a project reference from the specified project:</span></span>

`dotnet remove app/app.csproj reference lib/lib.csproj`

<span data-ttu-id="709f7-120">Entfernen Sie mehrere Projektverweise aus dem Projekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="709f7-120">Remove multiple project references from the project in the current directory:</span></span>

`dotnet remove reference lib1/lib1.csproj lib2/lib2.csproj`

<span data-ttu-id="709f7-121">Entfernen Sie mehrere Projektverweise mithilfe eines Globmusters auf Unix/Linux:</span><span class="sxs-lookup"><span data-stu-id="709f7-121">Remove multiple project references using a glob pattern on Unix/Linux:</span></span>

`dotnet remove app/app.csproj reference **/*.csproj`
