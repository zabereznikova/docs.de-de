---
title: Verweisbefehl „dotnet remove“ – .NET Core-CLI
description: Der Verweisbefehl „dotnet remove“ bietet eine praktische Option zum Entfernen von Projekt-zu-Projekt-Verweisen.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: b281b255be7f49a99a6b4928c340cd4fb085f085
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34696230"
---
# <a name="dotnet-remove-reference"></a><span data-ttu-id="135e1-103">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="135e1-103">dotnet remove reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="135e1-104">name</span><span class="sxs-lookup"><span data-stu-id="135e1-104">Name</span></span>

<span data-ttu-id="135e1-105">`dotnet remove reference`: Entfernt Projekt-zu-Projekt-Verweise.</span><span class="sxs-lookup"><span data-stu-id="135e1-105">`dotnet remove reference` - Removes project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="135e1-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="135e1-106">Synopsis</span></span>

`dotnet remove [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a><span data-ttu-id="135e1-107">description</span><span class="sxs-lookup"><span data-stu-id="135e1-107">Description</span></span>

<span data-ttu-id="135e1-108">Der `dotnet remove reference`-Befehl bietet eine praktische Option zum Entfernen von Projektverweisen von einem Projekt.</span><span class="sxs-lookup"><span data-stu-id="135e1-108">The `dotnet remove reference` command provides a convenient option to remove project references from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="135e1-109">Argumente</span><span class="sxs-lookup"><span data-stu-id="135e1-109">Arguments</span></span>

`PROJECT`

<span data-ttu-id="135e1-110">Zielprojektdatei.</span><span class="sxs-lookup"><span data-stu-id="135e1-110">Target project file.</span></span> <span data-ttu-id="135e1-111">Wenn keine angegeben ist, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="135e1-111">If not specified, the command searches the current directory for one.</span></span>

`PROJECT_REFERENCES`

<span data-ttu-id="135e1-112">Zu entfernende Projekt-zu-Projekt-Verweise (P2P).</span><span class="sxs-lookup"><span data-stu-id="135e1-112">Project-to-project (P2P) references to remove.</span></span> <span data-ttu-id="135e1-113">Sie können ein oder mehrere Projekte angeben.</span><span class="sxs-lookup"><span data-stu-id="135e1-113">You can specify one or multiple projects.</span></span> <span data-ttu-id="135e1-114">[Globmuster](https://en.wikipedia.org/wiki/Glob_(programming)) werden auf Unix/Linux-basierten Terminals unterstützt.</span><span class="sxs-lookup"><span data-stu-id="135e1-114">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

## <a name="options"></a><span data-ttu-id="135e1-115">Optionen</span><span class="sxs-lookup"><span data-stu-id="135e1-115">Options</span></span>

`-h|--help`

<span data-ttu-id="135e1-116">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="135e1-116">Prints out a short help for the command.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="135e1-117">Entfernt den Verweis nur, wenn auf ein bestimmtes [Framework](../../standard/frameworks.md) abgezielt wird.</span><span class="sxs-lookup"><span data-stu-id="135e1-117">Removes the reference only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

## <a name="examples"></a><span data-ttu-id="135e1-118">Beispiele</span><span class="sxs-lookup"><span data-stu-id="135e1-118">Examples</span></span>

<span data-ttu-id="135e1-119">Entfernen Sie einen Projektverweis aus dem angegebenen Projekt:</span><span class="sxs-lookup"><span data-stu-id="135e1-119">Remove a project reference from the specified project:</span></span>

`dotnet remove app/app.csproj reference lib/lib.csproj`

<span data-ttu-id="135e1-120">Entfernen Sie mehrere Projektverweise aus dem Projekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="135e1-120">Remove multiple project references from the project in the current directory:</span></span>

`dotnet remove reference lib1/lib1.csproj lib2/lib2.csproj`

<span data-ttu-id="135e1-121">Entfernen Sie mehrere Projektverweise mithilfe eines Globmusters auf Unix/Linux:</span><span class="sxs-lookup"><span data-stu-id="135e1-121">Remove multiple project references using a glob pattern on Unix/Linux:</span></span>

`dotnet remove app/app.csproj reference **/*.csproj`
