---
title: Befehl „dotnet tool list“
description: Der Befehl „dotnet tool list“ listet die angegebenen globalen .NET Core-Tools auf Ihrem Computer auf.
ms.date: 05/29/2018
ms.openlocfilehash: d3ff7fc90faf6ede3f7de0d5af5112c77ca140db
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54712918"
---
# <a name="dotnet-tool-list"></a><span data-ttu-id="1e7e4-103">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="1e7e4-103">dotnet tool list</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="1e7e4-104">name</span><span class="sxs-lookup"><span data-stu-id="1e7e4-104">Name</span></span>

<span data-ttu-id="1e7e4-105">`dotnet tool list`: listet alle [globalen .NET Core-Tools](global-tools.md) auf, die derzeit im Standardverzeichnis oder unter dem angegebenen Pfad auf Ihrem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="1e7e4-105">`dotnet tool list` - Lists all [.NET Core Global Tools](global-tools.md) currently installed in the default directory on your machine or in the specified path.</span></span>

## <a name="synopsis"></a><span data-ttu-id="1e7e4-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="1e7e4-106">Synopsis</span></span>

```console
dotnet tool list <-g|--global>
dotnet tool list <--tool-path>
dotnet tool list <-h|--help>
```

## <a name="description"></a><span data-ttu-id="1e7e4-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1e7e4-107">Description</span></span>

<span data-ttu-id="1e7e4-108">Der Befehl `dotnet tool list` ermöglicht Ihnen das Auflisten aller globalen .NET Core-Tools, die benutzerweit (aktuelles Benutzerprofil) oder unter dem angegebenen Pfad auf Ihrem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="1e7e4-108">The `dotnet tool list` command provides a way for you to list all .NET Core Global Tools installed user-wide on your machine (current user profile) or in the specified path.</span></span> <span data-ttu-id="1e7e4-109">Der Befehl listet den Paketnamen, die installierte Version und den Befehl für das globale Tool auf.</span><span class="sxs-lookup"><span data-stu-id="1e7e4-109">The command lists the package name, version installed, and the Global Tool command.</span></span> <span data-ttu-id="1e7e4-110">Zum Verwenden des list-Befehls müssen Sie entweder mit der Option `--global` angeben, dass alle benutzerweiten Tools angezeigt werden sollen, oder mit der Option `--tool-path` einen benutzerdefinierten Pfad angeben.</span><span class="sxs-lookup"><span data-stu-id="1e7e4-110">To use the list command, you either have to specify that you want to see all user-wide tools using the `--global` option or specify a custom path using the `--tool-path` option.</span></span>

## <a name="options"></a><span data-ttu-id="1e7e4-111">Optionen</span><span class="sxs-lookup"><span data-stu-id="1e7e4-111">Options</span></span>

`-g|--global`

<span data-ttu-id="1e7e4-112">Listet benutzerweite globale Tools auf.</span><span class="sxs-lookup"><span data-stu-id="1e7e4-112">Lists user-wide Global Tools.</span></span> <span data-ttu-id="1e7e4-113">Kann nicht mit der Option `--tool-path` kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="1e7e4-113">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="1e7e4-114">Wenn Sie diese Option nicht angeben, müssen Sie die Option `--tool-path` angeben.</span><span class="sxs-lookup"><span data-stu-id="1e7e4-114">If you don't specify this option, you must specify the `--tool-path` option.</span></span>

`-h|--help`

<span data-ttu-id="1e7e4-115">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="1e7e4-115">Prints out a short help for the command.</span></span>

`--tool-path <PATH>`

<span data-ttu-id="1e7e4-116">Legt einen benutzerdefinierten Speicherort fest, an dem globale Tools gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="1e7e4-116">Specifies a custom location where to find Global Tools.</span></span> <span data-ttu-id="1e7e4-117">„PATH“ kann absolut oder relativ sein.</span><span class="sxs-lookup"><span data-stu-id="1e7e4-117">PATH can be absolute or relative.</span></span> <span data-ttu-id="1e7e4-118">Kann nicht mit der Option `--global` kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="1e7e4-118">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="1e7e4-119">Wenn Sie diese Option nicht angeben, müssen Sie die Option `--global` angeben.</span><span class="sxs-lookup"><span data-stu-id="1e7e4-119">If you don't specify this option, you must specify the `--global` option.</span></span>

## <a name="examples"></a><span data-ttu-id="1e7e4-120">Beispiele</span><span class="sxs-lookup"><span data-stu-id="1e7e4-120">Examples</span></span>

<span data-ttu-id="1e7e4-121">Listet alle globale Tools auf, die benutzerweit auf Ihrem Computer installiert sind (aktuelles Benutzerprofil):</span><span class="sxs-lookup"><span data-stu-id="1e7e4-121">Lists all Global Tools installed user-wide on your machine (current user profile):</span></span>

`dotnet tool list -g`

<span data-ttu-id="1e7e4-122">Listet die globalen Tools aus einem bestimmten Windows-Ordner auf:</span><span class="sxs-lookup"><span data-stu-id="1e7e4-122">Lists the Global Tools from a specific Windows folder:</span></span>

`dotnet tool list --tool-path c:\global-tools`

<span data-ttu-id="1e7e4-123">Listet die globalen Tools aus einem bestimmten Linux-/macOS-Ordner auf:</span><span class="sxs-lookup"><span data-stu-id="1e7e4-123">Lists the Global Tools from a specific Linux/macOS folder:</span></span>

`dotnet tool list --tool-path ~/bin`

## <a name="see-also"></a><span data-ttu-id="1e7e4-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1e7e4-124">See also</span></span>

- [<span data-ttu-id="1e7e4-125">.NET Core Global Tools (Globale .NET Core-Tools)</span><span class="sxs-lookup"><span data-stu-id="1e7e4-125">.NET Core Global Tools</span></span>](global-tools.md)
