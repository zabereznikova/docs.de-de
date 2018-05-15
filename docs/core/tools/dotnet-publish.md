---
title: dotnet publish-Befehl – .NET Core-CLI
description: Der „dotnet publish“-Befehl veröffentlicht ein .NET Core-Projekt in einem Verzeichnis.
author: mairaw
ms.author: mairaw
ms.date: 03/10/2018
ms.openlocfilehash: f4c422eab20f5fe2d1b0c09133953f22a539474e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="dotnet-publish"></a><span data-ttu-id="40b3d-103">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="40b3d-103">dotnet publish</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="40b3d-104">name</span><span class="sxs-lookup"><span data-stu-id="40b3d-104">Name</span></span>

<span data-ttu-id="40b3d-105">`dotnet publish`: Packt die Anwendung und ihre Abhängigkeiten in einen Ordner für die Bereitstellung auf einem Hostsystem.</span><span class="sxs-lookup"><span data-stu-id="40b3d-105">`dotnet publish` - Packs the application and its dependencies into a folder for deployment to a hosting system.</span></span>

## <a name="synopsis"></a><span data-ttu-id="40b3d-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="40b3d-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="40b3d-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="40b3d-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [--no-dependencies] [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="40b3d-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="40b3d-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="40b3d-109">description</span><span class="sxs-lookup"><span data-stu-id="40b3d-109">Description</span></span>

<span data-ttu-id="40b3d-110">`dotnet publish` kompiliert die Anwendung, liest ihre Abhängigkeiten, die in der Projektdatei angegeben sind, und veröffentlicht die resultierenden Dateien in einem Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="40b3d-110">`dotnet publish` compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="40b3d-111">Die Ausgabe wird Folgendes enthalten:</span><span class="sxs-lookup"><span data-stu-id="40b3d-111">The output will contain the following:</span></span>

* <span data-ttu-id="40b3d-112">Intermediate Language-Code (IL) in einer Assembly mit einer *DLL*-Erweiterung.</span><span class="sxs-lookup"><span data-stu-id="40b3d-112">Intermediate Language (IL) code in an assembly with a *dll* extension.</span></span>
* <span data-ttu-id="40b3d-113">*deps.json*-Datei, die alle Abhängigkeiten des Projekts enthält.</span><span class="sxs-lookup"><span data-stu-id="40b3d-113">*.deps.json* file that contains all of the dependencies of the project.</span></span>
* <span data-ttu-id="40b3d-114">Eine *.runtime.config.json*-Datei, die die freigegebene Laufzeit angibt, die die Anwendung erwartet, sowie andere Konfigurationsoptionen für die Laufzeit (z.B. Typ der automatischen Speicherbereinigung).</span><span class="sxs-lookup"><span data-stu-id="40b3d-114">*.runtime.config.json* file that specifies the shared runtime that the application expects, as well as other configuration options for the runtime (for example, garbage collection type).</span></span>
* <span data-ttu-id="40b3d-115">Die Abhängigkeiten der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="40b3d-115">The application's dependencies.</span></span> <span data-ttu-id="40b3d-116">Diese werden aus dem NuGet-Cache in den Ausgabeordner kopiert.</span><span class="sxs-lookup"><span data-stu-id="40b3d-116">These are copied from the NuGet cache into the output folder.</span></span>

