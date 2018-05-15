---
title: dotnet list-Verweisbefehl – .NET Core-CLI
description: Der Verweisbefehl „dotnet-list“ bietet eine praktische Option zum Listen von Verweisen zwischen Projekten.
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.openlocfilehash: 24cb1124fc3f8707afe727e6a73d35d5dde39937
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="988c3-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="988c3-103">dotnet list reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="988c3-104">name</span><span class="sxs-lookup"><span data-stu-id="988c3-104">Name</span></span>

<span data-ttu-id="988c3-105">`dotnet list reference`: Listet Projekt-zu-Projekt-Verweise auf.</span><span class="sxs-lookup"><span data-stu-id="988c3-105">`dotnet list reference` - Lists project to project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="988c3-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="988c3-106">Synopsis</span></span>

`dotnet list [<PROJECT>] reference [-h|--help]`

## <a name="description"></a><span data-ttu-id="988c3-107">description</span><span class="sxs-lookup"><span data-stu-id="988c3-107">Description</span></span>

<span data-ttu-id="988c3-108">Der `dotnet list reference`-Befehl bietet eine praktische Option zum Listen von Projektverweisen auf ein bestimmtes Projekt.</span><span class="sxs-lookup"><span data-stu-id="988c3-108">The `dotnet list reference` command provides a convenient option to list project references for a given project.</span></span>

## <a name="arguments"></a><span data-ttu-id="988c3-109">Argumente</span><span class="sxs-lookup"><span data-stu-id="988c3-109">Arguments</span></span>

`PROJECT`

<span data-ttu-id="988c3-110">Gibt die Projektdatei an, die für die Auflistung von Verweisen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="988c3-110">Specifies the project file to use for listing references.</span></span> <span data-ttu-id="988c3-111">Ist dieses Argument nicht angegeben, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="988c3-111">If not specified, the command will search the current directory for a project file.</span></span>

## <a name="options"></a><span data-ttu-id="988c3-112">Optionen</span><span class="sxs-lookup"><span data-stu-id="988c3-112">Options</span></span>

`-h|--help`

<span data-ttu-id="988c3-113">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="988c3-113">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="988c3-114">Beispiele</span><span class="sxs-lookup"><span data-stu-id="988c3-114">Examples</span></span>

<span data-ttu-id="988c3-115">Listen Sie die Projektverweise für das angegebene Projekt:</span><span class="sxs-lookup"><span data-stu-id="988c3-115">List the project references for the specified project:</span></span>

`dotnet list app/app.csproj reference`

<span data-ttu-id="988c3-116">Listen Sie die Projektverweise für das Projekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="988c3-116">List the project references for the project in the current directory:</span></span>

`dotnet list reference`
