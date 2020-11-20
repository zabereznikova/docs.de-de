---
title: Befehl „dotnet tool install“
description: Der Befehl „dotnet tool install“ installiert das angegebene .NET-Tool auf Ihrem Computer.
ms.date: 02/14/2020
ms.openlocfilehash: 1dd870a8f91e557a2f59919682616aa8817fc070
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634323"
---
# <a name="dotnet-tool-install"></a><span data-ttu-id="688d5-103">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="688d5-103">dotnet tool install</span></span>

<span data-ttu-id="688d5-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="688d5-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="688d5-105">name</span><span class="sxs-lookup"><span data-stu-id="688d5-105">Name</span></span>

<span data-ttu-id="688d5-106">`dotnet tool install`: Der Befehl installiert das angegebene [.NET-Tool](global-tools.md) auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="688d5-106">`dotnet tool install` - Installs the specified [.NET tool](global-tools.md) on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="688d5-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="688d5-107">Synopsis</span></span>

```dotnetcli
dotnet tool install <PACKAGE_NAME> -g|--global
    [--add-source <SOURCE>] [--configfile <FILE>]
    [--framework <FRAMEWORK>] [-v|--verbosity <LEVEL>]
    [--version <VERSION_NUMBER>]

dotnet tool install <PACKAGE_NAME> --tool-path <PATH>
    [--add-source <SOURCE>] [--configfile <FILE>]
    [--framework <FRAMEWORK>] [-v|--verbosity <LEVEL>]
    [--version <VERSION_NUMBER>]

dotnet tool install <PACKAGE_NAME>
    [--add-source <SOURCE>] [--configfile <FILE>]
    [--framework <FRAMEWORK>] [-v|--verbosity <LEVEL>]
    [--version <VERSION_NUMBER>]

dotnet tool install -h|--help
```

## <a name="description"></a><span data-ttu-id="688d5-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="688d5-108">Description</span></span>

<span data-ttu-id="688d5-109">Der Befehl `dotnet tool install` ermöglicht Ihnen das Installieren von .NET-Tools auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="688d5-109">The `dotnet tool install` command provides a way for you to install .NET tools on your machine.</span></span> <span data-ttu-id="688d5-110">Um den Befehl zu verwenden, geben Sie eine der folgenden Installationsoptionen an:</span><span class="sxs-lookup"><span data-stu-id="688d5-110">To use the command, you specify one of the following installation options:</span></span>

