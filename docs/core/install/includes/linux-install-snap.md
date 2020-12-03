---
ms.openlocfilehash: 83808f2f3a05333ed5d9e3809cbc2fd6e230d02c
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96031764"
---

[<span data-ttu-id="ffe4a-101">.Net Core ist im Snap Store verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ffe4a-101">.NET Core is available from the Snap Store.</span></span>](https://snapcraft.io/dotnet-sdk)

<span data-ttu-id="ffe4a-102">Ein Snap ist ein Bündel aus einer Anwendung und ihren Abhängigkeiten, das ohne Änderungen in vielen verschiedenen Linux-Distributionen funktioniert.</span><span class="sxs-lookup"><span data-stu-id="ffe4a-102">A snap is a bundle of an app and its dependencies that works without modification across many different Linux distributions.</span></span> <span data-ttu-id="ffe4a-103">Snaps sind über den Snap Store abrufbar und installierbar.</span><span class="sxs-lookup"><span data-stu-id="ffe4a-103">Snaps are discoverable and installable from the Snap Store.</span></span> <span data-ttu-id="ffe4a-104">Weitere Informationen zu Snap finden Sie unter [Erste Schritte mit Snap](https://snapcraft.io/docs/getting-started).</span><span class="sxs-lookup"><span data-stu-id="ffe4a-104">For more information about Snap, see [Getting started with Snap](https://snapcraft.io/docs/getting-started).</span></span>

<span data-ttu-id="ffe4a-105">Nur unterstützte Versionen von .NET Core sind über Snap verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ffe4a-105">Only supported versions of .NET Core are available through Snap.</span></span>

### <a name="install-the-sdk"></a><span data-ttu-id="ffe4a-106">Installieren des SDKs</span><span class="sxs-lookup"><span data-stu-id="ffe4a-106">Install the SDK</span></span>

<span data-ttu-id="ffe4a-107">Snap-Pakete für das .NET SDK werden alle unter demselben Bezeichner veröffentlicht: `dotnet-sdk`.</span><span class="sxs-lookup"><span data-stu-id="ffe4a-107">Snap packages for .NET SDK are all published under the same identifier: `dotnet-sdk`.</span></span> <span data-ttu-id="ffe4a-108">Eine bestimmte Version des SDK kann durch Angabe des Kanals installiert werden.</span><span class="sxs-lookup"><span data-stu-id="ffe4a-108">A specific version of the SDK can be installed by specifying the channel.</span></span> <span data-ttu-id="ffe4a-109">Das SDK enthält die entsprechende Runtime.</span><span class="sxs-lookup"><span data-stu-id="ffe4a-109">The SDK includes the corresponding runtime.</span></span> <span data-ttu-id="ffe4a-110">In der folgenden Tabelle sind die Kanäle aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="ffe4a-110">The following table lists the channels:</span></span>

| <span data-ttu-id="ffe4a-111">.NET-Version</span><span class="sxs-lookup"><span data-stu-id="ffe4a-111">.NET version</span></span> | <span data-ttu-id="ffe4a-112">Snap-Paket</span><span class="sxs-lookup"><span data-stu-id="ffe4a-112">Snap package</span></span>             |
|--------------|--------------------------|
| <span data-ttu-id="ffe4a-113">5.0</span><span class="sxs-lookup"><span data-stu-id="ffe4a-113">5.0</span></span>          | <span data-ttu-id="ffe4a-114">`5.0` oder `latest/stable`</span><span class="sxs-lookup"><span data-stu-id="ffe4a-114">`5.0` or `latest/stable`</span></span> |
| <span data-ttu-id="ffe4a-115">3.1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="ffe4a-115">3.1 (LTS)</span></span>    | <span data-ttu-id="ffe4a-116">`3.1` oder `lts/stable`</span><span class="sxs-lookup"><span data-stu-id="ffe4a-116">`3.1` or `lts/stable`</span></span>    |
| <span data-ttu-id="ffe4a-117">2.1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="ffe4a-117">2.1 (LTS)</span></span>    | `2.1`                    |

<span data-ttu-id="ffe4a-118">Verwenden Sie den Befehl `snap install`, um ein Snap-Paket für das .NET SDK zu installieren.</span><span class="sxs-lookup"><span data-stu-id="ffe4a-118">Use the `snap install` command to install a .NET SDK snap package.</span></span> <span data-ttu-id="ffe4a-119">Geben Sie mit dem Parameter `--channel` an, welche Version installiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ffe4a-119">Use the `--channel` parameter to indicate which version to install.</span></span> <span data-ttu-id="ffe4a-120">Bei Weglassen dieses Parameters wird `latest/stable` verwendet.</span><span class="sxs-lookup"><span data-stu-id="ffe4a-120">If this parameter is omitted, `latest/stable` is used.</span></span> <span data-ttu-id="ffe4a-121">In diesem Beispiel ist `5.0` angegeben:</span><span class="sxs-lookup"><span data-stu-id="ffe4a-121">In this example, `5.0` is specified:</span></span>

```bash
sudo snap install dotnet-sdk --classic --channel=5.0
```

<span data-ttu-id="ffe4a-122">Registrieren Sie als Nächstes den Befehl `dotnet` für das System mit dem Befehl `snap alias`:</span><span class="sxs-lookup"><span data-stu-id="ffe4a-122">Next, register the `dotnet` command for the system with the `snap alias` command:</span></span>

```bash
sudo snap alias dotnet-sdk.dotnet dotnet
```

<span data-ttu-id="ffe4a-123">Dieser Befehl ist wie folgt formatiert: `sudo snap alias {package}.{command} {alias}`.</span><span class="sxs-lookup"><span data-stu-id="ffe4a-123">This command is formatted as: `sudo snap alias {package}.{command} {alias}`.</span></span> <span data-ttu-id="ffe4a-124">Sie können für `{alias}` einen beliebigen Namen auswählen.</span><span class="sxs-lookup"><span data-stu-id="ffe4a-124">You can choose any `{alias}` name you would like.</span></span> <span data-ttu-id="ffe4a-125">Beispielsweise können Sie den Befehl nach der spezifischen Version benennen, die mittels Snap installiert wurde: `sudo snap alias dotnet-sdk.dotnet dotnet50`.</span><span class="sxs-lookup"><span data-stu-id="ffe4a-125">For example, you could name the command after the specific version installed by snap: `sudo snap alias dotnet-sdk.dotnet dotnet50`.</span></span> <span data-ttu-id="ffe4a-126">Beim Verwenden des Befehls `dotnet50` rufen Sie diese spezifische Version von .NET auf.</span><span class="sxs-lookup"><span data-stu-id="ffe4a-126">When you use the command `dotnet50`, you'll invoke this specific version of .NET.</span></span> <span data-ttu-id="ffe4a-127">Diese ist jedoch mit den meisten Tutorials und Beispielen unvereinbar, da erwartet wird, dass ein `dotnet`-Befehl verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ffe4a-127">But this is incompatible with most tutorials and examples as they expect a `dotnet` command to be available.</span></span>

### <a name="install-the-runtime"></a><span data-ttu-id="ffe4a-128">Installieren der Runtime</span><span class="sxs-lookup"><span data-stu-id="ffe4a-128">Install the runtime</span></span>

<span data-ttu-id="ffe4a-129">Snap-Pakete für die .NET Core-Runtime werden mit jeweils eigenem Paketbezeichner veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="ffe4a-129">Snap packages for .NET Core Runtime are each published under their own package identifier.</span></span> <span data-ttu-id="ffe4a-130">In der folgenden Tabelle sind die Paketbezeichner aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="ffe4a-130">The following table lists the package identifiers:</span></span>

| <span data-ttu-id="ffe4a-131">.NET-Version</span><span class="sxs-lookup"><span data-stu-id="ffe4a-131">.NET version</span></span>      | <span data-ttu-id="ffe4a-132">Snap-Paket</span><span class="sxs-lookup"><span data-stu-id="ffe4a-132">Snap package</span></span>        |
|-------------------|---------------------|
| <span data-ttu-id="ffe4a-133">5.0</span><span class="sxs-lookup"><span data-stu-id="ffe4a-133">5.0</span></span>               | `dotnet-runtime-50` |
| <span data-ttu-id="ffe4a-134">3.1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="ffe4a-134">3.1 (LTS)</span></span>         | `dotnet-runtime-31` |
| <span data-ttu-id="ffe4a-135">3.0</span><span class="sxs-lookup"><span data-stu-id="ffe4a-135">3.0</span></span>               | `dotnet-runtime-30` |
| <span data-ttu-id="ffe4a-136">2.2</span><span class="sxs-lookup"><span data-stu-id="ffe4a-136">2.2</span></span>               | `dotnet-runtime-22` |
| <span data-ttu-id="ffe4a-137">2.1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="ffe4a-137">2.1 (LTS)</span></span>         | `dotnet-runtime-21` |

<span data-ttu-id="ffe4a-138">Verwenden Sie den Befehl `snap install`, um ein Snap-Paket für die .NET-Runtime zu installieren.</span><span class="sxs-lookup"><span data-stu-id="ffe4a-138">Use the `snap install` command to install a .NET Runtime snap package.</span></span> <span data-ttu-id="ffe4a-139">In diesem Beispiel wird .NET 5.0 installiert:</span><span class="sxs-lookup"><span data-stu-id="ffe4a-139">In this example, .NET 5.0 is installed:</span></span>

```bash
sudo snap install dotnet-runtime-50 --classic
```

<span data-ttu-id="ffe4a-140">Registrieren Sie als Nächstes den Befehl `dotnet` für das System mit dem Befehl `snap alias`:</span><span class="sxs-lookup"><span data-stu-id="ffe4a-140">Next, register the `dotnet` command for the system with the `snap alias` command:</span></span>

```bash
sudo snap alias dotnet-runtime-50.dotnet dotnet
```

<span data-ttu-id="ffe4a-141">Dieser Befehl ist wie folgt formatiert: `sudo snap alias {package}.{command} {alias}`.</span><span class="sxs-lookup"><span data-stu-id="ffe4a-141">This command is formatted as: `sudo snap alias {package}.{command} {alias}`.</span></span> <span data-ttu-id="ffe4a-142">Sie können für `{alias}` einen beliebigen Namen auswählen.</span><span class="sxs-lookup"><span data-stu-id="ffe4a-142">You can choose any `{alias}` name you would like.</span></span> <span data-ttu-id="ffe4a-143">Beispielsweise können Sie den Befehl nach der spezifischen Version benennen, die mittels Snap installiert wurde: `sudo snap alias dotnet-runtime-50.dotnet dotnet50`.</span><span class="sxs-lookup"><span data-stu-id="ffe4a-143">For example, you could name the command after the specific version installed by snap: `sudo snap alias dotnet-runtime-50.dotnet dotnet50`.</span></span> <span data-ttu-id="ffe4a-144">Beim Verwenden des Befehls `dotnet50` rufen Sie diese spezifische Version von .NET auf.</span><span class="sxs-lookup"><span data-stu-id="ffe4a-144">When you use the command `dotnet50`, you'll invoke this specific version of .NET.</span></span> <span data-ttu-id="ffe4a-145">Diese ist jedoch mit den meisten Tutorials und Beispielen unvereinbar, da erwartet wird, dass ein `dotnet`-Befehl verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ffe4a-145">But this is incompatible with most tutorials and examples as they expect a `dotnet` command to be available.</span></span>

### <a name="ssl-certificate-errors"></a><span data-ttu-id="ffe4a-146">SSL-Zertifikatfehler</span><span class="sxs-lookup"><span data-stu-id="ffe4a-146">SSL Certificate errors</span></span>

<span data-ttu-id="ffe4a-147">Wenn .NET über Snap installiert wird, ist es möglich, dass bei einigen Distributionen die SSL-Zertifikate für .NET nicht gefunden werden und Sie während `restore` einen Fehler ähnlich dem folgenden erhalten:</span><span class="sxs-lookup"><span data-stu-id="ffe4a-147">When .NET is installed through Snap, it's possible that on some distros the .NET SSL certificates may not be found and you may receive an error similar to the following during `restore`:</span></span>

```bash
Processing post-creation actions...
Running 'dotnet restore' on /home/myhome/test/test.csproj...
  Restoring packages for /home/myhome/test/test.csproj...
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error : Unable to load the service index for source https://api.nuget.org/v3/index.json. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The SSL connection could not be established, see inner exception. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The remote certificate is invalid according to the validation procedure. [/home/myhome/test/test.csproj]
```

<span data-ttu-id="ffe4a-148">Zur Behebung dieses Problems müssen Sie einige Umgebungsvariablen festlegen:</span><span class="sxs-lookup"><span data-stu-id="ffe4a-148">To resolve this issue, set a few environment variables:</span></span>

```bash
export SSL_CERT_FILE=[path-to-certificate-file]
export SSL_CERT_DIR=/dev/null
```

<span data-ttu-id="ffe4a-149">Der Speicherort des Zertifikats variiert je nach Distribution.</span><span class="sxs-lookup"><span data-stu-id="ffe4a-149">The certificate location will vary by distro.</span></span> <span data-ttu-id="ffe4a-150">Hier finden Sie die Speicherorte für die Distributionen, in denen das Problem aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="ffe4a-150">Here are the locations for the distros where we have experienced the issue.</span></span>

* <span data-ttu-id="ffe4a-151">Fedora: `/etc/pki/ca-trust/extracted/pem/tls-ca-bundle.pem`</span><span class="sxs-lookup"><span data-stu-id="ffe4a-151">Fedora - `/etc/pki/ca-trust/extracted/pem/tls-ca-bundle.pem`</span></span>
* <span data-ttu-id="ffe4a-152">OpenSUSE: `/etc/ssl/ca-bundle.pem`</span><span class="sxs-lookup"><span data-stu-id="ffe4a-152">OpenSUSE - `/etc/ssl/ca-bundle.pem`</span></span>
* <span data-ttu-id="ffe4a-153">Solus: `/etc/ssl/certs/ca-certificates.crt`</span><span class="sxs-lookup"><span data-stu-id="ffe4a-153">Solus - `/etc/ssl/certs/ca-certificates.crt`</span></span>
