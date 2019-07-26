---
title: Befehl „dotnet publish“
description: Der „dotnet publish“-Befehl veröffentlicht ein .NET Core-Projekt in einem Verzeichnis.
ms.date: 05/29/2018
ms.openlocfilehash: 8cefeae17e464e14abc54dce1feb414a72c44164
ms.sourcegitcommit: 09d699aca28ae9723399bbd9d3d44aa0cbd3848d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/19/2019
ms.locfileid: "68331032"
---
# <a name="dotnet-publish"></a><span data-ttu-id="87c92-103">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="87c92-103">dotnet publish</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="87c92-104">name</span><span class="sxs-lookup"><span data-stu-id="87c92-104">Name</span></span>

<span data-ttu-id="87c92-105">`dotnet publish`: Packt die Anwendung und ihre Abhängigkeiten in einen Ordner für die Bereitstellung auf einem Hostsystem.</span><span class="sxs-lookup"><span data-stu-id="87c92-105">`dotnet publish` - Packs the application and its dependencies into a folder for deployment to a hosting system.</span></span>

## <a name="synopsis"></a><span data-ttu-id="87c92-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="87c92-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="87c92-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="87c92-107">.NET Core 2.1</span></span>](#tab/netcore21)

```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [--no-build] [--no-dependencies]
    [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="87c92-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="87c92-108">.NET Core 2.0</span></span>](#tab/netcore20)

```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [--no-dependencies]
    [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="87c92-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="87c92-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity]
    [--version-suffix]
