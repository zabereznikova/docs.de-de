---
title: Paketbefehl „dotnet-remove“ – .NET Core-CLI
description: Der Paketbefehl „dotnet-remove“ bietet eine praktische Option zum Entfernen von NuGet-Paketverweisen auf ein Projekt.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: ed6086bfdfadaa06494c857fc74687f1273af971
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34696857"
---
# <a name="dotnet-remove-package"></a><span data-ttu-id="2cbee-103">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="2cbee-103">dotnet remove package</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="2cbee-104">name</span><span class="sxs-lookup"><span data-stu-id="2cbee-104">Name</span></span>

<span data-ttu-id="2cbee-105">`dotnet remove package`: Entfernt Paketverweis aus einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="2cbee-105">`dotnet remove package` - Removes package reference from a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="2cbee-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="2cbee-106">Synopsis</span></span>

`dotnet remove [<PROJECT>] package <PACKAGE_NAME> [-h|--help]`

## <a name="description"></a><span data-ttu-id="2cbee-107">description</span><span class="sxs-lookup"><span data-stu-id="2cbee-107">Description</span></span>

<span data-ttu-id="2cbee-108">Der `dotnet remove package`-Befehl bietet eine praktische Option zum Entfernen von NuGet-Paketverweisen aus einem Projekt.</span><span class="sxs-lookup"><span data-stu-id="2cbee-108">The `dotnet remove package` command provides a convenient option to remove a NuGet package reference from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="2cbee-109">Argumente</span><span class="sxs-lookup"><span data-stu-id="2cbee-109">Arguments</span></span>

`PROJECT`

<span data-ttu-id="2cbee-110">Gibt die Projektdatei an.</span><span class="sxs-lookup"><span data-stu-id="2cbee-110">Specifies the project file.</span></span> <span data-ttu-id="2cbee-111">Wenn keine angegeben ist, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="2cbee-111">If not specified, the command searches the current directory for one.</span></span>

`PACKAGE_NAME`

<span data-ttu-id="2cbee-112">Zu entfernender Paketverweis.</span><span class="sxs-lookup"><span data-stu-id="2cbee-112">The package reference to remove.</span></span>

## <a name="options"></a><span data-ttu-id="2cbee-113">Optionen</span><span class="sxs-lookup"><span data-stu-id="2cbee-113">Options</span></span>

`-h|--help`

<span data-ttu-id="2cbee-114">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="2cbee-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="2cbee-115">Beispiele</span><span class="sxs-lookup"><span data-stu-id="2cbee-115">Examples</span></span>

<span data-ttu-id="2cbee-116">Entfernt `Newtonsoft.Json`-NuGet-Paket aus einem Projekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="2cbee-116">Removes `Newtonsoft.Json` NuGet package from a project in the current directory:</span></span>

`dotnet remove package Newtonsoft.Json`