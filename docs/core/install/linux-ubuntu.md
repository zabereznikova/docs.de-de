---
title: Installieren von .NET Core unter Ubuntu (.NET Core)
description: Veranschaulicht verschiedene Möglichkeiten, das .NET Core SDK und die NET Core-Runtime unter Ubuntu zu installieren.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 5c07de20110a1aecf2ec5cb9de88f204625e548d
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538452"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-ubuntu"></a><span data-ttu-id="339bc-103">Installieren des .NET Core SDK oder der .NET Core-Runtime unter Ubuntu</span><span class="sxs-lookup"><span data-stu-id="339bc-103">Install .NET Core SDK or .NET Core Runtime on Ubuntu</span></span>

<span data-ttu-id="339bc-104">.NET Core wird unter Ubuntu unterstützt.</span><span class="sxs-lookup"><span data-stu-id="339bc-104">.NET Core is supported on Ubuntu.</span></span> <span data-ttu-id="339bc-105">In diesem Artikel wird beschrieben, wie Sie .NET Core unter Ubuntu installieren.</span><span class="sxs-lookup"><span data-stu-id="339bc-105">This article describes how to install .NET Core on Ubuntu.</span></span> <span data-ttu-id="339bc-106">Wenn für eine Ubuntu-Version kein Support mehr geboten wird, wird .NET Core mit dieser Version nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="339bc-106">When an Ubuntu version falls out of support, .NET Core is no longer supported with that version.</span></span> <span data-ttu-id="339bc-107">Diese Anweisungen können Ihnen jedoch helfen, .NET Core in diesen Versionen auszuführen, auch wenn kein Support dafür geboten wird.</span><span class="sxs-lookup"><span data-stu-id="339bc-107">However, these instructions may help you to get .NET Core running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="339bc-108">Unterstützte Distributionen</span><span class="sxs-lookup"><span data-stu-id="339bc-108">Supported distributions</span></span>

<span data-ttu-id="339bc-109">Die folgende Tabelle ist eine Liste der derzeit unter Ubuntu unterstützten .NET Core-Versionen.</span><span class="sxs-lookup"><span data-stu-id="339bc-109">The following table is a list of currently supported .NET Core releases and the versions of Ubuntu they're supported on.</span></span> <span data-ttu-id="339bc-110">Diese Versionen werden weiterhin unterstützt, bis entweder die Version von [.NET Core das Ende des Supports](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) oder die Version von [Ubuntu das Ende ihrer Lebensdauer erreicht](https://wiki.ubuntu.com/Releases).</span><span class="sxs-lookup"><span data-stu-id="339bc-110">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Ubuntu reaches end-of-life](https://wiki.ubuntu.com/Releases).</span></span>

