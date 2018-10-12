---
title: dotnet-Befehl – .NET Core-CLI
description: Informationen zum dotnet-Befehl (generischer Treiber für die .NET Core CLI-Tools) und dessen Verwendung.
author: mairaw
ms.author: mairaw
ms.date: 06/04/2018
ms.openlocfilehash: 53e8f8bab1cbaabaa7926aa68197c18843b0b637
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/16/2018
ms.locfileid: "45615572"
---
# <a name="dotnet-command"></a><span data-ttu-id="fdc47-103">dotnet-Befehl</span><span class="sxs-lookup"><span data-stu-id="fdc47-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="fdc47-104">name</span><span class="sxs-lookup"><span data-stu-id="fdc47-104">Name</span></span>

<span data-ttu-id="fdc47-105">`dotnet`: Ein Tool für das Verwalten von .NET-Quellcode und Binärdateien.</span><span class="sxs-lookup"><span data-stu-id="fdc47-105">`dotnet` - A tool for managing .NET source code and binaries.</span></span>

## <a name="synopsis"></a><span data-ttu-id="fdc47-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="fdc47-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="fdc47-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="fdc47-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [--list-runtimes] [--list-sdks] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="fdc47-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="fdc47-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="fdc47-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="fdc47-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet [command] [arguments] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [-v|--verbosity] [--version]
```
---

## <a name="description"></a><span data-ttu-id="fdc47-110">Beschreibung </span><span class="sxs-lookup"><span data-stu-id="fdc47-110">Description</span></span>

<span data-ttu-id="fdc47-111">`dotnet` ist ein Tool für das Verwalten von .NET-Quellcode und Binärdateien.</span><span class="sxs-lookup"><span data-stu-id="fdc47-111">`dotnet` is a tool for managing .NET source code and binaries.</span></span> <span data-ttu-id="fdc47-112">Es stellt Befehle zur Verfügung, die bestimmte Aufgaben erfüllen, z.B. [`dotnet build`](dotnet-build.md) und [`dotnet run`](dotnet-run.md).</span><span class="sxs-lookup"><span data-stu-id="fdc47-112">It exposes commands that perform specific tasks, such as [`dotnet build`](dotnet-build.md) and [`dotnet run`](dotnet-run.md).</span></span> <span data-ttu-id="fdc47-113">Jeder Befehl definiert seine eigenen Argumente.</span><span class="sxs-lookup"><span data-stu-id="fdc47-113">Each command defines its own arguments.</span></span> <span data-ttu-id="fdc47-114">Geben Sie nach jedem Befehl `--help` ein, um auf eine kurze Hilfsdokumentation zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="fdc47-114">Type `--help` after each command to access brief help documentation.</span></span>

<span data-ttu-id="fdc47-115">`dotnet` kann zum Ausführen von Anwendungen verwendet werden, indem eine Anwendungs-DLL angegeben wird, z.B. `dotnet myapp.dll`.</span><span class="sxs-lookup"><span data-stu-id="fdc47-115">`dotnet` can be used to run applications, by specifying an application DLL, such as `dotnet myapp.dll`.</span></span> <span data-ttu-id="fdc47-116">Weitere Informationen über Bereitstellungsoptionen finden Sie unter [.NET Core-Anwendungsbereitstellung](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="fdc47-116">See [.NET Core application deployment](../deploying/index.md) for to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="fdc47-117">Optionen</span><span class="sxs-lookup"><span data-stu-id="fdc47-117">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="fdc47-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="fdc47-118">.NET Core 2.1</span></span>](#tab/netcore21)

`--additional-deps <PATH>`

<span data-ttu-id="fdc47-119">Pfad zur zusätzlichen *deps.json*-Datei.</span><span class="sxs-lookup"><span data-stu-id="fdc47-119">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="fdc47-120">Pfad, der die Suchrichtlinie und die zu suchenden Assemblys enthält.</span><span class="sxs-lookup"><span data-stu-id="fdc47-120">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="fdc47-121">Ermöglicht die diagnostische Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="fdc47-121">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="fdc47-122">Version der .NET Core-Runtime, die zum Ausführen der Anwendung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="fdc47-122">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="fdc47-123">Gibt Dokumentation für einen bestimmten Befehl aus, z.B. `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="fdc47-123">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="fdc47-124">`dotnet --help` gibt eine Liste der verfügbaren Befehle zurück.</span><span class="sxs-lookup"><span data-stu-id="fdc47-124">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="fdc47-125">Gibt ausführliche Informationen über eine .NET Core-Installation und die Computerumgebung aus, z.B. das aktuelle Betriebssystem und den Commit-SHA für die .NET Core-Version.</span><span class="sxs-lookup"><span data-stu-id="fdc47-125">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--list-runtimes`

<span data-ttu-id="fdc47-126">Zeigt die installierten .NET Core-Runtimes an.</span><span class="sxs-lookup"><span data-stu-id="fdc47-126">Displays the installed .NET Core runtimes.</span></span>

`--list-sdks`

<span data-ttu-id="fdc47-127">Zeigt die installierten .NET Core-SDKs an.</span><span class="sxs-lookup"><span data-stu-id="fdc47-127">Displays the installed .NET Core SDKs.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="fdc47-128">Deaktiviert Rollforward der Nebenversion, wenn `0` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="fdc47-128">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="fdc47-129">Weitere Informationen finden Sie unter [Rollforward](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="fdc47-129">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="fdc47-130">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="fdc47-130">Sets the verbosity level of the command.</span></span> <span data-ttu-id="fdc47-131">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="fdc47-131">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="fdc47-132">Nicht in jedem Befehl unterstützt. Auf der Seite der einzelnen Befehle finden Sie heraus, ob diese Option verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="fdc47-132">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="fdc47-133">Druckt die Version des verwendeten .NET Core-SDK aus.</span><span class="sxs-lookup"><span data-stu-id="fdc47-133">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="fdc47-134">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="fdc47-134">.NET Core 2.0</span></span>](#tab/netcore20)

`--additional-deps <PATH>`

<span data-ttu-id="fdc47-135">Pfad zur zusätzlichen *deps.json*-Datei.</span><span class="sxs-lookup"><span data-stu-id="fdc47-135">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="fdc47-136">Pfad, der die Suchrichtlinie und die zu suchenden Assemblys enthält.</span><span class="sxs-lookup"><span data-stu-id="fdc47-136">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="fdc47-137">Ermöglicht die diagnostische Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="fdc47-137">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="fdc47-138">Version der .NET Core-Runtime, die zum Ausführen der Anwendung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="fdc47-138">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="fdc47-139">Gibt Dokumentation für einen bestimmten Befehl aus, z.B. `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="fdc47-139">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="fdc47-140">`dotnet --help` gibt eine Liste der verfügbaren Befehle zurück.</span><span class="sxs-lookup"><span data-stu-id="fdc47-140">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="fdc47-141">Gibt ausführliche Informationen über eine .NET Core-Installation und die Computerumgebung aus, z.B. das aktuelle Betriebssystem und den Commit-SHA für die .NET Core-Version.</span><span class="sxs-lookup"><span data-stu-id="fdc47-141">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="fdc47-142">Deaktiviert Rollforward der Nebenversion, wenn `0` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="fdc47-142">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="fdc47-143">Weitere Informationen finden Sie unter [Rollforward](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="fdc47-143">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="fdc47-144">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="fdc47-144">Sets the verbosity level of the command.</span></span> <span data-ttu-id="fdc47-145">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="fdc47-145">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="fdc47-146">Nicht in jedem Befehl unterstützt. Auf der Seite der einzelnen Befehle finden Sie heraus, ob diese Option verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="fdc47-146">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="fdc47-147">Druckt die Version des verwendeten .NET Core-SDK aus.</span><span class="sxs-lookup"><span data-stu-id="fdc47-147">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="fdc47-148">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="fdc47-148">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="fdc47-149">Pfad, der die Suchrichtlinie und die zu suchenden Assemblys enthält.</span><span class="sxs-lookup"><span data-stu-id="fdc47-149">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="fdc47-150">Ermöglicht die diagnostische Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="fdc47-150">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="fdc47-151">Version der .NET Core-Runtime, die zum Ausführen der Anwendung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="fdc47-151">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="fdc47-152">Gibt Dokumentation für einen bestimmten Befehl aus, z.B. `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="fdc47-152">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="fdc47-153">`dotnet --help` gibt eine Liste der verfügbaren Befehle zurück.</span><span class="sxs-lookup"><span data-stu-id="fdc47-153">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="fdc47-154">Gibt ausführliche Informationen über eine .NET Core-Installation und die Computerumgebung aus, z.B. das aktuelle Betriebssystem und den Commit-SHA für die .NET Core-Version.</span><span class="sxs-lookup"><span data-stu-id="fdc47-154">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="fdc47-155">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="fdc47-155">Sets the verbosity level of the command.</span></span> <span data-ttu-id="fdc47-156">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="fdc47-156">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="fdc47-157">Nicht in jedem Befehl unterstützt. Auf der Seite der einzelnen Befehle finden Sie heraus, ob diese Option verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="fdc47-157">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="fdc47-158">Druckt die Version des verwendeten .NET Core-SDK aus.</span><span class="sxs-lookup"><span data-stu-id="fdc47-158">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="fdc47-159">dotnet-Befehle</span><span class="sxs-lookup"><span data-stu-id="fdc47-159">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="fdc47-160">Allgemein</span><span class="sxs-lookup"><span data-stu-id="fdc47-160">General</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="fdc47-161">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="fdc47-161">.NET Core 2.1</span></span>](#tab/netcore21)

| <span data-ttu-id="fdc47-162">Befehl</span><span class="sxs-lookup"><span data-stu-id="fdc47-162">Command</span></span>                                       | <span data-ttu-id="fdc47-163">Funktion</span><span class="sxs-lookup"><span data-stu-id="fdc47-163">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="fdc47-164">dotnet build</span><span class="sxs-lookup"><span data-stu-id="fdc47-164">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="fdc47-165">Erstellt eine .NET Core-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="fdc47-165">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="fdc47-166">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="fdc47-166">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="fdc47-167">Interagiert mit Servern, die von einem Build gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="fdc47-167">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="fdc47-168">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="fdc47-168">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="fdc47-169">Bereinigen von Buildausgaben.</span><span class="sxs-lookup"><span data-stu-id="fdc47-169">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="fdc47-170">dotnet help</span><span class="sxs-lookup"><span data-stu-id="fdc47-170">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="fdc47-171">Zeigt eine ausführlichere Onlinedokumentation für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="fdc47-171">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="fdc47-172">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="fdc47-172">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="fdc47-173">Migriert ein gültiges Preview 2-Projekt in ein .NET Core SDK 1.0-Projekt.</span><span class="sxs-lookup"><span data-stu-id="fdc47-173">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="fdc47-174">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="fdc47-174">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="fdc47-175">Ermöglicht den Zugriff auf die MSBuild-Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="fdc47-175">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="fdc47-176">dotnet new</span><span class="sxs-lookup"><span data-stu-id="fdc47-176">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="fdc47-177">Initialisiert ein C#- oder F#-Projekt für eine bestimmte Vorlage.</span><span class="sxs-lookup"><span data-stu-id="fdc47-177">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="fdc47-178">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="fdc47-178">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="fdc47-179">Erstellt ein NuGet-Paket aus Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="fdc47-179">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="fdc47-180">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="fdc47-180">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="fdc47-181">Veröffentlicht eine .NET Framework-abhängige oder eigenständige Anwendung.</span><span class="sxs-lookup"><span data-stu-id="fdc47-181">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="fdc47-182">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="fdc47-182">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="fdc47-183">Stellt die Abhängigkeiten für eine bestimmte Anwendung wieder her.</span><span class="sxs-lookup"><span data-stu-id="fdc47-183">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="fdc47-184">dotnet run</span><span class="sxs-lookup"><span data-stu-id="fdc47-184">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="fdc47-185">Führt die Anwendung aus der Quelle aus.</span><span class="sxs-lookup"><span data-stu-id="fdc47-185">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="fdc47-186">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="fdc47-186">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="fdc47-187">Optionen zum Hinzufügen, Entfernen und Listen von Projekten in einer Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="fdc47-187">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="fdc47-188">dotnet store</span><span class="sxs-lookup"><span data-stu-id="fdc47-188">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="fdc47-189">Speichert Assemblys im Laufzeitpaketspeicher.</span><span class="sxs-lookup"><span data-stu-id="fdc47-189">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="fdc47-190">dotnet test</span><span class="sxs-lookup"><span data-stu-id="fdc47-190">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="fdc47-191">Führt Tests mit einem Test Runner aus.</span><span class="sxs-lookup"><span data-stu-id="fdc47-191">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="fdc47-192">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="fdc47-192">.NET Core 2.0</span></span>](#tab/netcore20)

| <span data-ttu-id="fdc47-193">Befehl</span><span class="sxs-lookup"><span data-stu-id="fdc47-193">Command</span></span>                             | <span data-ttu-id="fdc47-194">Funktion</span><span class="sxs-lookup"><span data-stu-id="fdc47-194">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="fdc47-195">dotnet build</span><span class="sxs-lookup"><span data-stu-id="fdc47-195">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="fdc47-196">Erstellt eine .NET Core-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="fdc47-196">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="fdc47-197">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="fdc47-197">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="fdc47-198">Bereinigen von Buildausgaben.</span><span class="sxs-lookup"><span data-stu-id="fdc47-198">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="fdc47-199">dotnet help</span><span class="sxs-lookup"><span data-stu-id="fdc47-199">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="fdc47-200">Zeigt eine ausführlichere Onlinedokumentation für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="fdc47-200">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="fdc47-201">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="fdc47-201">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="fdc47-202">Migriert ein gültiges Preview 2-Projekt in ein .NET Core SDK 1.0-Projekt.</span><span class="sxs-lookup"><span data-stu-id="fdc47-202">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="fdc47-203">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="fdc47-203">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="fdc47-204">Ermöglicht den Zugriff auf die MSBuild-Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="fdc47-204">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="fdc47-205">dotnet new</span><span class="sxs-lookup"><span data-stu-id="fdc47-205">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="fdc47-206">Initialisiert ein C#- oder F#-Projekt für eine bestimmte Vorlage.</span><span class="sxs-lookup"><span data-stu-id="fdc47-206">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="fdc47-207">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="fdc47-207">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="fdc47-208">Erstellt ein NuGet-Paket aus Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="fdc47-208">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="fdc47-209">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="fdc47-209">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="fdc47-210">Veröffentlicht eine .NET Framework-abhängige oder eigenständige Anwendung.</span><span class="sxs-lookup"><span data-stu-id="fdc47-210">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="fdc47-211">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="fdc47-211">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="fdc47-212">Stellt die Abhängigkeiten für eine bestimmte Anwendung wieder her.</span><span class="sxs-lookup"><span data-stu-id="fdc47-212">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="fdc47-213">dotnet run</span><span class="sxs-lookup"><span data-stu-id="fdc47-213">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="fdc47-214">Führt die Anwendung aus der Quelle aus.</span><span class="sxs-lookup"><span data-stu-id="fdc47-214">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="fdc47-215">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="fdc47-215">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="fdc47-216">Optionen zum Hinzufügen, Entfernen und Listen von Projekten in einer Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="fdc47-216">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="fdc47-217">dotnet store</span><span class="sxs-lookup"><span data-stu-id="fdc47-217">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="fdc47-218">Speichert Assemblys im Laufzeitpaketspeicher.</span><span class="sxs-lookup"><span data-stu-id="fdc47-218">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="fdc47-219">dotnet test</span><span class="sxs-lookup"><span data-stu-id="fdc47-219">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="fdc47-220">Führt Tests mit einem Test Runner aus.</span><span class="sxs-lookup"><span data-stu-id="fdc47-220">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="fdc47-221">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="fdc47-221">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="fdc47-222">Befehl</span><span class="sxs-lookup"><span data-stu-id="fdc47-222">Command</span></span>                             | <span data-ttu-id="fdc47-223">Funktion</span><span class="sxs-lookup"><span data-stu-id="fdc47-223">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="fdc47-224">dotnet build</span><span class="sxs-lookup"><span data-stu-id="fdc47-224">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="fdc47-225">Erstellt eine .NET Core-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="fdc47-225">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="fdc47-226">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="fdc47-226">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="fdc47-227">Bereinigen von Buildausgaben.</span><span class="sxs-lookup"><span data-stu-id="fdc47-227">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="fdc47-228">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="fdc47-228">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="fdc47-229">Migriert ein gültiges Preview 2-Projekt in ein .NET Core SDK 1.0-Projekt.</span><span class="sxs-lookup"><span data-stu-id="fdc47-229">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="fdc47-230">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="fdc47-230">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="fdc47-231">Ermöglicht den Zugriff auf die MSBuild-Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="fdc47-231">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="fdc47-232">dotnet new</span><span class="sxs-lookup"><span data-stu-id="fdc47-232">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="fdc47-233">Initialisiert ein C#- oder F#-Projekt für eine bestimmte Vorlage.</span><span class="sxs-lookup"><span data-stu-id="fdc47-233">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="fdc47-234">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="fdc47-234">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="fdc47-235">Erstellt ein NuGet-Paket aus Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="fdc47-235">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="fdc47-236">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="fdc47-236">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="fdc47-237">Veröffentlicht eine .NET Framework-abhängige oder eigenständige Anwendung.</span><span class="sxs-lookup"><span data-stu-id="fdc47-237">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="fdc47-238">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="fdc47-238">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="fdc47-239">Stellt die Abhängigkeiten für eine bestimmte Anwendung wieder her.</span><span class="sxs-lookup"><span data-stu-id="fdc47-239">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="fdc47-240">dotnet run</span><span class="sxs-lookup"><span data-stu-id="fdc47-240">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="fdc47-241">Führt die Anwendung aus der Quelle aus.</span><span class="sxs-lookup"><span data-stu-id="fdc47-241">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="fdc47-242">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="fdc47-242">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="fdc47-243">Optionen zum Hinzufügen, Entfernen und Listen von Projekten in einer Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="fdc47-243">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="fdc47-244">dotnet test</span><span class="sxs-lookup"><span data-stu-id="fdc47-244">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="fdc47-245">Führt Tests mit einem Test Runner aus.</span><span class="sxs-lookup"><span data-stu-id="fdc47-245">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="fdc47-246">Projektverweise</span><span class="sxs-lookup"><span data-stu-id="fdc47-246">Project references</span></span>

<span data-ttu-id="fdc47-247">Befehl</span><span class="sxs-lookup"><span data-stu-id="fdc47-247">Command</span></span> | <span data-ttu-id="fdc47-248">Funktion</span><span class="sxs-lookup"><span data-stu-id="fdc47-248">Function</span></span>
--- | ---
[<span data-ttu-id="fdc47-249">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="fdc47-249">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="fdc47-250">Fügt einen Projektverweis hinzu.</span><span class="sxs-lookup"><span data-stu-id="fdc47-250">Adds a project reference.</span></span>
[<span data-ttu-id="fdc47-251">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="fdc47-251">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="fdc47-252">Listet Projektverweise auf.</span><span class="sxs-lookup"><span data-stu-id="fdc47-252">Lists project references.</span></span>
[<span data-ttu-id="fdc47-253">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="fdc47-253">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="fdc47-254">Entfernt einen Projektverweis.</span><span class="sxs-lookup"><span data-stu-id="fdc47-254">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="fdc47-255">NuGet-Pakete</span><span class="sxs-lookup"><span data-stu-id="fdc47-255">NuGet packages</span></span>

<span data-ttu-id="fdc47-256">Befehl</span><span class="sxs-lookup"><span data-stu-id="fdc47-256">Command</span></span> | <span data-ttu-id="fdc47-257">Funktion</span><span class="sxs-lookup"><span data-stu-id="fdc47-257">Function</span></span>
--- | ---
[<span data-ttu-id="fdc47-258">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="fdc47-258">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="fdc47-259">Fügt ein NuGet-Paket hinzu.</span><span class="sxs-lookup"><span data-stu-id="fdc47-259">Adds a NuGet package.</span></span>
[<span data-ttu-id="fdc47-260">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="fdc47-260">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="fdc47-261">Entfernt ein NuGet-Paket.</span><span class="sxs-lookup"><span data-stu-id="fdc47-261">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="fdc47-262">NuGet-Befehle</span><span class="sxs-lookup"><span data-stu-id="fdc47-262">NuGet commands</span></span>

<span data-ttu-id="fdc47-263">Befehl</span><span class="sxs-lookup"><span data-stu-id="fdc47-263">Command</span></span> | <span data-ttu-id="fdc47-264">Funktion</span><span class="sxs-lookup"><span data-stu-id="fdc47-264">Function</span></span>
--- | ---
[<span data-ttu-id="fdc47-265">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="fdc47-265">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="fdc47-266">Löscht ein Paket vom Server oder hebt dessen Auflistung auf.</span><span class="sxs-lookup"><span data-stu-id="fdc47-266">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="fdc47-267">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="fdc47-267">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="fdc47-268">Löscht lokale NuGet-Ressourcen, z.B. den http-Anforderungscache, den temporären Cache oder den Ordner mit globalen Paketen auf dem Computer, oder listet diese Ressourcen auf.</span><span class="sxs-lookup"><span data-stu-id="fdc47-268">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="fdc47-269">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="fdc47-269">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="fdc47-270">Überträgt ein Paket auf den Server und veröffentlicht es.</span><span class="sxs-lookup"><span data-stu-id="fdc47-270">Pushes a package to the server and publishes it.</span></span>

### <a name="global-tools-commands"></a><span data-ttu-id="fdc47-271">Befehle für globale Tools</span><span class="sxs-lookup"><span data-stu-id="fdc47-271">Global Tools commands</span></span>

<span data-ttu-id="fdc47-272">[Globale .NET Core-Tools](global-tools.md) sind beginnend mit .NET Core SDK 2.1.300 verfügbar:</span><span class="sxs-lookup"><span data-stu-id="fdc47-272">[.NET Core Global Tools](global-tools.md) are available starting with .NET Core SDK 2.1.300:</span></span>

<span data-ttu-id="fdc47-273">Befehl</span><span class="sxs-lookup"><span data-stu-id="fdc47-273">Command</span></span> | <span data-ttu-id="fdc47-274">Funktion</span><span class="sxs-lookup"><span data-stu-id="fdc47-274">Function</span></span>
--- | ---
[<span data-ttu-id="fdc47-275">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="fdc47-275">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="fdc47-276">Installiert ein Global Tool auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="fdc47-276">Installs a Global Tool on your machine.</span></span>
[<span data-ttu-id="fdc47-277">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="fdc47-277">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="fdc47-278">Listet alle globalen Tools auf, die derzeit im Standardverzeichnis oder unter dem angegebenen Pfad auf Ihrem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="fdc47-278">Lists all Global Tools currently installed in the default directory on your machine or in the specified path.</span></span>
[<span data-ttu-id="fdc47-279">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="fdc47-279">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="fdc47-280">Deinstalliert ein Global-Tool von Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="fdc47-280">Uninstalls a Global Tool from your machine.</span></span>
[<span data-ttu-id="fdc47-281">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="fdc47-281">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="fdc47-282">Aktualisiert ein Global Tool auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="fdc47-282">Updates a Global Tool on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="fdc47-283">Zusätzliche Tools</span><span class="sxs-lookup"><span data-stu-id="fdc47-283">Additional tools</span></span>

<span data-ttu-id="fdc47-284">Beginnend mit .NET Core SDK 2.1.300 steht eine Reihe von Tools, die nur auf Projektbasis unter Verwendung von `DotnetCliToolReference` verfügbar waren, jetzt als Teil des .NET Core SDK zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="fdc47-284">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="fdc47-285">Diese Tools werden in der folgenden Tabelle aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="fdc47-285">These tools are listed in the following table:</span></span>

| <span data-ttu-id="fdc47-286">Tool</span><span class="sxs-lookup"><span data-stu-id="fdc47-286">Tool</span></span>                                              | <span data-ttu-id="fdc47-287">Funktion</span><span class="sxs-lookup"><span data-stu-id="fdc47-287">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="fdc47-288">dev-certs</span><span class="sxs-lookup"><span data-stu-id="fdc47-288">dev-certs</span></span>                                         | <span data-ttu-id="fdc47-289">Erstellt und verwaltet Entwicklungszertifikate.</span><span class="sxs-lookup"><span data-stu-id="fdc47-289">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="fdc47-290">ef</span><span class="sxs-lookup"><span data-stu-id="fdc47-290">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="fdc47-291">Entity Framework Core-Befehlszeilentools.</span><span class="sxs-lookup"><span data-stu-id="fdc47-291">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="fdc47-292">sql-cache</span><span class="sxs-lookup"><span data-stu-id="fdc47-292">sql-cache</span></span>                                         | <span data-ttu-id="fdc47-293">SQL Server-Cache-Befehlszeilentools.</span><span class="sxs-lookup"><span data-stu-id="fdc47-293">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="fdc47-294">user-secrets</span><span class="sxs-lookup"><span data-stu-id="fdc47-294">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="fdc47-295">Verwaltet die Entwicklung von Benutzergeheimnissen.</span><span class="sxs-lookup"><span data-stu-id="fdc47-295">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="fdc47-296">watch</span><span class="sxs-lookup"><span data-stu-id="fdc47-296">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="fdc47-297">Startet einen Datei-Watcher, der einen Befehl ausführt, wenn sich Dateien ändern.</span><span class="sxs-lookup"><span data-stu-id="fdc47-297">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="fdc47-298">Geben Sie `dotnet <tool-name> --help` ein, um weitere Informationen zu den einzelnen Tools zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="fdc47-298">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="fdc47-299">Beispiele</span><span class="sxs-lookup"><span data-stu-id="fdc47-299">Examples</span></span>

<span data-ttu-id="fdc47-300">Erstellt eine neue .NET Core-Konsolenanwendung:</span><span class="sxs-lookup"><span data-stu-id="fdc47-300">Creates a new .NET Core console application:</span></span>

`dotnet new console`

<span data-ttu-id="fdc47-301">Wiederherstellen von Abhängigkeiten für eine bestimmte Anwendung:</span><span class="sxs-lookup"><span data-stu-id="fdc47-301">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="fdc47-302">Erstellen eines Projekts und seiner Abhängigkeiten in einem vorgegebenen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="fdc47-302">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="fdc47-303">Führen Sie eine Anwendungs-DLL aus, z.B. `myapp.dll`:</span><span class="sxs-lookup"><span data-stu-id="fdc47-303">Run an application DLL, such as `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="fdc47-304">Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="fdc47-304">Environment variables</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="fdc47-305">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="fdc47-305">.NET Core 2.1</span></span>](#tab/netcore21)

`DOTNET_PACKAGES`

<span data-ttu-id="fdc47-306">Der Cache des primären Pakets.</span><span class="sxs-lookup"><span data-stu-id="fdc47-306">The primary package cache.</span></span> <span data-ttu-id="fdc47-307">Wenn er nicht festgelegt wird, wird standardmäßig `$HOME/.nuget/packages` unter Unix oder `%HOME%\NuGet\Packages` unter Windows verwendet.</span><span class="sxs-lookup"><span data-stu-id="fdc47-307">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="fdc47-308">Gibt den Speicherort des Wartungsindex an, der vom freigegebenen Host verwendet wird, wenn die Laufzeit geladen wird.</span><span class="sxs-lookup"><span data-stu-id="fdc47-308">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="fdc47-309">Gibt an, ob Daten zur Nutzung von .NET Core-Tools gesammelt und an Microsoft gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="fdc47-309">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="fdc47-310">Legen Sie `true` fest, um die Telemetriefunktion zu deaktivieren (Wert `true`, `1` oder `yes` wird akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="fdc47-310">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="fdc47-311">Legen Sie andernfalls `false` fest, um die Telemetriefunktionen zu aktivieren (Wert `false`, `0` oder `no` wird akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="fdc47-311">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="fdc47-312">Ohne Festlegung ist der Standardwert `false`, und die Telemetriefunktion ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="fdc47-312">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="fdc47-313">Gibt an, ob die .NET Core-Runtime, das freigegebene Framework oder das SDK vom globalen Speicherort aus aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="fdc47-313">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="fdc47-314">Wenn nicht, ist der Standardwert `true`.</span><span class="sxs-lookup"><span data-stu-id="fdc47-314">If not set, it defaults to `true`.</span></span> <span data-ttu-id="fdc47-315">Wenn der Wert auf `false` festgelegt wird, wird nicht vom globalen Speicherort aus aufgelöst und es gibt isolierte .NET Core-Installationen (die Werte `0` oder `false` werden akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="fdc47-315">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="fdc47-316">Weitere Informationen zu Lookup mit mehreren Ebenen finden Sie unter [Multi-level SharedFX lookup (SharedFX-Lookup mit mehreren Ebenen)](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span><span class="sxs-lookup"><span data-stu-id="fdc47-316">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`

<span data-ttu-id="fdc47-317">Deaktiviert Rollforward der Nebenversion, wenn `0` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="fdc47-317">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="fdc47-318">Weitere Informationen finden Sie unter [Rollforward](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="fdc47-318">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="fdc47-319">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="fdc47-319">.NET Core 2.0</span></span>](#tab/netcore20)

`DOTNET_PACKAGES`

<span data-ttu-id="fdc47-320">Der Cache des primären Pakets.</span><span class="sxs-lookup"><span data-stu-id="fdc47-320">The primary package cache.</span></span> <span data-ttu-id="fdc47-321">Wenn er nicht festgelegt wird, wird standardmäßig `$HOME/.nuget/packages` unter Unix oder `%HOME%\NuGet\Packages` unter Windows verwendet.</span><span class="sxs-lookup"><span data-stu-id="fdc47-321">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="fdc47-322">Gibt den Speicherort des Wartungsindex an, der vom freigegebenen Host verwendet wird, wenn die Laufzeit geladen wird.</span><span class="sxs-lookup"><span data-stu-id="fdc47-322">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="fdc47-323">Gibt an, ob Daten zur Nutzung von .NET Core-Tools gesammelt und an Microsoft gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="fdc47-323">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="fdc47-324">Legen Sie `true` fest, um die Telemetriefunktion zu deaktivieren (Wert `true`, `1` oder `yes` wird akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="fdc47-324">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="fdc47-325">Legen Sie andernfalls `false` fest, um die Telemetriefunktionen zu aktivieren (Wert `false`, `0` oder `no` wird akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="fdc47-325">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="fdc47-326">Ohne Festlegung ist der Standardwert `false`, und die Telemetriefunktion ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="fdc47-326">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="fdc47-327">Gibt an, ob die .NET Core-Runtime, das freigegebene Framework oder das SDK vom globalen Speicherort aus aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="fdc47-327">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="fdc47-328">Wenn nicht, ist der Standardwert `true`.</span><span class="sxs-lookup"><span data-stu-id="fdc47-328">If not set, it defaults to `true`.</span></span> <span data-ttu-id="fdc47-329">Wenn der Wert auf `false` festgelegt wird, wird nicht vom globalen Speicherort aus aufgelöst und es gibt isolierte .NET Core-Installationen (die Werte `0` oder `false` werden akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="fdc47-329">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="fdc47-330">Weitere Informationen zu Lookup mit mehreren Ebenen finden Sie unter [Multi-level SharedFX lookup (SharedFX-Lookup mit mehreren Ebenen)](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span><span class="sxs-lookup"><span data-stu-id="fdc47-330">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="fdc47-331">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="fdc47-331">.NET Core 1.x</span></span>](#tab/netcore1x)

`DOTNET_PACKAGES`

<span data-ttu-id="fdc47-332">Der Cache des primären Pakets.</span><span class="sxs-lookup"><span data-stu-id="fdc47-332">The primary package cache.</span></span> <span data-ttu-id="fdc47-333">Wenn er nicht festgelegt wird, wird standardmäßig `$HOME/.nuget/packages` unter Unix oder `%HOME%\NuGet\Packages` unter Windows verwendet.</span><span class="sxs-lookup"><span data-stu-id="fdc47-333">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="fdc47-334">Gibt den Speicherort des Wartungsindex an, der vom freigegebenen Host verwendet wird, wenn die Laufzeit geladen wird.</span><span class="sxs-lookup"><span data-stu-id="fdc47-334">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="fdc47-335">Gibt an, ob Daten zur Nutzung von .NET Core-Tools gesammelt und an Microsoft gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="fdc47-335">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="fdc47-336">Legen Sie `true` fest, um die Telemetriefunktion zu deaktivieren (Wert `true`, `1` oder `yes` wird akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="fdc47-336">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="fdc47-337">Legen Sie andernfalls `false` fest, um die Telemetriefunktionen zu aktivieren (Wert `false`, `0` oder `no` wird akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="fdc47-337">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="fdc47-338">Ohne Festlegung ist der Standardwert `false`, und die Telemetriefunktion ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="fdc47-338">If not set, the default is `false` and the telemetry feature is active.</span></span>

---
