---
title: Befehl „dotnet restore“
description: Erfahren Sie mehr über das Wiederherstellen von Abhängigkeiten und projektspezifischen Tools mit dem Befehl dotnet-restore.
ms.date: 05/29/2018
ms.openlocfilehash: 1e0e1fbf6ab5f595773a072242440e30865fed16
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2019
ms.locfileid: "70969772"
---
# <a name="dotnet-restore"></a><span data-ttu-id="c5b1f-103">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="c5b1f-103">dotnet restore</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="c5b1f-104">name</span><span class="sxs-lookup"><span data-stu-id="c5b1f-104">Name</span></span>

<span data-ttu-id="c5b1f-105">`dotnet restore`: Stellt die Abhängigkeiten und Tools eines Projekts wieder her</span><span class="sxs-lookup"><span data-stu-id="c5b1f-105">`dotnet restore` - Restores the dependencies and tools of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c5b1f-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="c5b1f-106">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="c5b1f-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="c5b1f-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```console
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--force] [--ignore-failed-sources] [--no-cache]
    [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity] [--interactive]
dotnet restore [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c5b1f-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c5b1f-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--ignore-failed-sources] [--no-cache]
    [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity]
dotnet restore [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="c5b1f-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c5b1f-109">Description</span></span>

<span data-ttu-id="c5b1f-110">Der Befehl `dotnet restore` verwendet NuGet zum Wiederherstellen von Abhängigkeiten sowie projektspezifischen Tools, die in der Projektdatei angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-110">The `dotnet restore` command uses NuGet to restore dependencies as well as project-specific tools that are specified in the project file.</span></span> <span data-ttu-id="c5b1f-111">Die Wiederherstellung von Abhängigkeiten und Tools wird standardmäßig parallel ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-111">By default, the restoration of dependencies and tools are executed in parallel.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="c5b1f-112">Zum Wiederherstellen der Abhängigkeiten benötigt NuGet die Feeds, wo sich die Pakete befinden.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-112">To restore the dependencies, NuGet needs the feeds where the packages are located.</span></span> <span data-ttu-id="c5b1f-113">Feeds werden normalerweise über die *nuget.config*-Konfigurationsdatei bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-113">Feeds are usually provided via the *nuget.config* configuration file.</span></span> <span data-ttu-id="c5b1f-114">Eine standardmäßige Konfigurationsdatei wird bereitgestellt, wenn die CLI-Tools installiert sind.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-114">A default configuration file is provided when the CLI tools are installed.</span></span> <span data-ttu-id="c5b1f-115">Sie geben zusätzliche Feeds an, indem Sie eine eigene *nuget.config*-Datei im Projektverzeichnis erstellen.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-115">You specify additional feeds by creating your own *nuget.config* file in the project directory.</span></span> <span data-ttu-id="c5b1f-116">Sie können auch zusätzliche Feeds pro Aufruf an der Eingabeaufforderung angeben.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-116">You also specify additional feeds per invocation at a command prompt.</span></span>

<span data-ttu-id="c5b1f-117">Für Abhängigkeiten geben Sie mithilfe des Arguments `--packages` an, wo die wiederhergestellten Pakete während der Wiederherstellung platziert werden.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-117">For dependencies, you specify where the restored packages are placed during the restore operation using the `--packages` argument.</span></span> <span data-ttu-id="c5b1f-118">Wenn nichts angegeben wurde, wird der Standardcache des NuGet-Pakets verwendet. Er befindet sich im Verzeichnis `.nuget/packages` im Basisverzeichnis des Benutzers auf allen Betriebssystemen.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-118">If not specified, the default NuGet package cache is used, which is found in the `.nuget/packages` directory in the user's home directory on all operating systems.</span></span> <span data-ttu-id="c5b1f-119">Zum Beispiel */home/user1* unter Linux oder *C:\Users\user1* unter Windows.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-119">For example, */home/user1* on Linux or *C:\Users\user1* on Windows.</span></span>

<span data-ttu-id="c5b1f-120">Für projektspezifische Tools stellt `dotnet restore` zunächst das Paket wieder her, in dem sich das Tool befindet, und danach die Abhängigkeiten des Tools gemäß seiner Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-120">For project-specific tooling, `dotnet restore` first restores the package in which the tool is packed, and then proceeds to restore the tool's dependencies as specified in its project file.</span></span>

### <a name="nugetconfig-differences"></a><span data-ttu-id="c5b1f-121">Unterschiede bei „nuget.config“</span><span class="sxs-lookup"><span data-stu-id="c5b1f-121">nuget.config differences</span></span>

<span data-ttu-id="c5b1f-122">Das Verhalten des Befehls `dotnet restore` wird durch Einstellungen in der *nuget.config*-Datei (falls vorhanden) beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-122">The behavior of the `dotnet restore` command is affected by the settings in the *nuget.config* file, if present.</span></span> <span data-ttu-id="c5b1f-123">Das Festlegen von `globalPackagesFolder` in *nuget.config* platziert z. B. die wiederhergestellten NuGet-Pakete in den angegebenen Ordner.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-123">For example, setting the `globalPackagesFolder` in *nuget.config* places the restored NuGet packages in the specified folder.</span></span> <span data-ttu-id="c5b1f-124">Dies ist eine Alternative zur Angabe der Option `--packages` im `dotnet restore`-Befehl.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-124">This is an alternative to specifying the `--packages` option on the `dotnet restore` command.</span></span> <span data-ttu-id="c5b1f-125">Weitere Informationen finden Sie in der [Referenz zu „nuget.config“](/nuget/schema/nuget-config-file).</span><span class="sxs-lookup"><span data-stu-id="c5b1f-125">For more information, see the [nuget.config reference](/nuget/schema/nuget-config-file).</span></span>

<span data-ttu-id="c5b1f-126">Es gibt drei bestimmte Einstellungen, die von `dotnet restore` ignoriert werden:</span><span class="sxs-lookup"><span data-stu-id="c5b1f-126">There are three specific settings that `dotnet restore` ignores:</span></span>

- [<span data-ttu-id="c5b1f-127">bindingRedirects</span><span class="sxs-lookup"><span data-stu-id="c5b1f-127">bindingRedirects</span></span>](/nuget/schema/nuget-config-file#bindingredirects-section)

  <span data-ttu-id="c5b1f-128">Bindungsumleitungen funktionieren nicht mit `<PackageReference>`-Elementen, und .NET Core unterstützt nur `<PackageReference>`-Elemente für NuGet-Pakete.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-128">Binding redirects don't work with `<PackageReference>` elements and .NET Core only supports `<PackageReference>` elements for NuGet packages.</span></span>

- [<span data-ttu-id="c5b1f-129">solution</span><span class="sxs-lookup"><span data-stu-id="c5b1f-129">solution</span></span>](/nuget/schema/nuget-config-file#solution-section)

  <span data-ttu-id="c5b1f-130">Diese Einstellung ist spezifisch für Visual Studio und gilt nicht für .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-130">This setting is Visual Studio specific and doesn't apply to .NET Core.</span></span> <span data-ttu-id="c5b1f-131">.NET Core verwendet keine `packages.config`-Datei, aber stattdessen `<PackageReference>`-Elemente für NuGet-Pakete.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-131">.NET Core doesn't use a `packages.config` file and instead uses `<PackageReference>` elements for NuGet packages.</span></span>

- [<span data-ttu-id="c5b1f-132">trustedSigners</span><span class="sxs-lookup"><span data-stu-id="c5b1f-132">trustedSigners</span></span>](/nuget/schema/nuget-config-file#trustedsigners-section)

  <span data-ttu-id="c5b1f-133">Diese Einstellung ist nicht anwendbar, da [NuGet noch keine plattformübergreifende Überprüfung](https://github.com/NuGet/Home/issues/7939) vertrauenswürdiger Pakete unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-133">This setting isn't applicable as [NuGet doesn't yet support cross-platform verification](https://github.com/NuGet/Home/issues/7939) of trusted packages.</span></span>

## <a name="implicit-dotnet-restore"></a><span data-ttu-id="c5b1f-134">Impliziter `dotnet restore`</span><span class="sxs-lookup"><span data-stu-id="c5b1f-134">Implicit `dotnet restore`</span></span>

<span data-ttu-id="c5b1f-135">Ab .NET Core 2.0 wird `dotnet restore` bei Bedarf implizit ausgeführt, wenn Sie die folgenden Befehle ausführen:</span><span class="sxs-lookup"><span data-stu-id="c5b1f-135">Starting with .NET Core 2.0, `dotnet restore` is run implicitly if necessary when you issue the following commands:</span></span>

- [`dotnet new`](dotnet-new.md)
- [`dotnet build`](dotnet-build.md)
- [`dotnet build-server`](dotnet-build-server.md)
- [`dotnet run`](dotnet-run.md)
- [`dotnet test`](dotnet-test.md)
- [`dotnet publish`](dotnet-publish.md)
- [`dotnet pack`](dotnet-pack.md)

<span data-ttu-id="c5b1f-136">In den meisten Fällen müssen Sie den `dotnet restore`-Befehl nicht länger explizit verwenden.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-136">In most cases, you no longer need to explicitly use the `dotnet restore` command.</span></span>

<span data-ttu-id="c5b1f-137">In manchen Fällen kann es sich als unpraktisch erweisen, `dotnet restore` implizit auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-137">Sometimes, it might be inconvenient to run `dotnet restore` implicitly.</span></span> <span data-ttu-id="c5b1f-138">Zum Beispiel müssen einige automatisierte Systeme, wie etwa Buildsysteme, `dotnet restore` explizit aufrufen, um zu kontrollieren, wann die Wiederherstellung stattfindet, damit sie die Netzwerknutzung steuern können.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-138">For example, some automated systems, such as build systems, need to call `dotnet restore` explicitly to control when the restore occurs so that they can control network usage.</span></span> <span data-ttu-id="c5b1f-139">Sie können das Flag `--no-restore` mit einem beliebigen Befehl aus dieser Reihe verwenden, um die implizite Wiederherstellung zu deaktivieren und eine implizite Ausführung von `dotnet restore` zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-139">To prevent `dotnet restore` from running implicitly, you can use the `--no-restore` flag with any of these commands to disable implicit restore.</span></span>

## <a name="arguments"></a><span data-ttu-id="c5b1f-140">Argumente</span><span class="sxs-lookup"><span data-stu-id="c5b1f-140">Arguments</span></span>

`ROOT`

<span data-ttu-id="c5b1f-141">Optionaler Pfad zur wiederherzustellenden Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-141">Optional path to the project file to restore.</span></span>

## <a name="options"></a><span data-ttu-id="c5b1f-142">Optionen</span><span class="sxs-lookup"><span data-stu-id="c5b1f-142">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="c5b1f-143">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="c5b1f-143">.NET Core 2.x</span></span>](#tab/netcore2x)

`--configfile <FILE>`

<span data-ttu-id="c5b1f-144">Die NuGet-Konfigurationsdatei (*nuget.config*) für den Wiederherstellungsvorgang.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-144">The NuGet configuration file (*nuget.config*) to use for the restore operation.</span></span>

`--disable-parallel`

<span data-ttu-id="c5b1f-145">Deaktiviert paralleles Erstellen von mehreren Projekten.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-145">Disables restoring multiple projects in parallel.</span></span>

`--force`

<span data-ttu-id="c5b1f-146">Erzwingt das Auflösen aller Abhängigkeiten, auch wenn die letzte Wiederherstellung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-146">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="c5b1f-147">Dieses Flag anzugeben, entspricht dem Löschen der Datei *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-147">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="c5b1f-148">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-148">Prints out a short help for the command.</span></span>

`--ignore-failed-sources`

<span data-ttu-id="c5b1f-149">Bei fehlerhaften Quellen nur warnen, wenn Pakete die Versionsanforderung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-149">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

`--no-cache`

<span data-ttu-id="c5b1f-150">Gibt an, dass Pakete und HTTP-Anfragen nicht zwischengespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-150">Specifies to not cache packages and HTTP requests.</span></span>

`--no-dependencies`

<span data-ttu-id="c5b1f-151">Wenn Sie ein Projekt mit Projekt-zu-Projekt-Verweisen (P2P) wiederherstellen, stellen Sie das Stammprojekt wieder her und nicht die Verweise.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-151">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--packages <PACKAGES_DIRECTORY>`

