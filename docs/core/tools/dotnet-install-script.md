---
title: Dotnet-Installationsskripts
description: Erfahren Sie mehr über die dotnet-Installationsskripts zur Installation des .NET Core SDK und der Shared Runtime.
ms.date: 01/23/2020
ms.openlocfilehash: 76055627c6b2016396209c9594dba36e56eb841c
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920576"
---
# <a name="dotnet-install-scripts-reference"></a><span data-ttu-id="14058-103">Dotnet-Installationsskripts Verweis</span><span class="sxs-lookup"><span data-stu-id="14058-103">dotnet-install scripts reference</span></span>

## <a name="name"></a><span data-ttu-id="14058-104">name</span><span class="sxs-lookup"><span data-stu-id="14058-104">Name</span></span>

<span data-ttu-id="14058-105">`dotnet-install.ps1` | `dotnet-install.sh`: Skript, mit dem das .NET Core SDK und die Shared Runtime installiert werden.</span><span class="sxs-lookup"><span data-stu-id="14058-105">`dotnet-install.ps1` | `dotnet-install.sh` - Script used to install the .NET Core SDK and the shared runtime.</span></span>

## <a name="synopsis"></a><span data-ttu-id="14058-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="14058-106">Synopsis</span></span>

<span data-ttu-id="14058-107">Windows:</span><span class="sxs-lookup"><span data-stu-id="14058-107">Windows:</span></span>

```powershell
dotnet-install.ps1 [-Channel] [-Version] [-JSonFile] [-InstallDir] [-Architecture]
    [-Runtime] [-DryRun] [-NoPath] [-Verbose] [-AzureFeed] [-UncachedFeed] [-NoCdn] [-FeedCredential]
    [-ProxyAddress] [-ProxyUseDefaultCredentials] [-SkipNonVersionedFiles] [-Help]
```

<span data-ttu-id="14058-108">Linux/macOS:</span><span class="sxs-lookup"><span data-stu-id="14058-108">Linux/macOs:</span></span>

```bash
dotnet-install.sh [--channel] [--version] [--jsonfile] [--install-dir] [--architecture]
    [--runtime] [--dry-run] [--no-path] [--verbose] [--azure-feed] [--uncached-feed] [--no-cdn] [--feed-credential]
    [--runtime-id] [--skip-non-versioned-files] [--help]
```

## <a name="description"></a><span data-ttu-id="14058-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="14058-109">Description</span></span>

<span data-ttu-id="14058-110">Die `dotnet-install`-Skripts werden verwendet, um eine Nicht-Administrator-Installation des .NET Core SDK durchzuführen, die die .NET Core-CLI und die freigegebene Runtime enthält.</span><span class="sxs-lookup"><span data-stu-id="14058-110">The `dotnet-install` scripts are used to perform a non-admin installation of the .NET Core SDK, which includes the .NET Core CLI and the shared runtime.</span></span>

<span data-ttu-id="14058-111">Es wird empfohlen, die stabile Version der Skripts zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="14058-111">We recommend that you use the stable version of the scripts:</span></span>

- <span data-ttu-id="14058-112">Bash (Linux/macOS): <https://dot.net/v1/dotnet-install.sh></span><span class="sxs-lookup"><span data-stu-id="14058-112">Bash (Linux/macOS): <https://dot.net/v1/dotnet-install.sh></span></span>
- <span data-ttu-id="14058-113">PowerShell (Windows): <https://dot.net/v1/dotnet-install.ps1></span><span class="sxs-lookup"><span data-stu-id="14058-113">PowerShell (Windows): <https://dot.net/v1/dotnet-install.ps1></span></span>

