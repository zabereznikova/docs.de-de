---
title: dotnet-Befehl – .NET Core-CLI
description: Informationen zum dotnet-Befehl (generischer Treiber für die .NET Core CLI-Tools) und dessen Verwendung.
author: mairaw
ms.author: mairaw
ms.date: 06/04/2018
ms.openlocfilehash: 788dc746705f9328683019ab3ad9836204a1ea63
ms.sourcegitcommit: fc70fcb9c789b6a4aefcdace46f3643fd076450f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2018
ms.locfileid: "34805658"
---
# <a name="dotnet-command"></a><span data-ttu-id="172ba-103">dotnet-Befehl</span><span class="sxs-lookup"><span data-stu-id="172ba-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="172ba-104">name</span><span class="sxs-lookup"><span data-stu-id="172ba-104">Name</span></span>

<span data-ttu-id="172ba-105">`dotnet`: Allgemeiner Treiber für das Ausführen der Befehlszeilenbefehle.</span><span class="sxs-lookup"><span data-stu-id="172ba-105">`dotnet` - General driver for running the command-line commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="172ba-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="172ba-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="172ba-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="172ba-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [--list-runtimes] [--list-sdks] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="172ba-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="172ba-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="172ba-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="172ba-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet [command] [arguments] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [-v|--verbosity] [--version]
```
---

## <a name="description"></a><span data-ttu-id="172ba-110">description</span><span class="sxs-lookup"><span data-stu-id="172ba-110">Description</span></span>

<span data-ttu-id="172ba-111">`dotnet` ist ein generischer Treiber für die Befehlszeilenschnittstellen-Toolkette (CLI).</span><span class="sxs-lookup"><span data-stu-id="172ba-111">`dotnet` is a generic driver for the Command Line Interface (CLI) toolchain.</span></span> <span data-ttu-id="172ba-112">Bietet bei eigenständigem Aufruf kurze Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="172ba-112">Invoked on its own, it provides brief usage instructions.</span></span>

<span data-ttu-id="172ba-113">Jede bestimmte Funktion ist als Befehl implementiert.</span><span class="sxs-lookup"><span data-stu-id="172ba-113">Each specific feature is implemented as a command.</span></span> <span data-ttu-id="172ba-114">Um die Funktion zu verwenden, wird der Befehl nach `dotnet` angegeben, wie z.B. [`dotnet build`](dotnet-build.md).</span><span class="sxs-lookup"><span data-stu-id="172ba-114">To use the feature, the command is specified after `dotnet`, such as [`dotnet build`](dotnet-build.md).</span></span> <span data-ttu-id="172ba-115">Alle Argumente nach dem Befehl sind die eigenen Argumente.</span><span class="sxs-lookup"><span data-stu-id="172ba-115">All of the arguments following the command are its own arguments.</span></span>

<span data-ttu-id="172ba-116">Nur bei [Framework-abhängigen Apps](../deploying/index.md) wird `dotnet` als eigenständiger Befehl verwendet.</span><span class="sxs-lookup"><span data-stu-id="172ba-116">The only time `dotnet` is used as a command on its own is to run [framework-dependent apps](../deploying/index.md).</span></span> <span data-ttu-id="172ba-117">Geben Sie eine Anwendungs-DLL nach dem Verb `dotnet` an, um die Anwendung auszuführen (zum Beispiel `dotnet myapp.dll`).</span><span class="sxs-lookup"><span data-stu-id="172ba-117">Specify an application DLL after the `dotnet` verb to execute the application (for example, `dotnet myapp.dll`).</span></span>

## <a name="options"></a><span data-ttu-id="172ba-118">Optionen</span><span class="sxs-lookup"><span data-stu-id="172ba-118">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="172ba-119">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="172ba-119">.NET Core 2.1</span></span>](#tab/netcore21)

`--additional-deps <PATH>`

<span data-ttu-id="172ba-120">Pfad zur zusätzlichen *deps.json*-Datei.</span><span class="sxs-lookup"><span data-stu-id="172ba-120">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="172ba-121">Pfad, der die Suchrichtlinie und die zu suchenden Assemblys enthält.</span><span class="sxs-lookup"><span data-stu-id="172ba-121">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="172ba-122">Ermöglicht die diagnostische Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="172ba-122">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="172ba-123">Version der installierten .NET Core-Laufzeit, die für die Ausführung der Anwendung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="172ba-123">Version of the installed .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="172ba-124">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="172ba-124">Prints out a short help for the command.</span></span> <span data-ttu-id="172ba-125">Bei Verwendung mit `dotnet` wird auch eine Liste der verfügbaren Befehle gedruckt.</span><span class="sxs-lookup"><span data-stu-id="172ba-125">If using with `dotnet`, it also prints a list of the available commands.</span></span>

`--info`

<span data-ttu-id="172ba-126">Druckt nähere Informationen zu den CLI-Tools und der Umgebung, z.B. das aktuelle Betriebssystem, den Commit-SHA für die Version und weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="172ba-126">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`--list-runtimes`

<span data-ttu-id="172ba-127">Zeigt die installierten .NET Core-Runtimes an.</span><span class="sxs-lookup"><span data-stu-id="172ba-127">Displays the installed .NET Core runtimes.</span></span>

`--list-sdks`

<span data-ttu-id="172ba-128">Zeigt die installierten .NET Core-SDKs an.</span><span class="sxs-lookup"><span data-stu-id="172ba-128">Displays the installed .NET Core SDKs.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="172ba-129">Führt ein Rollforward auf ein geteiltes Framework ohne Kandidaten durch.</span><span class="sxs-lookup"><span data-stu-id="172ba-129">Rolls forward on no candidate shared framework.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="172ba-130">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="172ba-130">Sets the verbosity level of the command.</span></span> <span data-ttu-id="172ba-131">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="172ba-131">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="172ba-132">Nicht in jedem Befehl unterstützt. Auf der Seite der einzelnen Befehle finden Sie heraus, ob diese Option verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="172ba-132">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="172ba-133">Druckt die Version des verwendeten .NET Core-SDK aus.</span><span class="sxs-lookup"><span data-stu-id="172ba-133">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="172ba-134">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="172ba-134">.NET Core 2.0</span></span>](#tab/netcore20)

`--additional-deps <PATH>`

<span data-ttu-id="172ba-135">Pfad zur zusätzlichen *deps.json*-Datei.</span><span class="sxs-lookup"><span data-stu-id="172ba-135">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="172ba-136">Pfad, der die Suchrichtlinie und die zu suchenden Assemblys enthält.</span><span class="sxs-lookup"><span data-stu-id="172ba-136">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="172ba-137">Ermöglicht die diagnostische Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="172ba-137">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="172ba-138">Version der installierten .NET Core-Laufzeit, die für die Ausführung der Anwendung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="172ba-138">Version of the installed .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="172ba-139">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="172ba-139">Prints out a short help for the command.</span></span> <span data-ttu-id="172ba-140">Bei Verwendung mit `dotnet` wird auch eine Liste der verfügbaren Befehle gedruckt.</span><span class="sxs-lookup"><span data-stu-id="172ba-140">If using with `dotnet`, it also prints a list of the available commands.</span></span>

`--info`

<span data-ttu-id="172ba-141">Druckt nähere Informationen zu den CLI-Tools und der Umgebung, z.B. das aktuelle Betriebssystem, den Commit-SHA für die Version und weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="172ba-141">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="172ba-142">Führt ein Rollforward auf ein geteiltes Framework ohne Kandidaten durch.</span><span class="sxs-lookup"><span data-stu-id="172ba-142">Rolls forward on no candidate shared framework.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="172ba-143">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="172ba-143">Sets the verbosity level of the command.</span></span> <span data-ttu-id="172ba-144">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="172ba-144">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="172ba-145">Nicht in jedem Befehl unterstützt. Auf der Seite der einzelnen Befehle finden Sie heraus, ob diese Option verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="172ba-145">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="172ba-146">Druckt die Version des verwendeten .NET Core-SDK aus.</span><span class="sxs-lookup"><span data-stu-id="172ba-146">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="172ba-147">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="172ba-147">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="172ba-148">Pfad, der die Suchrichtlinie und die zu suchenden Assemblys enthält.</span><span class="sxs-lookup"><span data-stu-id="172ba-148">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="172ba-149">Ermöglicht die diagnostische Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="172ba-149">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="172ba-150">Version der installierten .NET Core-Laufzeit, die für die Ausführung der Anwendung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="172ba-150">Version of the installed .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="172ba-151">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="172ba-151">Prints out a short help for the command.</span></span> <span data-ttu-id="172ba-152">Bei Verwendung mit `dotnet` wird auch eine Liste der verfügbaren Befehle gedruckt.</span><span class="sxs-lookup"><span data-stu-id="172ba-152">If using with `dotnet`, it also prints a list of the available commands.</span></span>

`--info`

<span data-ttu-id="172ba-153">Druckt nähere Informationen zu den CLI-Tools und der Umgebung, z.B. das aktuelle Betriebssystem, den Commit-SHA für die Version und weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="172ba-153">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="172ba-154">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="172ba-154">Sets the verbosity level of the command.</span></span> <span data-ttu-id="172ba-155">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="172ba-155">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="172ba-156">Nicht in jedem Befehl unterstützt. Auf der Seite der einzelnen Befehle finden Sie heraus, ob diese Option verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="172ba-156">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="172ba-157">Druckt die Version des verwendeten .NET Core-SDK aus.</span><span class="sxs-lookup"><span data-stu-id="172ba-157">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="172ba-158">dotnet-Befehle</span><span class="sxs-lookup"><span data-stu-id="172ba-158">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="172ba-159">Allgemein</span><span class="sxs-lookup"><span data-stu-id="172ba-159">General</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="172ba-160">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="172ba-160">.NET Core 2.1</span></span>](#tab/netcore21)

| <span data-ttu-id="172ba-161">Befehl</span><span class="sxs-lookup"><span data-stu-id="172ba-161">Command</span></span>                                       | <span data-ttu-id="172ba-162">Funktion</span><span class="sxs-lookup"><span data-stu-id="172ba-162">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="172ba-163">dotnet build</span><span class="sxs-lookup"><span data-stu-id="172ba-163">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="172ba-164">Erstellt eine .NET Core-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="172ba-164">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="172ba-165">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="172ba-165">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="172ba-166">Interagiert mit Servern, die von einem Build gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="172ba-166">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="172ba-167">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="172ba-167">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="172ba-168">Bereinigen von Buildausgaben.</span><span class="sxs-lookup"><span data-stu-id="172ba-168">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="172ba-169">dotnet help</span><span class="sxs-lookup"><span data-stu-id="172ba-169">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="172ba-170">Zeigt eine ausführlichere Onlinedokumentation für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="172ba-170">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="172ba-171">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="172ba-171">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="172ba-172">Migriert ein gültiges Preview 2-Projekt in ein .NET Core SDK 1.0-Projekt.</span><span class="sxs-lookup"><span data-stu-id="172ba-172">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="172ba-173">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="172ba-173">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="172ba-174">Ermöglicht den Zugriff auf die MSBuild-Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="172ba-174">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="172ba-175">dotnet new</span><span class="sxs-lookup"><span data-stu-id="172ba-175">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="172ba-176">Initialisiert ein C#- oder F#-Projekt für eine bestimmte Vorlage.</span><span class="sxs-lookup"><span data-stu-id="172ba-176">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="172ba-177">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="172ba-177">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="172ba-178">Erstellt ein NuGet-Paket aus Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="172ba-178">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="172ba-179">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="172ba-179">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="172ba-180">Veröffentlicht eine .NET Framework-abhängige oder eigenständige Anwendung.</span><span class="sxs-lookup"><span data-stu-id="172ba-180">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="172ba-181">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="172ba-181">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="172ba-182">Stellt die Abhängigkeiten für eine bestimmte Anwendung wieder her.</span><span class="sxs-lookup"><span data-stu-id="172ba-182">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="172ba-183">dotnet run</span><span class="sxs-lookup"><span data-stu-id="172ba-183">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="172ba-184">Führt die Anwendung aus der Quelle aus.</span><span class="sxs-lookup"><span data-stu-id="172ba-184">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="172ba-185">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="172ba-185">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="172ba-186">Optionen zum Hinzufügen, Entfernen und Listen von Projekten in einer Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="172ba-186">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="172ba-187">dotnet store</span><span class="sxs-lookup"><span data-stu-id="172ba-187">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="172ba-188">Speichert Assemblys im Laufzeitpaketspeicher.</span><span class="sxs-lookup"><span data-stu-id="172ba-188">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="172ba-189">dotnet test</span><span class="sxs-lookup"><span data-stu-id="172ba-189">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="172ba-190">Führt Tests mit einem Test Runner aus.</span><span class="sxs-lookup"><span data-stu-id="172ba-190">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="172ba-191">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="172ba-191">.NET Core 2.0</span></span>](#tab/netcore20)

| <span data-ttu-id="172ba-192">Befehl</span><span class="sxs-lookup"><span data-stu-id="172ba-192">Command</span></span>                             | <span data-ttu-id="172ba-193">Funktion</span><span class="sxs-lookup"><span data-stu-id="172ba-193">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="172ba-194">dotnet build</span><span class="sxs-lookup"><span data-stu-id="172ba-194">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="172ba-195">Erstellt eine .NET Core-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="172ba-195">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="172ba-196">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="172ba-196">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="172ba-197">Bereinigen von Buildausgaben.</span><span class="sxs-lookup"><span data-stu-id="172ba-197">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="172ba-198">dotnet help</span><span class="sxs-lookup"><span data-stu-id="172ba-198">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="172ba-199">Zeigt eine ausführlichere Onlinedokumentation für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="172ba-199">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="172ba-200">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="172ba-200">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="172ba-201">Migriert ein gültiges Preview 2-Projekt in ein .NET Core SDK 1.0-Projekt.</span><span class="sxs-lookup"><span data-stu-id="172ba-201">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="172ba-202">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="172ba-202">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="172ba-203">Ermöglicht den Zugriff auf die MSBuild-Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="172ba-203">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="172ba-204">dotnet new</span><span class="sxs-lookup"><span data-stu-id="172ba-204">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="172ba-205">Initialisiert ein C#- oder F#-Projekt für eine bestimmte Vorlage.</span><span class="sxs-lookup"><span data-stu-id="172ba-205">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="172ba-206">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="172ba-206">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="172ba-207">Erstellt ein NuGet-Paket aus Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="172ba-207">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="172ba-208">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="172ba-208">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="172ba-209">Veröffentlicht eine .NET Framework-abhängige oder eigenständige Anwendung.</span><span class="sxs-lookup"><span data-stu-id="172ba-209">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="172ba-210">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="172ba-210">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="172ba-211">Stellt die Abhängigkeiten für eine bestimmte Anwendung wieder her.</span><span class="sxs-lookup"><span data-stu-id="172ba-211">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="172ba-212">dotnet run</span><span class="sxs-lookup"><span data-stu-id="172ba-212">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="172ba-213">Führt die Anwendung aus der Quelle aus.</span><span class="sxs-lookup"><span data-stu-id="172ba-213">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="172ba-214">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="172ba-214">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="172ba-215">Optionen zum Hinzufügen, Entfernen und Listen von Projekten in einer Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="172ba-215">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="172ba-216">dotnet store</span><span class="sxs-lookup"><span data-stu-id="172ba-216">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="172ba-217">Speichert Assemblys im Laufzeitpaketspeicher.</span><span class="sxs-lookup"><span data-stu-id="172ba-217">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="172ba-218">dotnet test</span><span class="sxs-lookup"><span data-stu-id="172ba-218">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="172ba-219">Führt Tests mit einem Test Runner aus.</span><span class="sxs-lookup"><span data-stu-id="172ba-219">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="172ba-220">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="172ba-220">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="172ba-221">Befehl</span><span class="sxs-lookup"><span data-stu-id="172ba-221">Command</span></span>                             | <span data-ttu-id="172ba-222">Funktion</span><span class="sxs-lookup"><span data-stu-id="172ba-222">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="172ba-223">dotnet build</span><span class="sxs-lookup"><span data-stu-id="172ba-223">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="172ba-224">Erstellt eine .NET Core-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="172ba-224">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="172ba-225">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="172ba-225">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="172ba-226">Bereinigen von Buildausgaben.</span><span class="sxs-lookup"><span data-stu-id="172ba-226">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="172ba-227">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="172ba-227">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="172ba-228">Migriert ein gültiges Preview 2-Projekt in ein .NET Core SDK 1.0-Projekt.</span><span class="sxs-lookup"><span data-stu-id="172ba-228">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="172ba-229">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="172ba-229">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="172ba-230">Ermöglicht den Zugriff auf die MSBuild-Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="172ba-230">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="172ba-231">dotnet new</span><span class="sxs-lookup"><span data-stu-id="172ba-231">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="172ba-232">Initialisiert ein C#- oder F#-Projekt für eine bestimmte Vorlage.</span><span class="sxs-lookup"><span data-stu-id="172ba-232">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="172ba-233">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="172ba-233">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="172ba-234">Erstellt ein NuGet-Paket aus Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="172ba-234">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="172ba-235">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="172ba-235">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="172ba-236">Veröffentlicht eine .NET Framework-abhängige oder eigenständige Anwendung.</span><span class="sxs-lookup"><span data-stu-id="172ba-236">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="172ba-237">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="172ba-237">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="172ba-238">Stellt die Abhängigkeiten für eine bestimmte Anwendung wieder her.</span><span class="sxs-lookup"><span data-stu-id="172ba-238">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="172ba-239">dotnet run</span><span class="sxs-lookup"><span data-stu-id="172ba-239">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="172ba-240">Führt die Anwendung aus der Quelle aus.</span><span class="sxs-lookup"><span data-stu-id="172ba-240">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="172ba-241">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="172ba-241">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="172ba-242">Optionen zum Hinzufügen, Entfernen und Listen von Projekten in einer Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="172ba-242">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="172ba-243">dotnet test</span><span class="sxs-lookup"><span data-stu-id="172ba-243">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="172ba-244">Führt Tests mit einem Test Runner aus.</span><span class="sxs-lookup"><span data-stu-id="172ba-244">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="172ba-245">Projektverweise</span><span class="sxs-lookup"><span data-stu-id="172ba-245">Project references</span></span>

<span data-ttu-id="172ba-246">Befehl</span><span class="sxs-lookup"><span data-stu-id="172ba-246">Command</span></span> | <span data-ttu-id="172ba-247">Funktion</span><span class="sxs-lookup"><span data-stu-id="172ba-247">Function</span></span>
--- | ---
[<span data-ttu-id="172ba-248">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="172ba-248">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="172ba-249">Fügt einen Projektverweis hinzu.</span><span class="sxs-lookup"><span data-stu-id="172ba-249">Adds a project reference.</span></span>
[<span data-ttu-id="172ba-250">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="172ba-250">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="172ba-251">Listet Projektverweise auf.</span><span class="sxs-lookup"><span data-stu-id="172ba-251">Lists project references.</span></span>
[<span data-ttu-id="172ba-252">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="172ba-252">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="172ba-253">Entfernt einen Projektverweis.</span><span class="sxs-lookup"><span data-stu-id="172ba-253">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="172ba-254">NuGet-Pakete</span><span class="sxs-lookup"><span data-stu-id="172ba-254">NuGet packages</span></span>

<span data-ttu-id="172ba-255">Befehl</span><span class="sxs-lookup"><span data-stu-id="172ba-255">Command</span></span> | <span data-ttu-id="172ba-256">Funktion</span><span class="sxs-lookup"><span data-stu-id="172ba-256">Function</span></span>
--- | ---
[<span data-ttu-id="172ba-257">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="172ba-257">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="172ba-258">Fügt ein NuGet-Paket hinzu.</span><span class="sxs-lookup"><span data-stu-id="172ba-258">Adds a NuGet package.</span></span>
[<span data-ttu-id="172ba-259">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="172ba-259">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="172ba-260">Entfernt ein NuGet-Paket.</span><span class="sxs-lookup"><span data-stu-id="172ba-260">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="172ba-261">NuGet-Befehle</span><span class="sxs-lookup"><span data-stu-id="172ba-261">NuGet commands</span></span>

<span data-ttu-id="172ba-262">Befehl</span><span class="sxs-lookup"><span data-stu-id="172ba-262">Command</span></span> | <span data-ttu-id="172ba-263">Funktion</span><span class="sxs-lookup"><span data-stu-id="172ba-263">Function</span></span>
--- | ---
[<span data-ttu-id="172ba-264">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="172ba-264">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="172ba-265">Löscht ein Paket vom Server oder hebt dessen Auflistung auf.</span><span class="sxs-lookup"><span data-stu-id="172ba-265">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="172ba-266">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="172ba-266">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="172ba-267">Löscht lokale NuGet-Ressourcen, z.B. den http-Anforderungscache, den temporären Cache oder den Ordner mit globalen Paketen auf dem Computer, oder listet diese Ressourcen auf.</span><span class="sxs-lookup"><span data-stu-id="172ba-267">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="172ba-268">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="172ba-268">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="172ba-269">Überträgt ein Paket auf den Server und veröffentlicht es.</span><span class="sxs-lookup"><span data-stu-id="172ba-269">Pushes a package to the server and publishes it.</span></span>

### <a name="global-tools-commands"></a><span data-ttu-id="172ba-270">Befehle für globale Tools</span><span class="sxs-lookup"><span data-stu-id="172ba-270">Global Tools commands</span></span>

<span data-ttu-id="172ba-271">[Globale .NET Core-Tools](global-tools.md) sind beginnend mit .NET Core SDK 2.1.300 verfügbar:</span><span class="sxs-lookup"><span data-stu-id="172ba-271">[.NET Core Global Tools](global-tools.md) are available starting with .NET Core SDK 2.1.300:</span></span>

<span data-ttu-id="172ba-272">Befehl</span><span class="sxs-lookup"><span data-stu-id="172ba-272">Command</span></span> | <span data-ttu-id="172ba-273">Funktion</span><span class="sxs-lookup"><span data-stu-id="172ba-273">Function</span></span>
--- | ---
[<span data-ttu-id="172ba-274">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="172ba-274">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="172ba-275">Installiert ein Global Tool auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="172ba-275">Installs a Global Tool on your machine.</span></span>
[<span data-ttu-id="172ba-276">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="172ba-276">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="172ba-277">Listet alle globalen Tools auf, die derzeit im Standardverzeichnis oder unter dem angegebenen Pfad auf Ihrem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="172ba-277">Lists all Global Tools currently installed in the default directory on your machine or in the specified path.</span></span>
[<span data-ttu-id="172ba-278">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="172ba-278">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="172ba-279">Deinstalliert ein Global-Tool von Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="172ba-279">Uninstalls a Global Tool from your machine.</span></span>
[<span data-ttu-id="172ba-280">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="172ba-280">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="172ba-281">Aktualisiert ein Global Tool auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="172ba-281">Updates a Global Tool on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="172ba-282">Zusätzliche Tools</span><span class="sxs-lookup"><span data-stu-id="172ba-282">Additional tools</span></span>

<span data-ttu-id="172ba-283">Beginnend mit .NET Core SDK 2.1.300 steht eine Reihe von Tools, die nur auf Projektbasis unter Verwendung von `DotnetCliToolReference` verfügbar waren, jetzt als Teil des .NET Core SDK zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="172ba-283">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="172ba-284">Zu diesen Tools gehören:</span><span class="sxs-lookup"><span data-stu-id="172ba-284">These tools include:</span></span>

| <span data-ttu-id="172ba-285">Tool</span><span class="sxs-lookup"><span data-stu-id="172ba-285">Tool</span></span>                                              | <span data-ttu-id="172ba-286">Funktion</span><span class="sxs-lookup"><span data-stu-id="172ba-286">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="172ba-287">dev-certs</span><span class="sxs-lookup"><span data-stu-id="172ba-287">dev-certs</span></span>                                         | <span data-ttu-id="172ba-288">Erstellt und verwaltet Entwicklungszertifikate.</span><span class="sxs-lookup"><span data-stu-id="172ba-288">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="172ba-289">ef</span><span class="sxs-lookup"><span data-stu-id="172ba-289">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="172ba-290">Entity Framework Core-Befehlszeilentools.</span><span class="sxs-lookup"><span data-stu-id="172ba-290">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="172ba-291">sql-cache</span><span class="sxs-lookup"><span data-stu-id="172ba-291">sql-cache</span></span>                                         | <span data-ttu-id="172ba-292">SQL Server-Cache-Befehlszeilentools.</span><span class="sxs-lookup"><span data-stu-id="172ba-292">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="172ba-293">user-secrets</span><span class="sxs-lookup"><span data-stu-id="172ba-293">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="172ba-294">Verwaltet die Entwicklung von Benutzergeheimnissen.</span><span class="sxs-lookup"><span data-stu-id="172ba-294">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="172ba-295">watch</span><span class="sxs-lookup"><span data-stu-id="172ba-295">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="172ba-296">Startet einen Datei-Watcher, der einen Befehl ausführt, wenn sich Dateien ändern.</span><span class="sxs-lookup"><span data-stu-id="172ba-296">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="172ba-297">Weitere Informationen zu den einzelnen Tools finden Sie unter `dotnet <tool-name> --help`.</span><span class="sxs-lookup"><span data-stu-id="172ba-297">For more information about each tool, execute `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="172ba-298">Beispiele</span><span class="sxs-lookup"><span data-stu-id="172ba-298">Examples</span></span>

