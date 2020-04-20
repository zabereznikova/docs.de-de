---
title: Befehl „dotnet tool install“
description: Der Befehl „dotnet tool install“ installiert das angegebene .NET Core-Tool auf Ihrem Computer.
ms.date: 02/14/2020
ms.openlocfilehash: 723d25caa6009288dbb55d55f173b04d7b983450
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463362"
---
# <a name="dotnet-tool-install"></a><span data-ttu-id="86a6e-103">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="86a6e-103">dotnet tool install</span></span>

<span data-ttu-id="86a6e-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="86a6e-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="86a6e-105">name</span><span class="sxs-lookup"><span data-stu-id="86a6e-105">Name</span></span>

<span data-ttu-id="86a6e-106">`dotnet tool install`: Installiert das angegebene [.NET Core-Tool](global-tools.md) auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="86a6e-106">`dotnet tool install` - Installs the specified [.NET Core tool](global-tools.md) on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="86a6e-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="86a6e-107">Synopsis</span></span>

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

## <a name="description"></a><span data-ttu-id="86a6e-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="86a6e-108">Description</span></span>

<span data-ttu-id="86a6e-109">Der Befehl `dotnet tool install` ermöglicht Ihnen das Installieren von .NET Core-Tools auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="86a6e-109">The `dotnet tool install` command provides a way for you to install .NET Core tools on your machine.</span></span> <span data-ttu-id="86a6e-110">Um den Befehl zu verwenden, geben Sie eine der folgenden Installationsoptionen an:</span><span class="sxs-lookup"><span data-stu-id="86a6e-110">To use the command, you specify one of the following installation options:</span></span>

