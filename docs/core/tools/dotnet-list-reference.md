---
title: dotnet list-Verweisbefehl – .NET Core-CLI
description: Der Verweisbefehl „dotnet-list“ bietet eine praktische Option zum Listen von Verweisen zwischen Projekten.
author: mairaw
ms.author: mairaw
ms.date: 05/25/2018
ms.openlocfilehash: 821e6d276af44bf984c8ac1b42b4e954dbe69556
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34697182"
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="3f6dd-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="3f6dd-103">dotnet list reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="3f6dd-104">name</span><span class="sxs-lookup"><span data-stu-id="3f6dd-104">Name</span></span>

<span data-ttu-id="3f6dd-105">`dotnet list reference`: Listet Projekt-zu-Projekt-Verweise auf.</span><span class="sxs-lookup"><span data-stu-id="3f6dd-105">`dotnet list reference` - Lists project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="3f6dd-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="3f6dd-106">Synopsis</span></span>

`dotnet list [<PROJECT>] reference [-h|--help]`

## <a name="description"></a><span data-ttu-id="3f6dd-107">description</span><span class="sxs-lookup"><span data-stu-id="3f6dd-107">Description</span></span>

<span data-ttu-id="3f6dd-108">Der `dotnet list reference`-Befehl bietet eine praktische Option zum Listen von Projektverweisen auf ein bestimmtes Projekt.</span><span class="sxs-lookup"><span data-stu-id="3f6dd-108">The `dotnet list reference` command provides a convenient option to list project references for a given project.</span></span>

## <a name="arguments"></a><span data-ttu-id="3f6dd-109">Argumente</span><span class="sxs-lookup"><span data-stu-id="3f6dd-109">Arguments</span></span>

`PROJECT`

<span data-ttu-id="3f6dd-110">Gibt die Projektdatei an, die für die Auflistung von Verweisen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3f6dd-110">Specifies the project file to use for listing references.</span></span> <span data-ttu-id="3f6dd-111">Ist dieses Argument nicht angegeben, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="3f6dd-111">If not specified, the command searches the current directory for a project file.</span></span>

## <a name="options"></a><span data-ttu-id="3f6dd-112">Optionen</span><span class="sxs-lookup"><span data-stu-id="3f6dd-112">Options</span></span>

`-h|--help`

<span data-ttu-id="3f6dd-113">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="3f6dd-113">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="3f6dd-114">Beispiele</span><span class="sxs-lookup"><span data-stu-id="3f6dd-114">Examples</span></span>

<span data-ttu-id="3f6dd-115">Listen Sie die Projektverweise für das angegebene Projekt:</span><span class="sxs-lookup"><span data-stu-id="3f6dd-115">List the project references for the specified project:</span></span>

`dotnet list app/app.csproj reference`

<span data-ttu-id="3f6dd-116">Listen Sie die Projektverweise für das Projekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="3f6dd-116">List the project references for the project in the current directory:</span></span>

`dotnet list reference`