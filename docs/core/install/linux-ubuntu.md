---
title: 'Installieren von .NET unter Ubuntu: .NET'
description: In diesem Artikel werden verschiedene Möglichkeiten veranschaulicht, das .NET SDK und die .NET-Runtime unter Ubuntu zu installieren.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: 14e5e9548d4aa09a586e2038f3e35a489ee65cd2
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970764"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-ubuntu"></a><span data-ttu-id="f84ad-103">Installieren des .NET SDK oder der .NET-Runtime unter Ubuntu</span><span class="sxs-lookup"><span data-stu-id="f84ad-103">Install the .NET SDK or the .NET Runtime on Ubuntu</span></span>

<span data-ttu-id="f84ad-104">.NET wird unter Ubuntu unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f84ad-104">.NET is supported on Ubuntu.</span></span> <span data-ttu-id="f84ad-105">In diesem Artikel wird beschrieben, wie Sie .NET unter Ubuntu installieren.</span><span class="sxs-lookup"><span data-stu-id="f84ad-105">This article describes how to install .NET on Ubuntu.</span></span> <span data-ttu-id="f84ad-106">Wenn für eine Ubuntu-Version kein Support mehr geboten wird, wird .NET mit dieser Version nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f84ad-106">When an Ubuntu version falls out of support, .NET is no longer supported with that version.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="f84ad-107">Unterstützte Distributionen</span><span class="sxs-lookup"><span data-stu-id="f84ad-107">Supported distributions</span></span>

<span data-ttu-id="f84ad-108">Die folgende Tabelle enthält die derzeit unterstützten .NET-Releases und die Versionen von Ubuntu, unter denen sie unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="f84ad-108">The following table is a list of currently supported .NET releases and the versions of Ubuntu they're supported on.</span></span> <span data-ttu-id="f84ad-109">Diese Versionen werden weiterhin unterstützt, bis entweder die Version von [.NET das Ende des Supports](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) oder die Version von [Ubuntu das Ende ihrer Lebensdauer erreicht](https://wiki.ubuntu.com/Releases).</span><span class="sxs-lookup"><span data-stu-id="f84ad-109">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Ubuntu reaches end-of-life](https://wiki.ubuntu.com/Releases).</span></span>

