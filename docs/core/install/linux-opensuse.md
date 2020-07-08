---
title: Installieren von .NET Core unter openSUSE (.NET Core)
description: Veranschaulicht verschiedene Möglichkeiten, das .NET Core SDK und die NET Core-Runtime unter openSUSE zu installieren.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 24f0a5b5278d038c2f941b0984efcacd91dcbe31
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619467"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-opensuse"></a><span data-ttu-id="526e3-103">Installieren des .NET Core SDK oder der .NET Core-Runtime unter openSUSE</span><span class="sxs-lookup"><span data-stu-id="526e3-103">Install .NET Core SDK or .NET Core Runtime on openSUSE</span></span>

<span data-ttu-id="526e3-104">.NET Core wird unter openSUSE unterstützt.</span><span class="sxs-lookup"><span data-stu-id="526e3-104">.NET Core is supported on openSUSE.</span></span> <span data-ttu-id="526e3-105">In diesem Artikel wird beschrieben, wie Sie .NET Core unter openSUSE installieren.</span><span class="sxs-lookup"><span data-stu-id="526e3-105">This article describes how to install .NET Core on openSUSE.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="526e3-106">Unterstützte Distributionen</span><span class="sxs-lookup"><span data-stu-id="526e3-106">Supported distributions</span></span>

<span data-ttu-id="526e3-107">Die folgende Tabelle ist eine Liste der derzeit unter openSUSE 15 unterstützten .NET Core-Versionen.</span><span class="sxs-lookup"><span data-stu-id="526e3-107">The following table is a list of currently supported .NET Core releases on openSUSE 15.</span></span> <span data-ttu-id="526e3-108">Diese Versionen werden weiterhin unterstützt, bis entweder die Version von [.NET Core das Ende des Supports](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) erreicht oder die Version von openSUSE nicht mehr unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="526e3-108">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of openSUSE is no longer supported.</span></span>

