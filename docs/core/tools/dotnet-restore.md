---
title: "dotnet restore-Befehl – .NET Core-CLI"
description: "Erfahren Sie mehr über das Wiederherstellen von Abhängigkeiten und projektspezifischen Tools mit dem Befehl dotnet-restore."
keywords: dotnet-restore, CLI, CLI-Befehl, .NET Core
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.translationtype: HT
ms.sourcegitcommit: 019461964ba63d874ce86511474aa37b4342bbc4
ms.openlocfilehash: 86de979257d4e1be3a29d8876494b7f4966e5b1c
ms.contentlocale: de-de
ms.lasthandoff: 08/29/2017

---
# <a name="dotnet-restore"></a><span data-ttu-id="d61f4-104">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="d61f4-104">dotnet restore</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="d61f4-105">Name</span><span class="sxs-lookup"><span data-stu-id="d61f4-105">Name</span></span>

<span data-ttu-id="d61f4-106">`dotnet restore`: Stellt die Abhängigkeiten und Tools eines Projekts wieder her</span><span class="sxs-lookup"><span data-stu-id="d61f4-106">`dotnet restore` - Restores the dependencies and tools of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d61f4-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="d61f4-107">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d61f4-108">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d61f4-108">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--force] [--ignore-failed-sources] [--no-cache] [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity]
dotnet restore [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d61f4-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d61f4-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--ignore-failed-sources] [--no-cache] [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity]
dotnet restore [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="d61f4-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d61f4-110">Description</span></span>

<span data-ttu-id="d61f4-111">Der Befehl `dotnet restore` verwendet NuGet zum Wiederherstellen von Abhängigkeiten sowie projektspezifischen Tools, die in der Projektdatei angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="d61f4-111">The `dotnet restore` command uses NuGet to restore dependencies as well as project-specific tools that are specified in the project file.</span></span> <span data-ttu-id="d61f4-112">Standardmäßig wird die Wiederherstellung von Abhängigkeiten und Tools parallel ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d61f4-112">By default, the restoration of dependencies and tools are performed in parallel.</span></span>

<span data-ttu-id="d61f4-113">Zum Wiederherstellen der Abhängigkeiten benötigt NuGet die Feeds, wo sich die Pakete befinden.</span><span class="sxs-lookup"><span data-stu-id="d61f4-113">In order to restore the dependencies, NuGet needs the feeds where the packages are located.</span></span> <span data-ttu-id="d61f4-114">Feeds werden in der Regel über die Konfigurationsdatei *NuGet.config* bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="d61f4-114">Feeds are usually provided via the *NuGet.config* configuration file.</span></span> <span data-ttu-id="d61f4-115">Eine standardmäßige Konfigurationsdatei wird bereitgestellt, wenn die CLI-Tools installiert sind.</span><span class="sxs-lookup"><span data-stu-id="d61f4-115">A default configuration file is provided when the CLI tools are installed.</span></span> <span data-ttu-id="d61f4-116">Sie geben zusätzliche Feeds an, indem Sie eine eigene *NuGet.config*-Datei im Projektverzeichnis erstellen.</span><span class="sxs-lookup"><span data-stu-id="d61f4-116">You specify additional feeds by creating your own *NuGet.config* file in the project directory.</span></span> <span data-ttu-id="d61f4-117">Sie können auch zusätzliche Feeds pro Aufruf an der Eingabeaufforderung angeben.</span><span class="sxs-lookup"><span data-stu-id="d61f4-117">You also specify additional feeds per invocation at a command prompt.</span></span>

<span data-ttu-id="d61f4-118">Für Abhängigkeiten geben Sie mithilfe des Arguments `--packages` an, wo die wiederhergestellten Pakete während der Wiederherstellung platziert werden.</span><span class="sxs-lookup"><span data-stu-id="d61f4-118">For dependencies, you specify where the restored packages are placed during the restore operation using the `--packages` argument.</span></span> <span data-ttu-id="d61f4-119">Wenn nichts angegeben wurde, wird der Standardcache des NuGet-Pakets verwendet. Er befindet sich im Verzeichnis `.nuget/packages` im Basisverzeichnis des Benutzers auf allen Betriebssystemen (z.B. */home/user1* unter Linux oder *C:\Users\user1* unter Windows).</span><span class="sxs-lookup"><span data-stu-id="d61f4-119">If not specified, the default NuGet package cache is used, which is found in the `.nuget/packages` directory in the user's home directory on all operating systems (for example, */home/user1* on Linux or *C:\Users\user1* on Windows).</span></span>

<span data-ttu-id="d61f4-120">Für projektspezifische Tools stellt `dotnet restore` zunächst das Paket wieder her, in dem sich das Tool befindet, und danach die Abhängigkeiten des Tools gemäß seiner Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="d61f4-120">For project-specific tooling, `dotnet restore` first restores the package in which the tool is packed, and then proceeds to restore the tool's dependencies as specified in its project file.</span></span>

<span data-ttu-id="d61f4-121">Das Verhalten des Befehls `dotnet restore` wird durch einige Einstellungen in der *NuGet.Config*-Datei (falls vorhanden) beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="d61f4-121">The behavior of the `dotnet restore` command is affected by some of the settings in the *Nuget.Config* file, if present.</span></span> <span data-ttu-id="d61f4-122">Das Festlegen von `globalPackagesFolder` in *NuGet.Config* platziert z.B. die wiederhergestellten NuGet-Pakete in den angegebenen Ordner.</span><span class="sxs-lookup"><span data-stu-id="d61f4-122">For example, setting the `globalPackagesFolder` in *NuGet.Config* places the restored NuGet packages in the specified folder.</span></span> <span data-ttu-id="d61f4-123">Dies ist eine Alternative zur Angabe der Option `--packages` im `dotnet restore`-Befehl.</span><span class="sxs-lookup"><span data-stu-id="d61f4-123">This is an alternative to specifying the `--packages` option on the `dotnet restore` command.</span></span> <span data-ttu-id="d61f4-124">Weitere Informationen finden Sie im [NuGet.Config-Referenzthema](/nuget/schema/nuget-config-file).</span><span class="sxs-lookup"><span data-stu-id="d61f4-124">For more information, see the [NuGet.Config reference](/nuget/schema/nuget-config-file).</span></span>

## <a name="arguments"></a><span data-ttu-id="d61f4-125">Argumente</span><span class="sxs-lookup"><span data-stu-id="d61f4-125">Arguments</span></span>

`ROOT`

<span data-ttu-id="d61f4-126">Optionaler Pfad zur wiederherzustellenden Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="d61f4-126">Optional path to the project file to restore.</span></span>

## <a name="options"></a><span data-ttu-id="d61f4-127">Optionen</span><span class="sxs-lookup"><span data-stu-id="d61f4-127">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d61f4-128">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d61f4-128">.NET Core 2.x</span></span>](#tab/netcore2x)

`--configfile <FILE>`

<span data-ttu-id="d61f4-129">Die NuGet-Konfigurationsdatei (*NuGet.config*) für den Wiederherstellungsvorgang.</span><span class="sxs-lookup"><span data-stu-id="d61f4-129">The NuGet configuration file (*NuGet.config*) to use for the restore operation.</span></span>

`--disable-parallel`

<span data-ttu-id="d61f4-130">Deaktiviert paralleles Erstellen von mehreren Projekten.</span><span class="sxs-lookup"><span data-stu-id="d61f4-130">Disables restoring multiple projects in parallel.</span></span>

`--force`

<span data-ttu-id="d61f4-131">Erzwingt das Auflösen aller Abhängigkeiten, auch wenn die letzte Wiederherstellung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="d61f4-131">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="d61f4-132">Dies entspricht dem Löschen der Datei *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="d61f4-132">This is equivalent to deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="d61f4-133">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="d61f4-133">Prints out a short help for the command.</span></span>

`--ignore-failed-sources`

<span data-ttu-id="d61f4-134">Bei fehlerhaften Quellen nur warnen, wenn Pakete die Versionsanforderung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="d61f4-134">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

`--no-cache`

<span data-ttu-id="d61f4-135">Gibt an, dass Pakete und HTTP-Anfragen nicht zwischengespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="d61f4-135">Specifies to not cache packages and HTTP requests.</span></span>

`--no-dependencies`

<span data-ttu-id="d61f4-136">Wenn Sie ein Projekt mit Projekt-zu-Projekt-Verweisen (P2P) wiederherstellen, stellen Sie das Stammprojekt wieder her und nicht die Verweise.</span><span class="sxs-lookup"><span data-stu-id="d61f4-136">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--packages <PACKAGES_DIRECTORY>`

<span data-ttu-id="d61f4-137">Gibt das Verzeichnis für wiederhergestellte Pakete an.</span><span class="sxs-lookup"><span data-stu-id="d61f4-137">Specifies the directory for restored packages.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="d61f4-138">Gibt eine Laufzeit für die Wiederherstellung des Pakets an.</span><span class="sxs-lookup"><span data-stu-id="d61f4-138">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="d61f4-139">Wird für das Wiederherstellen von Paketen für Laufzeiten verwendet, die nicht explizit im `<RuntimeIdentifiers>`-Tag in der *.csproj*-Datei aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="d61f4-139">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="d61f4-140">Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="d61f4-140">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="d61f4-141">Es können mehrere RIDs bereitgestellt werden, indem diese Option mehrmals angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d61f4-141">Provide multiple RIDs by specifying this option multiple times.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="d61f4-142">Gibt eine NuGet-Paketquelle an, die während des Wiederherstellungsvorgangs zu verwenden ist.</span><span class="sxs-lookup"><span data-stu-id="d61f4-142">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="d61f4-143">Dies überschreibt alle Quellen, die in der/den *NuGet.config*-Datei(en) angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="d61f4-143">This overrides all of the sources specified in the *NuGet.config* file(s).</span></span> <span data-ttu-id="d61f4-144">Es können mehrere Quellen bereitgestellt werden, indem diese Option mehrmals angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d61f4-144">Multiple sources can be provided by specifying this option multiple times.</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="d61f4-145">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="d61f4-145">Sets the verbosity level of the command.</span></span> <span data-ttu-id="d61f4-146">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="d61f4-146">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d61f4-147">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d61f4-147">.NET Core 1.x</span></span>](#tab/netcore1x)

`--configfile <FILE>`

<span data-ttu-id="d61f4-148">Die NuGet-Konfigurationsdatei (*NuGet.config*) für den Wiederherstellungsvorgang.</span><span class="sxs-lookup"><span data-stu-id="d61f4-148">The NuGet configuration file (*NuGet.config*) to use for the restore operation.</span></span>

`--disable-parallel`

<span data-ttu-id="d61f4-149">Deaktiviert paralleles Erstellen von mehreren Projekten.</span><span class="sxs-lookup"><span data-stu-id="d61f4-149">Disables restoring multiple projects in parallel.</span></span>

`-h|--help`

<span data-ttu-id="d61f4-150">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="d61f4-150">Prints out a short help for the command.</span></span>

`--ignore-failed-sources`

<span data-ttu-id="d61f4-151">Bei fehlerhaften Quellen nur warnen, wenn Pakete die Versionsanforderung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="d61f4-151">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

`--no-cache`

<span data-ttu-id="d61f4-152">Gibt an, dass Pakete und HTTP-Anfragen nicht zwischengespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="d61f4-152">Specifies to not cache packages and HTTP requests.</span></span>

`--no-dependencies`

<span data-ttu-id="d61f4-153">Wenn Sie ein Projekt mit Projekt-zu-Projekt-Verweisen (P2P) wiederherstellen, stellen Sie das Stammprojekt wieder her und nicht die Verweise.</span><span class="sxs-lookup"><span data-stu-id="d61f4-153">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--packages <PACKAGES_DIRECTORY>`

<span data-ttu-id="d61f4-154">Gibt das Verzeichnis für wiederhergestellte Pakete an.</span><span class="sxs-lookup"><span data-stu-id="d61f4-154">Specifies the directory for restored packages.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="d61f4-155">Gibt eine Laufzeit für die Wiederherstellung des Pakets an.</span><span class="sxs-lookup"><span data-stu-id="d61f4-155">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="d61f4-156">Wird für das Wiederherstellen von Paketen für Laufzeiten verwendet, die nicht explizit im `<RuntimeIdentifiers>`-Tag in der *.csproj*-Datei aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="d61f4-156">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="d61f4-157">Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="d61f4-157">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="d61f4-158">Es können mehrere RIDs bereitgestellt werden, indem diese Option mehrmals angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d61f4-158">Provide multiple RIDs by specifying this option multiple times.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="d61f4-159">Gibt eine NuGet-Paketquelle an, die während des Wiederherstellungsvorgangs zu verwenden ist.</span><span class="sxs-lookup"><span data-stu-id="d61f4-159">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="d61f4-160">Dies überschreibt alle Quellen, die in der/den *NuGet.config*-Datei(en) angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="d61f4-160">This overrides all of the sources specified in the *NuGet.config* file(s).</span></span> <span data-ttu-id="d61f4-161">Es können mehrere Quellen bereitgestellt werden, indem diese Option mehrmals angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d61f4-161">Multiple sources can be provided by specifying this option multiple times.</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="d61f4-162">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="d61f4-162">Sets the verbosity level of the command.</span></span> <span data-ttu-id="d61f4-163">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="d61f4-163">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="d61f4-164">Beispiele</span><span class="sxs-lookup"><span data-stu-id="d61f4-164">Examples</span></span>

<span data-ttu-id="d61f4-165">Wiederherstellen von Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="d61f4-165">Restore dependencies and tools for the project in the current directory:</span></span>

`dotnet restore`

<span data-ttu-id="d61f4-166">Wiederherstellen von Abhängigkeiten und Tools für das Projekt `app1` im vorgegebenen Pfad:</span><span class="sxs-lookup"><span data-stu-id="d61f4-166">Restore dependencies and tools for the `app1` project found in the given path:</span></span>

`dotnet restore ~/projects/app1/app1.csproj`

<span data-ttu-id="d61f4-167">Wiederherstellen der Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis mit dem bereitgestellten Dateipfad als Quelle:</span><span class="sxs-lookup"><span data-stu-id="d61f4-167">Restore the dependencies and tools for the project in the current directory using the file path provided as the source:</span></span>

`dotnet restore -s c:\packages\mypackages`

<span data-ttu-id="d61f4-168">Wiederherstellen der Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis mit den beiden bereitgestellten Dateipfaden als Quellen:</span><span class="sxs-lookup"><span data-stu-id="d61f4-168">Restore the dependencies and tools for the project in the current directory using the two file paths provided as sources:</span></span>

`dotnet restore -s c:\packages\mypackages -s c:\packages\myotherpackages`

<span data-ttu-id="d61f4-169">Wiederherstellen von Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis und nur Anzeige von nur minimaler Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="d61f4-169">Restore dependencies and tools for the project in the current directory and shows only minimal output:</span></span>

`dotnet restore --verbosity minimal`

