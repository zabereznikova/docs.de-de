---
title: Installieren von .NET Core unter Fedora (.NET Core)
description: Veranschaulicht verschiedene Möglichkeiten, das .NET Core SDK und die NET Core-Runtime unter Fedora zu installieren.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 89a55ad2e9fd66d277d0c3eb6a07bd402574bd0a
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538513"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-fedora"></a><span data-ttu-id="f685a-103">Installieren des .NET Core SDK oder der .NET Core-Runtime unter Fedora</span><span class="sxs-lookup"><span data-stu-id="f685a-103">Install .NET Core SDK or .NET Core Runtime on Fedora</span></span>

<span data-ttu-id="f685a-104">.NET Core wird unter Fedora unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f685a-104">.NET Core is supported on Fedora.</span></span> <span data-ttu-id="f685a-105">In diesem Artikel wird beschrieben, wie Sie .NET Core unter Fedora installieren.</span><span class="sxs-lookup"><span data-stu-id="f685a-105">This article describes how to install .NET Core on Fedora.</span></span> <span data-ttu-id="f685a-106">Wenn für eine Fedora-Version kein Support mehr geboten wird, wird .NET Core mit dieser Version nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f685a-106">When a Fedora version falls out of support, .NET Core is no longer supported with that version.</span></span> <span data-ttu-id="f685a-107">Diese Anweisungen können Ihnen jedoch helfen, .NET Core in diesen Versionen auszuführen, auch wenn kein Support dafür geboten wird.</span><span class="sxs-lookup"><span data-stu-id="f685a-107">However, these instructions may help you to get .NET Core running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="f685a-108">Unterstützte Distributionen</span><span class="sxs-lookup"><span data-stu-id="f685a-108">Supported distributions</span></span>

<span data-ttu-id="f685a-109">Die folgende Tabelle ist eine Liste der derzeit unterstützten .NET Core-Versionen und der Versionen von Fedora, unter denen sie unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="f685a-109">The following table is a list of currently supported .NET Core releases and the versions of Fedora they're supported on.</span></span> <span data-ttu-id="f685a-110">Diese Versionen werden weiterhin unterstützt, bis entweder die Version von [.NET Core das Ende des Supports](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) oder die Version von [Fedora das Ende ihrer Lebensdauer erreicht](https://fedoraproject.org/wiki/End_of_life).</span><span class="sxs-lookup"><span data-stu-id="f685a-110">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Fedora reaches end-of-life](https://fedoraproject.org/wiki/End_of_life).</span></span>

- <span data-ttu-id="f685a-111">✔️ gibt an, dass die Version von Fedora oder .NET Core weiterhin unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="f685a-111">A ✔️ indicates that the version of Fedora or .NET Core is still supported.</span></span>
- <span data-ttu-id="f685a-112">❌ gibt an, dass die Version von Fedora oder .NET Core in dieser Fedora-Version nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="f685a-112">A ❌ indicates that the version of Fedora or .NET Core isn't supported on that Fedora release.</span></span>
- <span data-ttu-id="f685a-113">Wenn sowohl eine Version von Fedora als auch eine Version von .NET Core über ✔️ verfügen, wird diese Kombination aus Betriebssystem und .NET unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f685a-113">When both a version of Fedora and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="f685a-114">Fedora</span><span class="sxs-lookup"><span data-stu-id="f685a-114">Fedora</span></span>                   | <span data-ttu-id="f685a-115">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="f685a-115">.NET Core 2.1</span></span> | <span data-ttu-id="f685a-116">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="f685a-116">.NET Core 3.1</span></span> | <span data-ttu-id="f685a-117">.NET 5 Preview (nur manuelle Installation)</span><span class="sxs-lookup"><span data-stu-id="f685a-117">.NET 5 Preview (manual install only)</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="f685a-118">✔️ [32](linux-fedora.md#fedora-32-)</span><span class="sxs-lookup"><span data-stu-id="f685a-118">✔️ [32](linux-fedora.md#fedora-32-)</span></span> | <span data-ttu-id="f685a-119">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="f685a-119">✔️ 2.1</span></span>        | <span data-ttu-id="f685a-120">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="f685a-120">✔️ 3.1</span></span>        | <span data-ttu-id="f685a-121">✔️ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="f685a-121">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="f685a-122">✔️ [31](linux-fedora.md#fedora-31-)</span><span class="sxs-lookup"><span data-stu-id="f685a-122">✔️ [31](linux-fedora.md#fedora-31-)</span></span> | <span data-ttu-id="f685a-123">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="f685a-123">✔️ 2.1</span></span>        | <span data-ttu-id="f685a-124">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="f685a-124">✔️ 3.1</span></span>        | <span data-ttu-id="f685a-125">✔️ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="f685a-125">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="f685a-126">❌ [30](linux-fedora.md#fedora-30-)</span><span class="sxs-lookup"><span data-stu-id="f685a-126">❌ [30](linux-fedora.md#fedora-30-)</span></span> | <span data-ttu-id="f685a-127">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="f685a-127">✔️ 2.1</span></span>        | <span data-ttu-id="f685a-128">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="f685a-128">✔️ 3.1</span></span>        | <span data-ttu-id="f685a-129">❌ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="f685a-129">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="f685a-130">❌ [29](linux-fedora.md#fedora-29-)</span><span class="sxs-lookup"><span data-stu-id="f685a-130">❌ [29](linux-fedora.md#fedora-29-)</span></span> | <span data-ttu-id="f685a-131">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="f685a-131">✔️ 2.1</span></span>        | <span data-ttu-id="f685a-132">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="f685a-132">✔️ 3.1</span></span>        | <span data-ttu-id="f685a-133">❌ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="f685a-133">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="f685a-134">❌ [28](linux-fedora.md#fedora-28-)</span><span class="sxs-lookup"><span data-stu-id="f685a-134">❌ [28](linux-fedora.md#fedora-28-)</span></span> | <span data-ttu-id="f685a-135">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="f685a-135">✔️ 2.1</span></span>        | <span data-ttu-id="f685a-136">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="f685a-136">❌ 3.1</span></span>        | <span data-ttu-id="f685a-137">❌ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="f685a-137">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="f685a-138">❌ [27](linux-fedora.md#fedora-27-)</span><span class="sxs-lookup"><span data-stu-id="f685a-138">❌ [27](linux-fedora.md#fedora-27-)</span></span> | <span data-ttu-id="f685a-139">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="f685a-139">✔️ 2.1</span></span>        | <span data-ttu-id="f685a-140">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="f685a-140">❌ 3.1</span></span>        | <span data-ttu-id="f685a-141">❌ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="f685a-141">❌ 5.0 Preview</span></span> |

