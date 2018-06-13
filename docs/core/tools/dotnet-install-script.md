---
title: Dotnet-Installationsskripts
description: Informationen zu Dotnet-Installationsskripts zur Installation von .NET Core CLI-Tools und freigegebener Laufzeit.
author: blackdwarf
ms.author: mairaw
ms.date: 09/11/2017
ms.openlocfilehash: acdf49950ebb49751c55ae72b3f623e590489202
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33214379"
---
# <a name="dotnet-install-scripts-reference"></a><span data-ttu-id="907a8-103">Dotnet-Installationsskripts Verweis</span><span class="sxs-lookup"><span data-stu-id="907a8-103">dotnet-install scripts reference</span></span>

## <a name="name"></a><span data-ttu-id="907a8-104">name</span><span class="sxs-lookup"><span data-stu-id="907a8-104">Name</span></span>

<span data-ttu-id="907a8-105">`dotnet-install.ps1` | `dotnet-install.sh`: Skript, mit dem die .NET Core-CLI-Tools und die freigegebene Laufzeit installiert werden.</span><span class="sxs-lookup"><span data-stu-id="907a8-105">`dotnet-install.ps1` | `dotnet-install.sh` - Script used to install the .NET Core CLI tools and the shared runtime.</span></span>

## <a name="synopsis"></a><span data-ttu-id="907a8-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="907a8-106">Synopsis</span></span>

<span data-ttu-id="907a8-107">Windows:</span><span class="sxs-lookup"><span data-stu-id="907a8-107">Windows:</span></span>

`dotnet-install.ps1 [-Channel] [-Version] [-InstallDir] [-Architecture] [-SharedRuntime] [-DryRun] [-NoPath] [-AzureFeed] [-ProxyAddress] [--Verbose] [--Help]`

<span data-ttu-id="907a8-108">Mac OS/Linux:</span><span class="sxs-lookup"><span data-stu-id="907a8-108">macOS/Linux:</span></span>

`dotnet-install.sh [--channel] [--version] [--install-dir] [--architecture] [--shared-runtime] [--dry-run] [--no-path] [--azure-feed] [--verbose] [--help]`

## <a name="description"></a><span data-ttu-id="907a8-109">description</span><span class="sxs-lookup"><span data-stu-id="907a8-109">Description</span></span>

<span data-ttu-id="907a8-110">Die `dotnet-install`-Skripts werden verwendet, um eine Nicht-Administrator-Installation des .NET Core-SDK durchzuführen, die die .NET Core-CLI-Tools und die freigegebene Laufzeit enthält.</span><span class="sxs-lookup"><span data-stu-id="907a8-110">The `dotnet-install` scripts are used to perform a non-admin installation of the .NET Core SDK, which includes the .NET Core CLI tools and the shared runtime.</span></span>

