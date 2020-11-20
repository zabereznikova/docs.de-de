---
title: Befehl „dotnet tool update“
description: Der Befehl „dotnet tool update“ aktualisiert das angegebene .NET-Tool auf Ihrem Computer.
ms.date: 07/08/2020
ms.openlocfilehash: 18b153e53a6dbcb32e50ae4a7d06a1c2f53d1eb5
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634076"
---
# <a name="dotnet-tool-update"></a><span data-ttu-id="6bc2e-103">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="6bc2e-103">dotnet tool update</span></span>

<span data-ttu-id="6bc2e-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="6bc2e-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="6bc2e-105">name</span><span class="sxs-lookup"><span data-stu-id="6bc2e-105">Name</span></span>

<span data-ttu-id="6bc2e-106">`dotnet tool update`: Aktualisiert das angegebene [.NET-Tool](global-tools.md) auf Ihrem Computer</span><span class="sxs-lookup"><span data-stu-id="6bc2e-106">`dotnet tool update` - Updates the specified [.NET tool](global-tools.md) on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="6bc2e-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="6bc2e-107">Synopsis</span></span>

```dotnetcli
dotnet tool update <PACKAGE_ID> -g|--global
    [--add-source <SOURCE>] [--configfile <FILE>]
    [--disable-parallel] [--framework <FRAMEWORK>]
    [--ignore-failed-sources] [--interactive] [--no-cache]
    [-v|--verbosity <LEVEL>] [--version <VERSION>]

dotnet tool update <PACKAGE_ID> --tool-path <PATH>
    [--add-source <SOURCE>] [--configfile <FILE>]
    [--disable-parallel] [--framework <FRAMEWORK>]
    [--ignore-failed-sources] [--interactive] [--no-cache]
    [-v|--verbosity <LEVEL>] [--version <VERSION>]

dotnet tool update <PACKAGE_ID> --local
    [--add-source <SOURCE>] [--configfile <FILE>]
    [--disable-parallel] [--framework <FRAMEWORK>]
    [--ignore-failed-sources] [--interactive] [--no-cache]
    [--tool-manifest <PATH>]
    [-v|--verbosity <LEVEL>] [--version <VERSION>]

dotnet tool update -h|--help
```

## <a name="description"></a><span data-ttu-id="6bc2e-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6bc2e-108">Description</span></span>

<span data-ttu-id="6bc2e-109">Der Befehl `dotnet tool update` ermöglicht Ihnen das Aktualisieren der .NET-Tools auf Ihrem Computer auf die neueste stabile Version des Pakets.</span><span class="sxs-lookup"><span data-stu-id="6bc2e-109">The `dotnet tool update` command provides a way for you to update .NET tools on your machine to the latest stable version of the package.</span></span> <span data-ttu-id="6bc2e-110">Der Befehl deinstalliert und installiert ein Tool neu, sodass es aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="6bc2e-110">The command uninstalls and reinstalls a tool, effectively updating it.</span></span> <span data-ttu-id="6bc2e-111">Um den Befehl zu verwenden, geben Sie eine der folgenden Optionen an:</span><span class="sxs-lookup"><span data-stu-id="6bc2e-111">To use the command, you specify one of the following options:</span></span>

