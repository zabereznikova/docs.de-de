---
title: dotnet-Befehl – .NET Core-CLI
description: Informationen zum dotnet-Befehl (generischer Treiber für die .NET Core CLI-Tools) und dessen Verwendung.
author: mairaw
ms.author: mairaw
ms.date: 03/20/2018
ms.openlocfilehash: c56ed032ccef6c6fd19a13214b04b384ffff28d5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="dotnet-command"></a><span data-ttu-id="6f740-103">dotnet-Befehl</span><span class="sxs-lookup"><span data-stu-id="6f740-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="6f740-104">name</span><span class="sxs-lookup"><span data-stu-id="6f740-104">Name</span></span>

<span data-ttu-id="6f740-105">`dotnet`: Allgemeiner Treiber für das Ausführen der Befehlszeilenbefehle.</span><span class="sxs-lookup"><span data-stu-id="6f740-105">`dotnet` - General driver for running the command-line commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="6f740-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="6f740-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="6f740-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="6f740-107">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="6f740-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="6f740-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet [command] [arguments] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [-v|--verbosity] [--version]
```
---

## <a name="description"></a><span data-ttu-id="6f740-109">description</span><span class="sxs-lookup"><span data-stu-id="6f740-109">Description</span></span>

<span data-ttu-id="6f740-110">`dotnet` ist ein generischer Treiber für die Befehlszeilenschnittstellen-Toolkette (CLI).</span><span class="sxs-lookup"><span data-stu-id="6f740-110">`dotnet` is a generic driver for the Command Line Interface (CLI) toolchain.</span></span> <span data-ttu-id="6f740-111">Bietet bei eigenständigem Aufruf kurze Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="6f740-111">Invoked on its own, it provides brief usage instructions.</span></span>

<span data-ttu-id="6f740-112">Jede bestimmte Funktion ist als Befehl implementiert.</span><span class="sxs-lookup"><span data-stu-id="6f740-112">Each specific feature is implemented as a command.</span></span> <span data-ttu-id="6f740-113">Um die Funktion zu verwenden, wird der Befehl nach `dotnet` angegeben, wie z.B. [`dotnet build`](dotnet-build.md).</span><span class="sxs-lookup"><span data-stu-id="6f740-113">In order to use the feature, the command is specified after `dotnet`, such as [`dotnet build`](dotnet-build.md).</span></span> <span data-ttu-id="6f740-114">Alle Argumente nach dem Befehl sind die eigenen Argumente.</span><span class="sxs-lookup"><span data-stu-id="6f740-114">All of the arguments following the command are its own arguments.</span></span>

<span data-ttu-id="6f740-115">Nur bei [Framework-abhängigen Apps](../deploying/index.md) wird `dotnet` als eigenständiger Befehl verwendet.</span><span class="sxs-lookup"><span data-stu-id="6f740-115">The only time `dotnet` is used as a command on its own is to run [framework-dependent apps](../deploying/index.md).</span></span> <span data-ttu-id="6f740-116">Geben Sie eine Anwendungs-DLL nach dem Verb `dotnet` an, um die Anwendung auszuführen (zum Beispiel `dotnet myapp.dll`).</span><span class="sxs-lookup"><span data-stu-id="6f740-116">Specify an application DLL after the `dotnet` verb to execute the application (for example, `dotnet myapp.dll`).</span></span>

## <a name="options"></a><span data-ttu-id="6f740-117">Optionen</span><span class="sxs-lookup"><span data-stu-id="6f740-117">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="6f740-118">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="6f740-118">.NET Core 2.x</span></span>](#tab/netcore2x)

`--additional-deps <PATH>`

<span data-ttu-id="6f740-119">Pfad zur zusätzlichen *deps.json*-Datei.</span><span class="sxs-lookup"><span data-stu-id="6f740-119">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="6f740-120">Pfad, der die Suchrichtlinie und die zu suchenden Assemblys enthält.</span><span class="sxs-lookup"><span data-stu-id="6f740-120">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="6f740-121">Ermöglicht die diagnostische Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="6f740-121">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="6f740-122">Version der installierten .NET Core-Laufzeit, die für die Ausführung der Anwendung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="6f740-122">Version of the installed .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="6f740-123">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="6f740-123">Prints out a short help for the command.</span></span> <span data-ttu-id="6f740-124">Bei Verwendung mit `dotnet` wird auch eine Liste der verfügbaren Befehle gedruckt.</span><span class="sxs-lookup"><span data-stu-id="6f740-124">If using with `dotnet`, it also prints a list of the available commands.</span></span>

`--info`

<span data-ttu-id="6f740-125">Druckt nähere Informationen zu den CLI-Tools und der Umgebung, z.B. das aktuelle Betriebssystem, den Commit-SHA für die Version und weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="6f740-125">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="6f740-126">Führt ein Rollforward auf ein geteiltes Framework ohne Kandidaten durch.</span><span class="sxs-lookup"><span data-stu-id="6f740-126">Rolls forward on no candidate shared framework.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="6f740-127">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="6f740-127">Sets the verbosity level of the command.</span></span> <span data-ttu-id="6f740-128">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="6f740-128">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="6f740-129">Nicht in jedem Befehl unterstützt. Auf der Seite der einzelnen Befehle finden Sie heraus, ob diese Option verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="6f740-129">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="6f740-130">Druckt die Version des verwendeten .NET Core-SDK aus.</span><span class="sxs-lookup"><span data-stu-id="6f740-130">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="6f740-131">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="6f740-131">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="6f740-132">Pfad, der die Suchrichtlinie und die zu suchenden Assemblys enthält.</span><span class="sxs-lookup"><span data-stu-id="6f740-132">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="6f740-133">Ermöglicht die diagnostische Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="6f740-133">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="6f740-134">Version der installierten .NET Core-Laufzeit, die für die Ausführung der Anwendung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="6f740-134">Version of the installed .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="6f740-135">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="6f740-135">Prints out a short help for the command.</span></span> <span data-ttu-id="6f740-136">Bei Verwendung mit `dotnet` wird auch eine Liste der verfügbaren Befehle gedruckt.</span><span class="sxs-lookup"><span data-stu-id="6f740-136">If using with `dotnet`, it also prints a list of the available commands.</span></span>

`--info`

<span data-ttu-id="6f740-137">Druckt nähere Informationen zu den CLI-Tools und der Umgebung, z.B. das aktuelle Betriebssystem, den Commit-SHA für die Version und weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="6f740-137">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="6f740-138">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="6f740-138">Sets the verbosity level of the command.</span></span> <span data-ttu-id="6f740-139">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="6f740-139">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="6f740-140">Nicht in jedem Befehl unterstützt. Auf der Seite der einzelnen Befehle finden Sie heraus, ob diese Option verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="6f740-140">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="6f740-141">Druckt die Version des verwendeten .NET Core-SDK aus.</span><span class="sxs-lookup"><span data-stu-id="6f740-141">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="6f740-142">dotnet-Befehle</span><span class="sxs-lookup"><span data-stu-id="6f740-142">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="6f740-143">Allgemein</span><span class="sxs-lookup"><span data-stu-id="6f740-143">General</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="6f740-144">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="6f740-144">.NET Core 2.x</span></span>](#tab/netcore2x)

| <span data-ttu-id="6f740-145">Befehl</span><span class="sxs-lookup"><span data-stu-id="6f740-145">Command</span></span>                             | <span data-ttu-id="6f740-146">Funktion</span><span class="sxs-lookup"><span data-stu-id="6f740-146">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="6f740-147">dotnet build</span><span class="sxs-lookup"><span data-stu-id="6f740-147">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="6f740-148">Erstellt eine .NET Core-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="6f740-148">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="6f740-149">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="6f740-149">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="6f740-150">Bereinigen von Buildausgaben.</span><span class="sxs-lookup"><span data-stu-id="6f740-150">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="6f740-151">dotnet help</span><span class="sxs-lookup"><span data-stu-id="6f740-151">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="6f740-152">Zeigt eine ausführlichere Onlinedokumentation für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="6f740-152">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="6f740-153">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="6f740-153">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="6f740-154">Migriert ein gültiges Preview 2-Projekt in ein .NET Core SDK 1.0-Projekt.</span><span class="sxs-lookup"><span data-stu-id="6f740-154">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="6f740-155">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="6f740-155">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="6f740-156">Ermöglicht den Zugriff auf die MSBuild-Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="6f740-156">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="6f740-157">dotnet new</span><span class="sxs-lookup"><span data-stu-id="6f740-157">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="6f740-158">Initialisiert ein C#- oder F#-Projekt für eine bestimmte Vorlage.</span><span class="sxs-lookup"><span data-stu-id="6f740-158">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="6f740-159">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="6f740-159">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="6f740-160">Erstellt ein NuGet-Paket aus Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="6f740-160">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="6f740-161">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="6f740-161">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="6f740-162">Veröffentlicht eine .NET Framework-abhängige oder eigenständige Anwendung.</span><span class="sxs-lookup"><span data-stu-id="6f740-162">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="6f740-163">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="6f740-163">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="6f740-164">Stellt die Abhängigkeiten für eine bestimmte Anwendung wieder her.</span><span class="sxs-lookup"><span data-stu-id="6f740-164">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="6f740-165">dotnet run</span><span class="sxs-lookup"><span data-stu-id="6f740-165">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="6f740-166">Führt die Anwendung aus der Quelle aus.</span><span class="sxs-lookup"><span data-stu-id="6f740-166">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="6f740-167">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="6f740-167">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="6f740-168">Optionen zum Hinzufügen, Entfernen und Listen von Projekten in einer Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="6f740-168">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="6f740-169">dotnet store</span><span class="sxs-lookup"><span data-stu-id="6f740-169">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="6f740-170">Speichert Assemblys im Laufzeitpaketspeicher.</span><span class="sxs-lookup"><span data-stu-id="6f740-170">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="6f740-171">dotnet test</span><span class="sxs-lookup"><span data-stu-id="6f740-171">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="6f740-172">Führt Tests mit einem Test Runner aus.</span><span class="sxs-lookup"><span data-stu-id="6f740-172">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="6f740-173">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="6f740-173">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="6f740-174">Befehl</span><span class="sxs-lookup"><span data-stu-id="6f740-174">Command</span></span>                             | <span data-ttu-id="6f740-175">Funktion</span><span class="sxs-lookup"><span data-stu-id="6f740-175">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="6f740-176">dotnet build</span><span class="sxs-lookup"><span data-stu-id="6f740-176">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="6f740-177">Erstellt eine .NET Core-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="6f740-177">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="6f740-178">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="6f740-178">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="6f740-179">Bereinigen von Buildausgaben.</span><span class="sxs-lookup"><span data-stu-id="6f740-179">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="6f740-180">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="6f740-180">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="6f740-181">Migriert ein gültiges Preview 2-Projekt in ein .NET Core SDK 1.0-Projekt.</span><span class="sxs-lookup"><span data-stu-id="6f740-181">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="6f740-182">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="6f740-182">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="6f740-183">Ermöglicht den Zugriff auf die MSBuild-Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="6f740-183">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="6f740-184">dotnet new</span><span class="sxs-lookup"><span data-stu-id="6f740-184">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="6f740-185">Initialisiert ein C#- oder F#-Projekt für eine bestimmte Vorlage.</span><span class="sxs-lookup"><span data-stu-id="6f740-185">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="6f740-186">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="6f740-186">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="6f740-187">Erstellt ein NuGet-Paket aus Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="6f740-187">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="6f740-188">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="6f740-188">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="6f740-189">Veröffentlicht eine .NET Framework-abhängige oder eigenständige Anwendung.</span><span class="sxs-lookup"><span data-stu-id="6f740-189">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="6f740-190">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="6f740-190">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="6f740-191">Stellt die Abhängigkeiten für eine bestimmte Anwendung wieder her.</span><span class="sxs-lookup"><span data-stu-id="6f740-191">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="6f740-192">dotnet run</span><span class="sxs-lookup"><span data-stu-id="6f740-192">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="6f740-193">Führt die Anwendung aus der Quelle aus.</span><span class="sxs-lookup"><span data-stu-id="6f740-193">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="6f740-194">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="6f740-194">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="6f740-195">Optionen zum Hinzufügen, Entfernen und Listen von Projekten in einer Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="6f740-195">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="6f740-196">dotnet test</span><span class="sxs-lookup"><span data-stu-id="6f740-196">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="6f740-197">Führt Tests mit einem Test Runner aus.</span><span class="sxs-lookup"><span data-stu-id="6f740-197">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="6f740-198">Projektverweise</span><span class="sxs-lookup"><span data-stu-id="6f740-198">Project references</span></span>

<span data-ttu-id="6f740-199">Befehl</span><span class="sxs-lookup"><span data-stu-id="6f740-199">Command</span></span> | <span data-ttu-id="6f740-200">Funktion</span><span class="sxs-lookup"><span data-stu-id="6f740-200">Function</span></span>
--- | ---
[<span data-ttu-id="6f740-201">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="6f740-201">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="6f740-202">Projektverweis hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6f740-202">Add a project reference.</span></span>
[<span data-ttu-id="6f740-203">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="6f740-203">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="6f740-204">Projektverweise auflisten.</span><span class="sxs-lookup"><span data-stu-id="6f740-204">List project references.</span></span>
[<span data-ttu-id="6f740-205">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="6f740-205">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="6f740-206">Einen Projektverweis entfernen.</span><span class="sxs-lookup"><span data-stu-id="6f740-206">Remove a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="6f740-207">NuGet-Pakete</span><span class="sxs-lookup"><span data-stu-id="6f740-207">NuGet packages</span></span>

<span data-ttu-id="6f740-208">Befehl</span><span class="sxs-lookup"><span data-stu-id="6f740-208">Command</span></span> | <span data-ttu-id="6f740-209">Funktion</span><span class="sxs-lookup"><span data-stu-id="6f740-209">Function</span></span>
--- | ---
[<span data-ttu-id="6f740-210">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="6f740-210">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="6f740-211">Ein NuGet-Paket hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6f740-211">Add a NuGet package.</span></span>
[<span data-ttu-id="6f740-212">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="6f740-212">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="6f740-213">Ein NuGet-Paket entfernen.</span><span class="sxs-lookup"><span data-stu-id="6f740-213">Remove a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="6f740-214">NuGet-Befehle</span><span class="sxs-lookup"><span data-stu-id="6f740-214">NuGet commands</span></span>

<span data-ttu-id="6f740-215">Befehl</span><span class="sxs-lookup"><span data-stu-id="6f740-215">Command</span></span> | <span data-ttu-id="6f740-216">Funktion</span><span class="sxs-lookup"><span data-stu-id="6f740-216">Function</span></span>
--- | ---
[<span data-ttu-id="6f740-217">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="6f740-217">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="6f740-218">Löscht ein Paket vom Server oder hebt dessen Auflistung auf.</span><span class="sxs-lookup"><span data-stu-id="6f740-218">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="6f740-219">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="6f740-219">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="6f740-220">Löscht lokale NuGet-Ressourcen, z.B. den http-Anforderungscache, den temporären Cache oder den Ordner mit globalen Paketen auf dem Computer, oder listet diese Ressourcen auf.</span><span class="sxs-lookup"><span data-stu-id="6f740-220">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="6f740-221">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="6f740-221">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="6f740-222">Überträgt ein Paket auf den Server und veröffentlicht es.</span><span class="sxs-lookup"><span data-stu-id="6f740-222">Pushes a package to the server and publishes it.</span></span>

## <a name="examples"></a><span data-ttu-id="6f740-223">Beispiele</span><span class="sxs-lookup"><span data-stu-id="6f740-223">Examples</span></span>

<span data-ttu-id="6f740-224">Initialisieren einer .NET Core-Konsolenanwendung, die kompiliert und ausgeführt werden kann:</span><span class="sxs-lookup"><span data-stu-id="6f740-224">Initialize a sample .NET Core console application that can be compiled and run:</span></span>

`dotnet new console`

<span data-ttu-id="6f740-225">Wiederherstellen von Abhängigkeiten für eine bestimmte Anwendung:</span><span class="sxs-lookup"><span data-stu-id="6f740-225">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="6f740-226">Erstellen eines Projekts und seiner Abhängigkeiten in einem vorgegebenen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="6f740-226">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="6f740-227">Führen Sie eine Framework-abhängige Anwendung mit dem Namen `myapp.dll` aus:</span><span class="sxs-lookup"><span data-stu-id="6f740-227">Run a framework-dependent app named `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="6f740-228">Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="6f740-228">Environment variables</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="6f740-229">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="6f740-229">.NET Core 2.x</span></span>](#tab/netcore2x)

`DOTNET_PACKAGES`

<span data-ttu-id="6f740-230">Der Cache des primären Pakets.</span><span class="sxs-lookup"><span data-stu-id="6f740-230">The primary package cache.</span></span> <span data-ttu-id="6f740-231">Wenn er nicht festgelegt wird, wird standardmäßig `$HOME/.nuget/packages` unter Unix oder `%HOME%\NuGet\Packages` unter Windows verwendet.</span><span class="sxs-lookup"><span data-stu-id="6f740-231">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="6f740-232">Gibt den Speicherort des Wartungsindex an, der vom freigegebenen Host verwendet wird, wenn die Laufzeit geladen wird.</span><span class="sxs-lookup"><span data-stu-id="6f740-232">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="6f740-233">Gibt an, ob Daten zur Nutzung von .NET Core-Tools gesammelt und an Microsoft gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="6f740-233">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="6f740-234">Legen Sie sie auf `true` fest, um die Telemetriefunktion zu deaktivieren (Werte `true`, `1` oder `yes` werden akzeptiert); legen Sie sie andernfalls auf `false` fest, um die Telemetriefunktionen zu aktivieren (Werte `false`, `0` oder `no` werden akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="6f740-234">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted); otherwise, set to `false` to opt-in to the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="6f740-235">Wenn sie nicht festgelegt wird, ist der Standardwert `false`, und die Telemetriefunktion ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="6f740-235">If not set, the defaults is `false`, and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="6f740-236">Gibt an, ob die .NET Core-Runtime, das freigegebene Framework oder das SDK vom globalen Speicherort aus aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="6f740-236">Specifies whether .NET Core runtime, shared framework or SDK are resolved from the global location.</span></span> <span data-ttu-id="6f740-237">Wenn nicht, ist der Standardwert `true`.</span><span class="sxs-lookup"><span data-stu-id="6f740-237">If not set, it defaults to `true`.</span></span> <span data-ttu-id="6f740-238">Wenn der Wert auf `false` festgelegt wird, wird nicht vom globalen Speicherort aus aufgelöst und es gibt isolierte .NET Core-Installationen (die Werte `0` oder `false` werden akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="6f740-238">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="6f740-239">Weitere Informationen zu Lookup mit mehreren Ebenen finden Sie unter [Multi-level SharedFX lookup (SharedFX-Lookup mit mehreren Ebenen)](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span><span class="sxs-lookup"><span data-stu-id="6f740-239">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="6f740-240">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="6f740-240">.NET Core 1.x</span></span>](#tab/netcore1x)

`DOTNET_PACKAGES`

<span data-ttu-id="6f740-241">Der Cache des primären Pakets.</span><span class="sxs-lookup"><span data-stu-id="6f740-241">The primary package cache.</span></span> <span data-ttu-id="6f740-242">Wenn er nicht festgelegt wird, wird standardmäßig `$HOME/.nuget/packages` unter Unix oder `%HOME%\NuGet\Packages` unter Windows verwendet.</span><span class="sxs-lookup"><span data-stu-id="6f740-242">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="6f740-243">Gibt den Speicherort des Wartungsindex an, der vom freigegebenen Host verwendet wird, wenn die Laufzeit geladen wird.</span><span class="sxs-lookup"><span data-stu-id="6f740-243">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="6f740-244">Gibt an, ob Daten zur Nutzung von .NET Core-Tools gesammelt und an Microsoft gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="6f740-244">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="6f740-245">Legen Sie sie auf `true` fest, um die Telemetriefunktion zu deaktivieren (Werte `true`, `1` oder `yes` werden akzeptiert); legen Sie sie andernfalls auf `false` fest, um die Telemetriefunktionen zu aktivieren (Werte `false`, `0` oder `no` werden akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="6f740-245">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted); otherwise, set to `false` to opt-in to the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="6f740-246">Wenn sie nicht festgelegt wird, ist der Standardwert `false`, und die Telemetriefunktion ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="6f740-246">If not set, the defaults is `false`, and the telemetry feature is active.</span></span>

---
