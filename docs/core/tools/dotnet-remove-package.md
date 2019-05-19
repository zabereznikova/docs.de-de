---
title: Befehl „dotnet remove package“
description: Der Paketbefehl „dotnet-remove“ bietet eine praktische Option zum Entfernen von NuGet-Paketverweisen auf ein Projekt.
ms.date: 05/29/2018
ms.openlocfilehash: cbdeacff78ef20c9a73010e10a771a724b23792e
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632431"
---
# <a name="dotnet-remove-package"></a><span data-ttu-id="98aff-103">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="98aff-103">dotnet remove package</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="98aff-104">name</span><span class="sxs-lookup"><span data-stu-id="98aff-104">Name</span></span>

<span data-ttu-id="98aff-105">`dotnet remove package`: Entfernt Paketverweis aus einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="98aff-105">`dotnet remove package` - Removes package reference from a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="98aff-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="98aff-106">Synopsis</span></span>

`dotnet remove [<PROJECT>] package <PACKAGE_NAME> [-h|--help]`

## <a name="description"></a><span data-ttu-id="98aff-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="98aff-107">Description</span></span>

<span data-ttu-id="98aff-108">Der `dotnet remove package`-Befehl bietet eine praktische Option zum Entfernen von NuGet-Paketverweisen aus einem Projekt.</span><span class="sxs-lookup"><span data-stu-id="98aff-108">The `dotnet remove package` command provides a convenient option to remove a NuGet package reference from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="98aff-109">Argumente</span><span class="sxs-lookup"><span data-stu-id="98aff-109">Arguments</span></span>

`PROJECT`

<span data-ttu-id="98aff-110">Gibt die Projektdatei an.</span><span class="sxs-lookup"><span data-stu-id="98aff-110">Specifies the project file.</span></span> <span data-ttu-id="98aff-111">Wenn keine angegeben ist, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="98aff-111">If not specified, the command searches the current directory for one.</span></span>

`PACKAGE_NAME`

<span data-ttu-id="98aff-112">Zu entfernender Paketverweis.</span><span class="sxs-lookup"><span data-stu-id="98aff-112">The package reference to remove.</span></span>

## <a name="options"></a><span data-ttu-id="98aff-113">Optionen</span><span class="sxs-lookup"><span data-stu-id="98aff-113">Options</span></span>

`-h|--help`

<span data-ttu-id="98aff-114">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="98aff-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="98aff-115">Beispiele</span><span class="sxs-lookup"><span data-stu-id="98aff-115">Examples</span></span>

<span data-ttu-id="98aff-116">Entfernt `Newtonsoft.Json`-NuGet-Paket aus einem Projekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="98aff-116">Removes `Newtonsoft.Json` NuGet package from a project in the current directory:</span></span>

`dotnet remove package Newtonsoft.Json`
