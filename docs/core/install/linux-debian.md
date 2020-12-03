---
title: Installieren von .NET unter Debian (.NET)
description: Veranschaulicht verschiedene Möglichkeiten, das .NET SDK und die NET-Runtime unter Debian zu installieren
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 683d0a9c47edf3cf9c47426d659e778eeb6f84df
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96031890"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-debian"></a><span data-ttu-id="5dc45-103">Installieren des .NET SDK oder der .NET-Runtime unter Debian</span><span class="sxs-lookup"><span data-stu-id="5dc45-103">Install the .NET SDK or the .NET Runtime on Debian</span></span>

<span data-ttu-id="5dc45-104">In diesem Artikel wird beschrieben, wie Sie .NET unter Debian installieren.</span><span class="sxs-lookup"><span data-stu-id="5dc45-104">This article describes how to install .NET on Debian.</span></span> <span data-ttu-id="5dc45-105">Wenn für eine Debian-Version kein Support mehr angeboten wird, wird .NET mit dieser Version nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5dc45-105">When a Debian version falls out of support, .NET is no longer supported with that version.</span></span> <span data-ttu-id="5dc45-106">Diese Anweisungen können Ihnen jedoch helfen, .NET in diesen Versionen auszuführen, auch wenn kein Unterstützung dafür geboten wird.</span><span class="sxs-lookup"><span data-stu-id="5dc45-106">However, these instructions may help you to get .NET running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="5dc45-107">Unterstützte Distributionen</span><span class="sxs-lookup"><span data-stu-id="5dc45-107">Supported distributions</span></span>

<span data-ttu-id="5dc45-108">Die folgende Tabelle enthält die derzeit unterstützten .NET-Releases und Versionen von Debian, unter denen sie unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="5dc45-108">The following table is a list of currently supported .NET releases and the versions of Debian they're supported on.</span></span> <span data-ttu-id="5dc45-109">Diese Versionen werden weiterhin unterstützt, bis entweder die Version von [.NET das Ende des Supports](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) oder die Version von [Debian das Ende ihrer Lebensdauer erreicht](https://wiki.debian.org/DebianReleases).</span><span class="sxs-lookup"><span data-stu-id="5dc45-109">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Debian reaches end-of-life](https://wiki.debian.org/DebianReleases).</span></span>

