---
title: Dotnet-Installationsskripts
description: Informationen zu Dotnet-Installationsskripts zur Installation von .NET Core CLI-Tools und freigegebener Laufzeit.
keywords: Dotnet-Installation, Dotnet-Installationsskripts, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 09/11/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: b64e7e6f-ffb4-4fc8-b43b-5731c89479c2
ms.openlocfilehash: 2f15f37016fe824d76b501e4793e0b28bbdbe167
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="dotnet-install-scripts-reference"></a><span data-ttu-id="b4312-104">Dotnet-Installationsskripts Verweis</span><span class="sxs-lookup"><span data-stu-id="b4312-104">dotnet-install scripts reference</span></span>

## <a name="name"></a><span data-ttu-id="b4312-105">Name</span><span class="sxs-lookup"><span data-stu-id="b4312-105">Name</span></span>

<span data-ttu-id="b4312-106">`dotnet-install.ps1` | `dotnet-install.sh`: Skript, mit dem die .NET Core-CLI-Tools und die freigegebene Laufzeit installiert werden.</span><span class="sxs-lookup"><span data-stu-id="b4312-106">`dotnet-install.ps1` | `dotnet-install.sh` - Script used to install the .NET Core CLI tools and the shared runtime.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b4312-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="b4312-107">Synopsis</span></span>

<span data-ttu-id="b4312-108">Windows:</span><span class="sxs-lookup"><span data-stu-id="b4312-108">Windows:</span></span>

`dotnet-install.ps1 [-Channel] [-Version] [-InstallDir] [-Architecture] [-SharedRuntime] [-DryRun] [-NoPath] [-AzureFeed] [-ProxyAddress] [--Verbose] [--Help]`

<span data-ttu-id="b4312-109">Mac OS/Linux:</span><span class="sxs-lookup"><span data-stu-id="b4312-109">macOS/Linux:</span></span>

`dotnet-install.sh [--channel] [--version] [--install-dir] [--architecture] [--shared-runtime] [--dry-run] [--no-path] [--azure-feed] [--verbose] [--help]`

## <a name="description"></a><span data-ttu-id="b4312-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4312-110">Description</span></span>

<span data-ttu-id="b4312-111">Die `dotnet-install`-Skripts werden verwendet, um eine Nicht-Administrator-Installation des .NET Core-SDK durchzuführen, die die .NET Core-CLI-Tools und die freigegebene Laufzeit enthält.</span><span class="sxs-lookup"><span data-stu-id="b4312-111">The `dotnet-install` scripts are used to perform a non-admin installation of the .NET Core SDK, which includes the .NET Core CLI tools and the shared runtime.</span></span>

