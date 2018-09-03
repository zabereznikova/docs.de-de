---
title: '.NET Core-CLI-Befehl: dotnet tool install'
description: Der Befehl „dotnet tool install“ installiert das angegebene globale .NET Core-Tool auf Ihrem Computer.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: aad5a3e815936749d90f40975a8b13d34e89386c
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43418720"
---
# <a name="dotnet-tool-install"></a><span data-ttu-id="ea5e0-103">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="ea5e0-103">dotnet tool install</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="ea5e0-104">name</span><span class="sxs-lookup"><span data-stu-id="ea5e0-104">Name</span></span>

<span data-ttu-id="ea5e0-105">`dotnet tool install`: Installiert das angegebene [globale .NET Core-Tool](global-tools.md) auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="ea5e0-105">`dotnet tool install` - Installs the specified [.NET Core Global Tool](global-tools.md) on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="ea5e0-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="ea5e0-106">Synopsis</span></span>

```console
dotnet tool install <PACKAGE_NAME> <-g|--global> [--add-source] [--configfile] [--framework] [-v|--verbosity] [--version]
dotnet tool install <PACKAGE_NAME> <--tool-path> [--add-source] [--configfile] [--framework] [-v|--verbosity] [--version]
dotnet tool install <-h|--help>
```

## <a name="description"></a><span data-ttu-id="ea5e0-107">Beschreibung </span><span class="sxs-lookup"><span data-stu-id="ea5e0-107">Description</span></span>

<span data-ttu-id="ea5e0-108">Der `dotnet tool install`-Befehl ermöglicht Ihnen das Installieren von globalen .NET Core-Tools auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="ea5e0-108">The `dotnet tool install` command provides a way for you to install .NET Core Global Tools on your machine.</span></span> <span data-ttu-id="ea5e0-109">Zum Verwenden des Befehls müssen Sie entweder mit der Option `--global` angeben, dass Sie eine benutzerweite Installation durchführen möchten, oder mit der Option `--tool-path` einen Installationspfad angeben.</span><span class="sxs-lookup"><span data-stu-id="ea5e0-109">To use the command, you either have to specify that you want a user-wide installation using the `--global` option or you specify a path to install it using the `--tool-path` option.</span></span>

<span data-ttu-id="ea5e0-110">Globale Tools werden standardmäßig in den folgenden Verzeichnissen installiert, wenn Sie die Option `-g` (oder `--global`) angeben:</span><span class="sxs-lookup"><span data-stu-id="ea5e0-110">Global Tools are installed in the following directories by default when you specify the `-g` (or `--global`) option:</span></span>

| <span data-ttu-id="ea5e0-111">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="ea5e0-111">OS</span></span>          | <span data-ttu-id="ea5e0-112">Pfad</span><span class="sxs-lookup"><span data-stu-id="ea5e0-112">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="ea5e0-113">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="ea5e0-113">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="ea5e0-114">Windows</span><span class="sxs-lookup"><span data-stu-id="ea5e0-114">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

## <a name="arguments"></a><span data-ttu-id="ea5e0-115">Argumente</span><span class="sxs-lookup"><span data-stu-id="ea5e0-115">Arguments</span></span>

`PACKAGE_NAME`

<span data-ttu-id="ea5e0-116">Name oder ID des NuGet-Pakets, das das zu installierende globale .NET Core-Tool enthält.</span><span class="sxs-lookup"><span data-stu-id="ea5e0-116">Name/ID of the NuGet package that contains the .NET Core Global Tool to install.</span></span>

## <a name="options"></a><span data-ttu-id="ea5e0-117">Optionen</span><span class="sxs-lookup"><span data-stu-id="ea5e0-117">Options</span></span>

`--add-source <SOURCE>`

<span data-ttu-id="ea5e0-118">Fügt eine zusätzliche NuGet-Paketquelle für die Installation hinzu.</span><span class="sxs-lookup"><span data-stu-id="ea5e0-118">Adds an additional NuGet package source to use during installation.</span></span>

`--configfile <FILE>`

<span data-ttu-id="ea5e0-119">Die zu verwendende NuGet-Konfigurationsdatei (*nuget.config*).</span><span class="sxs-lookup"><span data-stu-id="ea5e0-119">The NuGet configuration (*nuget.config*) file to use.</span></span>

`--framework <FRAMEWORK>`

<span data-ttu-id="ea5e0-120">Legt das [Zielframework](../../standard/frameworks.md) des zu installierenden Tools fest.</span><span class="sxs-lookup"><span data-stu-id="ea5e0-120">Specifies the [target framework](../../standard/frameworks.md) to install the tool for.</span></span> <span data-ttu-id="ea5e0-121">Das .NET Core SDK versucht standardmäßig, das am besten geeignete Zielframework auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="ea5e0-121">By default, the .NET Core SDK tries to choose the most appropriate target framework.</span></span>

