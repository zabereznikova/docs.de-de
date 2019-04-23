---
title: dotnet-Befehl
description: Informationen zum dotnet-Befehl (generischer Treiber für die .NET Core CLI-Tools) und dessen Verwendung.
ms.date: 06/04/2018
ms.openlocfilehash: 5278adf44d12e428cdeacf1d475377ce9155c314
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2019
ms.locfileid: "59613004"
---
# <a name="dotnet-command"></a><span data-ttu-id="ca1e7-103">dotnet-Befehl</span><span class="sxs-lookup"><span data-stu-id="ca1e7-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="ca1e7-104">name</span><span class="sxs-lookup"><span data-stu-id="ca1e7-104">Name</span></span>

<span data-ttu-id="ca1e7-105">`dotnet`: Ein Tool für das Verwalten von .NET-Quellcode und Binärdateien.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-105">`dotnet` - A tool for managing .NET source code and binaries.</span></span>

## <a name="synopsis"></a><span data-ttu-id="ca1e7-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="ca1e7-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="ca1e7-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="ca1e7-107">.NET Core 2.1</span></span>](#tab/netcore21)

```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [--list-runtimes] [--list-sdks] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="ca1e7-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="ca1e7-108">.NET Core 2.0</span></span>](#tab/netcore20)

```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="ca1e7-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="ca1e7-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet [command] [arguments] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [-v|--verbosity] [--version]
```

---

## <a name="description"></a><span data-ttu-id="ca1e7-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ca1e7-110">Description</span></span>

<span data-ttu-id="ca1e7-111">`dotnet` ist ein Tool für das Verwalten von .NET-Quellcode und Binärdateien.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-111">`dotnet` is a tool for managing .NET source code and binaries.</span></span> <span data-ttu-id="ca1e7-112">Es stellt Befehle zur Verfügung, die bestimmte Aufgaben erfüllen, z.B. [`dotnet build`](dotnet-build.md) und [`dotnet run`](dotnet-run.md).</span><span class="sxs-lookup"><span data-stu-id="ca1e7-112">It exposes commands that perform specific tasks, such as [`dotnet build`](dotnet-build.md) and [`dotnet run`](dotnet-run.md).</span></span> <span data-ttu-id="ca1e7-113">Jeder Befehl definiert seine eigenen Argumente.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-113">Each command defines its own arguments.</span></span> <span data-ttu-id="ca1e7-114">Geben Sie nach jedem Befehl `--help` ein, um auf eine kurze Hilfsdokumentation zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-114">Type `--help` after each command to access brief help documentation.</span></span>

<span data-ttu-id="ca1e7-115">`dotnet` kann zum Ausführen von Anwendungen verwendet werden, indem eine Anwendungs-DLL angegeben wird, z.B. `dotnet myapp.dll`.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-115">`dotnet` can be used to run applications, by specifying an application DLL, such as `dotnet myapp.dll`.</span></span> <span data-ttu-id="ca1e7-116">Weitere Informationen über Bereitstellungsoptionen finden Sie unter [.NET Core-Anwendungsbereitstellung](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="ca1e7-116">See [.NET Core application deployment](../deploying/index.md) for to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="ca1e7-117">Optionen</span><span class="sxs-lookup"><span data-stu-id="ca1e7-117">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="ca1e7-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="ca1e7-118">.NET Core 2.1</span></span>](#tab/netcore21)

`--additional-deps <PATH>`

<span data-ttu-id="ca1e7-119">Pfad zur zusätzlichen *deps.json*-Datei.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-119">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="ca1e7-120">Pfad, der die Suchrichtlinie und die zu suchenden Assemblys enthält.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-120">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="ca1e7-121">Ermöglicht die diagnostische Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-121">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="ca1e7-122">Version der .NET Core-Runtime, die zum Ausführen der Anwendung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-122">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="ca1e7-123">Gibt Dokumentation für einen bestimmten Befehl aus, z.B. `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-123">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="ca1e7-124">`dotnet --help` gibt eine Liste der verfügbaren Befehle zurück.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-124">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="ca1e7-125">Gibt ausführliche Informationen über eine .NET Core-Installation und die Computerumgebung aus, z.B. das aktuelle Betriebssystem und den Commit-SHA für die .NET Core-Version.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-125">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--list-runtimes`

