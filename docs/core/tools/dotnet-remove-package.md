---
title: Befehl „dotnet remove package“
description: Der Paketbefehl „dotnet-remove“ bietet eine praktische Option zum Entfernen von NuGet-Paketverweisen auf ein Projekt.
ms.date: 02/14/2020
ms.openlocfilehash: 8eaa311748c5627351ef149012dc4dddd2ab2793
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503635"
---
# <a name="dotnet-remove-package"></a><span data-ttu-id="6290d-103">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="6290d-103">dotnet remove package</span></span>

<span data-ttu-id="6290d-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.x SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="6290d-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="6290d-105">name</span><span class="sxs-lookup"><span data-stu-id="6290d-105">Name</span></span>

<span data-ttu-id="6290d-106">`dotnet remove package`: Entfernt Paketverweis aus einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="6290d-106">`dotnet remove package` - Removes package reference from a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="6290d-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="6290d-107">Synopsis</span></span>

```dotnetcli
dotnet remove [<PROJECT>] package <PACKAGE_NAME> [-h|--help]
```

## <a name="description"></a><span data-ttu-id="6290d-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6290d-108">Description</span></span>

<span data-ttu-id="6290d-109">Der `dotnet remove package`-Befehl bietet eine praktische Option zum Entfernen von NuGet-Paketverweisen aus einem Projekt.</span><span class="sxs-lookup"><span data-stu-id="6290d-109">The `dotnet remove package` command provides a convenient option to remove a NuGet package reference from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="6290d-110">Argumente</span><span class="sxs-lookup"><span data-stu-id="6290d-110">Arguments</span></span>

`PROJECT`

<span data-ttu-id="6290d-111">Gibt die Projektdatei an.</span><span class="sxs-lookup"><span data-stu-id="6290d-111">Specifies the project file.</span></span> <span data-ttu-id="6290d-112">Wenn keine angegeben ist, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="6290d-112">If not specified, the command searches the current directory for one.</span></span>

`PACKAGE_NAME`

<span data-ttu-id="6290d-113">Zu entfernender Paketverweis.</span><span class="sxs-lookup"><span data-stu-id="6290d-113">The package reference to remove.</span></span>

## <a name="options"></a><span data-ttu-id="6290d-114">Optionen</span><span class="sxs-lookup"><span data-stu-id="6290d-114">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="6290d-115">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="6290d-115">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="6290d-116">Beispiele</span><span class="sxs-lookup"><span data-stu-id="6290d-116">Examples</span></span>

- <span data-ttu-id="6290d-117">Entfernen Sie das NuGet-Paket `Newtonsoft.Json` aus einem Projekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="6290d-117">Remove `Newtonsoft.Json` NuGet package from a project in the current directory:</span></span>

  ```dotnetcli
  dotnet remove package Newtonsoft.Json
  ```