`-g|--global`

<span data-ttu-id="ea5e0-122">Gibt an, dass die Installation benutzerweit ist.</span><span class="sxs-lookup"><span data-stu-id="ea5e0-122">Specifies that the installation is user wide.</span></span> <span data-ttu-id="ea5e0-123">Kann nicht mit der Option `--tool-path` kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="ea5e0-123">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="ea5e0-124">Wenn Sie diese Option nicht angeben, müssen Sie die Option `--tool-path` angeben.</span><span class="sxs-lookup"><span data-stu-id="ea5e0-124">If you don't specify this option, you must specify the `--tool-path` option.</span></span>

`-h|--help`

<span data-ttu-id="ea5e0-125">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="ea5e0-125">Prints out a short help for the command.</span></span>

`--tool-path <PATH>`

<span data-ttu-id="ea5e0-126">Gibt den Speicherort des globalen Tools an, das installiert wird.</span><span class="sxs-lookup"><span data-stu-id="ea5e0-126">Specifies the location where to install the Global Tool.</span></span> <span data-ttu-id="ea5e0-127">„PATH“ kann absolut oder relativ sein.</span><span class="sxs-lookup"><span data-stu-id="ea5e0-127">PATH can be absolute or relative.</span></span> <span data-ttu-id="ea5e0-128">Wenn kein Pfad vorhanden ist, versucht der Befehl, ihn zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ea5e0-128">If PATH doesn't exist, the command tries to create it.</span></span> <span data-ttu-id="ea5e0-129">Kann nicht mit der Option `--global` kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="ea5e0-129">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="ea5e0-130">Wenn Sie diese Option nicht angeben, müssen Sie die Option `--global` angeben.</span><span class="sxs-lookup"><span data-stu-id="ea5e0-130">If you don't specify this option, you must specify the `--global` option.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="ea5e0-131">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="ea5e0-131">Sets the verbosity level of the command.</span></span> <span data-ttu-id="ea5e0-132">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="ea5e0-132">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version <VERSION_NUMBER>`

<span data-ttu-id="ea5e0-133">Die Version des zu installierenden Tools.</span><span class="sxs-lookup"><span data-stu-id="ea5e0-133">The version of the tool to install.</span></span> <span data-ttu-id="ea5e0-134">Standardmäßig wird die neueste stabile Paketversion installiert.</span><span class="sxs-lookup"><span data-stu-id="ea5e0-134">By default, the latest stable package version is installed.</span></span> <span data-ttu-id="ea5e0-135">Verwenden Sie diese Optionen zum Installieren von Vorschau- oder früheren Versionen des Tools.</span><span class="sxs-lookup"><span data-stu-id="ea5e0-135">Use this option to install preview or older versions of the tool.</span></span>

## <a name="examples"></a><span data-ttu-id="ea5e0-136">Beispiele</span><span class="sxs-lookup"><span data-stu-id="ea5e0-136">Examples</span></span>

<span data-ttu-id="ea5e0-137">Installiert das globale Tool [dotnetsay](https://www.nuget.org/packages/dotnetsay/) am Standardspeicherort:</span><span class="sxs-lookup"><span data-stu-id="ea5e0-137">Installs the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool in the default location:</span></span>

`dotnet tool install -g dotnetsay`

<span data-ttu-id="ea5e0-138">Installiert das globale Tool [dotnetsay](https://www.nuget.org/packages/dotnetsay/) in einem bestimmten Windows-Ordner:</span><span class="sxs-lookup"><span data-stu-id="ea5e0-138">Installs the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool on a specific Windows folder:</span></span>

`dotnet tool install dotnetsay --tool-path c:\global-tools`

<span data-ttu-id="ea5e0-139">Installiert das globale Tool [dotnetsay](https://www.nuget.org/packages/dotnetsay/) in einem bestimmten Linux-/macOS-Ordner:</span><span class="sxs-lookup"><span data-stu-id="ea5e0-139">Installs the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool on a specific Linux/macOS folder:</span></span>

`dotnet tool install dotnetsay --tool-path ~/bin`

<span data-ttu-id="ea5e0-140">Installiert Version 2.0.0 des globalen Tools [dotnetsay](https://www.nuget.org/packages/dotnetsay/):</span><span class="sxs-lookup"><span data-stu-id="ea5e0-140">Installs version 2.0.0 of the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool:</span></span>

`dotnet tool install -g dotnetsay --version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="ea5e0-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ea5e0-141">See also</span></span>

* [<span data-ttu-id="ea5e0-142">.NET Core Global Tools (Globale .NET Core-Tools)</span><span class="sxs-lookup"><span data-stu-id="ea5e0-142">.NET Core Global Tools</span></span>](global-tools.md)