<span data-ttu-id="ca1e7-126">Zeigt die installierten .NET Core-Runtimes an.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-126">Displays the installed .NET Core runtimes.</span></span>

`--list-sdks`

<span data-ttu-id="ca1e7-127">Zeigt die installierten .NET Core-SDKs an.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-127">Displays the installed .NET Core SDKs.</span></span>

`--roll-forward-on-no-candidate-fx <N>`

<span data-ttu-id="ca1e7-128">Definiert ein Verhalten, wenn das erforderliche freigegebene Framework nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-128">Defines behavior when the required shared framework is not available.</span></span> <span data-ttu-id="ca1e7-129">`N` kann Folgendes sein:</span><span class="sxs-lookup"><span data-stu-id="ca1e7-129">`N` can be:</span></span>
* <span data-ttu-id="ca1e7-130">`0` - Das Ausführen von Rollforward ist auch für die Nebenversion deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-130">`0` - Disable even minor version roll forward.</span></span>
* <span data-ttu-id="ca1e7-131">`1` - Rollforward wird in der Nebenversion, nicht aber in der Hauptversion, ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-131">`1` - Roll forward on minor version, but not on major version.</span></span> <span data-ttu-id="ca1e7-132">Dies ist das Standardverhalten.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-132">This is the default behavior.</span></span>
* <span data-ttu-id="ca1e7-133">`2` - Rollforward wird in Neben- und Hauptversionen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-133">`2` - Roll forward on minor and major versions.</span></span>

 <span data-ttu-id="ca1e7-134">Weitere Informationen finden Sie unter [Rollforward](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="ca1e7-134">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="ca1e7-135">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-135">Sets the verbosity level of the command.</span></span> <span data-ttu-id="ca1e7-136">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-136">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="ca1e7-137">Nicht in jedem Befehl unterstützt. Auf der Seite der einzelnen Befehle finden Sie heraus, ob diese Option verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-137">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="ca1e7-138">Druckt die Version des verwendeten .NET Core-SDK aus.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-138">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="ca1e7-139">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="ca1e7-139">.NET Core 2.0</span></span>](#tab/netcore20)

`--additional-deps <PATH>`

<span data-ttu-id="ca1e7-140">Pfad zur zusätzlichen *deps.json*-Datei.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-140">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="ca1e7-141">Pfad, der die Suchrichtlinie und die zu suchenden Assemblys enthält.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-141">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="ca1e7-142">Ermöglicht die diagnostische Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-142">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="ca1e7-143">Version der .NET Core-Runtime, die zum Ausführen der Anwendung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-143">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="ca1e7-144">Gibt Dokumentation für einen bestimmten Befehl aus, z.B. `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-144">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="ca1e7-145">`dotnet --help` gibt eine Liste der verfügbaren Befehle zurück.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-145">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="ca1e7-146">Gibt ausführliche Informationen über eine .NET Core-Installation und die Computerumgebung aus, z.B. das aktuelle Betriebssystem und den Commit-SHA für die .NET Core-Version.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-146">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="ca1e7-147">Deaktiviert Rollforward der Nebenversion, wenn `0` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-147">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="ca1e7-148">Weitere Informationen finden Sie unter [Rollforward](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="ca1e7-148">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="ca1e7-149">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-149">Sets the verbosity level of the command.</span></span> <span data-ttu-id="ca1e7-150">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-150">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="ca1e7-151">Nicht in jedem Befehl unterstützt. Auf der Seite der einzelnen Befehle finden Sie heraus, ob diese Option verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-151">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="ca1e7-152">Druckt die Version des verwendeten .NET Core-SDK aus.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-152">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="ca1e7-153">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="ca1e7-153">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="ca1e7-154">Pfad, der die Suchrichtlinie und die zu suchenden Assemblys enthält.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-154">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="ca1e7-155">Ermöglicht die diagnostische Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-155">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="ca1e7-156">Version der .NET Core-Runtime, die zum Ausführen der Anwendung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-156">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="ca1e7-157">Gibt Dokumentation für einen bestimmten Befehl aus, z.B. `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-157">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="ca1e7-158">`dotnet --help` gibt eine Liste der verfügbaren Befehle zurück.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-158">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="ca1e7-159">Gibt ausführliche Informationen über eine .NET Core-Installation und die Computerumgebung aus, z.B. das aktuelle Betriebssystem und den Commit-SHA für die .NET Core-Version.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-159">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="ca1e7-160">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-160">Sets the verbosity level of the command.</span></span> <span data-ttu-id="ca1e7-161">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-161">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="ca1e7-162">Nicht in jedem Befehl unterstützt. Auf der Seite der einzelnen Befehle finden Sie heraus, ob diese Option verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-162">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="ca1e7-163">Druckt die Version des verwendeten .NET Core-SDK aus.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-163">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="ca1e7-164">dotnet-Befehle</span><span class="sxs-lookup"><span data-stu-id="ca1e7-164">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="ca1e7-165">Allgemein</span><span class="sxs-lookup"><span data-stu-id="ca1e7-165">General</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="ca1e7-166">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="ca1e7-166">.NET Core 2.1</span></span>](#tab/netcore21)

| <span data-ttu-id="ca1e7-167">Befehl</span><span class="sxs-lookup"><span data-stu-id="ca1e7-167">Command</span></span>                                       | <span data-ttu-id="ca1e7-168">Funktion</span><span class="sxs-lookup"><span data-stu-id="ca1e7-168">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="ca1e7-169">dotnet build</span><span class="sxs-lookup"><span data-stu-id="ca1e7-169">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="ca1e7-170">Erstellt eine .NET Core-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-170">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="ca1e7-171">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="ca1e7-171">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="ca1e7-172">Interagiert mit Servern, die von einem Build gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-172">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="ca1e7-173">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="ca1e7-173">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="ca1e7-174">Bereinigen von Buildausgaben.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-174">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="ca1e7-175">dotnet help</span><span class="sxs-lookup"><span data-stu-id="ca1e7-175">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="ca1e7-176">Zeigt eine ausführlichere Onlinedokumentation für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-176">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="ca1e7-177">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="ca1e7-177">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="ca1e7-178">Migriert ein gültiges Preview 2-Projekt in ein .NET Core SDK 1.0-Projekt.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-178">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="ca1e7-179">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="ca1e7-179">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="ca1e7-180">Ermöglicht den Zugriff auf die MSBuild-Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="ca1e7-180">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="ca1e7-181">dotnet new</span><span class="sxs-lookup"><span data-stu-id="ca1e7-181">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="ca1e7-182">Initialisiert ein C#- oder F#-Projekt für eine bestimmte Vorlage.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-182">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="ca1e7-183">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="ca1e7-183">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="ca1e7-184">Erstellt ein NuGet-Paket aus Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-184">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="ca1e7-185">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="ca1e7-185">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="ca1e7-186">Veröffentlicht eine .NET Framework-abhängige oder eigenständige Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-186">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="ca1e7-187">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="ca1e7-187">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="ca1e7-188">Stellt die Abhängigkeiten für eine bestimmte Anwendung wieder her.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-188">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="ca1e7-189">dotnet run</span><span class="sxs-lookup"><span data-stu-id="ca1e7-189">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="ca1e7-190">Führt die Anwendung aus der Quelle aus.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-190">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="ca1e7-191">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="ca1e7-191">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="ca1e7-192">Optionen zum Hinzufügen, Entfernen und Listen von Projekten in einer Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-192">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="ca1e7-193">dotnet store</span><span class="sxs-lookup"><span data-stu-id="ca1e7-193">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="ca1e7-194">Speichert Assemblys im Laufzeitpaketspeicher.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-194">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="ca1e7-195">dotnet test</span><span class="sxs-lookup"><span data-stu-id="ca1e7-195">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="ca1e7-196">Führt Tests mit einem Test Runner aus.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-196">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="ca1e7-197">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="ca1e7-197">.NET Core 2.0</span></span>](#tab/netcore20)

| <span data-ttu-id="ca1e7-198">Befehl</span><span class="sxs-lookup"><span data-stu-id="ca1e7-198">Command</span></span>                             | <span data-ttu-id="ca1e7-199">Funktion</span><span class="sxs-lookup"><span data-stu-id="ca1e7-199">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="ca1e7-200">dotnet build</span><span class="sxs-lookup"><span data-stu-id="ca1e7-200">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="ca1e7-201">Erstellt eine .NET Core-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-201">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="ca1e7-202">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="ca1e7-202">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="ca1e7-203">Bereinigen von Buildausgaben.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-203">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="ca1e7-204">dotnet help</span><span class="sxs-lookup"><span data-stu-id="ca1e7-204">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="ca1e7-205">Zeigt eine ausführlichere Onlinedokumentation für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-205">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="ca1e7-206">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="ca1e7-206">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="ca1e7-207">Migriert ein gültiges Preview 2-Projekt in ein .NET Core SDK 1.0-Projekt.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-207">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="ca1e7-208">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="ca1e7-208">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="ca1e7-209">Ermöglicht den Zugriff auf die MSBuild-Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="ca1e7-209">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="ca1e7-210">dotnet new</span><span class="sxs-lookup"><span data-stu-id="ca1e7-210">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="ca1e7-211">Initialisiert ein C#- oder F#-Projekt für eine bestimmte Vorlage.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-211">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="ca1e7-212">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="ca1e7-212">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="ca1e7-213">Erstellt ein NuGet-Paket aus Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-213">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="ca1e7-214">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="ca1e7-214">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="ca1e7-215">Veröffentlicht eine .NET Framework-abhängige oder eigenständige Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-215">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="ca1e7-216">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="ca1e7-216">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="ca1e7-217">Stellt die Abhängigkeiten für eine bestimmte Anwendung wieder her.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-217">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="ca1e7-218">dotnet run</span><span class="sxs-lookup"><span data-stu-id="ca1e7-218">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="ca1e7-219">Führt die Anwendung aus der Quelle aus.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-219">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="ca1e7-220">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="ca1e7-220">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="ca1e7-221">Optionen zum Hinzufügen, Entfernen und Listen von Projekten in einer Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-221">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="ca1e7-222">dotnet store</span><span class="sxs-lookup"><span data-stu-id="ca1e7-222">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="ca1e7-223">Speichert Assemblys im Laufzeitpaketspeicher.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-223">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="ca1e7-224">dotnet test</span><span class="sxs-lookup"><span data-stu-id="ca1e7-224">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="ca1e7-225">Führt Tests mit einem Test Runner aus.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-225">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="ca1e7-226">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="ca1e7-226">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="ca1e7-227">Befehl</span><span class="sxs-lookup"><span data-stu-id="ca1e7-227">Command</span></span>                             | <span data-ttu-id="ca1e7-228">Funktion</span><span class="sxs-lookup"><span data-stu-id="ca1e7-228">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="ca1e7-229">dotnet build</span><span class="sxs-lookup"><span data-stu-id="ca1e7-229">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="ca1e7-230">Erstellt eine .NET Core-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-230">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="ca1e7-231">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="ca1e7-231">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="ca1e7-232">Bereinigen von Buildausgaben.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-232">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="ca1e7-233">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="ca1e7-233">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="ca1e7-234">Migriert ein gültiges Preview 2-Projekt in ein .NET Core SDK 1.0-Projekt.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-234">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="ca1e7-235">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="ca1e7-235">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="ca1e7-236">Ermöglicht den Zugriff auf die MSBuild-Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="ca1e7-236">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="ca1e7-237">dotnet new</span><span class="sxs-lookup"><span data-stu-id="ca1e7-237">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="ca1e7-238">Initialisiert ein C#- oder F#-Projekt für eine bestimmte Vorlage.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-238">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="ca1e7-239">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="ca1e7-239">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="ca1e7-240">Erstellt ein NuGet-Paket aus Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-240">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="ca1e7-241">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="ca1e7-241">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="ca1e7-242">Veröffentlicht eine .NET Framework-abhängige oder eigenständige Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-242">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="ca1e7-243">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="ca1e7-243">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="ca1e7-244">Stellt die Abhängigkeiten für eine bestimmte Anwendung wieder her.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-244">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="ca1e7-245">dotnet run</span><span class="sxs-lookup"><span data-stu-id="ca1e7-245">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="ca1e7-246">Führt die Anwendung aus der Quelle aus.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-246">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="ca1e7-247">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="ca1e7-247">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="ca1e7-248">Optionen zum Hinzufügen, Entfernen und Listen von Projekten in einer Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-248">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="ca1e7-249">dotnet test</span><span class="sxs-lookup"><span data-stu-id="ca1e7-249">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="ca1e7-250">Führt Tests mit einem Test Runner aus.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-250">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="ca1e7-251">Projektverweise</span><span class="sxs-lookup"><span data-stu-id="ca1e7-251">Project references</span></span>

<span data-ttu-id="ca1e7-252">Befehl</span><span class="sxs-lookup"><span data-stu-id="ca1e7-252">Command</span></span> | <span data-ttu-id="ca1e7-253">Funktion</span><span class="sxs-lookup"><span data-stu-id="ca1e7-253">Function</span></span>
--- | ---
[<span data-ttu-id="ca1e7-254">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="ca1e7-254">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="ca1e7-255">Fügt einen Projektverweis hinzu.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-255">Adds a project reference.</span></span>
[<span data-ttu-id="ca1e7-256">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="ca1e7-256">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="ca1e7-257">Listet Projektverweise auf.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-257">Lists project references.</span></span>
[<span data-ttu-id="ca1e7-258">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="ca1e7-258">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="ca1e7-259">Entfernt einen Projektverweis.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-259">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="ca1e7-260">NuGet-Pakete</span><span class="sxs-lookup"><span data-stu-id="ca1e7-260">NuGet packages</span></span>

<span data-ttu-id="ca1e7-261">Befehl</span><span class="sxs-lookup"><span data-stu-id="ca1e7-261">Command</span></span> | <span data-ttu-id="ca1e7-262">Funktion</span><span class="sxs-lookup"><span data-stu-id="ca1e7-262">Function</span></span>
--- | ---
[<span data-ttu-id="ca1e7-263">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="ca1e7-263">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="ca1e7-264">Fügt ein NuGet-Paket hinzu.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-264">Adds a NuGet package.</span></span>
[<span data-ttu-id="ca1e7-265">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="ca1e7-265">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="ca1e7-266">Entfernt ein NuGet-Paket.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-266">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="ca1e7-267">NuGet-Befehle</span><span class="sxs-lookup"><span data-stu-id="ca1e7-267">NuGet commands</span></span>

<span data-ttu-id="ca1e7-268">Befehl</span><span class="sxs-lookup"><span data-stu-id="ca1e7-268">Command</span></span> | <span data-ttu-id="ca1e7-269">Funktion</span><span class="sxs-lookup"><span data-stu-id="ca1e7-269">Function</span></span>
--- | ---
[<span data-ttu-id="ca1e7-270">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="ca1e7-270">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="ca1e7-271">Löscht ein Paket vom Server oder hebt dessen Auflistung auf.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-271">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="ca1e7-272">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="ca1e7-272">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="ca1e7-273">Löscht lokale NuGet-Ressourcen, z.B. den http-Anforderungscache, den temporären Cache oder den Ordner mit globalen Paketen auf dem Computer, oder listet diese Ressourcen auf.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-273">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="ca1e7-274">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="ca1e7-274">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="ca1e7-275">Überträgt ein Paket auf den Server und veröffentlicht es.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-275">Pushes a package to the server and publishes it.</span></span>

### <a name="global-tools-commands"></a><span data-ttu-id="ca1e7-276">Befehle für globale Tools</span><span class="sxs-lookup"><span data-stu-id="ca1e7-276">Global Tools commands</span></span>

<span data-ttu-id="ca1e7-277">[Globale .NET Core-Tools](global-tools.md) sind beginnend mit .NET Core SDK 2.1.300 verfügbar:</span><span class="sxs-lookup"><span data-stu-id="ca1e7-277">[.NET Core Global Tools](global-tools.md) are available starting with .NET Core SDK 2.1.300:</span></span>

<span data-ttu-id="ca1e7-278">Befehl</span><span class="sxs-lookup"><span data-stu-id="ca1e7-278">Command</span></span> | <span data-ttu-id="ca1e7-279">Funktion</span><span class="sxs-lookup"><span data-stu-id="ca1e7-279">Function</span></span>
--- | ---
[<span data-ttu-id="ca1e7-280">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="ca1e7-280">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="ca1e7-281">Installiert ein Global Tool auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-281">Installs a Global Tool on your machine.</span></span>
[<span data-ttu-id="ca1e7-282">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="ca1e7-282">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="ca1e7-283">Listet alle globalen Tools auf, die derzeit im Standardverzeichnis oder unter dem angegebenen Pfad auf Ihrem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-283">Lists all Global Tools currently installed in the default directory on your machine or in the specified path.</span></span>
[<span data-ttu-id="ca1e7-284">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="ca1e7-284">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="ca1e7-285">Deinstalliert ein Global-Tool von Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-285">Uninstalls a Global Tool from your machine.</span></span>
[<span data-ttu-id="ca1e7-286">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="ca1e7-286">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="ca1e7-287">Aktualisiert ein Global Tool auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-287">Updates a Global Tool on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="ca1e7-288">Weitere Tools</span><span class="sxs-lookup"><span data-stu-id="ca1e7-288">Additional tools</span></span>

<span data-ttu-id="ca1e7-289">Beginnend mit .NET Core SDK 2.1.300 steht eine Reihe von Tools, die nur auf Projektbasis unter Verwendung von `DotnetCliToolReference` verfügbar waren, jetzt als Teil des .NET Core SDK zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-289">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="ca1e7-290">Diese Tools werden in der folgenden Tabelle aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="ca1e7-290">These tools are listed in the following table:</span></span>

| <span data-ttu-id="ca1e7-291">Tool</span><span class="sxs-lookup"><span data-stu-id="ca1e7-291">Tool</span></span>                                              | <span data-ttu-id="ca1e7-292">Funktion</span><span class="sxs-lookup"><span data-stu-id="ca1e7-292">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="ca1e7-293">dev-certs</span><span class="sxs-lookup"><span data-stu-id="ca1e7-293">dev-certs</span></span>                                         | <span data-ttu-id="ca1e7-294">Erstellt und verwaltet Entwicklungszertifikate.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-294">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="ca1e7-295">ef</span><span class="sxs-lookup"><span data-stu-id="ca1e7-295">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="ca1e7-296">Entity Framework Core-Befehlszeilentools.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-296">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="ca1e7-297">sql-cache</span><span class="sxs-lookup"><span data-stu-id="ca1e7-297">sql-cache</span></span>                                         | <span data-ttu-id="ca1e7-298">SQL Server-Cache-Befehlszeilentools.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-298">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="ca1e7-299">user-secrets</span><span class="sxs-lookup"><span data-stu-id="ca1e7-299">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="ca1e7-300">Verwaltet die Entwicklung von Benutzergeheimnissen.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-300">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="ca1e7-301">watch</span><span class="sxs-lookup"><span data-stu-id="ca1e7-301">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="ca1e7-302">Startet einen Datei-Watcher, der einen Befehl ausführt, wenn sich Dateien ändern.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-302">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="ca1e7-303">Geben Sie `dotnet <tool-name> --help` ein, um weitere Informationen zu den einzelnen Tools zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-303">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="ca1e7-304">Beispiele</span><span class="sxs-lookup"><span data-stu-id="ca1e7-304">Examples</span></span>

<span data-ttu-id="ca1e7-305">Erstellt eine neue .NET Core-Konsolenanwendung:</span><span class="sxs-lookup"><span data-stu-id="ca1e7-305">Creates a new .NET Core console application:</span></span>

`dotnet new console`

<span data-ttu-id="ca1e7-306">Wiederherstellen von Abhängigkeiten für eine bestimmte Anwendung:</span><span class="sxs-lookup"><span data-stu-id="ca1e7-306">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="ca1e7-307">Erstellen eines Projekts und seiner Abhängigkeiten in einem vorgegebenen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="ca1e7-307">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="ca1e7-308">Führen Sie eine Anwendungs-DLL aus, z.B. `myapp.dll`:</span><span class="sxs-lookup"><span data-stu-id="ca1e7-308">Run an application DLL, such as `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="ca1e7-309">Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="ca1e7-309">Environment variables</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="ca1e7-310">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="ca1e7-310">.NET Core 2.1</span></span>](#tab/netcore21)

`DOTNET_PACKAGES`

<span data-ttu-id="ca1e7-311">Der Cache des primären Pakets.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-311">The primary package cache.</span></span> <span data-ttu-id="ca1e7-312">Wenn er nicht festgelegt wird, wird standardmäßig `$HOME/.nuget/packages` unter Unix oder `%HOME%\NuGet\Packages` unter Windows verwendet.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-312">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="ca1e7-313">Gibt den Speicherort des Wartungsindex an, der vom freigegebenen Host verwendet wird, wenn die Laufzeit geladen wird.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-313">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="ca1e7-314">Gibt an, ob Daten zur Nutzung von .NET Core-Tools gesammelt und an Microsoft gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-314">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="ca1e7-315">Legen Sie `true` fest, um die Telemetriefunktion zu deaktivieren (Wert `true`, `1` oder `yes` wird akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="ca1e7-315">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="ca1e7-316">Legen Sie andernfalls `false` fest, um die Telemetriefunktionen zu aktivieren (Wert `false`, `0` oder `no` wird akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="ca1e7-316">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="ca1e7-317">Ohne Festlegung ist der Standardwert `false`, und die Telemetriefunktion ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-317">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="ca1e7-318">Gibt an, ob die .NET Core-Runtime, das freigegebene Framework oder das SDK vom globalen Speicherort aus aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-318">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="ca1e7-319">Wenn nicht, ist der Standardwert `true`.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-319">If not set, it defaults to `true`.</span></span> <span data-ttu-id="ca1e7-320">Wenn der Wert auf `false` festgelegt wird, wird nicht vom globalen Speicherort aus aufgelöst und es gibt isolierte .NET Core-Installationen (die Werte `0` oder `false` werden akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="ca1e7-320">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="ca1e7-321">Weitere Informationen zu Lookup mit mehreren Ebenen finden Sie unter [Multi-level SharedFX lookup (SharedFX-Lookup mit mehreren Ebenen)](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span><span class="sxs-lookup"><span data-stu-id="ca1e7-321">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`

<span data-ttu-id="ca1e7-322">Deaktiviert Rollforward der Nebenversion, wenn `0` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-322">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="ca1e7-323">Weitere Informationen finden Sie unter [Rollforward](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="ca1e7-323">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="ca1e7-324">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="ca1e7-324">.NET Core 2.0</span></span>](#tab/netcore20)

`DOTNET_PACKAGES`

<span data-ttu-id="ca1e7-325">Der Cache des primären Pakets.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-325">The primary package cache.</span></span> <span data-ttu-id="ca1e7-326">Wenn er nicht festgelegt wird, wird standardmäßig `$HOME/.nuget/packages` unter Unix oder `%HOME%\NuGet\Packages` unter Windows verwendet.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-326">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="ca1e7-327">Gibt den Speicherort des Wartungsindex an, der vom freigegebenen Host verwendet wird, wenn die Laufzeit geladen wird.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-327">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="ca1e7-328">Gibt an, ob Daten zur Nutzung von .NET Core-Tools gesammelt und an Microsoft gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-328">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="ca1e7-329">Legen Sie `true` fest, um die Telemetriefunktion zu deaktivieren (Wert `true`, `1` oder `yes` wird akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="ca1e7-329">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="ca1e7-330">Legen Sie andernfalls `false` fest, um die Telemetriefunktionen zu aktivieren (Wert `false`, `0` oder `no` wird akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="ca1e7-330">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="ca1e7-331">Ohne Festlegung ist der Standardwert `false`, und die Telemetriefunktion ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-331">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="ca1e7-332">Gibt an, ob die .NET Core-Runtime, das freigegebene Framework oder das SDK vom globalen Speicherort aus aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-332">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="ca1e7-333">Wenn nicht, ist der Standardwert `true`.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-333">If not set, it defaults to `true`.</span></span> <span data-ttu-id="ca1e7-334">Wenn der Wert auf `false` festgelegt wird, wird nicht vom globalen Speicherort aus aufgelöst und es gibt isolierte .NET Core-Installationen (die Werte `0` oder `false` werden akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="ca1e7-334">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="ca1e7-335">Weitere Informationen zu Lookup mit mehreren Ebenen finden Sie unter [Multi-level SharedFX lookup (SharedFX-Lookup mit mehreren Ebenen)](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span><span class="sxs-lookup"><span data-stu-id="ca1e7-335">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="ca1e7-336">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="ca1e7-336">.NET Core 1.x</span></span>](#tab/netcore1x)

`DOTNET_PACKAGES`

<span data-ttu-id="ca1e7-337">Der Cache des primären Pakets.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-337">The primary package cache.</span></span> <span data-ttu-id="ca1e7-338">Wenn er nicht festgelegt wird, wird standardmäßig `$HOME/.nuget/packages` unter Unix oder `%HOME%\NuGet\Packages` unter Windows verwendet.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-338">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="ca1e7-339">Gibt den Speicherort des Wartungsindex an, der vom freigegebenen Host verwendet wird, wenn die Laufzeit geladen wird.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-339">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="ca1e7-340">Gibt an, ob Daten zur Nutzung von .NET Core-Tools gesammelt und an Microsoft gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-340">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="ca1e7-341">Legen Sie `true` fest, um die Telemetriefunktion zu deaktivieren (Wert `true`, `1` oder `yes` wird akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="ca1e7-341">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="ca1e7-342">Legen Sie andernfalls `false` fest, um die Telemetriefunktionen zu aktivieren (Wert `false`, `0` oder `no` wird akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="ca1e7-342">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="ca1e7-343">Ohne Festlegung ist der Standardwert `false`, und die Telemetriefunktion ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ca1e7-343">If not set, the default is `false` and the telemetry feature is active.</span></span>

---
