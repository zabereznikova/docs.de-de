---
title: dotnet-Befehl
description: Erfahren Sie mehr über den dotnet-Befehl (den generischen Treiber für die .NET Core-CLI) und dessen Verwendung.
ms.date: 02/13/2020
ms.openlocfilehash: 364978465b63401907b46ead64dbceb2f15c8169
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451167"
---
# <a name="dotnet-command"></a><span data-ttu-id="c68b8-103">dotnet-Befehl</span><span class="sxs-lookup"><span data-stu-id="c68b8-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="c68b8-104">name</span><span class="sxs-lookup"><span data-stu-id="c68b8-104">Name</span></span>

<span data-ttu-id="c68b8-105">`dotnet`: Ein Tool für das Verwalten von .NET-Quellcode und Binärdateien.</span><span class="sxs-lookup"><span data-stu-id="c68b8-105">`dotnet` - A tool for managing .NET source code and binaries.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c68b8-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="c68b8-106">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-21"></a>[<span data-ttu-id="c68b8-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c68b8-107">.NET Core 2.1</span></span>](#tab/netcore21)

```dotnetcli
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [--depsfile]
    [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [--list-runtimes] [--list-sdks] [--roll-forward-on-no-candidate-fx] [--runtimeconfig] [-v|--verbosity] [--version]
```

# <a name="net-core-20"></a>[<span data-ttu-id="c68b8-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="c68b8-108">.NET Core 2.0</span></span>](#tab/netcore20)

```dotnetcli
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [--depsfile]
    [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx]
    [--runtimeconfig] [-v|--verbosity] [--version]
```

