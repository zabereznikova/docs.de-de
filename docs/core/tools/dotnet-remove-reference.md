---
title: Verweisbefehl „dotnet remove“ – .NET Core-CLI
description: Der Verweisbefehl „dotnet remove“ bietet eine praktische Option zum Entfernen von Projekt-zu-Projekt-Verweisen.
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.openlocfilehash: 209f1ad62221e8a80efa161354a2c074d74b7c5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="dotnet-remove-reference"></a><span data-ttu-id="98b83-103">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="98b83-103">dotnet remove reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="98b83-104">name</span><span class="sxs-lookup"><span data-stu-id="98b83-104">Name</span></span>

<span data-ttu-id="98b83-105">`dotnet remove reference`: Entfernt Projekt-zu-Projekt-Verweise.</span><span class="sxs-lookup"><span data-stu-id="98b83-105">`dotnet remove reference` - Removes project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="98b83-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="98b83-106">Synopsis</span></span>

`dotnet remove [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a><span data-ttu-id="98b83-107">description</span><span class="sxs-lookup"><span data-stu-id="98b83-107">Description</span></span>

<span data-ttu-id="98b83-108">Der `dotnet remove reference`-Befehl bietet eine praktische Option zum Entfernen von Projektverweisen von einem Projekt.</span><span class="sxs-lookup"><span data-stu-id="98b83-108">The `dotnet remove reference` command provides a convenient option to remove project references from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="98b83-109">Argumente</span><span class="sxs-lookup"><span data-stu-id="98b83-109">Arguments</span></span>

`PROJECT`

<span data-ttu-id="98b83-110">Zielprojektdatei.</span><span class="sxs-lookup"><span data-stu-id="98b83-110">Target project file.</span></span> <span data-ttu-id="98b83-111">Wenn keine angegeben ist, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="98b83-111">If not specified, the command searches the current directory for one.</span></span>

`PROJECT_REFERENCES`

<span data-ttu-id="98b83-112">Zu entfernende Projekt-zu-Projekt (P2P)-Verweise.</span><span class="sxs-lookup"><span data-stu-id="98b83-112">Project to project (P2P references to remove.</span></span> <span data-ttu-id="98b83-113">Sie können ein oder mehrere Projekte angeben.</span><span class="sxs-lookup"><span data-stu-id="98b83-113">You can specify one or multiple projects.</span></span> <span data-ttu-id="98b83-114">[Globmuster](https://en.wikipedia.org/wiki/Glob_(programming)) werden auf Unix/Linux-basierten Terminals unterstützt.</span><span class="sxs-lookup"><span data-stu-id="98b83-114">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

## <a name="options"></a><span data-ttu-id="98b83-115">Optionen</span><span class="sxs-lookup"><span data-stu-id="98b83-115">Options</span></span>

`-h|--help`

<span data-ttu-id="98b83-116">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="98b83-116">Prints out a short help for the command.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="98b83-117">Entfernt den Verweis nur, wenn auf ein bestimmtes [Framework](../../standard/frameworks.md) abgezielt wird.</span><span class="sxs-lookup"><span data-stu-id="98b83-117">Removes the reference only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

## <a name="examples"></a><span data-ttu-id="98b83-118">Beispiele</span><span class="sxs-lookup"><span data-stu-id="98b83-118">Examples</span></span>

<span data-ttu-id="98b83-119">Entfernen Sie einen Projektverweis aus dem angegebenen Projekt:</span><span class="sxs-lookup"><span data-stu-id="98b83-119">Remove a project reference from the specified project:</span></span>

`dotnet remove app/app.csproj reference lib/lib.csproj`

<span data-ttu-id="98b83-120">Entfernen Sie mehrere Projektverweise aus dem Projekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="98b83-120">Remove multiple project references from the project in the current directory:</span></span>

`dotnet remove reference lib1/lib1.csproj lib2/lib2.csproj`

<span data-ttu-id="98b83-121">Entfernen Sie mehrere Projektverweise mithilfe eines Globmusters auf Unix/Linux:</span><span class="sxs-lookup"><span data-stu-id="98b83-121">Remove multiple project references using a glob pattern on Unix/Linux:</span></span>

`dotnet remove app/app.csproj reference **/*.csproj`