dotnet publish [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="87c92-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="87c92-110">Description</span></span>

<span data-ttu-id="87c92-111">`dotnet publish` kompiliert die Anwendung, liest ihre Abhängigkeiten, die in der Projektdatei angegeben sind, und veröffentlicht die resultierenden Dateien in einem Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="87c92-111">`dotnet publish` compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="87c92-112">Die Ausgabe umfasst die folgenden Objekte:</span><span class="sxs-lookup"><span data-stu-id="87c92-112">The output includes the following assets:</span></span>

* <span data-ttu-id="87c92-113">Intermediate Language-Code (IL) in einer Assembly mit einer *DLL*-Erweiterung.</span><span class="sxs-lookup"><span data-stu-id="87c92-113">Intermediate Language (IL) code in an assembly with a *dll* extension.</span></span>
* <span data-ttu-id="87c92-114">*.deps.json*-Datei, die alle Abhängigkeiten des Projekts enthält.</span><span class="sxs-lookup"><span data-stu-id="87c92-114">*.deps.json* file that includes all of the dependencies of the project.</span></span>
* <span data-ttu-id="87c92-115">Eine Datei vom Typ *.runtimeconfig.json*, die die von der Anwendung erwartete freigegebene Laufzeit sowie andere Konfigurationsoptionen für die Laufzeit angibt (etwa die Art der Garbage Collection).</span><span class="sxs-lookup"><span data-stu-id="87c92-115">*.runtimeconfig.json* file that specifies the shared runtime that the application expects, as well as other configuration options for the runtime (for example, garbage collection type).</span></span>
* <span data-ttu-id="87c92-116">Die Abhängigkeiten der Anwendung, die aus dem NuGet-Cache in den Ausgabeordner kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="87c92-116">The application's dependencies, which are copied from the NuGet cache into the output folder.</span></span>

<span data-ttu-id="87c92-117">Die Ausgabe des Befehls `dotnet publish` steht für die Bereitstellung zur Ausführung auf einem Hostsystem bereit (z.B. ein Server, Computer, Mac oder Laptop).</span><span class="sxs-lookup"><span data-stu-id="87c92-117">The `dotnet publish` command's output is ready for deployment to a hosting system (for example, a server, PC, Mac, laptop) for execution.</span></span> <span data-ttu-id="87c92-118">Es ist die einzige offiziell unterstützte Methode zum Vorbereiten der Anwendung für die Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="87c92-118">It's the only officially supported way to prepare the application for deployment.</span></span> <span data-ttu-id="87c92-119">Je nach Art der Bereitstellung, die im Projekt angegeben ist, hat das Hostsystem die freigegebene .NET Core-Laufzeit installiert oder nicht.</span><span class="sxs-lookup"><span data-stu-id="87c92-119">Depending on the type of deployment that the project specifies, the hosting system may or may not have the .NET Core shared runtime installed on it.</span></span> <span data-ttu-id="87c92-120">Weitere Informationen finden Sie unter [.NET Core Anwendungsbereitstellung](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="87c92-120">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span> <span data-ttu-id="87c92-121">Die Verzeichnisstruktur der veröffentlichten Anwendung finden Sie unter [Directory structure (Verzeichnisstruktur)](/aspnet/core/hosting/directory-structure).</span><span class="sxs-lookup"><span data-stu-id="87c92-121">For the directory structure of a published application, see [Directory structure](/aspnet/core/hosting/directory-structure).</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a><span data-ttu-id="87c92-122">Argumente</span><span class="sxs-lookup"><span data-stu-id="87c92-122">Arguments</span></span>

`PROJECT`

<span data-ttu-id="87c92-123">Das zu veröffentlichende Projekt.</span><span class="sxs-lookup"><span data-stu-id="87c92-123">The project to publish.</span></span> <span data-ttu-id="87c92-124">Dies ist entweder der Pfad und der Dateiname einer [C#](csproj.md)-, F#- oder Visual Basic-Projektdatei oder der Pfad zu einem Verzeichnis mit einer C#-, F#- oder Visual Basic-Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="87c92-124">It's either the path and filename of a [C#](csproj.md), F#, or Visual Basic project file, or the path to a directory that contains a C#, F#, or Visual Basic project file.</span></span> <span data-ttu-id="87c92-125">Wenn nicht angegeben, wird standardmäßig das aktuelle Verzeichnis gewählt.</span><span class="sxs-lookup"><span data-stu-id="87c92-125">If not specified, it defaults to the current directory.</span></span>

## <a name="options"></a><span data-ttu-id="87c92-126">Optionen</span><span class="sxs-lookup"><span data-stu-id="87c92-126">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="87c92-127">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="87c92-127">.NET Core 2.1</span></span>](#tab/netcore21)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="87c92-128">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="87c92-128">Defines the build configuration.</span></span> <span data-ttu-id="87c92-129">Der Standardwert ist `Debug`sein.</span><span class="sxs-lookup"><span data-stu-id="87c92-129">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="87c92-130">Veröffentlicht die Anwendung für das angegebene [Zielframework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="87c92-130">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="87c92-131">Sie müssen das Zielframework in der Projektdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="87c92-131">You must specify the target framework in the project file.</span></span>

`--force`

<span data-ttu-id="87c92-132">Erzwingt das Auflösen aller Abhängigkeiten, auch wenn die letzte Wiederherstellung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="87c92-132">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="87c92-133">Dieses Flag anzugeben, entspricht dem Löschen der Datei *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="87c92-133">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="87c92-134">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="87c92-134">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="87c92-135">Gibt mindestens ein [Zielmanifest](../deploying/runtime-store.md) an, das verwendet wird, um die Menge an mit der App veröffentlichten Paketen zu senken.</span><span class="sxs-lookup"><span data-stu-id="87c92-135">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="87c92-136">Die Manifestdatei ist Teil der Ausgabe des [`dotnet store`-Befehls](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="87c92-136">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="87c92-137">Um mehrere Manifeste anzugeben, fügen Sie die `--manifest`-Option für jedes Manifest hinzu.</span><span class="sxs-lookup"><span data-stu-id="87c92-137">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="87c92-138">Diese Option ist am dem .NET Core 2.0 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="87c92-138">This option is available starting with .NET Core 2.0 SDK.</span></span>

`--no-build`

<span data-ttu-id="87c92-139">Erstellt das Projekt nicht vor der Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="87c92-139">Doesn't build the project before publishing.</span></span> <span data-ttu-id="87c92-140">Zudem wird das Flag `--no-restore` implizit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="87c92-140">It also implicitly sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="87c92-141">Ignoriert Verweise zwischen Projekten und stellt nur das zum Erstellen angegebene Stammprojekt wieder her.</span><span class="sxs-lookup"><span data-stu-id="87c92-141">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="87c92-142">Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="87c92-142">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="87c92-143">Gibt den Pfad für das Ausgabeverzeichnis an.</span><span class="sxs-lookup"><span data-stu-id="87c92-143">Specifies the path for the output directory.</span></span> <span data-ttu-id="87c92-144">Wenn nicht angegeben, wird standardmäßig *./bin/[configuration]/[framework]/publish/* für eine Framework-abhängige Bereitstellung oder *./bin/[configuration]/[framework]/[runtime]/publish/* für eine eigenständige Bereitstellung gewählt.</span><span class="sxs-lookup"><span data-stu-id="87c92-144">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="87c92-145">Bei einem relativen Pfad ist das generierte Ausgabeverzeichnis relativ zum Speicherort der Projektdatei anstatt zum aktuellen Arbeitsverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="87c92-145">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`--self-contained`

<span data-ttu-id="87c92-146">Veröffentlicht die .NET Core-Runtime mit Ihrer Anwendung, sodass die Runtime nicht auf dem Zielcomputer installiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="87c92-146">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="87c92-147">Wenn ein Runtimebezeichner angegeben ist, ist der Standardwert `true`.</span><span class="sxs-lookup"><span data-stu-id="87c92-147">If a runtime identifier is specified, its default value is `true`.</span></span> <span data-ttu-id="87c92-148">Weitere Informationen zu den verschiedenen Bereitstellungstypen finden Sie unter [.NET Core application deployment (Bereitstellung von .NET Core-Anwendungen)](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="87c92-148">For more information about the different deployment types, see [.NET Core application deployment](../deploying/index.md).</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="87c92-149">Veröffentlicht die Anwendung für eine bestimmte Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="87c92-149">Publishes the application for a given runtime.</span></span> <span data-ttu-id="87c92-150">Wird bei der Erstellung einer [eigenständigen Bereitstellung (Self-contained deployments, SCD)](../deploying/index.md#self-contained-deployments-scd) verwendet.</span><span class="sxs-lookup"><span data-stu-id="87c92-150">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="87c92-151">Eine Liste der Runtime-IDs (RIDs) finden Sie im [RID-Katalog](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="87c92-151">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="87c92-152">Standardmäßig wird eine [Framework-abhängige Bereitstellung (FDD)](../deploying/index.md#framework-dependent-deployments-fdd) veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="87c92-152">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="87c92-153">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="87c92-153">Sets the verbosity level of the command.</span></span> <span data-ttu-id="87c92-154">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="87c92-154">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="87c92-155">Definiert das Versionssuffix zum Ersetzen des Sternchens (`*`) im Versionsfeld der Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="87c92-155">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="87c92-156">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="87c92-156">.NET Core 2.0</span></span>](#tab/netcore20)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="87c92-157">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="87c92-157">Defines the build configuration.</span></span> <span data-ttu-id="87c92-158">Der Standardwert ist `Debug`sein.</span><span class="sxs-lookup"><span data-stu-id="87c92-158">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="87c92-159">Veröffentlicht die Anwendung für das angegebene [Zielframework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="87c92-159">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="87c92-160">Sie müssen das Zielframework in der Projektdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="87c92-160">You must specify the target framework in the project file.</span></span>

`--force`

<span data-ttu-id="87c92-161">Erzwingt das Auflösen aller Abhängigkeiten, auch wenn die letzte Wiederherstellung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="87c92-161">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="87c92-162">Dieses Flag anzugeben, entspricht dem Löschen der Datei *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="87c92-162">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="87c92-163">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="87c92-163">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="87c92-164">Gibt mindestens ein [Zielmanifest](../deploying/runtime-store.md) an, das verwendet wird, um die Menge an mit der App veröffentlichten Paketen zu senken.</span><span class="sxs-lookup"><span data-stu-id="87c92-164">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="87c92-165">Die Manifestdatei ist Teil der Ausgabe des [`dotnet store`-Befehls](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="87c92-165">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="87c92-166">Um mehrere Manifeste anzugeben, fügen Sie die `--manifest`-Option für jedes Manifest hinzu.</span><span class="sxs-lookup"><span data-stu-id="87c92-166">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="87c92-167">Diese Option ist am dem .NET Core 2.0 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="87c92-167">This option is available starting with .NET Core 2.0 SDK.</span></span>

`--no-dependencies`

<span data-ttu-id="87c92-168">Ignoriert Verweise zwischen Projekten und stellt nur das zum Erstellen angegebene Stammprojekt wieder her.</span><span class="sxs-lookup"><span data-stu-id="87c92-168">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="87c92-169">Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="87c92-169">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="87c92-170">Gibt den Pfad für das Ausgabeverzeichnis an.</span><span class="sxs-lookup"><span data-stu-id="87c92-170">Specifies the path for the output directory.</span></span> <span data-ttu-id="87c92-171">Wenn nicht angegeben, wird standardmäßig *./bin/[configuration]/[framework]/publish/* für eine Framework-abhängige Bereitstellung oder *./bin/[configuration]/[framework]/[runtime]/publish/* für eine eigenständige Bereitstellung gewählt.</span><span class="sxs-lookup"><span data-stu-id="87c92-171">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="87c92-172">Bei einem relativen Pfad ist das generierte Ausgabeverzeichnis relativ zum Speicherort der Projektdatei anstatt zum aktuellen Arbeitsverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="87c92-172">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`--self-contained`

<span data-ttu-id="87c92-173">Veröffentlicht die .NET Core-Runtime mit Ihrer Anwendung, sodass die Runtime nicht auf dem Zielcomputer installiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="87c92-173">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="87c92-174">Wenn ein Runtimebezeichner angegeben ist, ist der Standardwert `true`.</span><span class="sxs-lookup"><span data-stu-id="87c92-174">If a runtime identifier is specified, its default value is `true`.</span></span> <span data-ttu-id="87c92-175">Weitere Informationen zu den verschiedenen Bereitstellungstypen finden Sie unter [.NET Core application deployment (Bereitstellung von .NET Core-Anwendungen)](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="87c92-175">For more information about the different deployment types, see [.NET Core application deployment](../deploying/index.md).</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="87c92-176">Veröffentlicht die Anwendung für eine bestimmte Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="87c92-176">Publishes the application for a given runtime.</span></span> <span data-ttu-id="87c92-177">Wird bei der Erstellung einer [eigenständigen Bereitstellung (Self-contained deployments, SCD)](../deploying/index.md#self-contained-deployments-scd) verwendet.</span><span class="sxs-lookup"><span data-stu-id="87c92-177">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="87c92-178">Eine Liste der Runtime-IDs (RIDs) finden Sie im [RID-Katalog](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="87c92-178">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="87c92-179">Standardmäßig wird eine [Framework-abhängige Bereitstellung (FDD)](../deploying/index.md#framework-dependent-deployments-fdd) veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="87c92-179">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="87c92-180">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="87c92-180">Sets the verbosity level of the command.</span></span> <span data-ttu-id="87c92-181">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="87c92-181">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="87c92-182">Definiert das Versionssuffix zum Ersetzen des Sternchens (`*`) im Versionsfeld der Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="87c92-182">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="87c92-183">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="87c92-183">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="87c92-184">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="87c92-184">Defines the build configuration.</span></span> <span data-ttu-id="87c92-185">Der Standardwert ist `Debug`sein.</span><span class="sxs-lookup"><span data-stu-id="87c92-185">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="87c92-186">Veröffentlicht die Anwendung für das angegebene [Zielframework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="87c92-186">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="87c92-187">Sie müssen das Zielframework in der Projektdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="87c92-187">You must specify the target framework in the project file.</span></span>

`-h|--help`

<span data-ttu-id="87c92-188">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="87c92-188">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="87c92-189">Gibt mindestens ein [Zielmanifest](../deploying/runtime-store.md) an, das verwendet wird, um die Menge an mit der App veröffentlichten Paketen zu senken.</span><span class="sxs-lookup"><span data-stu-id="87c92-189">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="87c92-190">Die Manifestdatei ist Teil der Ausgabe des [`dotnet store`-Befehls](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="87c92-190">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="87c92-191">Um mehrere Manifeste anzugeben, fügen Sie die `--manifest`-Option für jedes Manifest hinzu.</span><span class="sxs-lookup"><span data-stu-id="87c92-191">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="87c92-192">Diese Option ist am dem .NET Core 2.0 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="87c92-192">This option is available starting with .NET Core 2.0 SDK.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="87c92-193">Gibt den Pfad für das Ausgabeverzeichnis an.</span><span class="sxs-lookup"><span data-stu-id="87c92-193">Specifies the path for the output directory.</span></span> <span data-ttu-id="87c92-194">Wenn nicht angegeben, wird standardmäßig *./bin/[configuration]/[framework]/publish/* für eine Framework-abhängige Bereitstellung oder *./bin/[configuration]/[framework]/[runtime]/publish/* für eine eigenständige Bereitstellung gewählt.</span><span class="sxs-lookup"><span data-stu-id="87c92-194">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="87c92-195">Bei einem relativen Pfad ist das generierte Ausgabeverzeichnis relativ zum Speicherort der Projektdatei anstatt zum aktuellen Arbeitsverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="87c92-195">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="87c92-196">Veröffentlicht die Anwendung für eine bestimmte Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="87c92-196">Publishes the application for a given runtime.</span></span> <span data-ttu-id="87c92-197">Wird bei der Erstellung einer [eigenständigen Bereitstellung (Self-contained deployments, SCD)](../deploying/index.md#self-contained-deployments-scd) verwendet.</span><span class="sxs-lookup"><span data-stu-id="87c92-197">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="87c92-198">Eine Liste der Runtime-IDs (RIDs) finden Sie im [RID-Katalog](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="87c92-198">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="87c92-199">Standardmäßig wird eine [Framework-abhängige Bereitstellung (FDD)](../deploying/index.md#framework-dependent-deployments-fdd) veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="87c92-199">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="87c92-200">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="87c92-200">Sets the verbosity level of the command.</span></span> <span data-ttu-id="87c92-201">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="87c92-201">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="87c92-202">Definiert das Versionssuffix zum Ersetzen des Sternchens (`*`) im Versionsfeld der Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="87c92-202">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

---

## <a name="examples"></a><span data-ttu-id="87c92-203">Beispiele</span><span class="sxs-lookup"><span data-stu-id="87c92-203">Examples</span></span>

<span data-ttu-id="87c92-204">Veröffentlicht das Projekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="87c92-204">Publish the project in the current directory:</span></span>

`dotnet publish`

<span data-ttu-id="87c92-205">Veröffentlichen Sie die Anwendung unter Verwendung der angegebenen Projektdatei:</span><span class="sxs-lookup"><span data-stu-id="87c92-205">Publish the application using the specified project file:</span></span>

`dotnet publish ~/projects/app1/app1.csproj`

<span data-ttu-id="87c92-206">Veröffentlichen Sie das Projekt aus dem aktuellen Verzeichnis unter Verwendung des `netcoreapp1.1`-Frameworks:</span><span class="sxs-lookup"><span data-stu-id="87c92-206">Publish the project in the current directory using the `netcoreapp1.1` framework:</span></span>

`dotnet publish --framework netcoreapp1.1`

<span data-ttu-id="87c92-207">Veröffentlichen der aktuellen Anwendung mithilfe des `netcoreapp1.1`-Frameworks und der Laufzeit für `OS X 10.10` (Sie müssen diese RID in der Projektdatei auflisten).</span><span class="sxs-lookup"><span data-stu-id="87c92-207">Publish the current application using the `netcoreapp1.1` framework and the runtime for `OS X 10.10` (you must list this RID in the project file).</span></span>

`dotnet publish --framework netcoreapp1.1 --runtime osx.10.11-x64`

<span data-ttu-id="87c92-208">Veröffentlichen sie die aktuelle Anwendung, aber fügen Sie während der Wiederherstellung keine Projekt-zu-Projekt-Verweise hinzu, sondern nur das Stammprojekt (.NET Core SDK 2.0 und spätere Versionen):</span><span class="sxs-lookup"><span data-stu-id="87c92-208">Publish the current application but don't restore project-to-project (P2P) references, just the root project during the restore operation (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet publish --no-dependencies`

## <a name="see-also"></a><span data-ttu-id="87c92-209">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="87c92-209">See also</span></span>

- [<span data-ttu-id="87c92-210">Zielframeworks</span><span class="sxs-lookup"><span data-stu-id="87c92-210">Target frameworks</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="87c92-211">Runtime-ID-Katalog (RID)</span><span class="sxs-lookup"><span data-stu-id="87c92-211">Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