<span data-ttu-id="14058-114">Diese Skripts sind vor allem in Szenarios für die Automatisierung und Nicht-Administrator-Installationen nützlich.</span><span class="sxs-lookup"><span data-stu-id="14058-114">The main usefulness of these scripts is in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="14058-115">Es gibt zwei Skripts: eines für PowerShell unter Windows und ein Bash-Skript für Linux/macOS.</span><span class="sxs-lookup"><span data-stu-id="14058-115">There are two scripts: one is a PowerShell script that works on Windows, and the other is a bash script that works on Linux/macOS.</span></span> <span data-ttu-id="14058-116">Beide Skripts weisen das gleiche Verhalten auf.</span><span class="sxs-lookup"><span data-stu-id="14058-116">Both scripts have the same behavior.</span></span> <span data-ttu-id="14058-117">Das Bash-Skript liest auch PowerShell-Schalter, sodass Sie PowerShell-Schalter mit dem Skript auf Linux/macOS-Systemen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="14058-117">The bash script also reads PowerShell switches, so you can use PowerShell switches with the script on Linux/macOS systems.</span></span>

<span data-ttu-id="14058-118">Die Installationsskripts laden die ZIP/Tarball-Datei vom CLI-Build-Ablagespeicherort herunter und installieren sie entweder am Standardspeicherort oder an einem in `-InstallDir|--install-dir` angegebenen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="14058-118">The installation scripts download the ZIP/tarball file from the CLI build drops and proceed to install it in either the default location or in a location specified by `-InstallDir|--install-dir`.</span></span> <span data-ttu-id="14058-119">In der Standardeinstellung laden die Installationsskripts das SDK herunter und installieren es.</span><span class="sxs-lookup"><span data-stu-id="14058-119">By default, the installation scripts download the SDK and install it.</span></span> <span data-ttu-id="14058-120">Wenn Sie nur die freigegebene Laufzeit abrufen möchten, geben Sie das `-Runtime|--runtime`-Argument an.</span><span class="sxs-lookup"><span data-stu-id="14058-120">If you wish to only obtain the shared runtime, specify the `-Runtime|--runtime` argument.</span></span>

<span data-ttu-id="14058-121">In der Standardeinstellung fügt das Skript den Installationsort dem $PATH für die aktuelle Sitzung hinzu.</span><span class="sxs-lookup"><span data-stu-id="14058-121">By default, the script adds the install location to the $PATH for the current session.</span></span> <span data-ttu-id="14058-122">Überschreiben Sie dieses Standardverhalten, indem sie das `-NoPath|--no-path`-Argument angeben.</span><span class="sxs-lookup"><span data-stu-id="14058-122">Override this default behavior by specifying the `-NoPath|--no-path` argument.</span></span>

