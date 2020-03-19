---
title: Befehl „dotnet tool install“
description: Der Befehl „dotnet tool install“ installiert das angegebene .NET Core-Tool auf Ihrem Computer.
ms.date: 02/14/2020
ms.openlocfilehash: 1e142773d1f981a8dc3b552d5a23d2864cdd82c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79146462"
---
# <a name="dotnet-tool-install"></a><span data-ttu-id="bfe00-103">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="bfe00-103">dotnet tool install</span></span>

<span data-ttu-id="bfe00-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="bfe00-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="bfe00-105">name</span><span class="sxs-lookup"><span data-stu-id="bfe00-105">Name</span></span>

<span data-ttu-id="bfe00-106">`dotnet tool install`: Installiert das angegebene [.NET Core-Tool](global-tools.md) auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="bfe00-106">`dotnet tool install` - Installs the specified [.NET Core tool](global-tools.md) on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="bfe00-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="bfe00-107">Synopsis</span></span>

```dotnetcli
dotnet tool install <PACKAGE_NAME> <-g|--global>
    [--add-source] [--configfile] [--framework]
    [-v|--verbosity] [--version]

dotnet tool install <PACKAGE_NAME> <--tool-path>
    [--add-source] [--configfile] [--framework]
    [-v|--verbosity] [--version]

dotnet tool install <PACKAGE_NAME>
    [--add-source] [--configfile] [--framework]
    [-v|--verbosity] [--version]

dotnet tool install <-h|--help>
```

## <a name="description"></a><span data-ttu-id="bfe00-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bfe00-108">Description</span></span>

<span data-ttu-id="bfe00-109">Der Befehl `dotnet tool install` ermöglicht Ihnen das Installieren von .NET Core-Tools auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="bfe00-109">The `dotnet tool install` command provides a way for you to install .NET Core tools on your machine.</span></span> <span data-ttu-id="bfe00-110">Um den Befehl zu verwenden, geben Sie eine der folgenden Installationsoptionen an:</span><span class="sxs-lookup"><span data-stu-id="bfe00-110">To use the command, you specify one of the following installation options:</span></span>

