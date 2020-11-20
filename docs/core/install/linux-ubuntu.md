---
title: 'Installieren von .NET unter Ubuntu: .NET'
description: In diesem Artikel werden verschiedene Möglichkeiten veranschaulicht, das .NET SDK und die .NET-Runtime unter Ubuntu zu installieren.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 419bcf3ccd011cadba8f8c64e195d7dbdbf7e241
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2020
ms.locfileid: "94507026"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-ubuntu"></a><span data-ttu-id="dbc42-103">Installieren des .NET SDK oder der .NET-Runtime unter Ubuntu</span><span class="sxs-lookup"><span data-stu-id="dbc42-103">Install the .NET SDK or the .NET Runtime on Ubuntu</span></span>

<span data-ttu-id="dbc42-104">.NET wird unter Ubuntu unterstützt.</span><span class="sxs-lookup"><span data-stu-id="dbc42-104">.NET is supported on Ubuntu.</span></span> <span data-ttu-id="dbc42-105">In diesem Artikel wird beschrieben, wie Sie .NET unter Ubuntu installieren.</span><span class="sxs-lookup"><span data-stu-id="dbc42-105">This article describes how to install .NET on Ubuntu.</span></span> <span data-ttu-id="dbc42-106">Wenn für eine Ubuntu-Version kein Support mehr geboten wird, wird .NET mit dieser Version nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="dbc42-106">When an Ubuntu version falls out of support, .NET is no longer supported with that version.</span></span> <span data-ttu-id="dbc42-107">Diese Anweisungen können Ihnen jedoch helfen, .NET in diesen Versionen auszuführen, auch wenn sie nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="dbc42-107">However, these instructions may help you to get .NET running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="dbc42-108">Unterstützte Distributionen</span><span class="sxs-lookup"><span data-stu-id="dbc42-108">Supported distributions</span></span>

<span data-ttu-id="dbc42-109">Die folgende Tabelle enthält die derzeit unterstützten .NET-Releases und die Versionen von Ubuntu, unter denen sie unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="dbc42-109">The following table is a list of currently supported .NET releases and the versions of Ubuntu they're supported on.</span></span> <span data-ttu-id="dbc42-110">Diese Versionen werden weiterhin unterstützt, bis entweder die Version von [.NET das Ende des Supports](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) oder die Version von [Ubuntu das Ende ihrer Lebensdauer erreicht](https://wiki.ubuntu.com/Releases).</span><span class="sxs-lookup"><span data-stu-id="dbc42-110">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Ubuntu reaches end-of-life](https://wiki.ubuntu.com/Releases).</span></span>

