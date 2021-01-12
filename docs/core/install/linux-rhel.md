---
title: 'Installieren von .NET unter RHEL: .NET'
description: In diesem Artikel werden verschiedene Möglichkeiten veranschaulicht, das .NET SDK und die NET-Runtime für RHEL zu installieren.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: d585017919507a8fdcbb24778a0ff3ab3d9049c2
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970797"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-rhel"></a><span data-ttu-id="9ce47-103">Installieren des .NET SDK oder der .NET-Runtime unter RHEL</span><span class="sxs-lookup"><span data-stu-id="9ce47-103">Install the .NET SDK or the .NET Runtime on RHEL</span></span>

<span data-ttu-id="9ce47-104">.NET wird unter RHEL unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9ce47-104">.NET is supported on RHEL.</span></span> <span data-ttu-id="9ce47-105">In diesem Artikel wird beschrieben, wie Sie .NET unter RHEL installieren.</span><span class="sxs-lookup"><span data-stu-id="9ce47-105">This article describes how to install .NET on RHEL.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="9ce47-106">Registrieren Ihres Red Hat-Abonnements</span><span class="sxs-lookup"><span data-stu-id="9ce47-106">Register your Red Hat subscription</span></span>

<span data-ttu-id="9ce47-107">Sie müssen sich zuerst mit dem Red Hat-Abonnement-Manager registrieren, um .NET von Red Hat unter RHEL installieren zu können.</span><span class="sxs-lookup"><span data-stu-id="9ce47-107">To install .NET from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="9ce47-108">Wenn Sie dies auf Ihrem System noch nicht getan haben oder Sie unsicher sind, finden Sie weitere Informationen in der [Red Hat-Produktdokumentation für .NET](https://access.redhat.com/documentation/net/5.0/).</span><span class="sxs-lookup"><span data-stu-id="9ce47-108">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET](https://access.redhat.com/documentation/net/5.0/).</span></span>

## <a name="supported-distributions"></a><span data-ttu-id="9ce47-109">Unterstützte Distributionen</span><span class="sxs-lookup"><span data-stu-id="9ce47-109">Supported distributions</span></span>

<span data-ttu-id="9ce47-110">Die folgende Tabelle enthält die derzeit unter RHEL 7 und RHEL 8 unterstützten .NET-Releases.</span><span class="sxs-lookup"><span data-stu-id="9ce47-110">The following table is a list of currently supported .NET releases on both RHEL 7 and RHEL 8.</span></span> <span data-ttu-id="9ce47-111">Diese Versionen werden weiterhin unterstützt, bis entweder die Version von [.NET das Ende des Supports](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) erreicht oder die Version von RHEL nicht mehr unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="9ce47-111">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of RHEL is no longer supported.</span></span>

- <span data-ttu-id="9ce47-112">✔️ gibt an, dass die Version von RHEL oder .NET weiterhin unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="9ce47-112">A ✔️ indicates that the version of RHEL or .NET is still supported.</span></span>
- <span data-ttu-id="9ce47-113">❌ gibt an, dass die Version von RHEL oder .NET in diesem RHEL-Release nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="9ce47-113">A ❌ indicates that the version of RHEL or .NET isn't supported on that RHEL release.</span></span>
- <span data-ttu-id="9ce47-114">Wenn sowohl eine Version von RHEL als auch eine Version von .NET mit ✔️ markiert sind, wird diese Kombination aus Betriebssystem und .NET unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9ce47-114">When both a version of RHEL and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="9ce47-115">RHEL</span><span class="sxs-lookup"><span data-stu-id="9ce47-115">RHEL</span></span>                     | <span data-ttu-id="9ce47-116">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="9ce47-116">.NET Core 2.1</span></span> | <span data-ttu-id="9ce47-117">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="9ce47-117">.NET Core 3.1</span></span> | <span data-ttu-id="9ce47-118">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="9ce47-118">.NET 5.0</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="9ce47-119">✔️ [8](#rhel-8-)</span><span class="sxs-lookup"><span data-stu-id="9ce47-119">✔️ [8](#rhel-8-)</span></span>        | <span data-ttu-id="9ce47-120">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="9ce47-120">✔️ 2.1</span></span>        | <span data-ttu-id="9ce47-121">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="9ce47-121">✔️ 3.1</span></span>        | <span data-ttu-id="9ce47-122">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="9ce47-122">✔️ 5.0</span></span> |
| <span data-ttu-id="9ce47-123">✔️ [7](#rhel-7--net-50)</span><span class="sxs-lookup"><span data-stu-id="9ce47-123">✔️ [7](#rhel-7--net-50)</span></span> | <span data-ttu-id="9ce47-124">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="9ce47-124">✔️ 2.1</span></span>        | <span data-ttu-id="9ce47-125">✔️ [3.1](#rhel-7--net-core-31)</span><span class="sxs-lookup"><span data-stu-id="9ce47-125">✔️ [3.1](#rhel-7--net-core-31)</span></span>        | <span data-ttu-id="9ce47-126">✔️ [5.0](#rhel-7--net-50)</span><span class="sxs-lookup"><span data-stu-id="9ce47-126">✔️ [5.0](#rhel-7--net-50)</span></span> |

<span data-ttu-id="9ce47-127">Die folgenden Versionen von .NET werden nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9ce47-127">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="9ce47-128">Die Downloads dafür bleiben weiterhin veröffentlicht:</span><span class="sxs-lookup"><span data-stu-id="9ce47-128">The downloads for these still remain published:</span></span>

- <span data-ttu-id="9ce47-129">3.0</span><span class="sxs-lookup"><span data-stu-id="9ce47-129">3.0</span></span>
- <span data-ttu-id="9ce47-130">2.2</span><span class="sxs-lookup"><span data-stu-id="9ce47-130">2.2</span></span>
- <span data-ttu-id="9ce47-131">2.0</span><span class="sxs-lookup"><span data-stu-id="9ce47-131">2.0</span></span>

## <a name="remove-preview-versions"></a><span data-ttu-id="9ce47-132">Entfernen von Vorschauversionen</span><span class="sxs-lookup"><span data-stu-id="9ce47-132">Remove preview versions</span></span>

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="rhel-8-"></a><span data-ttu-id="9ce47-133">RHEL 8 ✔️</span><span class="sxs-lookup"><span data-stu-id="9ce47-133">RHEL 8 ✔️</span></span>

<span data-ttu-id="9ce47-134">.NET ist in den AppStream-Repositorys für RHEL 8 enthalten.</span><span class="sxs-lookup"><span data-stu-id="9ce47-134">.NET is included in the AppStream repositories for RHEL 8.</span></span>

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="rhel-7--net-50"></a><span data-ttu-id="9ce47-135">RHEL 7 ✔️ .NET 5.0</span><span class="sxs-lookup"><span data-stu-id="9ce47-135">RHEL 7 ✔️ .NET 5.0</span></span>

<span data-ttu-id="9ce47-136">Mit dem folgenden Befehl wird das Paket `scl-utils` installiert:</span><span class="sxs-lookup"><span data-stu-id="9ce47-136">The following command installs the `scl-utils` package:</span></span>

```bash
sudo yum install scl-utils
```

### <a name="install-the-sdk"></a><span data-ttu-id="9ce47-137">Installieren des SDKs</span><span class="sxs-lookup"><span data-stu-id="9ce47-137">Install the SDK</span></span>

<span data-ttu-id="9ce47-138">Das .NET SDK ermöglicht Ihnen die Entwicklung von Apps mit .NET.</span><span class="sxs-lookup"><span data-stu-id="9ce47-138">The .NET SDK allows you to develop apps with .NET .</span></span> <span data-ttu-id="9ce47-139">Wenn Sie das .NET SDK installieren, müssen Sie die entsprechende Runtime nicht installieren.</span><span class="sxs-lookup"><span data-stu-id="9ce47-139">If you install the .NET SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="9ce47-140">Führen Sie die folgenden Befehle aus, um das .NET SDK zu installieren:</span><span class="sxs-lookup"><span data-stu-id="9ce47-140">To install .NET SDK, run the following commands:</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet50 -y
scl enable rh-dotnet50 bash
```

<span data-ttu-id="9ce47-141">Red Hat empfiehlt nicht die dauerhafte Aktivierung von `rh-dotnet50`, da dies andere Programme beeinträchtigen könnte.</span><span class="sxs-lookup"><span data-stu-id="9ce47-141">Red Hat does not recommend permanently enabling `rh-dotnet50` because it may affect other programs.</span></span> <span data-ttu-id="9ce47-142">Wenn Sie `rh-dotnet` dauerhaft aktivieren möchten, fügen Sie der Datei _~/.bashrc_ die folgende Zeile hinzu.</span><span class="sxs-lookup"><span data-stu-id="9ce47-142">If you want to enable `rh-dotnet` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet50
```

### <a name="install-the-runtime"></a><span data-ttu-id="9ce47-143">Installieren der Runtime</span><span class="sxs-lookup"><span data-stu-id="9ce47-143">Install the runtime</span></span>

<span data-ttu-id="9ce47-144">Die .NET-Runtime ermöglicht Ihnen die Ausführung von Apps, die mit .NET erstellt wurden und die Runtime nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="9ce47-144">The .NET Runtime allows you to run apps that were made with .NET that didn't include the runtime.</span></span> <span data-ttu-id="9ce47-145">Die folgenden Befehle installieren die ASP.NET Core-Runtime, die die kompatibelste Runtime für .NET Core ist.</span><span class="sxs-lookup"><span data-stu-id="9ce47-145">The commands below install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="9ce47-146">Führen Sie in Ihrem Terminal die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="9ce47-146">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet50-aspnetcore-runtime-5.0 -y
scl enable rh-dotnet50 bash
```

<span data-ttu-id="9ce47-147">Red Hat empfiehlt nicht die dauerhafte Aktivierung von `rh-dotnet50`, da dies andere Programme beeinträchtigen könnte.</span><span class="sxs-lookup"><span data-stu-id="9ce47-147">Red Hat does not recommend permanently enabling `rh-dotnet50` because it may affect other programs.</span></span> <span data-ttu-id="9ce47-148">Wenn Sie `rh-dotnet50` dauerhaft aktivieren möchten, fügen Sie der Datei _~/.bashrc_ die folgende Zeile hinzu.</span><span class="sxs-lookup"><span data-stu-id="9ce47-148">If you want to enable `rh-dotnet50` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet50
```

<span data-ttu-id="9ce47-149">Als Alternative zur ASP.NET Core-Runtime können Sie die .NET-Runtime installieren, die keine ASP.NET Core-Unterstützung bietet. Ersetzen Sie hierzu im obigen Befehl `rh-dotnet50-aspnetcore-runtime-5.0` durch `rh-dotnet50-dotnet-runtime-5.0`.</span><span class="sxs-lookup"><span data-stu-id="9ce47-149">As an alternative to the ASP.NET Core Runtime, you can install the .NET Runtime that doesn't include ASP.NET Core support: replace `rh-dotnet50-aspnetcore-runtime-5.0` in the commands above with `rh-dotnet50-dotnet-runtime-5.0`.</span></span>

## <a name="rhel-7--net-core-31"></a><span data-ttu-id="9ce47-150">RHEL 7 ✔️ .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="9ce47-150">RHEL 7 ✔️ .NET Core 3.1</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

<span data-ttu-id="9ce47-151">Mit dem folgenden Befehl wird das Paket `scl-utils` installiert:</span><span class="sxs-lookup"><span data-stu-id="9ce47-151">The following command installs the `scl-utils` package:</span></span>

```bash
sudo yum install scl-utils
```

### <a name="install-the-sdk"></a><span data-ttu-id="9ce47-152">Installieren des SDKs</span><span class="sxs-lookup"><span data-stu-id="9ce47-152">Install the SDK</span></span>

<span data-ttu-id="9ce47-153">Das .NET Core SDK ermöglicht Ihnen die Entwicklung von Apps mit .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9ce47-153">.NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="9ce47-154">Wenn Sie das .NET Core SDK installieren, müssen Sie die entsprechende Runtime nicht installieren.</span><span class="sxs-lookup"><span data-stu-id="9ce47-154">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="9ce47-155">Führen Sie die folgenden Befehle aus, um das .NET Core SDK zu installieren:</span><span class="sxs-lookup"><span data-stu-id="9ce47-155">To install .NET Core SDK, run the following commands:</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31 -y
scl enable rh-dotnet31 bash
```

<span data-ttu-id="9ce47-156">Red Hat empfiehlt nicht die dauerhafte Aktivierung von `rh-dotnet31`, da dies andere Programme beeinträchtigen könnte.</span><span class="sxs-lookup"><span data-stu-id="9ce47-156">Red Hat does not recommend permanently enabling `rh-dotnet31` because it may affect other programs.</span></span> <span data-ttu-id="9ce47-157">So enthält beispielsweise `rh-dotnet31` eine Version von `libcurl`, die sich von der Basisversion von RHEL unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="9ce47-157">For example, `rh-dotnet31` includes a version of `libcurl` that differs from the base RHEL version.</span></span> <span data-ttu-id="9ce47-158">Dies kann zu Problemen in Programmen führen, die keine andere Version von `libcurl` erwarten.</span><span class="sxs-lookup"><span data-stu-id="9ce47-158">This may lead to issues in programs that do not expect a different version of `libcurl`.</span></span> <span data-ttu-id="9ce47-159">Wenn Sie `rh-dotnet` dauerhaft aktivieren möchten, fügen Sie der Datei _~/.bashrc_ die folgende Zeile hinzu.</span><span class="sxs-lookup"><span data-stu-id="9ce47-159">If you want to enable `rh-dotnet` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet31
```

### <a name="install-the-runtime"></a><span data-ttu-id="9ce47-160">Installieren der Runtime</span><span class="sxs-lookup"><span data-stu-id="9ce47-160">Install the runtime</span></span>

<span data-ttu-id="9ce47-161">Die .NET Core-Runtime ermöglicht Ihnen die Ausführung von Apps, die mit .NET Core erstellt wurden und die Runtime nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="9ce47-161">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="9ce47-162">Die folgenden Befehle installieren die ASP.NET Core-Runtime, die die kompatibelste Runtime für .NET Core ist.</span><span class="sxs-lookup"><span data-stu-id="9ce47-162">The commands below install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="9ce47-163">Führen Sie in Ihrem Terminal die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="9ce47-163">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31-aspnetcore-runtime-3.1 -y
scl enable rh-dotnet31 bash
```

<span data-ttu-id="9ce47-164">Red Hat empfiehlt nicht die dauerhafte Aktivierung von `rh-dotnet31`, da dies andere Programme beeinträchtigen könnte.</span><span class="sxs-lookup"><span data-stu-id="9ce47-164">Red Hat does not recommend permanently enabling `rh-dotnet31` because it may affect other programs.</span></span> <span data-ttu-id="9ce47-165">So enthält beispielsweise `rh-dotnet31` eine Version von `libcurl`, die sich von der Basisversion von RHEL unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="9ce47-165">For example, `rh-dotnet31` includes a version of `libcurl` that differs from the base RHEL version.</span></span> <span data-ttu-id="9ce47-166">Dies kann zu Problemen in Programmen führen, die keine andere Version von `libcurl` erwarten.</span><span class="sxs-lookup"><span data-stu-id="9ce47-166">This may lead to issues in programs that do not expect a different version of `libcurl`.</span></span> <span data-ttu-id="9ce47-167">Wenn Sie `rh-dotnet31` dauerhaft aktivieren möchten, fügen Sie der Datei _~/.bashrc_ die folgende Zeile hinzu.</span><span class="sxs-lookup"><span data-stu-id="9ce47-167">If you want to enable `rh-dotnet31` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet31
```

<span data-ttu-id="9ce47-168">Als Alternative zur ASP.NET Core-Runtime können Sie die .NET Core-Runtime installieren, die keine ASP.NET Core-Unterstützung bietet. Ersetzen Sie im obigen Befehl `rh-dotnet31-aspnetcore-runtime-3.1` durch `rh-dotnet31-dotnet-runtime-3.1`.</span><span class="sxs-lookup"><span data-stu-id="9ce47-168">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime that doesn't include ASP.NET Core support: replace `rh-dotnet31-aspnetcore-runtime-3.1` in the commands above with `rh-dotnet31-dotnet-runtime-3.1`.</span></span>

## <a name="dependencies"></a><span data-ttu-id="9ce47-169">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="9ce47-169">Dependencies</span></span>

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="9ce47-170">Installieren anderer Versionen</span><span class="sxs-lookup"><span data-stu-id="9ce47-170">How to install other versions</span></span>

<span data-ttu-id="9ce47-171">Konsultieren Sie die [Red Hat-Dokumentation zu .NET](https://access.redhat.com/documentation/net/5.0/) hinsichtlich der Schritte, die zur Installation anderer Releases von .NET erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="9ce47-171">Consult the [Red Hat documentation for .NET](https://access.redhat.com/documentation/net/5.0/) on the steps required to install other releases of .NET.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9ce47-172">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="9ce47-172">Next steps</span></span>

- [<span data-ttu-id="9ce47-173">Aktivieren der Vervollständigung mit der TAB-TASTE für die .NET-CLI</span><span class="sxs-lookup"><span data-stu-id="9ce47-173">How to enable TAB completion for the .NET CLI</span></span>](../tools/enable-tab-autocomplete.md)
- [<span data-ttu-id="9ce47-174">Tutorial: Erstellen einer Konsolenanwendung mit dem .NET SDK in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="9ce47-174">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
