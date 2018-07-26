---
title: dotnet restore-Befehl – .NET Core-CLI
description: Erfahren Sie mehr über das Wiederherstellen von Abhängigkeiten und projektspezifischen Tools mit dem Befehl dotnet-restore.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 0eaab1aa1bc52bd5b3c51a6ed2dd7a59c35a4aa5
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37960588"
---
# <a name="dotnet-restore"></a><span data-ttu-id="92c5c-103">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="92c5c-103">dotnet restore</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="92c5c-104">name</span><span class="sxs-lookup"><span data-stu-id="92c5c-104">Name</span></span>

<span data-ttu-id="92c5c-105">`dotnet restore`: Stellt die Abhängigkeiten und Tools eines Projekts wieder her</span><span class="sxs-lookup"><span data-stu-id="92c5c-105">`dotnet restore` - Restores the dependencies and tools of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="92c5c-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="92c5c-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="92c5c-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="92c5c-107">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--force] [--ignore-failed-sources] [--no-cache]
    [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity]
dotnet restore [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="92c5c-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="92c5c-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--ignore-failed-sources] [--no-cache]
    [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity]
dotnet restore [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="92c5c-109">Beschreibung </span><span class="sxs-lookup"><span data-stu-id="92c5c-109">Description</span></span>

<span data-ttu-id="92c5c-110">Der Befehl `dotnet restore` verwendet NuGet zum Wiederherstellen von Abhängigkeiten sowie projektspezifischen Tools, die in der Projektdatei angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="92c5c-110">The `dotnet restore` command uses NuGet to restore dependencies as well as project-specific tools that are specified in the project file.</span></span> <span data-ttu-id="92c5c-111">Die Wiederherstellung von Abhängigkeiten und Tools wird standardmäßig parallel ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="92c5c-111">By default, the restoration of dependencies and tools are executed in parallel.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="92c5c-112">Zum Wiederherstellen der Abhängigkeiten benötigt NuGet die Feeds, wo sich die Pakete befinden.</span><span class="sxs-lookup"><span data-stu-id="92c5c-112">To restore the dependencies, NuGet needs the feeds where the packages are located.</span></span> <span data-ttu-id="92c5c-113">Feeds werden in der Regel über die Konfigurationsdatei *NuGet.config* bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="92c5c-113">Feeds are usually provided via the *NuGet.config* configuration file.</span></span> <span data-ttu-id="92c5c-114">Eine standardmäßige Konfigurationsdatei wird bereitgestellt, wenn die CLI-Tools installiert sind.</span><span class="sxs-lookup"><span data-stu-id="92c5c-114">A default configuration file is provided when the CLI tools are installed.</span></span> <span data-ttu-id="92c5c-115">Sie geben zusätzliche Feeds an, indem Sie eine eigene *NuGet.config*-Datei im Projektverzeichnis erstellen.</span><span class="sxs-lookup"><span data-stu-id="92c5c-115">You specify additional feeds by creating your own *NuGet.config* file in the project directory.</span></span> <span data-ttu-id="92c5c-116">Sie können auch zusätzliche Feeds pro Aufruf an der Eingabeaufforderung angeben.</span><span class="sxs-lookup"><span data-stu-id="92c5c-116">You also specify additional feeds per invocation at a command prompt.</span></span>

<span data-ttu-id="92c5c-117">Für Abhängigkeiten geben Sie mithilfe des Arguments `--packages` an, wo die wiederhergestellten Pakete während der Wiederherstellung platziert werden.</span><span class="sxs-lookup"><span data-stu-id="92c5c-117">For dependencies, you specify where the restored packages are placed during the restore operation using the `--packages` argument.</span></span> <span data-ttu-id="92c5c-118">Wenn nichts angegeben wurde, wird der Standardcache des NuGet-Pakets verwendet. Er befindet sich im Verzeichnis `.nuget/packages` im Basisverzeichnis des Benutzers auf allen Betriebssystemen.</span><span class="sxs-lookup"><span data-stu-id="92c5c-118">If not specified, the default NuGet package cache is used, which is found in the `.nuget/packages` directory in the user's home directory on all operating systems.</span></span> <span data-ttu-id="92c5c-119">Zum Beispiel */home/user1* unter Linux oder *C:\Users\user1* unter Windows.</span><span class="sxs-lookup"><span data-stu-id="92c5c-119">For example, */home/user1* on Linux or *C:\Users\user1* on Windows.</span></span>

<span data-ttu-id="92c5c-120">Für projektspezifische Tools stellt `dotnet restore` zunächst das Paket wieder her, in dem sich das Tool befindet, und danach die Abhängigkeiten des Tools gemäß seiner Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="92c5c-120">For project-specific tooling, `dotnet restore` first restores the package in which the tool is packed, and then proceeds to restore the tool's dependencies as specified in its project file.</span></span>

<span data-ttu-id="92c5c-121">Das Verhalten des Befehls `dotnet restore` wird durch einige Einstellungen in der *NuGet.Config*-Datei (falls vorhanden) beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="92c5c-121">The behavior of the `dotnet restore` command is affected by some of the settings in the *Nuget.Config* file, if present.</span></span> <span data-ttu-id="92c5c-122">Das Festlegen von `globalPackagesFolder` in *NuGet.Config* platziert z.B. die wiederhergestellten NuGet-Pakete in den angegebenen Ordner.</span><span class="sxs-lookup"><span data-stu-id="92c5c-122">For example, setting the `globalPackagesFolder` in *NuGet.Config* places the restored NuGet packages in the specified folder.</span></span> <span data-ttu-id="92c5c-123">Dies ist eine Alternative zur Angabe der Option `--packages` im `dotnet restore`-Befehl.</span><span class="sxs-lookup"><span data-stu-id="92c5c-123">This is an alternative to specifying the `--packages` option on the `dotnet restore` command.</span></span> <span data-ttu-id="92c5c-124">Weitere Informationen finden Sie im [NuGet.Config-Referenzthema](/nuget/schema/nuget-config-file).</span><span class="sxs-lookup"><span data-stu-id="92c5c-124">For more information, see the [NuGet.Config reference](/nuget/schema/nuget-config-file).</span></span>

## <a name="implicit-dotnet-restore"></a><span data-ttu-id="92c5c-125">Impliziter `dotnet restore`</span><span class="sxs-lookup"><span data-stu-id="92c5c-125">Implicit `dotnet restore`</span></span>

<span data-ttu-id="92c5c-126">Ab .NET Core 2.0 wird `dotnet restore` bei Bedarf implizit ausgeführt, wenn Sie die folgenden Befehle ausführen:</span><span class="sxs-lookup"><span data-stu-id="92c5c-126">Starting with .NET Core 2.0, `dotnet restore` is run implicitly if necessary when you issue the following commands:</span></span>

- [`dotnet new`](dotnet-new.md)
- [`dotnet build`](dotnet-build.md)
- [`dotnet build-server`](dotnet-build-server.md)
- [`dotnet run`](dotnet-run.md)
- [`dotnet test`](dotnet-test.md)
- [`dotnet publish`](dotnet-publish.md)
- [`dotnet pack`](dotnet-pack.md)

<span data-ttu-id="92c5c-127">In den meisten Fällen müssen Sie den `dotnet restore`-Befehl nicht länger explizit verwenden.</span><span class="sxs-lookup"><span data-stu-id="92c5c-127">In most cases, you no longer need to explicitly use the `dotnet restore` command.</span></span>

<span data-ttu-id="92c5c-128">In manchen Fällen kann es sich als unpraktisch erweisen, `dotnet restore` implizit auszuführen.</span><span class="sxs-lookup"><span data-stu-id="92c5c-128">Sometimes, it might be inconvenient to run `dotnet restore` implicitly.</span></span> <span data-ttu-id="92c5c-129">Zum Beispiel müssen einige automatisierte Systeme, wie etwa Buildsysteme, `dotnet restore` explizit aufrufen, um zu kontrollieren, wann die Wiederherstellung stattfindet, damit sie die Netzwerknutzung steuern können.</span><span class="sxs-lookup"><span data-stu-id="92c5c-129">For example, some automated systems, such as build systems, need to call `dotnet restore` explicitly to control when the restore occurs so that they can control network usage.</span></span> <span data-ttu-id="92c5c-130">Sie können das Flag `--no-restore` mit einem beliebigen Befehl aus dieser Reihe verwenden, um die implizite Wiederherstellung zu deaktivieren und eine implizite Ausführung von `dotnet restore` zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="92c5c-130">To prevent `dotnet restore` from running implicitly, you can use the `--no-restore` flag with any of these commands to disable implicit restore.</span></span>

## <a name="arguments"></a><span data-ttu-id="92c5c-131">Argumente</span><span class="sxs-lookup"><span data-stu-id="92c5c-131">Arguments</span></span>

`ROOT`

<span data-ttu-id="92c5c-132">Optionaler Pfad zur wiederherzustellenden Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="92c5c-132">Optional path to the project file to restore.</span></span>

## <a name="options"></a><span data-ttu-id="92c5c-133">Optionen</span><span class="sxs-lookup"><span data-stu-id="92c5c-133">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="92c5c-134">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="92c5c-134">.NET Core 2.x</span></span>](#tab/netcore2x)

`--configfile <FILE>`

<span data-ttu-id="92c5c-135">Die NuGet-Konfigurationsdatei (*NuGet.config*) für den Wiederherstellungsvorgang.</span><span class="sxs-lookup"><span data-stu-id="92c5c-135">The NuGet configuration file (*NuGet.config*) to use for the restore operation.</span></span>

`--disable-parallel`

<span data-ttu-id="92c5c-136">Deaktiviert paralleles Erstellen von mehreren Projekten.</span><span class="sxs-lookup"><span data-stu-id="92c5c-136">Disables restoring multiple projects in parallel.</span></span>

`--force`

<span data-ttu-id="92c5c-137">Erzwingt das Auflösen aller Abhängigkeiten, auch wenn die letzte Wiederherstellung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="92c5c-137">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="92c5c-138">Dieses Flag anzugeben, entspricht dem Löschen der Datei *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="92c5c-138">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="92c5c-139">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="92c5c-139">Prints out a short help for the command.</span></span>

`--ignore-failed-sources`

<span data-ttu-id="92c5c-140">Bei fehlerhaften Quellen nur warnen, wenn Pakete die Versionsanforderung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="92c5c-140">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

`--no-cache`

<span data-ttu-id="92c5c-141">Gibt an, dass Pakete und HTTP-Anfragen nicht zwischengespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="92c5c-141">Specifies to not cache packages and HTTP requests.</span></span>

`--no-dependencies`

<span data-ttu-id="92c5c-142">Wenn Sie ein Projekt mit Projekt-zu-Projekt-Verweisen (P2P) wiederherstellen, stellen Sie das Stammprojekt wieder her und nicht die Verweise.</span><span class="sxs-lookup"><span data-stu-id="92c5c-142">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--packages <PACKAGES_DIRECTORY>`

<span data-ttu-id="92c5c-143">Gibt das Verzeichnis für wiederhergestellte Pakete an.</span><span class="sxs-lookup"><span data-stu-id="92c5c-143">Specifies the directory for restored packages.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="92c5c-144">Gibt eine Laufzeit für die Wiederherstellung des Pakets an.</span><span class="sxs-lookup"><span data-stu-id="92c5c-144">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="92c5c-145">Wird für das Wiederherstellen von Paketen für Laufzeiten verwendet, die nicht explizit im `<RuntimeIdentifiers>`-Tag in der *.csproj*-Datei aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="92c5c-145">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="92c5c-146">Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="92c5c-146">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="92c5c-147">Es können mehrere RIDs bereitgestellt werden, indem diese Option mehrmals angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="92c5c-147">Provide multiple RIDs by specifying this option multiple times.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="92c5c-148">Gibt eine NuGet-Paketquelle an, die während des Wiederherstellungsvorgangs zu verwenden ist.</span><span class="sxs-lookup"><span data-stu-id="92c5c-148">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="92c5c-149">Diese Einstellung überschreibt alle Quellen, die in den *NuGet.config*-Dateien angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="92c5c-149">This setting overrides all of the sources specified in the *NuGet.config* files.</span></span> <span data-ttu-id="92c5c-150">Es können mehrere Quellen bereitgestellt werden, indem diese Option mehrmals angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="92c5c-150">Multiple sources can be provided by specifying this option multiple times.</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="92c5c-151">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="92c5c-151">Sets the verbosity level of the command.</span></span> <span data-ttu-id="92c5c-152">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="92c5c-152">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="92c5c-153">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="92c5c-153">.NET Core 1.x</span></span>](#tab/netcore1x)

`--configfile <FILE>`

<span data-ttu-id="92c5c-154">Die NuGet-Konfigurationsdatei (*NuGet.config*) für den Wiederherstellungsvorgang.</span><span class="sxs-lookup"><span data-stu-id="92c5c-154">The NuGet configuration file (*NuGet.config*) to use for the restore operation.</span></span>

`--disable-parallel`

<span data-ttu-id="92c5c-155">Deaktiviert paralleles Erstellen von mehreren Projekten.</span><span class="sxs-lookup"><span data-stu-id="92c5c-155">Disables restoring multiple projects in parallel.</span></span>

`-h|--help`

<span data-ttu-id="92c5c-156">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="92c5c-156">Prints out a short help for the command.</span></span>

`--ignore-failed-sources`

<span data-ttu-id="92c5c-157">Bei fehlerhaften Quellen nur warnen, wenn Pakete die Versionsanforderung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="92c5c-157">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

`--no-cache`

<span data-ttu-id="92c5c-158">Gibt an, dass Pakete und HTTP-Anfragen nicht zwischengespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="92c5c-158">Specifies to not cache packages and HTTP requests.</span></span>

`--no-dependencies`

<span data-ttu-id="92c5c-159">Wenn Sie ein Projekt mit Projekt-zu-Projekt-Verweisen (P2P) wiederherstellen, stellen Sie das Stammprojekt wieder her und nicht die Verweise.</span><span class="sxs-lookup"><span data-stu-id="92c5c-159">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--packages <PACKAGES_DIRECTORY>`

<span data-ttu-id="92c5c-160">Gibt das Verzeichnis für wiederhergestellte Pakete an.</span><span class="sxs-lookup"><span data-stu-id="92c5c-160">Specifies the directory for restored packages.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="92c5c-161">Gibt eine Laufzeit für die Wiederherstellung des Pakets an.</span><span class="sxs-lookup"><span data-stu-id="92c5c-161">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="92c5c-162">Wird für das Wiederherstellen von Paketen für Laufzeiten verwendet, die nicht explizit im `<RuntimeIdentifiers>`-Tag in der *.csproj*-Datei aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="92c5c-162">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="92c5c-163">Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="92c5c-163">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="92c5c-164">Es können mehrere RIDs bereitgestellt werden, indem diese Option mehrmals angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="92c5c-164">Provide multiple RIDs by specifying this option multiple times.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="92c5c-165">Gibt eine NuGet-Paketquelle an, die während des Wiederherstellungsvorgangs zu verwenden ist.</span><span class="sxs-lookup"><span data-stu-id="92c5c-165">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="92c5c-166">Dies überschreibt alle Quellen, die in den *NuGet.config*-Dateien angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="92c5c-166">This overrides all of the sources specified in the *NuGet.config* files.</span></span> <span data-ttu-id="92c5c-167">Es können mehrere Quellen bereitgestellt werden, indem diese Option mehrmals angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="92c5c-167">Multiple sources can be provided by specifying this option multiple times.</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="92c5c-168">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="92c5c-168">Sets the verbosity level of the command.</span></span> <span data-ttu-id="92c5c-169">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="92c5c-169">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="92c5c-170">Beispiele</span><span class="sxs-lookup"><span data-stu-id="92c5c-170">Examples</span></span>

<span data-ttu-id="92c5c-171">Wiederherstellen von Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="92c5c-171">Restore dependencies and tools for the project in the current directory:</span></span>

`dotnet restore`

<span data-ttu-id="92c5c-172">Wiederherstellen von Abhängigkeiten und Tools für das Projekt `app1` im vorgegebenen Pfad:</span><span class="sxs-lookup"><span data-stu-id="92c5c-172">Restore dependencies and tools for the `app1` project found in the given path:</span></span>

`dotnet restore ~/projects/app1/app1.csproj`

<span data-ttu-id="92c5c-173">Wiederherstellen der Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis mit dem bereitgestellten Dateipfad als Quelle:</span><span class="sxs-lookup"><span data-stu-id="92c5c-173">Restore the dependencies and tools for the project in the current directory using the file path provided as the source:</span></span>

`dotnet restore -s c:\packages\mypackages`

<span data-ttu-id="92c5c-174">Wiederherstellen der Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis mit den beiden bereitgestellten Dateipfaden als Quellen:</span><span class="sxs-lookup"><span data-stu-id="92c5c-174">Restore the dependencies and tools for the project in the current directory using the two file paths provided as sources:</span></span>

`dotnet restore -s c:\packages\mypackages -s c:\packages\myotherpackages`

<span data-ttu-id="92c5c-175">Wiederherstellen von Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis und nur Anzeige von nur minimaler Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="92c5c-175">Restore dependencies and tools for the project in the current directory and shows only minimal output:</span></span>

`dotnet restore --verbosity minimal`