- <span data-ttu-id="f84ad-110">✔️ gibt an, dass die Version von Ubuntu oder .NET Core weiterhin unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="f84ad-110">A ✔️ indicates that the version of Ubuntu or .NET is still supported.</span></span>
- <span data-ttu-id="f84ad-111">❌ gibt an, dass die Version von Ubuntu oder .NET unter diesem Ubuntu-Release nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="f84ad-111">A ❌ indicates that the version of Ubuntu or .NET isn't supported on that Ubuntu release.</span></span>
- <span data-ttu-id="f84ad-112">Wenn sowohl eine Version von Ubuntu als auch eine Version von .NET mit ✔️ markiert sind, wird diese Kombination aus Betriebssystem und .NET unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f84ad-112">When both a version of Ubuntu and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="f84ad-113">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="f84ad-113">Ubuntu</span></span>                   | <span data-ttu-id="f84ad-114">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="f84ad-114">.NET Core 2.1</span></span> | <span data-ttu-id="f84ad-115">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="f84ad-115">.NET Core 3.1</span></span> | <span data-ttu-id="f84ad-116">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="f84ad-116">.NET 5.0</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="f84ad-117">✔️ [20.10](#2010-)</span><span class="sxs-lookup"><span data-stu-id="f84ad-117">✔️ [20.10](#2010-)</span></span>       | <span data-ttu-id="f84ad-118">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="f84ad-118">✔️ 2.1</span></span>        | <span data-ttu-id="f84ad-119">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="f84ad-119">✔️ 3.1</span></span>        | <span data-ttu-id="f84ad-120">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="f84ad-120">✔️ 5.0</span></span> |
| <span data-ttu-id="f84ad-121">✔️ [20.04 (LTS)](#2004-)</span><span class="sxs-lookup"><span data-stu-id="f84ad-121">✔️ [20.04 (LTS)](#2004-)</span></span> | <span data-ttu-id="f84ad-122">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="f84ad-122">✔️ 2.1</span></span>        | <span data-ttu-id="f84ad-123">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="f84ad-123">✔️ 3.1</span></span>        | <span data-ttu-id="f84ad-124">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="f84ad-124">✔️ 5.0</span></span> |
| <span data-ttu-id="f84ad-125">❌ [19.10](#1910-)</span><span class="sxs-lookup"><span data-stu-id="f84ad-125">❌ [19.10](#1910-)</span></span>       | <span data-ttu-id="f84ad-126">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="f84ad-126">✔️ 2.1</span></span>        | <span data-ttu-id="f84ad-127">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="f84ad-127">✔️ 3.1</span></span>        | <span data-ttu-id="f84ad-128">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="f84ad-128">✔️ 5.0</span></span> |
| <span data-ttu-id="f84ad-129">❌ [19.04](#1904-)</span><span class="sxs-lookup"><span data-stu-id="f84ad-129">❌ [19.04](#1904-)</span></span>       | <span data-ttu-id="f84ad-130">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="f84ad-130">✔️ 2.1</span></span>        | <span data-ttu-id="f84ad-131">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="f84ad-131">✔️ 3.1</span></span>        | <span data-ttu-id="f84ad-132">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="f84ad-132">❌ 5.0</span></span> |
| <span data-ttu-id="f84ad-133">❌ [18.10](#1810-)</span><span class="sxs-lookup"><span data-stu-id="f84ad-133">❌ [18.10](#1810-)</span></span>       | <span data-ttu-id="f84ad-134">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="f84ad-134">✔️ 2.1</span></span>        | <span data-ttu-id="f84ad-135">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="f84ad-135">❌ 3.1</span></span>        | <span data-ttu-id="f84ad-136">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="f84ad-136">❌ 5.0</span></span> |
| <span data-ttu-id="f84ad-137">✔️ [18.04 (LTS)](#1804-)</span><span class="sxs-lookup"><span data-stu-id="f84ad-137">✔️ [18.04 (LTS)](#1804-)</span></span> | <span data-ttu-id="f84ad-138">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="f84ad-138">✔️ 2.1</span></span>        | <span data-ttu-id="f84ad-139">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="f84ad-139">✔️ 3.1</span></span>        | <span data-ttu-id="f84ad-140">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="f84ad-140">✔️ 5.0</span></span> |
| <span data-ttu-id="f84ad-141">❌ [17.10](#1710-)</span><span class="sxs-lookup"><span data-stu-id="f84ad-141">❌ [17.10](#1710-)</span></span>       | <span data-ttu-id="f84ad-142">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="f84ad-142">✔️ 2.1</span></span>        | <span data-ttu-id="f84ad-143">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="f84ad-143">❌ 3.1</span></span>        | <span data-ttu-id="f84ad-144">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="f84ad-144">❌ 5.0</span></span> |
| <span data-ttu-id="f84ad-145">❌ [17.04](#1704-)</span><span class="sxs-lookup"><span data-stu-id="f84ad-145">❌ [17.04](#1704-)</span></span>       | <span data-ttu-id="f84ad-146">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="f84ad-146">✔️ 2.1</span></span>        | <span data-ttu-id="f84ad-147">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="f84ad-147">❌ 3.1</span></span>        | <span data-ttu-id="f84ad-148">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="f84ad-148">❌ 5.0</span></span> |
| <span data-ttu-id="f84ad-149">❌ [16.10](#1610-)</span><span class="sxs-lookup"><span data-stu-id="f84ad-149">❌ [16.10](#1610-)</span></span>       | <span data-ttu-id="f84ad-150">❌ 2.1</span><span class="sxs-lookup"><span data-stu-id="f84ad-150">❌ 2.1</span></span>        | <span data-ttu-id="f84ad-151">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="f84ad-151">❌ 3.1</span></span>        | <span data-ttu-id="f84ad-152">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="f84ad-152">❌ 5.0</span></span> |
| <span data-ttu-id="f84ad-153">✔️ [16.04 (LTS)](#1604-)</span><span class="sxs-lookup"><span data-stu-id="f84ad-153">✔️ [16.04 (LTS)](#1604-)</span></span> | <span data-ttu-id="f84ad-154">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="f84ad-154">✔️ 2.1</span></span>        | <span data-ttu-id="f84ad-155">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="f84ad-155">✔️ 3.1</span></span>        | <span data-ttu-id="f84ad-156">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="f84ad-156">✔️ 5.0</span></span> |

<span data-ttu-id="f84ad-157">Die folgenden Versionen von .NET werden nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f84ad-157">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="f84ad-158">Die Downloads dafür bleiben weiterhin veröffentlicht:</span><span class="sxs-lookup"><span data-stu-id="f84ad-158">The downloads for these still remain published:</span></span>

- <span data-ttu-id="f84ad-159">3.0</span><span class="sxs-lookup"><span data-stu-id="f84ad-159">3.0</span></span>
- <span data-ttu-id="f84ad-160">2.2</span><span class="sxs-lookup"><span data-stu-id="f84ad-160">2.2</span></span>
- <span data-ttu-id="f84ad-161">2.0</span><span class="sxs-lookup"><span data-stu-id="f84ad-161">2.0</span></span>

## <a name="remove-preview-versions"></a><span data-ttu-id="f84ad-162">Entfernen von Vorschauversionen</span><span class="sxs-lookup"><span data-stu-id="f84ad-162">Remove preview versions</span></span>

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="2010-"></a><span data-ttu-id="f84ad-163">20.10 ✔️</span><span class="sxs-lookup"><span data-stu-id="f84ad-163">20.10 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/20.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="2004-"></a><span data-ttu-id="f84ad-164">20.04 ✔️</span><span class="sxs-lookup"><span data-stu-id="f84ad-164">20.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="1910-"></a><span data-ttu-id="f84ad-165">19.10 ❌</span><span class="sxs-lookup"><span data-stu-id="f84ad-165">19.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/19.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1904-"></a><span data-ttu-id="f84ad-166">19.04 ❌</span><span class="sxs-lookup"><span data-stu-id="f84ad-166">19.04 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/19.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1810-"></a><span data-ttu-id="f84ad-167">18.10 ❌</span><span class="sxs-lookup"><span data-stu-id="f84ad-167">18.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/18.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1804-"></a><span data-ttu-id="f84ad-168">18.04 ✔️</span><span class="sxs-lookup"><span data-stu-id="f84ad-168">18.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="1710-"></a><span data-ttu-id="f84ad-169">17.10 ❌</span><span class="sxs-lookup"><span data-stu-id="f84ad-169">17.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/17.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1704-"></a><span data-ttu-id="f84ad-170">17.04 ❌</span><span class="sxs-lookup"><span data-stu-id="f84ad-170">17.04 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/17.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1610-"></a><span data-ttu-id="f84ad-171">16.10 ❌</span><span class="sxs-lookup"><span data-stu-id="f84ad-171">16.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/16.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1604-"></a><span data-ttu-id="f84ad-172">16.04 ✔️</span><span class="sxs-lookup"><span data-stu-id="f84ad-172">16.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/16.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="f84ad-173">Installieren anderer Versionen</span><span class="sxs-lookup"><span data-stu-id="f84ad-173">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="use-apt-to-update-net"></a><span data-ttu-id="f84ad-174">Verwenden von APT zum Aktualisieren von .NET</span><span class="sxs-lookup"><span data-stu-id="f84ad-174">Use APT to update .NET</span></span>

<span data-ttu-id="f84ad-175">Wenn ein neues Patchrelease für .NET verfügbar ist, können Sie dieses einfach über APT mit den folgenden Befehlen aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="f84ad-175">When a new patch release is available for .NET, you can simply upgrade it through APT with the following commands:</span></span>

```bash
sudo apt-get update
sudo apt-get upgrade
```

## <a name="apt-troubleshooting"></a><span data-ttu-id="f84ad-176">Problembehandlung für APT</span><span class="sxs-lookup"><span data-stu-id="f84ad-176">APT troubleshooting</span></span>

<span data-ttu-id="f84ad-177">Dieser Abschnitt enthält Informationen zu häufigen Fehlern, die bei der Installation von .NET mit APT auftreten können.</span><span class="sxs-lookup"><span data-stu-id="f84ad-177">This section provides information on common errors you may get while using APT to install .NET.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="f84ad-178">Paket konnte nicht gefunden werden</span><span class="sxs-lookup"><span data-stu-id="f84ad-178">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="unable-to-locate--some-packages-could-not-be-installed"></a><span data-ttu-id="f84ad-179">"Das Paket kann nicht gefunden werden"/"Die Pakete konnten nicht installiert werden"</span><span class="sxs-lookup"><span data-stu-id="f84ad-179">Unable to locate \\ Some packages could not be installed</span></span>

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

### <a name="failed-to-fetch"></a><span data-ttu-id="f84ad-180">Fehler beim Abrufen</span><span class="sxs-lookup"><span data-stu-id="f84ad-180">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]

## <a name="dependencies"></a><span data-ttu-id="f84ad-181">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="f84ad-181">Dependencies</span></span>

<span data-ttu-id="f84ad-182">Wenn die Installation mit einem Paket-Manager erfolgt, werden diese Bibliotheken für Sie installiert.</span><span class="sxs-lookup"><span data-stu-id="f84ad-182">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="f84ad-183">Wenn Sie jedoch .NET manuell installieren oder eine eigenständige Anwendung veröffentlichen, müssen Sie sicherstellen, dass diese Bibliotheken installiert sind:</span><span class="sxs-lookup"><span data-stu-id="f84ad-183">But, if you manually install .NET or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="f84ad-184">libc6</span><span class="sxs-lookup"><span data-stu-id="f84ad-184">libc6</span></span>
- <span data-ttu-id="f84ad-185">libgcc1</span><span class="sxs-lookup"><span data-stu-id="f84ad-185">libgcc1</span></span>
- <span data-ttu-id="f84ad-186">libgssapi-krb5-2</span><span class="sxs-lookup"><span data-stu-id="f84ad-186">libgssapi-krb5-2</span></span>
- <span data-ttu-id="f84ad-187">libicu52 (für 14.X)</span><span class="sxs-lookup"><span data-stu-id="f84ad-187">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="f84ad-188">libicu55 (für 16.X)</span><span class="sxs-lookup"><span data-stu-id="f84ad-188">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="f84ad-189">libicu60 (für 18.X)</span><span class="sxs-lookup"><span data-stu-id="f84ad-189">libicu60 (for 18.x)</span></span>
- <span data-ttu-id="f84ad-190">libicu66 (für 20.x)</span><span class="sxs-lookup"><span data-stu-id="f84ad-190">libicu66 (for 20.x)</span></span>
- <span data-ttu-id="f84ad-191">libssl1.0.0 (für 14.x, 16.x)</span><span class="sxs-lookup"><span data-stu-id="f84ad-191">libssl1.0.0 (for 14.x, 16.x)</span></span>
- <span data-ttu-id="f84ad-192">libssl1.1 (für 18.x, 20.x)</span><span class="sxs-lookup"><span data-stu-id="f84ad-192">libssl1.1 (for 18.x, 20.x)</span></span>
- <span data-ttu-id="f84ad-193">libstdc++6</span><span class="sxs-lookup"><span data-stu-id="f84ad-193">libstdc++6</span></span>
- <span data-ttu-id="f84ad-194">zlib1g</span><span class="sxs-lookup"><span data-stu-id="f84ad-194">zlib1g</span></span>

<span data-ttu-id="f84ad-195">Für .NET-Apps, die die Assembly *System.Drawing.Common* verwenden, benötigen Sie außerdem die folgende Abhängigkeit:</span><span class="sxs-lookup"><span data-stu-id="f84ad-195">For .NET apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="f84ad-196">libgdiplus (Version 6.0.1 oder höher)</span><span class="sxs-lookup"><span data-stu-id="f84ad-196">libgdiplus (version 6.0.1 or later)</span></span>

  > [!WARNING]
  > <span data-ttu-id="f84ad-197">Sie können eine neuere Version von *libgdiplus* installieren, indem Sie Ihrem System das Mono-Repository hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f84ad-197">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="f84ad-198">Weitere Informationen finden Sie unter <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="f84ad-198">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f84ad-199">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f84ad-199">Next steps</span></span>

- [<span data-ttu-id="f84ad-200">Aktivieren der Vervollständigung mit der TAB-TASTE für die .NET-CLI</span><span class="sxs-lookup"><span data-stu-id="f84ad-200">How to enable TAB completion for the .NET CLI</span></span>](../tools/enable-tab-autocomplete.md)
- [<span data-ttu-id="f84ad-201">Tutorial: Erstellen einer Konsolenanwendung mit dem .NET SDK in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f84ad-201">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
