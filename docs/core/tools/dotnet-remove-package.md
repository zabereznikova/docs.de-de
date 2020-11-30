---
title: Befehl „dotnet remove package“
description: Der Paketbefehl „dotnet-remove“ bietet eine praktische Option zum Entfernen von NuGet-Paketverweisen auf ein Projekt.
ms.date: 02/14/2020
ms.openlocfilehash: fc74ac1364a0ed027b83dab270d382f238dc00e5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/29/2020
ms.locfileid: "81463458"
---
# <a name="dotnet-remove-package"></a><span data-ttu-id="62b8e-103">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="62b8e-103">dotnet remove package</span></span>

<span data-ttu-id="62b8e-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.x SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="62b8e-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="62b8e-105">Name</span><span class="sxs-lookup"><span data-stu-id="62b8e-105">Name</span></span>

<span data-ttu-id="62b8e-106">`dotnet remove package`: Entfernt Paketverweis aus einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="62b8e-106">`dotnet remove package` - Removes package reference from a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="62b8e-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="62b8e-107">Synopsis</span></span>

```dotnetcli
dotnet remove [<PROJECT>] package <PACKAGE_NAME>

dotnet remove package -h|--help
```

## <a name="description"></a><span data-ttu-id="62b8e-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="62b8e-108">Description</span></span>

<span data-ttu-id="62b8e-109">Der `dotnet remove package`-Befehl bietet eine praktische Option zum Entfernen von NuGet-Paketverweisen aus einem Projekt.</span><span class="sxs-lookup"><span data-stu-id="62b8e-109">The `dotnet remove package` command provides a convenient option to remove a NuGet package reference from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="62b8e-110">Argumente</span><span class="sxs-lookup"><span data-stu-id="62b8e-110">Arguments</span></span>

`PROJECT`

<span data-ttu-id="62b8e-111">Gibt die Projektdatei an.</span><span class="sxs-lookup"><span data-stu-id="62b8e-111">Specifies the project file.</span></span> <span data-ttu-id="62b8e-112">Wenn keine angegeben ist, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="62b8e-112">If not specified, the command searches the current directory for one.</span></span>

`PACKAGE_NAME`

<span data-ttu-id="62b8e-113">Zu entfernender Paketverweis.</span><span class="sxs-lookup"><span data-stu-id="62b8e-113">The package reference to remove.</span></span>

## <a name="options"></a><span data-ttu-id="62b8e-114">Optionen</span><span class="sxs-lookup"><span data-stu-id="62b8e-114">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="62b8e-115">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="62b8e-115">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="62b8e-116">Beispiele</span><span class="sxs-lookup"><span data-stu-id="62b8e-116">Examples</span></span>

- <span data-ttu-id="62b8e-117">Entfernen Sie das NuGet-Paket `Newtonsoft.Json` aus einem Projekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="62b8e-117">Remove `Newtonsoft.Json` NuGet package from a project in the current directory:</span></span>

  ```dotnetcli
  dotnet remove package Newtonsoft.Json
  ```
