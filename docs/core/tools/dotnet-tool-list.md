---
title: '.NET Core-CLI-Befehl: dotnet tool list'
description: Der Befehl „dotnet tool list“ listet die angegebenen globalen .NET Core-Tools auf Ihrem Computer auf.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: e2bea974207d3098ed67b69ed16a72a03c44cd8b
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2018
ms.locfileid: "48841241"
---
# <a name="dotnet-tool-list"></a><span data-ttu-id="86567-103">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="86567-103">dotnet tool list</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="86567-104">name</span><span class="sxs-lookup"><span data-stu-id="86567-104">Name</span></span>

<span data-ttu-id="86567-105">`dotnet tool list`: listet alle [globalen .NET Core-Tools](global-tools.md) auf, die derzeit im Standardverzeichnis oder unter dem angegebenen Pfad auf Ihrem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="86567-105">`dotnet tool list` - Lists all [.NET Core Global Tools](global-tools.md) currently installed in the default directory on your machine or in the specified path.</span></span>

## <a name="synopsis"></a><span data-ttu-id="86567-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="86567-106">Synopsis</span></span>

```console
dotnet tool list <-g|--global>
dotnet tool list <--tool-path>
dotnet tool list <-h|--help>
```

## <a name="description"></a><span data-ttu-id="86567-107">Beschreibung </span><span class="sxs-lookup"><span data-stu-id="86567-107">Description</span></span>

<span data-ttu-id="86567-108">Der Befehl `dotnet tool list` ermöglicht Ihnen das Auflisten aller globalen .NET Core-Tools, die benutzerweit (aktuelles Benutzerprofil) oder unter dem angegebenen Pfad auf Ihrem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="86567-108">The `dotnet tool list` command provides a way for you to list all .NET Core Global Tools installed user-wide on your machine (current user profile) or in the specified path.</span></span> <span data-ttu-id="86567-109">Der Befehl listet den Paketnamen, die installierte Version und den Befehl für das globale Tool auf.</span><span class="sxs-lookup"><span data-stu-id="86567-109">The command lists the package name, version installed, and the Global Tool command.</span></span> <span data-ttu-id="86567-110">Zum Verwenden des list-Befehls müssen Sie entweder mit der Option `--global` angeben, dass alle benutzerweiten Tools angezeigt werden sollen, oder mit der Option `--tool-path` einen benutzerdefinierten Pfad angeben.</span><span class="sxs-lookup"><span data-stu-id="86567-110">To use the list command, you either have to specify that you want to see all user-wide tools using the `--global` option or specify a custom path using the `--tool-path` option.</span></span>

## <a name="options"></a><span data-ttu-id="86567-111">Optionen</span><span class="sxs-lookup"><span data-stu-id="86567-111">Options</span></span>

`-g|--global`

<span data-ttu-id="86567-112">Listet benutzerweite globale Tools auf.</span><span class="sxs-lookup"><span data-stu-id="86567-112">Lists user-wide Global Tools.</span></span> <span data-ttu-id="86567-113">Kann nicht mit der Option `--tool-path` kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="86567-113">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="86567-114">Wenn Sie diese Option nicht angeben, müssen Sie die Option `--tool-path` angeben.</span><span class="sxs-lookup"><span data-stu-id="86567-114">If you don't specify this option, you must specify the `--tool-path` option.</span></span>

`-h|--help`

<span data-ttu-id="86567-115">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="86567-115">Prints out a short help for the command.</span></span>

`--tool-path <PATH>`

<span data-ttu-id="86567-116">Legt einen benutzerdefinierten Speicherort fest, an dem globale Tools gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="86567-116">Specifies a custom location where to find Global Tools.</span></span> <span data-ttu-id="86567-117">„PATH“ kann absolut oder relativ sein.</span><span class="sxs-lookup"><span data-stu-id="86567-117">PATH can be absolute or relative.</span></span> <span data-ttu-id="86567-118">Kann nicht mit der Option `--global` kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="86567-118">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="86567-119">Wenn Sie diese Option nicht angeben, müssen Sie die Option `--global` angeben.</span><span class="sxs-lookup"><span data-stu-id="86567-119">If you don't specify this option, you must specify the `--global` option.</span></span>

## <a name="examples"></a><span data-ttu-id="86567-120">Beispiele</span><span class="sxs-lookup"><span data-stu-id="86567-120">Examples</span></span>

<span data-ttu-id="86567-121">Listet alle globale Tools auf, die benutzerweit auf Ihrem Computer installiert sind (aktuelles Benutzerprofil):</span><span class="sxs-lookup"><span data-stu-id="86567-121">Lists all Global Tools installed user-wide on your machine (current user profile):</span></span>

`dotnet tool list -g`

<span data-ttu-id="86567-122">Listet die globalen Tools aus einem bestimmten Windows-Ordner auf:</span><span class="sxs-lookup"><span data-stu-id="86567-122">Lists the Global Tools from a specific Windows folder:</span></span>

`dotnet tool list --tool-path c:\global-tools`

<span data-ttu-id="86567-123">Listet die globalen Tools aus einem bestimmten Linux-/macOS-Ordner auf:</span><span class="sxs-lookup"><span data-stu-id="86567-123">Lists the Global Tools from a specific Linux/macOS folder:</span></span>

`dotnet tool list --tool-path ~/bin`

## <a name="see-also"></a><span data-ttu-id="86567-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="86567-124">See also</span></span>

* [<span data-ttu-id="86567-125">.NET Core Global Tools (Globale .NET Core-Tools)</span><span class="sxs-lookup"><span data-stu-id="86567-125">.NET Core Global Tools</span></span>](global-tools.md)