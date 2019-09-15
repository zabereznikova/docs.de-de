---
title: dotnet-Befehl
description: Informationen zum dotnet-Befehl (generischer Treiber für die .NET Core CLI-Tools) und dessen Verwendung.
ms.date: 06/04/2018
ms.openlocfilehash: 801320bf7f3527ac70f1d5b9fe3d0ce537e50e93
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2019
ms.locfileid: "70969779"
---
# <a name="dotnet-command"></a><span data-ttu-id="ad18b-103">dotnet-Befehl</span><span class="sxs-lookup"><span data-stu-id="ad18b-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="ad18b-104">name</span><span class="sxs-lookup"><span data-stu-id="ad18b-104">Name</span></span>

<span data-ttu-id="ad18b-105">`dotnet`: Ein Tool für das Verwalten von .NET-Quellcode und Binärdateien.</span><span class="sxs-lookup"><span data-stu-id="ad18b-105">`dotnet` - A tool for managing .NET source code and binaries.</span></span>

## <a name="synopsis"></a><span data-ttu-id="ad18b-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="ad18b-106">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="ad18b-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="ad18b-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [--depsfile]
    [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [--list-runtimes] [--list-sdks] [--roll-forward-on-no-candidate-fx] [--runtimeconfig] [-v|--verbosity] [--version]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="ad18b-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="ad18b-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [--depsfile]
    [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx]
    [--runtimeconfig] [-v|--verbosity] [--version]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="ad18b-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="ad18b-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet [command] [arguments] [--additionalprobingpath] [--depsfile] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--runtimeconfig] [-v|--verbosity] [--version]
