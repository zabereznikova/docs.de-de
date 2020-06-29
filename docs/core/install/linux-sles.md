---
title: Installieren von .NET Core unter SLES (.NET Core)
description: Veranschaulicht verschiedene Möglichkeiten, das .NET Core SDK und die NET Core-Runtime unter SLES zu installieren.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: e1a2490c1d653eb07aebdd51e34e1bf462906482
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324695"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-sles"></a><span data-ttu-id="a3e95-103">Installieren des .NET Core SDK oder der .NET Core-Runtime unter SLES</span><span class="sxs-lookup"><span data-stu-id="a3e95-103">Install .NET Core SDK or .NET Core Runtime on SLES</span></span>

<span data-ttu-id="a3e95-104">.NET Core wird unter SLES unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a3e95-104">.NET Core is supported on SLES.</span></span> <span data-ttu-id="a3e95-105">In diesem Artikel wird beschrieben, wie Sie .NET Core unter SLES installieren.</span><span class="sxs-lookup"><span data-stu-id="a3e95-105">This article describes how to install .NET Core on SLES.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="supported-distributions"></a><span data-ttu-id="a3e95-106">Unterstützte Distributionen</span><span class="sxs-lookup"><span data-stu-id="a3e95-106">Supported distributions</span></span>

<span data-ttu-id="a3e95-107">Die folgende Tabelle ist eine Liste der derzeit unter SLES 12 SP2 and SLES 15 unterstützten .NET Core-Versionen.</span><span class="sxs-lookup"><span data-stu-id="a3e95-107">The following table is a list of currently supported .NET Core releases on both SLES 12 SP2 and SLES 15.</span></span> <span data-ttu-id="a3e95-108">Diese Versionen werden weiterhin unterstützt, bis entweder die Version von [.NET Core das Ende des Supports](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) erreicht oder die Version von SLES nicht mehr unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="a3e95-108">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of SLES is no longer supported.</span></span>

