---
title: Installieren von .NET unter openSUSE (.NET)
description: Veranschaulicht verschiedene Möglichkeiten, das .NET SDK und die NET-Runtime unter openSUSE zu installieren
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 17012f3689e5834fd1629946767e931cb22a2c1b
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506909"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-opensuse"></a><span data-ttu-id="b893e-103">Installieren des .NET SDK oder der .NET-Runtime unter openSUSE</span><span class="sxs-lookup"><span data-stu-id="b893e-103">Install the .NET SDK or the .NET Runtime on openSUSE</span></span>

<span data-ttu-id="b893e-104">.NET wird unter openSUSE unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b893e-104">.NET is supported on openSUSE.</span></span> <span data-ttu-id="b893e-105">In diesem Artikel wird beschrieben, wie Sie .NET unter openSUSE installieren.</span><span class="sxs-lookup"><span data-stu-id="b893e-105">This article describes how to install .NET on openSUSE.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="b893e-106">Unterstützte Distributionen</span><span class="sxs-lookup"><span data-stu-id="b893e-106">Supported distributions</span></span>

<span data-ttu-id="b893e-107">Die folgende Tabelle enthält die derzeit unter openSUSE 15 unterstützten .NET-Releases.</span><span class="sxs-lookup"><span data-stu-id="b893e-107">The following table is a list of currently supported .NET releases on openSUSE 15.</span></span> <span data-ttu-id="b893e-108">Diese Versionen werden weiterhin unterstützt, bis entweder die Version von [.NET das Ende des Supports](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) erreicht oder die Version von openSUSE nicht mehr unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="b893e-108">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of openSUSE is no longer supported.</span></span>