<span data-ttu-id="172ba-299">Erstellt eine neue .NET Core-Konsolenanwendung:</span><span class="sxs-lookup"><span data-stu-id="172ba-299">Creates a new .NET Core console application:</span></span>

`dotnet new console`

<span data-ttu-id="172ba-300">Wiederherstellen von Abhängigkeiten für eine bestimmte Anwendung:</span><span class="sxs-lookup"><span data-stu-id="172ba-300">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="172ba-301">Erstellen eines Projekts und seiner Abhängigkeiten in einem vorgegebenen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="172ba-301">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="172ba-302">Führen Sie eine Framework-abhängige Anwendung mit dem Namen `myapp.dll` aus:</span><span class="sxs-lookup"><span data-stu-id="172ba-302">Run a framework-dependent app named `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="172ba-303">Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="172ba-303">Environment variables</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="172ba-304">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="172ba-304">.NET Core 2.1</span></span>](#tab/netcore21)

`DOTNET_PACKAGES`

<span data-ttu-id="172ba-305">Der Cache des primären Pakets.</span><span class="sxs-lookup"><span data-stu-id="172ba-305">The primary package cache.</span></span> <span data-ttu-id="172ba-306">Wenn er nicht festgelegt wird, wird standardmäßig `$HOME/.nuget/packages` unter Unix oder `%HOME%\NuGet\Packages` unter Windows verwendet.</span><span class="sxs-lookup"><span data-stu-id="172ba-306">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="172ba-307">Gibt den Speicherort des Wartungsindex an, der vom freigegebenen Host verwendet wird, wenn die Laufzeit geladen wird.</span><span class="sxs-lookup"><span data-stu-id="172ba-307">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="172ba-308">Gibt an, ob Daten zur Nutzung von .NET Core-Tools gesammelt und an Microsoft gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="172ba-308">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="172ba-309">Legen Sie `true` fest, um die Telemetriefunktion zu deaktivieren (Wert `true`, `1` oder `yes` wird akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="172ba-309">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="172ba-310">Legen Sie andernfalls `false` fest, um die Telemetriefunktionen zu aktivieren (Wert `false`, `0` oder `no` wird akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="172ba-310">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="172ba-311">Ohne Festlegung ist der Standardwert `false`, und die Telemetriefunktion ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="172ba-311">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="172ba-312">Gibt an, ob die .NET Core-Runtime, das freigegebene Framework oder das SDK vom globalen Speicherort aus aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="172ba-312">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="172ba-313">Wenn nicht, ist der Standardwert `true`.</span><span class="sxs-lookup"><span data-stu-id="172ba-313">If not set, it defaults to `true`.</span></span> <span data-ttu-id="172ba-314">Wenn der Wert auf `false` festgelegt wird, wird nicht vom globalen Speicherort aus aufgelöst und es gibt isolierte .NET Core-Installationen (die Werte `0` oder `false` werden akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="172ba-314">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="172ba-315">Weitere Informationen zu Lookup mit mehreren Ebenen finden Sie unter [Multi-level SharedFX lookup (SharedFX-Lookup mit mehreren Ebenen)](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span><span class="sxs-lookup"><span data-stu-id="172ba-315">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`

