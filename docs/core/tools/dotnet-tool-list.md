---
title: '.NET Core-CLI-Befehl: dotnet tool list'
description: Der Befehl „dotnet tool list“ listet die angegebenen globalen .NET Core-Tools auf Ihrem Computer auf.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: e2bea974207d3098ed67b69ed16a72a03c44cd8b
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45596922"
---
# <a name="dotnet-tool-list"></a><span data-ttu-id="4df3a-103">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="4df3a-103">dotnet tool list</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="4df3a-104">name</span><span class="sxs-lookup"><span data-stu-id="4df3a-104">Name</span></span>

<span data-ttu-id="4df3a-105">`dotnet tool list`: listet alle [globalen .NET Core-Tools](global-tools.md) auf, die derzeit im Standardverzeichnis oder unter dem angegebenen Pfad auf Ihrem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="4df3a-105">`dotnet tool list` - Lists all [.NET Core Global Tools](global-tools.md) currently installed in the default directory on your machine or in the specified path.</span></span>

## <a name="synopsis"></a><span data-ttu-id="4df3a-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="4df3a-106">Synopsis</span></span>

```console
dotnet tool list <-g|--global>
dotnet tool list <--tool-path>
dotnet tool list <-h|--help>
```

## <a name="description"></a><span data-ttu-id="4df3a-107">Beschreibung </span><span class="sxs-lookup"><span data-stu-id="4df3a-107">Description</span></span>

<span data-ttu-id="4df3a-108">Der Befehl `dotnet tool list` ermöglicht Ihnen das Auflisten aller globalen .NET Core-Tools, die benutzerweit (aktuelles Benutzerprofil) oder unter dem angegebenen Pfad auf Ihrem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="4df3a-108">The `dotnet tool list` command provides a way for you to list all .NET Core Global Tools installed user-wide on your machine (current user profile) or in the specified path.</span></span> <span data-ttu-id="4df3a-109">Der Befehl listet den Paketnamen, die installierte Version und den Befehl für das globale Tool auf.</span><span class="sxs-lookup"><span data-stu-id="4df3a-109">The command lists the package name, version installed, and the Global Tool command.</span></span> <span data-ttu-id="4df3a-110">Zum Verwenden des list-Befehls müssen Sie entweder mit der Option `--global` angeben, dass alle benutzerweiten Tools angezeigt werden sollen, oder mit der Option `--tool-path` einen benutzerdefinierten Pfad angeben.</span><span class="sxs-lookup"><span data-stu-id="4df3a-110">To use the list command, you either have to specify that you want to see all user-wide tools using the `--global` option or specify a custom path using the `--tool-path` option.</span></span>

## <a name="options"></a><span data-ttu-id="4df3a-111">Optionen</span><span class="sxs-lookup"><span data-stu-id="4df3a-111">Options</span></span>

`-g|--global`

<span data-ttu-id="4df3a-112">Listet benutzerweite globale Tools auf.</span><span class="sxs-lookup"><span data-stu-id="4df3a-112">Lists user-wide Global Tools.</span></span> <span data-ttu-id="4df3a-113">Kann nicht mit der Option `--tool-path` kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="4df3a-113">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="4df3a-114">Wenn Sie diese Option nicht angeben, müssen Sie die Option `--tool-path` angeben.</span><span class="sxs-lookup"><span data-stu-id="4df3a-114">If you don't specify this option, you must specify the `--tool-path` option.</span></span>

`-h|--help`

<span data-ttu-id="4df3a-115">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="4df3a-115">Prints out a short help for the command.</span></span>

`--tool-path <PATH>`

<span data-ttu-id="4df3a-116">Legt einen benutzerdefinierten Speicherort fest, an dem globale Tools gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="4df3a-116">Specifies a custom location where to find Global Tools.</span></span> <span data-ttu-id="4df3a-117">„PATH“ kann absolut oder relativ sein.</span><span class="sxs-lookup"><span data-stu-id="4df3a-117">PATH can be absolute or relative.</span></span> <span data-ttu-id="4df3a-118">Kann nicht mit der Option `--global` kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="4df3a-118">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="4df3a-119">Wenn Sie diese Option nicht angeben, müssen Sie die Option `--global` angeben.</span><span class="sxs-lookup"><span data-stu-id="4df3a-119">If you don't specify this option, you must specify the `--global` option.</span></span>

## <a name="examples"></a><span data-ttu-id="4df3a-120">Beispiele</span><span class="sxs-lookup"><span data-stu-id="4df3a-120">Examples</span></span>

<span data-ttu-id="4df3a-121">Listet alle globale Tools auf, die benutzerweit auf Ihrem Computer installiert sind (aktuelles Benutzerprofil):</span><span class="sxs-lookup"><span data-stu-id="4df3a-121">Lists all Global Tools installed user-wide on your machine (current user profile):</span></span>

`dotnet tool list -g`

<span data-ttu-id="4df3a-122">Listet die globalen Tools aus einem bestimmten Windows-Ordner auf:</span><span class="sxs-lookup"><span data-stu-id="4df3a-122">Lists the Global Tools from a specific Windows folder:</span></span>

`dotnet tool list --tool-path c:\global-tools`

<span data-ttu-id="4df3a-123">Listet die globalen Tools aus einem bestimmten Linux-/macOS-Ordner auf:</span><span class="sxs-lookup"><span data-stu-id="4df3a-123">Lists the Global Tools from a specific Linux/macOS folder:</span></span>

`dotnet tool list --tool-path ~/bin`

## <a name="see-also"></a><span data-ttu-id="4df3a-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4df3a-124">See also</span></span>

* [<span data-ttu-id="4df3a-125">.NET Core Global Tools (Globale .NET Core-Tools)</span><span class="sxs-lookup"><span data-stu-id="4df3a-125">.NET Core Global Tools</span></span>](global-tools.md)