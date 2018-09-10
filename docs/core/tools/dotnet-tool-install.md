---
title: '.NET Core-CLI-Befehl: dotnet tool install'
description: Der Befehl „dotnet tool install“ installiert das angegebene globale .NET Core-Tool auf Ihrem Computer.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: aad5a3e815936749d90f40975a8b13d34e89386c
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43512194"
---
# <a name="dotnet-tool-install"></a><span data-ttu-id="70fde-103">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="70fde-103">dotnet tool install</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="70fde-104">name</span><span class="sxs-lookup"><span data-stu-id="70fde-104">Name</span></span>

<span data-ttu-id="70fde-105">`dotnet tool install`: Installiert das angegebene [globale .NET Core-Tool](global-tools.md) auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="70fde-105">`dotnet tool install` - Installs the specified [.NET Core Global Tool](global-tools.md) on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="70fde-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="70fde-106">Synopsis</span></span>

```console
dotnet tool install <PACKAGE_NAME> <-g|--global> [--add-source] [--configfile] [--framework] [-v|--verbosity] [--version]
dotnet tool install <PACKAGE_NAME> <--tool-path> [--add-source] [--configfile] [--framework] [-v|--verbosity] [--version]
dotnet tool install <-h|--help>
```

## <a name="description"></a><span data-ttu-id="70fde-107">Beschreibung </span><span class="sxs-lookup"><span data-stu-id="70fde-107">Description</span></span>

<span data-ttu-id="70fde-108">Der `dotnet tool install`-Befehl ermöglicht Ihnen das Installieren von globalen .NET Core-Tools auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="70fde-108">The `dotnet tool install` command provides a way for you to install .NET Core Global Tools on your machine.</span></span> <span data-ttu-id="70fde-109">Zum Verwenden des Befehls müssen Sie entweder mit der Option `--global` angeben, dass Sie eine benutzerweite Installation durchführen möchten, oder mit der Option `--tool-path` einen Installationspfad angeben.</span><span class="sxs-lookup"><span data-stu-id="70fde-109">To use the command, you either have to specify that you want a user-wide installation using the `--global` option or you specify a path to install it using the `--tool-path` option.</span></span>

<span data-ttu-id="70fde-110">Globale Tools werden standardmäßig in den folgenden Verzeichnissen installiert, wenn Sie die Option `-g` (oder `--global`) angeben:</span><span class="sxs-lookup"><span data-stu-id="70fde-110">Global Tools are installed in the following directories by default when you specify the `-g` (or `--global`) option:</span></span>

| <span data-ttu-id="70fde-111">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="70fde-111">OS</span></span>          | <span data-ttu-id="70fde-112">Pfad</span><span class="sxs-lookup"><span data-stu-id="70fde-112">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="70fde-113">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="70fde-113">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="70fde-114">Windows</span><span class="sxs-lookup"><span data-stu-id="70fde-114">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

## <a name="arguments"></a><span data-ttu-id="70fde-115">Argumente</span><span class="sxs-lookup"><span data-stu-id="70fde-115">Arguments</span></span>

`PACKAGE_NAME`

<span data-ttu-id="70fde-116">Name oder ID des NuGet-Pakets, das das zu installierende globale .NET Core-Tool enthält.</span><span class="sxs-lookup"><span data-stu-id="70fde-116">Name/ID of the NuGet package that contains the .NET Core Global Tool to install.</span></span>

## <a name="options"></a><span data-ttu-id="70fde-117">Optionen</span><span class="sxs-lookup"><span data-stu-id="70fde-117">Options</span></span>

`--add-source <SOURCE>`

<span data-ttu-id="70fde-118">Fügt eine zusätzliche NuGet-Paketquelle für die Installation hinzu.</span><span class="sxs-lookup"><span data-stu-id="70fde-118">Adds an additional NuGet package source to use during installation.</span></span>

`--configfile <FILE>`

<span data-ttu-id="70fde-119">Die zu verwendende NuGet-Konfigurationsdatei (*nuget.config*).</span><span class="sxs-lookup"><span data-stu-id="70fde-119">The NuGet configuration (*nuget.config*) file to use.</span></span>

`--framework <FRAMEWORK>`

<span data-ttu-id="70fde-120">Legt das [Zielframework](../../standard/frameworks.md) des zu installierenden Tools fest.</span><span class="sxs-lookup"><span data-stu-id="70fde-120">Specifies the [target framework](../../standard/frameworks.md) to install the tool for.</span></span> <span data-ttu-id="70fde-121">Das .NET Core SDK versucht standardmäßig, das am besten geeignete Zielframework auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="70fde-121">By default, the .NET Core SDK tries to choose the most appropriate target framework.</span></span>