- <span data-ttu-id="b893e-109">✔️ gibt an, dass die Version von openSUSE oder .NET weiterhin unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="b893e-109">A ✔️ indicates that the version of openSUSE or .NET is still supported.</span></span>
- <span data-ttu-id="b893e-110">❌ gibt an, dass die Version von openSUSE oder .NET in diesem openSUSE-Release nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="b893e-110">A ❌ indicates that the version of openSUSE or .NET isn't supported on that openSUSE release.</span></span>
- <span data-ttu-id="b893e-111">Wenn sowohl eine Version von openSUSE als auch eine Version von .NET über ✔️ verfügen, wird diese Kombination aus Betriebssystem und .NET unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b893e-111">When both a version of openSUSE and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="b893e-112">openSUSE</span><span class="sxs-lookup"><span data-stu-id="b893e-112">openSUSE</span></span>                   | <span data-ttu-id="b893e-113">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="b893e-113">.NET Core 2.1</span></span> | <span data-ttu-id="b893e-114">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="b893e-114">.NET Core 3.1</span></span> | <span data-ttu-id="b893e-115">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="b893e-115">.NET 5.0</span></span> |
|----------------------------|---------------|---------------|----------------|
| <span data-ttu-id="b893e-116">✔️ [15](#opensuse-15-)</span><span class="sxs-lookup"><span data-stu-id="b893e-116">✔️ [15](#opensuse-15-)</span></span>     | <span data-ttu-id="b893e-117">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="b893e-117">✔️ 2.1</span></span>        | <span data-ttu-id="b893e-118">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="b893e-118">✔️ 3.1</span></span>        | <span data-ttu-id="b893e-119">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="b893e-119">✔️ 5.0</span></span> |

<span data-ttu-id="b893e-120">Die folgenden Versionen von .NET werden nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b893e-120">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="b893e-121">Die Downloads dafür bleiben weiterhin veröffentlicht:</span><span class="sxs-lookup"><span data-stu-id="b893e-121">The downloads for these still remain published:</span></span>

- <span data-ttu-id="b893e-122">3.0</span><span class="sxs-lookup"><span data-stu-id="b893e-122">3.0</span></span>
- <span data-ttu-id="b893e-123">2.2</span><span class="sxs-lookup"><span data-stu-id="b893e-123">2.2</span></span>
- <span data-ttu-id="b893e-124">2.0</span><span class="sxs-lookup"><span data-stu-id="b893e-124">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="b893e-125">Installieren anderer Versionen</span><span class="sxs-lookup"><span data-stu-id="b893e-125">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="opensuse-15-"></a><span data-ttu-id="b893e-126">openSUSE 15 ✔️</span><span class="sxs-lookup"><span data-stu-id="b893e-126">openSUSE 15 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo zypper install libicu
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
wget https://packages.microsoft.com/config/opensuse/15/prod.repo
sudo mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo
sudo chown root:root /etc/zypp/repos.d/microsoft-prod.repo
```

[!INCLUDE [linux-zyp-install-50](includes/linux-install-50-zyp.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="b893e-127">Problembehandlung des Paket-Managers</span><span class="sxs-lookup"><span data-stu-id="b893e-127">Troubleshoot the package manager</span></span>

<span data-ttu-id="b893e-128">Dieser Abschnitt enthält Informationen zu häufigen Fehlern, die bei der Verwendung des Paket-Managers zur Installation von .NET auftreten können.</span><span class="sxs-lookup"><span data-stu-id="b893e-128">This section provides information on common errors you may get while using the package manager to install .NET.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="b893e-129">Paket konnte nicht gefunden werden</span><span class="sxs-lookup"><span data-stu-id="b893e-129">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="failed-to-fetch"></a><span data-ttu-id="b893e-130">Fehler beim Abrufen</span><span class="sxs-lookup"><span data-stu-id="b893e-130">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="snap"></a><span data-ttu-id="b893e-131">Snap</span><span class="sxs-lookup"><span data-stu-id="b893e-131">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="b893e-132">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="b893e-132">Dependencies</span></span>

<span data-ttu-id="b893e-133">Wenn die Installation mit einem Paket-Manager erfolgt, werden diese Bibliotheken für Sie installiert.</span><span class="sxs-lookup"><span data-stu-id="b893e-133">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="b893e-134">Wenn Sie jedoch .NET manuell installieren oder eine eigenständige Anwendung veröffentlichen, müssen Sie sicherstellen, dass diese Bibliotheken installiert sind:</span><span class="sxs-lookup"><span data-stu-id="b893e-134">But, if you manually install .NET or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="b893e-135">krb5</span><span class="sxs-lookup"><span data-stu-id="b893e-135">krb5</span></span>
- <span data-ttu-id="b893e-136">libicu</span><span class="sxs-lookup"><span data-stu-id="b893e-136">libicu</span></span>
- <span data-ttu-id="b893e-137">libopenssl1_0_0</span><span class="sxs-lookup"><span data-stu-id="b893e-137">libopenssl1_0_0</span></span>

<span data-ttu-id="b893e-138">Wenn die OpenSSL-Version der Zielruntime-Umgebung 1.1 oder neuer ist, müssen Sie **compat-openssl10** installieren.</span><span class="sxs-lookup"><span data-stu-id="b893e-138">If the target runtime environment's OpenSSL version is 1.1 or newer, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="b893e-139">Weitere Informationen zu den Abhängigkeiten finden Sie unter [Eigenständige Linux-Apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span><span class="sxs-lookup"><span data-stu-id="b893e-139">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="b893e-140">Für .NET-Anwendungen, die die Assembly *System.Drawing.Common* verwenden, benötigen Sie außerdem die folgende Abhängigkeit:</span><span class="sxs-lookup"><span data-stu-id="b893e-140">For .NET apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- [<span data-ttu-id="b893e-141">libgdiplus (Version 6.0.1 oder höher)</span><span class="sxs-lookup"><span data-stu-id="b893e-141">libgdiplus (version 6.0.1 or later)</span></span>](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > <span data-ttu-id="b893e-142">Sie können eine neuere Version von *libgdiplus* installieren, indem Sie Ihrem System das Mono-Repository hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b893e-142">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="b893e-143">Weitere Informationen finden Sie unter <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="b893e-143">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="scripted-install"></a><span data-ttu-id="b893e-144">Per Skript gesteuerte Installation</span><span class="sxs-lookup"><span data-stu-id="b893e-144">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="b893e-145">Manuelle Installation</span><span class="sxs-lookup"><span data-stu-id="b893e-145">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="b893e-146">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="b893e-146">Next steps</span></span>

- [<span data-ttu-id="b893e-147">Tutorial: Erstellen einer Konsolenanwendung mit dem .NET SDK in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="b893e-147">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
