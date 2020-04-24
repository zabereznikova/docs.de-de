---
title: Dotnet-Installationsskripts
description: Erfahren Sie mehr über die dotnet-Installationsskripts zur Installation des .NET Core SDK und der Shared Runtime.
ms.date: 01/23/2020
ms.openlocfilehash: 591413a17db577560bd0324995066c8ea7a35895
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463677"
---
# <a name="dotnet-install-scripts-reference"></a><span data-ttu-id="805fe-103">Dotnet-Installationsskripts Verweis</span><span class="sxs-lookup"><span data-stu-id="805fe-103">dotnet-install scripts reference</span></span>

## <a name="name"></a><span data-ttu-id="805fe-104">name</span><span class="sxs-lookup"><span data-stu-id="805fe-104">Name</span></span>

<span data-ttu-id="805fe-105">`dotnet-install.ps1` | `dotnet-install.sh`: Skript, mit dem das .NET Core SDK und die Shared Runtime installiert werden.</span><span class="sxs-lookup"><span data-stu-id="805fe-105">`dotnet-install.ps1` | `dotnet-install.sh` - Script used to install the .NET Core SDK and the shared runtime.</span></span>

## <a name="synopsis"></a><span data-ttu-id="805fe-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="805fe-106">Synopsis</span></span>

<span data-ttu-id="805fe-107">Windows:</span><span class="sxs-lookup"><span data-stu-id="805fe-107">Windows:</span></span>

```powershell
dotnet-install.ps1 [-Architecture <ARCHITECTURE>] [-AzureFeed]
    [-Channel <CHANNEL>] [-DryRun] [-FeedCredential]
    [-InstallDir <DIRECTORY>] [-JSonFile <JSONFILE>]
    [-NoCdn] [-NoPath] [-ProxyAddress]
    [-ProxyUseDefaultCredentials] [-Runtime <RUNTIME>]
    [-SkipNonVersionedFiles] [-UncachedFeed] [-Verbose]
    [-Version <VERSION>]

dotnet-install.ps1 -Help
```

<span data-ttu-id="805fe-108">Linux/macOS:</span><span class="sxs-lookup"><span data-stu-id="805fe-108">Linux/macOs:</span></span>

```bash
dotnet-install.sh  [--architecture <ARCHITECTURE>] [--azure-feed]
    [--channel <CHANNEL>] [--dry-run] [--feed-credential]
    [--install-dir <DIRECTORY>] [--jsonfile <JSONFILE>]
    [--no-cdn] [--no-path] [--runtime <RUNTIME>] [--runtime-id <RID>]
    [--skip-non-versioned-files] [--uncached-feed] [--verbose]
    [--version <VERSION>]

dotnet-install.sh --help
```

## <a name="description"></a><span data-ttu-id="805fe-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="805fe-109">Description</span></span>

<span data-ttu-id="805fe-110">Die `dotnet-install`-Skripts werden verwendet, um eine Nicht-Administrator-Installation des .NET Core SDK durchzuführen, die die .NET Core-CLI und die freigegebene Runtime enthält.</span><span class="sxs-lookup"><span data-stu-id="805fe-110">The `dotnet-install` scripts are used to perform a non-admin installation of the .NET Core SDK, which includes the .NET Core CLI and the shared runtime.</span></span>

<span data-ttu-id="805fe-111">Es wird empfohlen, die stabile Version der Skripts zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="805fe-111">We recommend that you use the stable version of the scripts:</span></span>

- <span data-ttu-id="805fe-112">Bash (Linux/macOS): <https://dot.net/v1/dotnet-install.sh></span><span class="sxs-lookup"><span data-stu-id="805fe-112">Bash (Linux/macOS): <https://dot.net/v1/dotnet-install.sh></span></span>
- <span data-ttu-id="805fe-113">PowerShell (Windows): <https://dot.net/v1/dotnet-install.ps1></span><span class="sxs-lookup"><span data-stu-id="805fe-113">PowerShell (Windows): <https://dot.net/v1/dotnet-install.ps1></span></span>

