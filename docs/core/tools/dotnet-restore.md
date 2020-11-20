---
title: Befehl „dotnet restore“
description: Erfahren Sie mehr über das Wiederherstellen von Abhängigkeiten und projektspezifischen Tools mit dem Befehl dotnet-restore.
ms.date: 02/27/2020
ms.openlocfilehash: dcb68d6c690f2e12b61cfdfa6dc288bd474721c1
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634402"
---
# <a name="dotnet-restore"></a><span data-ttu-id="fcf7c-103">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="fcf7c-103">dotnet restore</span></span>

<span data-ttu-id="fcf7c-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="fcf7c-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="fcf7c-105">name</span><span class="sxs-lookup"><span data-stu-id="fcf7c-105">Name</span></span>

<span data-ttu-id="fcf7c-106">`dotnet restore`: Stellt die Abhängigkeiten und Tools eines Projekts wieder her</span><span class="sxs-lookup"><span data-stu-id="fcf7c-106">`dotnet restore` - Restores the dependencies and tools of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="fcf7c-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="fcf7c-107">Synopsis</span></span>

```dotnetcli
dotnet restore [<ROOT>] [--configfile <FILE>] [--disable-parallel]
    [-f|--force] [--force-evaluate] [--ignore-failed-sources]
    [--interactive] [--lock-file-path <LOCK_FILE_PATH>] [--locked-mode]
    [--no-cache] [--no-dependencies] [--packages <PACKAGES_DIRECTORY>]
    [-r|--runtime <RUNTIME_IDENTIFIER>] [-s|--source <SOURCE>]
    [--use-lock-file] [-v|--verbosity <LEVEL>]

dotnet restore -h|--help
```

## <a name="description"></a><span data-ttu-id="fcf7c-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fcf7c-108">Description</span></span>

<span data-ttu-id="fcf7c-109">Der Befehl `dotnet restore` verwendet NuGet zum Wiederherstellen von Abhängigkeiten sowie projektspezifischen Tools, die in der Projektdatei angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-109">The `dotnet restore` command uses NuGet to restore dependencies as well as project-specific tools that are specified in the project file.</span></span>  <span data-ttu-id="fcf7c-110">In den meisten Fällen müssen Sie nicht explizit den Befehl `dotnet restore` verwenden, da eine NuGet-Wiederherstellung bei Bedarf implizit ausgeführt wird, wenn Sie die folgenden Befehle ausführen:</span><span class="sxs-lookup"><span data-stu-id="fcf7c-110">In most cases, you don't need to explicitly use the `dotnet restore` command, since a NuGet restore is run implicitly if necessary when you run the following commands:</span></span>

- [`dotnet new`](dotnet-new.md)
- [`dotnet build`](dotnet-build.md)
- [`dotnet build-server`](dotnet-build-server.md)
- [`dotnet run`](dotnet-run.md)
- [`dotnet test`](dotnet-test.md)
- [`dotnet publish`](dotnet-publish.md)
- [`dotnet pack`](dotnet-pack.md)

<span data-ttu-id="fcf7c-111">Manchmal kann es unpraktisch sein, die implizite NuGet-Wiederherstellung mit diesen Befehlen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-111">Sometimes, it might be inconvenient to run the implicit NuGet restore with these commands.</span></span> <span data-ttu-id="fcf7c-112">Zum Beispiel müssen einige automatisierte Systeme, wie etwa Buildsysteme, `dotnet restore` explizit aufrufen, um zu kontrollieren, wann die Wiederherstellung stattfindet, damit sie die Netzwerknutzung steuern können.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-112">For example, some automated systems, such as build systems, need to call `dotnet restore` explicitly to control when the restore occurs so that they can control network usage.</span></span> <span data-ttu-id="fcf7c-113">Sie können das Flag `--no-restore` mit einem beliebigen dieser Befehle verwenden, um die implizite Wiederherstellung zu deaktivieren und eine implizite NuGet-Wiederherstellung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-113">To prevent the implicit NuGet restore, you can use the `--no-restore` flag with any of these commands to disable implicit restore.</span></span>

