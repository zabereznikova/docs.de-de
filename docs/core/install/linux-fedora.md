---
title: 'Installieren von .NET unter Fedora: .NET'
description: In diesem Artikel werden verschiedene Möglichkeiten veranschaulicht, das .NET SDK und die .NET-Runtime für Fedora zu installieren.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 9e96773e30fb8ee395e37dca7a4794cd42359bb2
ms.sourcegitcommit: c38bf879a2611ff46aacdd529b9f2725f93e18a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2020
ms.locfileid: "94594619"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-fedora"></a><span data-ttu-id="7a685-103">Installieren des .NET SDK oder der .NET-Runtime unter Fedora</span><span class="sxs-lookup"><span data-stu-id="7a685-103">Install the .NET SDK or the .NET Runtime on Fedora</span></span>

<span data-ttu-id="7a685-104">.NET wird unter Fedora unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7a685-104">.NET is supported on Fedora.</span></span> <span data-ttu-id="7a685-105">In diesem Artikel wird beschrieben, wie Sie .NET unter Fedora installieren.</span><span class="sxs-lookup"><span data-stu-id="7a685-105">This article describes how to install .NET on Fedora.</span></span> <span data-ttu-id="7a685-106">Wenn für eine Fedora-Version kein Support mehr geboten wird, wird .NET mit dieser Version nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7a685-106">When a Fedora version falls out of support, .NET is no longer supported with that version.</span></span> <span data-ttu-id="7a685-107">Diese Anweisungen können Ihnen jedoch helfen, .NET in diesen Versionen auszuführen, auch wenn sie nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="7a685-107">However, these instructions may help you to get .NET running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="7a685-108">Unterstützte Distributionen</span><span class="sxs-lookup"><span data-stu-id="7a685-108">Supported distributions</span></span>

<span data-ttu-id="7a685-109">Die folgende Tabelle enthält die derzeit unterstützten .NET-Releases und Versionen von Fedora, unter denen sie unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="7a685-109">The following table is a list of currently supported .NET releases and the versions of Fedora they're supported on.</span></span> <span data-ttu-id="7a685-110">Diese Versionen werden weiterhin unterstützt, bis entweder die Version von [.NET das Ende des Supports](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) oder die Version von [Fedora das Ende ihrer Lebensdauer erreicht](https://fedoraproject.org/wiki/End_of_life).</span><span class="sxs-lookup"><span data-stu-id="7a685-110">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Fedora reaches end-of-life](https://fedoraproject.org/wiki/End_of_life).</span></span>

