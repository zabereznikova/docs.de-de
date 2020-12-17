---
title: Installieren von .NET unter CentOS – .NET
description: In diesem Artikel werden verschiedene Möglichkeiten veranschaulicht, das .NET SDK und die .NET-Runtime unter CentOS zu installieren.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 2c3453c79a1dc31f01577bc0c1b9e320eb307c0a
ms.sourcegitcommit: 45c7148f2483db2501c1aa696ab6ed2ed8cb71b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/08/2020
ms.locfileid: "96851678"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-centos"></a><span data-ttu-id="258e4-103">Installieren des .NET SDK oder der .NET-Runtime unter CentOS</span><span class="sxs-lookup"><span data-stu-id="258e4-103">Install the .NET SDK or the .NET Runtime on CentOS</span></span>

<span data-ttu-id="258e4-104">.NET wird unter CentOS unterstützt.</span><span class="sxs-lookup"><span data-stu-id="258e4-104">.NET is supported on CentOS.</span></span> <span data-ttu-id="258e4-105">In diesem Artikel wird beschrieben, wie Sie .NET unter CentOS installieren.</span><span class="sxs-lookup"><span data-stu-id="258e4-105">This article describes how to install .NET on CentOS.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="258e4-106">Unterstützte Distributionen</span><span class="sxs-lookup"><span data-stu-id="258e4-106">Supported distributions</span></span>

<span data-ttu-id="258e4-107">Die folgende Tabelle enthält die derzeit unter CentOS 7 und CentOS 8 unterstützten .NET-Releases.</span><span class="sxs-lookup"><span data-stu-id="258e4-107">The following table is a list of currently supported .NET releases on both CentOS 7 and CentOS 8.</span></span> <span data-ttu-id="258e4-108">Diese Versionen werden weiterhin unterstützt, bis entweder die Version von [.NET das Ende des Supports](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) erreicht oder die Version von CentOS nicht mehr unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="258e4-108">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of CentOS is no longer supported.</span></span>

- <span data-ttu-id="258e4-109">Das Häkchen ✔️ gibt an, dass die Version von CentOS oder .NET weiterhin unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="258e4-109">A ✔️ indicates that the version of CentOS or .NET is still supported.</span></span>
- <span data-ttu-id="258e4-110">Das ❌ gibt an, dass die Version von CentOS oder .NET in diesem CentOS-Release nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="258e4-110">A ❌ indicates that the version of CentOS or .NET isn't supported on that CentOS release.</span></span>
- <span data-ttu-id="258e4-111">Wenn sowohl eine Version von CentOS als auch eine Version von .NET mit ✔️ markiert sind, wird diese Kombination aus einem Betriebssystem und .NET unterstützt.</span><span class="sxs-lookup"><span data-stu-id="258e4-111">When both a version of CentOS and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="258e4-112">CentOS</span><span class="sxs-lookup"><span data-stu-id="258e4-112">CentOS</span></span>                   | <span data-ttu-id="258e4-113">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="258e4-113">.NET Core 2.1</span></span> | <span data-ttu-id="258e4-114">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="258e4-114">.NET Core 3.1</span></span> | <span data-ttu-id="258e4-115">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="258e4-115">.NET 5.0</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="258e4-116">✔️ [8](#centos-8-)</span><span class="sxs-lookup"><span data-stu-id="258e4-116">✔️ [8](#centos-8-)</span></span> | <span data-ttu-id="258e4-117">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="258e4-117">✔️ 2.1</span></span>        | <span data-ttu-id="258e4-118">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="258e4-118">✔️ 3.1</span></span>        | <span data-ttu-id="258e4-119">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="258e4-119">✔️ 5.0</span></span> |
| <span data-ttu-id="258e4-120">✔️ [7](#centos-7-)</span><span class="sxs-lookup"><span data-stu-id="258e4-120">✔️ [7](#centos-7-)</span></span> | <span data-ttu-id="258e4-121">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="258e4-121">✔️ 2.1</span></span>        | <span data-ttu-id="258e4-122">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="258e4-122">✔️ 3.1</span></span>        | <span data-ttu-id="258e4-123">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="258e4-123">✔️ 5.0</span></span> |

<span data-ttu-id="258e4-124">Die folgenden Versionen von .NET werden nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="258e4-124">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="258e4-125">Die Downloads dafür bleiben weiterhin veröffentlicht:</span><span class="sxs-lookup"><span data-stu-id="258e4-125">The downloads for these still remain published:</span></span>

- <span data-ttu-id="258e4-126">3.0</span><span class="sxs-lookup"><span data-stu-id="258e4-126">3.0</span></span>
- <span data-ttu-id="258e4-127">2.2</span><span class="sxs-lookup"><span data-stu-id="258e4-127">2.2</span></span>
- <span data-ttu-id="258e4-128">2.0</span><span class="sxs-lookup"><span data-stu-id="258e4-128">2.0</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="remove-preview-versions"></a><span data-ttu-id="258e4-129">Entfernen von Vorschauversionen</span><span class="sxs-lookup"><span data-stu-id="258e4-129">Remove preview versions</span></span>

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="258e4-130">Installieren anderer Versionen</span><span class="sxs-lookup"><span data-stu-id="258e4-130">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="centos-8-"></a><span data-ttu-id="258e4-131">CentOS 8 ✔️</span><span class="sxs-lookup"><span data-stu-id="258e4-131">CentOS 8 ✔️</span></span>

<span data-ttu-id="258e4-132">.NET 5.0 ist in den Standardpaketrepositorys für CentOS 8 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="258e4-132">.NET 5.0 is available in the default package repositories for CentOS 8.</span></span>

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="centos-7-"></a><span data-ttu-id="258e4-133">CentOS 7 ✔️</span><span class="sxs-lookup"><span data-stu-id="258e4-133">CentOS 7 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/centos/7/packages-microsoft-prod.rpm
```

[!INCLUDE [linux-yum-install-50](includes/linux-install-50-yum.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="258e4-134">Problembehandlung des Paket-Managers</span><span class="sxs-lookup"><span data-stu-id="258e4-134">Troubleshoot the package manager</span></span>

<span data-ttu-id="258e4-135">Dieser Abschnitt enthält Informationen zu häufigen Fehlern, die bei der Verwendung des Paket-Managers zur Installation von .NET auftreten können.</span><span class="sxs-lookup"><span data-stu-id="258e4-135">This section provides information on common errors you may get while using the package manager to install .NET.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="258e4-136">Paket konnte nicht gefunden werden</span><span class="sxs-lookup"><span data-stu-id="258e4-136">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="failed-to-fetch"></a><span data-ttu-id="258e4-137">Fehler beim Abrufen</span><span class="sxs-lookup"><span data-stu-id="258e4-137">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="snap"></a><span data-ttu-id="258e4-138">Snap</span><span class="sxs-lookup"><span data-stu-id="258e4-138">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="258e4-139">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="258e4-139">Dependencies</span></span>

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="258e4-140">Per Skript gesteuerte Installation</span><span class="sxs-lookup"><span data-stu-id="258e4-140">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="258e4-141">Manuelle Installation</span><span class="sxs-lookup"><span data-stu-id="258e4-141">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="258e4-142">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="258e4-142">Next steps</span></span>

- [<span data-ttu-id="258e4-143">Tutorial: Erstellen einer Konsolenanwendung mit dem .NET SDK in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="258e4-143">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