<span data-ttu-id="805fe-114">Diese Skripts sind vor allem in Szenarios für die Automatisierung und Nicht-Administrator-Installationen nützlich.</span><span class="sxs-lookup"><span data-stu-id="805fe-114">The main usefulness of these scripts is in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="805fe-115">Es gibt zwei Skripts: eines für PowerShell unter Windows und ein Bash-Skript für Linux/macOS.</span><span class="sxs-lookup"><span data-stu-id="805fe-115">There are two scripts: one is a PowerShell script that works on Windows, and the other is a bash script that works on Linux/macOS.</span></span> <span data-ttu-id="805fe-116">Beide Skripts weisen das gleiche Verhalten auf.</span><span class="sxs-lookup"><span data-stu-id="805fe-116">Both scripts have the same behavior.</span></span> <span data-ttu-id="805fe-117">Das Bash-Skript liest auch PowerShell-Schalter, sodass Sie PowerShell-Schalter mit dem Skript auf Linux/macOS-Systemen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="805fe-117">The bash script also reads PowerShell switches, so you can use PowerShell switches with the script on Linux/macOS systems.</span></span>

<span data-ttu-id="805fe-118">Die Installationsskripts laden die ZIP/Tarball-Datei vom CLI-Build-Ablagespeicherort herunter und installieren sie entweder am Standardspeicherort oder an einem in `-InstallDir|--install-dir` angegebenen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="805fe-118">The installation scripts download the ZIP/tarball file from the CLI build drops and proceed to install it in either the default location or in a location specified by `-InstallDir|--install-dir`.</span></span> <span data-ttu-id="805fe-119">In der Standardeinstellung laden die Installationsskripts das SDK herunter und installieren es.</span><span class="sxs-lookup"><span data-stu-id="805fe-119">By default, the installation scripts download the SDK and install it.</span></span> <span data-ttu-id="805fe-120">Wenn Sie nur die freigegebene Laufzeit abrufen möchten, geben Sie das `-Runtime|--runtime`-Argument an.</span><span class="sxs-lookup"><span data-stu-id="805fe-120">If you wish to only obtain the shared runtime, specify the `-Runtime|--runtime` argument.</span></span>

<span data-ttu-id="805fe-121">In der Standardeinstellung fügt das Skript den Installationsort dem $PATH für die aktuelle Sitzung hinzu.</span><span class="sxs-lookup"><span data-stu-id="805fe-121">By default, the script adds the install location to the $PATH for the current session.</span></span> <span data-ttu-id="805fe-122">Überschreiben Sie dieses Standardverhalten, indem sie das `-NoPath|--no-path`-Argument angeben.</span><span class="sxs-lookup"><span data-stu-id="805fe-122">Override this default behavior by specifying the `-NoPath|--no-path` argument.</span></span>