<span data-ttu-id="907a8-111">Sie sollten die stabile Version verwenden, die auf der [.NET Core-Hauptwebsite](https://dot.net) gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="907a8-111">We recommend that you use the stable version that is hosted on [.NET Core main website](https://dot.net).</span></span> <span data-ttu-id="907a8-112">Die direkten Pfade zu den Skripts sind:</span><span class="sxs-lookup"><span data-stu-id="907a8-112">The direct paths to the scripts are:</span></span>

* <span data-ttu-id="907a8-113">https://dot.net/v1/dotnet-install.sh (Bash, UNIX)</span><span class="sxs-lookup"><span data-stu-id="907a8-113">https://dot.net/v1/dotnet-install.sh (bash, UNIX)</span></span>
* <span data-ttu-id="907a8-114">https://dot.net/v1/dotnet-install.ps1 (PowerShell, Windows)</span><span class="sxs-lookup"><span data-stu-id="907a8-114">https://dot.net/v1/dotnet-install.ps1 (Powershell, Windows)</span></span>

<span data-ttu-id="907a8-115">Diese Skripts sind vor allem in Szenarios für die Automatisierung und Nicht-Administrator-Installationen nützlich.</span><span class="sxs-lookup"><span data-stu-id="907a8-115">The main usefulness of these scripts is in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="907a8-116">Es gibt zwei Skripts: Das eine ist ein PowerShell-Skript, das unter Windows funktioniert.</span><span class="sxs-lookup"><span data-stu-id="907a8-116">There are two scripts: One is a PowerShell script that works on Windows.</span></span> <span data-ttu-id="907a8-117">Das andere Skript ist ein Bash-Skript für Linux/macOS.</span><span class="sxs-lookup"><span data-stu-id="907a8-117">The other script is a bash script that works on Linux/macOS.</span></span> <span data-ttu-id="907a8-118">Beide Skripts weisen das gleiche Verhalten auf.</span><span class="sxs-lookup"><span data-stu-id="907a8-118">Both scripts have the same behavior.</span></span> <span data-ttu-id="907a8-119">Das Bash-Skript liest auch PowerShell-Schalter, sodass Sie PowerShell-Schalter mit dem Skript auf Linux/macOS-Systemen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="907a8-119">The bash script also reads PowerShell switches, so you can use PowerShell switches with the script on Linux/macOS systems.</span></span> 

<span data-ttu-id="907a8-120">Die Installationsskripts laden die ZIP/Tarball-Datei vom CLI-Build-Ablagespeicherort herunter und installieren sie entweder am Standardspeicherort oder an einem in `-InstallDir|--install-dir` angegebenen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="907a8-120">The installation scripts download the ZIP/tarball file from the CLI build drops and proceed to install it in either the default location or in a location specified by `-InstallDir|--install-dir`.</span></span> <span data-ttu-id="907a8-121">In der Standardeinstellung laden die Installationsskripts das SDK herunter und installieren es.</span><span class="sxs-lookup"><span data-stu-id="907a8-121">By default, the installation scripts download the SDK and install it.</span></span> <span data-ttu-id="907a8-122">Wenn Sie nur die freigegebene Laufzeit abrufen möchten, geben Sie das `--shared-runtime`-Argument an.</span><span class="sxs-lookup"><span data-stu-id="907a8-122">If you wish to only obtain the shared runtime, specify the `--shared-runtime` argument.</span></span> 

<span data-ttu-id="907a8-123">In der Standardeinstellung fügt das Skript den Installationsort dem $PATH für die aktuelle Sitzung hinzu.</span><span class="sxs-lookup"><span data-stu-id="907a8-123">By default, the script adds the install location to the $PATH for the current session.</span></span> <span data-ttu-id="907a8-124">Überschreiben Sie dieses Standardverhalten, indem sie das `--no-path`-Argument angeben.</span><span class="sxs-lookup"><span data-stu-id="907a8-124">Override this default behavior by specifying the `--no-path` argument.</span></span> 

<span data-ttu-id="907a8-125">Bevor Sie das Skript ausführen, installieren Sie die erforderlichen [Abhängigkeiten](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span><span class="sxs-lookup"><span data-stu-id="907a8-125">Before running the script, install the required [dependencies](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span></span>

<span data-ttu-id="907a8-126">Installieren Sie eine bestimmte Version mithilfe des Arguments `--version`.</span><span class="sxs-lookup"><span data-stu-id="907a8-126">You can install a specific version using the `--version` argument.</span></span> <span data-ttu-id="907a8-127">Die Version muss als dreiteilige Version (z.B. 1.0.0-13232) angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="907a8-127">The version must be specified as a 3-part version (for example, 1.0.0-13232).</span></span> <span data-ttu-id="907a8-128">Wenn nicht angegeben, wird die `latest`-Version verwendet.</span><span class="sxs-lookup"><span data-stu-id="907a8-128">If omitted, it uses the `latest` version.</span></span>

## <a name="options"></a><span data-ttu-id="907a8-129">Optionen</span><span class="sxs-lookup"><span data-stu-id="907a8-129">Options</span></span>

`-Channel <CHANNEL>`

<span data-ttu-id="907a8-130">Gibt den Quellkanal für die Installation an.</span><span class="sxs-lookup"><span data-stu-id="907a8-130">Specifies the source channel for the installation.</span></span> <span data-ttu-id="907a8-131">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="907a8-131">The possible values are:</span></span>

- <span data-ttu-id="907a8-132">`Current`: Aktuelle Version</span><span class="sxs-lookup"><span data-stu-id="907a8-132">`Current` - Current release</span></span>
- <span data-ttu-id="907a8-133">`LTS`: Long Term Support-Kanal (aktuell unterstützte Versionen)</span><span class="sxs-lookup"><span data-stu-id="907a8-133">`LTS` - Long-Term Support channel (current supported release)</span></span>
- <span data-ttu-id="907a8-134">Zweiteilige Version im X.Y-Format, das eine bestimmte Version darstellt (z.B. `2.0` oder `1.0`)</span><span class="sxs-lookup"><span data-stu-id="907a8-134">Two-part version in X.Y format representing a specific release (for example, `2.0` or `1.0`)</span></span>
- <span data-ttu-id="907a8-135">Branchname [z.B. `release/2.0.0`, `release/2.0.0-preview2`, oder `master` für die neueste aus dem Branch `master` („topaktuelle“ nächtliche Versionen)]</span><span class="sxs-lookup"><span data-stu-id="907a8-135">Branch name [for example, `release/2.0.0`, `release/2.0.0-preview2`, or `master` for the latest from the `master` branch ("bleeding edge" nightly releases)]</span></span>

<span data-ttu-id="907a8-136">Der Standardwert ist `LTS`.</span><span class="sxs-lookup"><span data-stu-id="907a8-136">The default value is `LTS`.</span></span> <span data-ttu-id="907a8-137">Weitere Informationen zu .NET-Supportkanälen finden Sie unter dem Thema [.NET Core Support Lifecycle](https://www.microsoft.com/net/core/support).</span><span class="sxs-lookup"><span data-stu-id="907a8-137">For more information on .NET support channels, see the [.NET Core Support Lifecycle](https://www.microsoft.com/net/core/support) topic.</span></span>

`-Version <VERSION>`

<span data-ttu-id="907a8-138">Stellt eine bestimmte Buildversion dar.</span><span class="sxs-lookup"><span data-stu-id="907a8-138">Represents a specific build version.</span></span> <span data-ttu-id="907a8-139">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="907a8-139">The possible values are:</span></span>

- <span data-ttu-id="907a8-140">`latest` – der neueste Build auf dem Kanal (mit der `-Channel`-Option verwendet)</span><span class="sxs-lookup"><span data-stu-id="907a8-140">`latest` - Latest build on the channel (used with the `-Channel` option)</span></span>
- <span data-ttu-id="907a8-141">`coherent` – neuester kohärenter Build auf dem Kanal; verwendet die neueste stabile Paketkombination (mit Branch-Name-`-Channel`-Optionen verwendet)</span><span class="sxs-lookup"><span data-stu-id="907a8-141">`coherent` - Latest coherent build on the channel; uses the latest stable package combination (used with Branch name `-Channel` options)</span></span>
- <span data-ttu-id="907a8-142">Dreiteilige Version im X.Y.Z-Format, die eine bestimmte Buildversion darstellt; sie hat Vorrang vor der `-Channel`-Option.</span><span class="sxs-lookup"><span data-stu-id="907a8-142">Three-part version in X.Y.Z format representing a specific build version; supersedes the `-Channel` option.</span></span> <span data-ttu-id="907a8-143">Beispiel: `2.0.0-preview2-006120`</span><span class="sxs-lookup"><span data-stu-id="907a8-143">For example: `2.0.0-preview2-006120`</span></span>

<span data-ttu-id="907a8-144">Wenn kein Wert angegeben ist, hat `-Version` den Standardwert `latest`.</span><span class="sxs-lookup"><span data-stu-id="907a8-144">If omitted, `-Version` defaults to `latest`.</span></span>

`-InstallDir <DIRECTORY>`

<span data-ttu-id="907a8-145">Gibt den Installationspfad an.</span><span class="sxs-lookup"><span data-stu-id="907a8-145">Specifies the installation path.</span></span> <span data-ttu-id="907a8-146">Das Verzeichnis wird erstellt, wenn es nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="907a8-146">The directory is created if it doesn't exist.</span></span> <span data-ttu-id="907a8-147">Der Standardwert ist *%LocalAppData%\.dotnet*.</span><span class="sxs-lookup"><span data-stu-id="907a8-147">The default value is *%LocalAppData%\.dotnet*.</span></span> <span data-ttu-id="907a8-148">Beachten Sie, dass Binärdateien direkt im Verzeichnis platziert werden.</span><span class="sxs-lookup"><span data-stu-id="907a8-148">Note that binaries are placed directly in the directory.</span></span>

`-Architecture <ARCHITECTURE>`

<span data-ttu-id="907a8-149">Architektur der zu installierenden .NET Core-Binärdateien.</span><span class="sxs-lookup"><span data-stu-id="907a8-149">Architecture of the .NET Core binaries to install.</span></span> <span data-ttu-id="907a8-150">Mögliche Werte sind `auto`, `x64` und `x86`.</span><span class="sxs-lookup"><span data-stu-id="907a8-150">Possible values are `auto`, `x64`, and `x86`.</span></span> <span data-ttu-id="907a8-151">Der Standardwert ist `auto`, was die derzeit ausgeführte Betriebssystemarchitektur darstellt.</span><span class="sxs-lookup"><span data-stu-id="907a8-151">The default value is `auto`, which represents the currently running OS architecture.</span></span>

`-SharedRuntime`

<span data-ttu-id="907a8-152">Wenn festgelegt, beschränkt dieser Schalter die Installation auf die freigegebene Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="907a8-152">If set, this switch limits installation to the shared runtime.</span></span> <span data-ttu-id="907a8-153">Das gesamte SDK ist nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="907a8-153">The entire SDK isn't installed.</span></span>

`-DryRun`

<span data-ttu-id="907a8-154">Wenn festgelegt, führt das Skript die Installation nicht aus. Es zeigt stattdessen an, welche Befehlszeile verwendet werden soll, um die derzeit erforderliche Version der .NET Core-CLI konsistent zu installieren.</span><span class="sxs-lookup"><span data-stu-id="907a8-154">If set, the script won't perform the installation; but instead, it displays what command line to use to consistently install the currently requested version of the .NET Core CLI.</span></span> <span data-ttu-id="907a8-155">Wenn Sie z.B. Version `latest` angeben, wird eine Verbindung mit der bestimmten Version angezeigt, damit dieser Befehl deterministisch in einem Buildskript verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="907a8-155">For example if you specify version `latest`, it displays a link with the specific version so that this command can be used deterministically in a build script.</span></span> <span data-ttu-id="907a8-156">Außerdem wird der Speicherort der Binärdatei angezeigt, wenn Sie sie selbst installieren oder herunterladen möchten.</span><span class="sxs-lookup"><span data-stu-id="907a8-156">It also displays the binary's location if you prefer to install or download it yourself.</span></span>

`-NoPath`

<span data-ttu-id="907a8-157">Falls festgelegt, wird das Präfix/Installdir für die aktuelle Sitzung nicht in den Pfad exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="907a8-157">If set, the prefix/installdir are not exported to the path for the current session.</span></span> <span data-ttu-id="907a8-158">Standardmäßig wird das Skript den PFAD ändern. Somit werden die CLI-Tools sofort nach der Installation zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="907a8-158">By default, the script will modify the PATH, which makes the CLI tools available immediately after install.</span></span>

`-AzureFeed`

<span data-ttu-id="907a8-159">Gibt die URL für den Azure-Feed für den Installer an.</span><span class="sxs-lookup"><span data-stu-id="907a8-159">Specifies the URL for the Azure feed to the installer.</span></span> <span data-ttu-id="907a8-160">Es wird nicht empfohlen, diesen Wert zu ändern.</span><span class="sxs-lookup"><span data-stu-id="907a8-160">It isn't recommended that you change this value.</span></span> <span data-ttu-id="907a8-161">Die Standardeinstellung ist `https://dotnetcli.azureedge.net/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="907a8-161">The default is `https://dotnetcli.azureedge.net/dotnet`.</span></span>

`-ProxyAddress`

<span data-ttu-id="907a8-162">Wenn festgelegt, verwendet das Installationsprogramm den Proxy bei der Durchführung von Webanfragen.</span><span class="sxs-lookup"><span data-stu-id="907a8-162">If set, the installer uses the proxy when making web requests.</span></span> <span data-ttu-id="907a8-163">(Nur gültig für Windows)</span><span class="sxs-lookup"><span data-stu-id="907a8-163">(Only valid for Windows)</span></span>

`--verbose`

<span data-ttu-id="907a8-164">Diagnoseinformationen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="907a8-164">Display diagnostics information.</span></span>

`--help`

<span data-ttu-id="907a8-165">Druckt Hilfe für das Skript aus.</span><span class="sxs-lookup"><span data-stu-id="907a8-165">Prints out help for the script.</span></span>

## <a name="examples"></a><span data-ttu-id="907a8-166">Beispiele</span><span class="sxs-lookup"><span data-stu-id="907a8-166">Examples</span></span>

<span data-ttu-id="907a8-167">Installieren Sie die neueste langfristig unterstützte (Long-Term Supported, LTS) Version am Standardspeicherort:</span><span class="sxs-lookup"><span data-stu-id="907a8-167">Install the latest long-term supported (LTS) version to the default location:</span></span>

<span data-ttu-id="907a8-168">Windows:</span><span class="sxs-lookup"><span data-stu-id="907a8-168">Windows:</span></span>

`./dotnet-install.ps1 -Channel LTS`

<span data-ttu-id="907a8-169">Mac OS/Linux:</span><span class="sxs-lookup"><span data-stu-id="907a8-169">macOS/Linux:</span></span>

`./dotnet-install.sh --channel LTS`

<span data-ttu-id="907a8-170">Installieren Sie die aktuelle Version von Kanal 2.0 am angegebenen Speicherort:</span><span class="sxs-lookup"><span data-stu-id="907a8-170">Install the latest version from 2.0 channel to the specified location:</span></span>

<span data-ttu-id="907a8-171">Windows:</span><span class="sxs-lookup"><span data-stu-id="907a8-171">Windows:</span></span>

`./dotnet-install.ps1 -Channel 2.0 -InstallDir C:\cli`

<span data-ttu-id="907a8-172">Mac OS/Linux:</span><span class="sxs-lookup"><span data-stu-id="907a8-172">macOS/Linux:</span></span>

`./dotnet-install.sh --channel 2.0 --install-dir ~/cli`

<span data-ttu-id="907a8-173">Installieren Sie die Version 1.1.0 der freigegebenen Laufzeit:</span><span class="sxs-lookup"><span data-stu-id="907a8-173">Install the 1.1.0 version of the shared runtime:</span></span>

<span data-ttu-id="907a8-174">Windows:</span><span class="sxs-lookup"><span data-stu-id="907a8-174">Windows:</span></span>

`./dotnet-install.ps1 -SharedRuntime -Version 1.1.0`

<span data-ttu-id="907a8-175">Mac OS/Linux:</span><span class="sxs-lookup"><span data-stu-id="907a8-175">macOS/Linux:</span></span>

`./dotnet-install.sh --shared-runtime --version 1.1.0`

<span data-ttu-id="907a8-176">Rufen Sie das Skript ab, und installieren Sie die Beispiele für die .NET Core-CLI:</span><span class="sxs-lookup"><span data-stu-id="907a8-176">Obtain script and install .NET Core CLI one-liner examples:</span></span>

<span data-ttu-id="907a8-177">Windows:</span><span class="sxs-lookup"><span data-stu-id="907a8-177">Windows:</span></span>

`@powershell -NoProfile -ExecutionPolicy unrestricted -Command "&([scriptblock]::Create((Invoke-WebRequest -useb 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"`

<span data-ttu-id="907a8-178">Mac OS/Linux:</span><span class="sxs-lookup"><span data-stu-id="907a8-178">macOS/Linux:</span></span>

`curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>`

## <a name="see-also"></a><span data-ttu-id="907a8-179">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="907a8-179">See also</span></span>

<span data-ttu-id="907a8-180">[.NET Core-Versionen](https://github.com/dotnet/core/releases) </span><span class="sxs-lookup"><span data-stu-id="907a8-180">[.NET Core releases](https://github.com/dotnet/core/releases) </span></span>  
[<span data-ttu-id="907a8-181">Downloadarchiv von .NET Core Runtime und des SDK</span><span class="sxs-lookup"><span data-stu-id="907a8-181">.NET Core Runtime and SDK download archive</span></span>](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)