<span data-ttu-id="172ba-316">Deaktiviert Rollforward der Nebenversion.</span><span class="sxs-lookup"><span data-stu-id="172ba-316">Disables minor version roll forward.</span></span> <span data-ttu-id="172ba-317">Weitere Informationen finden Sie unter [Rollforward](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="172ba-317">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="172ba-318">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="172ba-318">.NET Core 2.0</span></span>](#tab/netcore20)

`DOTNET_PACKAGES`

<span data-ttu-id="172ba-319">Der Cache des primären Pakets.</span><span class="sxs-lookup"><span data-stu-id="172ba-319">The primary package cache.</span></span> <span data-ttu-id="172ba-320">Wenn er nicht festgelegt wird, wird standardmäßig `$HOME/.nuget/packages` unter Unix oder `%HOME%\NuGet\Packages` unter Windows verwendet.</span><span class="sxs-lookup"><span data-stu-id="172ba-320">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="172ba-321">Gibt den Speicherort des Wartungsindex an, der vom freigegebenen Host verwendet wird, wenn die Laufzeit geladen wird.</span><span class="sxs-lookup"><span data-stu-id="172ba-321">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="172ba-322">Gibt an, ob Daten zur Nutzung von .NET Core-Tools gesammelt und an Microsoft gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="172ba-322">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="172ba-323">Legen Sie `true` fest, um die Telemetriefunktion zu deaktivieren (Wert `true`, `1` oder `yes` wird akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="172ba-323">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="172ba-324">Legen Sie andernfalls `false` fest, um die Telemetriefunktionen zu aktivieren (Wert `false`, `0` oder `no` wird akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="172ba-324">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="172ba-325">Ohne Festlegung ist der Standardwert `false`, und die Telemetriefunktion ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="172ba-325">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="172ba-326">Gibt an, ob die .NET Core-Runtime, das freigegebene Framework oder das SDK vom globalen Speicherort aus aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="172ba-326">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="172ba-327">Wenn nicht, ist der Standardwert `true`.</span><span class="sxs-lookup"><span data-stu-id="172ba-327">If not set, it defaults to `true`.</span></span> <span data-ttu-id="172ba-328">Wenn der Wert auf `false` festgelegt wird, wird nicht vom globalen Speicherort aus aufgelöst und es gibt isolierte .NET Core-Installationen (die Werte `0` oder `false` werden akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="172ba-328">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="172ba-329">Weitere Informationen zu Lookup mit mehreren Ebenen finden Sie unter [Multi-level SharedFX lookup (SharedFX-Lookup mit mehreren Ebenen)](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span><span class="sxs-lookup"><span data-stu-id="172ba-329">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="172ba-330">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="172ba-330">.NET Core 1.x</span></span>](#tab/netcore1x)

`DOTNET_PACKAGES`

<span data-ttu-id="172ba-331">Der Cache des primären Pakets.</span><span class="sxs-lookup"><span data-stu-id="172ba-331">The primary package cache.</span></span> <span data-ttu-id="172ba-332">Wenn er nicht festgelegt wird, wird standardmäßig `$HOME/.nuget/packages` unter Unix oder `%HOME%\NuGet\Packages` unter Windows verwendet.</span><span class="sxs-lookup"><span data-stu-id="172ba-332">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="172ba-333">Gibt den Speicherort des Wartungsindex an, der vom freigegebenen Host verwendet wird, wenn die Laufzeit geladen wird.</span><span class="sxs-lookup"><span data-stu-id="172ba-333">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="172ba-334">Gibt an, ob Daten zur Nutzung von .NET Core-Tools gesammelt und an Microsoft gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="172ba-334">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="172ba-335">Legen Sie `true` fest, um die Telemetriefunktion zu deaktivieren (Wert `true`, `1` oder `yes` wird akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="172ba-335">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="172ba-336">Legen Sie andernfalls `false` fest, um die Telemetriefunktionen zu aktivieren (Wert `false`, `0` oder `no` wird akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="172ba-336">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="172ba-337">Ohne Festlegung ist der Standardwert `false`, und die Telemetriefunktion ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="172ba-337">If not set, the default is `false` and the telemetry feature is active.</span></span>

---
