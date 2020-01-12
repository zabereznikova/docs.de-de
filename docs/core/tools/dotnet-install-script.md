---
title: Dotnet-Installationsskripts
description: Informationen zu Dotnet-Installationsskripts zur Installation von .NET Core CLI-Tools und freigegebener Laufzeit.
ms.date: 01/16/2019
ms.openlocfilehash: f72e12fc415824a9c69eba6f52e3c01717cf654c
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740529"
---
# <a name="dotnet-install-scripts-reference"></a><span data-ttu-id="fcf20-103">Dotnet-Installationsskripts Verweis</span><span class="sxs-lookup"><span data-stu-id="fcf20-103">dotnet-install scripts reference</span></span>

## <a name="name"></a><span data-ttu-id="fcf20-104">name</span><span class="sxs-lookup"><span data-stu-id="fcf20-104">Name</span></span>

<span data-ttu-id="fcf20-105">`dotnet-install.ps1` | `dotnet-install.sh`: Skript, mit dem die .NET Core-CLI-Tools und die freigegebene Laufzeit installiert werden.</span><span class="sxs-lookup"><span data-stu-id="fcf20-105">`dotnet-install.ps1` | `dotnet-install.sh` - Script used to install the .NET Core CLI tools and the shared runtime.</span></span>

## <a name="synopsis"></a><span data-ttu-id="fcf20-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="fcf20-106">Synopsis</span></span>

<span data-ttu-id="fcf20-107">Windows:</span><span class="sxs-lookup"><span data-stu-id="fcf20-107">Windows:</span></span>

`dotnet-install.ps1 [-Channel] [-Version] [-InstallDir] [-Architecture] [-SharedRuntime] [-Runtime] [-DryRun] [-NoPath] [-Verbose] [-AzureFeed] [-UncachedFeed] [-NoCdn] [-FeedCredential] [-ProxyAddress] [-ProxyUseDefaultCredentials] [-SkipNonVersionedFiles] [-Help]`

<span data-ttu-id="fcf20-108">Mac OS/Linux:</span><span class="sxs-lookup"><span data-stu-id="fcf20-108">macOS/Linux:</span></span>

`dotnet-install.sh [--channel] [--version] [--install-dir] [--architecture] [--runtime] [--dry-run] [--no-path] [--verbose] [--azure-feed] [--uncached-feed] [--no-cdn] [--feed-credential] [--runtime-id] [--skip-non-versioned-files] [--help]`

## <a name="description"></a><span data-ttu-id="fcf20-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fcf20-109">Description</span></span>

<span data-ttu-id="fcf20-110">Die `dotnet-install`-Skripts werden verwendet, um eine Nicht-Administrator-Installation des .NET Core-SDK durchzuführen, die die .NET Core-CLI-Tools und die freigegebene Laufzeit enthält.</span><span class="sxs-lookup"><span data-stu-id="fcf20-110">The `dotnet-install` scripts are used to perform a non-admin installation of the .NET Core SDK, which includes the .NET Core CLI tools and the shared runtime.</span></span>