* <span data-ttu-id="86a6e-111">Verwenden Sie zum Installieren eines globalen Tools am Standardspeicherort die Option `--global`.</span><span class="sxs-lookup"><span data-stu-id="86a6e-111">To install a global tool in the default location, use the `--global` option.</span></span>
* <span data-ttu-id="86a6e-112">Verwenden Sie zum Installieren eines globalen Tools an einem benutzerdefinierten Speicherort die Option `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="86a6e-112">To install a global tool in a custom location,  use the `--tool-path` option.</span></span>
* <span data-ttu-id="86a6e-113">Wenn Sie ein lokales Tool installieren möchten, lassen Sie die Optionen `--global` und `--tool-path` weg.</span><span class="sxs-lookup"><span data-stu-id="86a6e-113">To install a local tool, omit the `--global` and `--tool-path` options.</span></span>

<span data-ttu-id="86a6e-114">**Lokale Tools sind ab .NET Core SDK 3.0 verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="86a6e-114">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

<span data-ttu-id="86a6e-115">Globale Tools werden standardmäßig in den folgenden Verzeichnissen installiert, wenn Sie die Option `-g` oder `--global` angeben:</span><span class="sxs-lookup"><span data-stu-id="86a6e-115">Global tools are installed in the following directories by default when you specify the `-g` or `--global` option:</span></span>

| <span data-ttu-id="86a6e-116">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="86a6e-116">OS</span></span>          | <span data-ttu-id="86a6e-117">Pfad</span><span class="sxs-lookup"><span data-stu-id="86a6e-117">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="86a6e-118">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="86a6e-118">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="86a6e-119">Windows</span><span class="sxs-lookup"><span data-stu-id="86a6e-119">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

<span data-ttu-id="86a6e-120">Lokale Tools werden zur Datei *tool-manifest.json* im Verzeichnis *.config* unter dem aktuellen Verzeichnis hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="86a6e-120">Local tools are added to a *tool-manifest.json* file in a *.config* directory under the current directory.</span></span> <span data-ttu-id="86a6e-121">Wenn noch keine Manifestdatei vorhanden ist, erstellen Sie sie, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="86a6e-121">If a manifest file doesn't exist yet, create it by running the following command:</span></span>

```dotnetcli
dotnet new tool-manifest
```

<span data-ttu-id="86a6e-122">Weitere Informationen finden Sie unter [Installieren eines lokalen Tools](global-tools.md#install-a-local-tool).</span><span class="sxs-lookup"><span data-stu-id="86a6e-122">For more information, see [Install a local tool](global-tools.md#install-a-local-tool).</span></span>

## <a name="arguments"></a><span data-ttu-id="86a6e-123">Argumente</span><span class="sxs-lookup"><span data-stu-id="86a6e-123">Arguments</span></span>

- **`PACKAGE_NAME`**

  <span data-ttu-id="86a6e-124">Name oder ID des NuGet-Pakets, das das zu installierende .NET Core-Tool enthält.</span><span class="sxs-lookup"><span data-stu-id="86a6e-124">Name/ID of the NuGet package that contains the .NET Core tool to install.</span></span>

## <a name="options"></a><span data-ttu-id="86a6e-125">Optionen</span><span class="sxs-lookup"><span data-stu-id="86a6e-125">Options</span></span>

- **`add-source <SOURCE>`**

  <span data-ttu-id="86a6e-126">Fügt eine zusätzliche NuGet-Paketquelle für die Installation hinzu.</span><span class="sxs-lookup"><span data-stu-id="86a6e-126">Adds an additional NuGet package source to use during installation.</span></span>

- **`configfile <FILE>`**

  <span data-ttu-id="86a6e-127">Die zu verwendende NuGet-Konfigurationsdatei (*nuget.config*).</span><span class="sxs-lookup"><span data-stu-id="86a6e-127">The NuGet configuration (*nuget.config*) file to use.</span></span>

- **`framework <FRAMEWORK>`**

  <span data-ttu-id="86a6e-128">Legt das [Zielframework](../../standard/frameworks.md) des zu installierenden Tools fest.</span><span class="sxs-lookup"><span data-stu-id="86a6e-128">Specifies the [target framework](../../standard/frameworks.md) to install the tool for.</span></span> <span data-ttu-id="86a6e-129">Das .NET Core SDK versucht standardmäßig, das am besten geeignete Zielframework auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="86a6e-129">By default, the .NET Core SDK tries to choose the most appropriate target framework.</span></span>

- **`-g|--global`**

  <span data-ttu-id="86a6e-130">Gibt an, dass die Installation benutzerweit ist.</span><span class="sxs-lookup"><span data-stu-id="86a6e-130">Specifies that the installation is user wide.</span></span> <span data-ttu-id="86a6e-131">Kann nicht mit der Option `--tool-path` kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="86a6e-131">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="86a6e-132">Durch Weglassen von `--global` und `--tool-path` wird die Installation eines lokalen Tools angegeben.</span><span class="sxs-lookup"><span data-stu-id="86a6e-132">Omitting both `--global` and `--tool-path` specifies a local tool installation.</span></span>

- **`-h|--help`**

  <span data-ttu-id="86a6e-133">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="86a6e-133">Prints out a short help for the command.</span></span>

- **`tool-path <PATH>`**

  <span data-ttu-id="86a6e-134">Gibt den Speicherort des globalen Tools an, das installiert wird.</span><span class="sxs-lookup"><span data-stu-id="86a6e-134">Specifies the location where to install the Global Tool.</span></span> <span data-ttu-id="86a6e-135">„PATH“ kann absolut oder relativ sein.</span><span class="sxs-lookup"><span data-stu-id="86a6e-135">PATH can be absolute or relative.</span></span> <span data-ttu-id="86a6e-136">Wenn kein Pfad vorhanden ist, versucht der Befehl, ihn zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="86a6e-136">If PATH doesn't exist, the command tries to create it.</span></span> <span data-ttu-id="86a6e-137">Durch Weglassen von `--global` und `--tool-path` wird die Installation eines lokalen Tools angegeben.</span><span class="sxs-lookup"><span data-stu-id="86a6e-137">Omitting both `--global` and `--tool-path` specifies a local tool installation.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="86a6e-138">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="86a6e-138">Sets the verbosity level of the command.</span></span> <span data-ttu-id="86a6e-139">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="86a6e-139">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

- **`--version <VERSION_NUMBER>`**

  <span data-ttu-id="86a6e-140">Die Version des zu installierenden Tools.</span><span class="sxs-lookup"><span data-stu-id="86a6e-140">The version of the tool to install.</span></span> <span data-ttu-id="86a6e-141">Standardmäßig wird die neueste stabile Paketversion installiert.</span><span class="sxs-lookup"><span data-stu-id="86a6e-141">By default, the latest stable package version is installed.</span></span> <span data-ttu-id="86a6e-142">Verwenden Sie diese Optionen zum Installieren von Vorschau- oder früheren Versionen des Tools.</span><span class="sxs-lookup"><span data-stu-id="86a6e-142">Use this option to install preview or older versions of the tool.</span></span>

## <a name="examples"></a><span data-ttu-id="86a6e-143">Beispiele</span><span class="sxs-lookup"><span data-stu-id="86a6e-143">Examples</span></span>

- **`dotnet tool install -g dotnetsay`**

  <span data-ttu-id="86a6e-144">Installiert [dotnetsay](https://www.nuget.org/packages/dotnetsay/) als globales Tool am Standardspeicherort.</span><span class="sxs-lookup"><span data-stu-id="86a6e-144">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool in the default location.</span></span>

- **`dotnet tool install dotnetsay --tool-path c:\global-tools`**

  <span data-ttu-id="86a6e-145">Installiert [dotnetsay](https://www.nuget.org/packages/dotnetsay/) als globales Tool in einem bestimmten Windows-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="86a6e-145">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool in a specific Windows directory.</span></span>

- **`dotnet tool install dotnetsay --tool-path ~/bin`**

  <span data-ttu-id="86a6e-146">Installiert [dotnetsay](https://www.nuget.org/packages/dotnetsay/) als globales Tool in einem bestimmten Linux/macOS-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="86a6e-146">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool in a specific Linux/macOS directory.</span></span>

- **`dotnet tool install -g dotnetsay --version 2.0.0`**

  <span data-ttu-id="86a6e-147">Installiert Version 2.0.0 von [dotnetsay](https://www.nuget.org/packages/dotnetsay/) als globales Tool.</span><span class="sxs-lookup"><span data-stu-id="86a6e-147">Installs version 2.0.0 of [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool.</span></span>

- **`dotnet tool install dotnetsay`**

  <span data-ttu-id="86a6e-148">Installiert [dotnetsay](https://www.nuget.org/packages/dotnetsay/) als lokales Tool im aktuellen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="86a6e-148">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a local tool for the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="86a6e-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="86a6e-149">See also</span></span>

- [<span data-ttu-id="86a6e-150">.NET Core-Tools</span><span class="sxs-lookup"><span data-stu-id="86a6e-150">.NET Core tools</span></span>](global-tools.md)
- [<span data-ttu-id="86a6e-151">Tutorial: Erstellen und Verwenden eines globalen .NET Core-Tools mithilfe der .NET Core-CLI</span><span class="sxs-lookup"><span data-stu-id="86a6e-151">Tutorial: Install and use a .NET Core global tool using the .NET Core CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="86a6e-152">Tutorial: Erstellen und Verwenden eines lokalen .NET Core-Tools mithilfe der .NET Core-CLI</span><span class="sxs-lookup"><span data-stu-id="86a6e-152">Tutorial: Install and use a .NET Core local tool using the .NET Core CLI</span></span>](local-tools-how-to-use.md)
