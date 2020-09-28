---
title: Installieren von .NET Core unter CentOS (.NET Core)
description: Veranschaulicht verschiedene Möglichkeiten, das .NET Core SDK und die NET Core-Runtime unter CentOS zu installieren.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 7937502067e1717fd7f5c973c64ad33ae2a443a0
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538617"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-centos"></a><span data-ttu-id="ee652-103">Installieren des .NET Core SDK oder der .NET Core-Runtime unter CentOS</span><span class="sxs-lookup"><span data-stu-id="ee652-103">Install .NET Core SDK or .NET Core Runtime on CentOS</span></span>

<span data-ttu-id="ee652-104">.NET Core wird unter CentOS unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ee652-104">.NET Core is supported on CentOS.</span></span> <span data-ttu-id="ee652-105">In diesem Artikel wird beschrieben, wie Sie .NET Core unter CentOS installieren.</span><span class="sxs-lookup"><span data-stu-id="ee652-105">This article describes how to install .NET Core on CentOS.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="ee652-106">Unterstützte Distributionen</span><span class="sxs-lookup"><span data-stu-id="ee652-106">Supported distributions</span></span>

<span data-ttu-id="ee652-107">Die folgende Tabelle ist eine Liste der derzeit unter CentOS 7 und CentOS 8 unterstützten .NET Core-Versionen.</span><span class="sxs-lookup"><span data-stu-id="ee652-107">The following table is a list of currently supported .NET Core releases on both CentOS 7 and CentOS 8.</span></span> <span data-ttu-id="ee652-108">Diese Versionen werden weiterhin unterstützt, bis entweder die Version von [.NET Core das Ende des Supports](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) erreicht oder die Version von CentOS nicht mehr unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="ee652-108">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of CentOS is no longer supported.</span></span>

- <span data-ttu-id="ee652-109">✔️ gibt an, dass die Version von CentOS oder .NET Core weiterhin unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="ee652-109">A ✔️ indicates that the version of CentOS or .NET Core is still supported.</span></span>
- <span data-ttu-id="ee652-110">❌ gibt an, dass die Version von CentOS oder .NET Core in dieser CentOS-Version nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="ee652-110">A ❌ indicates that the version of CentOS or .NET Core isn't supported on that CentOS release.</span></span>
- <span data-ttu-id="ee652-111">Wenn sowohl eine Version von CentOS als auch eine Version von .NET Core über ✔️ verfügen, wird diese Kombination aus Betriebssystem und .NET unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ee652-111">When both a version of CentOS and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="ee652-112">CentOS</span><span class="sxs-lookup"><span data-stu-id="ee652-112">CentOS</span></span>                   | <span data-ttu-id="ee652-113">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="ee652-113">.NET Core 2.1</span></span> | <span data-ttu-id="ee652-114">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="ee652-114">.NET Core 3.1</span></span> | <span data-ttu-id="ee652-115">.NET 5 Preview (nur manuelle Installation)</span><span class="sxs-lookup"><span data-stu-id="ee652-115">.NET 5 Preview (manual install only)</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="ee652-116">✔️ [8](#centos-8-)</span><span class="sxs-lookup"><span data-stu-id="ee652-116">✔️ [8](#centos-8-)</span></span> | <span data-ttu-id="ee652-117">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="ee652-117">✔️ 2.1</span></span>        | <span data-ttu-id="ee652-118">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="ee652-118">✔️ 3.1</span></span>        | <span data-ttu-id="ee652-119">✔️ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="ee652-119">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="ee652-120">✔️ [7](#centos-7-)</span><span class="sxs-lookup"><span data-stu-id="ee652-120">✔️ [7](#centos-7-)</span></span> | <span data-ttu-id="ee652-121">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="ee652-121">✔️ 2.1</span></span>        | <span data-ttu-id="ee652-122">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="ee652-122">✔️ 3.1</span></span>        | <span data-ttu-id="ee652-123">✔️ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="ee652-123">✔️ 5.0 Preview</span></span> |

<span data-ttu-id="ee652-124">Die folgenden Versionen von .NET Core werden nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ee652-124">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="ee652-125">Die Downloads dafür bleiben weiterhin veröffentlicht:</span><span class="sxs-lookup"><span data-stu-id="ee652-125">The downloads for these still remain published:</span></span>

- <span data-ttu-id="ee652-126">3.0</span><span class="sxs-lookup"><span data-stu-id="ee652-126">3.0</span></span>
- <span data-ttu-id="ee652-127">2.2</span><span class="sxs-lookup"><span data-stu-id="ee652-127">2.2</span></span>
- <span data-ttu-id="ee652-128">2.0</span><span class="sxs-lookup"><span data-stu-id="ee652-128">2.0</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="ee652-129">Installieren anderer Versionen</span><span class="sxs-lookup"><span data-stu-id="ee652-129">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="centos-8-"></a><span data-ttu-id="ee652-130">CentOS 8 ✔️</span><span class="sxs-lookup"><span data-stu-id="ee652-130">CentOS 8 ✔️</span></span>

<span data-ttu-id="ee652-131">NET Core 3.1 in den Standardpaketrepositorys für CentOS 8 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ee652-131">.NET Core 3.1 is available in the default package repositories for CentOS 8.</span></span>

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="centos-7-"></a><span data-ttu-id="ee652-132">CentOS 7 ✔️</span><span class="sxs-lookup"><span data-stu-id="ee652-132">CentOS 7 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/centos/7/packages-microsoft-prod.rpm
```

[!INCLUDE [linux-yum-install-31](includes/linux-install-31-yum.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="ee652-133">Problembehandlung des Paket-Managers</span><span class="sxs-lookup"><span data-stu-id="ee652-133">Troubleshoot the package manager</span></span>

<span data-ttu-id="ee652-134">Dieser Abschnitt enthält Informationen zu häufigen Fehlern, die bei der Verwendung des Paket-Managers zur Installation von .NET Core auftreten können.</span><span class="sxs-lookup"><span data-stu-id="ee652-134">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="ee652-135">Paket konnte nicht gefunden werden</span><span class="sxs-lookup"><span data-stu-id="ee652-135">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="failed-to-fetch"></a><span data-ttu-id="ee652-136">Fehler beim Abrufen</span><span class="sxs-lookup"><span data-stu-id="ee652-136">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="snap"></a><span data-ttu-id="ee652-137">Snap</span><span class="sxs-lookup"><span data-stu-id="ee652-137">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="ee652-138">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="ee652-138">Dependencies</span></span>

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="ee652-139">Per Skript gesteuerte Installation</span><span class="sxs-lookup"><span data-stu-id="ee652-139">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="ee652-140">Manuelle Installation</span><span class="sxs-lookup"><span data-stu-id="ee652-140">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="ee652-141">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="ee652-141">Next steps</span></span>

- [<span data-ttu-id="ee652-142">Tutorial: Erstellen einer Konsolenanwendung mit dem .NET Core SDK in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="ee652-142">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
