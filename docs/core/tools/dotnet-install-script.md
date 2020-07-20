---
title: Dotnet-Installationsskripts
description: Erfahren Sie mehr über die dotnet-Installationsskripts zur Installation des .NET Core SDK und der Shared Runtime.
ms.date: 04/30/2020
ms.openlocfilehash: cecfbb86c4a2863161d3df7c78201fa8057abfe5
ms.sourcegitcommit: 3492dafceb5d4183b6b0d2f3bdf4a1abc4d5ed8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2020
ms.locfileid: "86415925"
---
# <a name="dotnet-install-scripts-reference"></a><span data-ttu-id="0b00a-103">Dotnet-Installationsskripts Verweis</span><span class="sxs-lookup"><span data-stu-id="0b00a-103">dotnet-install scripts reference</span></span>

## <a name="name"></a><span data-ttu-id="0b00a-104">name</span><span class="sxs-lookup"><span data-stu-id="0b00a-104">Name</span></span>

<span data-ttu-id="0b00a-105">`dotnet-install.ps1` | `dotnet-install.sh`: Skript, mit dem das .NET Core SDK und die Shared Runtime installiert werden.</span><span class="sxs-lookup"><span data-stu-id="0b00a-105">`dotnet-install.ps1` | `dotnet-install.sh` - Script used to install the .NET Core SDK and the shared runtime.</span></span>

## <a name="synopsis"></a><span data-ttu-id="0b00a-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="0b00a-106">Synopsis</span></span>

<span data-ttu-id="0b00a-107">Windows:</span><span class="sxs-lookup"><span data-stu-id="0b00a-107">Windows:</span></span>

```powershell
dotnet-install.ps1 [-Architecture <ARCHITECTURE>] [-AzureFeed]
    [-Channel <CHANNEL>] [-DryRun] [-FeedCredential]
    [-InstallDir <DIRECTORY>] [-JSonFile <JSONFILE>]
    [-NoCdn] [-NoPath] [-ProxyAddress]
    [-ProxyUseDefaultCredentials] [-Runtime <RUNTIME>]
    [-SkipNonVersionedFiles] [-UncachedFeed] [-Verbose]
    [-Version <VERSION>]

Get-Help ./dotnet-install.ps1
```

<span data-ttu-id="0b00a-108">Linux/macOS:</span><span class="sxs-lookup"><span data-stu-id="0b00a-108">Linux/macOS:</span></span>

```bash
dotnet-install.sh  [--architecture <ARCHITECTURE>] [--azure-feed]
    [--channel <CHANNEL>] [--dry-run] [--feed-credential]
    [--install-dir <DIRECTORY>] [--jsonfile <JSONFILE>]
    [--no-cdn] [--no-path] [--runtime <RUNTIME>] [--runtime-id <RID>]
    [--skip-non-versioned-files] [--uncached-feed] [--verbose]
    [--version <VERSION>]

dotnet-install.sh --help
```

<span data-ttu-id="0b00a-109">Das Bash-Skript liest auch PowerShell-Schalter, sodass Sie PowerShell-Schalter mit dem Skript auf Linux/macOS-Systemen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="0b00a-109">The bash script also reads PowerShell switches, so you can use PowerShell switches with the script on Linux/macOS systems.</span></span>

## <a name="description"></a><span data-ttu-id="0b00a-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0b00a-110">Description</span></span>

<span data-ttu-id="0b00a-111">Die `dotnet-install`-Skripts werden verwendet, um eine Nicht-Administrator-Installation des .NET Core SDK durchzuführen, die die .NET Core-CLI und die freigegebene Runtime enthält.</span><span class="sxs-lookup"><span data-stu-id="0b00a-111">The `dotnet-install` scripts perform a non-admin installation of the .NET Core SDK, which includes the .NET Core CLI and the shared runtime.</span></span> <span data-ttu-id="0b00a-112">Es gibt zwei Skripts:</span><span class="sxs-lookup"><span data-stu-id="0b00a-112">There are two scripts:</span></span>

