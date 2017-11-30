---
title: "dotnet-Befehl – .NET Core-CLI"
description: "Informationen zum dotnet-Befehl (generischer Treiber für die .NET Core CLI-Tools) und dessen Verwendung."
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: bba8d77cda7538bf008dc0f510f9279d3c695c3d
ms.sourcegitcommit: a19548e5167cbe7e9e58df4ffd8c3b23f17d5c7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2017
---
# <a name="dotnet-command"></a><span data-ttu-id="c936a-103">dotnet-Befehl</span><span class="sxs-lookup"><span data-stu-id="c936a-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="c936a-104">Name</span><span class="sxs-lookup"><span data-stu-id="c936a-104">Name</span></span>

<span data-ttu-id="c936a-105">`dotnet`: Allgemeiner Treiber für das Ausführen der Befehlszeilenbefehle.</span><span class="sxs-lookup"><span data-stu-id="c936a-105">`dotnet` - General driver for running the command-line commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c936a-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="c936a-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="c936a-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="c936a-107">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx] [-v|--verbose] [--version]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c936a-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c936a-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet [command] [arguments] [--additionalprobingpath] [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [-v|--verbose] [--version]
```
---

## <a name="description"></a><span data-ttu-id="c936a-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c936a-109">Description</span></span>

<span data-ttu-id="c936a-110">`dotnet` ist ein generischer Treiber für die Befehlszeilenschnittstellen-Toolkette (CLI).</span><span class="sxs-lookup"><span data-stu-id="c936a-110">`dotnet` is a generic driver for the Command Line Interface (CLI) toolchain.</span></span> <span data-ttu-id="c936a-111">Bietet bei eigenständigem Aufruf kurze Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="c936a-111">Invoked on its own, it provides brief usage instructions.</span></span>

<span data-ttu-id="c936a-112">Jede bestimmte Funktion ist als Befehl implementiert.</span><span class="sxs-lookup"><span data-stu-id="c936a-112">Each specific feature is implemented as a command.</span></span> <span data-ttu-id="c936a-113">Um die Funktion zu verwenden, wird der Befehl nach `dotnet` angegeben, wie z.B. [`dotnet build`](dotnet-build.md).</span><span class="sxs-lookup"><span data-stu-id="c936a-113">In order to use the feature, the command is specified after `dotnet`, such as [`dotnet build`](dotnet-build.md).</span></span> <span data-ttu-id="c936a-114">Alle Argumente nach dem Befehl sind die eigenen Argumente.</span><span class="sxs-lookup"><span data-stu-id="c936a-114">All of the arguments following the command are its own arguments.</span></span>

<span data-ttu-id="c936a-115">Nur bei [Framework-abhängigen Apps](../deploying/index.md) wird `dotnet` als eigenständiger Befehl verwendet.</span><span class="sxs-lookup"><span data-stu-id="c936a-115">The only time `dotnet` is used as a command on its own is to run [framework-dependent apps](../deploying/index.md).</span></span> <span data-ttu-id="c936a-116">Geben Sie eine Anwendungs-DLL nach dem Verb `dotnet` an, um die Anwendung auszuführen (zum Beispiel `dotnet myapp.dll`).</span><span class="sxs-lookup"><span data-stu-id="c936a-116">Specify an application DLL after the `dotnet` verb to execute the application (for example, `dotnet myapp.dll`).</span></span>

## <a name="options"></a><span data-ttu-id="c936a-117">Optionen</span><span class="sxs-lookup"><span data-stu-id="c936a-117">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="c936a-118">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="c936a-118">.NET Core 2.x</span></span>](#tab/netcore2x)

`--additionaldeps <PATH>`

<span data-ttu-id="c936a-119">Pfad zur zusätzlichen *deps.json* Datei.</span><span class="sxs-lookup"><span data-stu-id="c936a-119">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="c936a-120">Pfad, der die Suchrichtlinie und die zu suchenden Assemblys enthält.</span><span class="sxs-lookup"><span data-stu-id="c936a-120">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="c936a-121">Ermöglicht die diagnostische Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="c936a-121">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="c936a-122">Version der installierten .NET Core-Laufzeit, die für die Ausführung der Anwendung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c936a-122">Version of the installed .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="c936a-123">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="c936a-123">Prints out a short help for the command.</span></span> <span data-ttu-id="c936a-124">Bei Verwendung mit `dotnet` wird auch eine Liste der verfügbaren Befehle gedruckt.</span><span class="sxs-lookup"><span data-stu-id="c936a-124">If using with `dotnet`, it also prints a list of the available commands.</span></span>

`--info`

<span data-ttu-id="c936a-125">Druckt nähere Informationen zu den CLI-Tools und der Umgebung, z.B. das aktuelle Betriebssystem, den Commit-SHA für die Version und weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="c936a-125">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="c936a-126">Führt ein Rollforward auf ein geteiltes Framework ohne Kandidaten durch.</span><span class="sxs-lookup"><span data-stu-id="c936a-126">Rolls forward on no candidate shared framework.</span></span>

`-v|--verbose`

<span data-ttu-id="c936a-127">Aktiviert die ausführliche Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="c936a-127">Enables verbose output.</span></span>

`--version`

<span data-ttu-id="c936a-128">Druckt die Version des verwendeten .NET Core-SDK aus.</span><span class="sxs-lookup"><span data-stu-id="c936a-128">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c936a-129">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c936a-129">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="c936a-130">Pfad, der die Suchrichtlinie und die zu suchenden Assemblys enthält.</span><span class="sxs-lookup"><span data-stu-id="c936a-130">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="c936a-131">Ermöglicht die diagnostische Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="c936a-131">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="c936a-132">Version der installierten .NET Core-Laufzeit, die für die Ausführung der Anwendung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c936a-132">Version of the installed .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="c936a-133">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="c936a-133">Prints out a short help for the command.</span></span> <span data-ttu-id="c936a-134">Bei Verwendung mit `dotnet` wird auch eine Liste der verfügbaren Befehle gedruckt.</span><span class="sxs-lookup"><span data-stu-id="c936a-134">If using with `dotnet`, it also prints a list of the available commands.</span></span>

`--info`

<span data-ttu-id="c936a-135">Druckt nähere Informationen zu den CLI-Tools und der Umgebung, z.B. das aktuelle Betriebssystem, den Commit-SHA für die Version und weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="c936a-135">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`-v|--verbose`

<span data-ttu-id="c936a-136">Aktiviert die ausführliche Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="c936a-136">Enables verbose output.</span></span>

`--version`

<span data-ttu-id="c936a-137">Druckt die Version des verwendeten .NET Core-SDK aus.</span><span class="sxs-lookup"><span data-stu-id="c936a-137">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="c936a-138">dotnet-Befehle</span><span class="sxs-lookup"><span data-stu-id="c936a-138">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="c936a-139">Allgemein</span><span class="sxs-lookup"><span data-stu-id="c936a-139">General</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="c936a-140">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="c936a-140">.NET Core 2.x</span></span>](#tab/netcore2x)

| <span data-ttu-id="c936a-141">Befehl</span><span class="sxs-lookup"><span data-stu-id="c936a-141">Command</span></span>                             | <span data-ttu-id="c936a-142">Funktion</span><span class="sxs-lookup"><span data-stu-id="c936a-142">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="c936a-143">dotnet build</span><span class="sxs-lookup"><span data-stu-id="c936a-143">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="c936a-144">Erstellt eine .NET Core-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="c936a-144">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="c936a-145">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="c936a-145">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="c936a-146">Bereinigen von Buildausgaben.</span><span class="sxs-lookup"><span data-stu-id="c936a-146">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="c936a-147">dotnet help</span><span class="sxs-lookup"><span data-stu-id="c936a-147">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="c936a-148">Zeigt eine ausführlichere Onlinedokumentation für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="c936a-148">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="c936a-149">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="c936a-149">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="c936a-150">Migriert ein gültiges Preview 2-Projekt in ein .NET Core SDK 1.0-Projekt.</span><span class="sxs-lookup"><span data-stu-id="c936a-150">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="c936a-151">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="c936a-151">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="c936a-152">Ermöglicht den Zugriff auf die MSBuild-Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="c936a-152">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="c936a-153">dotnet new</span><span class="sxs-lookup"><span data-stu-id="c936a-153">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="c936a-154">Initialisiert ein C#- oder F#-Projekt für eine bestimmte Vorlage.</span><span class="sxs-lookup"><span data-stu-id="c936a-154">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="c936a-155">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="c936a-155">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="c936a-156">Erstellt ein NuGet-Paket aus Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="c936a-156">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="c936a-157">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="c936a-157">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="c936a-158">Veröffentlicht eine .NET Framework-abhängige oder eigenständige Anwendung.</span><span class="sxs-lookup"><span data-stu-id="c936a-158">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="c936a-159">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="c936a-159">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="c936a-160">Stellt die Abhängigkeiten für eine bestimmte Anwendung wieder her.</span><span class="sxs-lookup"><span data-stu-id="c936a-160">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="c936a-161">dotnet run</span><span class="sxs-lookup"><span data-stu-id="c936a-161">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="c936a-162">Führt die Anwendung aus der Quelle aus.</span><span class="sxs-lookup"><span data-stu-id="c936a-162">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="c936a-163">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="c936a-163">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="c936a-164">Optionen zum Hinzufügen, Entfernen und Listen von Projekten in einer Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="c936a-164">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="c936a-165">dotnet store</span><span class="sxs-lookup"><span data-stu-id="c936a-165">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="c936a-166">Speichert Assemblys im Laufzeitpaketspeicher.</span><span class="sxs-lookup"><span data-stu-id="c936a-166">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="c936a-167">dotnet test</span><span class="sxs-lookup"><span data-stu-id="c936a-167">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="c936a-168">Führt Tests mit einem Test Runner aus.</span><span class="sxs-lookup"><span data-stu-id="c936a-168">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c936a-169">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c936a-169">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="c936a-170">Befehl</span><span class="sxs-lookup"><span data-stu-id="c936a-170">Command</span></span>                             | <span data-ttu-id="c936a-171">Funktion</span><span class="sxs-lookup"><span data-stu-id="c936a-171">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="c936a-172">dotnet build</span><span class="sxs-lookup"><span data-stu-id="c936a-172">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="c936a-173">Erstellt eine .NET Core-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="c936a-173">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="c936a-174">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="c936a-174">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="c936a-175">Bereinigen von Buildausgaben.</span><span class="sxs-lookup"><span data-stu-id="c936a-175">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="c936a-176">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="c936a-176">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="c936a-177">Migriert ein gültiges Preview 2-Projekt in ein .NET Core SDK 1.0-Projekt.</span><span class="sxs-lookup"><span data-stu-id="c936a-177">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="c936a-178">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="c936a-178">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="c936a-179">Ermöglicht den Zugriff auf die MSBuild-Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="c936a-179">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="c936a-180">dotnet new</span><span class="sxs-lookup"><span data-stu-id="c936a-180">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="c936a-181">Initialisiert ein C#- oder F#-Projekt für eine bestimmte Vorlage.</span><span class="sxs-lookup"><span data-stu-id="c936a-181">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="c936a-182">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="c936a-182">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="c936a-183">Erstellt ein NuGet-Paket aus Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="c936a-183">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="c936a-184">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="c936a-184">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="c936a-185">Veröffentlicht eine .NET Framework-abhängige oder eigenständige Anwendung.</span><span class="sxs-lookup"><span data-stu-id="c936a-185">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="c936a-186">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="c936a-186">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="c936a-187">Stellt die Abhängigkeiten für eine bestimmte Anwendung wieder her.</span><span class="sxs-lookup"><span data-stu-id="c936a-187">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="c936a-188">dotnet run</span><span class="sxs-lookup"><span data-stu-id="c936a-188">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="c936a-189">Führt die Anwendung aus der Quelle aus.</span><span class="sxs-lookup"><span data-stu-id="c936a-189">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="c936a-190">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="c936a-190">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="c936a-191">Optionen zum Hinzufügen, Entfernen und Listen von Projekten in einer Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="c936a-191">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="c936a-192">dotnet test</span><span class="sxs-lookup"><span data-stu-id="c936a-192">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="c936a-193">Führt Tests mit einem Test Runner aus.</span><span class="sxs-lookup"><span data-stu-id="c936a-193">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="c936a-194">Projektverweise</span><span class="sxs-lookup"><span data-stu-id="c936a-194">Project references</span></span>

<span data-ttu-id="c936a-195">Befehl</span><span class="sxs-lookup"><span data-stu-id="c936a-195">Command</span></span> | <span data-ttu-id="c936a-196">Funktion</span><span class="sxs-lookup"><span data-stu-id="c936a-196">Function</span></span>
--- | ---
[<span data-ttu-id="c936a-197">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="c936a-197">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="c936a-198">Projektverweis hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c936a-198">Add a project reference.</span></span>
[<span data-ttu-id="c936a-199">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="c936a-199">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="c936a-200">Projektverweise auflisten.</span><span class="sxs-lookup"><span data-stu-id="c936a-200">List project references.</span></span>
[<span data-ttu-id="c936a-201">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="c936a-201">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="c936a-202">Einen Projektverweis entfernen.</span><span class="sxs-lookup"><span data-stu-id="c936a-202">Remove a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="c936a-203">NuGet-Pakete</span><span class="sxs-lookup"><span data-stu-id="c936a-203">NuGet packages</span></span>

<span data-ttu-id="c936a-204">Befehl</span><span class="sxs-lookup"><span data-stu-id="c936a-204">Command</span></span> | <span data-ttu-id="c936a-205">Funktion</span><span class="sxs-lookup"><span data-stu-id="c936a-205">Function</span></span>
--- | ---
[<span data-ttu-id="c936a-206">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="c936a-206">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="c936a-207">Ein NuGet-Paket hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c936a-207">Add a NuGet package.</span></span>
[<span data-ttu-id="c936a-208">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="c936a-208">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="c936a-209">Ein NuGet-Paket entfernen.</span><span class="sxs-lookup"><span data-stu-id="c936a-209">Remove a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="c936a-210">NuGet-Befehle</span><span class="sxs-lookup"><span data-stu-id="c936a-210">NuGet commands</span></span>

<span data-ttu-id="c936a-211">Befehl</span><span class="sxs-lookup"><span data-stu-id="c936a-211">Command</span></span> | <span data-ttu-id="c936a-212">Funktion</span><span class="sxs-lookup"><span data-stu-id="c936a-212">Function</span></span>
--- | ---
[<span data-ttu-id="c936a-213">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="c936a-213">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="c936a-214">Löscht ein Paket vom Server oder hebt dessen Auflistung auf.</span><span class="sxs-lookup"><span data-stu-id="c936a-214">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="c936a-215">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="c936a-215">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="c936a-216">Löscht lokale NuGet-Ressourcen, z.B. den http-Anforderungscache, den temporären Cache oder den Ordner mit globalen Paketen auf dem Computer, oder listet diese Ressourcen auf.</span><span class="sxs-lookup"><span data-stu-id="c936a-216">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="c936a-217">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="c936a-217">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="c936a-218">Überträgt ein Paket auf den Server und veröffentlicht es.</span><span class="sxs-lookup"><span data-stu-id="c936a-218">Pushes a package to the server and publishes it.</span></span>

## <a name="examples"></a><span data-ttu-id="c936a-219">Beispiele</span><span class="sxs-lookup"><span data-stu-id="c936a-219">Examples</span></span>

<span data-ttu-id="c936a-220">Initialisieren einer .NET Core-Konsolenanwendung, die kompiliert und ausgeführt werden kann:</span><span class="sxs-lookup"><span data-stu-id="c936a-220">Initialize a sample .NET Core console application that can be compiled and run:</span></span>

`dotnet new console`

<span data-ttu-id="c936a-221">Wiederherstellen von Abhängigkeiten für eine bestimmte Anwendung:</span><span class="sxs-lookup"><span data-stu-id="c936a-221">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="c936a-222">Erstellen eines Projekts und seiner Abhängigkeiten in einem vorgegebenen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="c936a-222">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="c936a-223">Führen Sie eine Framework-abhängige Anwendung mit dem Namen `myapp.dll` aus:</span><span class="sxs-lookup"><span data-stu-id="c936a-223">Run a framework-dependent app named `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="c936a-224">Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="c936a-224">Environment variables</span></span>

`DOTNET_PACKAGES`

<span data-ttu-id="c936a-225">Der Cache des primären Pakets.</span><span class="sxs-lookup"><span data-stu-id="c936a-225">The primary package cache.</span></span> <span data-ttu-id="c936a-226">Wenn er nicht festgelegt wird, wird standardmäßig `$HOME/.nuget/packages` unter Unix oder `%HOME%\NuGet\Packages` unter Windows verwendet.</span><span class="sxs-lookup"><span data-stu-id="c936a-226">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="c936a-227">Gibt den Speicherort des Wartungsindex an, der vom freigegebenen Host verwendet wird, wenn die Laufzeit geladen wird.</span><span class="sxs-lookup"><span data-stu-id="c936a-227">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="c936a-228">Gibt an, ob Daten zur Nutzung von .NET Core-Tools gesammelt und an Microsoft gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="c936a-228">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="c936a-229">Legen Sie sie auf `true` fest, um die Telemetriefunktion zu deaktivieren (Werte `true`, `1` oder `yes` werden akzeptiert); legen Sie sie andernfalls auf `false` fest, um die Telemetriefunktionen zu aktivieren (Werte `false`, `0` oder `no` werden akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="c936a-229">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted); otherwise, set to `false` to opt-in to the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="c936a-230">Wenn sie nicht festgelegt wird, ist der Standardwert `false`, und die Telemetriefunktion ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="c936a-230">If not set, the defaults is `false`, and the telemetry feature is active.</span></span>