```

---

## <a name="description"></a><span data-ttu-id="ad18b-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ad18b-110">Description</span></span>

<span data-ttu-id="ad18b-111">`dotnet` ist ein Tool für das Verwalten von .NET-Quellcode und Binärdateien.</span><span class="sxs-lookup"><span data-stu-id="ad18b-111">`dotnet` is a tool for managing .NET source code and binaries.</span></span> <span data-ttu-id="ad18b-112">Es stellt Befehle zur Verfügung, die bestimmte Aufgaben erfüllen, z.B. [`dotnet build`](dotnet-build.md) und [`dotnet run`](dotnet-run.md).</span><span class="sxs-lookup"><span data-stu-id="ad18b-112">It exposes commands that perform specific tasks, such as [`dotnet build`](dotnet-build.md) and [`dotnet run`](dotnet-run.md).</span></span> <span data-ttu-id="ad18b-113">Jeder Befehl definiert seine eigenen Argumente.</span><span class="sxs-lookup"><span data-stu-id="ad18b-113">Each command defines its own arguments.</span></span> <span data-ttu-id="ad18b-114">Geben Sie nach jedem Befehl `--help` ein, um auf eine kurze Hilfsdokumentation zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="ad18b-114">Type `--help` after each command to access brief help documentation.</span></span>

<span data-ttu-id="ad18b-115">`dotnet` kann zum Ausführen von Anwendungen verwendet werden, indem eine Anwendungs-DLL angegeben wird, z.B. `dotnet myapp.dll`.</span><span class="sxs-lookup"><span data-stu-id="ad18b-115">`dotnet` can be used to run applications, by specifying an application DLL, such as `dotnet myapp.dll`.</span></span> <span data-ttu-id="ad18b-116">Weitere Informationen über Bereitstellungsoptionen finden Sie unter [.NET Core-Anwendungsbereitstellung](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="ad18b-116">See [.NET Core application deployment](../deploying/index.md) for to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="ad18b-117">Optionen</span><span class="sxs-lookup"><span data-stu-id="ad18b-117">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="ad18b-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="ad18b-118">.NET Core 2.1</span></span>](#tab/netcore21)

`--additional-deps <PATH>`

<span data-ttu-id="ad18b-119">Pfad zu einer zusätzlichen *.deps.json*-Datei.</span><span class="sxs-lookup"><span data-stu-id="ad18b-119">Path to an additional *.deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="ad18b-120">Pfad, der die Suchrichtlinie und die zu suchenden Assemblys enthält.</span><span class="sxs-lookup"><span data-stu-id="ad18b-120">Path containing probing policy and assemblies to probe.</span></span>

`--depsfile`

<span data-ttu-id="ad18b-121">Pfad zu einer *deps.json*-Datei.</span><span class="sxs-lookup"><span data-stu-id="ad18b-121">Path to a *deps.json* file.</span></span>

<span data-ttu-id="ad18b-122">Eine *deps.json*-Datei enthält eine Liste mit (Kompilierungs-)Abhängigkeiten und Versionsinformationen, die verwendet werden, um Assemblykonflikte zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="ad18b-122">A *deps.json* file contains a list of dependencies, compilation dependencies and version information used to address assembly conflicts.</span></span> <span data-ttu-id="ad18b-123">Weitere Informationen zu dieser Datei finden Sie auf GitHub unter [Laufzeitkonfigurationsdateien](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="ad18b-123">For more information about this file, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) on GitHub.</span></span>

`-d|--diagnostics`

<span data-ttu-id="ad18b-124">Ermöglicht die diagnostische Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="ad18b-124">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="ad18b-125">Version der .NET Core-Runtime, die zum Ausführen der Anwendung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ad18b-125">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="ad18b-126">Gibt Dokumentation für einen bestimmten Befehl aus, z.B. `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="ad18b-126">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="ad18b-127">`dotnet --help` gibt eine Liste der verfügbaren Befehle zurück.</span><span class="sxs-lookup"><span data-stu-id="ad18b-127">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="ad18b-128">Gibt ausführliche Informationen über eine .NET Core-Installation und die Computerumgebung aus, z.B. das aktuelle Betriebssystem und den Commit-SHA für die .NET Core-Version.</span><span class="sxs-lookup"><span data-stu-id="ad18b-128">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--list-runtimes`

<span data-ttu-id="ad18b-129">Zeigt die installierten .NET Core-Runtimes an.</span><span class="sxs-lookup"><span data-stu-id="ad18b-129">Displays the installed .NET Core runtimes.</span></span>

`--list-sdks`

<span data-ttu-id="ad18b-130">Zeigt die installierten .NET Core-SDKs an.</span><span class="sxs-lookup"><span data-stu-id="ad18b-130">Displays the installed .NET Core SDKs.</span></span>

`--roll-forward-on-no-candidate-fx <N>`

<span data-ttu-id="ad18b-131">Definiert ein Verhalten, wenn das erforderliche freigegebene Framework nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ad18b-131">Defines behavior when the required shared framework is not available.</span></span> <span data-ttu-id="ad18b-132">`N` kann Folgendes sein:</span><span class="sxs-lookup"><span data-stu-id="ad18b-132">`N` can be:</span></span>

- <span data-ttu-id="ad18b-133">`0` - Das Ausführen von Rollforward ist auch für die Nebenversion deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="ad18b-133">`0` - Disable even minor version roll forward.</span></span>
- <span data-ttu-id="ad18b-134">`1` - Rollforward wird in der Nebenversion, nicht aber in der Hauptversion, ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ad18b-134">`1` - Roll forward on minor version, but not on major version.</span></span> <span data-ttu-id="ad18b-135">Dies ist das Standardverhalten.</span><span class="sxs-lookup"><span data-stu-id="ad18b-135">This is the default behavior.</span></span>
- <span data-ttu-id="ad18b-136">`2` - Rollforward wird in Neben- und Hauptversionen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ad18b-136">`2` - Roll forward on minor and major versions.</span></span>

 <span data-ttu-id="ad18b-137">Weitere Informationen finden Sie unter [Rollforward](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="ad18b-137">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`--runtimeconfig`

<span data-ttu-id="ad18b-138">Der Pfad zu einer *runtimeconfig.json*-Datei.</span><span class="sxs-lookup"><span data-stu-id="ad18b-138">Path to a *runtimeconfig.json* file.</span></span>

<span data-ttu-id="ad18b-139">Eine *runtimeconfig.json*-Datei ist eine Konfigurationsdatei mit Einstellungen für die Laufzeitkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="ad18b-139">A *runtimeconfig.json* file is a configuration file containing runtime configuration settings.</span></span> <span data-ttu-id="ad18b-140">Weitere Informationen finden Sie auf GitHub unter [Laufzeitkonfigurationsdateien](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="ad18b-140">For more information, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) on GitHub.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="ad18b-141">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="ad18b-141">Sets the verbosity level of the command.</span></span> <span data-ttu-id="ad18b-142">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="ad18b-142">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="ad18b-143">Nicht in jedem Befehl unterstützt. Auf der Seite der einzelnen Befehle finden Sie heraus, ob diese Option verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ad18b-143">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="ad18b-144">Druckt die Version des verwendeten .NET Core-SDK aus.</span><span class="sxs-lookup"><span data-stu-id="ad18b-144">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="ad18b-145">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="ad18b-145">.NET Core 2.0</span></span>](#tab/netcore20)

`--additional-deps <PATH>`

<span data-ttu-id="ad18b-146">Pfad zu einer zusätzlichen *.deps.json*-Datei.</span><span class="sxs-lookup"><span data-stu-id="ad18b-146">Path to an additional *.deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="ad18b-147">Pfad, der die Suchrichtlinie und die zu suchenden Assemblys enthält.</span><span class="sxs-lookup"><span data-stu-id="ad18b-147">Path containing probing policy and assemblies to probe.</span></span>

`--depsfile`

<span data-ttu-id="ad18b-148">Pfad zu einer *deps.json*-Datei.</span><span class="sxs-lookup"><span data-stu-id="ad18b-148">Path to a *deps.json* file.</span></span>

<span data-ttu-id="ad18b-149">Eine *deps.json*-Datei enthält eine Liste mit (Kompilierungs-)Abhängigkeiten und Versionsinformationen, die verwendet werden, um Assemblykonflikte zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="ad18b-149">A *deps.json* file contains a list of dependencies, compilation dependencies and version information used to address assembly conflicts.</span></span> <span data-ttu-id="ad18b-150">Weitere Informationen zu dieser Datei finden Sie auf [GitHub unter Laufzeitkonfigurationsdateien](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="ad18b-150">For more details on this file, see [Runtime Configuration Files on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

`-d|--diagnostics`

<span data-ttu-id="ad18b-151">Ermöglicht die diagnostische Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="ad18b-151">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="ad18b-152">Version der .NET Core-Runtime, die zum Ausführen der Anwendung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ad18b-152">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="ad18b-153">Gibt Dokumentation für einen bestimmten Befehl aus, z.B. `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="ad18b-153">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="ad18b-154">`dotnet --help` gibt eine Liste der verfügbaren Befehle zurück.</span><span class="sxs-lookup"><span data-stu-id="ad18b-154">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="ad18b-155">Gibt ausführliche Informationen über eine .NET Core-Installation und die Computerumgebung aus, z.B. das aktuelle Betriebssystem und den Commit-SHA für die .NET Core-Version.</span><span class="sxs-lookup"><span data-stu-id="ad18b-155">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="ad18b-156">Deaktiviert Rollforward der Nebenversion, wenn `0` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ad18b-156">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="ad18b-157">Weitere Informationen finden Sie unter [Rollforward](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="ad18b-157">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`--runtimeconfig`