* <span data-ttu-id="0b00a-113">Ein PowerShell-Skript, das unter Windows verwendet werden kann</span><span class="sxs-lookup"><span data-stu-id="0b00a-113">A PowerShell script that works on Windows.</span></span>
* <span data-ttu-id="0b00a-114">Ein Bash-Skript für Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="0b00a-114">A bash script that works on Linux/macOS.</span></span>

### <a name="purpose"></a><span data-ttu-id="0b00a-115">Zweck</span><span class="sxs-lookup"><span data-stu-id="0b00a-115">Purpose</span></span>

 <span data-ttu-id="0b00a-116">Diese Skripts sind für die Verwendung in Continuous Integration-Szenarios (CI) konzipiert, in denen Folgendes zutrifft:</span><span class="sxs-lookup"><span data-stu-id="0b00a-116">The intended use of the scripts is for Continuous Integration (CI) scenarios, where:</span></span>

* <span data-ttu-id="0b00a-117">Das SDK muss ohne Benutzerinteraktion und ohne Administratorrechte installiert werden.</span><span class="sxs-lookup"><span data-stu-id="0b00a-117">The SDK needs to be installed without user interaction and without admin rights.</span></span>
* <span data-ttu-id="0b00a-118">Die SDK-Installation muss nicht für mehrere CI-Ausführungen beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="0b00a-118">The SDK installation doesn't need to persist across multiple CI runs.</span></span>

  <span data-ttu-id="0b00a-119">Die typische Sequenz für Ereignisse lautet folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="0b00a-119">The typical sequence of events:</span></span>
  * <span data-ttu-id="0b00a-120">Die CI wird ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="0b00a-120">CI is triggered.</span></span>
  * <span data-ttu-id="0b00a-121">Die CI installiert das SDK mithilfe eines dieser Skripts.</span><span class="sxs-lookup"><span data-stu-id="0b00a-121">CI installs the SDK using one of these scripts.</span></span>
  * <span data-ttu-id="0b00a-122">Die CI schließt ihre Aufgaben ab und bereinigt temporäre Daten einschließlich der SDK-Installation.</span><span class="sxs-lookup"><span data-stu-id="0b00a-122">CI finishes its work and clears temporary data including the SDK installation.</span></span>

<span data-ttu-id="0b00a-123">Verwenden Sie die Installationsprogramme anstatt dieser Skripts, um eine Entwicklungsumgebung einzurichten oder um Apps auszuführen.</span><span class="sxs-lookup"><span data-stu-id="0b00a-123">To set up a development environment or to run apps, use the installers rather than these scripts.</span></span>

### <a name="recommended-version"></a><span data-ttu-id="0b00a-124">Empfohlene Version</span><span class="sxs-lookup"><span data-stu-id="0b00a-124">Recommended version</span></span>

<span data-ttu-id="0b00a-125">Es wird empfohlen, die stabile Version der Skripts zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="0b00a-125">We recommend that you use the stable version of the scripts:</span></span>

- <span data-ttu-id="0b00a-126">Bash (Linux/macOS): <https://dot.net/v1/dotnet-install.sh></span><span class="sxs-lookup"><span data-stu-id="0b00a-126">Bash (Linux/macOS): <https://dot.net/v1/dotnet-install.sh></span></span>
- <span data-ttu-id="0b00a-127">PowerShell (Windows): <https://dot.net/v1/dotnet-install.ps1></span><span class="sxs-lookup"><span data-stu-id="0b00a-127">PowerShell (Windows): <https://dot.net/v1/dotnet-install.ps1></span></span>

### <a name="script-behavior"></a><span data-ttu-id="0b00a-128">Skriptverhalten</span><span class="sxs-lookup"><span data-stu-id="0b00a-128">Script behavior</span></span>

<span data-ttu-id="0b00a-129">Beide Skripts weisen das gleiche Verhalten auf.</span><span class="sxs-lookup"><span data-stu-id="0b00a-129">Both scripts have the same behavior.</span></span> <span data-ttu-id="0b00a-130">Sie laden die ZIP-/Tarball-Datei vom CLI-Build-Ablagespeicherort herunter und installieren sie entweder am Standardspeicherort oder an einem in `-InstallDir|--install-dir` angegebenen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="0b00a-130">They download the ZIP/tarball file from the CLI build drops and proceed to install it in either the default location or in a location specified by `-InstallDir|--install-dir`.</span></span>

