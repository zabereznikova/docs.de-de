---
title: 'Installieren von .NET unter Linux mithilfe von Snap: .NET'
description: In diesem Artikel wird veranschaulicht, wie Sie das .NET SDK oder die .NET-Runtime unter Linux mithilfe von Snap installieren.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: 741933b5ca6f01d73b388675fe7f8a43c4efb0f9
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970924"
---
# <a name="install-the-net-sdk-or-the-net-runtime-with-snap"></a><span data-ttu-id="e7351-103">Installieren des .NET SDK oder der .NET-Runtime mithilfe von Snap</span><span class="sxs-lookup"><span data-stu-id="e7351-103">Install the .NET SDK or the .NET Runtime with Snap</span></span>

<span data-ttu-id="e7351-104">Verwenden Sie ein Snap-Paket, um das .NET SDK oder die .NET-Runtime zu installieren.</span><span class="sxs-lookup"><span data-stu-id="e7351-104">Use a Snap package to install the .NET SDK or .NET Runtime.</span></span> <span data-ttu-id="e7351-105">Snaps stellen eine gute Alternative zum in Ihre Linux-Distribution integrierten Paket-Manager dar.</span><span class="sxs-lookup"><span data-stu-id="e7351-105">Snaps are a great alternative to the package manager built into your Linux distribution.</span></span> <span data-ttu-id="e7351-106">In diesem Artikel wird beschrieben, wie Sie .NET mithilfe von [Snap](https://snapcraft.io/dotnet-sdk) installieren.</span><span class="sxs-lookup"><span data-stu-id="e7351-106">This article describes how to install .NET through [Snap](https://snapcraft.io/dotnet-sdk).</span></span>

<span data-ttu-id="e7351-107">Ein Snap ist ein Bündel aus einer Anwendung und ihren Abhängigkeiten, das ohne Änderungen in vielen verschiedenen Linux-Distributionen funktioniert.</span><span class="sxs-lookup"><span data-stu-id="e7351-107">A snap is a bundle of an app and its dependencies that works without modification across many different Linux distributions.</span></span> <span data-ttu-id="e7351-108">Snaps sind über den Snap Store abrufbar und installierbar.</span><span class="sxs-lookup"><span data-stu-id="e7351-108">Snaps are discoverable and installable from the Snap Store.</span></span> <span data-ttu-id="e7351-109">Weitere Informationen zu Snap finden Sie unter [Erste Schritte mit Snap](https://snapcraft.io/docs/getting-started).</span><span class="sxs-lookup"><span data-stu-id="e7351-109">For more information about Snap, see [Getting started with Snap](https://snapcraft.io/docs/getting-started).</span></span>

> [!CAUTION]
> <span data-ttu-id="e7351-110">Snap-Pakete werden in WSL2 unter Windows 10 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e7351-110">Snap packages aren't supported in WSL2 on Windows 10.</span></span> <span data-ttu-id="e7351-111">Verwenden Sie alternativ das [`dotnet-install`-Skript](linux-scripted-manual.md#scripted-install) oder den Paket-Manager für die jeweilige WSL2-Distribution.</span><span class="sxs-lookup"><span data-stu-id="e7351-111">As an alternative, use the [`dotnet-install` script](linux-scripted-manual.md#scripted-install) or the package manager for the particular WSL2 distribution.</span></span> <span data-ttu-id="e7351-112">Es ist nicht empfehlenswert, jedoch können Sie versuchen, Snap mit einer [nicht unterstützten Problemumgehung aus den Snapcraft-Foren](https://forum.snapcraft.io/t/running-snaps-on-wsl2-insiders-only-for-now/13033) zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e7351-112">It's not recommended but you can try to enable snap with an [unsupported workaround from the snapcraft forums](https://forum.snapcraft.io/t/running-snaps-on-wsl2-insiders-only-for-now/13033).</span></span>

## <a name="net-releases"></a><span data-ttu-id="e7351-113">.NET-Releases</span><span class="sxs-lookup"><span data-stu-id="e7351-113">.NET releases</span></span>

<span data-ttu-id="e7351-114">Nur ✔️ unterstützte Versionen des .NET SDK sind über Snap verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e7351-114">Only ✔️ supported versions of .NET SDK are available through Snap.</span></span> <span data-ttu-id="e7351-115">Alle Versionen der .NET-Runtime sind ab Version 2.1 über Snap verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e7351-115">All versions of the .NET Runtime are available through snap starting with version 2.1.</span></span> <span data-ttu-id="e7351-116">In der folgenden Tabelle sind die Versionen von .NET (und .NET Core) aufgelistet:</span><span class="sxs-lookup"><span data-stu-id="e7351-116">The following table lists the .NET (and .NET Core) releases:</span></span>

| <span data-ttu-id="e7351-117">✔️ Unterstützt</span><span class="sxs-lookup"><span data-stu-id="e7351-117">✔️ Supported</span></span> | <span data-ttu-id="e7351-118">❌ Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="e7351-118">❌ Unsupported</span></span> |
|-------------|---------------|
| <span data-ttu-id="e7351-119">5.0</span><span class="sxs-lookup"><span data-stu-id="e7351-119">5.0</span></span>         | <span data-ttu-id="e7351-120">3.0</span><span class="sxs-lookup"><span data-stu-id="e7351-120">3.0</span></span>           |
| <span data-ttu-id="e7351-121">3.1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="e7351-121">3.1 (LTS)</span></span>   | <span data-ttu-id="e7351-122">2.2</span><span class="sxs-lookup"><span data-stu-id="e7351-122">2.2</span></span>           |
| <span data-ttu-id="e7351-123">2.1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="e7351-123">2.1 (LTS)</span></span>   | <span data-ttu-id="e7351-124">2.0</span><span class="sxs-lookup"><span data-stu-id="e7351-124">2.0</span></span>           |
|             | <span data-ttu-id="e7351-125">1.1</span><span class="sxs-lookup"><span data-stu-id="e7351-125">1.1</span></span>           |
|             | <span data-ttu-id="e7351-126">1.0</span><span class="sxs-lookup"><span data-stu-id="e7351-126">1.0</span></span>           |

<span data-ttu-id="e7351-127">Weitere Informationen zum Lebenszyklus von .NET-Versionen finden Sie in der [Richtlinie zur Unterstützung von .NET Core und .NET 5](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="e7351-127">For more information about the life cycle of .NET releases, see [.NET Core and .NET 5 Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span></span>

## <a name="sdk-or-runtime"></a><span data-ttu-id="e7351-128">SDK oder Runtime</span><span class="sxs-lookup"><span data-stu-id="e7351-128">SDK or Runtime</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="install-the-sdk"></a><span data-ttu-id="e7351-129">Installieren des SDK</span><span class="sxs-lookup"><span data-stu-id="e7351-129">Install the SDK</span></span>

<span data-ttu-id="e7351-130">Snap-Pakete für das .NET SDK werden alle unter demselben Bezeichner veröffentlicht: `dotnet-sdk`.</span><span class="sxs-lookup"><span data-stu-id="e7351-130">Snap packages for the .NET SDK are all published under the same identifier: `dotnet-sdk`.</span></span> <span data-ttu-id="e7351-131">Eine bestimmte Version des SDK kann durch Angabe des Kanals installiert werden.</span><span class="sxs-lookup"><span data-stu-id="e7351-131">A specific version of the SDK can be installed by specifying the channel.</span></span> <span data-ttu-id="e7351-132">Das SDK enthält die entsprechende Runtime.</span><span class="sxs-lookup"><span data-stu-id="e7351-132">The SDK includes the corresponding runtime.</span></span> <span data-ttu-id="e7351-133">In der folgenden Tabelle sind die Kanäle aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="e7351-133">The following table lists the channels:</span></span>

| <span data-ttu-id="e7351-134">.NET-Version</span><span class="sxs-lookup"><span data-stu-id="e7351-134">.NET version</span></span> | <span data-ttu-id="e7351-135">Snap-Paket oder -Kanal</span><span class="sxs-lookup"><span data-stu-id="e7351-135">Snap package or channel</span></span>  |
|--------------|--------------------------|
| <span data-ttu-id="e7351-136">5.0</span><span class="sxs-lookup"><span data-stu-id="e7351-136">5.0</span></span>          | <span data-ttu-id="e7351-137">`5.0` oder `latest/stable`</span><span class="sxs-lookup"><span data-stu-id="e7351-137">`5.0` or `latest/stable`</span></span> |
| <span data-ttu-id="e7351-138">3.1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="e7351-138">3.1 (LTS)</span></span>    | <span data-ttu-id="e7351-139">`3.1` oder `lts/stable`</span><span class="sxs-lookup"><span data-stu-id="e7351-139">`3.1` or `lts/stable`</span></span>    |
| <span data-ttu-id="e7351-140">2.1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="e7351-140">2.1 (LTS)</span></span>    | `2.1`                    |

<span data-ttu-id="e7351-141">Verwenden Sie den Befehl `snap install`, um ein Snap-Paket für das .NET SDK zu installieren.</span><span class="sxs-lookup"><span data-stu-id="e7351-141">Use the `snap install` command to install a .NET SDK snap package.</span></span> <span data-ttu-id="e7351-142">Geben Sie mit dem Parameter `--channel` an, welche Version installiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="e7351-142">Use the `--channel` parameter to indicate which version to install.</span></span> <span data-ttu-id="e7351-143">Bei Weglassen dieses Parameters wird `latest/stable` verwendet.</span><span class="sxs-lookup"><span data-stu-id="e7351-143">If this parameter is omitted, `latest/stable` is used.</span></span> <span data-ttu-id="e7351-144">In diesem Beispiel ist `5.0` angegeben:</span><span class="sxs-lookup"><span data-stu-id="e7351-144">In this example, `5.0` is specified:</span></span>

```bash
sudo snap install dotnet-sdk --classic --channel=5.0
```

<span data-ttu-id="e7351-145">Registrieren Sie als Nächstes den Befehl `dotnet` für das System mit dem Befehl `snap alias`:</span><span class="sxs-lookup"><span data-stu-id="e7351-145">Next, register the `dotnet` command for the system with the `snap alias` command:</span></span>

```bash
sudo snap alias dotnet-sdk.dotnet dotnet
```

<span data-ttu-id="e7351-146">Dieser Befehl ist wie folgt formatiert: `sudo snap alias {package}.{command} {alias}`.</span><span class="sxs-lookup"><span data-stu-id="e7351-146">This command is formatted as: `sudo snap alias {package}.{command} {alias}`.</span></span> <span data-ttu-id="e7351-147">Sie können für `{alias}` einen beliebigen Namen auswählen.</span><span class="sxs-lookup"><span data-stu-id="e7351-147">You can choose any `{alias}` name you would like.</span></span> <span data-ttu-id="e7351-148">Beispielsweise können Sie den Befehl nach der spezifischen Version benennen, die mittels Snap installiert wurde: `sudo snap alias dotnet-sdk.dotnet dotnet50`.</span><span class="sxs-lookup"><span data-stu-id="e7351-148">For example, you could name the command after the specific version installed by snap: `sudo snap alias dotnet-sdk.dotnet dotnet50`.</span></span> <span data-ttu-id="e7351-149">Beim Verwenden des Befehls `dotnet50` rufen Sie diese spezifische Version von .NET auf.</span><span class="sxs-lookup"><span data-stu-id="e7351-149">When you use the command `dotnet50`, you'll invoke this specific version of .NET.</span></span> <span data-ttu-id="e7351-150">Die Auswahl eines anderen Alias ist jedoch mit den meisten Tutorials und Beispielen unvereinbar, da erwartet wird, dass ein `dotnet`-Befehl verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e7351-150">But choosing a different alias is incompatible with most tutorials and examples as they expect a `dotnet` command to be used.</span></span>

## <a name="install-the-runtime"></a><span data-ttu-id="e7351-151">Installieren der Runtime</span><span class="sxs-lookup"><span data-stu-id="e7351-151">Install the runtime</span></span>

<span data-ttu-id="e7351-152">Snap-Pakete für die .NET-Runtime werden mit jeweils eigenem Paketbezeichner veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="e7351-152">Snap packages for the .NET Runtime are each published under their own package identifier.</span></span> <span data-ttu-id="e7351-153">In der folgenden Tabelle sind die Paketbezeichner aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="e7351-153">The following table lists the package identifiers:</span></span>

| <span data-ttu-id="e7351-154">.NET-Version</span><span class="sxs-lookup"><span data-stu-id="e7351-154">.NET version</span></span>      | <span data-ttu-id="e7351-155">Snap-Paket</span><span class="sxs-lookup"><span data-stu-id="e7351-155">Snap package</span></span>        |
|-------------------|---------------------|
| <span data-ttu-id="e7351-156">5.0</span><span class="sxs-lookup"><span data-stu-id="e7351-156">5.0</span></span>               | `dotnet-runtime-50` |
| <span data-ttu-id="e7351-157">3.1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="e7351-157">3.1 (LTS)</span></span>         | `dotnet-runtime-31` |
| <span data-ttu-id="e7351-158">3.0</span><span class="sxs-lookup"><span data-stu-id="e7351-158">3.0</span></span>               | `dotnet-runtime-30` |
| <span data-ttu-id="e7351-159">2.2</span><span class="sxs-lookup"><span data-stu-id="e7351-159">2.2</span></span>               | `dotnet-runtime-22` |
| <span data-ttu-id="e7351-160">2.1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="e7351-160">2.1 (LTS)</span></span>         | `dotnet-runtime-21` |

<span data-ttu-id="e7351-161">Verwenden Sie den Befehl `snap install`, um ein Snap-Paket für die .NET-Runtime zu installieren.</span><span class="sxs-lookup"><span data-stu-id="e7351-161">Use the `snap install` command to install a .NET Runtime snap package.</span></span> <span data-ttu-id="e7351-162">In diesem Beispiel wird .NET 5.0 installiert:</span><span class="sxs-lookup"><span data-stu-id="e7351-162">In this example, .NET 5.0 is installed:</span></span>

```bash
sudo snap install dotnet-runtime-50 --classic
```

<span data-ttu-id="e7351-163">Registrieren Sie als Nächstes den Befehl `dotnet` für das System mit dem Befehl `snap alias`:</span><span class="sxs-lookup"><span data-stu-id="e7351-163">Next, register the `dotnet` command for the system with the `snap alias` command:</span></span>

```bash
sudo snap alias dotnet-runtime-50.dotnet dotnet
```

<span data-ttu-id="e7351-164">Der Befehl ist wie folgt formatiert: `sudo snap alias {package}.{command} {alias}`.</span><span class="sxs-lookup"><span data-stu-id="e7351-164">The command is formatted as: `sudo snap alias {package}.{command} {alias}`.</span></span> <span data-ttu-id="e7351-165">Sie können für `{alias}` einen beliebigen Namen auswählen.</span><span class="sxs-lookup"><span data-stu-id="e7351-165">You can choose any `{alias}` name you would like.</span></span> <span data-ttu-id="e7351-166">Beispielsweise können Sie den Befehl nach der spezifischen Version benennen, die mittels Snap installiert wurde: `sudo snap alias dotnet-runtime-50.dotnet dotnet50`.</span><span class="sxs-lookup"><span data-stu-id="e7351-166">For example, you could name the command after the specific version installed by snap: `sudo snap alias dotnet-runtime-50.dotnet dotnet50`.</span></span> <span data-ttu-id="e7351-167">Beim Verwenden des Befehls `dotnet50` rufen Sie eine spezifische Version von .NET auf.</span><span class="sxs-lookup"><span data-stu-id="e7351-167">When you use the command `dotnet50`, you'll invoke a specific version of .NET.</span></span> <span data-ttu-id="e7351-168">Die Auswahl eines anderen Alias ist jedoch mit den meisten Tutorials und Beispielen unvereinbar, da erwartet wird, dass ein `dotnet`-Befehl verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="e7351-168">But choosing a different alias is incompatible with most tutorials and examples as they expect a `dotnet` command to be available.</span></span>

## <a name="tlsssl-certificate-errors"></a><span data-ttu-id="e7351-169">TLS/SSL-Zertifikatfehler</span><span class="sxs-lookup"><span data-stu-id="e7351-169">TLS/SSL Certificate errors</span></span>

<span data-ttu-id="e7351-170">Wenn .NET über Snap installiert wird, ist es möglich, dass bei einigen Distributionen die TLS/SSL-Zertifikate für .NET nicht gefunden werden und während `restore` eine Fehlermeldung angezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="e7351-170">When .NET is installed through Snap, it's possible that on some distros the .NET TLS/SSL certificates may not be found and you may receive an error during `restore`:</span></span>

```bash
Processing post-creation actions...
Running 'dotnet restore' on /home/myhome/test/test.csproj...
  Restoring packages for /home/myhome/test/test.csproj...
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error : Unable to load the service index for source https://api.nuget.org/v3/index.json. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The SSL connection could not be established, see inner exception. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The remote certificate is invalid according to the validation procedure. [/home/myhome/test/test.csproj]
```

<span data-ttu-id="e7351-171">Zum Lösen dieses Problems müssen Sie einige Umgebungsvariablen festlegen:</span><span class="sxs-lookup"><span data-stu-id="e7351-171">To resolve this problem, set a few environment variables:</span></span>

```bash
export SSL_CERT_FILE=[path-to-certificate-file]
export SSL_CERT_DIR=/dev/null
```

<span data-ttu-id="e7351-172">Der Speicherort des Zertifikats variiert je nach Distribution.</span><span class="sxs-lookup"><span data-stu-id="e7351-172">The certificate location will vary by distro.</span></span> <span data-ttu-id="e7351-173">Hier finden Sie die Speicherorte für die Distributionen, in denen das Problem aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="e7351-173">Here are the locations for the distros where the issue has been experienced.</span></span>

| <span data-ttu-id="e7351-174">Distribution</span><span class="sxs-lookup"><span data-stu-id="e7351-174">Distribution</span></span> | <span data-ttu-id="e7351-175">Standort</span><span class="sxs-lookup"><span data-stu-id="e7351-175">Location</span></span>                                            |
|--------------|-----------------------------------------------------|
| <span data-ttu-id="e7351-176">**Fedora**</span><span class="sxs-lookup"><span data-stu-id="e7351-176">**Fedora**</span></span>   | `/etc/pki/ca-trust/extracted/pem/tls-ca-bundle.pem` |
| <span data-ttu-id="e7351-177">**OpenSUSE**</span><span class="sxs-lookup"><span data-stu-id="e7351-177">**OpenSUSE**</span></span> | `/etc/ssl/ca-bundle.pem`                            |
| <span data-ttu-id="e7351-178">**Solus**</span><span class="sxs-lookup"><span data-stu-id="e7351-178">**Solus**</span></span>    | `/etc/ssl/certs/ca-certificates.crt`                |

## <a name="next-steps"></a><span data-ttu-id="e7351-179">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="e7351-179">Next steps</span></span>

- [<span data-ttu-id="e7351-180">Aktivieren der Vervollständigung mit der TAB-TASTE für die .NET-CLI</span><span class="sxs-lookup"><span data-stu-id="e7351-180">How to enable TAB completion for the .NET CLI</span></span>](../tools/enable-tab-autocomplete.md)
- [<span data-ttu-id="e7351-181">Tutorial: Erstellen einer Konsolenanwendung mit dem .NET SDK in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="e7351-181">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
