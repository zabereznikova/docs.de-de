---
title: 'Installieren von .NET unter Fedora: .NET'
description: In diesem Artikel werden verschiedene Möglichkeiten veranschaulicht, das .NET SDK und die .NET-Runtime für Fedora zu installieren.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: 9dd8c6264831e2a9382960be505639f1eba95151
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970823"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-fedora"></a><span data-ttu-id="f9630-103">Installieren des .NET SDK oder der .NET-Runtime unter Fedora</span><span class="sxs-lookup"><span data-stu-id="f9630-103">Install the .NET SDK or the .NET Runtime on Fedora</span></span>

<span data-ttu-id="f9630-104">.NET wird unter Fedora unterstützt. In diesem Artikel wird beschrieben, wie Sie .NET unter Fedora installieren.</span><span class="sxs-lookup"><span data-stu-id="f9630-104">.NET is supported on Fedora and this article describes how to install .NET on Fedora.</span></span> <span data-ttu-id="f9630-105">Wenn für eine Fedora-Version kein Support mehr geboten wird, wird .NET mit dieser Version nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f9630-105">When a Fedora version falls out of support, .NET is no longer supported with that version.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="install-net-50"></a><span data-ttu-id="f9630-106">Installieren von .NET 5.0</span><span class="sxs-lookup"><span data-stu-id="f9630-106">Install .NET 5.0</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

<span data-ttu-id="f9630-107">**Fedora 32**</span><span class="sxs-lookup"><span data-stu-id="f9630-107">**Fedora 32**</span></span>

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/32/prod.repo
```

<span data-ttu-id="f9630-108">**Fedora 33**</span><span class="sxs-lookup"><span data-stu-id="f9630-108">**Fedora 33**</span></span>

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/33/prod.repo
```

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="install-net-core-31"></a><span data-ttu-id="f9630-109">Installieren von .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="f9630-109">Install .NET Core 3.1</span></span>

<span data-ttu-id="f9630-110">Die neueste in den Standardpaketrepositorys für Fedora verfügbare Version von .NET ist .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="f9630-110">The latest version of .NET available in the default package repositories for Fedora is .NET Core 3.1.</span></span>

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="supported-distributions"></a><span data-ttu-id="f9630-111">Unterstützte Distributionen</span><span class="sxs-lookup"><span data-stu-id="f9630-111">Supported distributions</span></span>

<span data-ttu-id="f9630-112">Die folgende Tabelle enthält die derzeit unterstützten .NET-Releases und Versionen von Fedora, unter denen sie unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="f9630-112">The following table is a list of currently supported .NET releases and the versions of Fedora they're supported on.</span></span> <span data-ttu-id="f9630-113">Diese Versionen werden weiterhin unterstützt, bis entweder die Version von [.NET das Ende des Supports](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) oder die Version von [Fedora das Ende ihrer Lebensdauer erreicht](https://fedoraproject.org/wiki/End_of_life).</span><span class="sxs-lookup"><span data-stu-id="f9630-113">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Fedora reaches end-of-life](https://fedoraproject.org/wiki/End_of_life).</span></span>