- <span data-ttu-id="7a685-111">✔️ gibt an, dass die Version von Fedora oder .NET weiterhin unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="7a685-111">A ✔️ indicates that the version of Fedora or .NET is still supported.</span></span>
- <span data-ttu-id="7a685-112">❌ gibt an, dass die Version von Fedora oder .NET in diesem Fedora-Release nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="7a685-112">A ❌ indicates that the version of Fedora or .NET isn't supported on that Fedora release.</span></span>
- <span data-ttu-id="7a685-113">Wenn sowohl eine Version von Fedora als auch eine Version von .NET mit ✔️ markiert sind, wird diese Kombination aus Betriebssystem und .NET unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7a685-113">When both a version of Fedora and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="7a685-114">Fedora</span><span class="sxs-lookup"><span data-stu-id="7a685-114">Fedora</span></span>               | <span data-ttu-id="7a685-115">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="7a685-115">.NET Core 2.1</span></span> | <span data-ttu-id="7a685-116">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="7a685-116">.NET Core 3.1</span></span> | <span data-ttu-id="7a685-117">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="7a685-117">.NET 5.0</span></span> |
|----------------------|---------------|---------------|----------|
| <span data-ttu-id="7a685-118">✔️ [33](#fedora-33-)</span><span class="sxs-lookup"><span data-stu-id="7a685-118">✔️ [33](#fedora-33-)</span></span> | <span data-ttu-id="7a685-119">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="7a685-119">✔️ 2.1</span></span>        | <span data-ttu-id="7a685-120">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="7a685-120">✔️ 3.1</span></span>        | <span data-ttu-id="7a685-121">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="7a685-121">✔️ 5.0</span></span> |
| <span data-ttu-id="7a685-122">✔️ [32](#fedora-32-)</span><span class="sxs-lookup"><span data-stu-id="7a685-122">✔️ [32](#fedora-32-)</span></span> | <span data-ttu-id="7a685-123">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="7a685-123">✔️ 2.1</span></span>        | <span data-ttu-id="7a685-124">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="7a685-124">✔️ 3.1</span></span>        | <span data-ttu-id="7a685-125">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="7a685-125">✔️ 5.0</span></span> |
| <span data-ttu-id="7a685-126">❌ [31](#fedora-31-)</span><span class="sxs-lookup"><span data-stu-id="7a685-126">❌ [31](#fedora-31-)</span></span> | <span data-ttu-id="7a685-127">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="7a685-127">✔️ 2.1</span></span>        | <span data-ttu-id="7a685-128">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="7a685-128">✔️ 3.1</span></span>        | <span data-ttu-id="7a685-129">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="7a685-129">❌ 5.0</span></span> |
| <span data-ttu-id="7a685-130">❌ [30](#fedora-30-)</span><span class="sxs-lookup"><span data-stu-id="7a685-130">❌ [30](#fedora-30-)</span></span> | <span data-ttu-id="7a685-131">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="7a685-131">✔️ 2.1</span></span>        | <span data-ttu-id="7a685-132">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="7a685-132">✔️ 3.1</span></span>        | <span data-ttu-id="7a685-133">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="7a685-133">❌ 5.0</span></span> |
| <span data-ttu-id="7a685-134">❌ [29](#fedora-29-)</span><span class="sxs-lookup"><span data-stu-id="7a685-134">❌ [29](#fedora-29-)</span></span> | <span data-ttu-id="7a685-135">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="7a685-135">✔️ 2.1</span></span>        | <span data-ttu-id="7a685-136">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="7a685-136">✔️ 3.1</span></span>        | <span data-ttu-id="7a685-137">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="7a685-137">❌ 5.0</span></span> |
| <span data-ttu-id="7a685-138">❌ [28](#fedora-28-)</span><span class="sxs-lookup"><span data-stu-id="7a685-138">❌ [28](#fedora-28-)</span></span> | <span data-ttu-id="7a685-139">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="7a685-139">✔️ 2.1</span></span>        | <span data-ttu-id="7a685-140">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="7a685-140">❌ 3.1</span></span>        | <span data-ttu-id="7a685-141">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="7a685-141">❌ 5.0</span></span> |
| <span data-ttu-id="7a685-142">❌ [27](#fedora-27-)</span><span class="sxs-lookup"><span data-stu-id="7a685-142">❌ [27](#fedora-27-)</span></span> | <span data-ttu-id="7a685-143">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="7a685-143">✔️ 2.1</span></span>        | <span data-ttu-id="7a685-144">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="7a685-144">❌ 3.1</span></span>        | <span data-ttu-id="7a685-145">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="7a685-145">❌ 5.0</span></span> |

<span data-ttu-id="7a685-146">Die folgenden Versionen von .NET werden nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7a685-146">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="7a685-147">Die Downloads dafür bleiben weiterhin veröffentlicht:</span><span class="sxs-lookup"><span data-stu-id="7a685-147">The downloads for these still remain published:</span></span>

- <span data-ttu-id="7a685-148">3.0</span><span class="sxs-lookup"><span data-stu-id="7a685-148">3.0</span></span>
- <span data-ttu-id="7a685-149">2.2</span><span class="sxs-lookup"><span data-stu-id="7a685-149">2.2</span></span>
- <span data-ttu-id="7a685-150">2.0</span><span class="sxs-lookup"><span data-stu-id="7a685-150">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="7a685-151">Installieren anderer Versionen</span><span class="sxs-lookup"><span data-stu-id="7a685-151">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="fedora-33-"></a><span data-ttu-id="7a685-152">Fedora 33 ✔️</span><span class="sxs-lookup"><span data-stu-id="7a685-152">Fedora 33 ✔️</span></span>

> [!TIP]
> <span data-ttu-id="7a685-153">.NET 3.1 ist in den Standardpaketrepositorys für Fedora 33 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7a685-153">.NET Core 3.1 is available in the default package repositories for Fedora 33.</span></span> <span data-ttu-id="7a685-154">Verwenden Sie zur Installation von .NET Core 3.1 den `dnf install`-Befehl mit entsprechendem Paket, z. B. `aspnetcore-runtime-3.1` oder `dotnet-sdk-3.1`.</span><span class="sxs-lookup"><span data-stu-id="7a685-154">To install .NET Core 3.1, use the `dnf install` command with the appropriate package, such as `aspnetcore-runtime-3.1` or `dotnet-sdk-3.1`.</span></span> <span data-ttu-id="7a685-155">NET Core 5.0 ist in den Standardpaketrepositorys noch nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7a685-155">.NET 5.0 isn't yet available in the default package repositories.</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/33/prod.repo
```

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="fedora-32-"></a><span data-ttu-id="7a685-156">Fedora 32 ✔️</span><span class="sxs-lookup"><span data-stu-id="7a685-156">Fedora 32 ✔️</span></span>

> [!TIP]
> <span data-ttu-id="7a685-157">NET Core 3.1 in den Standardpaketrepositorys für Fedora 32 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7a685-157">.NET Core 3.1 is available in the default package repositories for Fedora 32.</span></span> <span data-ttu-id="7a685-158">Verwenden Sie zur Installation von .NET Core 3.1 den `dnf install`-Befehl mit entsprechendem Paket, z. B. `aspnetcore-runtime-3.1` oder `dotnet-sdk-3.1`.</span><span class="sxs-lookup"><span data-stu-id="7a685-158">To install .NET Core 3.1, use the `dnf install` command with the appropriate package, such as `aspnetcore-runtime-3.1` or `dotnet-sdk-3.1`.</span></span> <span data-ttu-id="7a685-159">NET Core 5.0 ist in den Standardpaketrepositorys noch nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7a685-159">.NET 5.0 isn't yet available in the default package repositories.</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/32/prod.repo
```

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="fedora-31-"></a><span data-ttu-id="7a685-160">Fedora 31 ❌</span><span class="sxs-lookup"><span data-stu-id="7a685-160">Fedora 31 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/31/prod.repo
```

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="fedora-30-"></a><span data-ttu-id="7a685-161">Fedora 30 ❌</span><span class="sxs-lookup"><span data-stu-id="7a685-161">Fedora 30 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/30/prod.repo
```

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="fedora-29-"></a><span data-ttu-id="7a685-162">Fedora 29 ❌</span><span class="sxs-lookup"><span data-stu-id="7a685-162">Fedora 29 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/29/prod.repo
```

[!INCLUDE [linux-dnf-install-30](includes/linux-install-30-dnf.md)]

## <a name="fedora-28-"></a><span data-ttu-id="7a685-163">Fedora 28 ❌</span><span class="sxs-lookup"><span data-stu-id="7a685-163">Fedora 28 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/28/prod.repo
```

[!INCLUDE [linux-dnf-install-20](includes/linux-install-20-dnf.md)]

## <a name="fedora-27-"></a><span data-ttu-id="7a685-164">Fedora 27 ❌</span><span class="sxs-lookup"><span data-stu-id="7a685-164">Fedora 27 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/27/prod.repo
```

[!INCLUDE [linux-dnf-install-20](includes/linux-install-20-dnf.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="7a685-165">Problembehandlung des Paket-Managers</span><span class="sxs-lookup"><span data-stu-id="7a685-165">Troubleshoot the package manager</span></span>

<span data-ttu-id="7a685-166">Dieser Abschnitt enthält Informationen zu häufigen Fehlern, die bei der Verwendung des Paket-Managers zur Installation von .NET Core auftreten können.</span><span class="sxs-lookup"><span data-stu-id="7a685-166">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="7a685-167">Paket konnte nicht gefunden werden</span><span class="sxs-lookup"><span data-stu-id="7a685-167">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="failed-to-fetch"></a><span data-ttu-id="7a685-168">Fehler beim Abrufen</span><span class="sxs-lookup"><span data-stu-id="7a685-168">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="snap"></a><span data-ttu-id="7a685-169">Snap</span><span class="sxs-lookup"><span data-stu-id="7a685-169">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="7a685-170">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="7a685-170">Dependencies</span></span>

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="7a685-171">Per Skript gesteuerte Installation</span><span class="sxs-lookup"><span data-stu-id="7a685-171">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="7a685-172">Manuelle Installation</span><span class="sxs-lookup"><span data-stu-id="7a685-172">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="7a685-173">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="7a685-173">Next steps</span></span>

- [<span data-ttu-id="7a685-174">Tutorial: Erstellen einer Konsolenanwendung mit dem .NET SDK in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="7a685-174">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