* <span data-ttu-id="bfe00-111">Verwenden Sie zum Installieren eines globalen Tools am Standardspeicherort die Option `--global`.</span><span class="sxs-lookup"><span data-stu-id="bfe00-111">To install a global tool in the default location, use the `--global` option.</span></span>
* <span data-ttu-id="bfe00-112">Verwenden Sie zum Installieren eines globalen Tools an einem benutzerdefinierten Speicherort die Option `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="bfe00-112">To install a global tool in a custom location,  use the `--tool-path` option.</span></span>
* <span data-ttu-id="bfe00-113">Wenn Sie ein lokales Tool installieren möchten, lassen Sie die Optionen `--global` und `--tool-path` weg.</span><span class="sxs-lookup"><span data-stu-id="bfe00-113">To install a local tool, omit the `--global` and `--tool-path` options.</span></span>

<span data-ttu-id="bfe00-114">**Lokale Tools sind ab .NET Core SDK 3.0 verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="bfe00-114">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

<span data-ttu-id="bfe00-115">Globale Tools werden standardmäßig in den folgenden Verzeichnissen installiert, wenn Sie die Option `-g` oder `--global` angeben:</span><span class="sxs-lookup"><span data-stu-id="bfe00-115">Global tools are installed in the following directories by default when you specify the `-g` or `--global` option:</span></span>

| <span data-ttu-id="bfe00-116">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="bfe00-116">OS</span></span>          | <span data-ttu-id="bfe00-117">Pfad</span><span class="sxs-lookup"><span data-stu-id="bfe00-117">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="bfe00-118">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="bfe00-118">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="bfe00-119">Windows</span><span class="sxs-lookup"><span data-stu-id="bfe00-119">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

<span data-ttu-id="bfe00-120">Lokale Tools werden zur Datei *tool-manifest.json* im Verzeichnis *.config* unter dem aktuellen Verzeichnis hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="bfe00-120">Local tools are added to a *tool-manifest.json* file in a *.config* directory under the current directory.</span></span> <span data-ttu-id="bfe00-121">Wenn noch keine Manifestdatei vorhanden ist, erstellen Sie sie, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="bfe00-121">If a manifest file doesn't exist yet, create it by running the following command:</span></span>

```dotnetcli
dotnet new tool-manifest
```

<span data-ttu-id="bfe00-122">Weitere Informationen finden Sie unter [Installieren eines lokalen Tools](global-tools.md#install-a-local-tool).</span><span class="sxs-lookup"><span data-stu-id="bfe00-122">For more information, see [Install a local tool](global-tools.md#install-a-local-tool).</span></span>

## <a name="arguments"></a><span data-ttu-id="bfe00-123">Argumente</span><span class="sxs-lookup"><span data-stu-id="bfe00-123">Arguments</span></span>

- **`PACKAGE_NAME`**

  <span data-ttu-id="bfe00-124">Name oder ID des NuGet-Pakets, das das zu installierende .NET Core-Tool enthält.</span><span class="sxs-lookup"><span data-stu-id="bfe00-124">Name/ID of the NuGet package that contains the .NET Core tool to install.</span></span>

## <a name="options"></a><span data-ttu-id="bfe00-125">Optionen</span><span class="sxs-lookup"><span data-stu-id="bfe00-125">Options</span></span>

- **`add-source <SOURCE>`**

  <span data-ttu-id="bfe00-126">Fügt eine zusätzliche NuGet-Paketquelle für die Installation hinzu.</span><span class="sxs-lookup"><span data-stu-id="bfe00-126">Adds an additional NuGet package source to use during installation.</span></span>

- **`configfile <FILE>`**

  <span data-ttu-id="bfe00-127">Die zu verwendende NuGet-Konfigurationsdatei (*nuget.config*).</span><span class="sxs-lookup"><span data-stu-id="bfe00-127">The NuGet configuration (*nuget.config*) file to use.</span></span>

- **`framework <FRAMEWORK>`**

  <span data-ttu-id="bfe00-128">Legt das [Zielframework](../../standard/frameworks.md) des zu installierenden Tools fest.</span><span class="sxs-lookup"><span data-stu-id="bfe00-128">Specifies the [target framework](../../standard/frameworks.md) to install the tool for.</span></span> <span data-ttu-id="bfe00-129">Das .NET Core SDK versucht standardmäßig, das am besten geeignete Zielframework auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="bfe00-129">By default, the .NET Core SDK tries to choose the most appropriate target framework.</span></span>

- **`-g|--global`**

  <span data-ttu-id="bfe00-130">Gibt an, dass die Installation benutzerweit ist.</span><span class="sxs-lookup"><span data-stu-id="bfe00-130">Specifies that the installation is user wide.</span></span> <span data-ttu-id="bfe00-131">Kann nicht mit der Option `--tool-path` kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="bfe00-131">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="bfe00-132">Durch Weglassen von `--global` und `--tool-path` wird die Installation eines lokalen Tools angegeben.</span><span class="sxs-lookup"><span data-stu-id="bfe00-132">Omitting both `--global` and `--tool-path` specifies a local tool installation.</span></span>

- **`-h|--help`**

  <span data-ttu-id="bfe00-133">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="bfe00-133">Prints out a short help for the command.</span></span>

- **`tool-path <PATH>`**

  <span data-ttu-id="bfe00-134">Gibt den Speicherort des globalen Tools an, das installiert wird.</span><span class="sxs-lookup"><span data-stu-id="bfe00-134">Specifies the location where to install the Global Tool.</span></span> <span data-ttu-id="bfe00-135">„PATH“ kann absolut oder relativ sein.</span><span class="sxs-lookup"><span data-stu-id="bfe00-135">PATH can be absolute or relative.</span></span> <span data-ttu-id="bfe00-136">Wenn kein Pfad vorhanden ist, versucht der Befehl, ihn zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bfe00-136">If PATH doesn't exist, the command tries to create it.</span></span> <span data-ttu-id="bfe00-137">Durch Weglassen von `--global` und `--tool-path` wird die Installation eines lokalen Tools angegeben.</span><span class="sxs-lookup"><span data-stu-id="bfe00-137">Omitting both `--global` and `--tool-path` specifies a local tool installation.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="bfe00-138">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="bfe00-138">Sets the verbosity level of the command.</span></span> <span data-ttu-id="bfe00-139">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="bfe00-139">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

- **`--version <VERSION_NUMBER>`**

  <span data-ttu-id="bfe00-140">Die Version des zu installierenden Tools.</span><span class="sxs-lookup"><span data-stu-id="bfe00-140">The version of the tool to install.</span></span> <span data-ttu-id="bfe00-141">Standardmäßig wird die neueste stabile Paketversion installiert.</span><span class="sxs-lookup"><span data-stu-id="bfe00-141">By default, the latest stable package version is installed.</span></span> <span data-ttu-id="bfe00-142">Verwenden Sie diese Optionen zum Installieren von Vorschau- oder früheren Versionen des Tools.</span><span class="sxs-lookup"><span data-stu-id="bfe00-142">Use this option to install preview or older versions of the tool.</span></span>

## <a name="examples"></a><span data-ttu-id="bfe00-143">Beispiele</span><span class="sxs-lookup"><span data-stu-id="bfe00-143">Examples</span></span>

- **`dotnet tool install -g dotnetsay`**

  <span data-ttu-id="bfe00-144">Installiert [dotnetsay](https://www.nuget.org/packages/dotnetsay/) als globales Tool am Standardspeicherort.</span><span class="sxs-lookup"><span data-stu-id="bfe00-144">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool in the default location.</span></span>

- **`dotnet tool install dotnetsay --tool-path c:\global-tools`**

  <span data-ttu-id="bfe00-145">Installiert [dotnetsay](https://www.nuget.org/packages/dotnetsay/) als globales Tool in einem bestimmten Windows-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="bfe00-145">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool in a specific Windows directory.</span></span>

- **`dotnet tool install dotnetsay --tool-path ~/bin`**

  <span data-ttu-id="bfe00-146">Installiert [dotnetsay](https://www.nuget.org/packages/dotnetsay/) als globales Tool in einem bestimmten Linux/macOS-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="bfe00-146">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool in a specific Linux/macOS directory.</span></span>

- **`dotnet tool install -g dotnetsay --version 2.0.0`**

  <span data-ttu-id="bfe00-147">Installiert Version 2.0.0 von [dotnetsay](https://www.nuget.org/packages/dotnetsay/) als globales Tool.</span><span class="sxs-lookup"><span data-stu-id="bfe00-147">Installs version 2.0.0 of [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool.</span></span>

- **`dotnet tool install dotnetsay`**

  <span data-ttu-id="bfe00-148">Installiert [dotnetsay](https://www.nuget.org/packages/dotnetsay/) als lokales Tool im aktuellen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="bfe00-148">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a local tool for the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="bfe00-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bfe00-149">See also</span></span>

- [<span data-ttu-id="bfe00-150">.NET Core-Tools</span><span class="sxs-lookup"><span data-stu-id="bfe00-150">.NET Core tools</span></span>](global-tools.md)
- [<span data-ttu-id="bfe00-151">Tutorial: Erstellen und Verwenden eines globalen .NET Core-Tools mithilfe der .NET Core-CLI</span><span class="sxs-lookup"><span data-stu-id="bfe00-151">Tutorial: Install and use a .NET Core global tool using the .NET Core CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="bfe00-152">Tutorial: Erstellen und Verwenden eines lokalen .NET Core-Tools mithilfe der .NET Core-CLI</span><span class="sxs-lookup"><span data-stu-id="bfe00-152">Tutorial: Install and use a .NET Core local tool using the .NET Core CLI</span></span>](local-tools-how-to-use.md)
