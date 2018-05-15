---
title: Paketbefehl „dotnet-remove“ – .NET Core-CLI
description: Der Paketbefehl „dotnet-remove“ bietet eine praktische Option zum Entfernen von NuGet-Paketverweisen auf ein Projekt.
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.openlocfilehash: 6a18be1a853119be245623e8fa0a0e44ed819e8b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="dotnet-remove-package"></a><span data-ttu-id="d0963-103">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="d0963-103">dotnet remove package</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="d0963-104">name</span><span class="sxs-lookup"><span data-stu-id="d0963-104">Name</span></span>

<span data-ttu-id="d0963-105">`dotnet remove package`: Entfernt Paketverweis aus einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="d0963-105">`dotnet remove package` - Removes package reference from a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d0963-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="d0963-106">Synopsis</span></span>

`dotnet remove [<PROJECT>] package <PACKAGE_NAME> [-h|--help]`

## <a name="description"></a><span data-ttu-id="d0963-107">description</span><span class="sxs-lookup"><span data-stu-id="d0963-107">Description</span></span>

<span data-ttu-id="d0963-108">Der `dotnet remove package`-Befehl bietet eine praktische Option zum Entfernen von NuGet-Paketverweisen aus einem Projekt.</span><span class="sxs-lookup"><span data-stu-id="d0963-108">The `dotnet remove package` command provides a convenient option to remove a NuGet package reference from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="d0963-109">Argumente</span><span class="sxs-lookup"><span data-stu-id="d0963-109">Arguments</span></span>

`PROJECT`

<span data-ttu-id="d0963-110">Gibt die Projektdatei an.</span><span class="sxs-lookup"><span data-stu-id="d0963-110">Specifies the project file.</span></span> <span data-ttu-id="d0963-111">Ist dieses Argument nicht angegeben, sucht der Befehl im aktuellen Verzeichnis nach einer Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="d0963-111">If not specified, the command will search the current directory for one.</span></span>

`PACKAGE_NAME`

<span data-ttu-id="d0963-112">Zu entfernender Paketverweis.</span><span class="sxs-lookup"><span data-stu-id="d0963-112">The package reference to remove.</span></span>

## <a name="options"></a><span data-ttu-id="d0963-113">Optionen</span><span class="sxs-lookup"><span data-stu-id="d0963-113">Options</span></span>

`-h|--help`

<span data-ttu-id="d0963-114">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="d0963-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="d0963-115">Beispiele</span><span class="sxs-lookup"><span data-stu-id="d0963-115">Examples</span></span>

<span data-ttu-id="d0963-116">Entfernt `Newtonsoft.Json`-NuGet-Paket aus einem Projekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="d0963-116">Removes `Newtonsoft.Json` NuGet package from a project in the current directory:</span></span>

`dotnet remove package Newtonsoft.Json`