`-g|--global`

<span data-ttu-id="70fde-122">Gibt an, dass die Installation benutzerweit ist.</span><span class="sxs-lookup"><span data-stu-id="70fde-122">Specifies that the installation is user wide.</span></span> <span data-ttu-id="70fde-123">Kann nicht mit der Option `--tool-path` kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="70fde-123">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="70fde-124">Wenn Sie diese Option nicht angeben, müssen Sie die Option `--tool-path` angeben.</span><span class="sxs-lookup"><span data-stu-id="70fde-124">If you don't specify this option, you must specify the `--tool-path` option.</span></span>

`-h|--help`

<span data-ttu-id="70fde-125">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="70fde-125">Prints out a short help for the command.</span></span>

`--tool-path <PATH>`

<span data-ttu-id="70fde-126">Gibt den Speicherort des globalen Tools an, das installiert wird.</span><span class="sxs-lookup"><span data-stu-id="70fde-126">Specifies the location where to install the Global Tool.</span></span> <span data-ttu-id="70fde-127">„PATH“ kann absolut oder relativ sein.</span><span class="sxs-lookup"><span data-stu-id="70fde-127">PATH can be absolute or relative.</span></span> <span data-ttu-id="70fde-128">Wenn kein Pfad vorhanden ist, versucht der Befehl, ihn zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="70fde-128">If PATH doesn't exist, the command tries to create it.</span></span> <span data-ttu-id="70fde-129">Kann nicht mit der Option `--global` kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="70fde-129">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="70fde-130">Wenn Sie diese Option nicht angeben, müssen Sie die Option `--global` angeben.</span><span class="sxs-lookup"><span data-stu-id="70fde-130">If you don't specify this option, you must specify the `--global` option.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="70fde-131">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="70fde-131">Sets the verbosity level of the command.</span></span> <span data-ttu-id="70fde-132">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="70fde-132">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version <VERSION_NUMBER>`

<span data-ttu-id="70fde-133">Die Version des zu installierenden Tools.</span><span class="sxs-lookup"><span data-stu-id="70fde-133">The version of the tool to install.</span></span> <span data-ttu-id="70fde-134">Standardmäßig wird die neueste stabile Paketversion installiert.</span><span class="sxs-lookup"><span data-stu-id="70fde-134">By default, the latest stable package version is installed.</span></span> <span data-ttu-id="70fde-135">Verwenden Sie diese Optionen zum Installieren von Vorschau- oder früheren Versionen des Tools.</span><span class="sxs-lookup"><span data-stu-id="70fde-135">Use this option to install preview or older versions of the tool.</span></span>

## <a name="examples"></a><span data-ttu-id="70fde-136">Beispiele</span><span class="sxs-lookup"><span data-stu-id="70fde-136">Examples</span></span>

<span data-ttu-id="70fde-137">Installiert das globale Tool [dotnetsay](https://www.nuget.org/packages/dotnetsay/) am Standardspeicherort:</span><span class="sxs-lookup"><span data-stu-id="70fde-137">Installs the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool in the default location:</span></span>

`dotnet tool install -g dotnetsay`

<span data-ttu-id="70fde-138">Installiert das globale Tool [dotnetsay](https://www.nuget.org/packages/dotnetsay/) in einem bestimmten Windows-Ordner:</span><span class="sxs-lookup"><span data-stu-id="70fde-138">Installs the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool on a specific Windows folder:</span></span>

`dotnet tool install dotnetsay --tool-path c:\global-tools`

<span data-ttu-id="70fde-139">Installiert das globale Tool [dotnetsay](https://www.nuget.org/packages/dotnetsay/) in einem bestimmten Linux-/macOS-Ordner:</span><span class="sxs-lookup"><span data-stu-id="70fde-139">Installs the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool on a specific Linux/macOS folder:</span></span>

`dotnet tool install dotnetsay --tool-path ~/bin`

<span data-ttu-id="70fde-140">Installiert Version 2.0.0 des globalen Tools [dotnetsay](https://www.nuget.org/packages/dotnetsay/):</span><span class="sxs-lookup"><span data-stu-id="70fde-140">Installs version 2.0.0 of the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool:</span></span>

`dotnet tool install -g dotnetsay --version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="70fde-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="70fde-141">See also</span></span>

* [<span data-ttu-id="70fde-142">.NET Core Global Tools (Globale .NET Core-Tools)</span><span class="sxs-lookup"><span data-stu-id="70fde-142">.NET Core Global Tools</span></span>](global-tools.md)