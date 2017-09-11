---
title: "Verweisbefehl „dotnet-list“ – .NET Core-CLI"
description: "Der Verweisbefehl „dotnet-list“ bietet eine praktische Option zum Listen von Projekt-zu-Projekt-Verweisen."
keywords: dotnet-list, CLI, CLI-Befehl, .NET Core
author: spboyer
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 8f954a0c-03f8-4fbc-a529-b313ab12c623
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 701345e4db51d26b9eefe8f02b6c0526934de5c9
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-list-reference"></a><span data-ttu-id="8fce1-104">Verweis „dotnet-list“</span><span class="sxs-lookup"><span data-stu-id="8fce1-104">dotnet-list reference</span></span>

## <a name="name"></a><span data-ttu-id="8fce1-105">Name</span><span class="sxs-lookup"><span data-stu-id="8fce1-105">Name</span></span>

<span data-ttu-id="8fce1-106">`dotnet-list reference`: Listet Projekt-zu-Projekt-Verweise auf.</span><span class="sxs-lookup"><span data-stu-id="8fce1-106">`dotnet-list reference` - Lists project to project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="8fce1-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="8fce1-107">Synopsis</span></span>

`dotnet list [<PROJECT>] reference [-h|--help]`

## <a name="description"></a><span data-ttu-id="8fce1-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8fce1-108">Description</span></span>

<span data-ttu-id="8fce1-109">Der `dotnet list reference`-Befehl bietet eine praktische Option zum Listen von Projektverweisen auf ein bestimmtes Projekt.</span><span class="sxs-lookup"><span data-stu-id="8fce1-109">The `dotnet list reference` command provides a convenient option to list project references for a given project.</span></span>

## <a name="arguments"></a><span data-ttu-id="8fce1-110">Argumente</span><span class="sxs-lookup"><span data-stu-id="8fce1-110">Arguments</span></span>

`PROJECT`

<span data-ttu-id="8fce1-111">Gibt die Projektdatei an, die für die Auflistung von Verweisen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="8fce1-111">Specifies the project file to use for listing references.</span></span> <span data-ttu-id="8fce1-112">Ist dieses Argument nicht angegeben, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="8fce1-112">If not specified, the command will search the current directory for a project file.</span></span>

## <a name="options"></a><span data-ttu-id="8fce1-113">Optionen</span><span class="sxs-lookup"><span data-stu-id="8fce1-113">Options</span></span>

`-h|--help`

<span data-ttu-id="8fce1-114">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="8fce1-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="8fce1-115">Beispiele</span><span class="sxs-lookup"><span data-stu-id="8fce1-115">Examples</span></span>

<span data-ttu-id="8fce1-116">Listen Sie die Projektverweise für das angegebene Projekt:</span><span class="sxs-lookup"><span data-stu-id="8fce1-116">List the project references for the specified project:</span></span>

`dotnet list app/app.csproj reference`

<span data-ttu-id="8fce1-117">Listen Sie die Projektverweise für das Projekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="8fce1-117">List the project references for the project in the current directory:</span></span>

`dotnet list reference`

