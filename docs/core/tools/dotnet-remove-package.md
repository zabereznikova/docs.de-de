---
title: "Paketbefehl „dotnet-remove“ – .NET Core-CLI"
description: "Der Paketbefehl „dotnet-remove“ bietet eine praktische Option zum Entfernen von NuGet-Paketverweisen auf ein Projekt."
keywords: dotnet-remove, CLI, CLI-Befehl, .NET Core
author: spboyer
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 2fcc8d37-16b3-4581-8038-832160e72d36
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a3fef846d5850e2c2a158ccd1f30a84e8f23f793
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-remove-package"></a><span data-ttu-id="2d93b-104">Paket „dotnet-remove“</span><span class="sxs-lookup"><span data-stu-id="2d93b-104">dotnet-remove package</span></span>

## <a name="name"></a><span data-ttu-id="2d93b-105">Name</span><span class="sxs-lookup"><span data-stu-id="2d93b-105">Name</span></span>

<span data-ttu-id="2d93b-106">`dotnet-remove package`: Entfernt Paketverweis aus einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="2d93b-106">`dotnet-remove package` - Removes package reference from a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="2d93b-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="2d93b-107">Synopsis</span></span>

`dotnet remove [<PROJECT>] package <PACKAGE_NAME> [-h|--help]`

## <a name="description"></a><span data-ttu-id="2d93b-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2d93b-108">Description</span></span>

<span data-ttu-id="2d93b-109">Der `dotnet remove package`-Befehl bietet eine praktische Option zum Entfernen von NuGet-Paketverweisen aus einem Projekt.</span><span class="sxs-lookup"><span data-stu-id="2d93b-109">The `dotnet remove package` command provides a convenient option to remove a NuGet package reference from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="2d93b-110">Argumente</span><span class="sxs-lookup"><span data-stu-id="2d93b-110">Arguments</span></span>

`PROJECT`

<span data-ttu-id="2d93b-111">Gibt die Projektdatei an.</span><span class="sxs-lookup"><span data-stu-id="2d93b-111">Specifies the project file.</span></span> <span data-ttu-id="2d93b-112">Ist dieses Argument nicht angegeben, sucht der Befehl im aktuellen Verzeichnis nach einer Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="2d93b-112">If not specified, the command will search the current directory for one.</span></span>

`PACKAGE_NAME`

<span data-ttu-id="2d93b-113">Zu entfernender Paketverweis.</span><span class="sxs-lookup"><span data-stu-id="2d93b-113">The package reference to remove.</span></span>

## <a name="options"></a><span data-ttu-id="2d93b-114">Optionen</span><span class="sxs-lookup"><span data-stu-id="2d93b-114">Options</span></span>

`-h|--help`

<span data-ttu-id="2d93b-115">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="2d93b-115">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="2d93b-116">Beispiele</span><span class="sxs-lookup"><span data-stu-id="2d93b-116">Examples</span></span>

<span data-ttu-id="2d93b-117">Entfernt `Newtonsoft.Json`-NuGet-Paket aus einem Projekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="2d93b-117">Removes `Newtonsoft.Json` NuGet package from a project in the current directory:</span></span>

`dotnet remove package Newtonsoft.Json`