<span data-ttu-id="0b00a-131">In der Standardeinstellung laden die Installationsskripts das SDK herunter und installieren es.</span><span class="sxs-lookup"><span data-stu-id="0b00a-131">By default, the installation scripts download the SDK and install it.</span></span> <span data-ttu-id="0b00a-132">Wenn Sie nur die freigegebene Laufzeit abrufen möchten, geben Sie das `-Runtime|--runtime`-Argument an.</span><span class="sxs-lookup"><span data-stu-id="0b00a-132">If you wish to only obtain the shared runtime, specify the `-Runtime|--runtime` argument.</span></span>

<span data-ttu-id="0b00a-133">In der Standardeinstellung fügt das Skript den Installationsort dem $PATH für die aktuelle Sitzung hinzu.</span><span class="sxs-lookup"><span data-stu-id="0b00a-133">By default, the script adds the install location to the $PATH for the current session.</span></span> <span data-ttu-id="0b00a-134">Überschreiben Sie dieses Standardverhalten, indem sie das `-NoPath|--no-path`-Argument angeben.</span><span class="sxs-lookup"><span data-stu-id="0b00a-134">Override this default behavior by specifying the `-NoPath|--no-path` argument.</span></span> <span data-ttu-id="0b00a-135">Das Skript legt die Umgebungsvariable `DOTNET_ROOT` nicht fest.</span><span class="sxs-lookup"><span data-stu-id="0b00a-135">The script doesn't set the `DOTNET_ROOT` environment variable.</span></span>