* <span data-ttu-id="688d5-111">Verwenden Sie zum Installieren eines globalen Tools am Standardspeicherort die Option `--global`.</span><span class="sxs-lookup"><span data-stu-id="688d5-111">To install a global tool in the default location, use the `--global` option.</span></span>
* <span data-ttu-id="688d5-112">Verwenden Sie zum Installieren eines globalen Tools an einem benutzerdefinierten Speicherort die Option `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="688d5-112">To install a global tool in a custom location,  use the `--tool-path` option.</span></span>
* <span data-ttu-id="688d5-113">Wenn Sie ein lokales Tool installieren möchten, lassen Sie die Optionen `--global` und `--tool-path` weg.</span><span class="sxs-lookup"><span data-stu-id="688d5-113">To install a local tool, omit the `--global` and `--tool-path` options.</span></span>

<span data-ttu-id="688d5-114">**Lokale Tools sind ab .NET Core SDK 3.0 verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="688d5-114">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

<span data-ttu-id="688d5-115">Globale Tools werden standardmäßig in den folgenden Verzeichnissen installiert, wenn Sie die Option `-g` oder `--global` angeben:</span><span class="sxs-lookup"><span data-stu-id="688d5-115">Global tools are installed in the following directories by default when you specify the `-g` or `--global` option:</span></span>

| <span data-ttu-id="688d5-116">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="688d5-116">OS</span></span>          | <span data-ttu-id="688d5-117">Pfad</span><span class="sxs-lookup"><span data-stu-id="688d5-117">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="688d5-118">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="688d5-118">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="688d5-119">Windows</span><span class="sxs-lookup"><span data-stu-id="688d5-119">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

<span data-ttu-id="688d5-120">Lokale Tools werden der Datei *dotnet-tools.json* im Verzeichnis *.config* unter dem aktuellen Verzeichnis hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="688d5-120">Local tools are added to a *dotnet-tools.json* file in a *.config* directory under the current directory.</span></span> <span data-ttu-id="688d5-121">Wenn noch keine Manifestdatei vorhanden ist, erstellen Sie sie, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="688d5-121">If a manifest file doesn't exist yet, create it by running the following command:</span></span>

```dotnetcli
dotnet new tool-manifest
```

<span data-ttu-id="688d5-122">Weitere Informationen finden Sie unter [Installieren eines lokalen Tools](global-tools.md#install-a-local-tool).</span><span class="sxs-lookup"><span data-stu-id="688d5-122">For more information, see [Install a local tool](global-tools.md#install-a-local-tool).</span></span>

## <a name="arguments"></a><span data-ttu-id="688d5-123">Argumente</span><span class="sxs-lookup"><span data-stu-id="688d5-123">Arguments</span></span>

- **`PACKAGE_NAME`**

  <span data-ttu-id="688d5-124">Der Name oder die ID des NuGet-Pakets, das das zu installierende .NET-Tool enthält</span><span class="sxs-lookup"><span data-stu-id="688d5-124">Name/ID of the NuGet package that contains the .NET tool to install.</span></span>

## <a name="options"></a><span data-ttu-id="688d5-125">Optionen</span><span class="sxs-lookup"><span data-stu-id="688d5-125">Options</span></span>

- **`add-source <SOURCE>`**

  <span data-ttu-id="688d5-126">Fügt eine zusätzliche NuGet-Paketquelle für die Installation hinzu.</span><span class="sxs-lookup"><span data-stu-id="688d5-126">Adds an additional NuGet package source to use during installation.</span></span>

- **`configfile <FILE>`**

  <span data-ttu-id="688d5-127">Die zu verwendende NuGet-Konfigurationsdatei (*nuget.config*).</span><span class="sxs-lookup"><span data-stu-id="688d5-127">The NuGet configuration (*nuget.config*) file to use.</span></span>

- **`framework <FRAMEWORK>`**

  <span data-ttu-id="688d5-128">Legt das [Zielframework](../../standard/frameworks.md) des zu installierenden Tools fest.</span><span class="sxs-lookup"><span data-stu-id="688d5-128">Specifies the [target framework](../../standard/frameworks.md) to install the tool for.</span></span> <span data-ttu-id="688d5-129">Das .NET SDK versucht standardmäßig, das am besten geeignete Zielframework auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="688d5-129">By default, the .NET SDK tries to choose the most appropriate target framework.</span></span>

- **`-g|--global`**

  <span data-ttu-id="688d5-130">Gibt an, dass die Installation benutzerweit ist.</span><span class="sxs-lookup"><span data-stu-id="688d5-130">Specifies that the installation is user wide.</span></span> <span data-ttu-id="688d5-131">Kann nicht mit der Option `--tool-path` kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="688d5-131">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="688d5-132">Durch Weglassen von `--global` und `--tool-path` wird die Installation eines lokalen Tools angegeben.</span><span class="sxs-lookup"><span data-stu-id="688d5-132">Omitting both `--global` and `--tool-path` specifies a local tool installation.</span></span>

- **`-h|--help`**

  <span data-ttu-id="688d5-133">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="688d5-133">Prints out a short help for the command.</span></span>

- **`tool-path <PATH>`**

  <span data-ttu-id="688d5-134">Gibt den Speicherort des globalen Tools an, das installiert wird.</span><span class="sxs-lookup"><span data-stu-id="688d5-134">Specifies the location where to install the Global Tool.</span></span> <span data-ttu-id="688d5-135">„PATH“ kann absolut oder relativ sein.</span><span class="sxs-lookup"><span data-stu-id="688d5-135">PATH can be absolute or relative.</span></span> <span data-ttu-id="688d5-136">Wenn kein Pfad vorhanden ist, versucht der Befehl, ihn zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="688d5-136">If PATH doesn't exist, the command tries to create it.</span></span> <span data-ttu-id="688d5-137">Durch Weglassen von `--global` und `--tool-path` wird die Installation eines lokalen Tools angegeben.</span><span class="sxs-lookup"><span data-stu-id="688d5-137">Omitting both `--global` and `--tool-path` specifies a local tool installation.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="688d5-138">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="688d5-138">Sets the verbosity level of the command.</span></span> <span data-ttu-id="688d5-139">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="688d5-139">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

- **`--version <VERSION_NUMBER>`**

  <span data-ttu-id="688d5-140">Die Version des zu installierenden Tools.</span><span class="sxs-lookup"><span data-stu-id="688d5-140">The version of the tool to install.</span></span> <span data-ttu-id="688d5-141">Standardmäßig wird die neueste stabile Paketversion installiert.</span><span class="sxs-lookup"><span data-stu-id="688d5-141">By default, the latest stable package version is installed.</span></span> <span data-ttu-id="688d5-142">Verwenden Sie diese Optionen zum Installieren von Vorschau- oder früheren Versionen des Tools.</span><span class="sxs-lookup"><span data-stu-id="688d5-142">Use this option to install preview or older versions of the tool.</span></span>

## <a name="examples"></a><span data-ttu-id="688d5-143">Beispiele</span><span class="sxs-lookup"><span data-stu-id="688d5-143">Examples</span></span>

- **`dotnet tool install -g dotnetsay`**

  <span data-ttu-id="688d5-144">Installiert [dotnetsay](https://www.nuget.org/packages/dotnetsay/) als globales Tool am Standardspeicherort.</span><span class="sxs-lookup"><span data-stu-id="688d5-144">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool in the default location.</span></span>

- **`dotnet tool install dotnetsay --tool-path c:\global-tools`**

  <span data-ttu-id="688d5-145">Installiert [dotnetsay](https://www.nuget.org/packages/dotnetsay/) als globales Tool in einem bestimmten Windows-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="688d5-145">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool in a specific Windows directory.</span></span>

- **`dotnet tool install dotnetsay --tool-path ~/bin`**

  <span data-ttu-id="688d5-146">Installiert [dotnetsay](https://www.nuget.org/packages/dotnetsay/) als globales Tool in einem bestimmten Linux/macOS-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="688d5-146">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool in a specific Linux/macOS directory.</span></span>

- **`dotnet tool install -g dotnetsay --version 2.0.0`**

  <span data-ttu-id="688d5-147">Installiert Version 2.0.0 von [dotnetsay](https://www.nuget.org/packages/dotnetsay/) als globales Tool.</span><span class="sxs-lookup"><span data-stu-id="688d5-147">Installs version 2.0.0 of [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool.</span></span>

- **`dotnet tool install dotnetsay`**

  <span data-ttu-id="688d5-148">Installiert [dotnetsay](https://www.nuget.org/packages/dotnetsay/) als lokales Tool im aktuellen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="688d5-148">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a local tool for the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="688d5-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="688d5-149">See also</span></span>

- [<span data-ttu-id="688d5-150">.NET-Tools</span><span class="sxs-lookup"><span data-stu-id="688d5-150">.NET tools</span></span>](global-tools.md)
- [<span data-ttu-id="688d5-151">Tutorial: Installieren und Verwenden eines globalen .NET-Tools mithilfe der .NET-CLI</span><span class="sxs-lookup"><span data-stu-id="688d5-151">Tutorial: Install and use a .NET global tool using the .NET CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="688d5-152">Tutorial: Installieren und Verwenden eines lokalen .NET-Tools mithilfe der .NET-CLI</span><span class="sxs-lookup"><span data-stu-id="688d5-152">Tutorial: Install and use a .NET local tool using the .NET CLI</span></span>](local-tools-how-to-use.md)