- <span data-ttu-id="339bc-111">✔️ gibt an, dass die Version von Ubuntu oder .NET Core weiterhin unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="339bc-111">A ✔️ indicates that the version of Ubuntu or .NET Core is still supported.</span></span>
- <span data-ttu-id="339bc-112">❌ gibt an, dass die Version von Ubuntu oder .NET Core in dieser Ubuntu-Version nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="339bc-112">A ❌ indicates that the version of Ubuntu or .NET Core isn't supported on that Ubuntu release.</span></span>
- <span data-ttu-id="339bc-113">Wenn sowohl eine Version von Ubuntu als auch eine Version von .NET Core über ✔️ verfügen, wird diese Kombination aus Betriebssystem und .NET unterstützt.</span><span class="sxs-lookup"><span data-stu-id="339bc-113">When both a version of Ubuntu and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="339bc-114">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="339bc-114">Ubuntu</span></span>                   | <span data-ttu-id="339bc-115">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="339bc-115">.NET Core 2.1</span></span> | <span data-ttu-id="339bc-116">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="339bc-116">.NET Core 3.1</span></span> | <span data-ttu-id="339bc-117">.NET 5 Preview (nur manuelle Installation)</span><span class="sxs-lookup"><span data-stu-id="339bc-117">.NET 5 Preview (manual install only)</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="339bc-118">✔️ [20.04 (LTS)](#2004-)</span><span class="sxs-lookup"><span data-stu-id="339bc-118">✔️ [20.04 (LTS)](#2004-)</span></span> | <span data-ttu-id="339bc-119">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="339bc-119">✔️ 2.1</span></span>        | <span data-ttu-id="339bc-120">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="339bc-120">✔️ 3.1</span></span>        | <span data-ttu-id="339bc-121">✔️ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="339bc-121">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="339bc-122">❌ [19.10](#1910-)</span><span class="sxs-lookup"><span data-stu-id="339bc-122">❌ [19.10](#1910-)</span></span>       | <span data-ttu-id="339bc-123">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="339bc-123">✔️ 2.1</span></span>        | <span data-ttu-id="339bc-124">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="339bc-124">✔️ 3.1</span></span>        | <span data-ttu-id="339bc-125">✔️ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="339bc-125">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="339bc-126">❌ [19.04](#1904-)</span><span class="sxs-lookup"><span data-stu-id="339bc-126">❌ [19.04](#1904-)</span></span>       | <span data-ttu-id="339bc-127">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="339bc-127">✔️ 2.1</span></span>        | <span data-ttu-id="339bc-128">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="339bc-128">✔️ 3.1</span></span>        | <span data-ttu-id="339bc-129">❌ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="339bc-129">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="339bc-130">❌ [18.10](#1810-)</span><span class="sxs-lookup"><span data-stu-id="339bc-130">❌ [18.10](#1810-)</span></span>       | <span data-ttu-id="339bc-131">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="339bc-131">✔️ 2.1</span></span>        | <span data-ttu-id="339bc-132">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="339bc-132">❌ 3.1</span></span>        | <span data-ttu-id="339bc-133">❌ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="339bc-133">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="339bc-134">✔️ [18.04 (LTS)](#1804-)</span><span class="sxs-lookup"><span data-stu-id="339bc-134">✔️ [18.04 (LTS)](#1804-)</span></span> | <span data-ttu-id="339bc-135">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="339bc-135">✔️ 2.1</span></span>        | <span data-ttu-id="339bc-136">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="339bc-136">✔️ 3.1</span></span>        | <span data-ttu-id="339bc-137">✔️ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="339bc-137">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="339bc-138">❌ [17.10](#1710-)</span><span class="sxs-lookup"><span data-stu-id="339bc-138">❌ [17.10](#1710-)</span></span>       | <span data-ttu-id="339bc-139">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="339bc-139">✔️ 2.1</span></span>        | <span data-ttu-id="339bc-140">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="339bc-140">❌ 3.1</span></span>        | <span data-ttu-id="339bc-141">❌ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="339bc-141">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="339bc-142">❌ [17.04](#1704-)</span><span class="sxs-lookup"><span data-stu-id="339bc-142">❌ [17.04](#1704-)</span></span>       | <span data-ttu-id="339bc-143">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="339bc-143">✔️ 2.1</span></span>        | <span data-ttu-id="339bc-144">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="339bc-144">❌ 3.1</span></span>        | <span data-ttu-id="339bc-145">❌ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="339bc-145">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="339bc-146">❌ [16.10](#1610-)</span><span class="sxs-lookup"><span data-stu-id="339bc-146">❌ [16.10](#1610-)</span></span>       | <span data-ttu-id="339bc-147">❌ 2.1</span><span class="sxs-lookup"><span data-stu-id="339bc-147">❌ 2.1</span></span>        | <span data-ttu-id="339bc-148">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="339bc-148">❌ 3.1</span></span>        | <span data-ttu-id="339bc-149">❌ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="339bc-149">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="339bc-150">✔️ [16.04 (LTS)](#1604-)</span><span class="sxs-lookup"><span data-stu-id="339bc-150">✔️ [16.04 (LTS)](#1604-)</span></span> | <span data-ttu-id="339bc-151">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="339bc-151">✔️ 2.1</span></span>        | <span data-ttu-id="339bc-152">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="339bc-152">✔️ 3.1</span></span>        | <span data-ttu-id="339bc-153">✔️ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="339bc-153">✔️ 5.0 Preview</span></span> |

<span data-ttu-id="339bc-154">Die folgenden Versionen von .NET Core werden nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="339bc-154">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="339bc-155">Die Downloads dafür bleiben weiterhin veröffentlicht:</span><span class="sxs-lookup"><span data-stu-id="339bc-155">The downloads for these still remain published:</span></span>

- <span data-ttu-id="339bc-156">3.0</span><span class="sxs-lookup"><span data-stu-id="339bc-156">3.0</span></span>
- <span data-ttu-id="339bc-157">2.2</span><span class="sxs-lookup"><span data-stu-id="339bc-157">2.2</span></span>
- <span data-ttu-id="339bc-158">2.0</span><span class="sxs-lookup"><span data-stu-id="339bc-158">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="339bc-159">Installieren anderer Versionen</span><span class="sxs-lookup"><span data-stu-id="339bc-159">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="2004-"></a><span data-ttu-id="339bc-160">20.04 ✔️</span><span class="sxs-lookup"><span data-stu-id="339bc-160">20.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1910-"></a><span data-ttu-id="339bc-161">19.10 ❌</span><span class="sxs-lookup"><span data-stu-id="339bc-161">19.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/19.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1904-"></a><span data-ttu-id="339bc-162">19.04 ❌</span><span class="sxs-lookup"><span data-stu-id="339bc-162">19.04 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/19.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1810-"></a><span data-ttu-id="339bc-163">18.10 ❌</span><span class="sxs-lookup"><span data-stu-id="339bc-163">18.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/18.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1804-"></a><span data-ttu-id="339bc-164">18.04 ✔️</span><span class="sxs-lookup"><span data-stu-id="339bc-164">18.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1710-"></a><span data-ttu-id="339bc-165">17.10 ❌</span><span class="sxs-lookup"><span data-stu-id="339bc-165">17.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/17.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1704-"></a><span data-ttu-id="339bc-166">17.04 ❌</span><span class="sxs-lookup"><span data-stu-id="339bc-166">17.04 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/17.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1610-"></a><span data-ttu-id="339bc-167">16.10 ❌</span><span class="sxs-lookup"><span data-stu-id="339bc-167">16.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/16.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1604-"></a><span data-ttu-id="339bc-168">16.04 ✔️</span><span class="sxs-lookup"><span data-stu-id="339bc-168">16.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/16.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="apt-update-sdk-or-runtime"></a><span data-ttu-id="339bc-169">APT Update SDK oder Runtime</span><span class="sxs-lookup"><span data-stu-id="339bc-169">APT update SDK or runtime</span></span>

<span data-ttu-id="339bc-170">Wenn eine neue Patchversion für .NET Core verfügbar ist, können Sie diese einfach über APT mit den folgenden Befehlen aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="339bc-170">When a new patch release is available for .NET Core, you can simply upgrade it through APT with the following commands:</span></span>

```bash
sudo apt-get update
sudo apt-get upgrade
```

## <a name="apt-troubleshooting"></a><span data-ttu-id="339bc-171">Problembehandlung für APT</span><span class="sxs-lookup"><span data-stu-id="339bc-171">APT troubleshooting</span></span>

<span data-ttu-id="339bc-172">Dieser Abschnitt enthält Informationen zu häufigen Fehlern, die bei der Installation von .NET Core mit APT auftreten können.</span><span class="sxs-lookup"><span data-stu-id="339bc-172">This section provides information on common errors you may get while using APT to install .NET Core.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="339bc-173">Paket konnte nicht gefunden werden</span><span class="sxs-lookup"><span data-stu-id="339bc-173">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="unable-to-locate--some-packages-could-not-be-installed"></a><span data-ttu-id="339bc-174">"Das Paket kann nicht gefunden werden"/"Die Pakete konnten nicht installiert werden"</span><span class="sxs-lookup"><span data-stu-id="339bc-174">Unable to locate \\ Some packages could not be installed</span></span>

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

### <a name="failed-to-fetch"></a><span data-ttu-id="339bc-175">Fehler beim Abrufen</span><span class="sxs-lookup"><span data-stu-id="339bc-175">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]

## <a name="snap"></a><span data-ttu-id="339bc-176">Snap</span><span class="sxs-lookup"><span data-stu-id="339bc-176">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="339bc-177">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="339bc-177">Dependencies</span></span>

<span data-ttu-id="339bc-178">Wenn die Installation mit einem Paket-Manager erfolgt, werden diese Bibliotheken für Sie installiert.</span><span class="sxs-lookup"><span data-stu-id="339bc-178">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="339bc-179">Wenn Sie jedoch .NET Core manuell installieren oder eine eigenständige Anwendung veröffentlichen, müssen Sie sicherstellen, dass diese Bibliotheken installiert sind:</span><span class="sxs-lookup"><span data-stu-id="339bc-179">But, if you manually install .NET Core or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="339bc-180">libc6</span><span class="sxs-lookup"><span data-stu-id="339bc-180">libc6</span></span>
- <span data-ttu-id="339bc-181">libgcc1</span><span class="sxs-lookup"><span data-stu-id="339bc-181">libgcc1</span></span>
- <span data-ttu-id="339bc-182">libgssapi-krb5-2</span><span class="sxs-lookup"><span data-stu-id="339bc-182">libgssapi-krb5-2</span></span>
- <span data-ttu-id="339bc-183">libicu52 (für 14.X)</span><span class="sxs-lookup"><span data-stu-id="339bc-183">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="339bc-184">libicu55 (für 16.X)</span><span class="sxs-lookup"><span data-stu-id="339bc-184">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="339bc-185">libicu60 (für 18.X)</span><span class="sxs-lookup"><span data-stu-id="339bc-185">libicu60 (for 18.x)</span></span>
- <span data-ttu-id="339bc-186">libicu66 (für 20.x)</span><span class="sxs-lookup"><span data-stu-id="339bc-186">libicu66 (for 20.x)</span></span>
- <span data-ttu-id="339bc-187">libssl1.0.0 (für 14.x, 16.x)</span><span class="sxs-lookup"><span data-stu-id="339bc-187">libssl1.0.0 (for 14.x, 16.x)</span></span>
- <span data-ttu-id="339bc-188">libssl1.1 (für 18.x, 20.x)</span><span class="sxs-lookup"><span data-stu-id="339bc-188">libssl1.1 (for 18.x, 20.x)</span></span>
- <span data-ttu-id="339bc-189">libstdc++6</span><span class="sxs-lookup"><span data-stu-id="339bc-189">libstdc++6</span></span>
- <span data-ttu-id="339bc-190">zlib1g</span><span class="sxs-lookup"><span data-stu-id="339bc-190">zlib1g</span></span>

<span data-ttu-id="339bc-191">Für .NET Core-Apps, die die Assembly *System.Drawing.Common* verwenden, benötigen Sie außerdem die folgende Abhängigkeit:</span><span class="sxs-lookup"><span data-stu-id="339bc-191">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="339bc-192">libgdiplus (Version 6.0.1 oder höher)</span><span class="sxs-lookup"><span data-stu-id="339bc-192">libgdiplus (version 6.0.1 or later)</span></span>

  > [!WARNING]
  > <span data-ttu-id="339bc-193">Sie können eine neuere Version von *libgdiplus* installieren, indem Sie Ihrem System das Mono-Repository hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="339bc-193">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="339bc-194">Weitere Informationen finden Sie unter <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="339bc-194">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="scripted-install"></a><span data-ttu-id="339bc-195">Per Skript gesteuerte Installation</span><span class="sxs-lookup"><span data-stu-id="339bc-195">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="339bc-196">Manuelle Installation</span><span class="sxs-lookup"><span data-stu-id="339bc-196">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="339bc-197">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="339bc-197">Next steps</span></span>

- [<span data-ttu-id="339bc-198">Tutorial: Erstellen einer Konsolenanwendung mit dem .NET Core SDK in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="339bc-198">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
