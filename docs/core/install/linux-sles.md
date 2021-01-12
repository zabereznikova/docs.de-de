---
title: 'Installieren von .NET für SLES: .NET'
description: In diesem Artikel werden verschiedene Möglichkeiten veranschaulicht, das .NET SDK und die .NET-Runtime für SLES zu installieren.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: 80da69616dd1507b809ef56d439645d569a6a805
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970784"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-sles"></a><span data-ttu-id="054fe-103">Installieren des .NET SDK oder der .NET-Runtime für SLES</span><span class="sxs-lookup"><span data-stu-id="054fe-103">Install the .NET SDK or the .NET Runtime on SLES</span></span>

<span data-ttu-id="054fe-104">.NET wird unter SLES unterstützt.</span><span class="sxs-lookup"><span data-stu-id="054fe-104">.NET is supported on SLES.</span></span> <span data-ttu-id="054fe-105">In diesem Artikel wird beschrieben, wie Sie .NET für SLES installieren.</span><span class="sxs-lookup"><span data-stu-id="054fe-105">This article describes how to install .NET on SLES.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="supported-distributions"></a><span data-ttu-id="054fe-106">Unterstützte Distributionen</span><span class="sxs-lookup"><span data-stu-id="054fe-106">Supported distributions</span></span>

<span data-ttu-id="054fe-107">Die folgende Tabelle enthält die derzeit unter SLES 12 SP2 und SLES 15 unterstützten .NET-Releases.</span><span class="sxs-lookup"><span data-stu-id="054fe-107">The following table is a list of currently supported .NET releases on both SLES 12 SP2 and SLES 15.</span></span> <span data-ttu-id="054fe-108">Diese Versionen werden weiterhin unterstützt, bis entweder die Version von [.NET das Ende des Supports](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) erreicht oder die Version von SLES nicht mehr unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="054fe-108">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of SLES is no longer supported.</span></span>