<span data-ttu-id="40b3d-117">Die `dotnet publish`-Ausgabe des Befehls ist bereit für die Bereitstellung auf einem Hostsystem (z.B. ein Server, PC, Mac, Laptops) für die Ausführung und ist der einzige offiziell unterstützte Weg, um die Anwendung für die Bereitstellung vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="40b3d-117">The `dotnet publish` command's output is ready for deployment to a hosting system (for example, a server, PC, Mac, laptop) for execution and is the only officially supported way to prepare the application for deployment.</span></span> <span data-ttu-id="40b3d-118">Je nach Art der Bereitstellung, die im Projekt angegeben ist, hat das Hostsystem die freigegebene .NET Core-Laufzeit installiert oder nicht.</span><span class="sxs-lookup"><span data-stu-id="40b3d-118">Depending on the type of deployment that the project specifies, the hosting system may or may not have the .NET Core shared runtime installed on it.</span></span> <span data-ttu-id="40b3d-119">Weitere Informationen finden Sie unter [.NET Core Anwendungsbereitstellung](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="40b3d-119">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span> <span data-ttu-id="40b3d-120">Die Verzeichnisstruktur der veröffentlichten Anwendung finden Sie unter [Directory structure (Verzeichnisstruktur)](/aspnet/core/hosting/directory-structure).</span><span class="sxs-lookup"><span data-stu-id="40b3d-120">For the directory structure of a published application, see [Directory structure](/aspnet/core/hosting/directory-structure).</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a><span data-ttu-id="40b3d-121">Argumente</span><span class="sxs-lookup"><span data-stu-id="40b3d-121">Arguments</span></span>

`PROJECT`

<span data-ttu-id="40b3d-122">Das zu veröffentlichende Projekt – standardmäßig das aktuelle Verzeichnis, wenn nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="40b3d-122">The project to publish, which defaults to the current directory if not specified.</span></span>

## <a name="options"></a><span data-ttu-id="40b3d-123">Optionen</span><span class="sxs-lookup"><span data-stu-id="40b3d-123">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="40b3d-124">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="40b3d-124">.NET Core 2.x</span></span>](#tab/netcore2x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="40b3d-125">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="40b3d-125">Defines the build configuration.</span></span> <span data-ttu-id="40b3d-126">Der Standardwert ist `Debug`.</span><span class="sxs-lookup"><span data-stu-id="40b3d-126">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="40b3d-127">Veröffentlicht die Anwendung für das angegebene [Zielframework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="40b3d-127">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="40b3d-128">Sie müssen das Zielframework in der Projektdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="40b3d-128">You must specify the target framework in the project file.</span></span>

`--force`