### <a name="specify-feeds"></a><span data-ttu-id="fcf7c-114">Angeben von Feeds</span><span class="sxs-lookup"><span data-stu-id="fcf7c-114">Specify feeds</span></span>

<span data-ttu-id="fcf7c-115">Zum Wiederherstellen der Abhängigkeiten benötigt NuGet die Feeds, wo sich die Pakete befinden.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-115">To restore the dependencies, NuGet needs the feeds where the packages are located.</span></span> <span data-ttu-id="fcf7c-116">Feeds werden normalerweise über die *nuget.config*-Konfigurationsdatei bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-116">Feeds are usually provided via the *nuget.config* configuration file.</span></span> <span data-ttu-id="fcf7c-117">Eine Standardkonfigurationsdatei wird bereitgestellt, wenn das .NET SDK installiert sind.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-117">A default configuration file is provided when the .NET SDK is installed.</span></span> <span data-ttu-id="fcf7c-118">Führen Sie eine der folgenden Schritte durch, um zusätzliche Feeds anzugeben:</span><span class="sxs-lookup"><span data-stu-id="fcf7c-118">To specify additional feeds, do one of the following:</span></span>

- <span data-ttu-id="fcf7c-119">Erstellen Sie eine eigene *nuget.config*-Datei im Projektverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-119">Create your own *nuget.config* file in the project directory.</span></span> <span data-ttu-id="fcf7c-120">Weitere Informationen finden Sie unter [Gängige NuGet-Konfigurationen](/nuget/consume-packages/configuring-nuget-behavior) und unter [Unterschiede bei „nuget.config“](#nugetconfig-differences) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-120">For more information, see [Common NuGet configurations](/nuget/consume-packages/configuring-nuget-behavior) and [nuget.config differences](#nugetconfig-differences) later in this article.</span></span>
- <span data-ttu-id="fcf7c-121">Verwenden Sie `dotnet nuget`-Befehle wie [`dotnet nuget add source`](dotnet-nuget-add-source.md).</span><span class="sxs-lookup"><span data-stu-id="fcf7c-121">Use `dotnet nuget` commands such as [`dotnet nuget add source`](dotnet-nuget-add-source.md).</span></span>

<span data-ttu-id="fcf7c-122">Sie können die *nuget.config-* -Feeds mit der `-s`-Option überschreiben.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-122">You can override the *nuget.config* feeds with the `-s` option.</span></span>

<span data-ttu-id="fcf7c-123">Informationen zur Verwendung authentifizierter Feeds finden Sie unter [Nutzen von Paketen aus authentifizierten Feeds](/nuget/consume-packages/consuming-packages-authenticated-feeds).</span><span class="sxs-lookup"><span data-stu-id="fcf7c-123">For information about how to use authenticated feeds, see [Consuming packages from authenticated feeds](/nuget/consume-packages/consuming-packages-authenticated-feeds).</span></span>

### <a name="global-packages-folder"></a><span data-ttu-id="fcf7c-124">Ordner für globale Pakete</span><span class="sxs-lookup"><span data-stu-id="fcf7c-124">Global packages folder</span></span>

<span data-ttu-id="fcf7c-125">Für Abhängigkeiten können Sie mithilfe des Arguments `--packages` angeben, wo die wiederhergestellten Pakete während der Wiederherstellung platziert werden.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-125">For dependencies, you can specify where the restored packages are placed during the restore operation using the `--packages` argument.</span></span> <span data-ttu-id="fcf7c-126">Wenn nichts angegeben wurde, wird der Standardcache des NuGet-Pakets verwendet. Er befindet sich im Verzeichnis `.nuget/packages` im Basisverzeichnis des Benutzers auf allen Betriebssystemen.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-126">If not specified, the default NuGet package cache is used, which is found in the `.nuget/packages` directory in the user's home directory on all operating systems.</span></span> <span data-ttu-id="fcf7c-127">Zum Beispiel */home/user1* unter Linux oder *C:\Users\user1* unter Windows.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-127">For example, */home/user1* on Linux or *C:\Users\user1* on Windows.</span></span>

### <a name="project-specific-tooling"></a><span data-ttu-id="fcf7c-128">Projektspezifische Tools</span><span class="sxs-lookup"><span data-stu-id="fcf7c-128">Project-specific tooling</span></span>

<span data-ttu-id="fcf7c-129">Für projektspezifische Tools stellt `dotnet restore` zunächst das Paket wieder her, in dem sich das Tool befindet, und danach die Abhängigkeiten des Tools gemäß seiner Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-129">For project-specific tooling, `dotnet restore` first restores the package in which the tool is packed, and then proceeds to restore the tool's dependencies as specified in its project file.</span></span>

### <a name="nugetconfig-differences"></a><span data-ttu-id="fcf7c-130">Unterschiede bei „nuget.config“</span><span class="sxs-lookup"><span data-stu-id="fcf7c-130">nuget.config differences</span></span>

<span data-ttu-id="fcf7c-131">Das Verhalten des Befehls `dotnet restore` wird durch Einstellungen in der *nuget.config*-Datei (falls vorhanden) beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-131">The behavior of the `dotnet restore` command is affected by the settings in the *nuget.config* file, if present.</span></span> <span data-ttu-id="fcf7c-132">Das Festlegen von `globalPackagesFolder` in *nuget.config* platziert z. B. die wiederhergestellten NuGet-Pakete in den angegebenen Ordner.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-132">For example, setting the `globalPackagesFolder` in *nuget.config* places the restored NuGet packages in the specified folder.</span></span> <span data-ttu-id="fcf7c-133">Dies ist eine Alternative zur Angabe der Option `--packages` im `dotnet restore`-Befehl.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-133">This is an alternative to specifying the `--packages` option on the `dotnet restore` command.</span></span> <span data-ttu-id="fcf7c-134">Weitere Informationen finden Sie in der [Referenz zu „nuget.config“](/nuget/schema/nuget-config-file).</span><span class="sxs-lookup"><span data-stu-id="fcf7c-134">For more information, see the [nuget.config reference](/nuget/schema/nuget-config-file).</span></span>

<span data-ttu-id="fcf7c-135">Es gibt drei bestimmte Einstellungen, die von `dotnet restore` ignoriert werden:</span><span class="sxs-lookup"><span data-stu-id="fcf7c-135">There are three specific settings that `dotnet restore` ignores:</span></span>

- [<span data-ttu-id="fcf7c-136">bindingRedirects</span><span class="sxs-lookup"><span data-stu-id="fcf7c-136">bindingRedirects</span></span>](/nuget/schema/nuget-config-file#bindingredirects-section)

  <span data-ttu-id="fcf7c-137">Bindungsumleitungen funktionieren nicht mit `<PackageReference>`-Elementen, und .NET unterstützt nur `<PackageReference>`-Elemente für NuGet-Pakete.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-137">Binding redirects don't work with `<PackageReference>` elements and .NET only supports `<PackageReference>` elements for NuGet packages.</span></span>

- [<span data-ttu-id="fcf7c-138">solution</span><span class="sxs-lookup"><span data-stu-id="fcf7c-138">solution</span></span>](/nuget/schema/nuget-config-file#solution-section)

  <span data-ttu-id="fcf7c-139">Diese Einstellung ist spezifisch für Visual Studio und gilt nicht für .NET.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-139">This setting is Visual Studio specific and doesn't apply to .NET.</span></span> <span data-ttu-id="fcf7c-140">.NET verwendet keine `packages.config`-Datei, aber stattdessen `<PackageReference>`-Elemente für NuGet-Pakete.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-140">.NET doesn't use a `packages.config` file and instead uses `<PackageReference>` elements for NuGet packages.</span></span>

- [<span data-ttu-id="fcf7c-141">trustedSigners</span><span class="sxs-lookup"><span data-stu-id="fcf7c-141">trustedSigners</span></span>](/nuget/schema/nuget-config-file#trustedsigners-section)

  <span data-ttu-id="fcf7c-142">Diese Einstellung ist nicht anwendbar, da [NuGet noch keine plattformübergreifende Überprüfung](https://github.com/NuGet/Home/issues/7939) vertrauenswürdiger Pakete unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-142">This setting isn't applicable as [NuGet doesn't yet support cross-platform verification](https://github.com/NuGet/Home/issues/7939) of trusted packages.</span></span>

## <a name="arguments"></a><span data-ttu-id="fcf7c-143">Argumente</span><span class="sxs-lookup"><span data-stu-id="fcf7c-143">Arguments</span></span>

- **`ROOT`**

  <span data-ttu-id="fcf7c-144">Optionaler Pfad zur wiederherzustellenden Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-144">Optional path to the project file to restore.</span></span>

## <a name="options"></a><span data-ttu-id="fcf7c-145">Optionen</span><span class="sxs-lookup"><span data-stu-id="fcf7c-145">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="fcf7c-146">Die NuGet-Konfigurationsdatei (*nuget.config*) für den Wiederherstellungsvorgang.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-146">The NuGet configuration file (*nuget.config*) to use for the restore operation.</span></span>

- **`--disable-parallel`**

  <span data-ttu-id="fcf7c-147">Deaktiviert paralleles Erstellen von mehreren Projekten.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-147">Disables restoring multiple projects in parallel.</span></span>

- **`--force`**

  <span data-ttu-id="fcf7c-148">Erzwingt das Auflösen aller Abhängigkeiten, auch wenn die letzte Wiederherstellung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-148">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="fcf7c-149">Dieses Flag anzugeben, entspricht dem Löschen der Datei *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-149">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

- **`--force-evaluate`**

  <span data-ttu-id="fcf7c-150">Erzwingt die Neubewertung aller Abhängigkeiten bei der Wiederherstellung, selbst wenn bereits eine Sperrdatei vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-150">Forces restore to reevaluate all dependencies even if a lock file already exists.</span></span>

- **`-h|--help`**

  <span data-ttu-id="fcf7c-151">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-151">Prints out a short help for the command.</span></span>

- **`--ignore-failed-sources`**

  <span data-ttu-id="fcf7c-152">Bei fehlerhaften Quellen nur warnen, wenn Pakete die Versionsanforderung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-152">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

- **`--interactive`**

  <span data-ttu-id="fcf7c-153">Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten (z.B. um die Authentifizierung abzuschließen).</span><span class="sxs-lookup"><span data-stu-id="fcf7c-153">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span> <span data-ttu-id="fcf7c-154">Ab .NET Core 2.1.400.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-154">Since .NET Core 2.1.400.</span></span>

- **`--lock-file-path <LOCK_FILE_PATH>`**

  <span data-ttu-id="fcf7c-155">Ausgabespeicherort, in den die Projektsperrdatei geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-155">Output location where project lock file is written.</span></span> <span data-ttu-id="fcf7c-156">Standardmäßig ist dies *PROJECT_ROOT\packages.lock.json*.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-156">By default, this is *PROJECT_ROOT\packages.lock.json*.</span></span>

- **`--locked-mode`**

  <span data-ttu-id="fcf7c-157">Lassen Sie keine Aktualisierung der Projektsperrdatei zu.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-157">Don't allow updating project lock file.</span></span>

- **`--no-cache`**

  <span data-ttu-id="fcf7c-158">Gibt an, dass keine HTTP-Anforderungen zwischengespeichert werden</span><span class="sxs-lookup"><span data-stu-id="fcf7c-158">Specifies to not cache HTTP requests.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="fcf7c-159">Wenn Sie ein Projekt mit Projekt-zu-Projekt-Verweisen (P2P) wiederherstellen, stellen Sie das Stammprojekt wieder her und nicht die Verweise.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-159">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

- **`--packages <PACKAGES_DIRECTORY>`**

  <span data-ttu-id="fcf7c-160">Gibt das Verzeichnis für wiederhergestellte Pakete an.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-160">Specifies the directory for restored packages.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="fcf7c-161">Gibt eine Laufzeit für die Wiederherstellung des Pakets an.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-161">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="fcf7c-162">Wird für das Wiederherstellen von Paketen für Laufzeiten verwendet, die nicht explizit im `<RuntimeIdentifiers>`-Tag in der *.csproj*-Datei aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-162">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="fcf7c-163">Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="fcf7c-163">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="fcf7c-164">Es können mehrere RIDs bereitgestellt werden, indem diese Option mehrmals angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-164">Provide multiple RIDs by specifying this option multiple times.</span></span>

- **`-s|--source <SOURCE>`**

  <span data-ttu-id="fcf7c-165">Gibt den URI der NuGet-Paketquelle an, die während des Wiederherstellungsvorgangs zu verwenden ist.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-165">Specifies the URI of the NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="fcf7c-166">Diese Einstellung überschreibt alle Quellen, die in den *nuget.config*-Dateien angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-166">This setting overrides all of the sources specified in the *nuget.config* files.</span></span> <span data-ttu-id="fcf7c-167">Es können mehrere Quellen bereitgestellt werden, indem diese Option mehrmals angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-167">Multiple sources can be provided by specifying this option multiple times.</span></span>

- **`--use-lock-file`**

  <span data-ttu-id="fcf7c-168">Ermöglicht das Generieren und Verwenden einer Projektsperrdatei bei der Wiederherstellung.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-168">Enables project lock file to be generated and used with restore.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="fcf7c-169">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-169">Sets the verbosity level of the command.</span></span> <span data-ttu-id="fcf7c-170">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-170">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="fcf7c-171">Der Standardwert ist `minimal`sein.</span><span class="sxs-lookup"><span data-stu-id="fcf7c-171">Default value is `minimal`.</span></span>

## <a name="examples"></a><span data-ttu-id="fcf7c-172">Beispiele</span><span class="sxs-lookup"><span data-stu-id="fcf7c-172">Examples</span></span>

- <span data-ttu-id="fcf7c-173">Wiederherstellen von Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="fcf7c-173">Restore dependencies and tools for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet restore
  ```

- <span data-ttu-id="fcf7c-174">Wiederherstellen von Abhängigkeiten und Tools für das Projekt `app1` im vorgegebenen Pfad:</span><span class="sxs-lookup"><span data-stu-id="fcf7c-174">Restore dependencies and tools for the `app1` project found in the given path:</span></span>

  ```dotnetcli
  dotnet restore ./projects/app1/app1.csproj
  ```

- <span data-ttu-id="fcf7c-175">Wiederherstellen der Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis mit dem bereitgestellten Dateipfad als Quelle:</span><span class="sxs-lookup"><span data-stu-id="fcf7c-175">Restore the dependencies and tools for the project in the current   directory using the file path provided as the source:</span></span>

  ```dotnetcli
  dotnet restore -s c:\packages\mypackages
  ```

- <span data-ttu-id="fcf7c-176">Wiederherstellen der Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis mit den beiden bereitgestellten Dateipfaden als Quellen:</span><span class="sxs-lookup"><span data-stu-id="fcf7c-176">Restore the dependencies and tools for the project in the current   directory using the two file paths provided as sources:</span></span>

  ```dotnetcli
  dotnet restore -s c:\packages\mypackages -s c:\packages\myotherpackages
  ```

- <span data-ttu-id="fcf7c-177">Wiederherstellen von Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis mit detaillierter Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="fcf7c-177">Restore dependencies and tools for the project in the current directory   showing detailed output:</span></span>

  ```dotnetcli
  dotnet restore --verbosity detailed
  ```