- <span data-ttu-id="f9630-114">✔️ gibt an, dass die Version von Fedora oder .NET weiterhin unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="f9630-114">A ✔️ indicates that the version of Fedora or .NET is still supported.</span></span>
- <span data-ttu-id="f9630-115">❌ gibt an, dass die Version von Fedora oder .NET in diesem Fedora-Release nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="f9630-115">A ❌ indicates that the version of Fedora or .NET isn't supported on that Fedora release.</span></span>
- <span data-ttu-id="f9630-116">Wenn sowohl eine Version von Fedora als auch eine Version von .NET mit ✔️ markiert sind, wird diese Kombination aus Betriebssystem und .NET unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f9630-116">When both a version of Fedora and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="f9630-117">.NET-Version</span><span class="sxs-lookup"><span data-stu-id="f9630-117">.NET Version</span></span>  | <span data-ttu-id="f9630-118">Fedora 33 ✔️</span><span class="sxs-lookup"><span data-stu-id="f9630-118">Fedora 33 ✔️</span></span> | <span data-ttu-id="f9630-119">32 ✔️</span><span class="sxs-lookup"><span data-stu-id="f9630-119">32 ✔️</span></span> | <span data-ttu-id="f9630-120">31 ❌</span><span class="sxs-lookup"><span data-stu-id="f9630-120">31 ❌</span></span> | <span data-ttu-id="f9630-121">30 ❌</span><span class="sxs-lookup"><span data-stu-id="f9630-121">30 ❌</span></span> | <span data-ttu-id="f9630-122">29 ❌</span><span class="sxs-lookup"><span data-stu-id="f9630-122">29 ❌</span></span> | <span data-ttu-id="f9630-123">28 ❌</span><span class="sxs-lookup"><span data-stu-id="f9630-123">28 ❌</span></span> | <span data-ttu-id="f9630-124">27 ❌</span><span class="sxs-lookup"><span data-stu-id="f9630-124">27 ❌</span></span> |
| ------------  | ---------: | --: | --: | --: | --: | --: | --: |
| <span data-ttu-id="f9630-125">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="f9630-125">.NET 5.0</span></span>      | <span data-ttu-id="f9630-126">✔️</span><span class="sxs-lookup"><span data-stu-id="f9630-126">✔️</span></span>        | <span data-ttu-id="f9630-127">✔️</span><span class="sxs-lookup"><span data-stu-id="f9630-127">✔️</span></span> | ❌|❌ |❌ |❌  |❌ |
| <span data-ttu-id="f9630-128">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="f9630-128">.NET Core 3.1</span></span> | <span data-ttu-id="f9630-129">✔️</span><span class="sxs-lookup"><span data-stu-id="f9630-129">✔️</span></span>        | <span data-ttu-id="f9630-130">✔️</span><span class="sxs-lookup"><span data-stu-id="f9630-130">✔️</span></span> | <span data-ttu-id="f9630-131">✔️</span><span class="sxs-lookup"><span data-stu-id="f9630-131">✔️</span></span>|<span data-ttu-id="f9630-132">✔️</span><span class="sxs-lookup"><span data-stu-id="f9630-132">✔️</span></span> |<span data-ttu-id="f9630-133">✔️</span><span class="sxs-lookup"><span data-stu-id="f9630-133">✔️</span></span> |❌  |❌ |
| <span data-ttu-id="f9630-134">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="f9630-134">.NET Core 2.1</span></span> | <span data-ttu-id="f9630-135">✔️</span><span class="sxs-lookup"><span data-stu-id="f9630-135">✔️</span></span>        | <span data-ttu-id="f9630-136">✔️</span><span class="sxs-lookup"><span data-stu-id="f9630-136">✔️</span></span> | <span data-ttu-id="f9630-137">✔️</span><span class="sxs-lookup"><span data-stu-id="f9630-137">✔️</span></span>|<span data-ttu-id="f9630-138">✔️</span><span class="sxs-lookup"><span data-stu-id="f9630-138">✔️</span></span> |<span data-ttu-id="f9630-139">✔️</span><span class="sxs-lookup"><span data-stu-id="f9630-139">✔️</span></span> |<span data-ttu-id="f9630-140">✔️</span><span class="sxs-lookup"><span data-stu-id="f9630-140">✔️</span></span>  |<span data-ttu-id="f9630-141">✔️</span><span class="sxs-lookup"><span data-stu-id="f9630-141">✔️</span></span> |

<span data-ttu-id="f9630-142">Die folgenden Versionen von .NET werden nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f9630-142">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="f9630-143">Die Downloads dafür bleiben weiterhin veröffentlicht:</span><span class="sxs-lookup"><span data-stu-id="f9630-143">The downloads for these still remain published:</span></span>

- <span data-ttu-id="f9630-144">3.0</span><span class="sxs-lookup"><span data-stu-id="f9630-144">3.0</span></span>
- <span data-ttu-id="f9630-145">2.2</span><span class="sxs-lookup"><span data-stu-id="f9630-145">2.2</span></span>
- <span data-ttu-id="f9630-146">2.0</span><span class="sxs-lookup"><span data-stu-id="f9630-146">2.0</span></span>

## <a name="remove-preview-versions"></a><span data-ttu-id="f9630-147">Entfernen von Vorschauversionen</span><span class="sxs-lookup"><span data-stu-id="f9630-147">Remove preview versions</span></span>

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="dependencies"></a><span data-ttu-id="f9630-148">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="f9630-148">Dependencies</span></span>

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="install-on-older-distributions"></a><span data-ttu-id="f9630-149">Installieren unter älteren Distributionen</span><span class="sxs-lookup"><span data-stu-id="f9630-149">Install on older distributions</span></span>