<span data-ttu-id="805fe-123">Bevor Sie das Skript ausführen, installieren Sie die erforderlichen [Abhängigkeiten](../install/dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="805fe-123">Before running the script, install the required [dependencies](../install/dependencies.md).</span></span>

<span data-ttu-id="805fe-124">Installieren Sie eine bestimmte Version mithilfe des Arguments `-Version|--version`.</span><span class="sxs-lookup"><span data-stu-id="805fe-124">You can install a specific version using the `-Version|--version` argument.</span></span> <span data-ttu-id="805fe-125">Die Version muss als dreiteilige Version (z. B. `2.1.0`) angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="805fe-125">The version must be specified as a three-part version (for example, `2.1.0`).</span></span> <span data-ttu-id="805fe-126">Wenn nicht angegeben, wird die `latest`-Version verwendet.</span><span class="sxs-lookup"><span data-stu-id="805fe-126">If not provided, it uses the `latest` version.</span></span>

## <a name="options"></a><span data-ttu-id="805fe-127">Optionen</span><span class="sxs-lookup"><span data-stu-id="805fe-127">Options</span></span>

- **`-Architecture|--architecture <ARCHITECTURE>`**

  <span data-ttu-id="805fe-128">Architektur der zu installierenden .NET Core-Binärdateien.</span><span class="sxs-lookup"><span data-stu-id="805fe-128">Architecture of the .NET Core binaries to install.</span></span> <span data-ttu-id="805fe-129">Mögliche Werte sind `<auto>`, `amd64`, `x64`, `x86`, `arm64` und `arm`.</span><span class="sxs-lookup"><span data-stu-id="805fe-129">Possible values are `<auto>`, `amd64`, `x64`, `x86`, `arm64`, and `arm`.</span></span> <span data-ttu-id="805fe-130">Der Standardwert ist `<auto>`, was die derzeit ausgeführte Betriebssystemarchitektur darstellt.</span><span class="sxs-lookup"><span data-stu-id="805fe-130">The default value is `<auto>`, which represents the currently running OS architecture.</span></span>

- **`-AzureFeed|--azure-feed`**

  <span data-ttu-id="805fe-131">Gibt die URL für den Azure-Feed für den Installer an.</span><span class="sxs-lookup"><span data-stu-id="805fe-131">Specifies the URL for the Azure feed to the installer.</span></span> <span data-ttu-id="805fe-132">Es wird nicht empfohlen, diesen Wert nicht zu ändern.</span><span class="sxs-lookup"><span data-stu-id="805fe-132">We recommended that you don't change this value.</span></span> <span data-ttu-id="805fe-133">Der Standardwert ist `https://dotnetcli.azureedge.net/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="805fe-133">The default value is `https://dotnetcli.azureedge.net/dotnet`.</span></span>

- **`-Channel|--channel <CHANNEL>`**

  <span data-ttu-id="805fe-134">Gibt den Quellkanal für die Installation an.</span><span class="sxs-lookup"><span data-stu-id="805fe-134">Specifies the source channel for the installation.</span></span> <span data-ttu-id="805fe-135">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="805fe-135">The possible values are:</span></span>

  - <span data-ttu-id="805fe-136">`Current` – Aktuelles Release.</span><span class="sxs-lookup"><span data-stu-id="805fe-136">`Current` - Most current release.</span></span>
  - <span data-ttu-id="805fe-137">`LTS`: Long Term Support-Kanal (aktuell unterstütztes Release).</span><span class="sxs-lookup"><span data-stu-id="805fe-137">`LTS` - Long-Term Support channel (most current supported release).</span></span>
  - <span data-ttu-id="805fe-138">Zweiteilige Version im X.Y-Format, das eine bestimmte Version darstellt (z.B. `2.1` oder `3.0`).</span><span class="sxs-lookup"><span data-stu-id="805fe-138">Two-part version in X.Y format representing a specific release (for example, `2.1` or `3.0`).</span></span>
  - <span data-ttu-id="805fe-139">Branchname: zum Beispiel `release/3.1.1xx` oder `master` (für nächtliche Releases)</span><span class="sxs-lookup"><span data-stu-id="805fe-139">Branch name: for example, `release/3.1.1xx` or `master` (for nightly releases).</span></span> <span data-ttu-id="805fe-140">Verwenden Sie diese Option, um eine Version aus einem Vorschaukanal zu installieren.</span><span class="sxs-lookup"><span data-stu-id="805fe-140">Use this option to install a version from a preview channel.</span></span> <span data-ttu-id="805fe-141">Verwenden Sie den Namen des Kanals wie dieser unter [Installer und Binärdateien](https://github.com/dotnet/core-sdk#installers-and-binaries) aufgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="805fe-141">Use the name of the channel as listed in [Installers and Binaries](https://github.com/dotnet/core-sdk#installers-and-binaries).</span></span>

  <span data-ttu-id="805fe-142">Der Standardwert ist `LTS`.</span><span class="sxs-lookup"><span data-stu-id="805fe-142">The default value is `LTS`.</span></span> <span data-ttu-id="805fe-143">Weitere Informationen zu .NET-Supportkanälen finden Sie auf der Seite [.NET-Supportrichtlinie](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="805fe-143">For more information on .NET support channels, see the [.NET Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) page.</span></span>

- **`-DryRun|--dry-run`**

  <span data-ttu-id="805fe-144">Wenn festgelegt, führt das Skript die Installation nicht aus.</span><span class="sxs-lookup"><span data-stu-id="805fe-144">If set, the script won't perform the installation.</span></span> <span data-ttu-id="805fe-145">Es zeigt stattdessen an, welche Befehlszeile verwendet werden soll, um die derzeit erforderliche Version der .NET Core-CLI konsistent zu installieren.</span><span class="sxs-lookup"><span data-stu-id="805fe-145">Instead, it displays what command line to use to consistently install the currently requested version of the .NET Core CLI.</span></span> <span data-ttu-id="805fe-146">Wenn Sie z.B. Version `latest` angeben, wird eine Verbindung mit der bestimmten Version angezeigt, damit dieser Befehl deterministisch in einem Buildskript verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="805fe-146">For example, if you specify version `latest`, it displays a link with the specific version so that this command can be used deterministically in a build script.</span></span> <span data-ttu-id="805fe-147">Außerdem wird der Speicherort der Binärdatei angezeigt, wenn Sie sie selbst installieren oder herunterladen möchten.</span><span class="sxs-lookup"><span data-stu-id="805fe-147">It also displays the binary's location if you prefer to install or download it yourself.</span></span>

- **`-FeedCredential|--feed-credential`**

  <span data-ttu-id="805fe-148">Wird als Abfragezeichenfolge zum Anfügen an den Azure-Feed verwendet.</span><span class="sxs-lookup"><span data-stu-id="805fe-148">Used as a query string to append to the Azure feed.</span></span> <span data-ttu-id="805fe-149">Ermöglicht das Ändern der URL, um nicht öffentliche Blob Storage-Konten verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="805fe-149">It allows changing the URL to use non-public blob storage accounts.</span></span>

- **`-Help|--help`**

  <span data-ttu-id="805fe-150">Druckt Hilfe für das Skript aus.</span><span class="sxs-lookup"><span data-stu-id="805fe-150">Prints out help for the script.</span></span>

- **`-InstallDir|--install-dir <DIRECTORY>`**

  <span data-ttu-id="805fe-151">Gibt den Installationspfad an.</span><span class="sxs-lookup"><span data-stu-id="805fe-151">Specifies the installation path.</span></span> <span data-ttu-id="805fe-152">Das Verzeichnis wird erstellt, wenn es nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="805fe-152">The directory is created if it doesn't exist.</span></span> <span data-ttu-id="805fe-153">Der Standardwert ist *%LocalAppData%\Microsoft\dotnet*.</span><span class="sxs-lookup"><span data-stu-id="805fe-153">The default value is *%LocalAppData%\Microsoft\dotnet*.</span></span> <span data-ttu-id="805fe-154">Binärdateien werden direkt im Verzeichnis platziert.</span><span class="sxs-lookup"><span data-stu-id="805fe-154">Binaries are placed directly in this directory.</span></span>

- **`-JSonFile|--jsonfile <JSONFILE>`**

  <span data-ttu-id="805fe-155">Gibt einen Pfad zu einer [global.json](global-json.md)-Datei an, die zur Bestimmung der SDK-Version verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="805fe-155">Specifies a path to a [global.json](global-json.md) file that will be used to determine the SDK version.</span></span> <span data-ttu-id="805fe-156">Die Datei *global.json* muss einen Wert für `sdk:version` haben.</span><span class="sxs-lookup"><span data-stu-id="805fe-156">The *global.json* file must have a value for `sdk:version`.</span></span>

- **`-NoCdn|--no-cdn`**

  <span data-ttu-id="805fe-157">Deaktiviert das Herunterladen aus dem [Azure Content Delivery Network (CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) und verwendet den nicht zwischengespeicherten Feed direkt.</span><span class="sxs-lookup"><span data-stu-id="805fe-157">Disables downloading from the [Azure Content Delivery Network (CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) and uses the uncached feed directly.</span></span>

- **`-NoPath|--no-path`**

  <span data-ttu-id="805fe-158">Wenn festgelegt, wird der Installationsordner nicht in den Pfad für die aktuelle Sitzung exportiert.</span><span class="sxs-lookup"><span data-stu-id="805fe-158">If set, the installation folder isn't exported to the path for the current session.</span></span> <span data-ttu-id="805fe-159">Standardmäßig ändert das Skript den Pfad, wodurch die .NET Core-CLI sofort nach der Installation zur Verfügung gestellt wird.</span><span class="sxs-lookup"><span data-stu-id="805fe-159">By default, the script modifies the PATH, which makes the .NET Core CLI available immediately after install.</span></span>

- **`-ProxyAddress`**

  <span data-ttu-id="805fe-160">Wenn festgelegt, verwendet das Installationsprogramm den Proxy bei der Durchführung von Webanfragen.</span><span class="sxs-lookup"><span data-stu-id="805fe-160">If set, the installer uses the proxy when making web requests.</span></span> <span data-ttu-id="805fe-161">(Nur gültig für Windows)</span><span class="sxs-lookup"><span data-stu-id="805fe-161">(Only valid for Windows.)</span></span>

- **`ProxyUseDefaultCredentials`**

  <span data-ttu-id="805fe-162">Wenn festgelegt, verwendet der Installer bei Verwendung der Proxyadresse die Anmeldeinformationen des aktuellen Benutzers.</span><span class="sxs-lookup"><span data-stu-id="805fe-162">If set, the installer uses the credentials of the current user when using proxy address.</span></span> <span data-ttu-id="805fe-163">(Nur gültig für Windows)</span><span class="sxs-lookup"><span data-stu-id="805fe-163">(Only valid for Windows.)</span></span>

- **`-Runtime|--runtime <RUNTIME>`**

  <span data-ttu-id="805fe-164">Es wird nur die freigegebene Runtime installiert und nicht das gesamte SDK.</span><span class="sxs-lookup"><span data-stu-id="805fe-164">Installs just the shared runtime, not the entire SDK.</span></span> <span data-ttu-id="805fe-165">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="805fe-165">The possible values are:</span></span>

  - <span data-ttu-id="805fe-166">`dotnet` – die freigegebene Runtime von `Microsoft.NETCore.App`.</span><span class="sxs-lookup"><span data-stu-id="805fe-166">`dotnet` - the `Microsoft.NETCore.App` shared runtime.</span></span>
  - <span data-ttu-id="805fe-167">`aspnetcore` – die freigegebene Runtime von `Microsoft.AspNetCore.App`.</span><span class="sxs-lookup"><span data-stu-id="805fe-167">`aspnetcore` - the `Microsoft.AspNetCore.App` shared runtime.</span></span>
  - <span data-ttu-id="805fe-168">`windowsdesktop` – die freigegebene Runtime von `Microsoft.WindowsDesktop.App`.</span><span class="sxs-lookup"><span data-stu-id="805fe-168">`windowsdesktop` - the `Microsoft.WindowsDesktop.App` shared runtime.</span></span>

- **`--runtime-id <RID>`**

  <span data-ttu-id="805fe-169">Gibt den [Runtimebezeichner](../rid-catalog.md) an, für den die Tools installiert werden.</span><span class="sxs-lookup"><span data-stu-id="805fe-169">Specifies the [runtime identifier](../rid-catalog.md) for which the tools are being installed.</span></span> <span data-ttu-id="805fe-170">Verwenden Sie `linux-x64` für portable Linux-Distributionen.</span><span class="sxs-lookup"><span data-stu-id="805fe-170">Use `linux-x64` for portable Linux.</span></span> <span data-ttu-id="805fe-171">(Nur gültig für Linux und macOS)</span><span class="sxs-lookup"><span data-stu-id="805fe-171">(Only valid for Linux/macOS.)</span></span>

- **`-SharedRuntime|--shared-runtime`**

  > [!NOTE]
  > <span data-ttu-id="805fe-172">Dieser Parameter ist veraltet und wird in einer zukünftigen Version des Skripts möglicherweise entfernt.</span><span class="sxs-lookup"><span data-stu-id="805fe-172">This parameter is obsolete and may be removed in a future version of the script.</span></span> <span data-ttu-id="805fe-173">Die empfohlene Alternative ist die `-Runtime|--runtime`-Option.</span><span class="sxs-lookup"><span data-stu-id="805fe-173">The recommended alternative is the `-Runtime|--runtime` option.</span></span>

  <span data-ttu-id="805fe-174">Es werden nur die freigegebenen Runtimebestandteile installiert und nicht das gesamte SDK.</span><span class="sxs-lookup"><span data-stu-id="805fe-174">Installs just the shared runtime bits, not the entire SDK.</span></span> <span data-ttu-id="805fe-175">Diese Option entspricht der Angabe von `-Runtime|--runtime dotnet`.</span><span class="sxs-lookup"><span data-stu-id="805fe-175">This option is equivalent to specifying `-Runtime|--runtime dotnet`.</span></span>

- **`-SkipNonVersionedFiles|--skip-non-versioned-files`**

  <span data-ttu-id="805fe-176">Die Installation nicht versionierte Dateien, wie *dotnet.exe*, wird übersprungen, falls diese bereits vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="805fe-176">Skips installing non-versioned files, such as *dotnet.exe*, if they already exist.</span></span>

- **`-UncachedFeed|--uncached-feed`**

  <span data-ttu-id="805fe-177">Ermöglicht das Ändern der URL für den nicht zwischengespeicherten Feed, der von diesem Installer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="805fe-177">Allows changing the URL for the uncached feed used by this installer.</span></span> <span data-ttu-id="805fe-178">Es wird nicht empfohlen, diesen Wert nicht zu ändern.</span><span class="sxs-lookup"><span data-stu-id="805fe-178">We recommended that you don't change this value.</span></span>

- **`-Verbose|--verbose`**

  <span data-ttu-id="805fe-179">Es werden Diagnoseinformationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="805fe-179">Displays diagnostics information.</span></span>

- **`-Version|--version <VERSION>`**

  <span data-ttu-id="805fe-180">Stellt eine bestimmte Buildversion dar.</span><span class="sxs-lookup"><span data-stu-id="805fe-180">Represents a specific build version.</span></span> <span data-ttu-id="805fe-181">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="805fe-181">The possible values are:</span></span>

  - <span data-ttu-id="805fe-182">`latest` – der neueste Build auf dem Kanal (mit der `-Channel`-Option verwendet).</span><span class="sxs-lookup"><span data-stu-id="805fe-182">`latest` - Latest build on the channel (used with the `-Channel` option).</span></span>
  - <span data-ttu-id="805fe-183">`coherent` – neuester kohärenter Build auf dem Kanal; verwendet die neueste stabile Paketkombination (mit Branchname-`-Channel`-Optionen verwendet).</span><span class="sxs-lookup"><span data-stu-id="805fe-183">`coherent` - Latest coherent build on the channel; uses the latest stable package combination (used with Branch name `-Channel` options).</span></span>
  - <span data-ttu-id="805fe-184">Dreiteilige Version im X.Y.Z-Format, die eine bestimmte Buildversion darstellt; sie hat Vorrang vor der `-Channel`-Option.</span><span class="sxs-lookup"><span data-stu-id="805fe-184">Three-part version in X.Y.Z format representing a specific build version; supersedes the `-Channel` option.</span></span> <span data-ttu-id="805fe-185">Beispiel: `2.0.0-preview2-006120`.</span><span class="sxs-lookup"><span data-stu-id="805fe-185">For example: `2.0.0-preview2-006120`.</span></span>

  <span data-ttu-id="805fe-186">Wenn nichts angegeben ist, wird für `-Version` standardmäßig `latest` verwendet.</span><span class="sxs-lookup"><span data-stu-id="805fe-186">If not specified, `-Version` defaults to `latest`.</span></span>

## <a name="examples"></a><span data-ttu-id="805fe-187">Beispiele</span><span class="sxs-lookup"><span data-stu-id="805fe-187">Examples</span></span>

- <span data-ttu-id="805fe-188">Installieren Sie die neueste langfristig unterstützte (Long-Term Supported, LTS) Version am Standardspeicherort:</span><span class="sxs-lookup"><span data-stu-id="805fe-188">Install the latest long-term supported (LTS) version to the default location:</span></span>

  <span data-ttu-id="805fe-189">Windows:</span><span class="sxs-lookup"><span data-stu-id="805fe-189">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel LTS
  ```

  <span data-ttu-id="805fe-190">Mac OS/Linux:</span><span class="sxs-lookup"><span data-stu-id="805fe-190">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel LTS
  ```

- <span data-ttu-id="805fe-191">Installieren Sie die aktuelle Version von Kanal 3.1 am angegebenen Speicherort:</span><span class="sxs-lookup"><span data-stu-id="805fe-191">Install the latest version from 3.1 channel to the specified location:</span></span>

  <span data-ttu-id="805fe-192">Windows:</span><span class="sxs-lookup"><span data-stu-id="805fe-192">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel 3.1 -InstallDir C:\cli
  ```

  <span data-ttu-id="805fe-193">Mac OS/Linux:</span><span class="sxs-lookup"><span data-stu-id="805fe-193">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel 3.1 --install-dir ~/cli
  ```

- <span data-ttu-id="805fe-194">Installieren Sie die Version 3.0.0 der Shared Runtime:</span><span class="sxs-lookup"><span data-stu-id="805fe-194">Install the 3.0.0 version of the shared runtime:</span></span>

  <span data-ttu-id="805fe-195">Windows:</span><span class="sxs-lookup"><span data-stu-id="805fe-195">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Runtime dotnet -Version 3.0.0
  ```

  <span data-ttu-id="805fe-196">Mac OS/Linux:</span><span class="sxs-lookup"><span data-stu-id="805fe-196">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --runtime dotnet --version 3.0.0
  ```

- <span data-ttu-id="805fe-197">Rufen Sie das Skript ab und installieren Sie die Version 2.1.2 hinter einem Unternehmensproxy (nur Windows):</span><span class="sxs-lookup"><span data-stu-id="805fe-197">Obtain script and install the 2.1.2 version behind a corporate proxy (Windows only):</span></span>

  ```powershell
  Invoke-WebRequest 'https://dot.net/v1/dotnet-install.ps1' -Proxy $env:HTTP_PROXY -ProxyUseDefaultCredentials -OutFile 'dotnet-install.ps1';
  ./dotnet-install.ps1 -InstallDir '~/.dotnet' -Version '2.1.2' -ProxyAddress $env:HTTP_PROXY -ProxyUseDefaultCredentials;
  ```

- <span data-ttu-id="805fe-198">Rufen Sie das Skript ab, und installieren Sie die Beispiele für die .NET Core-CLI:</span><span class="sxs-lookup"><span data-stu-id="805fe-198">Obtain script and install .NET Core CLI one-liner examples:</span></span>

  <span data-ttu-id="805fe-199">Windows:</span><span class="sxs-lookup"><span data-stu-id="805fe-199">Windows:</span></span>

  ```powershell
  # Run a separate PowerShell process because the script calls exit, so it will end the current PowerShell session.
  &powershell -NoProfile -ExecutionPolicy unrestricted -Command "[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; &([scriptblock]::Create((Invoke-WebRequest -UseBasicParsing 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"
  ```

  <span data-ttu-id="805fe-200">Mac OS/Linux:</span><span class="sxs-lookup"><span data-stu-id="805fe-200">macOS/Linux:</span></span>

  ```bash
  curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>
  ```

## <a name="see-also"></a><span data-ttu-id="805fe-201">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="805fe-201">See also</span></span>

- [<span data-ttu-id="805fe-202">.NET Core-Releases</span><span class="sxs-lookup"><span data-stu-id="805fe-202">.NET Core releases</span></span>](https://github.com/dotnet/core/releases)
- [<span data-ttu-id="805fe-203">Downloadarchiv von .NET Core Runtime und des SDK</span><span class="sxs-lookup"><span data-stu-id="805fe-203">.NET Core Runtime and SDK download archive</span></span>](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)
