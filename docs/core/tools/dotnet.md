---
title: dotnet-Befehl – .NET Core-CLI
description: Informationen zum dotnet-Befehl (generischer Treiber für die .NET Core CLI-Tools) und dessen Verwendung.
author: mairaw
ms.author: mairaw
ms.date: 06/04/2018
ms.openlocfilehash: 53e8f8bab1cbaabaa7926aa68197c18843b0b637
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44079815"
---
# <a name="dotnet-command"></a><span data-ttu-id="ced7d-103">dotnet-Befehl</span><span class="sxs-lookup"><span data-stu-id="ced7d-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="ced7d-104">name</span><span class="sxs-lookup"><span data-stu-id="ced7d-104">Name</span></span>

<span data-ttu-id="ced7d-105">`dotnet`: Ein Tool für das Verwalten von .NET-Quellcode und Binärdateien.</span><span class="sxs-lookup"><span data-stu-id="ced7d-105">`dotnet` - A tool for managing .NET source code and binaries.</span></span>

## <a name="synopsis"></a><span data-ttu-id="ced7d-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="ced7d-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="ced7d-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="ced7d-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [--list-runtimes] [--list-sdks] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="ced7d-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="ced7d-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="ced7d-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="ced7d-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet [command] [arguments] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [-v|--verbosity] [--version]
```
---

## <a name="description"></a><span data-ttu-id="ced7d-110">Beschreibung </span><span class="sxs-lookup"><span data-stu-id="ced7d-110">Description</span></span>

<span data-ttu-id="ced7d-111">`dotnet` ist ein Tool für das Verwalten von .NET-Quellcode und Binärdateien.</span><span class="sxs-lookup"><span data-stu-id="ced7d-111">`dotnet` is a tool for managing .NET source code and binaries.</span></span> <span data-ttu-id="ced7d-112">Es stellt Befehle zur Verfügung, die bestimmte Aufgaben erfüllen, z.B. [`dotnet build`](dotnet-build.md) und [`dotnet run`](dotnet-run.md).</span><span class="sxs-lookup"><span data-stu-id="ced7d-112">It exposes commands that perform specific tasks, such as [`dotnet build`](dotnet-build.md) and [`dotnet run`](dotnet-run.md).</span></span> <span data-ttu-id="ced7d-113">Jeder Befehl definiert seine eigenen Argumente.</span><span class="sxs-lookup"><span data-stu-id="ced7d-113">Each command defines its own arguments.</span></span> <span data-ttu-id="ced7d-114">Geben Sie nach jedem Befehl `--help` ein, um auf eine kurze Hilfsdokumentation zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="ced7d-114">Type `--help` after each command to access brief help documentation.</span></span>

<span data-ttu-id="ced7d-115">`dotnet` kann zum Ausführen von Anwendungen verwendet werden, indem eine Anwendungs-DLL angegeben wird, z.B. `dotnet myapp.dll`.</span><span class="sxs-lookup"><span data-stu-id="ced7d-115">`dotnet` can be used to run applications, by specifying an application DLL, such as `dotnet myapp.dll`.</span></span> <span data-ttu-id="ced7d-116">Weitere Informationen über Bereitstellungsoptionen finden Sie unter [.NET Core-Anwendungsbereitstellung](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="ced7d-116">See [.NET Core application deployment](../deploying/index.md) for to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="ced7d-117">Optionen</span><span class="sxs-lookup"><span data-stu-id="ced7d-117">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="ced7d-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="ced7d-118">.NET Core 2.1</span></span>](#tab/netcore21)

`--additional-deps <PATH>`

<span data-ttu-id="ced7d-119">Pfad zur zusätzlichen *deps.json*-Datei.</span><span class="sxs-lookup"><span data-stu-id="ced7d-119">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="ced7d-120">Pfad, der die Suchrichtlinie und die zu suchenden Assemblys enthält.</span><span class="sxs-lookup"><span data-stu-id="ced7d-120">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="ced7d-121">Ermöglicht die diagnostische Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="ced7d-121">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="ced7d-122">Version der .NET Core-Runtime, die zum Ausführen der Anwendung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ced7d-122">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="ced7d-123">Gibt Dokumentation für einen bestimmten Befehl aus, z.B. `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="ced7d-123">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="ced7d-124">`dotnet --help` gibt eine Liste der verfügbaren Befehle zurück.</span><span class="sxs-lookup"><span data-stu-id="ced7d-124">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="ced7d-125">Gibt ausführliche Informationen über eine .NET Core-Installation und die Computerumgebung aus, z.B. das aktuelle Betriebssystem und den Commit-SHA für die .NET Core-Version.</span><span class="sxs-lookup"><span data-stu-id="ced7d-125">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--list-runtimes`

<span data-ttu-id="ced7d-126">Zeigt die installierten .NET Core-Runtimes an.</span><span class="sxs-lookup"><span data-stu-id="ced7d-126">Displays the installed .NET Core runtimes.</span></span>

`--list-sdks`

<span data-ttu-id="ced7d-127">Zeigt die installierten .NET Core-SDKs an.</span><span class="sxs-lookup"><span data-stu-id="ced7d-127">Displays the installed .NET Core SDKs.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="ced7d-128">Deaktiviert Rollforward der Nebenversion, wenn `0` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ced7d-128">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="ced7d-129">Weitere Informationen finden Sie unter [Rollforward](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="ced7d-129">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="ced7d-130">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="ced7d-130">Sets the verbosity level of the command.</span></span> <span data-ttu-id="ced7d-131">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="ced7d-131">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="ced7d-132">Nicht in jedem Befehl unterstützt. Auf der Seite der einzelnen Befehle finden Sie heraus, ob diese Option verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ced7d-132">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="ced7d-133">Druckt die Version des verwendeten .NET Core-SDK aus.</span><span class="sxs-lookup"><span data-stu-id="ced7d-133">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="ced7d-134">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="ced7d-134">.NET Core 2.0</span></span>](#tab/netcore20)

`--additional-deps <PATH>`

<span data-ttu-id="ced7d-135">Pfad zur zusätzlichen *deps.json*-Datei.</span><span class="sxs-lookup"><span data-stu-id="ced7d-135">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="ced7d-136">Pfad, der die Suchrichtlinie und die zu suchenden Assemblys enthält.</span><span class="sxs-lookup"><span data-stu-id="ced7d-136">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="ced7d-137">Ermöglicht die diagnostische Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="ced7d-137">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="ced7d-138">Version der .NET Core-Runtime, die zum Ausführen der Anwendung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ced7d-138">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="ced7d-139">Gibt Dokumentation für einen bestimmten Befehl aus, z.B. `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="ced7d-139">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="ced7d-140">`dotnet --help` gibt eine Liste der verfügbaren Befehle zurück.</span><span class="sxs-lookup"><span data-stu-id="ced7d-140">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="ced7d-141">Gibt ausführliche Informationen über eine .NET Core-Installation und die Computerumgebung aus, z.B. das aktuelle Betriebssystem und den Commit-SHA für die .NET Core-Version.</span><span class="sxs-lookup"><span data-stu-id="ced7d-141">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="ced7d-142">Deaktiviert Rollforward der Nebenversion, wenn `0` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ced7d-142">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="ced7d-143">Weitere Informationen finden Sie unter [Rollforward](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="ced7d-143">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="ced7d-144">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="ced7d-144">Sets the verbosity level of the command.</span></span> <span data-ttu-id="ced7d-145">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="ced7d-145">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="ced7d-146">Nicht in jedem Befehl unterstützt. Auf der Seite der einzelnen Befehle finden Sie heraus, ob diese Option verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ced7d-146">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="ced7d-147">Druckt die Version des verwendeten .NET Core-SDK aus.</span><span class="sxs-lookup"><span data-stu-id="ced7d-147">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="ced7d-148">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="ced7d-148">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="ced7d-149">Pfad, der die Suchrichtlinie und die zu suchenden Assemblys enthält.</span><span class="sxs-lookup"><span data-stu-id="ced7d-149">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="ced7d-150">Ermöglicht die diagnostische Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="ced7d-150">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="ced7d-151">Version der .NET Core-Runtime, die zum Ausführen der Anwendung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ced7d-151">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="ced7d-152">Gibt Dokumentation für einen bestimmten Befehl aus, z.B. `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="ced7d-152">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="ced7d-153">`dotnet --help` gibt eine Liste der verfügbaren Befehle zurück.</span><span class="sxs-lookup"><span data-stu-id="ced7d-153">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="ced7d-154">Gibt ausführliche Informationen über eine .NET Core-Installation und die Computerumgebung aus, z.B. das aktuelle Betriebssystem und den Commit-SHA für die .NET Core-Version.</span><span class="sxs-lookup"><span data-stu-id="ced7d-154">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="ced7d-155">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="ced7d-155">Sets the verbosity level of the command.</span></span> <span data-ttu-id="ced7d-156">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="ced7d-156">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="ced7d-157">Nicht in jedem Befehl unterstützt. Auf der Seite der einzelnen Befehle finden Sie heraus, ob diese Option verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ced7d-157">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="ced7d-158">Druckt die Version des verwendeten .NET Core-SDK aus.</span><span class="sxs-lookup"><span data-stu-id="ced7d-158">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="ced7d-159">dotnet-Befehle</span><span class="sxs-lookup"><span data-stu-id="ced7d-159">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="ced7d-160">Allgemein</span><span class="sxs-lookup"><span data-stu-id="ced7d-160">General</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="ced7d-161">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="ced7d-161">.NET Core 2.1</span></span>](#tab/netcore21)

| <span data-ttu-id="ced7d-162">Befehl</span><span class="sxs-lookup"><span data-stu-id="ced7d-162">Command</span></span>                                       | <span data-ttu-id="ced7d-163">Funktion</span><span class="sxs-lookup"><span data-stu-id="ced7d-163">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="ced7d-164">dotnet build</span><span class="sxs-lookup"><span data-stu-id="ced7d-164">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="ced7d-165">Erstellt eine .NET Core-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ced7d-165">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="ced7d-166">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="ced7d-166">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="ced7d-167">Interagiert mit Servern, die von einem Build gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="ced7d-167">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="ced7d-168">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="ced7d-168">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="ced7d-169">Bereinigen von Buildausgaben.</span><span class="sxs-lookup"><span data-stu-id="ced7d-169">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="ced7d-170">dotnet help</span><span class="sxs-lookup"><span data-stu-id="ced7d-170">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="ced7d-171">Zeigt eine ausführlichere Onlinedokumentation für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="ced7d-171">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="ced7d-172">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="ced7d-172">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="ced7d-173">Migriert ein gültiges Preview 2-Projekt in ein .NET Core SDK 1.0-Projekt.</span><span class="sxs-lookup"><span data-stu-id="ced7d-173">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="ced7d-174">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="ced7d-174">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="ced7d-175">Ermöglicht den Zugriff auf die MSBuild-Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="ced7d-175">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="ced7d-176">dotnet new</span><span class="sxs-lookup"><span data-stu-id="ced7d-176">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="ced7d-177">Initialisiert ein C#- oder F#-Projekt für eine bestimmte Vorlage.</span><span class="sxs-lookup"><span data-stu-id="ced7d-177">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="ced7d-178">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="ced7d-178">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="ced7d-179">Erstellt ein NuGet-Paket aus Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="ced7d-179">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="ced7d-180">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="ced7d-180">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="ced7d-181">Veröffentlicht eine .NET Framework-abhängige oder eigenständige Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ced7d-181">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="ced7d-182">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="ced7d-182">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="ced7d-183">Stellt die Abhängigkeiten für eine bestimmte Anwendung wieder her.</span><span class="sxs-lookup"><span data-stu-id="ced7d-183">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="ced7d-184">dotnet run</span><span class="sxs-lookup"><span data-stu-id="ced7d-184">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="ced7d-185">Führt die Anwendung aus der Quelle aus.</span><span class="sxs-lookup"><span data-stu-id="ced7d-185">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="ced7d-186">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="ced7d-186">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="ced7d-187">Optionen zum Hinzufügen, Entfernen und Listen von Projekten in einer Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="ced7d-187">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="ced7d-188">dotnet store</span><span class="sxs-lookup"><span data-stu-id="ced7d-188">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="ced7d-189">Speichert Assemblys im Laufzeitpaketspeicher.</span><span class="sxs-lookup"><span data-stu-id="ced7d-189">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="ced7d-190">dotnet test</span><span class="sxs-lookup"><span data-stu-id="ced7d-190">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="ced7d-191">Führt Tests mit einem Test Runner aus.</span><span class="sxs-lookup"><span data-stu-id="ced7d-191">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="ced7d-192">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="ced7d-192">.NET Core 2.0</span></span>](#tab/netcore20)

| <span data-ttu-id="ced7d-193">Befehl</span><span class="sxs-lookup"><span data-stu-id="ced7d-193">Command</span></span>                             | <span data-ttu-id="ced7d-194">Funktion</span><span class="sxs-lookup"><span data-stu-id="ced7d-194">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="ced7d-195">dotnet build</span><span class="sxs-lookup"><span data-stu-id="ced7d-195">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="ced7d-196">Erstellt eine .NET Core-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ced7d-196">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="ced7d-197">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="ced7d-197">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="ced7d-198">Bereinigen von Buildausgaben.</span><span class="sxs-lookup"><span data-stu-id="ced7d-198">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="ced7d-199">dotnet help</span><span class="sxs-lookup"><span data-stu-id="ced7d-199">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="ced7d-200">Zeigt eine ausführlichere Onlinedokumentation für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="ced7d-200">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="ced7d-201">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="ced7d-201">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="ced7d-202">Migriert ein gültiges Preview 2-Projekt in ein .NET Core SDK 1.0-Projekt.</span><span class="sxs-lookup"><span data-stu-id="ced7d-202">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="ced7d-203">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="ced7d-203">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="ced7d-204">Ermöglicht den Zugriff auf die MSBuild-Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="ced7d-204">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="ced7d-205">dotnet new</span><span class="sxs-lookup"><span data-stu-id="ced7d-205">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="ced7d-206">Initialisiert ein C#- oder F#-Projekt für eine bestimmte Vorlage.</span><span class="sxs-lookup"><span data-stu-id="ced7d-206">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="ced7d-207">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="ced7d-207">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="ced7d-208">Erstellt ein NuGet-Paket aus Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="ced7d-208">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="ced7d-209">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="ced7d-209">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="ced7d-210">Veröffentlicht eine .NET Framework-abhängige oder eigenständige Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ced7d-210">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="ced7d-211">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="ced7d-211">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="ced7d-212">Stellt die Abhängigkeiten für eine bestimmte Anwendung wieder her.</span><span class="sxs-lookup"><span data-stu-id="ced7d-212">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="ced7d-213">dotnet run</span><span class="sxs-lookup"><span data-stu-id="ced7d-213">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="ced7d-214">Führt die Anwendung aus der Quelle aus.</span><span class="sxs-lookup"><span data-stu-id="ced7d-214">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="ced7d-215">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="ced7d-215">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="ced7d-216">Optionen zum Hinzufügen, Entfernen und Listen von Projekten in einer Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="ced7d-216">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="ced7d-217">dotnet store</span><span class="sxs-lookup"><span data-stu-id="ced7d-217">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="ced7d-218">Speichert Assemblys im Laufzeitpaketspeicher.</span><span class="sxs-lookup"><span data-stu-id="ced7d-218">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="ced7d-219">dotnet test</span><span class="sxs-lookup"><span data-stu-id="ced7d-219">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="ced7d-220">Führt Tests mit einem Test Runner aus.</span><span class="sxs-lookup"><span data-stu-id="ced7d-220">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="ced7d-221">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="ced7d-221">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="ced7d-222">Befehl</span><span class="sxs-lookup"><span data-stu-id="ced7d-222">Command</span></span>                             | <span data-ttu-id="ced7d-223">Funktion</span><span class="sxs-lookup"><span data-stu-id="ced7d-223">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="ced7d-224">dotnet build</span><span class="sxs-lookup"><span data-stu-id="ced7d-224">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="ced7d-225">Erstellt eine .NET Core-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ced7d-225">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="ced7d-226">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="ced7d-226">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="ced7d-227">Bereinigen von Buildausgaben.</span><span class="sxs-lookup"><span data-stu-id="ced7d-227">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="ced7d-228">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="ced7d-228">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="ced7d-229">Migriert ein gültiges Preview 2-Projekt in ein .NET Core SDK 1.0-Projekt.</span><span class="sxs-lookup"><span data-stu-id="ced7d-229">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="ced7d-230">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="ced7d-230">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="ced7d-231">Ermöglicht den Zugriff auf die MSBuild-Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="ced7d-231">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="ced7d-232">dotnet new</span><span class="sxs-lookup"><span data-stu-id="ced7d-232">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="ced7d-233">Initialisiert ein C#- oder F#-Projekt für eine bestimmte Vorlage.</span><span class="sxs-lookup"><span data-stu-id="ced7d-233">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="ced7d-234">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="ced7d-234">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="ced7d-235">Erstellt ein NuGet-Paket aus Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="ced7d-235">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="ced7d-236">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="ced7d-236">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="ced7d-237">Veröffentlicht eine .NET Framework-abhängige oder eigenständige Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ced7d-237">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="ced7d-238">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="ced7d-238">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="ced7d-239">Stellt die Abhängigkeiten für eine bestimmte Anwendung wieder her.</span><span class="sxs-lookup"><span data-stu-id="ced7d-239">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="ced7d-240">dotnet run</span><span class="sxs-lookup"><span data-stu-id="ced7d-240">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="ced7d-241">Führt die Anwendung aus der Quelle aus.</span><span class="sxs-lookup"><span data-stu-id="ced7d-241">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="ced7d-242">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="ced7d-242">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="ced7d-243">Optionen zum Hinzufügen, Entfernen und Listen von Projekten in einer Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="ced7d-243">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="ced7d-244">dotnet test</span><span class="sxs-lookup"><span data-stu-id="ced7d-244">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="ced7d-245">Führt Tests mit einem Test Runner aus.</span><span class="sxs-lookup"><span data-stu-id="ced7d-245">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="ced7d-246">Projektverweise</span><span class="sxs-lookup"><span data-stu-id="ced7d-246">Project references</span></span>

<span data-ttu-id="ced7d-247">Befehl</span><span class="sxs-lookup"><span data-stu-id="ced7d-247">Command</span></span> | <span data-ttu-id="ced7d-248">Funktion</span><span class="sxs-lookup"><span data-stu-id="ced7d-248">Function</span></span>
--- | ---
[<span data-ttu-id="ced7d-249">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="ced7d-249">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="ced7d-250">Fügt einen Projektverweis hinzu.</span><span class="sxs-lookup"><span data-stu-id="ced7d-250">Adds a project reference.</span></span>
[<span data-ttu-id="ced7d-251">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="ced7d-251">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="ced7d-252">Listet Projektverweise auf.</span><span class="sxs-lookup"><span data-stu-id="ced7d-252">Lists project references.</span></span>
[<span data-ttu-id="ced7d-253">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="ced7d-253">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="ced7d-254">Entfernt einen Projektverweis.</span><span class="sxs-lookup"><span data-stu-id="ced7d-254">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="ced7d-255">NuGet-Pakete</span><span class="sxs-lookup"><span data-stu-id="ced7d-255">NuGet packages</span></span>

<span data-ttu-id="ced7d-256">Befehl</span><span class="sxs-lookup"><span data-stu-id="ced7d-256">Command</span></span> | <span data-ttu-id="ced7d-257">Funktion</span><span class="sxs-lookup"><span data-stu-id="ced7d-257">Function</span></span>
--- | ---
[<span data-ttu-id="ced7d-258">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="ced7d-258">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="ced7d-259">Fügt ein NuGet-Paket hinzu.</span><span class="sxs-lookup"><span data-stu-id="ced7d-259">Adds a NuGet package.</span></span>
[<span data-ttu-id="ced7d-260">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="ced7d-260">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="ced7d-261">Entfernt ein NuGet-Paket.</span><span class="sxs-lookup"><span data-stu-id="ced7d-261">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="ced7d-262">NuGet-Befehle</span><span class="sxs-lookup"><span data-stu-id="ced7d-262">NuGet commands</span></span>

<span data-ttu-id="ced7d-263">Befehl</span><span class="sxs-lookup"><span data-stu-id="ced7d-263">Command</span></span> | <span data-ttu-id="ced7d-264">Funktion</span><span class="sxs-lookup"><span data-stu-id="ced7d-264">Function</span></span>
--- | ---
[<span data-ttu-id="ced7d-265">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="ced7d-265">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="ced7d-266">Löscht ein Paket vom Server oder hebt dessen Auflistung auf.</span><span class="sxs-lookup"><span data-stu-id="ced7d-266">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="ced7d-267">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="ced7d-267">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="ced7d-268">Löscht lokale NuGet-Ressourcen, z.B. den http-Anforderungscache, den temporären Cache oder den Ordner mit globalen Paketen auf dem Computer, oder listet diese Ressourcen auf.</span><span class="sxs-lookup"><span data-stu-id="ced7d-268">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="ced7d-269">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="ced7d-269">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="ced7d-270">Überträgt ein Paket auf den Server und veröffentlicht es.</span><span class="sxs-lookup"><span data-stu-id="ced7d-270">Pushes a package to the server and publishes it.</span></span>

### <a name="global-tools-commands"></a><span data-ttu-id="ced7d-271">Befehle für globale Tools</span><span class="sxs-lookup"><span data-stu-id="ced7d-271">Global Tools commands</span></span>

<span data-ttu-id="ced7d-272">[Globale .NET Core-Tools](global-tools.md) sind beginnend mit .NET Core SDK 2.1.300 verfügbar:</span><span class="sxs-lookup"><span data-stu-id="ced7d-272">[.NET Core Global Tools](global-tools.md) are available starting with .NET Core SDK 2.1.300:</span></span>

<span data-ttu-id="ced7d-273">Befehl</span><span class="sxs-lookup"><span data-stu-id="ced7d-273">Command</span></span> | <span data-ttu-id="ced7d-274">Funktion</span><span class="sxs-lookup"><span data-stu-id="ced7d-274">Function</span></span>
--- | ---
[<span data-ttu-id="ced7d-275">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="ced7d-275">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="ced7d-276">Installiert ein Global Tool auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="ced7d-276">Installs a Global Tool on your machine.</span></span>
[<span data-ttu-id="ced7d-277">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="ced7d-277">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="ced7d-278">Listet alle globalen Tools auf, die derzeit im Standardverzeichnis oder unter dem angegebenen Pfad auf Ihrem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="ced7d-278">Lists all Global Tools currently installed in the default directory on your machine or in the specified path.</span></span>
[<span data-ttu-id="ced7d-279">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="ced7d-279">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="ced7d-280">Deinstalliert ein Global-Tool von Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="ced7d-280">Uninstalls a Global Tool from your machine.</span></span>
[<span data-ttu-id="ced7d-281">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="ced7d-281">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="ced7d-282">Aktualisiert ein Global Tool auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="ced7d-282">Updates a Global Tool on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="ced7d-283">Zusätzliche Tools</span><span class="sxs-lookup"><span data-stu-id="ced7d-283">Additional tools</span></span>

<span data-ttu-id="ced7d-284">Beginnend mit .NET Core SDK 2.1.300 steht eine Reihe von Tools, die nur auf Projektbasis unter Verwendung von `DotnetCliToolReference` verfügbar waren, jetzt als Teil des .NET Core SDK zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="ced7d-284">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="ced7d-285">Diese Tools werden in der folgenden Tabelle aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="ced7d-285">These tools are listed in the following table:</span></span>

| <span data-ttu-id="ced7d-286">Tool</span><span class="sxs-lookup"><span data-stu-id="ced7d-286">Tool</span></span>                                              | <span data-ttu-id="ced7d-287">Funktion</span><span class="sxs-lookup"><span data-stu-id="ced7d-287">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="ced7d-288">dev-certs</span><span class="sxs-lookup"><span data-stu-id="ced7d-288">dev-certs</span></span>                                         | <span data-ttu-id="ced7d-289">Erstellt und verwaltet Entwicklungszertifikate.</span><span class="sxs-lookup"><span data-stu-id="ced7d-289">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="ced7d-290">ef</span><span class="sxs-lookup"><span data-stu-id="ced7d-290">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="ced7d-291">Entity Framework Core-Befehlszeilentools.</span><span class="sxs-lookup"><span data-stu-id="ced7d-291">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="ced7d-292">sql-cache</span><span class="sxs-lookup"><span data-stu-id="ced7d-292">sql-cache</span></span>                                         | <span data-ttu-id="ced7d-293">SQL Server-Cache-Befehlszeilentools.</span><span class="sxs-lookup"><span data-stu-id="ced7d-293">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="ced7d-294">user-secrets</span><span class="sxs-lookup"><span data-stu-id="ced7d-294">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="ced7d-295">Verwaltet die Entwicklung von Benutzergeheimnissen.</span><span class="sxs-lookup"><span data-stu-id="ced7d-295">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="ced7d-296">watch</span><span class="sxs-lookup"><span data-stu-id="ced7d-296">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="ced7d-297">Startet einen Datei-Watcher, der einen Befehl ausführt, wenn sich Dateien ändern.</span><span class="sxs-lookup"><span data-stu-id="ced7d-297">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="ced7d-298">Geben Sie `dotnet <tool-name> --help` ein, um weitere Informationen zu den einzelnen Tools zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ced7d-298">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="ced7d-299">Beispiele</span><span class="sxs-lookup"><span data-stu-id="ced7d-299">Examples</span></span>

<span data-ttu-id="ced7d-300">Erstellt eine neue .NET Core-Konsolenanwendung:</span><span class="sxs-lookup"><span data-stu-id="ced7d-300">Creates a new .NET Core console application:</span></span>

`dotnet new console`

<span data-ttu-id="ced7d-301">Wiederherstellen von Abhängigkeiten für eine bestimmte Anwendung:</span><span class="sxs-lookup"><span data-stu-id="ced7d-301">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="ced7d-302">Erstellen eines Projekts und seiner Abhängigkeiten in einem vorgegebenen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="ced7d-302">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="ced7d-303">Führen Sie eine Anwendungs-DLL aus, z.B. `myapp.dll`:</span><span class="sxs-lookup"><span data-stu-id="ced7d-303">Run an application DLL, such as `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="ced7d-304">Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="ced7d-304">Environment variables</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="ced7d-305">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="ced7d-305">.NET Core 2.1</span></span>](#tab/netcore21)

`DOTNET_PACKAGES`

<span data-ttu-id="ced7d-306">Der Cache des primären Pakets.</span><span class="sxs-lookup"><span data-stu-id="ced7d-306">The primary package cache.</span></span> <span data-ttu-id="ced7d-307">Wenn er nicht festgelegt wird, wird standardmäßig `$HOME/.nuget/packages` unter Unix oder `%HOME%\NuGet\Packages` unter Windows verwendet.</span><span class="sxs-lookup"><span data-stu-id="ced7d-307">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="ced7d-308">Gibt den Speicherort des Wartungsindex an, der vom freigegebenen Host verwendet wird, wenn die Laufzeit geladen wird.</span><span class="sxs-lookup"><span data-stu-id="ced7d-308">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="ced7d-309">Gibt an, ob Daten zur Nutzung von .NET Core-Tools gesammelt und an Microsoft gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="ced7d-309">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="ced7d-310">Legen Sie `true` fest, um die Telemetriefunktion zu deaktivieren (Wert `true`, `1` oder `yes` wird akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="ced7d-310">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="ced7d-311">Legen Sie andernfalls `false` fest, um die Telemetriefunktionen zu aktivieren (Wert `false`, `0` oder `no` wird akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="ced7d-311">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="ced7d-312">Ohne Festlegung ist der Standardwert `false`, und die Telemetriefunktion ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ced7d-312">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="ced7d-313">Gibt an, ob die .NET Core-Runtime, das freigegebene Framework oder das SDK vom globalen Speicherort aus aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="ced7d-313">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="ced7d-314">Wenn nicht, ist der Standardwert `true`.</span><span class="sxs-lookup"><span data-stu-id="ced7d-314">If not set, it defaults to `true`.</span></span> <span data-ttu-id="ced7d-315">Wenn der Wert auf `false` festgelegt wird, wird nicht vom globalen Speicherort aus aufgelöst und es gibt isolierte .NET Core-Installationen (die Werte `0` oder `false` werden akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="ced7d-315">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="ced7d-316">Weitere Informationen zu Lookup mit mehreren Ebenen finden Sie unter [Multi-level SharedFX lookup (SharedFX-Lookup mit mehreren Ebenen)](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span><span class="sxs-lookup"><span data-stu-id="ced7d-316">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`

<span data-ttu-id="ced7d-317">Deaktiviert Rollforward der Nebenversion, wenn `0` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ced7d-317">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="ced7d-318">Weitere Informationen finden Sie unter [Rollforward](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="ced7d-318">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="ced7d-319">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="ced7d-319">.NET Core 2.0</span></span>](#tab/netcore20)

`DOTNET_PACKAGES`

<span data-ttu-id="ced7d-320">Der Cache des primären Pakets.</span><span class="sxs-lookup"><span data-stu-id="ced7d-320">The primary package cache.</span></span> <span data-ttu-id="ced7d-321">Wenn er nicht festgelegt wird, wird standardmäßig `$HOME/.nuget/packages` unter Unix oder `%HOME%\NuGet\Packages` unter Windows verwendet.</span><span class="sxs-lookup"><span data-stu-id="ced7d-321">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="ced7d-322">Gibt den Speicherort des Wartungsindex an, der vom freigegebenen Host verwendet wird, wenn die Laufzeit geladen wird.</span><span class="sxs-lookup"><span data-stu-id="ced7d-322">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="ced7d-323">Gibt an, ob Daten zur Nutzung von .NET Core-Tools gesammelt und an Microsoft gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="ced7d-323">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="ced7d-324">Legen Sie `true` fest, um die Telemetriefunktion zu deaktivieren (Wert `true`, `1` oder `yes` wird akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="ced7d-324">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="ced7d-325">Legen Sie andernfalls `false` fest, um die Telemetriefunktionen zu aktivieren (Wert `false`, `0` oder `no` wird akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="ced7d-325">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="ced7d-326">Ohne Festlegung ist der Standardwert `false`, und die Telemetriefunktion ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ced7d-326">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="ced7d-327">Gibt an, ob die .NET Core-Runtime, das freigegebene Framework oder das SDK vom globalen Speicherort aus aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="ced7d-327">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="ced7d-328">Wenn nicht, ist der Standardwert `true`.</span><span class="sxs-lookup"><span data-stu-id="ced7d-328">If not set, it defaults to `true`.</span></span> <span data-ttu-id="ced7d-329">Wenn der Wert auf `false` festgelegt wird, wird nicht vom globalen Speicherort aus aufgelöst und es gibt isolierte .NET Core-Installationen (die Werte `0` oder `false` werden akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="ced7d-329">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="ced7d-330">Weitere Informationen zu Lookup mit mehreren Ebenen finden Sie unter [Multi-level SharedFX lookup (SharedFX-Lookup mit mehreren Ebenen)](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span><span class="sxs-lookup"><span data-stu-id="ced7d-330">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="ced7d-331">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="ced7d-331">.NET Core 1.x</span></span>](#tab/netcore1x)

`DOTNET_PACKAGES`

<span data-ttu-id="ced7d-332">Der Cache des primären Pakets.</span><span class="sxs-lookup"><span data-stu-id="ced7d-332">The primary package cache.</span></span> <span data-ttu-id="ced7d-333">Wenn er nicht festgelegt wird, wird standardmäßig `$HOME/.nuget/packages` unter Unix oder `%HOME%\NuGet\Packages` unter Windows verwendet.</span><span class="sxs-lookup"><span data-stu-id="ced7d-333">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="ced7d-334">Gibt den Speicherort des Wartungsindex an, der vom freigegebenen Host verwendet wird, wenn die Laufzeit geladen wird.</span><span class="sxs-lookup"><span data-stu-id="ced7d-334">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="ced7d-335">Gibt an, ob Daten zur Nutzung von .NET Core-Tools gesammelt und an Microsoft gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="ced7d-335">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="ced7d-336">Legen Sie `true` fest, um die Telemetriefunktion zu deaktivieren (Wert `true`, `1` oder `yes` wird akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="ced7d-336">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="ced7d-337">Legen Sie andernfalls `false` fest, um die Telemetriefunktionen zu aktivieren (Wert `false`, `0` oder `no` wird akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="ced7d-337">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="ced7d-338">Ohne Festlegung ist der Standardwert `false`, und die Telemetriefunktion ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ced7d-338">If not set, the default is `false` and the telemetry feature is active.</span></span>

---