* <span data-ttu-id="6bc2e-112">Verwenden Sie zum Aktualisieren eines globalen Tools, das am Standardspeicherort installiert wurde, die Option `--global`.</span><span class="sxs-lookup"><span data-stu-id="6bc2e-112">To update a global tool that was installed in the default location, use the `--global` option</span></span>
* <span data-ttu-id="6bc2e-113">Verwenden Sie zum Aktualisieren eines globalen Tools, das an einem benutzerdefinierten Speicherort installiert wurde, die Option `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="6bc2e-113">To update a global tool that was installed in a custom location, use the `--tool-path` option.</span></span>
* <span data-ttu-id="6bc2e-114">Um ein lokales Tool zu aktualisieren, verwenden Sie die Option `--local`.</span><span class="sxs-lookup"><span data-stu-id="6bc2e-114">To update a local tool, use the `--local` option.</span></span>

<span data-ttu-id="6bc2e-115">**Lokale Tools sind ab .NET Core SDK 3.0 verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="6bc2e-115">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

## <a name="arguments"></a><span data-ttu-id="6bc2e-116">Argumente</span><span class="sxs-lookup"><span data-stu-id="6bc2e-116">Arguments</span></span>

- **`PACKAGE_ID`**

  <span data-ttu-id="6bc2e-117">Der Name oder die ID des NuGet-Pakets, das das zu aktualisierende globale .NET-Tool enthält.</span><span class="sxs-lookup"><span data-stu-id="6bc2e-117">Name/ID of the NuGet package that contains the .NET global tool to update.</span></span> <span data-ttu-id="6bc2e-118">Mithilfe des Befehls [dotnet tool list](dotnet-tool-list.md) können Sie den Paketnamen abrufen.</span><span class="sxs-lookup"><span data-stu-id="6bc2e-118">You can find the package name using the [dotnet tool list](dotnet-tool-list.md) command.</span></span>

## <a name="options"></a><span data-ttu-id="6bc2e-119">Optionen</span><span class="sxs-lookup"><span data-stu-id="6bc2e-119">Options</span></span>

- **`--add-source <SOURCE>`**

  <span data-ttu-id="6bc2e-120">Fügt eine zusätzliche NuGet-Paketquelle für die Installation hinzu.</span><span class="sxs-lookup"><span data-stu-id="6bc2e-120">Adds an additional NuGet package source to use during installation.</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="6bc2e-121">Die zu verwendende NuGet-Konfigurationsdatei (*nuget.config*).</span><span class="sxs-lookup"><span data-stu-id="6bc2e-121">The NuGet configuration (*nuget.config*) file to use.</span></span>

- **`--disable-parallel`**

  <span data-ttu-id="6bc2e-122">Verhindert die parallele Wiederherstellung mehrerer Projekte.</span><span class="sxs-lookup"><span data-stu-id="6bc2e-122">Prevent restoring multiple projects in parallel.</span></span>

- **`--framework <FRAMEWORK>`**

  <span data-ttu-id="6bc2e-123">Legt das [Zielframework](../../standard/frameworks.md) des zu aktualisierenden Tools fest.</span><span class="sxs-lookup"><span data-stu-id="6bc2e-123">Specifies the [target framework](../../standard/frameworks.md) to update the tool for.</span></span>

- **`--ignore-failed-sources`**

  <span data-ttu-id="6bc2e-124">Paketquellenfehler werden als Warnungen behandelt.</span><span class="sxs-lookup"><span data-stu-id="6bc2e-124">Treat package source failures as warnings.</span></span>

- **`--interactive`**

  <span data-ttu-id="6bc2e-125">Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten (z.B. um die Authentifizierung abzuschließen).</span><span class="sxs-lookup"><span data-stu-id="6bc2e-125">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span>

- **`--local`**

  <span data-ttu-id="6bc2e-126">Aktualisieren Sie das Tool und das lokale Toolmanifest.</span><span class="sxs-lookup"><span data-stu-id="6bc2e-126">Update the tool and the local tool manifest.</span></span> <span data-ttu-id="6bc2e-127">Kann nicht mit der Option `--global` oder der Option `--tool-path` kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="6bc2e-127">Can't be combined with the `--global` option or the `--tool-path` option.</span></span>

- **`--no-cache`**

  <span data-ttu-id="6bc2e-128">Pakete und HTTP-Anforderungen werden nicht zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="6bc2e-128">Do not cache packages and HTTP requests.</span></span>

- **`--tool-manifest <PATH>`**

  <span data-ttu-id="6bc2e-129">Pfad zur Manifestdatei.</span><span class="sxs-lookup"><span data-stu-id="6bc2e-129">Path to the manifest file.</span></span>

- **`--tool-path <PATH>`**

  <span data-ttu-id="6bc2e-130">Gibt den Speicherort an, in dem das globale Tool installiert ist.</span><span class="sxs-lookup"><span data-stu-id="6bc2e-130">Specifies the location where the global tool is installed.</span></span> <span data-ttu-id="6bc2e-131">„PATH“ kann absolut oder relativ sein.</span><span class="sxs-lookup"><span data-stu-id="6bc2e-131">PATH can be absolute or relative.</span></span> <span data-ttu-id="6bc2e-132">Kann nicht mit der Option `--global` kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="6bc2e-132">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="6bc2e-133">Durch Weglassen von `--global` und `--tool-path` wird angegeben, dass das zu aktualisierende Tool ein lokales Tool ist.</span><span class="sxs-lookup"><span data-stu-id="6bc2e-133">Omitting both `--global` and `--tool-path` specifies that the tool to be updated is a local tool.</span></span>

- **`--version <VERSION>`**

  <span data-ttu-id="6bc2e-134">Der Versionsbereich des Toolpakets, auf das aktualisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="6bc2e-134">The version range of the tool package to update to.</span></span> <span data-ttu-id="6bc2e-135">Dies kann nicht zum Herabstufen von Versionen verwendet werden. Sie müssen zuerst neuere Versionen `uninstall`.</span><span class="sxs-lookup"><span data-stu-id="6bc2e-135">This cannot be used to downgrade versions, you must `uninstall` newer versions first.</span></span>

- **`-g|--global`**

  <span data-ttu-id="6bc2e-136">Gibt an, dass das Update für ein benutzerweites Tool ist.</span><span class="sxs-lookup"><span data-stu-id="6bc2e-136">Specifies that the update is for a user-wide tool.</span></span> <span data-ttu-id="6bc2e-137">Kann nicht mit der Option `--tool-path` kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="6bc2e-137">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="6bc2e-138">Durch Weglassen von `--global` und `--tool-path` wird angegeben, dass das zu aktualisierende Tool ein lokales Tool ist.</span><span class="sxs-lookup"><span data-stu-id="6bc2e-138">Omitting both `--global` and `--tool-path` specifies that the tool to be updated is a local tool.</span></span>

- **`-h|--help`**

  <span data-ttu-id="6bc2e-139">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="6bc2e-139">Prints out a short help for the command.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="6bc2e-140">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="6bc2e-140">Sets the verbosity level of the command.</span></span> <span data-ttu-id="6bc2e-141">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="6bc2e-141">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="6bc2e-142">Beispiele</span><span class="sxs-lookup"><span data-stu-id="6bc2e-142">Examples</span></span>

- **`dotnet tool update -g dotnetsay`**

  <span data-ttu-id="6bc2e-143">Aktualisiert das globale Tool [dotnetsay](https://www.nuget.org/packages/dotnetsay/).</span><span class="sxs-lookup"><span data-stu-id="6bc2e-143">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool.</span></span>

- **`dotnet tool update dotnetsay --tool-path c:\global-tools`**

  <span data-ttu-id="6bc2e-144">Aktualisiert das globale Tool [dotnetsay](https://www.nuget.org/packages/dotnetsay/), das sich in einem bestimmten Windows-Verzeichnis befindet.</span><span class="sxs-lookup"><span data-stu-id="6bc2e-144">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool located in a specific Windows directory.</span></span>

- **`dotnet tool update dotnetsay --tool-path ~/bin`**

  <span data-ttu-id="6bc2e-145">Aktualisiert das globale Tool [dotnetsay](https://www.nuget.org/packages/dotnetsay/), das sich in einem bestimmten Linux-/macOS-Verzeichnis befindet.</span><span class="sxs-lookup"><span data-stu-id="6bc2e-145">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool located in a specific Linux/macOS directory.</span></span>

- **`dotnet tool update dotnetsay`**

  <span data-ttu-id="6bc2e-146">Aktualisiert das lokale Tool [dotnetsay](https://www.nuget.org/packages/dotnetsay/), das im lokalen Verzeichnis installiert ist.</span><span class="sxs-lookup"><span data-stu-id="6bc2e-146">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) local tool installed for the current directory.</span></span>

- **`dotnet tool update -g dotnetsay --version 2.0.*`**

  <span data-ttu-id="6bc2e-147">Aktualisiert das globale Tool [dotnetsay](https://www.nuget.org/packages/dotnetsay/) auf die neueste Patchversion mit einer Hauptversion von `2` und einer Nebenversion von `0`.</span><span class="sxs-lookup"><span data-stu-id="6bc2e-147">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool to the latest patch version, with a major version of `2`, and a minor version of `0`.</span></span>

- **`dotnet tool update -g dotnetsay --version (2.0.*,2.1.4)`**

  <span data-ttu-id="6bc2e-148">Aktualisiert das globale Tool [dotnetsay](https://www.nuget.org/packages/dotnetsay/) auf die niedrigste Version innerhalb des angegebenen Bereichs `(> 2.0.0 && < 2.1.4)`, Version `2.1.0` würde installiert.</span><span class="sxs-lookup"><span data-stu-id="6bc2e-148">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool to the lowest version within the specified range `(> 2.0.0 && < 2.1.4)`, version `2.1.0` would be installed.</span></span> <span data-ttu-id="6bc2e-149">Weitere Informationen zu Bereichen der semantischen Versionsverwaltung finden Sie unter [Versionsbereiche von NuGet-Paketen](/nuget/concepts/package-versioning#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="6bc2e-149">For more information on semantic versioning ranges, see [NuGet packaging version ranges](/nuget/concepts/package-versioning#version-ranges).</span></span>

## <a name="see-also"></a><span data-ttu-id="6bc2e-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6bc2e-150">See also</span></span>

- [<span data-ttu-id="6bc2e-151">.NET-Tools</span><span class="sxs-lookup"><span data-stu-id="6bc2e-151">.NET tools</span></span>](global-tools.md)
- [<span data-ttu-id="6bc2e-152">Semantische Versionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="6bc2e-152">Semantic versioning</span></span>](https://semver.org)
- [<span data-ttu-id="6bc2e-153">Tutorial: Installieren und Verwenden eines globalen .NET-Tools mithilfe der .NET-CLI</span><span class="sxs-lookup"><span data-stu-id="6bc2e-153">Tutorial: Install and use a .NET global tool using the .NET CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="6bc2e-154">Tutorial: Installieren und Verwenden eines lokalen .NET-Tools mithilfe der .NET-CLI</span><span class="sxs-lookup"><span data-stu-id="6bc2e-154">Tutorial: Install and use a .NET local tool using the .NET CLI</span></span>](local-tools-how-to-use.md)