<span data-ttu-id="f685a-142">Die folgenden Versionen von .NET Core werden nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f685a-142">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="f685a-143">Die Downloads dafür bleiben weiterhin veröffentlicht:</span><span class="sxs-lookup"><span data-stu-id="f685a-143">The downloads for these still remain published:</span></span>

- <span data-ttu-id="f685a-144">3.0</span><span class="sxs-lookup"><span data-stu-id="f685a-144">3.0</span></span>
- <span data-ttu-id="f685a-145">2.2</span><span class="sxs-lookup"><span data-stu-id="f685a-145">2.2</span></span>
- <span data-ttu-id="f685a-146">2.0</span><span class="sxs-lookup"><span data-stu-id="f685a-146">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="f685a-147">Installieren anderer Versionen</span><span class="sxs-lookup"><span data-stu-id="f685a-147">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="fedora-32-"></a><span data-ttu-id="f685a-148">Fedora 32 ✔️</span><span class="sxs-lookup"><span data-stu-id="f685a-148">Fedora 32 ✔️</span></span>

<span data-ttu-id="f685a-149">NET Core 3.1 in den Standardpaketrepositorys für Fedora 32 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f685a-149">.NET Core 3.1 is available in the default package repositories for Fedora 32.</span></span>

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="fedora-31-"></a><span data-ttu-id="f685a-150">Fedora 31 ✔️</span><span class="sxs-lookup"><span data-stu-id="f685a-150">Fedora 31 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/31/prod.repo
```

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="fedora-30-"></a><span data-ttu-id="f685a-151">Fedora 30 ❌</span><span class="sxs-lookup"><span data-stu-id="f685a-151">Fedora 30 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/30/prod.repo
```

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="fedora-29-"></a><span data-ttu-id="f685a-152">Fedora 29 ❌</span><span class="sxs-lookup"><span data-stu-id="f685a-152">Fedora 29 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/29/prod.repo
```

[!INCLUDE [linux-dnf-install-30](includes/linux-install-30-dnf.md)]

## <a name="fedora-28-"></a><span data-ttu-id="f685a-153">Fedora 28 ❌</span><span class="sxs-lookup"><span data-stu-id="f685a-153">Fedora 28 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/28/prod.repo
```

[!INCLUDE [linux-dnf-install-20](includes/linux-install-20-dnf.md)]

## <a name="fedora-27-"></a><span data-ttu-id="f685a-154">Fedora 27 ❌</span><span class="sxs-lookup"><span data-stu-id="f685a-154">Fedora 27 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/27/prod.repo
```

[!INCLUDE [linux-dnf-install-20](includes/linux-install-20-dnf.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="f685a-155">Problembehandlung des Paket-Managers</span><span class="sxs-lookup"><span data-stu-id="f685a-155">Troubleshoot the package manager</span></span>

<span data-ttu-id="f685a-156">Dieser Abschnitt enthält Informationen zu häufigen Fehlern, die bei der Verwendung des Paket-Managers zur Installation von .NET Core auftreten können.</span><span class="sxs-lookup"><span data-stu-id="f685a-156">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="f685a-157">Paket konnte nicht gefunden werden</span><span class="sxs-lookup"><span data-stu-id="f685a-157">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="failed-to-fetch"></a><span data-ttu-id="f685a-158">Fehler beim Abrufen</span><span class="sxs-lookup"><span data-stu-id="f685a-158">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="snap"></a><span data-ttu-id="f685a-159">Snap</span><span class="sxs-lookup"><span data-stu-id="f685a-159">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="f685a-160">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="f685a-160">Dependencies</span></span>

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="f685a-161">Per Skript gesteuerte Installation</span><span class="sxs-lookup"><span data-stu-id="f685a-161">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="f685a-162">Manuelle Installation</span><span class="sxs-lookup"><span data-stu-id="f685a-162">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="f685a-163">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f685a-163">Next steps</span></span>

- [<span data-ttu-id="f685a-164">Tutorial: Erstellen einer Konsolenanwendung mit dem .NET Core SDK in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f685a-164">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