- <span data-ttu-id="526e3-109">✔️ gibt an, dass die Version von openSUSE oder .NET Core weiterhin unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="526e3-109">A ✔️ indicates that the version of openSUSE or .NET Core is still supported.</span></span>
- <span data-ttu-id="526e3-110">❌ gibt an, dass die Version von openSUSE oder .NET Core in dieser openSUSE-Version nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="526e3-110">A ❌ indicates that the version of openSUSE or .NET Core isn't supported on that openSUSE release.</span></span>
- <span data-ttu-id="526e3-111">Wenn sowohl eine Version von openSUSE als auch eine Version von .NET Core über ✔️ verfügen, wird diese Kombination aus Betriebssystem und .NET unterstützt.</span><span class="sxs-lookup"><span data-stu-id="526e3-111">When both a version of openSUSE and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="526e3-112">openSUSE</span><span class="sxs-lookup"><span data-stu-id="526e3-112">openSUSE</span></span>                   | <span data-ttu-id="526e3-113">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="526e3-113">.NET Core 2.1</span></span> | <span data-ttu-id="526e3-114">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="526e3-114">.NET Core 3.1</span></span> | <span data-ttu-id="526e3-115">.NET 5 Preview (nur manuelle Installation)</span><span class="sxs-lookup"><span data-stu-id="526e3-115">.NET 5 Preview (manual install only)</span></span> |
|----------------------------|---------------|---------------|----------------|
| <span data-ttu-id="526e3-116">✔️ [15](#opensuse-15-)</span><span class="sxs-lookup"><span data-stu-id="526e3-116">✔️ [15](#opensuse-15-)</span></span>     | <span data-ttu-id="526e3-117">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="526e3-117">✔️ 2.1</span></span>        | <span data-ttu-id="526e3-118">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="526e3-118">✔️ 3.1</span></span>        | <span data-ttu-id="526e3-119">✔️ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="526e3-119">✔️ 5.0 Preview</span></span> |

<span data-ttu-id="526e3-120">Die folgenden Versionen von .NET Core werden nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="526e3-120">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="526e3-121">Die Downloads dafür bleiben weiterhin veröffentlicht:</span><span class="sxs-lookup"><span data-stu-id="526e3-121">The downloads for these still remain published:</span></span>

- <span data-ttu-id="526e3-122">3.0</span><span class="sxs-lookup"><span data-stu-id="526e3-122">3.0</span></span>
- <span data-ttu-id="526e3-123">2.2</span><span class="sxs-lookup"><span data-stu-id="526e3-123">2.2</span></span>
- <span data-ttu-id="526e3-124">2.0</span><span class="sxs-lookup"><span data-stu-id="526e3-124">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="526e3-125">Installieren anderer Versionen</span><span class="sxs-lookup"><span data-stu-id="526e3-125">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="opensuse-15-"></a><span data-ttu-id="526e3-126">openSUSE 15 ✔️</span><span class="sxs-lookup"><span data-stu-id="526e3-126">openSUSE 15 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo zypper install libicu
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
wget https://packages.microsoft.com/config/opensuse/15/prod.repo
sudo mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo
sudo chown root:root /etc/zypp/repos.d/microsoft-prod.repo
```

[!INCLUDE [linux-zyp-install-31](includes/linux-install-31-zyp.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="526e3-127">Problembehandlung des Paket-Managers</span><span class="sxs-lookup"><span data-stu-id="526e3-127">Troubleshoot the package manager</span></span>

<span data-ttu-id="526e3-128">Dieser Abschnitt enthält Informationen zu häufigen Fehlern, die bei der Verwendung des Paket-Managers zur Installation von .NET Core auftreten können.</span><span class="sxs-lookup"><span data-stu-id="526e3-128">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="526e3-129">Fehler beim Abrufen</span><span class="sxs-lookup"><span data-stu-id="526e3-129">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="snap"></a><span data-ttu-id="526e3-130">Snap</span><span class="sxs-lookup"><span data-stu-id="526e3-130">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="526e3-131">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="526e3-131">Dependencies</span></span>

<span data-ttu-id="526e3-132">Wenn die Installation mit einem Paket-Manager erfolgt, werden diese Bibliotheken für Sie installiert.</span><span class="sxs-lookup"><span data-stu-id="526e3-132">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="526e3-133">Wenn Sie jedoch .NET Core manuell installieren oder eine eigenständige Anwendung veröffentlichen, müssen Sie sicherstellen, dass diese Bibliotheken installiert sind:</span><span class="sxs-lookup"><span data-stu-id="526e3-133">But, if you manually install .NET Core or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="526e3-134">krb5</span><span class="sxs-lookup"><span data-stu-id="526e3-134">krb5</span></span>
- <span data-ttu-id="526e3-135">libicu</span><span class="sxs-lookup"><span data-stu-id="526e3-135">libicu</span></span>
- <span data-ttu-id="526e3-136">libopenssl1_0_0</span><span class="sxs-lookup"><span data-stu-id="526e3-136">libopenssl1_0_0</span></span>

<span data-ttu-id="526e3-137">Wenn die OpenSSL-Version der Zielruntime-Umgebung 1.1 oder neuer ist, müssen Sie **compat-openssl10** installieren.</span><span class="sxs-lookup"><span data-stu-id="526e3-137">If the target runtime environment's OpenSSL version is 1.1 or newer, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="526e3-138">Weitere Informationen zu den Abhängigkeiten finden Sie unter [Eigenständige Linux-Apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span><span class="sxs-lookup"><span data-stu-id="526e3-138">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="526e3-139">Für .NET Core-Apps, die die Assembly *System.Drawing.Common* verwenden, benötigen Sie außerdem die folgende Abhängigkeit:</span><span class="sxs-lookup"><span data-stu-id="526e3-139">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- [<span data-ttu-id="526e3-140">libgdiplus (Version 6.0.1 oder höher)</span><span class="sxs-lookup"><span data-stu-id="526e3-140">libgdiplus (version 6.0.1 or later)</span></span>](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > <span data-ttu-id="526e3-141">Sie können eine neuere Version von *libgdiplus* installieren, indem Sie Ihrem System das Mono-Repository hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="526e3-141">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="526e3-142">Weitere Informationen finden Sie unter <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="526e3-142">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="scripted-install"></a><span data-ttu-id="526e3-143">Per Skript gesteuerte Installation</span><span class="sxs-lookup"><span data-stu-id="526e3-143">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="526e3-144">Manuelle Installation</span><span class="sxs-lookup"><span data-stu-id="526e3-144">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="526e3-145">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="526e3-145">Next steps</span></span>

- [<span data-ttu-id="526e3-146">Tutorial: Erstellen einer Konsolenanwendung mit dem .NET Core SDK in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="526e3-146">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