<span data-ttu-id="0b00a-136">Bevor Sie das Skript ausführen, installieren Sie die erforderlichen [Abhängigkeiten](../install/windows.md#dependencies).</span><span class="sxs-lookup"><span data-stu-id="0b00a-136">Before running the script, install the required [dependencies](../install/windows.md#dependencies).</span></span>

<span data-ttu-id="0b00a-137">Installieren Sie eine bestimmte Version mithilfe des Arguments `-Version|--version`.</span><span class="sxs-lookup"><span data-stu-id="0b00a-137">You can install a specific version using the `-Version|--version` argument.</span></span> <span data-ttu-id="0b00a-138">Die Version muss als dreiteilige Versionsnummer (z. B. `2.1.0`) angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="0b00a-138">The version must be specified as a three-part version number, such as `2.1.0`.</span></span> <span data-ttu-id="0b00a-139">Wenn die Version nicht angegeben wird, installiert das Skript die `latest`-Version.</span><span class="sxs-lookup"><span data-stu-id="0b00a-139">If the version isn't specified, the script installs the `latest` version.</span></span>

<span data-ttu-id="0b00a-140">Die Installationsskripts aktualisieren die Registrierung unter Windows nicht.</span><span class="sxs-lookup"><span data-stu-id="0b00a-140">The install scripts do not update the registry on Windows.</span></span> <span data-ttu-id="0b00a-141">Sie laden nur die gezippten Binärdateien herunter und kopieren sie in einen Ordner.</span><span class="sxs-lookup"><span data-stu-id="0b00a-141">They just download the zipped binaries and copy them to a folder.</span></span> <span data-ttu-id="0b00a-142">Wenn Sie möchten, dass die Registrierungsschlüsselwerte aktualisiert werden, verwenden Sie die .NET Core-Installationsprogramme.</span><span class="sxs-lookup"><span data-stu-id="0b00a-142">If you want registry key values to be updated, use the .NET Core installers.</span></span>

## <a name="options"></a><span data-ttu-id="0b00a-143">Optionen</span><span class="sxs-lookup"><span data-stu-id="0b00a-143">Options</span></span>

- **`-Architecture|--architecture <ARCHITECTURE>`**

  <span data-ttu-id="0b00a-144">Architektur der zu installierenden .NET Core-Binärdateien.</span><span class="sxs-lookup"><span data-stu-id="0b00a-144">Architecture of the .NET Core binaries to install.</span></span> <span data-ttu-id="0b00a-145">Mögliche Werte sind `<auto>`, `amd64`, `x64`, `x86`, `arm64` und `arm`.</span><span class="sxs-lookup"><span data-stu-id="0b00a-145">Possible values are `<auto>`, `amd64`, `x64`, `x86`, `arm64`, and `arm`.</span></span> <span data-ttu-id="0b00a-146">Der Standardwert ist `<auto>`, was die derzeit ausgeführte Betriebssystemarchitektur darstellt.</span><span class="sxs-lookup"><span data-stu-id="0b00a-146">The default value is `<auto>`, which represents the currently running OS architecture.</span></span>

- **`-AzureFeed|--azure-feed`**

  <span data-ttu-id="0b00a-147">Gibt die URL für den Azure-Feed für den Installer an.</span><span class="sxs-lookup"><span data-stu-id="0b00a-147">Specifies the URL for the Azure feed to the installer.</span></span> <span data-ttu-id="0b00a-148">Es wird nicht empfohlen, diesen Wert nicht zu ändern.</span><span class="sxs-lookup"><span data-stu-id="0b00a-148">We recommended that you don't change this value.</span></span> <span data-ttu-id="0b00a-149">Der Standardwert ist `https://dotnetcli.azureedge.net/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="0b00a-149">The default value is `https://dotnetcli.azureedge.net/dotnet`.</span></span>

- **`-Channel|--channel <CHANNEL>`**

  <span data-ttu-id="0b00a-150">Gibt den Quellkanal für die Installation an.</span><span class="sxs-lookup"><span data-stu-id="0b00a-150">Specifies the source channel for the installation.</span></span> <span data-ttu-id="0b00a-151">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="0b00a-151">The possible values are:</span></span>

  - <span data-ttu-id="0b00a-152">`Current` – Aktuelles Release.</span><span class="sxs-lookup"><span data-stu-id="0b00a-152">`Current` - Most current release.</span></span>
  - <span data-ttu-id="0b00a-153">`LTS`: Long Term Support-Kanal (aktuell unterstütztes Release).</span><span class="sxs-lookup"><span data-stu-id="0b00a-153">`LTS` - Long-Term Support channel (most current supported release).</span></span>
  - <span data-ttu-id="0b00a-154">Zweiteilige Version im X.Y-Format, das eine bestimmte Version darstellt (z.B. `2.1` oder `3.0`).</span><span class="sxs-lookup"><span data-stu-id="0b00a-154">Two-part version in X.Y format representing a specific release (for example, `2.1` or `3.0`).</span></span>
  - <span data-ttu-id="0b00a-155">Branchname: zum Beispiel `release/3.1.1xx` oder `master` (für nächtliche Releases)</span><span class="sxs-lookup"><span data-stu-id="0b00a-155">Branch name: for example, `release/3.1.1xx` or `master` (for nightly releases).</span></span> <span data-ttu-id="0b00a-156">Verwenden Sie diese Option, um eine Version aus einem Vorschaukanal zu installieren.</span><span class="sxs-lookup"><span data-stu-id="0b00a-156">Use this option to install a version from a preview channel.</span></span> <span data-ttu-id="0b00a-157">Verwenden Sie den Namen des Kanals wie dieser unter [Installer und Binärdateien](https://github.com/dotnet/core-sdk#installers-and-binaries) aufgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0b00a-157">Use the name of the channel as listed in [Installers and Binaries](https://github.com/dotnet/core-sdk#installers-and-binaries).</span></span>

  <span data-ttu-id="0b00a-158">Der Standardwert ist `LTS`.</span><span class="sxs-lookup"><span data-stu-id="0b00a-158">The default value is `LTS`.</span></span> <span data-ttu-id="0b00a-159">Weitere Informationen zu .NET-Supportkanälen finden Sie auf der Seite [.NET-Supportrichtlinie](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="0b00a-159">For more information on .NET support channels, see the [.NET Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) page.</span></span>

- **`-DryRun|--dry-run`**

  <span data-ttu-id="0b00a-160">Wenn festgelegt, führt das Skript die Installation nicht aus.</span><span class="sxs-lookup"><span data-stu-id="0b00a-160">If set, the script won't perform the installation.</span></span> <span data-ttu-id="0b00a-161">Es zeigt stattdessen an, welche Befehlszeile verwendet werden soll, um die derzeit erforderliche Version der .NET Core-CLI konsistent zu installieren.</span><span class="sxs-lookup"><span data-stu-id="0b00a-161">Instead, it displays what command line to use to consistently install the currently requested version of the .NET Core CLI.</span></span> <span data-ttu-id="0b00a-162">Wenn Sie z.B. Version `latest` angeben, wird eine Verbindung mit der bestimmten Version angezeigt, damit dieser Befehl deterministisch in einem Buildskript verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="0b00a-162">For example, if you specify version `latest`, it displays a link with the specific version so that this command can be used deterministically in a build script.</span></span> <span data-ttu-id="0b00a-163">Außerdem wird der Speicherort der Binärdatei angezeigt, wenn Sie sie selbst installieren oder herunterladen möchten.</span><span class="sxs-lookup"><span data-stu-id="0b00a-163">It also displays the binary's location if you prefer to install or download it yourself.</span></span>

- **`-FeedCredential|--feed-credential`**

  <span data-ttu-id="0b00a-164">Wird als Abfragezeichenfolge zum Anfügen an den Azure-Feed verwendet.</span><span class="sxs-lookup"><span data-stu-id="0b00a-164">Used as a query string to append to the Azure feed.</span></span> <span data-ttu-id="0b00a-165">Ermöglicht das Ändern der URL, um nicht öffentliche Blob Storage-Konten verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="0b00a-165">It allows changing the URL to use non-public blob storage accounts.</span></span>

- **`--help`**

  <span data-ttu-id="0b00a-166">Druckt Hilfe für das Skript aus.</span><span class="sxs-lookup"><span data-stu-id="0b00a-166">Prints out help for the script.</span></span> <span data-ttu-id="0b00a-167">Gilt nur für das Bash-Skript.</span><span class="sxs-lookup"><span data-stu-id="0b00a-167">Applies only to bash script.</span></span> <span data-ttu-id="0b00a-168">Verwenden Sie `Get-Help ./dotnet-install.ps1` für PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0b00a-168">For PowerShell, use `Get-Help ./dotnet-install.ps1`.</span></span>

- **`-InstallDir|--install-dir <DIRECTORY>`**

  <span data-ttu-id="0b00a-169">Gibt den Installationspfad an.</span><span class="sxs-lookup"><span data-stu-id="0b00a-169">Specifies the installation path.</span></span> <span data-ttu-id="0b00a-170">Das Verzeichnis wird erstellt, wenn es nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="0b00a-170">The directory is created if it doesn't exist.</span></span> <span data-ttu-id="0b00a-171">Der Standardwert ist *%LocalAppData%\Microsoft\dotnet* unter Windows und */usr/share/dotnet* unter Linux/macOS.</span><span class="sxs-lookup"><span data-stu-id="0b00a-171">The default value is *%LocalAppData%\Microsoft\dotnet* on Windows and */usr/share/dotnet* on Linux/macOS.</span></span> <span data-ttu-id="0b00a-172">Binärdateien werden direkt im Verzeichnis platziert.</span><span class="sxs-lookup"><span data-stu-id="0b00a-172">Binaries are placed directly in this directory.</span></span>

- **`-JSonFile|--jsonfile <JSONFILE>`**

  <span data-ttu-id="0b00a-173">Gibt einen Pfad zu einer [global.json](global-json.md)-Datei an, die zur Bestimmung der SDK-Version verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0b00a-173">Specifies a path to a [global.json](global-json.md) file that will be used to determine the SDK version.</span></span> <span data-ttu-id="0b00a-174">Die Datei *global.json* muss einen Wert für `sdk:version` haben.</span><span class="sxs-lookup"><span data-stu-id="0b00a-174">The *global.json* file must have a value for `sdk:version`.</span></span>

- **`-NoCdn|--no-cdn`**

  <span data-ttu-id="0b00a-175">Deaktiviert das Herunterladen aus dem [Azure Content Delivery Network (CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) und verwendet den nicht zwischengespeicherten Feed direkt.</span><span class="sxs-lookup"><span data-stu-id="0b00a-175">Disables downloading from the [Azure Content Delivery Network (CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) and uses the uncached feed directly.</span></span>

- **`-NoPath|--no-path`**

  <span data-ttu-id="0b00a-176">Wenn festgelegt, wird der Installationsordner nicht in den Pfad für die aktuelle Sitzung exportiert.</span><span class="sxs-lookup"><span data-stu-id="0b00a-176">If set, the installation folder isn't exported to the path for the current session.</span></span> <span data-ttu-id="0b00a-177">Standardmäßig ändert das Skript den Pfad, wodurch die .NET Core-CLI sofort nach der Installation zur Verfügung gestellt wird.</span><span class="sxs-lookup"><span data-stu-id="0b00a-177">By default, the script modifies the PATH, which makes the .NET Core CLI available immediately after install.</span></span>

- **`-ProxyAddress`**

  <span data-ttu-id="0b00a-178">Wenn festgelegt, verwendet das Installationsprogramm den Proxy bei der Durchführung von Webanfragen.</span><span class="sxs-lookup"><span data-stu-id="0b00a-178">If set, the installer uses the proxy when making web requests.</span></span> <span data-ttu-id="0b00a-179">(Nur gültig für Windows)</span><span class="sxs-lookup"><span data-stu-id="0b00a-179">(Only valid for Windows.)</span></span>

- **`ProxyUseDefaultCredentials`**

  <span data-ttu-id="0b00a-180">Wenn festgelegt, verwendet der Installer bei Verwendung der Proxyadresse die Anmeldeinformationen des aktuellen Benutzers.</span><span class="sxs-lookup"><span data-stu-id="0b00a-180">If set, the installer uses the credentials of the current user when using proxy address.</span></span> <span data-ttu-id="0b00a-181">(Nur gültig für Windows)</span><span class="sxs-lookup"><span data-stu-id="0b00a-181">(Only valid for Windows.)</span></span>

- **`-Runtime|--runtime <RUNTIME>`**

  <span data-ttu-id="0b00a-182">Es wird nur die freigegebene Runtime installiert und nicht das gesamte SDK.</span><span class="sxs-lookup"><span data-stu-id="0b00a-182">Installs just the shared runtime, not the entire SDK.</span></span> <span data-ttu-id="0b00a-183">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="0b00a-183">The possible values are:</span></span>

  - <span data-ttu-id="0b00a-184">`dotnet` – die freigegebene Runtime von `Microsoft.NETCore.App`.</span><span class="sxs-lookup"><span data-stu-id="0b00a-184">`dotnet` - the `Microsoft.NETCore.App` shared runtime.</span></span>
  - <span data-ttu-id="0b00a-185">`aspnetcore` – die freigegebene Runtime von `Microsoft.AspNetCore.App`.</span><span class="sxs-lookup"><span data-stu-id="0b00a-185">`aspnetcore` - the `Microsoft.AspNetCore.App` shared runtime.</span></span>
  - <span data-ttu-id="0b00a-186">`windowsdesktop` – die freigegebene Runtime von `Microsoft.WindowsDesktop.App`.</span><span class="sxs-lookup"><span data-stu-id="0b00a-186">`windowsdesktop` - the `Microsoft.WindowsDesktop.App` shared runtime.</span></span>

- **`--runtime-id <RID>`**

  <span data-ttu-id="0b00a-187">Gibt den [Runtimebezeichner](../rid-catalog.md) an, für den die Tools installiert werden.</span><span class="sxs-lookup"><span data-stu-id="0b00a-187">Specifies the [runtime identifier](../rid-catalog.md) for which the tools are being installed.</span></span> <span data-ttu-id="0b00a-188">Verwenden Sie `linux-x64` für portable Linux-Distributionen.</span><span class="sxs-lookup"><span data-stu-id="0b00a-188">Use `linux-x64` for portable Linux.</span></span> <span data-ttu-id="0b00a-189">(Nur gültig für Linux und macOS)</span><span class="sxs-lookup"><span data-stu-id="0b00a-189">(Only valid for Linux/macOS.)</span></span>

- **`-SharedRuntime|--shared-runtime`**

  > [!NOTE]
  > <span data-ttu-id="0b00a-190">Dieser Parameter ist veraltet und wird in einer zukünftigen Version des Skripts möglicherweise entfernt.</span><span class="sxs-lookup"><span data-stu-id="0b00a-190">This parameter is obsolete and may be removed in a future version of the script.</span></span> <span data-ttu-id="0b00a-191">Die empfohlene Alternative ist die `-Runtime|--runtime`-Option.</span><span class="sxs-lookup"><span data-stu-id="0b00a-191">The recommended alternative is the `-Runtime|--runtime` option.</span></span>

  <span data-ttu-id="0b00a-192">Es werden nur die freigegebenen Runtimebestandteile installiert und nicht das gesamte SDK.</span><span class="sxs-lookup"><span data-stu-id="0b00a-192">Installs just the shared runtime bits, not the entire SDK.</span></span> <span data-ttu-id="0b00a-193">Diese Option entspricht der Angabe von `-Runtime|--runtime dotnet`.</span><span class="sxs-lookup"><span data-stu-id="0b00a-193">This option is equivalent to specifying `-Runtime|--runtime dotnet`.</span></span>

- **`-SkipNonVersionedFiles|--skip-non-versioned-files`**

  <span data-ttu-id="0b00a-194">Die Installation nicht versionierte Dateien, wie *dotnet.exe*, wird übersprungen, falls diese bereits vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="0b00a-194">Skips installing non-versioned files, such as *dotnet.exe*, if they already exist.</span></span>

- **`-UncachedFeed|--uncached-feed`**

  <span data-ttu-id="0b00a-195">Ermöglicht das Ändern der URL für den nicht zwischengespeicherten Feed, der von diesem Installer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0b00a-195">Allows changing the URL for the uncached feed used by this installer.</span></span> <span data-ttu-id="0b00a-196">Es wird nicht empfohlen, diesen Wert nicht zu ändern.</span><span class="sxs-lookup"><span data-stu-id="0b00a-196">We recommended that you don't change this value.</span></span>

- **`-Verbose|--verbose`**

  <span data-ttu-id="0b00a-197">Es werden Diagnoseinformationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0b00a-197">Displays diagnostics information.</span></span>

- **`-Version|--version <VERSION>`**

  <span data-ttu-id="0b00a-198">Stellt eine bestimmte Buildversion dar.</span><span class="sxs-lookup"><span data-stu-id="0b00a-198">Represents a specific build version.</span></span> <span data-ttu-id="0b00a-199">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="0b00a-199">The possible values are:</span></span>

  - <span data-ttu-id="0b00a-200">`latest` – der neueste Build auf dem Kanal (mit der `-Channel`-Option verwendet).</span><span class="sxs-lookup"><span data-stu-id="0b00a-200">`latest` - Latest build on the channel (used with the `-Channel` option).</span></span>
  - <span data-ttu-id="0b00a-201">`coherent` – neuester kohärenter Build auf dem Kanal; verwendet die neueste stabile Paketkombination (mit Branchname-`-Channel`-Optionen verwendet).</span><span class="sxs-lookup"><span data-stu-id="0b00a-201">`coherent` - Latest coherent build on the channel; uses the latest stable package combination (used with Branch name `-Channel` options).</span></span>
  - <span data-ttu-id="0b00a-202">Dreiteilige Version im X.Y.Z-Format, die eine bestimmte Buildversion darstellt; sie hat Vorrang vor der `-Channel`-Option.</span><span class="sxs-lookup"><span data-stu-id="0b00a-202">Three-part version in X.Y.Z format representing a specific build version; supersedes the `-Channel` option.</span></span> <span data-ttu-id="0b00a-203">Beispiel: `2.0.0-preview2-006120`.</span><span class="sxs-lookup"><span data-stu-id="0b00a-203">For example: `2.0.0-preview2-006120`.</span></span>

  <span data-ttu-id="0b00a-204">Wenn nichts angegeben ist, wird für `-Version` standardmäßig `latest` verwendet.</span><span class="sxs-lookup"><span data-stu-id="0b00a-204">If not specified, `-Version` defaults to `latest`.</span></span>

## <a name="examples"></a><span data-ttu-id="0b00a-205">Beispiele</span><span class="sxs-lookup"><span data-stu-id="0b00a-205">Examples</span></span>

- <span data-ttu-id="0b00a-206">Installieren Sie die neueste langfristig unterstützte (Long-Term Supported, LTS) Version am Standardspeicherort:</span><span class="sxs-lookup"><span data-stu-id="0b00a-206">Install the latest long-term supported (LTS) version to the default location:</span></span>

  <span data-ttu-id="0b00a-207">Windows:</span><span class="sxs-lookup"><span data-stu-id="0b00a-207">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel LTS
  ```

  <span data-ttu-id="0b00a-208">Mac OS/Linux:</span><span class="sxs-lookup"><span data-stu-id="0b00a-208">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel LTS
  ```

- <span data-ttu-id="0b00a-209">Installieren Sie die aktuelle Version von Kanal 3.1 am angegebenen Speicherort:</span><span class="sxs-lookup"><span data-stu-id="0b00a-209">Install the latest version from 3.1 channel to the specified location:</span></span>

  <span data-ttu-id="0b00a-210">Windows:</span><span class="sxs-lookup"><span data-stu-id="0b00a-210">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel 3.1 -InstallDir C:\cli
  ```

  <span data-ttu-id="0b00a-211">Mac OS/Linux:</span><span class="sxs-lookup"><span data-stu-id="0b00a-211">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel 3.1 --install-dir ~/cli
  ```

- <span data-ttu-id="0b00a-212">Installieren Sie die Version 3.0.0 der Shared Runtime:</span><span class="sxs-lookup"><span data-stu-id="0b00a-212">Install the 3.0.0 version of the shared runtime:</span></span>

  <span data-ttu-id="0b00a-213">Windows:</span><span class="sxs-lookup"><span data-stu-id="0b00a-213">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Runtime dotnet -Version 3.0.0
  ```

  <span data-ttu-id="0b00a-214">Mac OS/Linux:</span><span class="sxs-lookup"><span data-stu-id="0b00a-214">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --runtime dotnet --version 3.0.0
  ```

- <span data-ttu-id="0b00a-215">Rufen Sie das Skript ab und installieren Sie die Version 2.1.2 hinter einem Unternehmensproxy (nur Windows):</span><span class="sxs-lookup"><span data-stu-id="0b00a-215">Obtain script and install the 2.1.2 version behind a corporate proxy (Windows only):</span></span>

  ```powershell
  Invoke-WebRequest 'https://dot.net/v1/dotnet-install.ps1' -Proxy $env:HTTP_PROXY -ProxyUseDefaultCredentials -OutFile 'dotnet-install.ps1';
  ./dotnet-install.ps1 -InstallDir '~/.dotnet' -Version '2.1.2' -ProxyAddress $env:HTTP_PROXY -ProxyUseDefaultCredentials;
  ```

- <span data-ttu-id="0b00a-216">Rufen Sie das Skript ab, und installieren Sie die Beispiele für die .NET Core-CLI:</span><span class="sxs-lookup"><span data-stu-id="0b00a-216">Obtain script and install .NET Core CLI one-liner examples:</span></span>

  <span data-ttu-id="0b00a-217">Windows:</span><span class="sxs-lookup"><span data-stu-id="0b00a-217">Windows:</span></span>

  ```powershell
  # Run a separate PowerShell process because the script calls exit, so it will end the current PowerShell session.
  &powershell -NoProfile -ExecutionPolicy unrestricted -Command "[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; &([scriptblock]::Create((Invoke-WebRequest -UseBasicParsing 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"
  ```

  <span data-ttu-id="0b00a-218">Mac OS/Linux:</span><span class="sxs-lookup"><span data-stu-id="0b00a-218">macOS/Linux:</span></span>

  ```bash
  curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>
  ```

## <a name="see-also"></a><span data-ttu-id="0b00a-219">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b00a-219">See also</span></span>

- [<span data-ttu-id="0b00a-220">.NET Core-Releases</span><span class="sxs-lookup"><span data-stu-id="0b00a-220">.NET Core releases</span></span>](https://github.com/dotnet/core/releases)
- [<span data-ttu-id="0b00a-221">Downloadarchiv von .NET Core Runtime und des SDK</span><span class="sxs-lookup"><span data-stu-id="0b00a-221">.NET Core Runtime and SDK download archive</span></span>](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)