<span data-ttu-id="ad18b-158">Der Pfad zu einer *runtimeconfig.json*-Datei.</span><span class="sxs-lookup"><span data-stu-id="ad18b-158">Path to a *runtimeconfig.json* file.</span></span>

<span data-ttu-id="ad18b-159">Eine *runtimeconfig.json*-Datei ist eine Konfigurationsdatei mit Einstellungen für die Laufzeitkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="ad18b-159">A *runtimeconfig.json* file is a configuration file containing runtime configuration settings.</span></span> <span data-ttu-id="ad18b-160">Weitere Informationen finden Sie auf [GitHub unter Laufzeitkonfigurationsdateien](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="ad18b-160">For more details, see [Runtime Configuration Files on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="ad18b-161">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="ad18b-161">Sets the verbosity level of the command.</span></span> <span data-ttu-id="ad18b-162">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="ad18b-162">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="ad18b-163">Nicht in jedem Befehl unterstützt. Auf der Seite der einzelnen Befehle finden Sie heraus, ob diese Option verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ad18b-163">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="ad18b-164">Druckt die Version des verwendeten .NET Core-SDK aus.</span><span class="sxs-lookup"><span data-stu-id="ad18b-164">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="ad18b-165">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="ad18b-165">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="ad18b-166">Pfad, der die Suchrichtlinie und die zu suchenden Assemblys enthält.</span><span class="sxs-lookup"><span data-stu-id="ad18b-166">Path containing probing policy and assemblies to probe.</span></span>

`--depsfile`

<span data-ttu-id="ad18b-167">Pfad zu einer *deps.json*-Datei.</span><span class="sxs-lookup"><span data-stu-id="ad18b-167">Path to a *deps.json* file.</span></span>

<span data-ttu-id="ad18b-168">Eine *deps.json*-Datei enthält eine Liste mit (Kompilierungs-)Abhängigkeiten und Versionsinformationen, die verwendet werden, um Assemblykonflikte zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="ad18b-168">A *deps.json* file contains a list of dependencies, compilation dependencies and version information used to address assembly conflicts.</span></span> <span data-ttu-id="ad18b-169">Weitere Informationen zu dieser Datei finden Sie auf [GitHub unter Laufzeitkonfigurationsdateien](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="ad18b-169">For more details on this file, see [Runtime Configuration Files on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

`-d|--diagnostics`

<span data-ttu-id="ad18b-170">Ermöglicht die diagnostische Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="ad18b-170">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="ad18b-171">Version der .NET Core-Runtime, die zum Ausführen der Anwendung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ad18b-171">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="ad18b-172">Gibt Dokumentation für einen bestimmten Befehl aus, z.B. `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="ad18b-172">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="ad18b-173">`dotnet --help` gibt eine Liste der verfügbaren Befehle zurück.</span><span class="sxs-lookup"><span data-stu-id="ad18b-173">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="ad18b-174">Gibt ausführliche Informationen über eine .NET Core-Installation und die Computerumgebung aus, z.B. das aktuelle Betriebssystem und den Commit-SHA für die .NET Core-Version.</span><span class="sxs-lookup"><span data-stu-id="ad18b-174">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--runtimeconfig`

<span data-ttu-id="ad18b-175">Der Pfad zu einer *runtimeconfig.json*-Datei.</span><span class="sxs-lookup"><span data-stu-id="ad18b-175">Path to a *runtimeconfig.json* file.</span></span>

<span data-ttu-id="ad18b-176">Eine *runtimeconfig.json*-Datei ist eine Konfigurationsdatei mit Einstellungen für die Laufzeitkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="ad18b-176">A *runtimeconfig.json* file is a configuration file containing runtime configuration settings.</span></span> <span data-ttu-id="ad18b-177">Weitere Informationen finden Sie auf [GitHub unter Laufzeitkonfigurationsdateien](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="ad18b-177">For more details, see [Runtime Configuration Files on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="ad18b-178">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="ad18b-178">Sets the verbosity level of the command.</span></span> <span data-ttu-id="ad18b-179">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="ad18b-179">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="ad18b-180">Nicht in jedem Befehl unterstützt. Auf der Seite der einzelnen Befehle finden Sie heraus, ob diese Option verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ad18b-180">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="ad18b-181">Druckt die Version des verwendeten .NET Core-SDK aus.</span><span class="sxs-lookup"><span data-stu-id="ad18b-181">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="ad18b-182">dotnet-Befehle</span><span class="sxs-lookup"><span data-stu-id="ad18b-182">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="ad18b-183">Allgemein</span><span class="sxs-lookup"><span data-stu-id="ad18b-183">General</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="ad18b-184">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="ad18b-184">.NET Core 2.1</span></span>](#tab/netcore21)

| <span data-ttu-id="ad18b-185">Befehl</span><span class="sxs-lookup"><span data-stu-id="ad18b-185">Command</span></span>                                       | <span data-ttu-id="ad18b-186">Funktion</span><span class="sxs-lookup"><span data-stu-id="ad18b-186">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="ad18b-187">dotnet build</span><span class="sxs-lookup"><span data-stu-id="ad18b-187">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="ad18b-188">Erstellt eine .NET Core-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ad18b-188">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="ad18b-189">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="ad18b-189">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="ad18b-190">Interagiert mit Servern, die von einem Build gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="ad18b-190">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="ad18b-191">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="ad18b-191">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="ad18b-192">Bereinigen von Buildausgaben.</span><span class="sxs-lookup"><span data-stu-id="ad18b-192">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="ad18b-193">dotnet help</span><span class="sxs-lookup"><span data-stu-id="ad18b-193">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="ad18b-194">Zeigt eine ausführlichere Onlinedokumentation für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="ad18b-194">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="ad18b-195">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="ad18b-195">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="ad18b-196">Migriert ein gültiges Preview 2-Projekt in ein .NET Core SDK 1.0-Projekt.</span><span class="sxs-lookup"><span data-stu-id="ad18b-196">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="ad18b-197">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="ad18b-197">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="ad18b-198">Ermöglicht den Zugriff auf die MSBuild-Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="ad18b-198">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="ad18b-199">dotnet new</span><span class="sxs-lookup"><span data-stu-id="ad18b-199">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="ad18b-200">Initialisiert ein C#- oder F#-Projekt für eine bestimmte Vorlage.</span><span class="sxs-lookup"><span data-stu-id="ad18b-200">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="ad18b-201">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="ad18b-201">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="ad18b-202">Erstellt ein NuGet-Paket aus Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="ad18b-202">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="ad18b-203">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="ad18b-203">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="ad18b-204">Veröffentlicht eine .NET Framework-abhängige oder eigenständige Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ad18b-204">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="ad18b-205">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="ad18b-205">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="ad18b-206">Stellt die Abhängigkeiten für eine bestimmte Anwendung wieder her.</span><span class="sxs-lookup"><span data-stu-id="ad18b-206">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="ad18b-207">dotnet run</span><span class="sxs-lookup"><span data-stu-id="ad18b-207">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="ad18b-208">Führt die Anwendung aus der Quelle aus.</span><span class="sxs-lookup"><span data-stu-id="ad18b-208">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="ad18b-209">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="ad18b-209">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="ad18b-210">Optionen zum Hinzufügen, Entfernen und Listen von Projekten in einer Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="ad18b-210">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="ad18b-211">dotnet store</span><span class="sxs-lookup"><span data-stu-id="ad18b-211">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="ad18b-212">Speichert Assemblys im Laufzeitpaketspeicher.</span><span class="sxs-lookup"><span data-stu-id="ad18b-212">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="ad18b-213">dotnet test</span><span class="sxs-lookup"><span data-stu-id="ad18b-213">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="ad18b-214">Führt Tests mit einem Test Runner aus.</span><span class="sxs-lookup"><span data-stu-id="ad18b-214">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="ad18b-215">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="ad18b-215">.NET Core 2.0</span></span>](#tab/netcore20)

| <span data-ttu-id="ad18b-216">Befehl</span><span class="sxs-lookup"><span data-stu-id="ad18b-216">Command</span></span>                             | <span data-ttu-id="ad18b-217">Funktion</span><span class="sxs-lookup"><span data-stu-id="ad18b-217">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="ad18b-218">dotnet build</span><span class="sxs-lookup"><span data-stu-id="ad18b-218">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="ad18b-219">Erstellt eine .NET Core-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ad18b-219">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="ad18b-220">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="ad18b-220">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="ad18b-221">Bereinigen von Buildausgaben.</span><span class="sxs-lookup"><span data-stu-id="ad18b-221">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="ad18b-222">dotnet help</span><span class="sxs-lookup"><span data-stu-id="ad18b-222">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="ad18b-223">Zeigt eine ausführlichere Onlinedokumentation für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="ad18b-223">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="ad18b-224">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="ad18b-224">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="ad18b-225">Migriert ein gültiges Preview 2-Projekt in ein .NET Core SDK 1.0-Projekt.</span><span class="sxs-lookup"><span data-stu-id="ad18b-225">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="ad18b-226">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="ad18b-226">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="ad18b-227">Ermöglicht den Zugriff auf die MSBuild-Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="ad18b-227">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="ad18b-228">dotnet new</span><span class="sxs-lookup"><span data-stu-id="ad18b-228">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="ad18b-229">Initialisiert ein C#- oder F#-Projekt für eine bestimmte Vorlage.</span><span class="sxs-lookup"><span data-stu-id="ad18b-229">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="ad18b-230">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="ad18b-230">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="ad18b-231">Erstellt ein NuGet-Paket aus Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="ad18b-231">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="ad18b-232">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="ad18b-232">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="ad18b-233">Veröffentlicht eine .NET Framework-abhängige oder eigenständige Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ad18b-233">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="ad18b-234">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="ad18b-234">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="ad18b-235">Stellt die Abhängigkeiten für eine bestimmte Anwendung wieder her.</span><span class="sxs-lookup"><span data-stu-id="ad18b-235">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="ad18b-236">dotnet run</span><span class="sxs-lookup"><span data-stu-id="ad18b-236">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="ad18b-237">Führt die Anwendung aus der Quelle aus.</span><span class="sxs-lookup"><span data-stu-id="ad18b-237">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="ad18b-238">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="ad18b-238">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="ad18b-239">Optionen zum Hinzufügen, Entfernen und Listen von Projekten in einer Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="ad18b-239">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="ad18b-240">dotnet store</span><span class="sxs-lookup"><span data-stu-id="ad18b-240">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="ad18b-241">Speichert Assemblys im Laufzeitpaketspeicher.</span><span class="sxs-lookup"><span data-stu-id="ad18b-241">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="ad18b-242">dotnet test</span><span class="sxs-lookup"><span data-stu-id="ad18b-242">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="ad18b-243">Führt Tests mit einem Test Runner aus.</span><span class="sxs-lookup"><span data-stu-id="ad18b-243">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="ad18b-244">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="ad18b-244">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="ad18b-245">Befehl</span><span class="sxs-lookup"><span data-stu-id="ad18b-245">Command</span></span>                             | <span data-ttu-id="ad18b-246">Funktion</span><span class="sxs-lookup"><span data-stu-id="ad18b-246">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="ad18b-247">dotnet build</span><span class="sxs-lookup"><span data-stu-id="ad18b-247">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="ad18b-248">Erstellt eine .NET Core-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ad18b-248">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="ad18b-249">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="ad18b-249">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="ad18b-250">Bereinigen von Buildausgaben.</span><span class="sxs-lookup"><span data-stu-id="ad18b-250">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="ad18b-251">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="ad18b-251">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="ad18b-252">Migriert ein gültiges Preview 2-Projekt in ein .NET Core SDK 1.0-Projekt.</span><span class="sxs-lookup"><span data-stu-id="ad18b-252">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="ad18b-253">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="ad18b-253">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="ad18b-254">Ermöglicht den Zugriff auf die MSBuild-Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="ad18b-254">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="ad18b-255">dotnet new</span><span class="sxs-lookup"><span data-stu-id="ad18b-255">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="ad18b-256">Initialisiert ein C#- oder F#-Projekt für eine bestimmte Vorlage.</span><span class="sxs-lookup"><span data-stu-id="ad18b-256">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="ad18b-257">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="ad18b-257">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="ad18b-258">Erstellt ein NuGet-Paket aus Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="ad18b-258">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="ad18b-259">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="ad18b-259">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="ad18b-260">Veröffentlicht eine .NET Framework-abhängige oder eigenständige Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ad18b-260">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="ad18b-261">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="ad18b-261">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="ad18b-262">Stellt die Abhängigkeiten für eine bestimmte Anwendung wieder her.</span><span class="sxs-lookup"><span data-stu-id="ad18b-262">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="ad18b-263">dotnet run</span><span class="sxs-lookup"><span data-stu-id="ad18b-263">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="ad18b-264">Führt die Anwendung aus der Quelle aus.</span><span class="sxs-lookup"><span data-stu-id="ad18b-264">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="ad18b-265">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="ad18b-265">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="ad18b-266">Optionen zum Hinzufügen, Entfernen und Listen von Projekten in einer Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="ad18b-266">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="ad18b-267">dotnet test</span><span class="sxs-lookup"><span data-stu-id="ad18b-267">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="ad18b-268">Führt Tests mit einem Test Runner aus.</span><span class="sxs-lookup"><span data-stu-id="ad18b-268">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="ad18b-269">Projektverweise</span><span class="sxs-lookup"><span data-stu-id="ad18b-269">Project references</span></span>

<span data-ttu-id="ad18b-270">Befehl</span><span class="sxs-lookup"><span data-stu-id="ad18b-270">Command</span></span> | <span data-ttu-id="ad18b-271">Funktion</span><span class="sxs-lookup"><span data-stu-id="ad18b-271">Function</span></span>
--- | ---
[<span data-ttu-id="ad18b-272">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="ad18b-272">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="ad18b-273">Fügt einen Projektverweis hinzu.</span><span class="sxs-lookup"><span data-stu-id="ad18b-273">Adds a project reference.</span></span>
[<span data-ttu-id="ad18b-274">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="ad18b-274">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="ad18b-275">Listet Projektverweise auf.</span><span class="sxs-lookup"><span data-stu-id="ad18b-275">Lists project references.</span></span>
[<span data-ttu-id="ad18b-276">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="ad18b-276">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="ad18b-277">Entfernt einen Projektverweis.</span><span class="sxs-lookup"><span data-stu-id="ad18b-277">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="ad18b-278">NuGet-Pakete</span><span class="sxs-lookup"><span data-stu-id="ad18b-278">NuGet packages</span></span>

<span data-ttu-id="ad18b-279">Befehl</span><span class="sxs-lookup"><span data-stu-id="ad18b-279">Command</span></span> | <span data-ttu-id="ad18b-280">Funktion</span><span class="sxs-lookup"><span data-stu-id="ad18b-280">Function</span></span>
--- | ---
[<span data-ttu-id="ad18b-281">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="ad18b-281">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="ad18b-282">Fügt ein NuGet-Paket hinzu.</span><span class="sxs-lookup"><span data-stu-id="ad18b-282">Adds a NuGet package.</span></span>
[<span data-ttu-id="ad18b-283">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="ad18b-283">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="ad18b-284">Entfernt ein NuGet-Paket.</span><span class="sxs-lookup"><span data-stu-id="ad18b-284">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="ad18b-285">NuGet-Befehle</span><span class="sxs-lookup"><span data-stu-id="ad18b-285">NuGet commands</span></span>

<span data-ttu-id="ad18b-286">Befehl</span><span class="sxs-lookup"><span data-stu-id="ad18b-286">Command</span></span> | <span data-ttu-id="ad18b-287">Funktion</span><span class="sxs-lookup"><span data-stu-id="ad18b-287">Function</span></span>
--- | ---
[<span data-ttu-id="ad18b-288">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="ad18b-288">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="ad18b-289">Löscht ein Paket vom Server oder hebt dessen Auflistung auf.</span><span class="sxs-lookup"><span data-stu-id="ad18b-289">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="ad18b-290">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="ad18b-290">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="ad18b-291">Löscht lokale NuGet-Ressourcen, z.B. den http-Anforderungscache, den temporären Cache oder den Ordner mit globalen Paketen auf dem Computer, oder listet diese Ressourcen auf.</span><span class="sxs-lookup"><span data-stu-id="ad18b-291">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="ad18b-292">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="ad18b-292">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="ad18b-293">Überträgt ein Paket auf den Server und veröffentlicht es.</span><span class="sxs-lookup"><span data-stu-id="ad18b-293">Pushes a package to the server and publishes it.</span></span>

### <a name="global-tools-commands"></a><span data-ttu-id="ad18b-294">Befehle für globale Tools</span><span class="sxs-lookup"><span data-stu-id="ad18b-294">Global Tools commands</span></span>

<span data-ttu-id="ad18b-295">[Globale .NET Core-Tools](global-tools.md) sind beginnend mit .NET Core SDK 2.1.300 verfügbar:</span><span class="sxs-lookup"><span data-stu-id="ad18b-295">[.NET Core Global Tools](global-tools.md) are available starting with .NET Core SDK 2.1.300:</span></span>

<span data-ttu-id="ad18b-296">Befehl</span><span class="sxs-lookup"><span data-stu-id="ad18b-296">Command</span></span> | <span data-ttu-id="ad18b-297">Funktion</span><span class="sxs-lookup"><span data-stu-id="ad18b-297">Function</span></span>
--- | ---
[<span data-ttu-id="ad18b-298">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="ad18b-298">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="ad18b-299">Installiert ein Global Tool auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="ad18b-299">Installs a Global Tool on your machine.</span></span>
[<span data-ttu-id="ad18b-300">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="ad18b-300">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="ad18b-301">Listet alle globalen Tools auf, die derzeit im Standardverzeichnis oder unter dem angegebenen Pfad auf Ihrem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="ad18b-301">Lists all Global Tools currently installed in the default directory on your machine or in the specified path.</span></span>
[<span data-ttu-id="ad18b-302">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="ad18b-302">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="ad18b-303">Deinstalliert ein Global-Tool von Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="ad18b-303">Uninstalls a Global Tool from your machine.</span></span>
[<span data-ttu-id="ad18b-304">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="ad18b-304">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="ad18b-305">Aktualisiert ein Global Tool auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="ad18b-305">Updates a Global Tool on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="ad18b-306">Weitere Tools</span><span class="sxs-lookup"><span data-stu-id="ad18b-306">Additional tools</span></span>

<span data-ttu-id="ad18b-307">Beginnend mit .NET Core SDK 2.1.300 steht eine Reihe von Tools, die nur auf Projektbasis unter Verwendung von `DotnetCliToolReference` verfügbar waren, jetzt als Teil des .NET Core SDK zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="ad18b-307">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="ad18b-308">Diese Tools werden in der folgenden Tabelle aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="ad18b-308">These tools are listed in the following table:</span></span>

| <span data-ttu-id="ad18b-309">Tool</span><span class="sxs-lookup"><span data-stu-id="ad18b-309">Tool</span></span>                                              | <span data-ttu-id="ad18b-310">Funktion</span><span class="sxs-lookup"><span data-stu-id="ad18b-310">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="ad18b-311">dev-certs</span><span class="sxs-lookup"><span data-stu-id="ad18b-311">dev-certs</span></span>                                         | <span data-ttu-id="ad18b-312">Erstellt und verwaltet Entwicklungszertifikate.</span><span class="sxs-lookup"><span data-stu-id="ad18b-312">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="ad18b-313">ef</span><span class="sxs-lookup"><span data-stu-id="ad18b-313">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="ad18b-314">Entity Framework Core-Befehlszeilentools.</span><span class="sxs-lookup"><span data-stu-id="ad18b-314">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="ad18b-315">sql-cache</span><span class="sxs-lookup"><span data-stu-id="ad18b-315">sql-cache</span></span>                                         | <span data-ttu-id="ad18b-316">SQL Server-Cache-Befehlszeilentools.</span><span class="sxs-lookup"><span data-stu-id="ad18b-316">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="ad18b-317">user-secrets</span><span class="sxs-lookup"><span data-stu-id="ad18b-317">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="ad18b-318">Verwaltet die Entwicklung von Benutzergeheimnissen.</span><span class="sxs-lookup"><span data-stu-id="ad18b-318">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="ad18b-319">watch</span><span class="sxs-lookup"><span data-stu-id="ad18b-319">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="ad18b-320">Startet einen Datei-Watcher, der einen Befehl ausführt, wenn sich Dateien ändern.</span><span class="sxs-lookup"><span data-stu-id="ad18b-320">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="ad18b-321">Geben Sie `dotnet <tool-name> --help` ein, um weitere Informationen zu den einzelnen Tools zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ad18b-321">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="ad18b-322">Beispiele</span><span class="sxs-lookup"><span data-stu-id="ad18b-322">Examples</span></span>

<span data-ttu-id="ad18b-323">Erstellt eine neue .NET Core-Konsolenanwendung:</span><span class="sxs-lookup"><span data-stu-id="ad18b-323">Creates a new .NET Core console application:</span></span>

`dotnet new console`

<span data-ttu-id="ad18b-324">Wiederherstellen von Abhängigkeiten für eine bestimmte Anwendung:</span><span class="sxs-lookup"><span data-stu-id="ad18b-324">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="ad18b-325">Erstellen eines Projekts und seiner Abhängigkeiten in einem vorgegebenen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="ad18b-325">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="ad18b-326">Führen Sie eine Anwendungs-DLL aus, z.B. `myapp.dll`:</span><span class="sxs-lookup"><span data-stu-id="ad18b-326">Run an application DLL, such as `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="ad18b-327">Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="ad18b-327">Environment variables</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="ad18b-328">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="ad18b-328">.NET Core 2.1</span></span>](#tab/netcore21)

`DOTNET_PACKAGES`

<span data-ttu-id="ad18b-329">Der Ordner für globale Pakete.</span><span class="sxs-lookup"><span data-stu-id="ad18b-329">The global packages folder.</span></span> <span data-ttu-id="ad18b-330">Wenn er nicht festgelegt wird, wird standardmäßig `~/.nuget/packages` unter Unix oder `%userprofile%\.nuget\packages` unter Windows verwendet.</span><span class="sxs-lookup"><span data-stu-id="ad18b-330">If not set, it defaults to `~/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="ad18b-331">Gibt den Speicherort des Wartungsindex an, der vom freigegebenen Host verwendet wird, wenn die Laufzeit geladen wird.</span><span class="sxs-lookup"><span data-stu-id="ad18b-331">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="ad18b-332">Gibt an, ob Daten zur Nutzung von .NET Core-Tools gesammelt und an Microsoft gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="ad18b-332">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="ad18b-333">Legen Sie `true` fest, um die Telemetriefunktion zu deaktivieren (Wert `true`, `1` oder `yes` wird akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="ad18b-333">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="ad18b-334">Legen Sie andernfalls `false` fest, um die Telemetriefunktionen zu aktivieren (Wert `false`, `0` oder `no` wird akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="ad18b-334">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="ad18b-335">Ohne Festlegung ist der Standardwert `false`, und die Telemetriefunktion ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ad18b-335">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="ad18b-336">Gibt an, ob die .NET Core-Runtime, das freigegebene Framework oder das SDK vom globalen Speicherort aus aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="ad18b-336">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="ad18b-337">Wenn nicht, ist der Standardwert `true`.</span><span class="sxs-lookup"><span data-stu-id="ad18b-337">If not set, it defaults to `true`.</span></span> <span data-ttu-id="ad18b-338">Wenn der Wert auf `false` festgelegt wird, wird nicht vom globalen Speicherort aus aufgelöst und es gibt isolierte .NET Core-Installationen (die Werte `0` oder `false` werden akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="ad18b-338">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="ad18b-339">Weitere Informationen zu Lookup mit mehreren Ebenen finden Sie unter [Multi-level SharedFX lookup (SharedFX-Lookup mit mehreren Ebenen)](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span><span class="sxs-lookup"><span data-stu-id="ad18b-339">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`

<span data-ttu-id="ad18b-340">Deaktiviert Rollforward der Nebenversion, wenn `0` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ad18b-340">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="ad18b-341">Weitere Informationen finden Sie unter [Rollforward](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="ad18b-341">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="ad18b-342">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="ad18b-342">.NET Core 2.0</span></span>](#tab/netcore20)

`DOTNET_PACKAGES`

<span data-ttu-id="ad18b-343">Der Cache des primären Pakets.</span><span class="sxs-lookup"><span data-stu-id="ad18b-343">The primary package cache.</span></span> <span data-ttu-id="ad18b-344">Wenn er nicht festgelegt wird, wird standardmäßig `$HOME/.nuget/packages` unter Unix oder `%userprofile%\.nuget\packages` unter Windows verwendet.</span><span class="sxs-lookup"><span data-stu-id="ad18b-344">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="ad18b-345">Gibt den Speicherort des Wartungsindex an, der vom freigegebenen Host verwendet wird, wenn die Laufzeit geladen wird.</span><span class="sxs-lookup"><span data-stu-id="ad18b-345">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="ad18b-346">Gibt an, ob Daten zur Nutzung von .NET Core-Tools gesammelt und an Microsoft gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="ad18b-346">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="ad18b-347">Legen Sie `true` fest, um die Telemetriefunktion zu deaktivieren (Wert `true`, `1` oder `yes` wird akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="ad18b-347">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="ad18b-348">Legen Sie andernfalls `false` fest, um die Telemetriefunktionen zu aktivieren (Wert `false`, `0` oder `no` wird akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="ad18b-348">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="ad18b-349">Ohne Festlegung ist der Standardwert `false`, und die Telemetriefunktion ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ad18b-349">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="ad18b-350">Gibt an, ob die .NET Core-Runtime, das freigegebene Framework oder das SDK vom globalen Speicherort aus aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="ad18b-350">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="ad18b-351">Wenn nicht, ist der Standardwert `true`.</span><span class="sxs-lookup"><span data-stu-id="ad18b-351">If not set, it defaults to `true`.</span></span> <span data-ttu-id="ad18b-352">Wenn der Wert auf `false` festgelegt wird, wird nicht vom globalen Speicherort aus aufgelöst und es gibt isolierte .NET Core-Installationen (die Werte `0` oder `false` werden akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="ad18b-352">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="ad18b-353">Weitere Informationen zu Lookup mit mehreren Ebenen finden Sie unter [Multi-level SharedFX lookup (SharedFX-Lookup mit mehreren Ebenen)](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span><span class="sxs-lookup"><span data-stu-id="ad18b-353">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="ad18b-354">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="ad18b-354">.NET Core 1.x</span></span>](#tab/netcore1x)

`DOTNET_PACKAGES`

<span data-ttu-id="ad18b-355">Der Cache des primären Pakets.</span><span class="sxs-lookup"><span data-stu-id="ad18b-355">The primary package cache.</span></span> <span data-ttu-id="ad18b-356">Wenn er nicht festgelegt wird, wird standardmäßig `$HOME/.nuget/packages` unter Unix oder `%userprofile%\.nuget\packages` unter Windows verwendet.</span><span class="sxs-lookup"><span data-stu-id="ad18b-356">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="ad18b-357">Gibt den Speicherort des Wartungsindex an, der vom freigegebenen Host verwendet wird, wenn die Laufzeit geladen wird.</span><span class="sxs-lookup"><span data-stu-id="ad18b-357">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="ad18b-358">Gibt an, ob Daten zur Nutzung von .NET Core-Tools gesammelt und an Microsoft gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="ad18b-358">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="ad18b-359">Legen Sie `true` fest, um die Telemetriefunktion zu deaktivieren (Wert `true`, `1` oder `yes` wird akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="ad18b-359">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="ad18b-360">Legen Sie andernfalls `false` fest, um die Telemetriefunktionen zu aktivieren (Wert `false`, `0` oder `no` wird akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="ad18b-360">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="ad18b-361">Ohne Festlegung ist der Standardwert `false`, und die Telemetriefunktion ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ad18b-361">If not set, the default is `false` and the telemetry feature is active.</span></span>

---

## <a name="see-also"></a><span data-ttu-id="ad18b-362">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad18b-362">See also</span></span>

- [<span data-ttu-id="ad18b-363">Laufzeitkonfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="ad18b-363">Runtime Configuration Files</span></span>](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)