<span data-ttu-id="b4312-112">Sie sollten die stabile Version verwenden, die auf der [.NET Core-Hauptwebsite](https://dot.net) gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="b4312-112">We recommend that you use the stable version that is hosted on [.NET Core main website](https://dot.net).</span></span> <span data-ttu-id="b4312-113">Die direkten Pfade zu den Skripts sind:</span><span class="sxs-lookup"><span data-stu-id="b4312-113">The direct paths to the scripts are:</span></span>

* <span data-ttu-id="b4312-114">https://dot.net/v1/dotnet-install.sh (bash, UNIX)</span><span class="sxs-lookup"><span data-stu-id="b4312-114">https://dot.net/v1/dotnet-install.sh (bash, UNIX)</span></span>
* <span data-ttu-id="b4312-115">https://dot.net/v1/dotnet-install.ps1 (Powershell, Windows)</span><span class="sxs-lookup"><span data-stu-id="b4312-115">https://dot.net/v1/dotnet-install.ps1 (Powershell, Windows)</span></span>

<span data-ttu-id="b4312-116">Diese Skripts sind vor allem in Szenarios für die Automatisierung und Nicht-Administrator-Installationen nützlich.</span><span class="sxs-lookup"><span data-stu-id="b4312-116">The main usefulness of these scripts is in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="b4312-117">Es gibt zwei Skripts: Das eine ist ein PowerShell-Skript, das unter Windows funktioniert.</span><span class="sxs-lookup"><span data-stu-id="b4312-117">There are two scripts: One is a PowerShell script that works on Windows.</span></span> <span data-ttu-id="b4312-118">Das andere Skript ist ein Bash-Skript für Linux/macOS.</span><span class="sxs-lookup"><span data-stu-id="b4312-118">The other script is a bash script that works on Linux/macOS.</span></span> <span data-ttu-id="b4312-119">Beide Skripts weisen das gleiche Verhalten auf.</span><span class="sxs-lookup"><span data-stu-id="b4312-119">Both scripts have the same behavior.</span></span> <span data-ttu-id="b4312-120">Das Bash-Skript liest auch PowerShell-Schalter, sodass Sie PowerShell-Schalter mit dem Skript auf Linux/macOS-Systemen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="b4312-120">The bash script also reads PowerShell switches, so you can use PowerShell switches with the script on Linux/macOS systems.</span></span> 

<span data-ttu-id="b4312-121">Die Installationsskripts laden die ZIP/Tarball-Datei vom CLI-Build-Ablagespeicherort herunter und installieren sie entweder am Standardspeicherort oder an einem in `-InstallDir|--install-dir` angegebenen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="b4312-121">The installation scripts download the ZIP/tarball file from the CLI build drops and proceed to install it in either the default location or in a location specified by `-InstallDir|--install-dir`.</span></span> <span data-ttu-id="b4312-122">In der Standardeinstellung laden die Installationsskripts das SDK herunter und installieren es.</span><span class="sxs-lookup"><span data-stu-id="b4312-122">By default, the installation scripts download the SDK and install it.</span></span> <span data-ttu-id="b4312-123">Wenn Sie nur die freigegebene Laufzeit abrufen möchten, geben Sie das `--shared-runtime`-Argument an.</span><span class="sxs-lookup"><span data-stu-id="b4312-123">If you wish to only obtain the shared runtime, specify the `--shared-runtime` argument.</span></span> 

<span data-ttu-id="b4312-124">In der Standardeinstellung fügt das Skript den Installationsort dem $PATH für die aktuelle Sitzung hinzu.</span><span class="sxs-lookup"><span data-stu-id="b4312-124">By default, the script adds the install location to the $PATH for the current session.</span></span> <span data-ttu-id="b4312-125">Überschreiben Sie dieses Standardverhalten, indem sie das `--no-path`-Argument angeben.</span><span class="sxs-lookup"><span data-stu-id="b4312-125">Override this default behavior by specifying the `--no-path` argument.</span></span> 

<span data-ttu-id="b4312-126">Bevor Sie das Skript ausführen, installieren Sie die erforderlichen [Abhängigkeiten](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span><span class="sxs-lookup"><span data-stu-id="b4312-126">Before running the script, install the required [dependencies](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span></span>

<span data-ttu-id="b4312-127">Installieren Sie eine bestimmte Version mithilfe des Arguments `--version`.</span><span class="sxs-lookup"><span data-stu-id="b4312-127">You can install a specific version using the `--version` argument.</span></span> <span data-ttu-id="b4312-128">Die Version muss als dreiteilige Version (z.B. 1.0.0-13232) angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b4312-128">The version must be specified as a 3-part version (for example, 1.0.0-13232).</span></span> <span data-ttu-id="b4312-129">Wenn nicht angegeben, wird die `latest`-Version verwendet.</span><span class="sxs-lookup"><span data-stu-id="b4312-129">If omitted, it uses the `latest` version.</span></span>

## <a name="options"></a><span data-ttu-id="b4312-130">Optionen</span><span class="sxs-lookup"><span data-stu-id="b4312-130">Options</span></span>

`-Channel <CHANNEL>`

<span data-ttu-id="b4312-131">Gibt den Quellkanal für die Installation an.</span><span class="sxs-lookup"><span data-stu-id="b4312-131">Specifies the source channel for the installation.</span></span> <span data-ttu-id="b4312-132">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="b4312-132">The possible values are:</span></span>

- <span data-ttu-id="b4312-133">`Current`: Aktuelle Version</span><span class="sxs-lookup"><span data-stu-id="b4312-133">`Current` - Current release</span></span>
- <span data-ttu-id="b4312-134">`LTS`: Long Term Support-Kanal (aktuell unterstützte Versionen)</span><span class="sxs-lookup"><span data-stu-id="b4312-134">`LTS` - Long-Term Support channel (current supported release)</span></span>
- <span data-ttu-id="b4312-135">Zweiteilige Version im X.Y-Format, das eine bestimmte Version darstellt (z.B. `2.0` oder `1.0`)</span><span class="sxs-lookup"><span data-stu-id="b4312-135">Two-part version in X.Y format representing a specific release (for example, `2.0` or `1.0`)</span></span>
- <span data-ttu-id="b4312-136">Branchname [z.B. `release/2.0.0`, `release/2.0.0-preview2`, oder `master` für die neueste aus dem Branch `master` („topaktuelle“ nächtliche Versionen)]</span><span class="sxs-lookup"><span data-stu-id="b4312-136">Branch name [for example, `release/2.0.0`, `release/2.0.0-preview2`, or `master` for the latest from the `master` branch ("bleeding edge" nightly releases)]</span></span>

<span data-ttu-id="b4312-137">Der Standardwert ist `LTS`.</span><span class="sxs-lookup"><span data-stu-id="b4312-137">The default value is `LTS`.</span></span> <span data-ttu-id="b4312-138">Weitere Informationen zu .NET-Supportkanälen finden Sie unter dem Thema [.NET Core Support Lifecycle](https://www.microsoft.com/net/core/support).</span><span class="sxs-lookup"><span data-stu-id="b4312-138">For more information on .NET support channels, see the [.NET Core Support Lifecycle](https://www.microsoft.com/net/core/support) topic.</span></span>

`-Version <VERSION>`

<span data-ttu-id="b4312-139">Stellt eine bestimmte Buildversion dar.</span><span class="sxs-lookup"><span data-stu-id="b4312-139">Represents a specific build version.</span></span> <span data-ttu-id="b4312-140">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="b4312-140">The possible values are:</span></span>

- <span data-ttu-id="b4312-141">`latest` – der neueste Build auf dem Kanal (mit der `-Channel`-Option verwendet)</span><span class="sxs-lookup"><span data-stu-id="b4312-141">`latest` - Latest build on the channel (used with the `-Channel` option)</span></span>
- <span data-ttu-id="b4312-142">`coherent` – neuester kohärenter Build auf dem Kanal; verwendet die neueste stabile Paketkombination (mit Branch-Name-`-Channel`-Optionen verwendet)</span><span class="sxs-lookup"><span data-stu-id="b4312-142">`coherent` - Latest coherent build on the channel; uses the latest stable package combination (used with Branch name `-Channel` options)</span></span>
- <span data-ttu-id="b4312-143">Dreiteilige Version im X.Y.Z-Format, die eine bestimmte Buildversion darstellt; sie hat Vorrang vor der `-Channel`-Option.</span><span class="sxs-lookup"><span data-stu-id="b4312-143">Three-part version in X.Y.Z format representing a specific build version; supersedes the `-Channel` option.</span></span> <span data-ttu-id="b4312-144">Beispiel: `2.0.0-preview2-006120`</span><span class="sxs-lookup"><span data-stu-id="b4312-144">For example: `2.0.0-preview2-006120`</span></span>

<span data-ttu-id="b4312-145">Wenn kein Wert angegeben ist, hat `-Version` den Standardwert `latest`.</span><span class="sxs-lookup"><span data-stu-id="b4312-145">If omitted, `-Version` defaults to `latest`.</span></span>

`-InstallDir <DIRECTORY>`

<span data-ttu-id="b4312-146">Gibt den Installationspfad an.</span><span class="sxs-lookup"><span data-stu-id="b4312-146">Specifies the installation path.</span></span> <span data-ttu-id="b4312-147">Das Verzeichnis wird erstellt, wenn es nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="b4312-147">The directory is created if it doesn't exist.</span></span> <span data-ttu-id="b4312-148">Der Standardwert ist *%LocalAppData%\.dotnet*.</span><span class="sxs-lookup"><span data-stu-id="b4312-148">The default value is *%LocalAppData%\.dotnet*.</span></span> <span data-ttu-id="b4312-149">Beachten Sie, dass Binärdateien direkt im Verzeichnis platziert werden.</span><span class="sxs-lookup"><span data-stu-id="b4312-149">Note that binaries are placed directly in the directory.</span></span>

`-Architecture <ARCHITECTURE>`

<span data-ttu-id="b4312-150">Architektur der zu installierenden .NET Core-Binärdateien.</span><span class="sxs-lookup"><span data-stu-id="b4312-150">Architecture of the .NET Core binaries to install.</span></span> <span data-ttu-id="b4312-151">Mögliche Werte sind `auto`, `x64` und `x86`.</span><span class="sxs-lookup"><span data-stu-id="b4312-151">Possible values are `auto`, `x64`, and `x86`.</span></span> <span data-ttu-id="b4312-152">Der Standardwert ist `auto`, was die derzeit ausgeführte Betriebssystemarchitektur darstellt.</span><span class="sxs-lookup"><span data-stu-id="b4312-152">The default value is `auto`, which represents the currently running OS architecture.</span></span>

`-SharedRuntime`

<span data-ttu-id="b4312-153">Wenn festgelegt, beschränkt dieser Schalter die Installation auf die freigegebene Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="b4312-153">If set, this switch limits installation to the shared runtime.</span></span> <span data-ttu-id="b4312-154">Das gesamte SDK ist nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="b4312-154">The entire SDK isn't installed.</span></span>

`-DryRun`

<span data-ttu-id="b4312-155">Wenn festgelegt, führt das Skript die Installation nicht aus. Es zeigt stattdessen an, welche Befehlszeile verwendet werden soll, um die derzeit erforderliche Version der .NET Core-CLI konsistent zu installieren.</span><span class="sxs-lookup"><span data-stu-id="b4312-155">If set, the script won't perform the installation; but instead, it displays what command line to use to consistently install the currently requested version of the .NET Core CLI.</span></span> <span data-ttu-id="b4312-156">Wenn Sie z.B. Version `latest` angeben, wird eine Verbindung mit der bestimmten Version angezeigt, damit dieser Befehl deterministisch in einem Buildskript verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="b4312-156">For example if you specify version `latest`, it displays a link with the specific version so that this command can be used deterministically in a build script.</span></span> <span data-ttu-id="b4312-157">Außerdem wird der Speicherort der Binärdatei angezeigt, wenn Sie sie selbst installieren oder herunterladen möchten.</span><span class="sxs-lookup"><span data-stu-id="b4312-157">It also displays the binary's location if you prefer to install or download it yourself.</span></span>

`-NoPath`

<span data-ttu-id="b4312-158">Falls festgelegt, wird das Präfix/Installdir für die aktuelle Sitzung nicht in den Pfad exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="b4312-158">If set, the prefix/installdir are not exported to the path for the current session.</span></span> <span data-ttu-id="b4312-159">Standardmäßig wird das Skript den PFAD ändern. Somit werden die CLI-Tools sofort nach der Installation zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="b4312-159">By default, the script will modify the PATH, which makes the CLI tools available immediately after install.</span></span>

`-AzureFeed`

<span data-ttu-id="b4312-160">Gibt die URL für den Azure-Feed für den Installer an.</span><span class="sxs-lookup"><span data-stu-id="b4312-160">Specifies the URL for the Azure feed to the installer.</span></span> <span data-ttu-id="b4312-161">Es wird nicht empfohlen, diesen Wert zu ändern.</span><span class="sxs-lookup"><span data-stu-id="b4312-161">It isn't recommended that you change this value.</span></span> <span data-ttu-id="b4312-162">Die Standardeinstellung ist `https://dotnetcli.azureedge.net/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="b4312-162">The default is `https://dotnetcli.azureedge.net/dotnet`.</span></span>

`-ProxyAddress`

<span data-ttu-id="b4312-163">Wenn festgelegt, verwendet das Installationsprogramm den Proxy bei der Durchführung von Webanfragen.</span><span class="sxs-lookup"><span data-stu-id="b4312-163">If set, the installer uses the proxy when making web requests.</span></span> <span data-ttu-id="b4312-164">(Nur gültig für Windows)</span><span class="sxs-lookup"><span data-stu-id="b4312-164">(Only valid for Windows)</span></span>

`--verbose`

<span data-ttu-id="b4312-165">Diagnoseinformationen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="b4312-165">Display diagnostics information.</span></span>

`--help`

<span data-ttu-id="b4312-166">Druckt Hilfe für das Skript aus.</span><span class="sxs-lookup"><span data-stu-id="b4312-166">Prints out help for the script.</span></span>

## <a name="examples"></a><span data-ttu-id="b4312-167">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b4312-167">Examples</span></span>

<span data-ttu-id="b4312-168">Installieren Sie die neueste langfristig unterstützte (Long-Term Supported, LTS) Version am Standardspeicherort:</span><span class="sxs-lookup"><span data-stu-id="b4312-168">Install the latest long-term supported (LTS) version to the default location:</span></span>

<span data-ttu-id="b4312-169">Windows:</span><span class="sxs-lookup"><span data-stu-id="b4312-169">Windows:</span></span>

`./dotnet-install.ps1 -Channel LTS`

<span data-ttu-id="b4312-170">Mac OS/Linux:</span><span class="sxs-lookup"><span data-stu-id="b4312-170">macOS/Linux:</span></span>

`./dotnet-install.sh --channel LTS`

<span data-ttu-id="b4312-171">Installieren Sie die aktuelle Version von Kanal 2.0 am angegebenen Speicherort:</span><span class="sxs-lookup"><span data-stu-id="b4312-171">Install the latest version from 2.0 channel to the specified location:</span></span>

<span data-ttu-id="b4312-172">Windows:</span><span class="sxs-lookup"><span data-stu-id="b4312-172">Windows:</span></span>

`./dotnet-install.ps1 -Channel 2.0 -InstallDir C:\cli`

<span data-ttu-id="b4312-173">Mac OS/Linux:</span><span class="sxs-lookup"><span data-stu-id="b4312-173">macOS/Linux:</span></span>

`./dotnet-install.sh --channel 2.0 --install-dir ~/cli`

<span data-ttu-id="b4312-174">Installieren Sie die Version 1.1.0 der freigegebenen Laufzeit:</span><span class="sxs-lookup"><span data-stu-id="b4312-174">Install the 1.1.0 version of the shared runtime:</span></span>

<span data-ttu-id="b4312-175">Windows:</span><span class="sxs-lookup"><span data-stu-id="b4312-175">Windows:</span></span>

`./dotnet-install.ps1 -SharedRuntime -Version 1.1.0`

<span data-ttu-id="b4312-176">Mac OS/Linux:</span><span class="sxs-lookup"><span data-stu-id="b4312-176">macOS/Linux:</span></span>

`./dotnet-install.sh --shared-runtime --version 1.1.0`

<span data-ttu-id="b4312-177">Rufen Sie das Skript ab, und installieren Sie die Beispiele für die .NET Core-CLI:</span><span class="sxs-lookup"><span data-stu-id="b4312-177">Obtain script and install .NET Core CLI one-liner examples:</span></span>

<span data-ttu-id="b4312-178">Windows:</span><span class="sxs-lookup"><span data-stu-id="b4312-178">Windows:</span></span>

`@powershell -NoProfile -ExecutionPolicy unrestricted -Command "&([scriptblock]::Create((Invoke-WebRequest -useb 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"`

<span data-ttu-id="b4312-179">Mac OS/Linux:</span><span class="sxs-lookup"><span data-stu-id="b4312-179">macOS/Linux:</span></span>

`curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>`

## <a name="see-also"></a><span data-ttu-id="b4312-180">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4312-180">See also</span></span>

<span data-ttu-id="b4312-181">[.NET Core-Versionen](https://github.com/dotnet/core/releases) </span><span class="sxs-lookup"><span data-stu-id="b4312-181">[.NET Core releases](https://github.com/dotnet/core/releases) </span></span>  
[<span data-ttu-id="b4312-182">Downloadarchiv von .NET Core Runtime und des SDK</span><span class="sxs-lookup"><span data-stu-id="b4312-182">.NET Core Runtime and SDK download archive</span></span>](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)