<span data-ttu-id="c5b1f-152">Gibt das Verzeichnis für wiederhergestellte Pakete an.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-152">Specifies the directory for restored packages.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="c5b1f-153">Gibt eine Laufzeit für die Wiederherstellung des Pakets an.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-153">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="c5b1f-154">Wird für das Wiederherstellen von Paketen für Laufzeiten verwendet, die nicht explizit im `<RuntimeIdentifiers>`-Tag in der *.csproj*-Datei aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-154">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="c5b1f-155">Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="c5b1f-155">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="c5b1f-156">Es können mehrere RIDs bereitgestellt werden, indem diese Option mehrmals angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-156">Provide multiple RIDs by specifying this option multiple times.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="c5b1f-157">Gibt eine NuGet-Paketquelle an, die während des Wiederherstellungsvorgangs zu verwenden ist.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-157">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="c5b1f-158">Diese Einstellung überschreibt alle Quellen, die in den *nuget.config*-Dateien angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-158">This setting overrides all of the sources specified in the *nuget.config* files.</span></span> <span data-ttu-id="c5b1f-159">Es können mehrere Quellen bereitgestellt werden, indem diese Option mehrmals angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-159">Multiple sources can be provided by specifying this option multiple times.</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="c5b1f-160">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-160">Sets the verbosity level of the command.</span></span> <span data-ttu-id="c5b1f-161">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-161">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--interactive`