<span data-ttu-id="14058-123">Bevor Sie das Skript ausführen, installieren Sie die erforderlichen [Abhängigkeiten](../install/dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="14058-123">Before running the script, install the required [dependencies](../install/dependencies.md).</span></span>

<span data-ttu-id="14058-124">Installieren Sie eine bestimmte Version mithilfe des Arguments `-Version|--version`.</span><span class="sxs-lookup"><span data-stu-id="14058-124">You can install a specific version using the `-Version|--version` argument.</span></span> <span data-ttu-id="14058-125">Die Version muss als dreiteilige Version (z. B. `2.1.0`) angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="14058-125">The version must be specified as a three-part version (for example, `2.1.0`).</span></span> <span data-ttu-id="14058-126">Wenn nicht angegeben, wird die `latest`-Version verwendet.</span><span class="sxs-lookup"><span data-stu-id="14058-126">If not provided, it uses the `latest` version.</span></span>

## <a name="options"></a><span data-ttu-id="14058-127">Optionen</span><span class="sxs-lookup"><span data-stu-id="14058-127">Options</span></span>

- **`-Channel|--channel <CHANNEL>`**

  <span data-ttu-id="14058-128">Gibt den Quellkanal für die Installation an.</span><span class="sxs-lookup"><span data-stu-id="14058-128">Specifies the source channel for the installation.</span></span> <span data-ttu-id="14058-129">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="14058-129">The possible values are:</span></span>

  - <span data-ttu-id="14058-130">`Current` – Aktuelles Release.</span><span class="sxs-lookup"><span data-stu-id="14058-130">`Current` - Most current release.</span></span>
  - <span data-ttu-id="14058-131">`LTS`: Long Term Support-Kanal (aktuell unterstütztes Release).</span><span class="sxs-lookup"><span data-stu-id="14058-131">`LTS` - Long-Term Support channel (most current supported release).</span></span>
  - <span data-ttu-id="14058-132">Zweiteilige Version im X.Y-Format, das eine bestimmte Version darstellt (z.B. `2.1` oder `3.0`).</span><span class="sxs-lookup"><span data-stu-id="14058-132">Two-part version in X.Y format representing a specific release (for example, `2.1` or `3.0`).</span></span>
  - <span data-ttu-id="14058-133">Branchname: zum Beispiel `release/3.1.1xx` oder `master` (für nächtliche Releases)</span><span class="sxs-lookup"><span data-stu-id="14058-133">Branch name: for example, `release/3.1.1xx` or `master` (for nightly releases).</span></span> <span data-ttu-id="14058-134">Verwenden Sie diese Option, um eine Version aus einem Vorschaukanal zu installieren.</span><span class="sxs-lookup"><span data-stu-id="14058-134">Use this option to install a version from a preview channel.</span></span> <span data-ttu-id="14058-135">Verwenden Sie den Namen des Kanals wie dieser unter [Installer und Binärdateien](https://github.com/dotnet/core-sdk#installers-and-binaries) aufgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="14058-135">Use the name of the channel as listed in [Installers and Binaries](https://github.com/dotnet/core-sdk#installers-and-binaries).</span></span>

  <span data-ttu-id="14058-136">Der Standardwert ist `LTS`.</span><span class="sxs-lookup"><span data-stu-id="14058-136">The default value is `LTS`.</span></span> <span data-ttu-id="14058-137">Weitere Informationen zu .NET-Supportkanälen finden Sie auf der Seite [.NET-Supportrichtlinie](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="14058-137">For more information on .NET support channels, see the [.NET Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) page.</span></span>

- **`-Version|--version <VERSION>`**

  <span data-ttu-id="14058-138">Stellt eine bestimmte Buildversion dar.</span><span class="sxs-lookup"><span data-stu-id="14058-138">Represents a specific build version.</span></span> <span data-ttu-id="14058-139">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="14058-139">The possible values are:</span></span>

  - <span data-ttu-id="14058-140">`latest` – der neueste Build auf dem Kanal (mit der `-Channel`-Option verwendet).</span><span class="sxs-lookup"><span data-stu-id="14058-140">`latest` - Latest build on the channel (used with the `-Channel` option).</span></span>
  - <span data-ttu-id="14058-141">`coherent` – neuester kohärenter Build auf dem Kanal; verwendet die neueste stabile Paketkombination (mit Branchname-`-Channel`-Optionen verwendet).</span><span class="sxs-lookup"><span data-stu-id="14058-141">`coherent` - Latest coherent build on the channel; uses the latest stable package combination (used with Branch name `-Channel` options).</span></span>
  - <span data-ttu-id="14058-142">Dreiteilige Version im X.Y.Z-Format, die eine bestimmte Buildversion darstellt; sie hat Vorrang vor der `-Channel`-Option.</span><span class="sxs-lookup"><span data-stu-id="14058-142">Three-part version in X.Y.Z format representing a specific build version; supersedes the `-Channel` option.</span></span> <span data-ttu-id="14058-143">Beispiel: `2.0.0-preview2-006120`.</span><span class="sxs-lookup"><span data-stu-id="14058-143">For example: `2.0.0-preview2-006120`.</span></span>

  <span data-ttu-id="14058-144">Wenn nichts angegeben ist, wird für `-Version` standardmäßig `latest` verwendet.</span><span class="sxs-lookup"><span data-stu-id="14058-144">If not specified, `-Version` defaults to `latest`.</span></span>

- **`-JSonFile|--jsonfile <JSONFILE>`**

  <span data-ttu-id="14058-145">Gibt einen Pfad zu einer [global.json](global-json.md)-Datei an, die zur Bestimmung der SDK-Version verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="14058-145">Specifies a path to a [global.json](global-json.md) file that will be used to determine the SDK version.</span></span> <span data-ttu-id="14058-146">Die Datei *global.json* muss einen Wert für `sdk:version` haben.</span><span class="sxs-lookup"><span data-stu-id="14058-146">The *global.json* file must have a value for `sdk:version`.</span></span>

- **`-InstallDir|--install-dir <DIRECTORY>`**

  <span data-ttu-id="14058-147">Gibt den Installationspfad an.</span><span class="sxs-lookup"><span data-stu-id="14058-147">Specifies the installation path.</span></span> <span data-ttu-id="14058-148">Das Verzeichnis wird erstellt, wenn es nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="14058-148">The directory is created if it doesn't exist.</span></span> <span data-ttu-id="14058-149">Der Standardwert ist *%LocalAppData%\Microsoft\dotnet*.</span><span class="sxs-lookup"><span data-stu-id="14058-149">The default value is *%LocalAppData%\Microsoft\dotnet*.</span></span> <span data-ttu-id="14058-150">Binärdateien werden direkt im Verzeichnis platziert.</span><span class="sxs-lookup"><span data-stu-id="14058-150">Binaries are placed directly in this directory.</span></span>

- **`-Architecture|--architecture <ARCHITECTURE>`**

  <span data-ttu-id="14058-151">Architektur der zu installierenden .NET Core-Binärdateien.</span><span class="sxs-lookup"><span data-stu-id="14058-151">Architecture of the .NET Core binaries to install.</span></span> <span data-ttu-id="14058-152">Mögliche Werte sind `<auto>`, `amd64`, `x64`, `x86`, `arm64` und `arm`.</span><span class="sxs-lookup"><span data-stu-id="14058-152">Possible values are `<auto>`, `amd64`, `x64`, `x86`, `arm64`, and `arm`.</span></span> <span data-ttu-id="14058-153">Der Standardwert ist `<auto>`, was die derzeit ausgeführte Betriebssystemarchitektur darstellt.</span><span class="sxs-lookup"><span data-stu-id="14058-153">The default value is `<auto>`, which represents the currently running OS architecture.</span></span>

- **`-SharedRuntime|--shared-runtime`**

  > [!NOTE]
  > <span data-ttu-id="14058-154">Dieser Parameter ist veraltet und wird in einer zukünftigen Version des Skripts möglicherweise entfernt.</span><span class="sxs-lookup"><span data-stu-id="14058-154">This parameter is obsolete and may be removed in a future version of the script.</span></span> <span data-ttu-id="14058-155">Die empfohlene Alternative ist die `-Runtime|--runtime`-Option.</span><span class="sxs-lookup"><span data-stu-id="14058-155">The recommended alternative is the `-Runtime|--runtime` option.</span></span>

  <span data-ttu-id="14058-156">Es werden nur die freigegebenen Runtimebestandteile installiert und nicht das gesamte SDK.</span><span class="sxs-lookup"><span data-stu-id="14058-156">Installs just the shared runtime bits, not the entire SDK.</span></span> <span data-ttu-id="14058-157">Diese Option entspricht der Angabe von `-Runtime|--runtime dotnet`.</span><span class="sxs-lookup"><span data-stu-id="14058-157">This option is equivalent to specifying `-Runtime|--runtime dotnet`.</span></span>

- **`-Runtime|--runtime <RUNTIME>`**

  <span data-ttu-id="14058-158">Es wird nur die freigegebene Runtime installiert und nicht das gesamte SDK.</span><span class="sxs-lookup"><span data-stu-id="14058-158">Installs just the shared runtime, not the entire SDK.</span></span> <span data-ttu-id="14058-159">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="14058-159">The possible values are:</span></span>

  - <span data-ttu-id="14058-160">`dotnet` – die freigegebene Runtime von `Microsoft.NETCore.App`.</span><span class="sxs-lookup"><span data-stu-id="14058-160">`dotnet` - the `Microsoft.NETCore.App` shared runtime.</span></span>
  - <span data-ttu-id="14058-161">`aspnetcore` – die freigegebene Runtime von `Microsoft.AspNetCore.App`.</span><span class="sxs-lookup"><span data-stu-id="14058-161">`aspnetcore` - the `Microsoft.AspNetCore.App` shared runtime.</span></span>
  - <span data-ttu-id="14058-162">`windowsdesktop` – die freigegebene Runtime von `Microsoft.WindowsDesktop.App`.</span><span class="sxs-lookup"><span data-stu-id="14058-162">`windowsdesktop` - the `Microsoft.WindowsDesktop.App` shared runtime.</span></span>

- **`-DryRun|--dry-run`**

  <span data-ttu-id="14058-163">Wenn festgelegt, führt das Skript die Installation nicht aus.</span><span class="sxs-lookup"><span data-stu-id="14058-163">If set, the script won't perform the installation.</span></span> <span data-ttu-id="14058-164">Es zeigt stattdessen an, welche Befehlszeile verwendet werden soll, um die derzeit erforderliche Version der .NET Core-CLI konsistent zu installieren.</span><span class="sxs-lookup"><span data-stu-id="14058-164">Instead, it displays what command line to use to consistently install the currently requested version of the .NET Core CLI.</span></span> <span data-ttu-id="14058-165">Wenn Sie z.B. Version `latest` angeben, wird eine Verbindung mit der bestimmten Version angezeigt, damit dieser Befehl deterministisch in einem Buildskript verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="14058-165">For example, if you specify version `latest`, it displays a link with the specific version so that this command can be used deterministically in a build script.</span></span> <span data-ttu-id="14058-166">Außerdem wird der Speicherort der Binärdatei angezeigt, wenn Sie sie selbst installieren oder herunterladen möchten.</span><span class="sxs-lookup"><span data-stu-id="14058-166">It also displays the binary's location if you prefer to install or download it yourself.</span></span>

- **`-NoPath|--no-path`**

  <span data-ttu-id="14058-167">Wenn festgelegt, wird der Installationsordner nicht in den Pfad für die aktuelle Sitzung exportiert.</span><span class="sxs-lookup"><span data-stu-id="14058-167">If set, the installation folder isn't exported to the path for the current session.</span></span> <span data-ttu-id="14058-168">Standardmäßig ändert das Skript den Pfad, wodurch die .NET Core-CLI sofort nach der Installation zur Verfügung gestellt wird.</span><span class="sxs-lookup"><span data-stu-id="14058-168">By default, the script modifies the PATH, which makes the .NET Core CLI available immediately after install.</span></span>

- **`-Verbose|--verbose`**

  <span data-ttu-id="14058-169">Es werden Diagnoseinformationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="14058-169">Displays diagnostics information.</span></span>

- **`-AzureFeed|--azure-feed`**

  <span data-ttu-id="14058-170">Gibt die URL für den Azure-Feed für den Installer an.</span><span class="sxs-lookup"><span data-stu-id="14058-170">Specifies the URL for the Azure feed to the installer.</span></span> <span data-ttu-id="14058-171">Es wird nicht empfohlen, diesen Wert nicht zu ändern.</span><span class="sxs-lookup"><span data-stu-id="14058-171">We recommended that you don't change this value.</span></span> <span data-ttu-id="14058-172">Der Standardwert ist `https://dotnetcli.azureedge.net/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="14058-172">The default value is `https://dotnetcli.azureedge.net/dotnet`.</span></span>

- **`-UncachedFeed|--uncached-feed`**

  <span data-ttu-id="14058-173">Ermöglicht das Ändern der URL für den nicht zwischengespeicherten Feed, der von diesem Installer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="14058-173">Allows changing the URL for the uncached feed used by this installer.</span></span> <span data-ttu-id="14058-174">Es wird nicht empfohlen, diesen Wert nicht zu ändern.</span><span class="sxs-lookup"><span data-stu-id="14058-174">We recommended that you don't change this value.</span></span>

- **`-NoCdn|--no-cdn`**

  <span data-ttu-id="14058-175">Deaktiviert das Herunterladen aus dem [Azure Content Delivery Network (CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) und verwendet den nicht zwischengespeicherten Feed direkt.</span><span class="sxs-lookup"><span data-stu-id="14058-175">Disables downloading from the [Azure Content Delivery Network (CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) and uses the uncached feed directly.</span></span>

- **`-FeedCredential|--feed-credential`**

  <span data-ttu-id="14058-176">Wird als Abfragezeichenfolge zum Anfügen an den Azure-Feed verwendet.</span><span class="sxs-lookup"><span data-stu-id="14058-176">Used as a query string to append to the Azure feed.</span></span> <span data-ttu-id="14058-177">Ermöglicht das Ändern der URL, um nicht öffentliche Blob Storage-Konten verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="14058-177">It allows changing the URL to use non-public blob storage accounts.</span></span>

- **`--runtime-id`**

  <span data-ttu-id="14058-178">Gibt den [Runtimebezeichner](../rid-catalog.md) an, für den die Tools installiert werden.</span><span class="sxs-lookup"><span data-stu-id="14058-178">Specifies the [runtime identifier](../rid-catalog.md) for which the tools are being installed.</span></span> <span data-ttu-id="14058-179">Verwenden Sie `linux-x64` für portable Linux-Distributionen.</span><span class="sxs-lookup"><span data-stu-id="14058-179">Use `linux-x64` for portable Linux.</span></span> <span data-ttu-id="14058-180">(Nur für Linux und macOS gültig)</span><span class="sxs-lookup"><span data-stu-id="14058-180">(Only valid for Linux/macOS)</span></span>

- **`-ProxyAddress`**

  <span data-ttu-id="14058-181">Wenn festgelegt, verwendet das Installationsprogramm den Proxy bei der Durchführung von Webanfragen.</span><span class="sxs-lookup"><span data-stu-id="14058-181">If set, the installer uses the proxy when making web requests.</span></span> <span data-ttu-id="14058-182">(Nur gültig für Windows)</span><span class="sxs-lookup"><span data-stu-id="14058-182">(Only valid for Windows)</span></span>

- **`ProxyUseDefaultCredentials`**

  <span data-ttu-id="14058-183">Wenn festgelegt, verwendet der Installer bei Verwendung der Proxyadresse die Anmeldeinformationen des aktuellen Benutzers.</span><span class="sxs-lookup"><span data-stu-id="14058-183">If set, the installer uses the credentials of the current user when using proxy address.</span></span> <span data-ttu-id="14058-184">(Nur gültig für Windows)</span><span class="sxs-lookup"><span data-stu-id="14058-184">(Only valid for Windows)</span></span>

- **`-SkipNonVersionedFiles|--skip-non-versioned-files`**

  <span data-ttu-id="14058-185">Die Installation nicht versionierte Dateien, wie *dotnet.exe*, wird übersprungen, falls diese bereits vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="14058-185">Skips installing non-versioned files, such as *dotnet.exe*, if they already exist.</span></span>

- **`-Help|--help`**

  <span data-ttu-id="14058-186">Druckt Hilfe für das Skript aus.</span><span class="sxs-lookup"><span data-stu-id="14058-186">Prints out help for the script.</span></span>

## <a name="examples"></a><span data-ttu-id="14058-187">Beispiele</span><span class="sxs-lookup"><span data-stu-id="14058-187">Examples</span></span>

- <span data-ttu-id="14058-188">Installieren Sie die neueste langfristig unterstützte (Long-Term Supported, LTS) Version am Standardspeicherort:</span><span class="sxs-lookup"><span data-stu-id="14058-188">Install the latest long-term supported (LTS) version to the default location:</span></span>

  <span data-ttu-id="14058-189">Windows:</span><span class="sxs-lookup"><span data-stu-id="14058-189">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel LTS
  ```

  <span data-ttu-id="14058-190">Mac OS/Linux:</span><span class="sxs-lookup"><span data-stu-id="14058-190">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel LTS
  ```

- <span data-ttu-id="14058-191">Installieren Sie die aktuelle Version von Kanal 3.1 am angegebenen Speicherort:</span><span class="sxs-lookup"><span data-stu-id="14058-191">Install the latest version from 3.1 channel to the specified location:</span></span>

  <span data-ttu-id="14058-192">Windows:</span><span class="sxs-lookup"><span data-stu-id="14058-192">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel 3.1 -InstallDir C:\cli
  ```

  <span data-ttu-id="14058-193">Mac OS/Linux:</span><span class="sxs-lookup"><span data-stu-id="14058-193">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel 3.1 --install-dir ~/cli
  ```

- <span data-ttu-id="14058-194">Installieren Sie die Version 3.0.0 der Shared Runtime:</span><span class="sxs-lookup"><span data-stu-id="14058-194">Install the 3.0.0 version of the shared runtime:</span></span>

  <span data-ttu-id="14058-195">Windows:</span><span class="sxs-lookup"><span data-stu-id="14058-195">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Runtime dotnet -Version 3.0.0
  ```

  <span data-ttu-id="14058-196">Mac OS/Linux:</span><span class="sxs-lookup"><span data-stu-id="14058-196">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --runtime dotnet --version 3.0.0
  ```

- <span data-ttu-id="14058-197">Rufen Sie das Skript ab und installieren Sie die Version 2.1.2 hinter einem Unternehmensproxy (nur Windows):</span><span class="sxs-lookup"><span data-stu-id="14058-197">Obtain script and install the 2.1.2 version behind a corporate proxy (Windows only):</span></span>

  ```powershell
  Invoke-WebRequest 'https://dot.net/v1/dotnet-install.ps1' -Proxy $env:HTTP_PROXY -ProxyUseDefaultCredentials -OutFile 'dotnet-install.ps1';
  ./dotnet-install.ps1 -InstallDir '~/.dotnet' -Version '2.1.2' -ProxyAddress $env:HTTP_PROXY -ProxyUseDefaultCredentials;
  ```

- <span data-ttu-id="14058-198">Rufen Sie das Skript ab, und installieren Sie die Beispiele für die .NET Core-CLI:</span><span class="sxs-lookup"><span data-stu-id="14058-198">Obtain script and install .NET Core CLI one-liner examples:</span></span>

  <span data-ttu-id="14058-199">Windows:</span><span class="sxs-lookup"><span data-stu-id="14058-199">Windows:</span></span>

  ```powershell
  # Run a separate PowerShell process because the script calls exit, so it will end the current PowerShell session.
  &powershell -NoProfile -ExecutionPolicy unrestricted -Command "[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; &([scriptblock]::Create((Invoke-WebRequest -UseBasicParsing 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"
  ```

  <span data-ttu-id="14058-200">Mac OS/Linux:</span><span class="sxs-lookup"><span data-stu-id="14058-200">macOS/Linux:</span></span>

  ```bash
  curl -ssl https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>
  ```

## <a name="see-also"></a><span data-ttu-id="14058-201">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="14058-201">See also</span></span>

- [<span data-ttu-id="14058-202">.NET Core-Releases</span><span class="sxs-lookup"><span data-stu-id="14058-202">.NET Core releases</span></span>](https://github.com/dotnet/core/releases)
- [<span data-ttu-id="14058-203">Downloadarchiv von .NET Core Runtime und des SDK</span><span class="sxs-lookup"><span data-stu-id="14058-203">.NET Core Runtime and SDK download archive</span></span>](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)