- <span data-ttu-id="dbc42-111">✔️ gibt an, dass die Version von Ubuntu oder .NET Core weiterhin unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="dbc42-111">A ✔️ indicates that the version of Ubuntu or .NET is still supported.</span></span>
- <span data-ttu-id="dbc42-112">❌ gibt an, dass die Version von Ubuntu oder .NET unter diesem Ubuntu-Release nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="dbc42-112">A ❌ indicates that the version of Ubuntu or .NET isn't supported on that Ubuntu release.</span></span>
- <span data-ttu-id="dbc42-113">Wenn sowohl eine Version von Ubuntu als auch eine Version von .NET mit ✔️ markiert sind, wird diese Kombination aus Betriebssystem und .NET unterstützt.</span><span class="sxs-lookup"><span data-stu-id="dbc42-113">When both a version of Ubuntu and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="dbc42-114">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="dbc42-114">Ubuntu</span></span>                   | <span data-ttu-id="dbc42-115">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="dbc42-115">.NET Core 2.1</span></span> | <span data-ttu-id="dbc42-116">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="dbc42-116">.NET Core 3.1</span></span> | <span data-ttu-id="dbc42-117">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="dbc42-117">.NET 5.0</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="dbc42-118">✔️ [20.10](#2010-)</span><span class="sxs-lookup"><span data-stu-id="dbc42-118">✔️ [20.10](#2010-)</span></span>       | <span data-ttu-id="dbc42-119">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="dbc42-119">✔️ 2.1</span></span>        | <span data-ttu-id="dbc42-120">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="dbc42-120">✔️ 3.1</span></span>        | <span data-ttu-id="dbc42-121">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="dbc42-121">✔️ 5.0</span></span> |
| <span data-ttu-id="dbc42-122">✔️ [20.04 (LTS)](#2004-)</span><span class="sxs-lookup"><span data-stu-id="dbc42-122">✔️ [20.04 (LTS)](#2004-)</span></span> | <span data-ttu-id="dbc42-123">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="dbc42-123">✔️ 2.1</span></span>        | <span data-ttu-id="dbc42-124">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="dbc42-124">✔️ 3.1</span></span>        | <span data-ttu-id="dbc42-125">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="dbc42-125">✔️ 5.0</span></span> |
| <span data-ttu-id="dbc42-126">❌ [19.10](#1910-)</span><span class="sxs-lookup"><span data-stu-id="dbc42-126">❌ [19.10](#1910-)</span></span>       | <span data-ttu-id="dbc42-127">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="dbc42-127">✔️ 2.1</span></span>        | <span data-ttu-id="dbc42-128">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="dbc42-128">✔️ 3.1</span></span>        | <span data-ttu-id="dbc42-129">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="dbc42-129">✔️ 5.0</span></span> |
| <span data-ttu-id="dbc42-130">❌ [19.04](#1904-)</span><span class="sxs-lookup"><span data-stu-id="dbc42-130">❌ [19.04](#1904-)</span></span>       | <span data-ttu-id="dbc42-131">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="dbc42-131">✔️ 2.1</span></span>        | <span data-ttu-id="dbc42-132">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="dbc42-132">✔️ 3.1</span></span>        | <span data-ttu-id="dbc42-133">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="dbc42-133">❌ 5.0</span></span> |
| <span data-ttu-id="dbc42-134">❌ [18.10](#1810-)</span><span class="sxs-lookup"><span data-stu-id="dbc42-134">❌ [18.10](#1810-)</span></span>       | <span data-ttu-id="dbc42-135">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="dbc42-135">✔️ 2.1</span></span>        | <span data-ttu-id="dbc42-136">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="dbc42-136">❌ 3.1</span></span>        | <span data-ttu-id="dbc42-137">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="dbc42-137">❌ 5.0</span></span> |
| <span data-ttu-id="dbc42-138">✔️ [18.04 (LTS)](#1804-)</span><span class="sxs-lookup"><span data-stu-id="dbc42-138">✔️ [18.04 (LTS)](#1804-)</span></span> | <span data-ttu-id="dbc42-139">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="dbc42-139">✔️ 2.1</span></span>        | <span data-ttu-id="dbc42-140">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="dbc42-140">✔️ 3.1</span></span>        | <span data-ttu-id="dbc42-141">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="dbc42-141">✔️ 5.0</span></span> |
| <span data-ttu-id="dbc42-142">❌ [17.10](#1710-)</span><span class="sxs-lookup"><span data-stu-id="dbc42-142">❌ [17.10](#1710-)</span></span>       | <span data-ttu-id="dbc42-143">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="dbc42-143">✔️ 2.1</span></span>        | <span data-ttu-id="dbc42-144">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="dbc42-144">❌ 3.1</span></span>        | <span data-ttu-id="dbc42-145">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="dbc42-145">❌ 5.0</span></span> |
| <span data-ttu-id="dbc42-146">❌ [17.04](#1704-)</span><span class="sxs-lookup"><span data-stu-id="dbc42-146">❌ [17.04](#1704-)</span></span>       | <span data-ttu-id="dbc42-147">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="dbc42-147">✔️ 2.1</span></span>        | <span data-ttu-id="dbc42-148">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="dbc42-148">❌ 3.1</span></span>        | <span data-ttu-id="dbc42-149">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="dbc42-149">❌ 5.0</span></span> |
| <span data-ttu-id="dbc42-150">❌ [16.10](#1610-)</span><span class="sxs-lookup"><span data-stu-id="dbc42-150">❌ [16.10](#1610-)</span></span>       | <span data-ttu-id="dbc42-151">❌ 2.1</span><span class="sxs-lookup"><span data-stu-id="dbc42-151">❌ 2.1</span></span>        | <span data-ttu-id="dbc42-152">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="dbc42-152">❌ 3.1</span></span>        | <span data-ttu-id="dbc42-153">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="dbc42-153">❌ 5.0</span></span> |
| <span data-ttu-id="dbc42-154">✔️ [16.04 (LTS)](#1604-)</span><span class="sxs-lookup"><span data-stu-id="dbc42-154">✔️ [16.04 (LTS)](#1604-)</span></span> | <span data-ttu-id="dbc42-155">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="dbc42-155">✔️ 2.1</span></span>        | <span data-ttu-id="dbc42-156">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="dbc42-156">✔️ 3.1</span></span>        | <span data-ttu-id="dbc42-157">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="dbc42-157">✔️ 5.0</span></span> |

<span data-ttu-id="dbc42-158">Die folgenden Versionen von .NET werden nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="dbc42-158">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="dbc42-159">Die Downloads dafür bleiben weiterhin veröffentlicht:</span><span class="sxs-lookup"><span data-stu-id="dbc42-159">The downloads for these still remain published:</span></span>

- <span data-ttu-id="dbc42-160">3.0</span><span class="sxs-lookup"><span data-stu-id="dbc42-160">3.0</span></span>
- <span data-ttu-id="dbc42-161">2.2</span><span class="sxs-lookup"><span data-stu-id="dbc42-161">2.2</span></span>
- <span data-ttu-id="dbc42-162">2.0</span><span class="sxs-lookup"><span data-stu-id="dbc42-162">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="dbc42-163">Installieren anderer Versionen</span><span class="sxs-lookup"><span data-stu-id="dbc42-163">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="2010-"></a><span data-ttu-id="dbc42-164">20.10 ✔️</span><span class="sxs-lookup"><span data-stu-id="dbc42-164">20.10 ✔️</span></span>

<span data-ttu-id="dbc42-165">Die .NET 5- und .NET Core 3.1-Paketfeeds für Ubuntu 20.10 haben derzeit ein Problem.</span><span class="sxs-lookup"><span data-stu-id="dbc42-165">.NET 5 and .NET Core 3.1 package feeds for Ubuntu 20.10 currently have an issue.</span></span> <span data-ttu-id="dbc42-166">Weitere Informationen zu diesem Problem finden Sie unter dem [GitHub-Issue dotnet/core#5549](https://github.com/dotnet/core/issues/5549).</span><span class="sxs-lookup"><span data-stu-id="dbc42-166">For more information about the issue, see [GitHub issue dotnet/core#5549](https://github.com/dotnet/core/issues/5549).</span></span> <span data-ttu-id="dbc42-167">Dieser Artikel wird aktualisiert, sobald das Problem gelöst ist.</span><span class="sxs-lookup"><span data-stu-id="dbc42-167">This article will be updated when the issue is resolved.</span></span>

<span data-ttu-id="dbc42-168">Befolgen Sie zur Installation von .NET 5 oder .NET Core 3.1 unter Ubuntu 20.10 die Anleitung für [20.04](#2004-).</span><span class="sxs-lookup"><span data-stu-id="dbc42-168">To install .NET 5 or .NET Core 3.1 on Ubuntu 20.10, follow the instructions for [20.04](#2004-).</span></span>

## <a name="2004-"></a><span data-ttu-id="dbc42-169">20.04 ✔️</span><span class="sxs-lookup"><span data-stu-id="dbc42-169">20.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="1910-"></a><span data-ttu-id="dbc42-170">19.10 ❌</span><span class="sxs-lookup"><span data-stu-id="dbc42-170">19.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/19.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1904-"></a><span data-ttu-id="dbc42-171">19.04 ❌</span><span class="sxs-lookup"><span data-stu-id="dbc42-171">19.04 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/19.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1810-"></a><span data-ttu-id="dbc42-172">18.10 ❌</span><span class="sxs-lookup"><span data-stu-id="dbc42-172">18.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/18.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1804-"></a><span data-ttu-id="dbc42-173">18.04 ✔️</span><span class="sxs-lookup"><span data-stu-id="dbc42-173">18.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="1710-"></a><span data-ttu-id="dbc42-174">17.10 ❌</span><span class="sxs-lookup"><span data-stu-id="dbc42-174">17.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/17.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1704-"></a><span data-ttu-id="dbc42-175">17.04 ❌</span><span class="sxs-lookup"><span data-stu-id="dbc42-175">17.04 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/17.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1610-"></a><span data-ttu-id="dbc42-176">16.10 ❌</span><span class="sxs-lookup"><span data-stu-id="dbc42-176">16.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/16.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1604-"></a><span data-ttu-id="dbc42-177">16.04 ✔️</span><span class="sxs-lookup"><span data-stu-id="dbc42-177">16.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/16.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="apt-update-sdk-or-runtime"></a><span data-ttu-id="dbc42-178">APT Update SDK oder Runtime</span><span class="sxs-lookup"><span data-stu-id="dbc42-178">APT update SDK or runtime</span></span>

<span data-ttu-id="dbc42-179">Wenn ein neues Patchrelease für .NET verfügbar ist, können Sie dieses einfach über APT mit den folgenden Befehlen aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="dbc42-179">When a new patch release is available for .NET, you can simply upgrade it through APT with the following commands:</span></span>

```bash
sudo apt-get update
sudo apt-get upgrade
```

## <a name="apt-troubleshooting"></a><span data-ttu-id="dbc42-180">Problembehandlung für APT</span><span class="sxs-lookup"><span data-stu-id="dbc42-180">APT troubleshooting</span></span>

<span data-ttu-id="dbc42-181">Dieser Abschnitt enthält Informationen zu häufigen Fehlern, die bei der Installation von .NET mit APT auftreten können.</span><span class="sxs-lookup"><span data-stu-id="dbc42-181">This section provides information on common errors you may get while using APT to install .NET.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="dbc42-182">Paket konnte nicht gefunden werden</span><span class="sxs-lookup"><span data-stu-id="dbc42-182">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="unable-to-locate--some-packages-could-not-be-installed"></a><span data-ttu-id="dbc42-183">"Das Paket kann nicht gefunden werden"/"Die Pakete konnten nicht installiert werden"</span><span class="sxs-lookup"><span data-stu-id="dbc42-183">Unable to locate \\ Some packages could not be installed</span></span>

[!INCLUDE [package-manager-failed-to-find-deb](includes/package-manager-failed-to-find-deb.md)]

```bash
sudo apt-get install -y gpg
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor -o microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/ubuntu/{os-version}/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y {dotnet-package}
```

### <a name="failed-to-fetch"></a><span data-ttu-id="dbc42-184">Fehler beim Abrufen</span><span class="sxs-lookup"><span data-stu-id="dbc42-184">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]

## <a name="snap"></a><span data-ttu-id="dbc42-185">Snap</span><span class="sxs-lookup"><span data-stu-id="dbc42-185">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="dbc42-186">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="dbc42-186">Dependencies</span></span>

<span data-ttu-id="dbc42-187">Wenn die Installation mit einem Paket-Manager erfolgt, werden diese Bibliotheken für Sie installiert.</span><span class="sxs-lookup"><span data-stu-id="dbc42-187">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="dbc42-188">Wenn Sie jedoch .NET manuell installieren oder eine eigenständige Anwendung veröffentlichen, müssen Sie sicherstellen, dass diese Bibliotheken installiert sind:</span><span class="sxs-lookup"><span data-stu-id="dbc42-188">But, if you manually install .NET or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="dbc42-189">libc6</span><span class="sxs-lookup"><span data-stu-id="dbc42-189">libc6</span></span>
- <span data-ttu-id="dbc42-190">libgcc1</span><span class="sxs-lookup"><span data-stu-id="dbc42-190">libgcc1</span></span>
- <span data-ttu-id="dbc42-191">libgssapi-krb5-2</span><span class="sxs-lookup"><span data-stu-id="dbc42-191">libgssapi-krb5-2</span></span>
- <span data-ttu-id="dbc42-192">libicu52 (für 14.X)</span><span class="sxs-lookup"><span data-stu-id="dbc42-192">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="dbc42-193">libicu55 (für 16.X)</span><span class="sxs-lookup"><span data-stu-id="dbc42-193">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="dbc42-194">libicu60 (für 18.X)</span><span class="sxs-lookup"><span data-stu-id="dbc42-194">libicu60 (for 18.x)</span></span>
- <span data-ttu-id="dbc42-195">libicu66 (für 20.x)</span><span class="sxs-lookup"><span data-stu-id="dbc42-195">libicu66 (for 20.x)</span></span>
- <span data-ttu-id="dbc42-196">libssl1.0.0 (für 14.x, 16.x)</span><span class="sxs-lookup"><span data-stu-id="dbc42-196">libssl1.0.0 (for 14.x, 16.x)</span></span>
- <span data-ttu-id="dbc42-197">libssl1.1 (für 18.x, 20.x)</span><span class="sxs-lookup"><span data-stu-id="dbc42-197">libssl1.1 (for 18.x, 20.x)</span></span>
- <span data-ttu-id="dbc42-198">libstdc++6</span><span class="sxs-lookup"><span data-stu-id="dbc42-198">libstdc++6</span></span>
- <span data-ttu-id="dbc42-199">zlib1g</span><span class="sxs-lookup"><span data-stu-id="dbc42-199">zlib1g</span></span>

<span data-ttu-id="dbc42-200">Für .NET-Apps, die die Assembly *System.Drawing.Common* verwenden, benötigen Sie außerdem die folgende Abhängigkeit:</span><span class="sxs-lookup"><span data-stu-id="dbc42-200">For .NET apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="dbc42-201">libgdiplus (Version 6.0.1 oder höher)</span><span class="sxs-lookup"><span data-stu-id="dbc42-201">libgdiplus (version 6.0.1 or later)</span></span>

  > [!WARNING]
  > <span data-ttu-id="dbc42-202">Sie können eine neuere Version von *libgdiplus* installieren, indem Sie Ihrem System das Mono-Repository hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="dbc42-202">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="dbc42-203">Weitere Informationen finden Sie unter <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="dbc42-203">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="scripted-install"></a><span data-ttu-id="dbc42-204">Per Skript gesteuerte Installation</span><span class="sxs-lookup"><span data-stu-id="dbc42-204">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="dbc42-205">Manuelle Installation</span><span class="sxs-lookup"><span data-stu-id="dbc42-205">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="dbc42-206">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="dbc42-206">Next steps</span></span>

- [<span data-ttu-id="dbc42-207">Tutorial: Erstellen einer Konsolenanwendung mit dem .NET SDK in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="dbc42-207">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