- <span data-ttu-id="054fe-109">✔️ gibt an, dass die Version von SLES oder .NET weiterhin unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="054fe-109">A ✔️ indicates that the version of SLES or .NET is still supported.</span></span>
- <span data-ttu-id="054fe-110">❌ gibt an, dass die Version von SLES oder .NET in diesem SLES-Release nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="054fe-110">A ❌ indicates that the version of SLES or .NET isn't supported on that SLES release.</span></span>
- <span data-ttu-id="054fe-111">Wenn sowohl eine Version von SLES als auch eine Version von .NET mit ✔️ markiert sind, wird diese Kombination aus Betriebssystem und .NET unterstützt.</span><span class="sxs-lookup"><span data-stu-id="054fe-111">When both a version of SLES and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="054fe-112">SLES</span><span class="sxs-lookup"><span data-stu-id="054fe-112">SLES</span></span>                   | <span data-ttu-id="054fe-113">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="054fe-113">.NET Core 2.1</span></span> | <span data-ttu-id="054fe-114">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="054fe-114">.NET Core 3.1</span></span> | <span data-ttu-id="054fe-115">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="054fe-115">.NET 5.0</span></span> |
|------------------------|---------------|---------------|----------------|
| <span data-ttu-id="054fe-116">✔️ [15](#sles-15-)</span><span class="sxs-lookup"><span data-stu-id="054fe-116">✔️ [15](#sles-15-)</span></span>     | <span data-ttu-id="054fe-117">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="054fe-117">✔️ 2.1</span></span>        | <span data-ttu-id="054fe-118">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="054fe-118">✔️ 3.1</span></span>        | <span data-ttu-id="054fe-119">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="054fe-119">✔️ 5.0</span></span> |
| <span data-ttu-id="054fe-120">✔️ [12 SP2](#sles-12-)</span><span class="sxs-lookup"><span data-stu-id="054fe-120">✔️ [12 SP2](#sles-12-)</span></span> | <span data-ttu-id="054fe-121">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="054fe-121">✔️ 2.1</span></span>        | <span data-ttu-id="054fe-122">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="054fe-122">✔️ 3.1</span></span>        | <span data-ttu-id="054fe-123">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="054fe-123">✔️ 5.0</span></span> |

<span data-ttu-id="054fe-124">Die folgenden Versionen von .NET Core werden nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="054fe-124">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="054fe-125">Die Downloads dafür bleiben weiterhin veröffentlicht:</span><span class="sxs-lookup"><span data-stu-id="054fe-125">The downloads for these still remain published:</span></span>

- <span data-ttu-id="054fe-126">3.0</span><span class="sxs-lookup"><span data-stu-id="054fe-126">3.0</span></span>
- <span data-ttu-id="054fe-127">2.2</span><span class="sxs-lookup"><span data-stu-id="054fe-127">2.2</span></span>
- <span data-ttu-id="054fe-128">2.0</span><span class="sxs-lookup"><span data-stu-id="054fe-128">2.0</span></span>

## <a name="remove-preview-versions"></a><span data-ttu-id="054fe-129">Entfernen von Vorschauversionen</span><span class="sxs-lookup"><span data-stu-id="054fe-129">Remove preview versions</span></span>

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="sles-15-"></a><span data-ttu-id="054fe-130">SLES 15 ✔️</span><span class="sxs-lookup"><span data-stu-id="054fe-130">SLES 15 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/15/packages-microsoft-prod.rpm
```

<span data-ttu-id="054fe-131">Das Setuppaket für das Microsoft-Repository „SLES 15“ installiert zurzeit die Datei *microsoft-prod.repo* im falschen Verzeichnis, sodass zypper die .NET-Pakete nicht finden kann.</span><span class="sxs-lookup"><span data-stu-id="054fe-131">Currently, the SLES 15 Microsoft repository setup package installs the *microsoft-prod.repo* file to the wrong directory, preventing zypper from finding the .NET packages.</span></span> <span data-ttu-id="054fe-132">Erstellen Sie einen Symlink im richtigen Verzeichnis, um dieses Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="054fe-132">To fix this problem, create a symlink in the correct directory.</span></span>

```bash
sudo ln -s /etc/yum.repos.d/microsoft-prod.repo /etc/zypp/repos.d/microsoft-prod.repo
```

[!INCLUDE [linux-zyp-install-50](includes/linux-install-50-zyp.md)]

## <a name="sles-12-"></a><span data-ttu-id="054fe-133">SLES 12 ✔️</span><span class="sxs-lookup"><span data-stu-id="054fe-133">SLES 12 ✔️</span></span>

<span data-ttu-id="054fe-134">.NET setzt für die SLES 12-Familie mindestens SP2 voraus.</span><span class="sxs-lookup"><span data-stu-id="054fe-134">.NET requires SP2 as a minimum for the SLES 12 family.</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/12/packages-microsoft-prod.rpm
```

[!INCLUDE [linux-zyp-install-50](includes/linux-install-50-zyp.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="054fe-135">Installieren anderer Versionen</span><span class="sxs-lookup"><span data-stu-id="054fe-135">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="054fe-136">Problembehandlung des Paket-Managers</span><span class="sxs-lookup"><span data-stu-id="054fe-136">Troubleshoot the package manager</span></span>

<span data-ttu-id="054fe-137">Dieser Abschnitt enthält Informationen zu häufigen Fehlern, die bei der Verwendung des Paket-Managers zur Installation von .NET auftreten können.</span><span class="sxs-lookup"><span data-stu-id="054fe-137">This section provides information on common errors you may get while using the package manager to install .NET.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="054fe-138">Fehler beim Abrufen</span><span class="sxs-lookup"><span data-stu-id="054fe-138">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="dependencies"></a><span data-ttu-id="054fe-139">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="054fe-139">Dependencies</span></span>

<span data-ttu-id="054fe-140">Wenn die Installation mit einem Paket-Manager erfolgt, werden diese Bibliotheken für Sie installiert.</span><span class="sxs-lookup"><span data-stu-id="054fe-140">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="054fe-141">Wenn Sie jedoch .NET manuell installieren oder eine eigenständige Anwendung veröffentlichen, müssen Sie sicherstellen, dass diese Bibliotheken installiert sind:</span><span class="sxs-lookup"><span data-stu-id="054fe-141">But, if you manually install .NET or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="054fe-142">krb5</span><span class="sxs-lookup"><span data-stu-id="054fe-142">krb5</span></span>
- <span data-ttu-id="054fe-143">libicu</span><span class="sxs-lookup"><span data-stu-id="054fe-143">libicu</span></span>
- <span data-ttu-id="054fe-144">libopenssl1_1</span><span class="sxs-lookup"><span data-stu-id="054fe-144">libopenssl1_1</span></span>

<span data-ttu-id="054fe-145">Wenn die OpenSSL-Version der Zielruntime-Umgebung 1.1 oder neuer ist, müssen Sie **compat-openssl10** installieren.</span><span class="sxs-lookup"><span data-stu-id="054fe-145">If the target runtime environment's OpenSSL version is 1.1 or newer, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="054fe-146">Weitere Informationen zu den Abhängigkeiten finden Sie unter [Eigenständige Linux-Apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span><span class="sxs-lookup"><span data-stu-id="054fe-146">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="054fe-147">Für .NET-Anwendungen, die die Assembly *System.Drawing.Common* verwenden, benötigen Sie außerdem die folgende Abhängigkeit:</span><span class="sxs-lookup"><span data-stu-id="054fe-147">For .NET apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- [<span data-ttu-id="054fe-148">libgdiplus (Version 6.0.1 oder höher)</span><span class="sxs-lookup"><span data-stu-id="054fe-148">libgdiplus (version 6.0.1 or later)</span></span>](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > <span data-ttu-id="054fe-149">Sie können eine neuere Version von *libgdiplus* installieren, indem Sie Ihrem System das Mono-Repository hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="054fe-149">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="054fe-150">Weitere Informationen finden Sie unter <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="054fe-150">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="next-steps"></a><span data-ttu-id="054fe-151">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="054fe-151">Next steps</span></span>

- [<span data-ttu-id="054fe-152">Aktivieren der Vervollständigung mit der TAB-TASTE für die .NET-CLI</span><span class="sxs-lookup"><span data-stu-id="054fe-152">How to enable TAB completion for the .NET CLI</span></span>](../tools/enable-tab-autocomplete.md)
- [<span data-ttu-id="054fe-153">Tutorial: Erstellen einer Konsolenanwendung mit dem .NET SDK in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="054fe-153">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
