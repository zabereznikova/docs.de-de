---
title: Befehl „dotnet remove package“
description: Der Paketbefehl „dotnet-remove“ bietet eine praktische Option zum Entfernen von NuGet-Paketverweisen auf ein Projekt.
ms.date: 02/14/2020
ms.openlocfilehash: 8eaa311748c5627351ef149012dc4dddd2ab2793
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503635"
---
# <a name="dotnet-remove-package"></a><span data-ttu-id="8d40f-103">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="8d40f-103">dotnet remove package</span></span>

<span data-ttu-id="8d40f-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.x SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="8d40f-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="8d40f-105">Name</span><span class="sxs-lookup"><span data-stu-id="8d40f-105">Name</span></span>

<span data-ttu-id="8d40f-106">`dotnet remove package`: Entfernt Paketverweis aus einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="8d40f-106">`dotnet remove package` - Removes package reference from a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="8d40f-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="8d40f-107">Synopsis</span></span>

```dotnetcli
dotnet remove [<PROJECT>] package <PACKAGE_NAME> [-h|--help]
```

## <a name="description"></a><span data-ttu-id="8d40f-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8d40f-108">Description</span></span>

<span data-ttu-id="8d40f-109">Der `dotnet remove package`-Befehl bietet eine praktische Option zum Entfernen von NuGet-Paketverweisen aus einem Projekt.</span><span class="sxs-lookup"><span data-stu-id="8d40f-109">The `dotnet remove package` command provides a convenient option to remove a NuGet package reference from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="8d40f-110">Argumente</span><span class="sxs-lookup"><span data-stu-id="8d40f-110">Arguments</span></span>

`PROJECT`

<span data-ttu-id="8d40f-111">Gibt die Projektdatei an.</span><span class="sxs-lookup"><span data-stu-id="8d40f-111">Specifies the project file.</span></span> <span data-ttu-id="8d40f-112">Wenn keine angegeben ist, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="8d40f-112">If not specified, the command searches the current directory for one.</span></span>

`PACKAGE_NAME`

<span data-ttu-id="8d40f-113">Zu entfernender Paketverweis.</span><span class="sxs-lookup"><span data-stu-id="8d40f-113">The package reference to remove.</span></span>

## <a name="options"></a><span data-ttu-id="8d40f-114">Optionen</span><span class="sxs-lookup"><span data-stu-id="8d40f-114">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="8d40f-115">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="8d40f-115">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="8d40f-116">Beispiele</span><span class="sxs-lookup"><span data-stu-id="8d40f-116">Examples</span></span>

- <span data-ttu-id="8d40f-117">Entfernen Sie das NuGet-Paket `Newtonsoft.Json` aus einem Projekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="8d40f-117">Remove `Newtonsoft.Json` NuGet package from a project in the current directory:</span></span>

  ```dotnetcli
  dotnet remove package Newtonsoft.Json
  ```
