---
title: Befehl „dotnet restore“
description: Erfahren Sie mehr über das Wiederherstellen von Abhängigkeiten und projektspezifischen Tools mit dem Befehl dotnet-restore.
ms.date: 05/29/2018
ms.openlocfilehash: 82dd85e340a4cb520f781d977b0798b0f532a088
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75340437"
---
# <a name="dotnet-restore"></a><span data-ttu-id="2b717-103">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="2b717-103">dotnet restore</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="2b717-104">name</span><span class="sxs-lookup"><span data-stu-id="2b717-104">Name</span></span>

<span data-ttu-id="2b717-105">`dotnet restore`: Stellt die Abhängigkeiten und Tools eines Projekts wieder her</span><span class="sxs-lookup"><span data-stu-id="2b717-105">`dotnet restore` - Restores the dependencies and tools of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="2b717-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="2b717-106">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="2b717-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="2b717-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```dotnetcli
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--force] [--ignore-failed-sources] [--no-cache]
    [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity] [--interactive]
dotnet restore [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="2b717-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="2b717-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--ignore-failed-sources] [--no-cache]
    [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity]
dotnet restore [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="2b717-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2b717-109">Description</span></span>

<span data-ttu-id="2b717-110">Der Befehl `dotnet restore` verwendet NuGet zum Wiederherstellen von Abhängigkeiten sowie projektspezifischen Tools, die in der Projektdatei angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="2b717-110">The `dotnet restore` command uses NuGet to restore dependencies as well as project-specific tools that are specified in the project file.</span></span> <span data-ttu-id="2b717-111">Die Wiederherstellung von Abhängigkeiten und Tools wird standardmäßig parallel ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2b717-111">By default, the restoration of dependencies and tools are executed in parallel.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="2b717-112">Zum Wiederherstellen der Abhängigkeiten benötigt NuGet die Feeds, wo sich die Pakete befinden.</span><span class="sxs-lookup"><span data-stu-id="2b717-112">To restore the dependencies, NuGet needs the feeds where the packages are located.</span></span> <span data-ttu-id="2b717-113">Feeds werden normalerweise über die *nuget.config*-Konfigurationsdatei bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="2b717-113">Feeds are usually provided via the *nuget.config* configuration file.</span></span> <span data-ttu-id="2b717-114">Eine standardmäßige Konfigurationsdatei wird bereitgestellt, wenn die CLI-Tools installiert sind.</span><span class="sxs-lookup"><span data-stu-id="2b717-114">A default configuration file is provided when the CLI tools are installed.</span></span> <span data-ttu-id="2b717-115">Sie geben zusätzliche Feeds an, indem Sie eine eigene *nuget.config*-Datei im Projektverzeichnis erstellen.</span><span class="sxs-lookup"><span data-stu-id="2b717-115">You specify additional feeds by creating your own *nuget.config* file in the project directory.</span></span> <span data-ttu-id="2b717-116">Sie können die *nuget.config-* -Feeds mit der `-s`-Option überschreiben.</span><span class="sxs-lookup"><span data-stu-id="2b717-116">You can override the *nuget.config* feeds with the `-s` option.</span></span>

<span data-ttu-id="2b717-117">Für Abhängigkeiten geben Sie mithilfe des Arguments `--packages` an, wo die wiederhergestellten Pakete während der Wiederherstellung platziert werden.</span><span class="sxs-lookup"><span data-stu-id="2b717-117">For dependencies, you specify where the restored packages are placed during the restore operation using the `--packages` argument.</span></span> <span data-ttu-id="2b717-118">Wenn nichts angegeben wurde, wird der Standardcache des NuGet-Pakets verwendet. Er befindet sich im Verzeichnis `.nuget/packages` im Basisverzeichnis des Benutzers auf allen Betriebssystemen.</span><span class="sxs-lookup"><span data-stu-id="2b717-118">If not specified, the default NuGet package cache is used, which is found in the `.nuget/packages` directory in the user's home directory on all operating systems.</span></span> <span data-ttu-id="2b717-119">Zum Beispiel */home/user1* unter Linux oder *C:\Users\user1* unter Windows.</span><span class="sxs-lookup"><span data-stu-id="2b717-119">For example, */home/user1* on Linux or *C:\Users\user1* on Windows.</span></span>

<span data-ttu-id="2b717-120">Für projektspezifische Tools stellt `dotnet restore` zunächst das Paket wieder her, in dem sich das Tool befindet, und danach die Abhängigkeiten des Tools gemäß seiner Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="2b717-120">For project-specific tooling, `dotnet restore` first restores the package in which the tool is packed, and then proceeds to restore the tool's dependencies as specified in its project file.</span></span>

### <a name="nugetconfig-differences"></a><span data-ttu-id="2b717-121">Unterschiede bei „nuget.config“</span><span class="sxs-lookup"><span data-stu-id="2b717-121">nuget.config differences</span></span>

<span data-ttu-id="2b717-122">Das Verhalten des Befehls `dotnet restore` wird durch Einstellungen in der *nuget.config*-Datei (falls vorhanden) beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="2b717-122">The behavior of the `dotnet restore` command is affected by the settings in the *nuget.config* file, if present.</span></span> <span data-ttu-id="2b717-123">Das Festlegen von `globalPackagesFolder` in *nuget.config* platziert z. B. die wiederhergestellten NuGet-Pakete in den angegebenen Ordner.</span><span class="sxs-lookup"><span data-stu-id="2b717-123">For example, setting the `globalPackagesFolder` in *nuget.config* places the restored NuGet packages in the specified folder.</span></span> <span data-ttu-id="2b717-124">Dies ist eine Alternative zur Angabe der Option `--packages` im `dotnet restore`-Befehl.</span><span class="sxs-lookup"><span data-stu-id="2b717-124">This is an alternative to specifying the `--packages` option on the `dotnet restore` command.</span></span> <span data-ttu-id="2b717-125">Weitere Informationen finden Sie in der [Referenz zu „nuget.config“](/nuget/schema/nuget-config-file).</span><span class="sxs-lookup"><span data-stu-id="2b717-125">For more information, see the [nuget.config reference](/nuget/schema/nuget-config-file).</span></span>

<span data-ttu-id="2b717-126">Es gibt drei bestimmte Einstellungen, die von `dotnet restore` ignoriert werden:</span><span class="sxs-lookup"><span data-stu-id="2b717-126">There are three specific settings that `dotnet restore` ignores:</span></span>

- [<span data-ttu-id="2b717-127">bindingRedirects</span><span class="sxs-lookup"><span data-stu-id="2b717-127">bindingRedirects</span></span>](/nuget/schema/nuget-config-file#bindingredirects-section)

  <span data-ttu-id="2b717-128">Bindungsumleitungen funktionieren nicht mit `<PackageReference>`-Elementen, und .NET Core unterstützt nur `<PackageReference>`-Elemente für NuGet-Pakete.</span><span class="sxs-lookup"><span data-stu-id="2b717-128">Binding redirects don't work with `<PackageReference>` elements and .NET Core only supports `<PackageReference>` elements for NuGet packages.</span></span>

- [<span data-ttu-id="2b717-129">solution</span><span class="sxs-lookup"><span data-stu-id="2b717-129">solution</span></span>](/nuget/schema/nuget-config-file#solution-section)

  <span data-ttu-id="2b717-130">Diese Einstellung ist spezifisch für Visual Studio und gilt nicht für .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2b717-130">This setting is Visual Studio specific and doesn't apply to .NET Core.</span></span> <span data-ttu-id="2b717-131">.NET Core verwendet keine `packages.config`-Datei, aber stattdessen `<PackageReference>`-Elemente für NuGet-Pakete.</span><span class="sxs-lookup"><span data-stu-id="2b717-131">.NET Core doesn't use a `packages.config` file and instead uses `<PackageReference>` elements for NuGet packages.</span></span>

- [<span data-ttu-id="2b717-132">trustedSigners</span><span class="sxs-lookup"><span data-stu-id="2b717-132">trustedSigners</span></span>](/nuget/schema/nuget-config-file#trustedsigners-section)

  <span data-ttu-id="2b717-133">Diese Einstellung ist nicht anwendbar, da [NuGet noch keine plattformübergreifende Überprüfung](https://github.com/NuGet/Home/issues/7939) vertrauenswürdiger Pakete unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2b717-133">This setting isn't applicable as [NuGet doesn't yet support cross-platform verification](https://github.com/NuGet/Home/issues/7939) of trusted packages.</span></span>

## <a name="implicit-dotnet-restore"></a><span data-ttu-id="2b717-134">Impliziter `dotnet restore`</span><span class="sxs-lookup"><span data-stu-id="2b717-134">Implicit `dotnet restore`</span></span>

<span data-ttu-id="2b717-135">Ab .NET Core 2.0 wird `dotnet restore` bei Bedarf implizit ausgeführt, wenn Sie die folgenden Befehle ausführen:</span><span class="sxs-lookup"><span data-stu-id="2b717-135">Starting with .NET Core 2.0, `dotnet restore` is run implicitly if necessary when you issue the following commands:</span></span>

- [`dotnet new`](dotnet-new.md)
- [`dotnet build`](dotnet-build.md)
- [`dotnet build-server`](dotnet-build-server.md)
- [`dotnet run`](dotnet-run.md)
- [`dotnet test`](dotnet-test.md)
- [`dotnet publish`](dotnet-publish.md)
- [`dotnet pack`](dotnet-pack.md)

<span data-ttu-id="2b717-136">In den meisten Fällen müssen Sie den `dotnet restore`-Befehl nicht länger explizit verwenden.</span><span class="sxs-lookup"><span data-stu-id="2b717-136">In most cases, you no longer need to explicitly use the `dotnet restore` command.</span></span>

<span data-ttu-id="2b717-137">In manchen Fällen kann es sich als unpraktisch erweisen, `dotnet restore` implizit auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2b717-137">Sometimes, it might be inconvenient to run `dotnet restore` implicitly.</span></span> <span data-ttu-id="2b717-138">Zum Beispiel müssen einige automatisierte Systeme, wie etwa Buildsysteme, `dotnet restore` explizit aufrufen, um zu kontrollieren, wann die Wiederherstellung stattfindet, damit sie die Netzwerknutzung steuern können.</span><span class="sxs-lookup"><span data-stu-id="2b717-138">For example, some automated systems, such as build systems, need to call `dotnet restore` explicitly to control when the restore occurs so that they can control network usage.</span></span> <span data-ttu-id="2b717-139">Sie können das Flag `--no-restore` mit einem beliebigen Befehl aus dieser Reihe verwenden, um die implizite Wiederherstellung zu deaktivieren und eine implizite Ausführung von `dotnet restore` zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="2b717-139">To prevent `dotnet restore` from running implicitly, you can use the `--no-restore` flag with any of these commands to disable implicit restore.</span></span>

## <a name="arguments"></a><span data-ttu-id="2b717-140">Argumente</span><span class="sxs-lookup"><span data-stu-id="2b717-140">Arguments</span></span>

`ROOT`

<span data-ttu-id="2b717-141">Optionaler Pfad zur wiederherzustellenden Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="2b717-141">Optional path to the project file to restore.</span></span>

## <a name="options"></a><span data-ttu-id="2b717-142">Optionen</span><span class="sxs-lookup"><span data-stu-id="2b717-142">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="2b717-143">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="2b717-143">.NET Core 2.x</span></span>](#tab/netcore2x)

`--configfile <FILE>`

<span data-ttu-id="2b717-144">Die NuGet-Konfigurationsdatei (*nuget.config*) für den Wiederherstellungsvorgang.</span><span class="sxs-lookup"><span data-stu-id="2b717-144">The NuGet configuration file (*nuget.config*) to use for the restore operation.</span></span>

`--disable-parallel`

<span data-ttu-id="2b717-145">Deaktiviert paralleles Erstellen von mehreren Projekten.</span><span class="sxs-lookup"><span data-stu-id="2b717-145">Disables restoring multiple projects in parallel.</span></span>

`--force`

<span data-ttu-id="2b717-146">Erzwingt das Auflösen aller Abhängigkeiten, auch wenn die letzte Wiederherstellung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="2b717-146">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="2b717-147">Dieses Flag anzugeben, entspricht dem Löschen der Datei *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="2b717-147">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="2b717-148">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="2b717-148">Prints out a short help for the command.</span></span>

`--ignore-failed-sources`

<span data-ttu-id="2b717-149">Bei fehlerhaften Quellen nur warnen, wenn Pakete die Versionsanforderung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="2b717-149">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

`--no-cache`

<span data-ttu-id="2b717-150">Gibt an, dass Pakete und HTTP-Anfragen nicht zwischengespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="2b717-150">Specifies to not cache packages and HTTP requests.</span></span>

`--no-dependencies`

<span data-ttu-id="2b717-151">Wenn Sie ein Projekt mit Projekt-zu-Projekt-Verweisen (P2P) wiederherstellen, stellen Sie das Stammprojekt wieder her und nicht die Verweise.</span><span class="sxs-lookup"><span data-stu-id="2b717-151">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--packages <PACKAGES_DIRECTORY>`

<span data-ttu-id="2b717-152">Gibt das Verzeichnis für wiederhergestellte Pakete an.</span><span class="sxs-lookup"><span data-stu-id="2b717-152">Specifies the directory for restored packages.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="2b717-153">Gibt eine Laufzeit für die Wiederherstellung des Pakets an.</span><span class="sxs-lookup"><span data-stu-id="2b717-153">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="2b717-154">Wird für das Wiederherstellen von Paketen für Laufzeiten verwendet, die nicht explizit im `<RuntimeIdentifiers>`-Tag in der *.csproj*-Datei aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="2b717-154">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="2b717-155">Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="2b717-155">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="2b717-156">Es können mehrere RIDs bereitgestellt werden, indem diese Option mehrmals angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2b717-156">Provide multiple RIDs by specifying this option multiple times.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="2b717-157">Gibt eine NuGet-Paketquelle an, die während des Wiederherstellungsvorgangs zu verwenden ist.</span><span class="sxs-lookup"><span data-stu-id="2b717-157">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="2b717-158">Diese Einstellung überschreibt alle Quellen, die in den *nuget.config*-Dateien angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="2b717-158">This setting overrides all of the sources specified in the *nuget.config* files.</span></span> <span data-ttu-id="2b717-159">Es können mehrere Quellen bereitgestellt werden, indem diese Option mehrmals angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2b717-159">Multiple sources can be provided by specifying this option multiple times.</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="2b717-160">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="2b717-160">Sets the verbosity level of the command.</span></span> <span data-ttu-id="2b717-161">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="2b717-161">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="2b717-162">Der Standardwert ist `minimal`sein.</span><span class="sxs-lookup"><span data-stu-id="2b717-162">Default value is `minimal`.</span></span>

`--interactive`

<span data-ttu-id="2b717-163">Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten (z.B. um die Authentifizierung abzuschließen).</span><span class="sxs-lookup"><span data-stu-id="2b717-163">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span> <span data-ttu-id="2b717-164">Ab .NET Core 2.1.400.</span><span class="sxs-lookup"><span data-stu-id="2b717-164">Since .NET Core 2.1.400.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="2b717-165">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="2b717-165">.NET Core 1.x</span></span>](#tab/netcore1x)

`--configfile <FILE>`

<span data-ttu-id="2b717-166">Die NuGet-Konfigurationsdatei (*nuget.config*) für den Wiederherstellungsvorgang.</span><span class="sxs-lookup"><span data-stu-id="2b717-166">The NuGet configuration file (*nuget.config*) to use for the restore operation.</span></span>

`--disable-parallel`

<span data-ttu-id="2b717-167">Deaktiviert paralleles Erstellen von mehreren Projekten.</span><span class="sxs-lookup"><span data-stu-id="2b717-167">Disables restoring multiple projects in parallel.</span></span>

`-h|--help`

<span data-ttu-id="2b717-168">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="2b717-168">Prints out a short help for the command.</span></span>

`--ignore-failed-sources`

<span data-ttu-id="2b717-169">Bei fehlerhaften Quellen nur warnen, wenn Pakete die Versionsanforderung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="2b717-169">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

`--no-cache`

<span data-ttu-id="2b717-170">Gibt an, dass Pakete und HTTP-Anfragen nicht zwischengespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="2b717-170">Specifies to not cache packages and HTTP requests.</span></span>

`--no-dependencies`

<span data-ttu-id="2b717-171">Wenn Sie ein Projekt mit Projekt-zu-Projekt-Verweisen (P2P) wiederherstellen, stellen Sie das Stammprojekt wieder her und nicht die Verweise.</span><span class="sxs-lookup"><span data-stu-id="2b717-171">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--packages <PACKAGES_DIRECTORY>`

<span data-ttu-id="2b717-172">Gibt das Verzeichnis für wiederhergestellte Pakete an.</span><span class="sxs-lookup"><span data-stu-id="2b717-172">Specifies the directory for restored packages.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="2b717-173">Gibt eine Laufzeit für die Wiederherstellung des Pakets an.</span><span class="sxs-lookup"><span data-stu-id="2b717-173">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="2b717-174">Wird für das Wiederherstellen von Paketen für Laufzeiten verwendet, die nicht explizit im `<RuntimeIdentifiers>`-Tag in der *.csproj*-Datei aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="2b717-174">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="2b717-175">Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="2b717-175">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="2b717-176">Es können mehrere RIDs bereitgestellt werden, indem diese Option mehrmals angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2b717-176">Provide multiple RIDs by specifying this option multiple times.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="2b717-177">Gibt eine NuGet-Paketquelle an, die während des Wiederherstellungsvorgangs zu verwenden ist.</span><span class="sxs-lookup"><span data-stu-id="2b717-177">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="2b717-178">Dadurch werden alle Quellen überschrieben, die in den *nuget.config*-Dateien angegeben sind. Die Datei *nuget.config* wird so gelesen, als wäre das `<packageSource>`-Element nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="2b717-178">This overrides all of the sources specified in the *nuget.config* files, effectively reading the *nuget.config* file as if the `<packageSource>` element was not there.</span></span> <span data-ttu-id="2b717-179">Es können mehrere Quellen bereitgestellt werden, indem diese Option mehrmals angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2b717-179">Multiple sources can be provided by specifying this option multiple times.</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="2b717-180">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="2b717-180">Sets the verbosity level of the command.</span></span> <span data-ttu-id="2b717-181">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="2b717-181">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="2b717-182">Der Standardwert ist `minimal`.</span><span class="sxs-lookup"><span data-stu-id="2b717-182">The default is `minimal`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="2b717-183">Beispiele</span><span class="sxs-lookup"><span data-stu-id="2b717-183">Examples</span></span>

<span data-ttu-id="2b717-184">Wiederherstellen von Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="2b717-184">Restore dependencies and tools for the project in the current directory:</span></span>

`dotnet restore`

<span data-ttu-id="2b717-185">Wiederherstellen von Abhängigkeiten und Tools für das Projekt `app1` im vorgegebenen Pfad:</span><span class="sxs-lookup"><span data-stu-id="2b717-185">Restore dependencies and tools for the `app1` project found in the given path:</span></span>

`dotnet restore ~/projects/app1/app1.csproj`

<span data-ttu-id="2b717-186">Wiederherstellen der Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis mit dem bereitgestellten Dateipfad als Quelle:</span><span class="sxs-lookup"><span data-stu-id="2b717-186">Restore the dependencies and tools for the project in the current directory using the file path provided as the source:</span></span>

`dotnet restore -s c:\packages\mypackages`

<span data-ttu-id="2b717-187">Wiederherstellen der Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis mit den beiden bereitgestellten Dateipfaden als Quellen:</span><span class="sxs-lookup"><span data-stu-id="2b717-187">Restore the dependencies and tools for the project in the current directory using the two file paths provided as sources:</span></span>

`dotnet restore -s c:\packages\mypackages -s c:\packages\myotherpackages`

<span data-ttu-id="2b717-188">Wiederherstellen von Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis mit detaillierter Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="2b717-188">Restore dependencies and tools for the project in the current directory showing detailed output:</span></span>

`dotnet restore --verbosity detailed`