- <span data-ttu-id="a3e95-109">✔️ gibt an, dass die Version von SLES oder .NET Core weiterhin unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="a3e95-109">A ✔️ indicates that the version of SLES or .NET Core is still supported.</span></span>
- <span data-ttu-id="a3e95-110">❌ gibt an, dass die Version von SLES oder .NET Core in dieser SLES-Version nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="a3e95-110">A ❌ indicates that the version of SLES or .NET Core isn't supported on that SLES release.</span></span>
- <span data-ttu-id="a3e95-111">Wenn sowohl eine Version von SLES als auch eine Version von .NET Core über ✔️ verfügen, wird diese Kombination aus Betriebssystem und .NET unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a3e95-111">When both a version of SLES and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="a3e95-112">SLES</span><span class="sxs-lookup"><span data-stu-id="a3e95-112">SLES</span></span>                   | <span data-ttu-id="a3e95-113">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="a3e95-113">.NET Core 2.1</span></span> | <span data-ttu-id="a3e95-114">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="a3e95-114">.NET Core 3.1</span></span> | <span data-ttu-id="a3e95-115">.NET 5 Preview (nur manuelle Installation)</span><span class="sxs-lookup"><span data-stu-id="a3e95-115">.NET 5 Preview (manual install only)</span></span> |
|------------------------|---------------|---------------|----------------|
| <span data-ttu-id="a3e95-116">✔️ [15](#sles-15-)</span><span class="sxs-lookup"><span data-stu-id="a3e95-116">✔️ [15](#sles-15-)</span></span>     | <span data-ttu-id="a3e95-117">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="a3e95-117">✔️ 2.1</span></span>        | <span data-ttu-id="a3e95-118">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="a3e95-118">✔️ 3.1</span></span>        | <span data-ttu-id="a3e95-119">✔️ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="a3e95-119">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="a3e95-120">✔️ [12 SP2](#sles-12-)</span><span class="sxs-lookup"><span data-stu-id="a3e95-120">✔️ [12 SP2](#sles-12-)</span></span> | <span data-ttu-id="a3e95-121">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="a3e95-121">✔️ 2.1</span></span>        | <span data-ttu-id="a3e95-122">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="a3e95-122">✔️ 3.1</span></span>        | <span data-ttu-id="a3e95-123">✔️ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="a3e95-123">✔️ 5.0 Preview</span></span> |

<span data-ttu-id="a3e95-124">Die folgenden Versionen von .NET Core werden nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a3e95-124">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="a3e95-125">Die Downloads dafür bleiben weiterhin veröffentlicht:</span><span class="sxs-lookup"><span data-stu-id="a3e95-125">The downloads for these still remain published:</span></span>

- <span data-ttu-id="a3e95-126">3.0</span><span class="sxs-lookup"><span data-stu-id="a3e95-126">3.0</span></span>
- <span data-ttu-id="a3e95-127">2.2</span><span class="sxs-lookup"><span data-stu-id="a3e95-127">2.2</span></span>
- <span data-ttu-id="a3e95-128">2.0</span><span class="sxs-lookup"><span data-stu-id="a3e95-128">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="a3e95-129">Installieren anderer Versionen</span><span class="sxs-lookup"><span data-stu-id="a3e95-129">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="sles-15-"></a><span data-ttu-id="a3e95-130">SLES 15 ✔️</span><span class="sxs-lookup"><span data-stu-id="a3e95-130">SLES 15 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/15/packages-microsoft-prod.rpm
```

<span data-ttu-id="a3e95-131">Das Setuppaket für das Microsoft-Repository „SLES 15“ installiert zurzeit die Datei *microsoft-prod.repo* im falschen Verzeichnis, sodass zypper die .NET Core-Pakete nicht finden kann.</span><span class="sxs-lookup"><span data-stu-id="a3e95-131">Currently, the SLES 15 Microsoft repository setup package installs the *microsoft-prod.repo* file to the wrong directory, preventing zypper from finding the .NET Core packages.</span></span> <span data-ttu-id="a3e95-132">Erstellen Sie einen Symlink im richtigen Verzeichnis, um dieses Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="a3e95-132">To fix this problem, create a symlink in the correct directory.</span></span>

```bash
sudo ln -s /etc/yum.repos.d/microsoft-prod.repo /etc/zypp/repos.d/microsoft-prod.repo
```

[!INCLUDE [linux-zyp-install-31](includes/linux-install-31-zyp.md)]

## <a name="sles-12-"></a><span data-ttu-id="a3e95-133">SLES 12 ✔️</span><span class="sxs-lookup"><span data-stu-id="a3e95-133">SLES 12 ✔️</span></span>

<span data-ttu-id="a3e95-134">NET Core setzt für die SLES 12-Familie mindestens SP2 voraus.</span><span class="sxs-lookup"><span data-stu-id="a3e95-134">.NET Core requires SP2 as a minimum for the SLES 12 family.</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/12/packages-microsoft-prod.rpm
```

[!INCLUDE [linux-zyp-install-31](includes/linux-install-31-zyp.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="a3e95-135">Problembehandlung des Paket-Managers</span><span class="sxs-lookup"><span data-stu-id="a3e95-135">Troubleshoot the package manager</span></span>

<span data-ttu-id="a3e95-136">Dieser Abschnitt enthält Informationen zu häufigen Fehlern, die bei der Verwendung des Paket-Managers zur Installation von .NET Core auftreten können.</span><span class="sxs-lookup"><span data-stu-id="a3e95-136">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="a3e95-137">Fehler beim Abrufen</span><span class="sxs-lookup"><span data-stu-id="a3e95-137">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="dependencies"></a><span data-ttu-id="a3e95-138">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="a3e95-138">Dependencies</span></span>

[!INCLUDE [linux-install-dependencies](includes/linux-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="a3e95-139">Per Skript gesteuerte Installation</span><span class="sxs-lookup"><span data-stu-id="a3e95-139">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="a3e95-140">Manuelle Installation</span><span class="sxs-lookup"><span data-stu-id="a3e95-140">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="a3e95-141">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="a3e95-141">Next steps</span></span>

- [<span data-ttu-id="a3e95-142">Tutorial: Erstellen einer Konsolenanwendung mit dem .NET Core SDK in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="a3e95-142">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
