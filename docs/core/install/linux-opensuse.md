---
title: Installieren von .NET Core unter openSUSE (.NET Core)
description: Veranschaulicht verschiedene Möglichkeiten, das .NET Core SDK und die NET Core-Runtime unter openSUSE zu installieren.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 3a2ff1ca1519428f42c88048dde22aa11baaaa01
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324748"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-opensuse"></a><span data-ttu-id="a7df9-103">Installieren des .NET Core SDK oder der .NET Core-Runtime unter openSUSE</span><span class="sxs-lookup"><span data-stu-id="a7df9-103">Install .NET Core SDK or .NET Core Runtime on openSUSE</span></span>

<span data-ttu-id="a7df9-104">.NET Core wird unter openSUSE unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a7df9-104">.NET Core is supported on openSUSE.</span></span> <span data-ttu-id="a7df9-105">In diesem Artikel wird beschrieben, wie Sie .NET Core unter openSUSE installieren.</span><span class="sxs-lookup"><span data-stu-id="a7df9-105">This article describes how to install .NET Core on openSUSE.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="a7df9-106">Unterstützte Distributionen</span><span class="sxs-lookup"><span data-stu-id="a7df9-106">Supported distributions</span></span>

<span data-ttu-id="a7df9-107">Die folgende Tabelle ist eine Liste der derzeit unter openSUSE 15 unterstützten .NET Core-Versionen.</span><span class="sxs-lookup"><span data-stu-id="a7df9-107">The following table is a list of currently supported .NET Core releases on openSUSE 15.</span></span> <span data-ttu-id="a7df9-108">Diese Versionen werden weiterhin unterstützt, bis entweder die Version von [.NET Core das Ende des Supports](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) erreicht oder die Version von openSUSE nicht mehr unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="a7df9-108">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of openSUSE is no longer supported.</span></span>

- <span data-ttu-id="a7df9-109">✔️ gibt an, dass die Version von openSUSE oder .NET Core weiterhin unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="a7df9-109">A ✔️ indicates that the version of openSUSE or .NET Core is still supported.</span></span>
- <span data-ttu-id="a7df9-110">❌ gibt an, dass die Version von openSUSE oder .NET Core in dieser openSUSE-Version nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="a7df9-110">A ❌ indicates that the version of openSUSE or .NET Core isn't supported on that openSUSE release.</span></span>
- <span data-ttu-id="a7df9-111">Wenn sowohl eine Version von openSUSE als auch eine Version von .NET Core über ✔️ verfügen, wird diese Kombination aus Betriebssystem und .NET unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a7df9-111">When both a version of openSUSE and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="a7df9-112">openSUSE</span><span class="sxs-lookup"><span data-stu-id="a7df9-112">openSUSE</span></span>                   | <span data-ttu-id="a7df9-113">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="a7df9-113">.NET Core 2.1</span></span> | <span data-ttu-id="a7df9-114">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="a7df9-114">.NET Core 3.1</span></span> | <span data-ttu-id="a7df9-115">.NET 5 Preview (nur manuelle Installation)</span><span class="sxs-lookup"><span data-stu-id="a7df9-115">.NET 5 Preview (manual install only)</span></span> |
|----------------------------|---------------|---------------|----------------|
| <span data-ttu-id="a7df9-116">✔️ [15](#opensuse-15-)</span><span class="sxs-lookup"><span data-stu-id="a7df9-116">✔️ [15](#opensuse-15-)</span></span>     | <span data-ttu-id="a7df9-117">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="a7df9-117">✔️ 2.1</span></span>        | <span data-ttu-id="a7df9-118">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="a7df9-118">✔️ 3.1</span></span>        | <span data-ttu-id="a7df9-119">✔️ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="a7df9-119">✔️ 5.0 Preview</span></span> |

<span data-ttu-id="a7df9-120">Die folgenden Versionen von .NET Core werden nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a7df9-120">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="a7df9-121">Die Downloads dafür bleiben weiterhin veröffentlicht:</span><span class="sxs-lookup"><span data-stu-id="a7df9-121">The downloads for these still remain published:</span></span>

- <span data-ttu-id="a7df9-122">3.0</span><span class="sxs-lookup"><span data-stu-id="a7df9-122">3.0</span></span>
- <span data-ttu-id="a7df9-123">2.2</span><span class="sxs-lookup"><span data-stu-id="a7df9-123">2.2</span></span>
- <span data-ttu-id="a7df9-124">2.0</span><span class="sxs-lookup"><span data-stu-id="a7df9-124">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="a7df9-125">Installieren anderer Versionen</span><span class="sxs-lookup"><span data-stu-id="a7df9-125">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="opensuse-15-"></a><span data-ttu-id="a7df9-126">openSUSE 15 ✔️</span><span class="sxs-lookup"><span data-stu-id="a7df9-126">openSUSE 15 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo zypper install libicu
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
wget https://packages.microsoft.com/config/opensuse/15/prod.repo
sudo mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo
sudo chown root:root /etc/zypp/repos.d/microsoft-prod.repo
```

[!INCLUDE [linux-zyp-install-31](includes/linux-install-31-zyp.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="a7df9-127">Problembehandlung des Paket-Managers</span><span class="sxs-lookup"><span data-stu-id="a7df9-127">Troubleshoot the package manager</span></span>

<span data-ttu-id="a7df9-128">Dieser Abschnitt enthält Informationen zu häufigen Fehlern, die bei der Verwendung des Paket-Managers zur Installation von .NET Core auftreten können.</span><span class="sxs-lookup"><span data-stu-id="a7df9-128">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="a7df9-129">Fehler beim Abrufen</span><span class="sxs-lookup"><span data-stu-id="a7df9-129">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="snap"></a><span data-ttu-id="a7df9-130">Snap</span><span class="sxs-lookup"><span data-stu-id="a7df9-130">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="a7df9-131">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="a7df9-131">Dependencies</span></span>

[!INCLUDE [linux-install-dependencies](includes/linux-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="a7df9-132">Per Skript gesteuerte Installation</span><span class="sxs-lookup"><span data-stu-id="a7df9-132">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="a7df9-133">Manuelle Installation</span><span class="sxs-lookup"><span data-stu-id="a7df9-133">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="a7df9-134">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="a7df9-134">Next steps</span></span>

- [<span data-ttu-id="a7df9-135">Tutorial: Erstellen einer Konsolenanwendung mit dem .NET Core SDK in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="a7df9-135">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
