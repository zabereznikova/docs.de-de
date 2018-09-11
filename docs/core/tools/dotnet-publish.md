---
title: dotnet publish-Befehl – .NET Core-CLI
description: Der „dotnet publish“-Befehl veröffentlicht ein .NET Core-Projekt in einem Verzeichnis.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: a60777d613573076f41fba3e5ed610b236884063
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43416921"
---
# <a name="dotnet-publish"></a><span data-ttu-id="bc0e1-103">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="bc0e1-103">dotnet publish</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="bc0e1-104">name</span><span class="sxs-lookup"><span data-stu-id="bc0e1-104">Name</span></span>

<span data-ttu-id="bc0e1-105">`dotnet publish`: Packt die Anwendung und ihre Abhängigkeiten in einen Ordner für die Bereitstellung auf einem Hostsystem.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-105">`dotnet publish` - Packs the application and its dependencies into a folder for deployment to a hosting system.</span></span>

## <a name="synopsis"></a><span data-ttu-id="bc0e1-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="bc0e1-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="bc0e1-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="bc0e1-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [--no-build] [--no-dependencies]
    [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="bc0e1-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="bc0e1-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [--no-dependencies]
    [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="bc0e1-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="bc0e1-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity]
    [--version-suffix]
dotnet publish [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="bc0e1-110">Beschreibung </span><span class="sxs-lookup"><span data-stu-id="bc0e1-110">Description</span></span>

<span data-ttu-id="bc0e1-111">`dotnet publish` kompiliert die Anwendung, liest ihre Abhängigkeiten, die in der Projektdatei angegeben sind, und veröffentlicht die resultierenden Dateien in einem Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-111">`dotnet publish` compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="bc0e1-112">Die Ausgabe umfasst die folgenden Objekte:</span><span class="sxs-lookup"><span data-stu-id="bc0e1-112">The output includes the following assets:</span></span>

* <span data-ttu-id="bc0e1-113">Intermediate Language-Code (IL) in einer Assembly mit einer *DLL*-Erweiterung.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-113">Intermediate Language (IL) code in an assembly with a *dll* extension.</span></span>
* <span data-ttu-id="bc0e1-114">*.deps.json*-Datei, die alle Abhängigkeiten des Projekts enthält.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-114">*.deps.json* file that includes all of the dependencies of the project.</span></span>
* <span data-ttu-id="bc0e1-115">Eine *.runtime.config.json*-Datei, die die freigegebene Laufzeit angibt, die die Anwendung erwartet, sowie andere Konfigurationsoptionen für die Laufzeit (z.B. Typ der automatischen Speicherbereinigung).</span><span class="sxs-lookup"><span data-stu-id="bc0e1-115">*.runtime.config.json* file that specifies the shared runtime that the application expects, as well as other configuration options for the runtime (for example, garbage collection type).</span></span>
* <span data-ttu-id="bc0e1-116">Die Abhängigkeiten der Anwendung, die aus dem NuGet-Cache in den Ausgabeordner kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-116">The application's dependencies, which are copied from the NuGet cache into the output folder.</span></span>

<span data-ttu-id="bc0e1-117">Die Ausgabe des Befehls `dotnet publish` steht für die Bereitstellung zur Ausführung auf einem Hostsystem bereit (z.B. ein Server, Computer, Mac oder Laptop).</span><span class="sxs-lookup"><span data-stu-id="bc0e1-117">The `dotnet publish` command's output is ready for deployment to a hosting system (for example, a server, PC, Mac, laptop) for execution.</span></span> <span data-ttu-id="bc0e1-118">Es ist die einzige offiziell unterstützte Methode zum Vorbereiten der Anwendung für die Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-118">It's the only officially supported way to prepare the application for deployment.</span></span> <span data-ttu-id="bc0e1-119">Je nach Art der Bereitstellung, die im Projekt angegeben ist, hat das Hostsystem die freigegebene .NET Core-Laufzeit installiert oder nicht.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-119">Depending on the type of deployment that the project specifies, the hosting system may or may not have the .NET Core shared runtime installed on it.</span></span> <span data-ttu-id="bc0e1-120">Weitere Informationen finden Sie unter [.NET Core Anwendungsbereitstellung](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="bc0e1-120">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span> <span data-ttu-id="bc0e1-121">Die Verzeichnisstruktur der veröffentlichten Anwendung finden Sie unter [Directory structure (Verzeichnisstruktur)](/aspnet/core/hosting/directory-structure).</span><span class="sxs-lookup"><span data-stu-id="bc0e1-121">For the directory structure of a published application, see [Directory structure](/aspnet/core/hosting/directory-structure).</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a><span data-ttu-id="bc0e1-122">Argumente</span><span class="sxs-lookup"><span data-stu-id="bc0e1-122">Arguments</span></span>

`PROJECT`

<span data-ttu-id="bc0e1-123">Das zu veröffentlichende Projekt.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-123">The project to publish.</span></span> <span data-ttu-id="bc0e1-124">Wenn nicht angegeben, wird standardmäßig das aktuelle Verzeichnis gewählt.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-124">If not specified, it defaults to the current directory.</span></span>

## <a name="options"></a><span data-ttu-id="bc0e1-125">Optionen</span><span class="sxs-lookup"><span data-stu-id="bc0e1-125">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="bc0e1-126">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="bc0e1-126">.NET Core 2.1</span></span>](#tab/netcore21)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="bc0e1-127">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-127">Defines the build configuration.</span></span> <span data-ttu-id="bc0e1-128">Der Standardwert ist `Debug`.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-128">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="bc0e1-129">Veröffentlicht die Anwendung für das angegebene [Zielframework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="bc0e1-129">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="bc0e1-130">Sie müssen das Zielframework in der Projektdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-130">You must specify the target framework in the project file.</span></span>

`--force`

<span data-ttu-id="bc0e1-131">Erzwingt das Auflösen aller Abhängigkeiten, auch wenn die letzte Wiederherstellung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-131">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="bc0e1-132">Dieses Flag anzugeben, entspricht dem Löschen der Datei *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-132">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="bc0e1-133">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-133">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="bc0e1-134">Gibt mindestens ein [Zielmanifest](../deploying/runtime-store.md) an, das verwendet wird, um die Menge an mit der App veröffentlichten Paketen zu senken.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-134">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="bc0e1-135">Die Manifestdatei ist Teil der Ausgabe des [`dotnet store`-Befehls](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="bc0e1-135">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="bc0e1-136">Um mehrere Manifeste anzugeben, fügen Sie die `--manifest`-Option für jedes Manifest hinzu.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-136">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="bc0e1-137">Diese Option ist am dem .NET Core 2.0 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-137">This option is available starting with .NET Core 2.0 SDK.</span></span>

`--no-build`

<span data-ttu-id="bc0e1-138">Erstellt das Projekt nicht vor der Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-138">Doesn't build the project before publishing.</span></span> <span data-ttu-id="bc0e1-139">Zudem wird das Flag `--no-restore` implizit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-139">It also implicitly sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="bc0e1-140">Ignoriert Verweise zwischen Projekten und stellt nur das zum Erstellen angegebene Stammprojekt wieder her.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-140">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="bc0e1-141">Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-141">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="bc0e1-142">Gibt den Pfad für das Ausgabeverzeichnis an.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-142">Specifies the path for the output directory.</span></span> <span data-ttu-id="bc0e1-143">Wenn nicht angegeben, wird standardmäßig *./bin/[configuration]/[framework]/publish/* für eine Framework-abhängige Bereitstellung oder *./bin/[configuration]/[framework]/[runtime]/publish/* für eine eigenständige Bereitstellung gewählt.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-143">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="bc0e1-144">Bei einem relativen Pfad ist das generierte Ausgabeverzeichnis relativ zum Speicherort der Projektdatei anstatt zum aktuellen Arbeitsverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-144">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`--self-contained`

<span data-ttu-id="bc0e1-145">Veröffentlicht die .NET Core-Runtime mit Ihrer Anwendung, sodass die Runtime nicht auf dem Zielcomputer installiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-145">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="bc0e1-146">Wenn ein Runtimebezeichner angegeben ist, ist der Standardwert `true`.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-146">If a runtime identifier is specified, its default value is `true`.</span></span> <span data-ttu-id="bc0e1-147">Weitere Informationen zu den verschiedenen Bereitstellungstypen finden Sie unter [.NET Core application deployment (Bereitstellung von .NET Core-Anwendungen)](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="bc0e1-147">For more information about the different deployment types, see [.NET Core application deployment](../deploying/index.md).</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="bc0e1-148">Veröffentlicht die Anwendung für eine bestimmte Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-148">Publishes the application for a given runtime.</span></span> <span data-ttu-id="bc0e1-149">Wird bei der Erstellung einer [eigenständigen Bereitstellung (Self-contained deployments, SCD)](../deploying/index.md#self-contained-deployments-scd) verwendet.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-149">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="bc0e1-150">Eine Liste der Runtime-IDs (RIDs) finden Sie im [RID-Katalog](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="bc0e1-150">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="bc0e1-151">Standardmäßig wird eine [Framework-abhängige Bereitstellung (FDD)](../deploying/index.md#framework-dependent-deployments-fdd) veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-151">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="bc0e1-152">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-152">Sets the verbosity level of the command.</span></span> <span data-ttu-id="bc0e1-153">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-153">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="bc0e1-154">Definiert das Versionssuffix zum Ersetzen des Sternchens (`*`) im Versionsfeld der Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-154">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="bc0e1-155">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="bc0e1-155">.NET Core 2.0</span></span>](#tab/netcore20)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="bc0e1-156">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-156">Defines the build configuration.</span></span> <span data-ttu-id="bc0e1-157">Der Standardwert ist `Debug`.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-157">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="bc0e1-158">Veröffentlicht die Anwendung für das angegebene [Zielframework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="bc0e1-158">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="bc0e1-159">Sie müssen das Zielframework in der Projektdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-159">You must specify the target framework in the project file.</span></span>

`--force`

<span data-ttu-id="bc0e1-160">Erzwingt das Auflösen aller Abhängigkeiten, auch wenn die letzte Wiederherstellung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-160">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="bc0e1-161">Dieses Flag anzugeben, entspricht dem Löschen der Datei *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-161">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="bc0e1-162">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-162">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="bc0e1-163">Gibt mindestens ein [Zielmanifest](../deploying/runtime-store.md) an, das verwendet wird, um die Menge an mit der App veröffentlichten Paketen zu senken.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-163">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="bc0e1-164">Die Manifestdatei ist Teil der Ausgabe des [`dotnet store`-Befehls](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="bc0e1-164">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="bc0e1-165">Um mehrere Manifeste anzugeben, fügen Sie die `--manifest`-Option für jedes Manifest hinzu.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-165">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="bc0e1-166">Diese Option ist am dem .NET Core 2.0 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-166">This option is available starting with .NET Core 2.0 SDK.</span></span>

`--no-dependencies`

<span data-ttu-id="bc0e1-167">Ignoriert Verweise zwischen Projekten und stellt nur das zum Erstellen angegebene Stammprojekt wieder her.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-167">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="bc0e1-168">Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-168">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="bc0e1-169">Gibt den Pfad für das Ausgabeverzeichnis an.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-169">Specifies the path for the output directory.</span></span> <span data-ttu-id="bc0e1-170">Wenn nicht angegeben, wird standardmäßig *./bin/[configuration]/[framework]/publish/* für eine Framework-abhängige Bereitstellung oder *./bin/[configuration]/[framework]/[runtime]/publish/* für eine eigenständige Bereitstellung gewählt.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-170">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="bc0e1-171">Bei einem relativen Pfad ist das generierte Ausgabeverzeichnis relativ zum Speicherort der Projektdatei anstatt zum aktuellen Arbeitsverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-171">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`--self-contained`

<span data-ttu-id="bc0e1-172">Veröffentlicht die .NET Core-Runtime mit Ihrer Anwendung, sodass die Runtime nicht auf dem Zielcomputer installiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-172">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="bc0e1-173">Wenn ein Runtimebezeichner angegeben ist, ist der Standardwert `true`.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-173">If a runtime identifier is specified, its default value is `true`.</span></span> <span data-ttu-id="bc0e1-174">Weitere Informationen zu den verschiedenen Bereitstellungstypen finden Sie unter [.NET Core application deployment (Bereitstellung von .NET Core-Anwendungen)](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="bc0e1-174">For more information about the different deployment types, see [.NET Core application deployment](../deploying/index.md).</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="bc0e1-175">Veröffentlicht die Anwendung für eine bestimmte Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-175">Publishes the application for a given runtime.</span></span> <span data-ttu-id="bc0e1-176">Wird bei der Erstellung einer [eigenständigen Bereitstellung (Self-contained deployments, SCD)](../deploying/index.md#self-contained-deployments-scd) verwendet.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-176">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="bc0e1-177">Eine Liste der Runtime-IDs (RIDs) finden Sie im [RID-Katalog](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="bc0e1-177">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="bc0e1-178">Standardmäßig wird eine [Framework-abhängige Bereitstellung (FDD)](../deploying/index.md#framework-dependent-deployments-fdd) veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-178">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="bc0e1-179">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-179">Sets the verbosity level of the command.</span></span> <span data-ttu-id="bc0e1-180">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-180">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="bc0e1-181">Definiert das Versionssuffix zum Ersetzen des Sternchens (`*`) im Versionsfeld der Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-181">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="bc0e1-182">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="bc0e1-182">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="bc0e1-183">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-183">Defines the build configuration.</span></span> <span data-ttu-id="bc0e1-184">Der Standardwert ist `Debug`.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-184">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="bc0e1-185">Veröffentlicht die Anwendung für das angegebene [Zielframework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="bc0e1-185">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="bc0e1-186">Sie müssen das Zielframework in der Projektdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-186">You must specify the target framework in the project file.</span></span>

`-h|--help`

<span data-ttu-id="bc0e1-187">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-187">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="bc0e1-188">Gibt mindestens ein [Zielmanifest](../deploying/runtime-store.md) an, das verwendet wird, um die Menge an mit der App veröffentlichten Paketen zu senken.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-188">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="bc0e1-189">Die Manifestdatei ist Teil der Ausgabe des [`dotnet store`-Befehls](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="bc0e1-189">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="bc0e1-190">Um mehrere Manifeste anzugeben, fügen Sie die `--manifest`-Option für jedes Manifest hinzu.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-190">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="bc0e1-191">Diese Option ist am dem .NET Core 2.0 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-191">This option is available starting with .NET Core 2.0 SDK.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="bc0e1-192">Gibt den Pfad für das Ausgabeverzeichnis an.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-192">Specifies the path for the output directory.</span></span> <span data-ttu-id="bc0e1-193">Wenn nicht angegeben, wird standardmäßig *./bin/[configuration]/[framework]/publish/* für eine Framework-abhängige Bereitstellung oder *./bin/[configuration]/[framework]/[runtime]/publish/* für eine eigenständige Bereitstellung gewählt.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-193">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="bc0e1-194">Bei einem relativen Pfad ist das generierte Ausgabeverzeichnis relativ zum Speicherort der Projektdatei anstatt zum aktuellen Arbeitsverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-194">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="bc0e1-195">Veröffentlicht die Anwendung für eine bestimmte Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-195">Publishes the application for a given runtime.</span></span> <span data-ttu-id="bc0e1-196">Wird bei der Erstellung einer [eigenständigen Bereitstellung (Self-contained deployments, SCD)](../deploying/index.md#self-contained-deployments-scd) verwendet.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-196">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="bc0e1-197">Eine Liste der Runtime-IDs (RIDs) finden Sie im [RID-Katalog](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="bc0e1-197">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="bc0e1-198">Standardmäßig wird eine [Framework-abhängige Bereitstellung (FDD)](../deploying/index.md#framework-dependent-deployments-fdd) veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-198">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="bc0e1-199">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-199">Sets the verbosity level of the command.</span></span> <span data-ttu-id="bc0e1-200">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-200">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="bc0e1-201">Definiert das Versionssuffix zum Ersetzen des Sternchens (`*`) im Versionsfeld der Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="bc0e1-201">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

---

## <a name="examples"></a><span data-ttu-id="bc0e1-202">Beispiele</span><span class="sxs-lookup"><span data-stu-id="bc0e1-202">Examples</span></span>

<span data-ttu-id="bc0e1-203">Veröffentlicht das Projekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="bc0e1-203">Publish the project in the current directory:</span></span>

`dotnet publish`

<span data-ttu-id="bc0e1-204">Veröffentlichen Sie die Anwendung unter Verwendung der angegebenen Projektdatei:</span><span class="sxs-lookup"><span data-stu-id="bc0e1-204">Publish the application using the specified project file:</span></span>

`dotnet publish ~/projects/app1/app1.csproj`

<span data-ttu-id="bc0e1-205">Veröffentlichen Sie das Projekt aus dem aktuellen Verzeichnis unter Verwendung des `netcoreapp1.1`-Frameworks:</span><span class="sxs-lookup"><span data-stu-id="bc0e1-205">Publish the project in the current directory using the `netcoreapp1.1` framework:</span></span>

`dotnet publish --framework netcoreapp1.1`

<span data-ttu-id="bc0e1-206">Veröffentlichen der aktuellen Anwendung mithilfe des `netcoreapp1.1`-Frameworks und der Laufzeit für `OS X 10.10` (Sie müssen diese RID in der Projektdatei auflisten).</span><span class="sxs-lookup"><span data-stu-id="bc0e1-206">Publish the current application using the `netcoreapp1.1` framework and the runtime for `OS X 10.10` (you must list this RID in the project file).</span></span>

`dotnet publish --framework netcoreapp1.1 --runtime osx.10.11-x64`

<span data-ttu-id="bc0e1-207">Veröffentlichen sie die aktuelle Anwendung, aber fügen Sie während der Wiederherstellung keine Projekt-zu-Projekt-Verweise hinzu, sondern nur das Stammprojekt (.NET Core SDK 2.0 und spätere Versionen):</span><span class="sxs-lookup"><span data-stu-id="bc0e1-207">Publish the current application but don't restore project-to-project (P2P) references, just the root project during the restore operation (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet publish --no-dependencies`

## <a name="see-also"></a><span data-ttu-id="bc0e1-208">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bc0e1-208">See also</span></span>

* [<span data-ttu-id="bc0e1-209">Zielframeworks</span><span class="sxs-lookup"><span data-stu-id="bc0e1-209">Target frameworks</span></span>](../../standard/frameworks.md)
* [<span data-ttu-id="bc0e1-210">Runtime-ID-Katalog (RID)</span><span class="sxs-lookup"><span data-stu-id="bc0e1-210">Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