# <a name="net-core-1x"></a>[<span data-ttu-id="c68b8-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c68b8-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet [command] [arguments] [--additionalprobingpath] [--depsfile] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--runtimeconfig] [-v|--verbosity] [--version]
```

---

## <a name="description"></a><span data-ttu-id="c68b8-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c68b8-110">Description</span></span>

<span data-ttu-id="c68b8-111">`dotnet` ist ein Tool für das Verwalten von .NET-Quellcode und Binärdateien.</span><span class="sxs-lookup"><span data-stu-id="c68b8-111">`dotnet` is a tool for managing .NET source code and binaries.</span></span> <span data-ttu-id="c68b8-112">Es stellt Befehle zur Verfügung, die bestimmte Aufgaben erfüllen, z.B. [`dotnet build`](dotnet-build.md) und [`dotnet run`](dotnet-run.md).</span><span class="sxs-lookup"><span data-stu-id="c68b8-112">It exposes commands that perform specific tasks, such as [`dotnet build`](dotnet-build.md) and [`dotnet run`](dotnet-run.md).</span></span> <span data-ttu-id="c68b8-113">Jeder Befehl definiert seine eigenen Argumente.</span><span class="sxs-lookup"><span data-stu-id="c68b8-113">Each command defines its own arguments.</span></span> <span data-ttu-id="c68b8-114">Geben Sie nach jedem Befehl `--help` ein, um auf eine kurze Hilfsdokumentation zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="c68b8-114">Type `--help` after each command to access brief help documentation.</span></span>

<span data-ttu-id="c68b8-115">`dotnet` kann zum Ausführen von Anwendungen verwendet werden, indem eine Anwendungs-DLL angegeben wird, z.B. `dotnet myapp.dll`.</span><span class="sxs-lookup"><span data-stu-id="c68b8-115">`dotnet` can be used to run applications, by specifying an application DLL, such as `dotnet myapp.dll`.</span></span> <span data-ttu-id="c68b8-116">Weitere Informationen über Bereitstellungsoptionen finden Sie unter [.NET Core-Anwendungsbereitstellung](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="c68b8-116">See [.NET Core application deployment](../deploying/index.md) for to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="c68b8-117">Optionen</span><span class="sxs-lookup"><span data-stu-id="c68b8-117">Options</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="c68b8-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c68b8-118">.NET Core 2.1</span></span>](#tab/netcore21)

`--additional-deps <PATH>`

<span data-ttu-id="c68b8-119">Pfad zu einer zusätzlichen *.deps.json*-Datei.</span><span class="sxs-lookup"><span data-stu-id="c68b8-119">Path to an additional *.deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="c68b8-120">Pfad, der die Suchrichtlinie und die zu suchenden Assemblys enthält.</span><span class="sxs-lookup"><span data-stu-id="c68b8-120">Path containing probing policy and assemblies to probe.</span></span>

`--depsfile`

<span data-ttu-id="c68b8-121">Pfad zu einer *deps.json*-Datei.</span><span class="sxs-lookup"><span data-stu-id="c68b8-121">Path to a *deps.json* file.</span></span>

<span data-ttu-id="c68b8-122">Eine *deps.json*-Datei enthält eine Liste mit Abhängigkeiten, Kompilierungsabhängigkeiten und Versionsinformationen, die verwendet werden, um Assemblykonflikte zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="c68b8-122">A *deps.json* file contains a list of dependencies, compilation dependencies, and version information used to address assembly conflicts.</span></span> <span data-ttu-id="c68b8-123">Weitere Informationen zu dieser Datei finden Sie auf GitHub unter [Laufzeitkonfigurationsdateien](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="c68b8-123">For more information about this file, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) on GitHub.</span></span>

`-d|--diagnostics`

<span data-ttu-id="c68b8-124">Ermöglicht die diagnostische Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="c68b8-124">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="c68b8-125">Version der .NET Core-Runtime, die zum Ausführen der Anwendung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c68b8-125">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="c68b8-126">Gibt Dokumentation für einen bestimmten Befehl aus, z.B. `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="c68b8-126">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="c68b8-127">`dotnet --help` gibt eine Liste der verfügbaren Befehle zurück.</span><span class="sxs-lookup"><span data-stu-id="c68b8-127">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="c68b8-128">Gibt ausführliche Informationen über eine .NET Core-Installation und die Computerumgebung aus, z.B. das aktuelle Betriebssystem und den Commit-SHA für die .NET Core-Version.</span><span class="sxs-lookup"><span data-stu-id="c68b8-128">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--list-runtimes`

<span data-ttu-id="c68b8-129">Zeigt die installierten .NET Core-Runtimes an.</span><span class="sxs-lookup"><span data-stu-id="c68b8-129">Displays the installed .NET Core runtimes.</span></span>

`--list-sdks`

<span data-ttu-id="c68b8-130">Zeigt die installierten .NET Core-SDKs an.</span><span class="sxs-lookup"><span data-stu-id="c68b8-130">Displays the installed .NET Core SDKs.</span></span>

`--roll-forward-on-no-candidate-fx <N>`

<span data-ttu-id="c68b8-131">Definiert ein Verhalten, wenn das erforderliche freigegebene Framework nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="c68b8-131">Defines behavior when the required shared framework is not available.</span></span> <span data-ttu-id="c68b8-132">`N` kann Folgendes sein:</span><span class="sxs-lookup"><span data-stu-id="c68b8-132">`N` can be:</span></span>

- <span data-ttu-id="c68b8-133">`0` - Das Ausführen von Rollforward ist auch für die Nebenversion deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="c68b8-133">`0` - Disable even minor version roll forward.</span></span>
- <span data-ttu-id="c68b8-134">`1` - Rollforward wird in der Nebenversion, nicht aber in der Hauptversion, ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c68b8-134">`1` - Roll forward on minor version, but not on major version.</span></span> <span data-ttu-id="c68b8-135">Dies ist das Standardverhalten.</span><span class="sxs-lookup"><span data-stu-id="c68b8-135">This is the default behavior.</span></span>
- <span data-ttu-id="c68b8-136">`2` - Rollforward wird in Neben- und Hauptversionen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c68b8-136">`2` - Roll forward on minor and major versions.</span></span>

 <span data-ttu-id="c68b8-137">Weitere Informationen finden Sie unter [Rollforward](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="c68b8-137">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`--runtimeconfig`

<span data-ttu-id="c68b8-138">Der Pfad zu einer *runtimeconfig.json*-Datei.</span><span class="sxs-lookup"><span data-stu-id="c68b8-138">Path to a *runtimeconfig.json* file.</span></span>

<span data-ttu-id="c68b8-139">Eine *runtimeconfig.json*-Datei ist eine Konfigurationsdatei mit Einstellungen für die Runtime.</span><span class="sxs-lookup"><span data-stu-id="c68b8-139">A *runtimeconfig.json* file is a configuration file containing run-time settings.</span></span> <span data-ttu-id="c68b8-140">Weitere Informationen finden Sie unter [Konfigurationseinstellungen für die .NET Core-Runtime](../run-time-config/index.md#runtimeconfigjson).</span><span class="sxs-lookup"><span data-stu-id="c68b8-140">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="c68b8-141">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="c68b8-141">Sets the verbosity level of the command.</span></span> <span data-ttu-id="c68b8-142">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="c68b8-142">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="c68b8-143">Nicht in jedem Befehl unterstützt. Auf der Seite der einzelnen Befehle finden Sie heraus, ob diese Option verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="c68b8-143">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="c68b8-144">Druckt die Version des verwendeten .NET Core-SDK aus.</span><span class="sxs-lookup"><span data-stu-id="c68b8-144">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-20"></a>[<span data-ttu-id="c68b8-145">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="c68b8-145">.NET Core 2.0</span></span>](#tab/netcore20)

`--additional-deps <PATH>`

<span data-ttu-id="c68b8-146">Pfad zu einer zusätzlichen *.deps.json*-Datei.</span><span class="sxs-lookup"><span data-stu-id="c68b8-146">Path to an additional *.deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="c68b8-147">Pfad, der die Suchrichtlinie und die zu suchenden Assemblys enthält.</span><span class="sxs-lookup"><span data-stu-id="c68b8-147">Path containing probing policy and assemblies to probe.</span></span>

`--depsfile`

<span data-ttu-id="c68b8-148">Pfad zu einer *deps.json*-Datei.</span><span class="sxs-lookup"><span data-stu-id="c68b8-148">Path to a *deps.json* file.</span></span>

<span data-ttu-id="c68b8-149">Eine *deps.json*-Datei enthält eine Liste mit (Kompilierungs-)Abhängigkeiten und Versionsinformationen, die verwendet werden, um Assemblykonflikte zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="c68b8-149">A *deps.json* file contains a list of dependencies, compilation dependencies and version information used to address assembly conflicts.</span></span> <span data-ttu-id="c68b8-150">Weitere Informationen zu dieser Datei finden Sie auf [GitHub unter Laufzeitkonfigurationsdateien](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="c68b8-150">For more details on this file, see [Runtime Configuration Files on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

`-d|--diagnostics`

<span data-ttu-id="c68b8-151">Ermöglicht die diagnostische Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="c68b8-151">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="c68b8-152">Version der .NET Core-Runtime, die zum Ausführen der Anwendung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c68b8-152">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="c68b8-153">Gibt Dokumentation für einen bestimmten Befehl aus, z.B. `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="c68b8-153">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="c68b8-154">`dotnet --help` gibt eine Liste der verfügbaren Befehle zurück.</span><span class="sxs-lookup"><span data-stu-id="c68b8-154">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="c68b8-155">Gibt ausführliche Informationen über eine .NET Core-Installation und die Computerumgebung aus, z.B. das aktuelle Betriebssystem und den Commit-SHA für die .NET Core-Version.</span><span class="sxs-lookup"><span data-stu-id="c68b8-155">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="c68b8-156">Deaktiviert Rollforward der Nebenversion, wenn `0` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="c68b8-156">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="c68b8-157">Weitere Informationen finden Sie unter [Rollforward](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="c68b8-157">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`--runtimeconfig`

<span data-ttu-id="c68b8-158">Der Pfad zu einer *runtimeconfig.json*-Datei.</span><span class="sxs-lookup"><span data-stu-id="c68b8-158">Path to a *runtimeconfig.json* file.</span></span>

<span data-ttu-id="c68b8-159">Eine *runtimeconfig.json*-Datei ist eine Konfigurationsdatei mit Einstellungen für die Runtime.</span><span class="sxs-lookup"><span data-stu-id="c68b8-159">A *runtimeconfig.json* file is a configuration file containing run-time settings.</span></span> <span data-ttu-id="c68b8-160">Weitere Informationen finden Sie unter [Konfigurationseinstellungen für die .NET Core-Runtime](../run-time-config/index.md#runtimeconfigjson).</span><span class="sxs-lookup"><span data-stu-id="c68b8-160">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="c68b8-161">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="c68b8-161">Sets the verbosity level of the command.</span></span> <span data-ttu-id="c68b8-162">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="c68b8-162">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="c68b8-163">Nicht in jedem Befehl unterstützt. Auf der Seite der einzelnen Befehle finden Sie heraus, ob diese Option verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="c68b8-163">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="c68b8-164">Druckt die Version des verwendeten .NET Core-SDK aus.</span><span class="sxs-lookup"><span data-stu-id="c68b8-164">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1x"></a>[<span data-ttu-id="c68b8-165">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c68b8-165">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="c68b8-166">Pfad, der die Suchrichtlinie und die zu suchenden Assemblys enthält.</span><span class="sxs-lookup"><span data-stu-id="c68b8-166">Path containing probing policy and assemblies to probe.</span></span>

`--depsfile`

<span data-ttu-id="c68b8-167">Pfad zu einer *deps.json*-Datei.</span><span class="sxs-lookup"><span data-stu-id="c68b8-167">Path to a *deps.json* file.</span></span>

<span data-ttu-id="c68b8-168">Eine *deps.json*-Datei enthält eine Liste mit (Kompilierungs-)Abhängigkeiten und Versionsinformationen, die verwendet werden, um Assemblykonflikte zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="c68b8-168">A *deps.json* file contains a list of dependencies, compilation dependencies and version information used to address assembly conflicts.</span></span> <span data-ttu-id="c68b8-169">Weitere Informationen zu dieser Datei finden Sie auf [GitHub unter Laufzeitkonfigurationsdateien](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="c68b8-169">For more details on this file, see [Runtime Configuration Files on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

`-d|--diagnostics`

<span data-ttu-id="c68b8-170">Ermöglicht die diagnostische Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="c68b8-170">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="c68b8-171">Version der .NET Core-Runtime, die zum Ausführen der Anwendung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c68b8-171">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="c68b8-172">Gibt Dokumentation für einen bestimmten Befehl aus, z.B. `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="c68b8-172">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="c68b8-173">`dotnet --help` gibt eine Liste der verfügbaren Befehle zurück.</span><span class="sxs-lookup"><span data-stu-id="c68b8-173">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="c68b8-174">Gibt ausführliche Informationen über eine .NET Core-Installation und die Computerumgebung aus, z.B. das aktuelle Betriebssystem und den Commit-SHA für die .NET Core-Version.</span><span class="sxs-lookup"><span data-stu-id="c68b8-174">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--runtimeconfig`

<span data-ttu-id="c68b8-175">Der Pfad zu einer *runtimeconfig.json*-Datei.</span><span class="sxs-lookup"><span data-stu-id="c68b8-175">Path to a *runtimeconfig.json* file.</span></span>

<span data-ttu-id="c68b8-176">Eine *runtimeconfig.json*-Datei ist eine Konfigurationsdatei mit Einstellungen für die Runtime.</span><span class="sxs-lookup"><span data-stu-id="c68b8-176">A *runtimeconfig.json* file is a configuration file containing run-time settings.</span></span> <span data-ttu-id="c68b8-177">Weitere Informationen finden Sie unter [Konfigurationseinstellungen für die .NET Core-Runtime](../run-time-config/index.md#runtimeconfigjson).</span><span class="sxs-lookup"><span data-stu-id="c68b8-177">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="c68b8-178">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="c68b8-178">Sets the verbosity level of the command.</span></span> <span data-ttu-id="c68b8-179">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="c68b8-179">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="c68b8-180">Nicht in jedem Befehl unterstützt. Auf der Seite der einzelnen Befehle finden Sie heraus, ob diese Option verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="c68b8-180">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="c68b8-181">Druckt die Version des verwendeten .NET Core-SDK aus.</span><span class="sxs-lookup"><span data-stu-id="c68b8-181">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="c68b8-182">dotnet-Befehle</span><span class="sxs-lookup"><span data-stu-id="c68b8-182">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="c68b8-183">Allgemein</span><span class="sxs-lookup"><span data-stu-id="c68b8-183">General</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="c68b8-184">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c68b8-184">.NET Core 2.1</span></span>](#tab/netcore21)

| <span data-ttu-id="c68b8-185">Befehl</span><span class="sxs-lookup"><span data-stu-id="c68b8-185">Command</span></span>                                       | <span data-ttu-id="c68b8-186">Funktion</span><span class="sxs-lookup"><span data-stu-id="c68b8-186">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="c68b8-187">dotnet build</span><span class="sxs-lookup"><span data-stu-id="c68b8-187">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="c68b8-188">Erstellt eine .NET Core-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="c68b8-188">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="c68b8-189">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="c68b8-189">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="c68b8-190">Interagiert mit Servern, die von einem Build gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="c68b8-190">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="c68b8-191">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="c68b8-191">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="c68b8-192">Bereinigen von Buildausgaben.</span><span class="sxs-lookup"><span data-stu-id="c68b8-192">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="c68b8-193">dotnet help</span><span class="sxs-lookup"><span data-stu-id="c68b8-193">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="c68b8-194">Zeigt eine ausführlichere Onlinedokumentation für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="c68b8-194">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="c68b8-195">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="c68b8-195">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="c68b8-196">Migriert ein gültiges Preview 2-Projekt in ein .NET Core SDK 1.0-Projekt.</span><span class="sxs-lookup"><span data-stu-id="c68b8-196">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="c68b8-197">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="c68b8-197">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="c68b8-198">Ermöglicht den Zugriff auf die MSBuild-Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="c68b8-198">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="c68b8-199">dotnet new</span><span class="sxs-lookup"><span data-stu-id="c68b8-199">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="c68b8-200">Initialisiert ein C#- oder F#-Projekt für eine bestimmte Vorlage.</span><span class="sxs-lookup"><span data-stu-id="c68b8-200">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="c68b8-201">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="c68b8-201">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="c68b8-202">Erstellt ein NuGet-Paket aus Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="c68b8-202">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="c68b8-203">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="c68b8-203">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="c68b8-204">Veröffentlicht eine .NET Framework-abhängige oder eigenständige Anwendung.</span><span class="sxs-lookup"><span data-stu-id="c68b8-204">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="c68b8-205">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="c68b8-205">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="c68b8-206">Stellt die Abhängigkeiten für eine bestimmte Anwendung wieder her.</span><span class="sxs-lookup"><span data-stu-id="c68b8-206">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="c68b8-207">dotnet run</span><span class="sxs-lookup"><span data-stu-id="c68b8-207">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="c68b8-208">Führt die Anwendung aus der Quelle aus.</span><span class="sxs-lookup"><span data-stu-id="c68b8-208">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="c68b8-209">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="c68b8-209">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="c68b8-210">Optionen zum Hinzufügen, Entfernen und Listen von Projekten in einer Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="c68b8-210">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="c68b8-211">dotnet store</span><span class="sxs-lookup"><span data-stu-id="c68b8-211">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="c68b8-212">Speichert Assemblys im Laufzeitpaketspeicher.</span><span class="sxs-lookup"><span data-stu-id="c68b8-212">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="c68b8-213">dotnet test</span><span class="sxs-lookup"><span data-stu-id="c68b8-213">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="c68b8-214">Führt Tests mit einem Test Runner aus.</span><span class="sxs-lookup"><span data-stu-id="c68b8-214">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-20"></a>[<span data-ttu-id="c68b8-215">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="c68b8-215">.NET Core 2.0</span></span>](#tab/netcore20)

| <span data-ttu-id="c68b8-216">Befehl</span><span class="sxs-lookup"><span data-stu-id="c68b8-216">Command</span></span>                             | <span data-ttu-id="c68b8-217">Funktion</span><span class="sxs-lookup"><span data-stu-id="c68b8-217">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="c68b8-218">dotnet build</span><span class="sxs-lookup"><span data-stu-id="c68b8-218">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="c68b8-219">Erstellt eine .NET Core-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="c68b8-219">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="c68b8-220">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="c68b8-220">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="c68b8-221">Bereinigen von Buildausgaben.</span><span class="sxs-lookup"><span data-stu-id="c68b8-221">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="c68b8-222">dotnet help</span><span class="sxs-lookup"><span data-stu-id="c68b8-222">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="c68b8-223">Zeigt eine ausführlichere Onlinedokumentation für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="c68b8-223">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="c68b8-224">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="c68b8-224">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="c68b8-225">Migriert ein gültiges Preview 2-Projekt in ein .NET Core SDK 1.0-Projekt.</span><span class="sxs-lookup"><span data-stu-id="c68b8-225">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="c68b8-226">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="c68b8-226">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="c68b8-227">Ermöglicht den Zugriff auf die MSBuild-Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="c68b8-227">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="c68b8-228">dotnet new</span><span class="sxs-lookup"><span data-stu-id="c68b8-228">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="c68b8-229">Initialisiert ein C#- oder F#-Projekt für eine bestimmte Vorlage.</span><span class="sxs-lookup"><span data-stu-id="c68b8-229">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="c68b8-230">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="c68b8-230">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="c68b8-231">Erstellt ein NuGet-Paket aus Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="c68b8-231">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="c68b8-232">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="c68b8-232">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="c68b8-233">Veröffentlicht eine .NET Framework-abhängige oder eigenständige Anwendung.</span><span class="sxs-lookup"><span data-stu-id="c68b8-233">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="c68b8-234">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="c68b8-234">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="c68b8-235">Stellt die Abhängigkeiten für eine bestimmte Anwendung wieder her.</span><span class="sxs-lookup"><span data-stu-id="c68b8-235">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="c68b8-236">dotnet run</span><span class="sxs-lookup"><span data-stu-id="c68b8-236">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="c68b8-237">Führt die Anwendung aus der Quelle aus.</span><span class="sxs-lookup"><span data-stu-id="c68b8-237">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="c68b8-238">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="c68b8-238">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="c68b8-239">Optionen zum Hinzufügen, Entfernen und Listen von Projekten in einer Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="c68b8-239">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="c68b8-240">dotnet store</span><span class="sxs-lookup"><span data-stu-id="c68b8-240">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="c68b8-241">Speichert Assemblys im Laufzeitpaketspeicher.</span><span class="sxs-lookup"><span data-stu-id="c68b8-241">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="c68b8-242">dotnet test</span><span class="sxs-lookup"><span data-stu-id="c68b8-242">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="c68b8-243">Führt Tests mit einem Test Runner aus.</span><span class="sxs-lookup"><span data-stu-id="c68b8-243">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1x"></a>[<span data-ttu-id="c68b8-244">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c68b8-244">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="c68b8-245">Befehl</span><span class="sxs-lookup"><span data-stu-id="c68b8-245">Command</span></span>                             | <span data-ttu-id="c68b8-246">Funktion</span><span class="sxs-lookup"><span data-stu-id="c68b8-246">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="c68b8-247">dotnet build</span><span class="sxs-lookup"><span data-stu-id="c68b8-247">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="c68b8-248">Erstellt eine .NET Core-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="c68b8-248">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="c68b8-249">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="c68b8-249">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="c68b8-250">Bereinigen von Buildausgaben.</span><span class="sxs-lookup"><span data-stu-id="c68b8-250">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="c68b8-251">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="c68b8-251">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="c68b8-252">Migriert ein gültiges Preview 2-Projekt in ein .NET Core SDK 1.0-Projekt.</span><span class="sxs-lookup"><span data-stu-id="c68b8-252">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="c68b8-253">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="c68b8-253">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="c68b8-254">Ermöglicht den Zugriff auf die MSBuild-Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="c68b8-254">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="c68b8-255">dotnet new</span><span class="sxs-lookup"><span data-stu-id="c68b8-255">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="c68b8-256">Initialisiert ein C#- oder F#-Projekt für eine bestimmte Vorlage.</span><span class="sxs-lookup"><span data-stu-id="c68b8-256">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="c68b8-257">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="c68b8-257">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="c68b8-258">Erstellt ein NuGet-Paket aus Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="c68b8-258">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="c68b8-259">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="c68b8-259">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="c68b8-260">Veröffentlicht eine .NET Framework-abhängige oder eigenständige Anwendung.</span><span class="sxs-lookup"><span data-stu-id="c68b8-260">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="c68b8-261">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="c68b8-261">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="c68b8-262">Stellt die Abhängigkeiten für eine bestimmte Anwendung wieder her.</span><span class="sxs-lookup"><span data-stu-id="c68b8-262">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="c68b8-263">dotnet run</span><span class="sxs-lookup"><span data-stu-id="c68b8-263">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="c68b8-264">Führt die Anwendung aus der Quelle aus.</span><span class="sxs-lookup"><span data-stu-id="c68b8-264">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="c68b8-265">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="c68b8-265">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="c68b8-266">Optionen zum Hinzufügen, Entfernen und Listen von Projekten in einer Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="c68b8-266">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="c68b8-267">dotnet test</span><span class="sxs-lookup"><span data-stu-id="c68b8-267">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="c68b8-268">Führt Tests mit einem Test Runner aus.</span><span class="sxs-lookup"><span data-stu-id="c68b8-268">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="c68b8-269">Projektverweise</span><span class="sxs-lookup"><span data-stu-id="c68b8-269">Project references</span></span>

<span data-ttu-id="c68b8-270">Befehl</span><span class="sxs-lookup"><span data-stu-id="c68b8-270">Command</span></span> | <span data-ttu-id="c68b8-271">Funktion</span><span class="sxs-lookup"><span data-stu-id="c68b8-271">Function</span></span>
--- | ---
[<span data-ttu-id="c68b8-272">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="c68b8-272">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="c68b8-273">Fügt einen Projektverweis hinzu.</span><span class="sxs-lookup"><span data-stu-id="c68b8-273">Adds a project reference.</span></span>
[<span data-ttu-id="c68b8-274">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="c68b8-274">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="c68b8-275">Listet Projektverweise auf.</span><span class="sxs-lookup"><span data-stu-id="c68b8-275">Lists project references.</span></span>
[<span data-ttu-id="c68b8-276">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="c68b8-276">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="c68b8-277">Entfernt einen Projektverweis.</span><span class="sxs-lookup"><span data-stu-id="c68b8-277">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="c68b8-278">NuGet-Pakete</span><span class="sxs-lookup"><span data-stu-id="c68b8-278">NuGet packages</span></span>

<span data-ttu-id="c68b8-279">Befehl</span><span class="sxs-lookup"><span data-stu-id="c68b8-279">Command</span></span> | <span data-ttu-id="c68b8-280">Funktion</span><span class="sxs-lookup"><span data-stu-id="c68b8-280">Function</span></span>
--- | ---
[<span data-ttu-id="c68b8-281">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="c68b8-281">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="c68b8-282">Fügt ein NuGet-Paket hinzu.</span><span class="sxs-lookup"><span data-stu-id="c68b8-282">Adds a NuGet package.</span></span>
[<span data-ttu-id="c68b8-283">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="c68b8-283">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="c68b8-284">Entfernt ein NuGet-Paket.</span><span class="sxs-lookup"><span data-stu-id="c68b8-284">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="c68b8-285">NuGet-Befehle</span><span class="sxs-lookup"><span data-stu-id="c68b8-285">NuGet commands</span></span>

<span data-ttu-id="c68b8-286">Befehl</span><span class="sxs-lookup"><span data-stu-id="c68b8-286">Command</span></span> | <span data-ttu-id="c68b8-287">Funktion</span><span class="sxs-lookup"><span data-stu-id="c68b8-287">Function</span></span>
--- | ---
[<span data-ttu-id="c68b8-288">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="c68b8-288">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="c68b8-289">Löscht ein Paket vom Server oder hebt dessen Auflistung auf.</span><span class="sxs-lookup"><span data-stu-id="c68b8-289">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="c68b8-290">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="c68b8-290">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="c68b8-291">Löscht lokale NuGet-Ressourcen, z.B. den http-Anforderungscache, den temporären Cache oder den Ordner mit globalen Paketen auf dem Computer, oder listet diese Ressourcen auf.</span><span class="sxs-lookup"><span data-stu-id="c68b8-291">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="c68b8-292">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="c68b8-292">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="c68b8-293">Überträgt ein Paket auf den Server und veröffentlicht es.</span><span class="sxs-lookup"><span data-stu-id="c68b8-293">Pushes a package to the server and publishes it.</span></span>

### <a name="global-tool-path-and-local-tools-commands"></a><span data-ttu-id="c68b8-294">Befehle für globale, Toolpfad- und lokale Tools</span><span class="sxs-lookup"><span data-stu-id="c68b8-294">Global, tool-path, and local tools commands</span></span>

<span data-ttu-id="c68b8-295">Tools sind Konsolenanwendungen, die über NuGet-Pakete installiert und über die Eingabeaufforderung aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c68b8-295">Tools are console applications that are installed from NuGet packages and are invoked from the command prompt.</span></span> <span data-ttu-id="c68b8-296">Sie können Tools selbst schreiben oder Drittanbietertools installieren.</span><span class="sxs-lookup"><span data-stu-id="c68b8-296">You can write tools yourself or install tools written by third parties.</span></span> <span data-ttu-id="c68b8-297">Tools werden auch als globale Tools, Toolpfadtools und lokale Tools bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="c68b8-297">Tools are also known as global tools, tool-path tools, and local tools.</span></span> <span data-ttu-id="c68b8-298">Weitere Informationen finden Sie unter [Übersicht über .NET Core-Tools](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c68b8-298">For more information, see [.NET Core tools overview](global-tools.md).</span></span> <span data-ttu-id="c68b8-299">Globale und Toolpfadtools sind ab .NET Core SDK 2.1 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c68b8-299">Global and tool-path tools are available starting with .NET Core SDK 2.1.</span></span> <span data-ttu-id="c68b8-300">Lokale Tools sind ab .NET Core SDK 3.0 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c68b8-300">Local tools are available starting with .NET Core SDK 3.0.</span></span>

<span data-ttu-id="c68b8-301">Befehl</span><span class="sxs-lookup"><span data-stu-id="c68b8-301">Command</span></span> | <span data-ttu-id="c68b8-302">Funktion</span><span class="sxs-lookup"><span data-stu-id="c68b8-302">Function</span></span>
--- | ---
[<span data-ttu-id="c68b8-303">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="c68b8-303">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="c68b8-304">Installiert ein Tool auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="c68b8-304">Installs a tool on your machine.</span></span>
[<span data-ttu-id="c68b8-305">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="c68b8-305">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="c68b8-306">Listet alle globalen, Toolpfad- und lokalen Tools auf, die derzeit auf Ihrem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="c68b8-306">Lists all global, tool-path, or local tools currently installed on your machine.</span></span>
[<span data-ttu-id="c68b8-307">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="c68b8-307">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="c68b8-308">Deinstalliert ein Tool von Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="c68b8-308">Uninstalls a tool from your machine.</span></span>
[<span data-ttu-id="c68b8-309">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="c68b8-309">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="c68b8-310">Aktualisiert ein Tool, das auf Ihrem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="c68b8-310">Updates a tool that is installed on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="c68b8-311">Weitere Tools</span><span class="sxs-lookup"><span data-stu-id="c68b8-311">Additional tools</span></span>

<span data-ttu-id="c68b8-312">Beginnend mit .NET Core SDK 2.1.300 steht eine Reihe von Tools, die nur auf Projektbasis unter Verwendung von `DotnetCliToolReference` verfügbar waren, jetzt als Teil des .NET Core SDK zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="c68b8-312">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="c68b8-313">Diese Tools werden in der folgenden Tabelle aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="c68b8-313">These tools are listed in the following table:</span></span>

| <span data-ttu-id="c68b8-314">Tool</span><span class="sxs-lookup"><span data-stu-id="c68b8-314">Tool</span></span>                                              | <span data-ttu-id="c68b8-315">Funktion</span><span class="sxs-lookup"><span data-stu-id="c68b8-315">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="c68b8-316">dev-certs</span><span class="sxs-lookup"><span data-stu-id="c68b8-316">dev-certs</span></span>                                         | <span data-ttu-id="c68b8-317">Erstellt und verwaltet Entwicklungszertifikate.</span><span class="sxs-lookup"><span data-stu-id="c68b8-317">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="c68b8-318">ef</span><span class="sxs-lookup"><span data-stu-id="c68b8-318">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="c68b8-319">Entity Framework Core-Befehlszeilentools.</span><span class="sxs-lookup"><span data-stu-id="c68b8-319">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="c68b8-320">sql-cache</span><span class="sxs-lookup"><span data-stu-id="c68b8-320">sql-cache</span></span>                                         | <span data-ttu-id="c68b8-321">SQL Server-Cache-Befehlszeilentools.</span><span class="sxs-lookup"><span data-stu-id="c68b8-321">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="c68b8-322">user-secrets</span><span class="sxs-lookup"><span data-stu-id="c68b8-322">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="c68b8-323">Verwaltet die Entwicklung von Benutzergeheimnissen.</span><span class="sxs-lookup"><span data-stu-id="c68b8-323">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="c68b8-324">watch</span><span class="sxs-lookup"><span data-stu-id="c68b8-324">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="c68b8-325">Startet einen Datei-Watcher, der einen Befehl ausführt, wenn sich Dateien ändern.</span><span class="sxs-lookup"><span data-stu-id="c68b8-325">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="c68b8-326">Geben Sie `dotnet <tool-name> --help` ein, um weitere Informationen zu den einzelnen Tools zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="c68b8-326">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="c68b8-327">Beispiele</span><span class="sxs-lookup"><span data-stu-id="c68b8-327">Examples</span></span>

<span data-ttu-id="c68b8-328">Erstellt eine neue .NET Core-Konsolenanwendung:</span><span class="sxs-lookup"><span data-stu-id="c68b8-328">Creates a new .NET Core console application:</span></span>

`dotnet new console`

<span data-ttu-id="c68b8-329">Wiederherstellen von Abhängigkeiten für eine bestimmte Anwendung:</span><span class="sxs-lookup"><span data-stu-id="c68b8-329">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="c68b8-330">Erstellen eines Projekts und seiner Abhängigkeiten in einem vorgegebenen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="c68b8-330">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="c68b8-331">Führen Sie eine Anwendungs-DLL aus, z.B. `myapp.dll`:</span><span class="sxs-lookup"><span data-stu-id="c68b8-331">Run an application DLL, such as `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="c68b8-332">Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="c68b8-332">Environment variables</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="c68b8-333">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c68b8-333">.NET Core 2.1</span></span>](#tab/netcore21)

`DOTNET_PACKAGES`

<span data-ttu-id="c68b8-334">Der Ordner für globale Pakete.</span><span class="sxs-lookup"><span data-stu-id="c68b8-334">The global packages folder.</span></span> <span data-ttu-id="c68b8-335">Wenn er nicht festgelegt wird, wird standardmäßig `~/.nuget/packages` unter Unix oder `%userprofile%\.nuget\packages` unter Windows verwendet.</span><span class="sxs-lookup"><span data-stu-id="c68b8-335">If not set, it defaults to `~/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="c68b8-336">Gibt den Speicherort des Wartungsindex an, der vom freigegebenen Host verwendet wird, wenn die Laufzeit geladen wird.</span><span class="sxs-lookup"><span data-stu-id="c68b8-336">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="c68b8-337">Gibt an, ob Daten zur Nutzung von .NET Core-Tools gesammelt und an Microsoft gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="c68b8-337">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="c68b8-338">Legen Sie `true` fest, um die Telemetriefunktion zu deaktivieren (Wert `true`, `1` oder `yes` wird akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="c68b8-338">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="c68b8-339">Legen Sie andernfalls `false` fest, um die Telemetriefunktionen zu aktivieren (Wert `false`, `0` oder `no` wird akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="c68b8-339">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="c68b8-340">Ohne Festlegung ist der Standardwert `false`, und die Telemetriefunktion ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="c68b8-340">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="c68b8-341">Gibt an, ob die .NET Core-Runtime, das freigegebene Framework oder das SDK vom globalen Speicherort aus aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="c68b8-341">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="c68b8-342">Wenn nicht, ist der Standardwert `true`.</span><span class="sxs-lookup"><span data-stu-id="c68b8-342">If not set, it defaults to `true`.</span></span> <span data-ttu-id="c68b8-343">Wenn der Wert auf `false` festgelegt wird, wird nicht vom globalen Speicherort aus aufgelöst und es gibt isolierte .NET Core-Installationen (die Werte `0` oder `false` werden akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="c68b8-343">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="c68b8-344">Weitere Informationen zu Lookup mit mehreren Ebenen finden Sie unter [Multi-level SharedFX lookup (SharedFX-Lookup mit mehreren Ebenen)](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span><span class="sxs-lookup"><span data-stu-id="c68b8-344">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`

<span data-ttu-id="c68b8-345">Deaktiviert Rollforward der Nebenversion, wenn `0` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="c68b8-345">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="c68b8-346">Weitere Informationen finden Sie unter [Rollforward](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="c68b8-346">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

# <a name="net-core-20"></a>[<span data-ttu-id="c68b8-347">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="c68b8-347">.NET Core 2.0</span></span>](#tab/netcore20)

`DOTNET_PACKAGES`

<span data-ttu-id="c68b8-348">Der Cache des primären Pakets.</span><span class="sxs-lookup"><span data-stu-id="c68b8-348">The primary package cache.</span></span> <span data-ttu-id="c68b8-349">Wenn er nicht festgelegt wird, wird standardmäßig `$HOME/.nuget/packages` unter Unix oder `%userprofile%\.nuget\packages` unter Windows verwendet.</span><span class="sxs-lookup"><span data-stu-id="c68b8-349">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="c68b8-350">Gibt den Speicherort des Wartungsindex an, der vom freigegebenen Host verwendet wird, wenn die Laufzeit geladen wird.</span><span class="sxs-lookup"><span data-stu-id="c68b8-350">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="c68b8-351">Gibt an, ob Daten zur Nutzung von .NET Core-Tools gesammelt und an Microsoft gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="c68b8-351">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="c68b8-352">Legen Sie `true` fest, um die Telemetriefunktion zu deaktivieren (Wert `true`, `1` oder `yes` wird akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="c68b8-352">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="c68b8-353">Legen Sie andernfalls `false` fest, um die Telemetriefunktionen zu aktivieren (Wert `false`, `0` oder `no` wird akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="c68b8-353">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="c68b8-354">Ohne Festlegung ist der Standardwert `false`, und die Telemetriefunktion ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="c68b8-354">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="c68b8-355">Gibt an, ob die .NET Core-Runtime, das freigegebene Framework oder das SDK vom globalen Speicherort aus aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="c68b8-355">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="c68b8-356">Wenn nicht, ist der Standardwert `true`.</span><span class="sxs-lookup"><span data-stu-id="c68b8-356">If not set, it defaults to `true`.</span></span> <span data-ttu-id="c68b8-357">Wenn der Wert auf `false` festgelegt wird, wird nicht vom globalen Speicherort aus aufgelöst und es gibt isolierte .NET Core-Installationen (die Werte `0` oder `false` werden akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="c68b8-357">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="c68b8-358">Weitere Informationen zu Lookup mit mehreren Ebenen finden Sie unter [Multi-level SharedFX lookup (SharedFX-Lookup mit mehreren Ebenen)](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span><span class="sxs-lookup"><span data-stu-id="c68b8-358">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

# <a name="net-core-1x"></a>[<span data-ttu-id="c68b8-359">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c68b8-359">.NET Core 1.x</span></span>](#tab/netcore1x)

`DOTNET_PACKAGES`

<span data-ttu-id="c68b8-360">Der Cache des primären Pakets.</span><span class="sxs-lookup"><span data-stu-id="c68b8-360">The primary package cache.</span></span> <span data-ttu-id="c68b8-361">Wenn er nicht festgelegt wird, wird standardmäßig `$HOME/.nuget/packages` unter Unix oder `%userprofile%\.nuget\packages` unter Windows verwendet.</span><span class="sxs-lookup"><span data-stu-id="c68b8-361">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="c68b8-362">Gibt den Speicherort des Wartungsindex an, der vom freigegebenen Host verwendet wird, wenn die Laufzeit geladen wird.</span><span class="sxs-lookup"><span data-stu-id="c68b8-362">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="c68b8-363">Gibt an, ob Daten zur Nutzung von .NET Core-Tools gesammelt und an Microsoft gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="c68b8-363">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="c68b8-364">Legen Sie `true` fest, um die Telemetriefunktion zu deaktivieren (Wert `true`, `1` oder `yes` wird akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="c68b8-364">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="c68b8-365">Legen Sie andernfalls `false` fest, um die Telemetriefunktionen zu aktivieren (Wert `false`, `0` oder `no` wird akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="c68b8-365">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="c68b8-366">Ohne Festlegung ist der Standardwert `false`, und die Telemetriefunktion ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="c68b8-366">If not set, the default is `false` and the telemetry feature is active.</span></span>

---

## <a name="see-also"></a><span data-ttu-id="c68b8-367">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c68b8-367">See also</span></span>

- [<span data-ttu-id="c68b8-368">Laufzeitkonfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="c68b8-368">Runtime Configuration Files</span></span>](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)
- [<span data-ttu-id="c68b8-369">Konfigurationseinstellungen für die .NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="c68b8-369">.NET Core run-time configuration settings</span></span>](../run-time-config/index.md)
