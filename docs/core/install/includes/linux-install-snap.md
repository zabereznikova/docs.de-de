---
ms.openlocfilehash: 5e77b7bd73c09e061a94a29703cf5286814d1ebb
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602687"
---

[<span data-ttu-id="ceaf1-101">.Net Core ist im Snap Store verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ceaf1-101">.NET Core is available from the Snap Store.</span></span>](https://snapcraft.io/dotnet-sdk)

<span data-ttu-id="ceaf1-102">Ein Snap ist ein Bündel aus einer Anwendung und ihren Abhängigkeiten, das ohne Änderungen in vielen verschiedenen Linux-Distributionen funktioniert.</span><span class="sxs-lookup"><span data-stu-id="ceaf1-102">A snap is a bundle of an app and its dependencies that works without modification across many different Linux distributions.</span></span> <span data-ttu-id="ceaf1-103">Snaps sind über den Snap Store abrufbar und installierbar.</span><span class="sxs-lookup"><span data-stu-id="ceaf1-103">Snaps are discoverable and installable from the Snap Store.</span></span> <span data-ttu-id="ceaf1-104">Weitere Informationen zu Snap finden Sie unter [Erste Schritte mit Snap](https://snapcraft.io/docs/getting-started).</span><span class="sxs-lookup"><span data-stu-id="ceaf1-104">For more information about Snap, see [Getting started with Snap](https://snapcraft.io/docs/getting-started).</span></span>

<span data-ttu-id="ceaf1-105">Nur unterstützte Versionen von .NET Core sind über Snap verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ceaf1-105">Only supported versions of .NET Core are available through Snap.</span></span>

### <a name="install-the-sdk"></a><span data-ttu-id="ceaf1-106">Installieren des SDKs</span><span class="sxs-lookup"><span data-stu-id="ceaf1-106">Install the SDK</span></span>

<span data-ttu-id="ceaf1-107">Snap-Pakete für das .NET Core SDK werden alle unter demselben Bezeichner veröffentlicht: `dotnet-sdk`.</span><span class="sxs-lookup"><span data-stu-id="ceaf1-107">Snap packages for .NET Core SDK are all published under the same identifier: `dotnet-sdk`.</span></span> <span data-ttu-id="ceaf1-108">Eine bestimmte Version des SDK kann durch Angabe des Kanals installiert werden.</span><span class="sxs-lookup"><span data-stu-id="ceaf1-108">A specific version of the SDK can be installed by specifying the channel.</span></span> <span data-ttu-id="ceaf1-109">Das SDK enthält die entsprechende Runtime.</span><span class="sxs-lookup"><span data-stu-id="ceaf1-109">The SDK includes the coresponding runtime.</span></span> <span data-ttu-id="ceaf1-110">In der folgenden Tabelle sind die Kanäle aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="ceaf1-110">The following table list the channels:</span></span>

| <span data-ttu-id="ceaf1-111">.NET Core-Version</span><span class="sxs-lookup"><span data-stu-id="ceaf1-111">.NET Core version</span></span> | <span data-ttu-id="ceaf1-112">Snap-Paket</span><span class="sxs-lookup"><span data-stu-id="ceaf1-112">Snap package</span></span>             |
|-------------------|--------------------------|
| <span data-ttu-id="ceaf1-113">3.1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="ceaf1-113">3.1 (LTS)</span></span>         | <span data-ttu-id="ceaf1-114">`3.1` oder `latest/stable`</span><span class="sxs-lookup"><span data-stu-id="ceaf1-114">`3.1` or `latest/stable`</span></span> |
| <span data-ttu-id="ceaf1-115">2.1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="ceaf1-115">2.1 (LTS)</span></span>         | `2.1`                    |
| <span data-ttu-id="ceaf1-116">.NET 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="ceaf1-116">.NET 5.0 preview</span></span>  | `5.0/beta`               |

<span data-ttu-id="ceaf1-117">Verwenden Sie den Befehl `snap install`, um ein Snap-Paket für das .NET Core SDK zu installieren.</span><span class="sxs-lookup"><span data-stu-id="ceaf1-117">Use the `snap install` command to install a .NET Core SDK snap package.</span></span> <span data-ttu-id="ceaf1-118">Geben Sie mit dem Parameter `--channel` an, welche Version installiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ceaf1-118">Use the `--channel` parameter to indicate which version to install.</span></span> <span data-ttu-id="ceaf1-119">Bei Weglassen dieses Parameters wird `latest/stable` verwendet.</span><span class="sxs-lookup"><span data-stu-id="ceaf1-119">If this parameter is omitted, `latest/stable` is used.</span></span> <span data-ttu-id="ceaf1-120">In diesem Beispiel ist `3.1` angegeben:</span><span class="sxs-lookup"><span data-stu-id="ceaf1-120">In this example, `3.1` is specified:</span></span>

```bash
sudo snap install dotnet-sdk --classic --channel=3.1
```

<span data-ttu-id="ceaf1-121">Registrieren Sie als Nächstes den Befehl `dotnet` für das System mit dem Befehl `snap alias`:</span><span class="sxs-lookup"><span data-stu-id="ceaf1-121">Next, register the `dotnet` command for the system with the `snap alias` command:</span></span>

```bash
sudo snap alias dotnet-sdk.dotnet dotnet
```

<span data-ttu-id="ceaf1-122">Dieser Befehl ist wie folgt formatiert: `sudo snap alias {package}.{command} {alias}`.</span><span class="sxs-lookup"><span data-stu-id="ceaf1-122">This command is formatted as: `sudo snap alias {package}.{command} {alias}`.</span></span> <span data-ttu-id="ceaf1-123">Sie können für `{alias}` einen beliebigen Namen auswählen.</span><span class="sxs-lookup"><span data-stu-id="ceaf1-123">You can choose any `{alias}` name you would like.</span></span> <span data-ttu-id="ceaf1-124">Beispielsweise können Sie den Befehl nach der spezifischen Version benennen, die mittels Snap installiert wurde: `sudo snap alias dotnet-sdk.dotnet dotnet31`.</span><span class="sxs-lookup"><span data-stu-id="ceaf1-124">For example, you could name the command after the specific version installed by snap: `sudo snap alias dotnet-sdk.dotnet dotnet31`.</span></span> <span data-ttu-id="ceaf1-125">Beim Verwenden des Befehls `dotnet31` rufen Sie diese spezifische Version von .NET auf.</span><span class="sxs-lookup"><span data-stu-id="ceaf1-125">When you use the command `dotnet31`, you'll invoke this specific version of .NET.</span></span> <span data-ttu-id="ceaf1-126">Diese ist jedoch mit den meisten Tutorials und Beispielen unvereinbar, da erwartet wird, dass ein `dotnet`-Befehl verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ceaf1-126">But this is incompatible with most tutorials and examples as they expect a `dotnet` command to be available.</span></span>

### <a name="install-the-runtime"></a><span data-ttu-id="ceaf1-127">Installieren der Runtime</span><span class="sxs-lookup"><span data-stu-id="ceaf1-127">Install the runtime</span></span>

<span data-ttu-id="ceaf1-128">Snap-Pakete für die .NET Core-Runtime werden mit jeweils eigenem Paketbezeichner veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="ceaf1-128">Snap packages for .NET Core Runtime are each published under their own package identifier.</span></span> <span data-ttu-id="ceaf1-129">In der folgenden Tabelle sind die Paketbezeichner aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="ceaf1-129">The following table lists the package identifiers:</span></span>

| <span data-ttu-id="ceaf1-130">.NET Core-Version</span><span class="sxs-lookup"><span data-stu-id="ceaf1-130">.NET Core version</span></span> | <span data-ttu-id="ceaf1-131">Snap-Paket</span><span class="sxs-lookup"><span data-stu-id="ceaf1-131">Snap package</span></span>        |
|-------------------|---------------------|
| <span data-ttu-id="ceaf1-132">3.1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="ceaf1-132">3.1 (LTS)</span></span>         | `dotnet-runtime-31` |
| <span data-ttu-id="ceaf1-133">3.0</span><span class="sxs-lookup"><span data-stu-id="ceaf1-133">3.0</span></span>               | `dotnet-runtime-30` |
| <span data-ttu-id="ceaf1-134">2.2</span><span class="sxs-lookup"><span data-stu-id="ceaf1-134">2.2</span></span>               | `dotnet-runtime-22` |
| <span data-ttu-id="ceaf1-135">2.1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="ceaf1-135">2.1 (LTS)</span></span>         | `dotnet-runtime-21` |

<span data-ttu-id="ceaf1-136">Verwenden Sie den Befehl `snap install`, um ein Snap-Paket für die .NET Core-Runtime zu installieren.</span><span class="sxs-lookup"><span data-stu-id="ceaf1-136">Use the `snap install` command to install a .NET Core Runtime snap package.</span></span> <span data-ttu-id="ceaf1-137">In diesem Beispiel wird .NET Core 3.1 installiert:</span><span class="sxs-lookup"><span data-stu-id="ceaf1-137">In this example, .NET Core 3.1 is installed:</span></span>

```bash
sudo snap install dotnet-runtime-31 --classic
```

<span data-ttu-id="ceaf1-138">Registrieren Sie als Nächstes den Befehl `dotnet` für das System mit dem Befehl `snap alias`:</span><span class="sxs-lookup"><span data-stu-id="ceaf1-138">Next, register the `dotnet` command for the system with the `snap alias` command:</span></span>

```bash
sudo snap alias dotnet-runtime-31.dotnet dotnet
```

<span data-ttu-id="ceaf1-139">Dieser Befehl ist wie folgt formatiert: `sudo snap alias {package}.{command} {alias}`.</span><span class="sxs-lookup"><span data-stu-id="ceaf1-139">This command is formatted as: `sudo snap alias {package}.{command} {alias}`.</span></span> <span data-ttu-id="ceaf1-140">Sie können für `{alias}` einen beliebigen Namen auswählen.</span><span class="sxs-lookup"><span data-stu-id="ceaf1-140">You can choose any `{alias}` name you would like.</span></span> <span data-ttu-id="ceaf1-141">Beispielsweise können Sie den Befehl nach der spezifischen Version benennen, die mittels Snap installiert wurde: `sudo snap alias dotnet-runtime-31.dotnet dotnet31`.</span><span class="sxs-lookup"><span data-stu-id="ceaf1-141">For example, you could name the command after the specific version installed by snap: `sudo snap alias dotnet-runtime-31.dotnet dotnet31`.</span></span> <span data-ttu-id="ceaf1-142">Beim Verwenden des Befehls `dotnet31` rufen Sie diese spezifische Version von .NET auf.</span><span class="sxs-lookup"><span data-stu-id="ceaf1-142">When you use the command `dotnet31`, you'll invoke this specific version of .NET.</span></span> <span data-ttu-id="ceaf1-143">Diese ist jedoch mit den meisten Tutorials und Beispielen unvereinbar, da erwartet wird, dass ein `dotnet`-Befehl verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ceaf1-143">But this is incompatible with most tutorials and examples as they expect a `dotnet` command to be available.</span></span>

### <a name="ssl-certificate-errors"></a><span data-ttu-id="ceaf1-144">SSL-Zertifikatfehler</span><span class="sxs-lookup"><span data-stu-id="ceaf1-144">SSL Certificate errors</span></span>

<span data-ttu-id="ceaf1-145">Wenn .NET über Snap installiert wird, ist es möglich, dass bei einigen Distributionen die SSL-Zertifikate für .NET nicht gefunden werden und Sie während `restore` einen Fehler ähnlich dem folgenden erhalten:</span><span class="sxs-lookup"><span data-stu-id="ceaf1-145">When .NET is installed through Snap, it's possible that on some distros the .NET SSL certificates may not be found and you may receive an error similar to the following during `restore`:</span></span>

```bash
Processing post-creation actions...
Running 'dotnet restore' on /home/myhome/test/test.csproj...
  Restoring packages for /home/myhome/test/test.csproj...
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error : Unable to load the service index for source https://api.nuget.org/v3/index.json. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The SSL connection could not be established, see inner exception. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The remote certificate is invalid according to the validation procedure. [/home/myhome/test/test.csproj]
```

<span data-ttu-id="ceaf1-146">Um dieses Problem zu beheben, legen Sie einige Umgebungsvariablen fest:</span><span class="sxs-lookup"><span data-stu-id="ceaf1-146">To resolve this issue, set a few enviornment variables:</span></span>

```bash
export SSL_CERT_FILE=[path-to-certificate-file]
export SSL_CERT_DIR=/dev/null
```

<span data-ttu-id="ceaf1-147">Der Speicherort des Zertifikats variiert je nach Distribution.</span><span class="sxs-lookup"><span data-stu-id="ceaf1-147">The certificate location will vary by distro.</span></span> <span data-ttu-id="ceaf1-148">Hier finden Sie die Speicherorte für die Distributionen, in denen das Problem aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="ceaf1-148">Here are the locations for the distros where we have experienced the issue.</span></span>

* <span data-ttu-id="ceaf1-149">Fedora: `/etc/pki/ca-trust/extracted/pem/tls-ca-bundle.pem`</span><span class="sxs-lookup"><span data-stu-id="ceaf1-149">Fedora - `/etc/pki/ca-trust/extracted/pem/tls-ca-bundle.pem`</span></span>
* <span data-ttu-id="ceaf1-150">OpenSUSE: `/etc/ssl/ca-bundle.pem`</span><span class="sxs-lookup"><span data-stu-id="ceaf1-150">OpenSUSE - `/etc/ssl/ca-bundle.pem`</span></span>
* <span data-ttu-id="ceaf1-151">Solus: `/etc/ssl/certs/ca-certificates.crt`</span><span class="sxs-lookup"><span data-stu-id="ceaf1-151">Solus - `/etc/ssl/certs/ca-certificates.crt`</span></span>