<span data-ttu-id="c5b1f-162">Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten (z.B. um die Authentifizierung abzuschließen).</span><span class="sxs-lookup"><span data-stu-id="c5b1f-162">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span> <span data-ttu-id="c5b1f-163">Ab .NET Core 2.1.400.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-163">Since .NET Core 2.1.400.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c5b1f-164">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c5b1f-164">.NET Core 1.x</span></span>](#tab/netcore1x)

`--configfile <FILE>`

<span data-ttu-id="c5b1f-165">Die NuGet-Konfigurationsdatei (*nuget.config*) für den Wiederherstellungsvorgang.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-165">The NuGet configuration file (*nuget.config*) to use for the restore operation.</span></span>

`--disable-parallel`

<span data-ttu-id="c5b1f-166">Deaktiviert paralleles Erstellen von mehreren Projekten.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-166">Disables restoring multiple projects in parallel.</span></span>

`-h|--help`

<span data-ttu-id="c5b1f-167">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-167">Prints out a short help for the command.</span></span>

`--ignore-failed-sources`

<span data-ttu-id="c5b1f-168">Bei fehlerhaften Quellen nur warnen, wenn Pakete die Versionsanforderung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-168">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

`--no-cache`

<span data-ttu-id="c5b1f-169">Gibt an, dass Pakete und HTTP-Anfragen nicht zwischengespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-169">Specifies to not cache packages and HTTP requests.</span></span>