<span data-ttu-id="fcf20-111">Sie sollten die stabile Version verwenden, die auf der [.NET Core-Hauptwebsite](https://dot.net) gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="fcf20-111">We recommend that you use the stable version that is hosted on [.NET Core main website](https://dot.net).</span></span> <span data-ttu-id="fcf20-112">Die direkten Pfade zu den Skripts sind:</span><span class="sxs-lookup"><span data-stu-id="fcf20-112">The direct paths to the scripts are:</span></span>

- <span data-ttu-id="fcf20-113"><https://dot.net/v1/dotnet-install.sh> (Bash, UNIX)</span><span class="sxs-lookup"><span data-stu-id="fcf20-113"><https://dot.net/v1/dotnet-install.sh> (bash, UNIX)</span></span>
- <span data-ttu-id="fcf20-114"><https://dot.net/v1/dotnet-install.ps1> (PowerShell, Windows)</span><span class="sxs-lookup"><span data-stu-id="fcf20-114"><https://dot.net/v1/dotnet-install.ps1> (Powershell, Windows)</span></span>

<span data-ttu-id="fcf20-115">Diese Skripts sind vor allem in Szenarios für die Automatisierung und Nicht-Administrator-Installationen nützlich.</span><span class="sxs-lookup"><span data-stu-id="fcf20-115">The main usefulness of these scripts is in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="fcf20-116">Es gibt zwei Skripts: eines für PowerShell unter Windows und ein Bash-Skript für Linux/macOS.</span><span class="sxs-lookup"><span data-stu-id="fcf20-116">There are two scripts: one is a PowerShell script that works on Windows, and the other is a bash script that works on Linux/macOS.</span></span> <span data-ttu-id="fcf20-117">Beide Skripts weisen das gleiche Verhalten auf.</span><span class="sxs-lookup"><span data-stu-id="fcf20-117">Both scripts have the same behavior.</span></span> <span data-ttu-id="fcf20-118">Das Bash-Skript liest auch PowerShell-Schalter, sodass Sie PowerShell-Schalter mit dem Skript auf Linux/macOS-Systemen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="fcf20-118">The bash script also reads PowerShell switches, so you can use PowerShell switches with the script on Linux/macOS systems.</span></span>

<span data-ttu-id="fcf20-119">Die Installationsskripts laden die ZIP/Tarball-Datei vom CLI-Build-Ablagespeicherort herunter und installieren sie entweder am Standardspeicherort oder an einem in `-InstallDir|--install-dir` angegebenen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="fcf20-119">The installation scripts download the ZIP/tarball file from the CLI build drops and proceed to install it in either the default location or in a location specified by `-InstallDir|--install-dir`.</span></span> <span data-ttu-id="fcf20-120">In der Standardeinstellung laden die Installationsskripts das SDK herunter und installieren es.</span><span class="sxs-lookup"><span data-stu-id="fcf20-120">By default, the installation scripts download the SDK and install it.</span></span> <span data-ttu-id="fcf20-121">Wenn Sie nur die freigegebene Laufzeit abrufen möchten, geben Sie das `--runtime`-Argument an.</span><span class="sxs-lookup"><span data-stu-id="fcf20-121">If you wish to only obtain the shared runtime, specify the `--runtime` argument.</span></span>

<span data-ttu-id="fcf20-122">In der Standardeinstellung fügt das Skript den Installationsort dem $PATH für die aktuelle Sitzung hinzu.</span><span class="sxs-lookup"><span data-stu-id="fcf20-122">By default, the script adds the install location to the $PATH for the current session.</span></span> <span data-ttu-id="fcf20-123">Überschreiben Sie dieses Standardverhalten, indem sie das `--no-path`-Argument angeben.</span><span class="sxs-lookup"><span data-stu-id="fcf20-123">Override this default behavior by specifying the `--no-path` argument.</span></span>

<span data-ttu-id="fcf20-124">Bevor Sie das Skript ausführen, installieren Sie die erforderlichen [Abhängigkeiten](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span><span class="sxs-lookup"><span data-stu-id="fcf20-124">Before running the script, install the required [dependencies](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span></span>

<span data-ttu-id="fcf20-125">Installieren Sie eine bestimmte Version mithilfe des Arguments `--version`.</span><span class="sxs-lookup"><span data-stu-id="fcf20-125">You can install a specific version using the `--version` argument.</span></span> <span data-ttu-id="fcf20-126">Die Version muss als dreiteilige Version (z.B. 1.0.0-13232) angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="fcf20-126">The version must be specified as a three-part version (for example, 1.0.0-13232).</span></span> <span data-ttu-id="fcf20-127">Wenn nicht angegeben, wird die `latest`-Version verwendet.</span><span class="sxs-lookup"><span data-stu-id="fcf20-127">If not provided, it uses the `latest` version.</span></span>

## <a name="options"></a><span data-ttu-id="fcf20-128">Optionen</span><span class="sxs-lookup"><span data-stu-id="fcf20-128">Options</span></span>

- **`-Channel <CHANNEL>`**

  <span data-ttu-id="fcf20-129">Gibt den Quellkanal für die Installation an.</span><span class="sxs-lookup"><span data-stu-id="fcf20-129">Specifies the source channel for the installation.</span></span> <span data-ttu-id="fcf20-130">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="fcf20-130">The possible values are:</span></span>

  - <span data-ttu-id="fcf20-131">`Current` – Aktuelles Release.</span><span class="sxs-lookup"><span data-stu-id="fcf20-131">`Current` - Most current release.</span></span>
  - <span data-ttu-id="fcf20-132">`LTS`: Long Term Support-Kanal (aktuell unterstütztes Release).</span><span class="sxs-lookup"><span data-stu-id="fcf20-132">`LTS` - Long-Term Support channel (most current supported release).</span></span>
  - <span data-ttu-id="fcf20-133">Zweiteilige Version im X.Y-Format, das eine bestimmte Version darstellt (z.B. `2.0` oder `1.0`).</span><span class="sxs-lookup"><span data-stu-id="fcf20-133">Two-part version in X.Y format representing a specific release (for example, `2.0` or `1.0`).</span></span>
  - <span data-ttu-id="fcf20-134">Branchname.</span><span class="sxs-lookup"><span data-stu-id="fcf20-134">Branch name.</span></span> <span data-ttu-id="fcf20-135">Zum Beispiel `release/2.0.0`, `release/2.0.0-preview2` or `master` (für nächtliche Releases).</span><span class="sxs-lookup"><span data-stu-id="fcf20-135">For example, `release/2.0.0`, `release/2.0.0-preview2`, or `master` (for nightly releases).</span></span>

  <span data-ttu-id="fcf20-136">Der Standardwert ist `LTS`.</span><span class="sxs-lookup"><span data-stu-id="fcf20-136">The default value is `LTS`.</span></span> <span data-ttu-id="fcf20-137">Weitere Informationen zu .NET-Supportkanälen finden Sie auf der Seite [.NET-Supportrichtlinie](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="fcf20-137">For more information on .NET support channels, see the [.NET Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) page.</span></span>

- **`-Version <VERSION>`**

  <span data-ttu-id="fcf20-138">Stellt eine bestimmte Buildversion dar.</span><span class="sxs-lookup"><span data-stu-id="fcf20-138">Represents a specific build version.</span></span> <span data-ttu-id="fcf20-139">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="fcf20-139">The possible values are:</span></span>

  - <span data-ttu-id="fcf20-140">`latest` – der neueste Build auf dem Kanal (mit der `-Channel`-Option verwendet).</span><span class="sxs-lookup"><span data-stu-id="fcf20-140">`latest` - Latest build on the channel (used with the `-Channel` option).</span></span>
  - <span data-ttu-id="fcf20-141">`coherent` – neuester kohärenter Build auf dem Kanal; verwendet die neueste stabile Paketkombination (mit Branchname-`-Channel`-Optionen verwendet).</span><span class="sxs-lookup"><span data-stu-id="fcf20-141">`coherent` - Latest coherent build on the channel; uses the latest stable package combination (used with Branch name `-Channel` options).</span></span>
  - <span data-ttu-id="fcf20-142">Dreiteilige Version im X.Y.Z-Format, die eine bestimmte Buildversion darstellt; sie hat Vorrang vor der `-Channel`-Option.</span><span class="sxs-lookup"><span data-stu-id="fcf20-142">Three-part version in X.Y.Z format representing a specific build version; supersedes the `-Channel` option.</span></span> <span data-ttu-id="fcf20-143">Beispiel: `2.0.0-preview2-006120`.</span><span class="sxs-lookup"><span data-stu-id="fcf20-143">For example: `2.0.0-preview2-006120`.</span></span>

  <span data-ttu-id="fcf20-144">Wenn nichts angegeben ist, wird für `-Version` standardmäßig `latest` verwendet.</span><span class="sxs-lookup"><span data-stu-id="fcf20-144">If not specified, `-Version` defaults to `latest`.</span></span>

- **`-InstallDir <DIRECTORY>`**

  <span data-ttu-id="fcf20-145">Gibt den Installationspfad an.</span><span class="sxs-lookup"><span data-stu-id="fcf20-145">Specifies the installation path.</span></span> <span data-ttu-id="fcf20-146">Das Verzeichnis wird erstellt, wenn es nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="fcf20-146">The directory is created if it doesn't exist.</span></span> <span data-ttu-id="fcf20-147">Der Standardwert ist *%LocalAppData%\Microsoft\dotnet*.</span><span class="sxs-lookup"><span data-stu-id="fcf20-147">The default value is *%LocalAppData%\Microsoft\dotnet*.</span></span> <span data-ttu-id="fcf20-148">Binärdateien werden direkt im Verzeichnis platziert.</span><span class="sxs-lookup"><span data-stu-id="fcf20-148">Binaries are placed directly in this directory.</span></span>

- **`-Architecture <ARCHITECTURE>`**

  <span data-ttu-id="fcf20-149">Architektur der zu installierenden .NET Core-Binärdateien.</span><span class="sxs-lookup"><span data-stu-id="fcf20-149">Architecture of the .NET Core binaries to install.</span></span> <span data-ttu-id="fcf20-150">Mögliche Werte sind `<auto>`, `amd64`, `x64`, `x86`, `arm64` und `arm`.</span><span class="sxs-lookup"><span data-stu-id="fcf20-150">Possible values are `<auto>`, `amd64`, `x64`, `x86`, `arm64`, and `arm`.</span></span> <span data-ttu-id="fcf20-151">Der Standardwert ist `<auto>`, was die derzeit ausgeführte Betriebssystemarchitektur darstellt.</span><span class="sxs-lookup"><span data-stu-id="fcf20-151">The default value is `<auto>`, which represents the currently running OS architecture.</span></span>

- **`-SharedRuntime`**

  > [!NOTE]
  > <span data-ttu-id="fcf20-152">Dieser Parameter ist veraltet und wird in einer zukünftigen Version des Skripts möglicherweise entfernt.</span><span class="sxs-lookup"><span data-stu-id="fcf20-152">This parameter is obsolete and may be removed in a future version of the script.</span></span> <span data-ttu-id="fcf20-153">Die empfohlene Alternative ist die `Runtime`-Option.</span><span class="sxs-lookup"><span data-stu-id="fcf20-153">The recommended alternative is the `Runtime` option.</span></span>

  <span data-ttu-id="fcf20-154">Es werden nur die freigegebenen Runtimebestandteile installiert und nicht das gesamte SDK.</span><span class="sxs-lookup"><span data-stu-id="fcf20-154">Installs just the shared runtime bits, not the entire SDK.</span></span> <span data-ttu-id="fcf20-155">Dies entspricht dem Angeben von `-Runtime dotnet`.</span><span class="sxs-lookup"><span data-stu-id="fcf20-155">This is equivalent to specifying `-Runtime dotnet`.</span></span>

- **`-Runtime <RUNTIME>`**

  <span data-ttu-id="fcf20-156">Es wird nur die freigegebene Runtime installiert und nicht das gesamte SDK.</span><span class="sxs-lookup"><span data-stu-id="fcf20-156">Installs just the shared runtime, not the entire SDK.</span></span> <span data-ttu-id="fcf20-157">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="fcf20-157">The possible values are:</span></span>

  - <span data-ttu-id="fcf20-158">`dotnet` – die freigegebene Runtime von `Microsoft.NETCore.App`.</span><span class="sxs-lookup"><span data-stu-id="fcf20-158">`dotnet` - the `Microsoft.NETCore.App` shared runtime.</span></span>
  - <span data-ttu-id="fcf20-159">`aspnetcore` – die freigegebene Runtime von `Microsoft.AspNetCore.App`.</span><span class="sxs-lookup"><span data-stu-id="fcf20-159">`aspnetcore` - the `Microsoft.AspNetCore.App` shared runtime.</span></span>

- **`-DryRun`**

  <span data-ttu-id="fcf20-160">Wenn festgelegt, führt das Skript die Installation nicht aus.</span><span class="sxs-lookup"><span data-stu-id="fcf20-160">If set, the script won't perform the installation.</span></span> <span data-ttu-id="fcf20-161">Es zeigt stattdessen an, welche Befehlszeile verwendet werden soll, um die derzeit erforderliche Version der .NET Core-CLI konsistent zu installieren.</span><span class="sxs-lookup"><span data-stu-id="fcf20-161">Instead, it displays what command line to use to consistently install the currently requested version of the .NET Core CLI.</span></span> <span data-ttu-id="fcf20-162">Wenn Sie z.B. Version `latest` angeben, wird eine Verbindung mit der bestimmten Version angezeigt, damit dieser Befehl deterministisch in einem Buildskript verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="fcf20-162">For example, if you specify version `latest`, it displays a link with the specific version so that this command can be used deterministically in a build script.</span></span> <span data-ttu-id="fcf20-163">Außerdem wird der Speicherort der Binärdatei angezeigt, wenn Sie sie selbst installieren oder herunterladen möchten.</span><span class="sxs-lookup"><span data-stu-id="fcf20-163">It also displays the binary's location if you prefer to install or download it yourself.</span></span>

- **`-NoPath`**

  <span data-ttu-id="fcf20-164">Wenn festgelegt, wird der Installationsordner nicht in den Pfad für die aktuelle Sitzung exportiert.</span><span class="sxs-lookup"><span data-stu-id="fcf20-164">If set, the installation folder isn't exported to the path for the current session.</span></span> <span data-ttu-id="fcf20-165">Standardmäßig wird das Skript den PFAD ändern. Somit werden die CLI-Tools sofort nach der Installation zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="fcf20-165">By default, the script modifies the PATH, which makes the CLI tools available immediately after install.</span></span>

- **`-Verbose`**

  <span data-ttu-id="fcf20-166">Es werden Diagnoseinformationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fcf20-166">Displays diagnostics information.</span></span>

- **`-AzureFeed`**

  <span data-ttu-id="fcf20-167">Gibt die URL für den Azure-Feed für den Installer an.</span><span class="sxs-lookup"><span data-stu-id="fcf20-167">Specifies the URL for the Azure feed to the installer.</span></span> <span data-ttu-id="fcf20-168">Es wird nicht empfohlen, diesen Wert nicht zu ändern.</span><span class="sxs-lookup"><span data-stu-id="fcf20-168">We recommended that you don't change this value.</span></span> <span data-ttu-id="fcf20-169">Der Standardwert ist `https://dotnetcli.azureedge.net/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="fcf20-169">The default value is `https://dotnetcli.azureedge.net/dotnet`.</span></span>

- **`-UncachedFeed`**

  <span data-ttu-id="fcf20-170">Ermöglicht das Ändern der URL für den nicht zwischengespeicherten Feed, der von diesem Installer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fcf20-170">Allows changing the URL for the uncached feed used by this installer.</span></span> <span data-ttu-id="fcf20-171">Es wird nicht empfohlen, diesen Wert nicht zu ändern.</span><span class="sxs-lookup"><span data-stu-id="fcf20-171">We recommended that you don't change this value.</span></span>

- **`-NoCdn`**

  <span data-ttu-id="fcf20-172">Deaktiviert das Herunterladen aus dem [Azure Content Delivery Network (CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) und verwendet den nicht zwischengespeicherten Feed direkt.</span><span class="sxs-lookup"><span data-stu-id="fcf20-172">Disables downloading from the [Azure Content Delivery Network (CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) and uses the uncached feed directly.</span></span>

- **`-FeedCredential`**

  <span data-ttu-id="fcf20-173">Wird als Abfragezeichenfolge zum Anfügen an den Azure-Feed verwendet.</span><span class="sxs-lookup"><span data-stu-id="fcf20-173">Used as a query string to append to the Azure feed.</span></span> <span data-ttu-id="fcf20-174">Ermöglicht das Ändern der URL, um nicht öffentliche Blob Storage-Konten verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="fcf20-174">It allows changing the URL to use non-public blob storage accounts.</span></span>

- **`-ProxyAddress`**

  <span data-ttu-id="fcf20-175">Wenn festgelegt, verwendet das Installationsprogramm den Proxy bei der Durchführung von Webanfragen.</span><span class="sxs-lookup"><span data-stu-id="fcf20-175">If set, the installer uses the proxy when making web requests.</span></span> <span data-ttu-id="fcf20-176">(Nur gültig für Windows)</span><span class="sxs-lookup"><span data-stu-id="fcf20-176">(Only valid for Windows)</span></span>

- **`ProxyUseDefaultCredentials`**

  <span data-ttu-id="fcf20-177">Wenn festgelegt, verwendet der Installer bei Verwendung der Proxyadresse die Anmeldeinformationen des aktuellen Benutzers.</span><span class="sxs-lookup"><span data-stu-id="fcf20-177">If set, the installer uses the credentials of the current user when using proxy address.</span></span> <span data-ttu-id="fcf20-178">(Nur gültig für Windows)</span><span class="sxs-lookup"><span data-stu-id="fcf20-178">(Only valid for Windows)</span></span>

- **`-SkipNonVersionedFiles`**

  <span data-ttu-id="fcf20-179">Die Installation nicht versionierte Dateien, wie *dotnet.exe*, wird übersprungen, falls diese bereits vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="fcf20-179">Skips installing non-versioned files, such as *dotnet.exe*, if they already exist.</span></span>

- **`-Help`**

  <span data-ttu-id="fcf20-180">Druckt Hilfe für das Skript aus.</span><span class="sxs-lookup"><span data-stu-id="fcf20-180">Prints out help for the script.</span></span>

## <a name="examples"></a><span data-ttu-id="fcf20-181">Beispiele</span><span class="sxs-lookup"><span data-stu-id="fcf20-181">Examples</span></span>

- <span data-ttu-id="fcf20-182">Installieren Sie die neueste langfristig unterstützte (Long-Term Supported, LTS) Version am Standardspeicherort:</span><span class="sxs-lookup"><span data-stu-id="fcf20-182">Install the latest long-term supported (LTS) version to the default location:</span></span>

  <span data-ttu-id="fcf20-183">Windows:</span><span class="sxs-lookup"><span data-stu-id="fcf20-183">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel LTS
  ```

  <span data-ttu-id="fcf20-184">Mac OS/Linux:</span><span class="sxs-lookup"><span data-stu-id="fcf20-184">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel LTS
  ```

- <span data-ttu-id="fcf20-185">Installieren Sie die aktuelle Version von Kanal 2.0 am angegebenen Speicherort:</span><span class="sxs-lookup"><span data-stu-id="fcf20-185">Install the latest version from 2.0 channel to the specified location:</span></span>

  <span data-ttu-id="fcf20-186">Windows:</span><span class="sxs-lookup"><span data-stu-id="fcf20-186">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel 2.0 -InstallDir C:\cli
  ```

  <span data-ttu-id="fcf20-187">Mac OS/Linux:</span><span class="sxs-lookup"><span data-stu-id="fcf20-187">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel 2.0 --install-dir ~/cli
  ```

- <span data-ttu-id="fcf20-188">Installieren Sie die Version 1.1.0 der freigegebenen Laufzeit:</span><span class="sxs-lookup"><span data-stu-id="fcf20-188">Install the 1.1.0 version of the shared runtime:</span></span>

  <span data-ttu-id="fcf20-189">Windows:</span><span class="sxs-lookup"><span data-stu-id="fcf20-189">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Runtime dotnet -Version 1.1.0
  ```

  <span data-ttu-id="fcf20-190">Mac OS/Linux:</span><span class="sxs-lookup"><span data-stu-id="fcf20-190">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --runtime dotnet --version 1.1.0
  ```

- <span data-ttu-id="fcf20-191">Rufen Sie das Skript ab und installieren Sie die Version 2.1.2 hinter einem Unternehmensproxy (nur Windows):</span><span class="sxs-lookup"><span data-stu-id="fcf20-191">Obtain script and install the 2.1.2 version behind a corporate proxy (Windows only):</span></span>

  ```powershell
  Invoke-WebRequest 'https://dot.net/v1/dotnet-install.ps1' -Proxy $env:HTTP_PROXY -ProxyUseDefaultCredentials -OutFile 'dotnet-install.ps1';
  ./dotnet-install.ps1 -InstallDir '~/.dotnet' -Version '2.1.2' -ProxyAddress $env:HTTP_PROXY -ProxyUseDefaultCredentials;
  ```

- <span data-ttu-id="fcf20-192">Rufen Sie das Skript ab, und installieren Sie die Beispiele für die .NET Core-CLI:</span><span class="sxs-lookup"><span data-stu-id="fcf20-192">Obtain script and install .NET Core CLI one-liner examples:</span></span>

  <span data-ttu-id="fcf20-193">Windows:</span><span class="sxs-lookup"><span data-stu-id="fcf20-193">Windows:</span></span>

  ```powershell
  @powershell -NoProfile -ExecutionPolicy unrestricted -Command "[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; &([scriptblock]::Create((Invoke-WebRequest -UseBasicParsing 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"
  ```

  <span data-ttu-id="fcf20-194">Mac OS/Linux:</span><span class="sxs-lookup"><span data-stu-id="fcf20-194">macOS/Linux:</span></span>

  ```bash
  curl -ssl https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>
  ```

## <a name="see-also"></a><span data-ttu-id="fcf20-195">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fcf20-195">See also</span></span>

- [<span data-ttu-id="fcf20-196">.NET Core-Releases</span><span class="sxs-lookup"><span data-stu-id="fcf20-196">.NET Core releases</span></span>](https://github.com/dotnet/core/releases)
- [<span data-ttu-id="fcf20-197">Downloadarchiv von .NET Core Runtime und des SDK</span><span class="sxs-lookup"><span data-stu-id="fcf20-197">.NET Core Runtime and SDK download archive</span></span>](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)