<span data-ttu-id="40b3d-129">Erzwingt das Auflösen aller Abhängigkeiten, auch wenn die letzte Wiederherstellung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="40b3d-129">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="40b3d-130">Dies entspricht dem Löschen der Datei *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="40b3d-130">This is equivalent to deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="40b3d-131">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="40b3d-131">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="40b3d-132">Gibt mindestens ein [Zielmanifest](../deploying/runtime-store.md) an, das verwendet wird, um die Menge an mit der App veröffentlichten Paketen zu senken.</span><span class="sxs-lookup"><span data-stu-id="40b3d-132">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="40b3d-133">Die Manifestdatei ist Teil der Ausgabe des [`dotnet store`-Befehls](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="40b3d-133">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="40b3d-134">Um mehrere Manifeste anzugeben, fügen Sie die `--manifest`-Option für jedes Manifest hinzu.</span><span class="sxs-lookup"><span data-stu-id="40b3d-134">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="40b3d-135">Diese Option ist am dem .NET Core 2.0 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="40b3d-135">This option is available starting with .NET Core 2.0 SDK.</span></span>

`--no-dependencies`

<span data-ttu-id="40b3d-136">Ignoriert Verweise zwischen Projekten und stellt nur das zum Erstellen angegebene Stammprojekt wieder her.</span><span class="sxs-lookup"><span data-stu-id="40b3d-136">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="40b3d-137">Führt kein implizites Wiederherstellen durch, wenn der Befehl ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="40b3d-137">Doesn't perform an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="40b3d-138">Gibt den Pfad für das Ausgabeverzeichnis an.</span><span class="sxs-lookup"><span data-stu-id="40b3d-138">Specifies the path for the output directory.</span></span> <span data-ttu-id="40b3d-139">Wenn nicht angegeben, wird standardmäßig *./bin/[configuration]/[framework]/* für eine Framework-abhängige Bereitstellung oder *./bin/[configuration]/[framework]/[runtime]* für eine eigenständige Bereitstellung gewählt.</span><span class="sxs-lookup"><span data-stu-id="40b3d-139">If not specified, it defaults to *./bin/[configuration]/[framework]/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]* for a self-contained deployment.</span></span>
<span data-ttu-id="40b3d-140">Wenn ein relativer Pfad bereitgestellt wird, ist das generierte Ausgabeverzeichnis relativ zum Speicherort der Projektdatei statt zum aktuellen Arbeitsverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="40b3d-140">If a relative path is provided, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`--self-contained`

<span data-ttu-id="40b3d-141">Veröffentlicht die .NET Core-Runtime mit Ihrer Anwendung, sodass die Runtime nicht auf dem Zielcomputer installiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="40b3d-141">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="40b3d-142">Wenn ein Runtimebezeichner angegeben ist, ist der Standardwert `true`.</span><span class="sxs-lookup"><span data-stu-id="40b3d-142">If a runtime identifier is specified, its default value is `true`.</span></span> <span data-ttu-id="40b3d-143">Weitere Informationen zu den verschiedenen Bereitstellungstypen finden Sie unter [.NET Core application deployment (Bereitstellung von .NET Core-Anwendungen)](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="40b3d-143">For more information about the different deployment types, see [.NET Core application deployment](../deploying/index.md).</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="40b3d-144">Veröffentlicht die Anwendung für eine bestimmte Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="40b3d-144">Publishes the application for a given runtime.</span></span> <span data-ttu-id="40b3d-145">Wird bei der Erstellung einer [eigenständigen Bereitstellung (Self-contained deployments, SCD)](../deploying/index.md#self-contained-deployments-scd) verwendet.</span><span class="sxs-lookup"><span data-stu-id="40b3d-145">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="40b3d-146">Eine Liste der Runtime-IDs (RIDs) finden Sie im [RID-Katalog](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="40b3d-146">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="40b3d-147">Standardmäßig wird eine [Framework-abhängige Bereitstellung (FDD)](../deploying/index.md#framework-dependent-deployments-fdd) veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="40b3d-147">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="40b3d-148">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="40b3d-148">Sets the verbosity level of the command.</span></span> <span data-ttu-id="40b3d-149">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="40b3d-149">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="40b3d-150">Definiert das Versionssuffix zum Ersetzen des Sternchens (`*`) im Versionsfeld der Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="40b3d-150">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="40b3d-151">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="40b3d-151">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="40b3d-152">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="40b3d-152">Defines the build configuration.</span></span> <span data-ttu-id="40b3d-153">Der Standardwert ist `Debug`.</span><span class="sxs-lookup"><span data-stu-id="40b3d-153">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="40b3d-154">Veröffentlicht die Anwendung für das angegebene [Zielframework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="40b3d-154">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="40b3d-155">Sie müssen das Zielframework in der Projektdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="40b3d-155">You must specify the target framework in the project file.</span></span>

`-h|--help`

<span data-ttu-id="40b3d-156">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="40b3d-156">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="40b3d-157">Gibt mindestens ein [Zielmanifest](../deploying/runtime-store.md) an, das verwendet wird, um die Menge an mit der App veröffentlichten Paketen zu senken.</span><span class="sxs-lookup"><span data-stu-id="40b3d-157">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="40b3d-158">Die Manifestdatei ist Teil der Ausgabe des [`dotnet store`-Befehls](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="40b3d-158">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="40b3d-159">Um mehrere Manifeste anzugeben, fügen Sie die `--manifest`-Option für jedes Manifest hinzu.</span><span class="sxs-lookup"><span data-stu-id="40b3d-159">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="40b3d-160">Diese Option ist am dem .NET Core 2.0 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="40b3d-160">This option is available starting with .NET Core 2.0 SDK.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="40b3d-161">Gibt den Pfad für das Ausgabeverzeichnis an.</span><span class="sxs-lookup"><span data-stu-id="40b3d-161">Specifies the path for the output directory.</span></span> <span data-ttu-id="40b3d-162">Wenn nicht angegeben, wird standardmäßig *./bin/[configuration]/[framework]/* für eine Framework-abhängige Bereitstellung oder *./bin/[configuration]/[framework]/[runtime]* für eine eigenständige Bereitstellung gewählt.</span><span class="sxs-lookup"><span data-stu-id="40b3d-162">If not specified, it defaults to *./bin/[configuration]/[framework]/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]* for a self-contained deployment.</span></span>
<span data-ttu-id="40b3d-163">Wenn ein relativer Pfad bereitgestellt wird, ist das generierte Ausgabeverzeichnis relativ zum Speicherort der Projektdatei statt zum aktuellen Arbeitsverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="40b3d-163">If a relative path is provided, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="40b3d-164">Veröffentlicht die Anwendung für eine bestimmte Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="40b3d-164">Publishes the application for a given runtime.</span></span> <span data-ttu-id="40b3d-165">Wird bei der Erstellung einer [eigenständigen Bereitstellung (Self-contained deployments, SCD)](../deploying/index.md#self-contained-deployments-scd) verwendet.</span><span class="sxs-lookup"><span data-stu-id="40b3d-165">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="40b3d-166">Eine Liste der Runtime-IDs (RIDs) finden Sie im [RID-Katalog](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="40b3d-166">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="40b3d-167">Standardmäßig wird eine [Framework-abhängige Bereitstellung (FDD)](../deploying/index.md#framework-dependent-deployments-fdd) veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="40b3d-167">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="40b3d-168">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="40b3d-168">Sets the verbosity level of the command.</span></span> <span data-ttu-id="40b3d-169">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="40b3d-169">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="40b3d-170">Definiert das Versionssuffix zum Ersetzen des Sternchens (`*`) im Versionsfeld der Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="40b3d-170">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

---

## <a name="examples"></a><span data-ttu-id="40b3d-171">Beispiele</span><span class="sxs-lookup"><span data-stu-id="40b3d-171">Examples</span></span>

<span data-ttu-id="40b3d-172">Veröffentlicht das Projekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="40b3d-172">Publish the project in the current directory:</span></span>

`dotnet publish`

<span data-ttu-id="40b3d-173">Veröffentlichen Sie die Anwendung unter Verwendung der angegebenen Projektdatei:</span><span class="sxs-lookup"><span data-stu-id="40b3d-173">Publish the application using the specified project file:</span></span>

`dotnet publish ~/projects/app1/app1.csproj`

<span data-ttu-id="40b3d-174">Veröffentlichen Sie das Projekt aus dem aktuellen Verzeichnis unter Verwendung des `netcoreapp1.1`-Frameworks:</span><span class="sxs-lookup"><span data-stu-id="40b3d-174">Publish the project in the current directory using the `netcoreapp1.1` framework:</span></span>

`dotnet publish --framework netcoreapp1.1`

<span data-ttu-id="40b3d-175">Veröffentlichen der aktuellen Anwendung mithilfe des `netcoreapp1.1`-Frameworks und der Laufzeit für `OS X 10.10` (Sie müssen diese RID in der Projektdatei auflisten).</span><span class="sxs-lookup"><span data-stu-id="40b3d-175">Publish the current application using the `netcoreapp1.1` framework and the runtime for `OS X 10.10` (you must list this RID in the project file).</span></span>

`dotnet publish --framework netcoreapp1.1 --runtime osx.10.11-x64`

<span data-ttu-id="40b3d-176">Veröffentlichen sie die aktuelle Anwendung, aber fügen Sie während der Wiederherstellung keine Projekt-zu-Projekt-Verweise hinzu, sondern nur das Stammprojekt (.NET Core SDK 2.0 und spätere Versionen):</span><span class="sxs-lookup"><span data-stu-id="40b3d-176">Publish the current application but don't restore project-to-project (P2P) references, just the root project during the restore operation (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet publish --no-dependencies`

## <a name="see-also"></a><span data-ttu-id="40b3d-177">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="40b3d-177">See also</span></span>

* [<span data-ttu-id="40b3d-178">Zielframeworks</span><span class="sxs-lookup"><span data-stu-id="40b3d-178">Target frameworks</span></span>](../../standard/frameworks.md)
* [<span data-ttu-id="40b3d-179">Runtime-ID-Katalog (RID)</span><span class="sxs-lookup"><span data-stu-id="40b3d-179">Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)