- <span data-ttu-id="5dc45-110">✔️ gibt an, dass die Version von Debian oder .NET weiterhin unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="5dc45-110">A ✔️ indicates that the version of Debian or .NET is still supported.</span></span>
- <span data-ttu-id="5dc45-111">❌ gibt an, dass die Version von Debian oder .NET in diesem Debian-Release nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="5dc45-111">A ❌ indicates that the version of Debian or .NET isn't supported on that Debian release.</span></span>
- <span data-ttu-id="5dc45-112">Wenn sowohl eine Version von Debian als auch eine Version von .NET über ✔️ verfügen, wird diese Kombination aus Betriebssystem und .NET unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5dc45-112">When both a version of Debian and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="5dc45-113">Debian</span><span class="sxs-lookup"><span data-stu-id="5dc45-113">Debian</span></span>                   | <span data-ttu-id="5dc45-114">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="5dc45-114">.NET Core 2.1</span></span> | <span data-ttu-id="5dc45-115">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="5dc45-115">.NET Core 3.1</span></span> | <span data-ttu-id="5dc45-116">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="5dc45-116">.NET 5.0</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="5dc45-117">✔️ [10](#debian-10-)</span><span class="sxs-lookup"><span data-stu-id="5dc45-117">✔️ [10](#debian-10-)</span></span>     | <span data-ttu-id="5dc45-118">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="5dc45-118">✔️ 2.1</span></span>        | <span data-ttu-id="5dc45-119">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="5dc45-119">✔️ 3.1</span></span>        | <span data-ttu-id="5dc45-120">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="5dc45-120">✔️ 5.0</span></span> |
| <span data-ttu-id="5dc45-121">✔️ [9](#debian-9-)</span><span class="sxs-lookup"><span data-stu-id="5dc45-121">✔️ [9](#debian-9-)</span></span>       | <span data-ttu-id="5dc45-122">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="5dc45-122">✔️ 2.1</span></span>        | <span data-ttu-id="5dc45-123">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="5dc45-123">✔️ 3.1</span></span>        | <span data-ttu-id="5dc45-124">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="5dc45-124">✔️ 5.0</span></span> |
| <span data-ttu-id="5dc45-125">❌ [8](#debian-8-)</span><span class="sxs-lookup"><span data-stu-id="5dc45-125">❌ [8](#debian-8-)</span></span>       | <span data-ttu-id="5dc45-126">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="5dc45-126">✔️ 2.1</span></span>        | <span data-ttu-id="5dc45-127">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="5dc45-127">❌ 3.1</span></span>        | <span data-ttu-id="5dc45-128">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="5dc45-128">❌ 5.0</span></span> |

<span data-ttu-id="5dc45-129">Die folgenden Versionen von .NET werden nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5dc45-129">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="5dc45-130">Die Downloads dafür bleiben weiterhin veröffentlicht:</span><span class="sxs-lookup"><span data-stu-id="5dc45-130">The downloads for these still remain published:</span></span>

- <span data-ttu-id="5dc45-131">3.0</span><span class="sxs-lookup"><span data-stu-id="5dc45-131">3.0</span></span>
- <span data-ttu-id="5dc45-132">2.2</span><span class="sxs-lookup"><span data-stu-id="5dc45-132">2.2</span></span>
- <span data-ttu-id="5dc45-133">2.0</span><span class="sxs-lookup"><span data-stu-id="5dc45-133">2.0</span></span>

## <a name="remove-preview-versions"></a><span data-ttu-id="5dc45-134">Entfernen von Vorschauversionen</span><span class="sxs-lookup"><span data-stu-id="5dc45-134">Remove preview versions</span></span>

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="5dc45-135">Installieren anderer Versionen</span><span class="sxs-lookup"><span data-stu-id="5dc45-135">How to install other versions</span></span>

[!INCLUDE [hack-pkgname](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="debian-10-"></a><span data-ttu-id="5dc45-136">Debian 10 ✔️</span><span class="sxs-lookup"><span data-stu-id="5dc45-136">Debian 10 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/debian/10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="debian-9-"></a><span data-ttu-id="5dc45-137">Debian 9 ✔️</span><span class="sxs-lookup"><span data-stu-id="5dc45-137">Debian 9 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/9/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="debian-8-"></a><span data-ttu-id="5dc45-138">Debian 8 ❌</span><span class="sxs-lookup"><span data-stu-id="5dc45-138">Debian 8 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-debian.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/8/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="apt-update-sdk-or-runtime"></a><span data-ttu-id="5dc45-139">APT Update SDK oder Runtime</span><span class="sxs-lookup"><span data-stu-id="5dc45-139">APT update SDK or runtime</span></span>

<span data-ttu-id="5dc45-140">Wenn ein neues Patchrelease für .NET verfügbar ist, können Sie dieses einfach über APT mit den folgenden Befehlen aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="5dc45-140">When a new patch release is available for .NET, you can simply upgrade it through APT with the following commands:</span></span>

```bash
sudo apt-get update
sudo apt-get upgrade
```

## <a name="apt-troubleshooting"></a><span data-ttu-id="5dc45-141">Problembehandlung für APT</span><span class="sxs-lookup"><span data-stu-id="5dc45-141">APT troubleshooting</span></span>

<span data-ttu-id="5dc45-142">Dieser Abschnitt enthält Informationen zu häufigen Fehlern, die bei der Installation von .NET mit APT auftreten können.</span><span class="sxs-lookup"><span data-stu-id="5dc45-142">This section provides information on common errors you may get while using APT to install .NET.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="5dc45-143">Paket konnte nicht gefunden werden</span><span class="sxs-lookup"><span data-stu-id="5dc45-143">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="unable-to-locate--some-packages-could-not-be-installed"></a><span data-ttu-id="5dc45-144">"Das Paket kann nicht gefunden werden"/"Die Pakete konnten nicht installiert werden"</span><span class="sxs-lookup"><span data-stu-id="5dc45-144">Unable to locate \\ Some packages could not be installed</span></span>

[!INCLUDE [package-manager-failed-to-find-deb](includes/package-manager-failed-to-find-deb.md)]

```bash
sudo apt-get install -y gpg
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor -o microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/{os-version}/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y {dotnet-package}
```

### <a name="failed-to-fetch"></a><span data-ttu-id="5dc45-145">Fehler beim Abrufen</span><span class="sxs-lookup"><span data-stu-id="5dc45-145">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]

## <a name="snap"></a><span data-ttu-id="5dc45-146">Snap</span><span class="sxs-lookup"><span data-stu-id="5dc45-146">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="5dc45-147">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="5dc45-147">Dependencies</span></span>

<span data-ttu-id="5dc45-148">Wenn die Installation mit einem Paket-Manager erfolgt, werden diese Bibliotheken für Sie installiert.</span><span class="sxs-lookup"><span data-stu-id="5dc45-148">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="5dc45-149">Wenn Sie jedoch .NET Core manuell installieren oder eine eigenständige Anwendung veröffentlichen, müssen Sie sicherstellen, dass diese Bibliotheken installiert sind:</span><span class="sxs-lookup"><span data-stu-id="5dc45-149">But, if you manually install .NET Core or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="5dc45-150">libc6</span><span class="sxs-lookup"><span data-stu-id="5dc45-150">libc6</span></span>
- <span data-ttu-id="5dc45-151">libgcc1</span><span class="sxs-lookup"><span data-stu-id="5dc45-151">libgcc1</span></span>
- <span data-ttu-id="5dc45-152">libgssapi-krb5-2</span><span class="sxs-lookup"><span data-stu-id="5dc45-152">libgssapi-krb5-2</span></span>
- <span data-ttu-id="5dc45-153">libicu52 (für 8.x)</span><span class="sxs-lookup"><span data-stu-id="5dc45-153">libicu52 (for 8.x)</span></span>
- <span data-ttu-id="5dc45-154">libicu57 (für 9.x)</span><span class="sxs-lookup"><span data-stu-id="5dc45-154">libicu57 (for 9.x)</span></span>
- <span data-ttu-id="5dc45-155">libicu63 (für 10.x)</span><span class="sxs-lookup"><span data-stu-id="5dc45-155">libicu63 (for 10.x)</span></span>
- <span data-ttu-id="5dc45-156">libicu67 (für 11.x)</span><span class="sxs-lookup"><span data-stu-id="5dc45-156">libicu67 (for 11.x)</span></span>
- <span data-ttu-id="5dc45-157">libssl1.0.0 (für 8.x)</span><span class="sxs-lookup"><span data-stu-id="5dc45-157">libssl1.0.0 (for 8.x)</span></span>
- <span data-ttu-id="5dc45-158">libssl1.1 (für 9.x–11.x)</span><span class="sxs-lookup"><span data-stu-id="5dc45-158">libssl1.1 (for 9.x-11.x)</span></span>
- <span data-ttu-id="5dc45-159">libstdc++6</span><span class="sxs-lookup"><span data-stu-id="5dc45-159">libstdc++6</span></span>
- <span data-ttu-id="5dc45-160">zlib1g</span><span class="sxs-lookup"><span data-stu-id="5dc45-160">zlib1g</span></span>

<span data-ttu-id="5dc45-161">Für .NET Core-Apps, die die Assembly *System.Drawing.Common* verwenden, benötigen Sie außerdem die folgende Abhängigkeit:</span><span class="sxs-lookup"><span data-stu-id="5dc45-161">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="5dc45-162">libgdiplus (Version 6.0.1 oder höher)</span><span class="sxs-lookup"><span data-stu-id="5dc45-162">libgdiplus (version 6.0.1 or later)</span></span>

  > [!WARNING]
  > <span data-ttu-id="5dc45-163">Sie können eine neuere Version von *libgdiplus* installieren, indem Sie Ihrem System das Mono-Repository hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5dc45-163">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="5dc45-164">Weitere Informationen finden Sie unter <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="5dc45-164">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="scripted-install"></a><span data-ttu-id="5dc45-165">Per Skript gesteuerte Installation</span><span class="sxs-lookup"><span data-stu-id="5dc45-165">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="5dc45-166">Manuelle Installation</span><span class="sxs-lookup"><span data-stu-id="5dc45-166">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="5dc45-167">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="5dc45-167">Next steps</span></span>

- [<span data-ttu-id="5dc45-168">Tutorial: Erstellen einer Konsolenanwendung mit dem .NET SDK in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="5dc45-168">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