`--no-dependencies`

<span data-ttu-id="c5b1f-170">Wenn Sie ein Projekt mit Projekt-zu-Projekt-Verweisen (P2P) wiederherstellen, stellen Sie das Stammprojekt wieder her und nicht die Verweise.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-170">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--packages <PACKAGES_DIRECTORY>`

<span data-ttu-id="c5b1f-171">Gibt das Verzeichnis für wiederhergestellte Pakete an.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-171">Specifies the directory for restored packages.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="c5b1f-172">Gibt eine Laufzeit für die Wiederherstellung des Pakets an.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-172">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="c5b1f-173">Wird für das Wiederherstellen von Paketen für Laufzeiten verwendet, die nicht explizit im `<RuntimeIdentifiers>`-Tag in der *.csproj*-Datei aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-173">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="c5b1f-174">Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="c5b1f-174">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="c5b1f-175">Es können mehrere RIDs bereitgestellt werden, indem diese Option mehrmals angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-175">Provide multiple RIDs by specifying this option multiple times.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="c5b1f-176">Gibt eine NuGet-Paketquelle an, die während des Wiederherstellungsvorgangs zu verwenden ist.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-176">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="c5b1f-177">Dadurch werden alle Quellen überschrieben, die in den *nuget.config*-Dateien angegeben sind. Die Datei *nuget.config* wird so gelesen, als wäre das `<packageSource>`-Element nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-177">This overrides all of the sources specified in the *nuget.config* files, effectively reading the *nuget.config* file as if the `<packageSource>` element was not there.</span></span> <span data-ttu-id="c5b1f-178">Es können mehrere Quellen bereitgestellt werden, indem diese Option mehrmals angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-178">Multiple sources can be provided by specifying this option multiple times.</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="c5b1f-179">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-179">Sets the verbosity level of the command.</span></span> <span data-ttu-id="c5b1f-180">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="c5b1f-180">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="c5b1f-181">Beispiele</span><span class="sxs-lookup"><span data-stu-id="c5b1f-181">Examples</span></span>

<span data-ttu-id="c5b1f-182">Wiederherstellen von Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="c5b1f-182">Restore dependencies and tools for the project in the current directory:</span></span>

`dotnet restore`

<span data-ttu-id="c5b1f-183">Wiederherstellen von Abhängigkeiten und Tools für das Projekt `app1` im vorgegebenen Pfad:</span><span class="sxs-lookup"><span data-stu-id="c5b1f-183">Restore dependencies and tools for the `app1` project found in the given path:</span></span>

`dotnet restore ~/projects/app1/app1.csproj`

<span data-ttu-id="c5b1f-184">Wiederherstellen der Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis mit dem bereitgestellten Dateipfad als Quelle:</span><span class="sxs-lookup"><span data-stu-id="c5b1f-184">Restore the dependencies and tools for the project in the current directory using the file path provided as the source:</span></span>

`dotnet restore -s c:\packages\mypackages`

<span data-ttu-id="c5b1f-185">Wiederherstellen der Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis mit den beiden bereitgestellten Dateipfaden als Quellen:</span><span class="sxs-lookup"><span data-stu-id="c5b1f-185">Restore the dependencies and tools for the project in the current directory using the two file paths provided as sources:</span></span>

`dotnet restore -s c:\packages\mypackages -s c:\packages\myotherpackages`

<span data-ttu-id="c5b1f-186">Wiederherstellen von Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis und nur Anzeige von nur minimaler Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="c5b1f-186">Restore dependencies and tools for the project in the current directory and shows only minimal output:</span></span>

`dotnet restore --verbosity minimal`