<span data-ttu-id="f9630-150">Bei älteren Versionen von Fedora ist .NET Core nicht in den Standardpaketrepositorys enthalten.</span><span class="sxs-lookup"><span data-stu-id="f9630-150">Older versions of Fedora don't contain .NET Core in the default package repositories.</span></span> <span data-ttu-id="f9630-151">Sie können .NET mit [Snap](linux-snap.md), über das [_dotnet-install.sh_-Skript](linux-scripted-manual.md#scripted-install) oder über das Microsoft-Repository für die Installation von .NET installieren:</span><span class="sxs-lookup"><span data-stu-id="f9630-151">You can install .NET with [snap](linux-snap.md), through the [_dotnet-install.sh_ script](linux-scripted-manual.md#scripted-install), or use Microsoft's repository to install .NET:</span></span>

01. <span data-ttu-id="f9630-152">Fügen Sie zunächst den Microsoft-Signaturschlüssel zur Liste der vertrauenswürdigen Schlüssel hinzu.</span><span class="sxs-lookup"><span data-stu-id="f9630-152">First, add the Microsoft signing key to your list of trusted keys.</span></span>

    ```bash
    sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
    ```

02. <span data-ttu-id="f9630-153">Fügen Sie als Nächstes das Microsoft-Paketrepository hinzu.</span><span class="sxs-lookup"><span data-stu-id="f9630-153">Next, add the Microsoft package repository.</span></span> <span data-ttu-id="f9630-154">Die Quelle des Repositorys basiert auf Ihrer Fedora-Version.</span><span class="sxs-lookup"><span data-stu-id="f9630-154">The source of the repository is based on your version of Fedora.</span></span>

    | <span data-ttu-id="f9630-155">Fedora-Version</span><span class="sxs-lookup"><span data-stu-id="f9630-155">Fedora Version</span></span> | <span data-ttu-id="f9630-156">Paketrepository</span><span class="sxs-lookup"><span data-stu-id="f9630-156">Package repository</span></span> |
    | -------------- | ------- |
    | <span data-ttu-id="f9630-157">31</span><span class="sxs-lookup"><span data-stu-id="f9630-157">31</span></span>             | `https://packages.microsoft.com/config/fedora/31/prod.repo` |
    | <span data-ttu-id="f9630-158">30</span><span class="sxs-lookup"><span data-stu-id="f9630-158">30</span></span>             | `https://packages.microsoft.com/config/fedora/30/prod.repo` |
    | <span data-ttu-id="f9630-159">29</span><span class="sxs-lookup"><span data-stu-id="f9630-159">29</span></span>             | `https://packages.microsoft.com/config/fedora/29/prod.repo` |
    | <span data-ttu-id="f9630-160">28</span><span class="sxs-lookup"><span data-stu-id="f9630-160">28</span></span>             | `https://packages.microsoft.com/config/fedora/28/prod.repo` |
    | <span data-ttu-id="f9630-161">27</span><span class="sxs-lookup"><span data-stu-id="f9630-161">27</span></span>             | `https://packages.microsoft.com/config/fedora/27/prod.repo` |

    ```bash
    sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/31/prod.repo
    ```

[!INCLUDE [linux-dnf-install-31](./includes/linux-install-31-dnf.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="f9630-162">Installieren anderer Versionen</span><span class="sxs-lookup"><span data-stu-id="f9630-162">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="f9630-163">Problembehandlung des Paket-Managers</span><span class="sxs-lookup"><span data-stu-id="f9630-163">Troubleshoot the package manager</span></span>

<span data-ttu-id="f9630-164">Dieser Abschnitt enthält Informationen zu häufigen Fehlern, die bei der Verwendung des Paket-Managers zur Installation von .NET oder .NET Core auftreten können.</span><span class="sxs-lookup"><span data-stu-id="f9630-164">This section provides information on common errors you may get while using the package manager to install .NET or .NET Core.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="f9630-165">Paket konnte nicht gefunden werden</span><span class="sxs-lookup"><span data-stu-id="f9630-165">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="failed-to-fetch"></a><span data-ttu-id="f9630-166">Fehler beim Abrufen</span><span class="sxs-lookup"><span data-stu-id="f9630-166">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="next-steps"></a><span data-ttu-id="f9630-167">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f9630-167">Next steps</span></span>

- [<span data-ttu-id="f9630-168">Aktivieren der Vervollständigung mit der TAB-TASTE für die .NET-CLI</span><span class="sxs-lookup"><span data-stu-id="f9630-168">How to enable TAB completion for the .NET CLI</span></span>](../tools/enable-tab-autocomplete.md)
- [<span data-ttu-id="f9630-169">Tutorial: Erstellen einer Konsolenanwendung mit dem .NET SDK in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f9630-169">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
