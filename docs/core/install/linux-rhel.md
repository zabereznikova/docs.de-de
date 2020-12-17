---
title: 'Installieren von .NET unter RHEL: .NET'
description: In diesem Artikel werden verschiedene Möglichkeiten veranschaulicht, das .NET SDK und die NET-Runtime für RHEL zu installieren.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 0b6138185bfd3e2f50c1b31e82779165715a5b6e
ms.sourcegitcommit: 45c7148f2483db2501c1aa696ab6ed2ed8cb71b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/08/2020
ms.locfileid: "96851639"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-rhel"></a><span data-ttu-id="2e635-103">Installieren des .NET SDK oder der .NET-Runtime unter RHEL</span><span class="sxs-lookup"><span data-stu-id="2e635-103">Install the .NET SDK or the .NET Runtime on RHEL</span></span>

<span data-ttu-id="2e635-104">.NET wird unter RHEL unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2e635-104">.NET is supported on RHEL.</span></span> <span data-ttu-id="2e635-105">In diesem Artikel wird beschrieben, wie Sie .NET unter RHEL installieren.</span><span class="sxs-lookup"><span data-stu-id="2e635-105">This article describes how to install .NET on RHEL.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="2e635-106">Registrieren Ihres Red Hat-Abonnements</span><span class="sxs-lookup"><span data-stu-id="2e635-106">Register your Red Hat subscription</span></span>

<span data-ttu-id="2e635-107">Sie müssen sich zuerst mit dem Red Hat-Abonnement-Manager registrieren, um .NET von Red Hat unter RHEL installieren zu können.</span><span class="sxs-lookup"><span data-stu-id="2e635-107">To install .NET from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="2e635-108">Wenn Sie dies auf Ihrem System noch nicht getan haben oder Sie unsicher sind, finden Sie weitere Informationen in der [Red Hat-Produktdokumentation für .NET](https://access.redhat.com/documentation/net/5.0/).</span><span class="sxs-lookup"><span data-stu-id="2e635-108">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET](https://access.redhat.com/documentation/net/5.0/).</span></span>

## <a name="supported-distributions"></a><span data-ttu-id="2e635-109">Unterstützte Distributionen</span><span class="sxs-lookup"><span data-stu-id="2e635-109">Supported distributions</span></span>

<span data-ttu-id="2e635-110">Die folgende Tabelle enthält die derzeit unter RHEL 7 und RHEL 8 unterstützten .NET-Releases.</span><span class="sxs-lookup"><span data-stu-id="2e635-110">The following table is a list of currently supported .NET releases on both RHEL 7 and RHEL 8.</span></span> <span data-ttu-id="2e635-111">Diese Versionen werden weiterhin unterstützt, bis entweder die Version von [.NET das Ende des Supports](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) erreicht oder die Version von RHEL nicht mehr unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="2e635-111">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of RHEL is no longer supported.</span></span>

- <span data-ttu-id="2e635-112">✔️ gibt an, dass die Version von RHEL oder .NET weiterhin unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="2e635-112">A ✔️ indicates that the version of RHEL or .NET is still supported.</span></span>
- <span data-ttu-id="2e635-113">❌ gibt an, dass die Version von RHEL oder .NET in diesem RHEL-Release nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="2e635-113">A ❌ indicates that the version of RHEL or .NET isn't supported on that RHEL release.</span></span>
- <span data-ttu-id="2e635-114">Wenn sowohl eine Version von RHEL als auch eine Version von .NET mit ✔️ markiert sind, wird diese Kombination aus Betriebssystem und .NET unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2e635-114">When both a version of RHEL and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="2e635-115">RHEL</span><span class="sxs-lookup"><span data-stu-id="2e635-115">RHEL</span></span>                     | <span data-ttu-id="2e635-116">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="2e635-116">.NET Core 2.1</span></span> | <span data-ttu-id="2e635-117">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="2e635-117">.NET Core 3.1</span></span> | <span data-ttu-id="2e635-118">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="2e635-118">.NET 5.0</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="2e635-119">✔️ [8](#rhel-8-)</span><span class="sxs-lookup"><span data-stu-id="2e635-119">✔️ [8](#rhel-8-)</span></span>        | <span data-ttu-id="2e635-120">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="2e635-120">✔️ 2.1</span></span>        | <span data-ttu-id="2e635-121">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="2e635-121">✔️ 3.1</span></span>        | <span data-ttu-id="2e635-122">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="2e635-122">✔️ 5.0</span></span> |
| <span data-ttu-id="2e635-123">✔️ [7](#rhel-7--net-50)</span><span class="sxs-lookup"><span data-stu-id="2e635-123">✔️ [7](#rhel-7--net-50)</span></span> | <span data-ttu-id="2e635-124">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="2e635-124">✔️ 2.1</span></span>        | <span data-ttu-id="2e635-125">✔️ [3.1](#rhel-7--net-core-31)</span><span class="sxs-lookup"><span data-stu-id="2e635-125">✔️ [3.1](#rhel-7--net-core-31)</span></span>        | <span data-ttu-id="2e635-126">✔️ [5.0](#rhel-7--net-50)</span><span class="sxs-lookup"><span data-stu-id="2e635-126">✔️ [5.0](#rhel-7--net-50)</span></span> |

<span data-ttu-id="2e635-127">Die folgenden Versionen von .NET werden nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2e635-127">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="2e635-128">Die Downloads dafür bleiben weiterhin veröffentlicht:</span><span class="sxs-lookup"><span data-stu-id="2e635-128">The downloads for these still remain published:</span></span>

- <span data-ttu-id="2e635-129">3.0</span><span class="sxs-lookup"><span data-stu-id="2e635-129">3.0</span></span>
- <span data-ttu-id="2e635-130">2.2</span><span class="sxs-lookup"><span data-stu-id="2e635-130">2.2</span></span>
- <span data-ttu-id="2e635-131">2.0</span><span class="sxs-lookup"><span data-stu-id="2e635-131">2.0</span></span>

## <a name="remove-preview-versions"></a><span data-ttu-id="2e635-132">Entfernen von Vorschauversionen</span><span class="sxs-lookup"><span data-stu-id="2e635-132">Remove preview versions</span></span>

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="2e635-133">Installieren anderer Versionen</span><span class="sxs-lookup"><span data-stu-id="2e635-133">How to install other versions</span></span>

<span data-ttu-id="2e635-134">Konsultieren Sie die [Red Hat-Dokumentation zu .NET](https://access.redhat.com/documentation/net/5.0/) hinsichtlich der Schritte, die zur Installation anderer Releases von .NET erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="2e635-134">Consult the [Red Hat documentation for .NET](https://access.redhat.com/documentation/net/5.0/) on the steps required to install other releases of .NET.</span></span>

## <a name="rhel-8-"></a><span data-ttu-id="2e635-135">RHEL 8 ✔️</span><span class="sxs-lookup"><span data-stu-id="2e635-135">RHEL 8 ✔️</span></span>

<span data-ttu-id="2e635-136">.NET ist in den AppStream-Repositorys für RHEL 8 enthalten.</span><span class="sxs-lookup"><span data-stu-id="2e635-136">.NET is included in the AppStream repositories for RHEL 8.</span></span>

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="rhel-7--net-50"></a><span data-ttu-id="2e635-137">RHEL 7 ✔️ .NET 5.0</span><span class="sxs-lookup"><span data-stu-id="2e635-137">RHEL 7 ✔️ .NET 5.0</span></span>

<span data-ttu-id="2e635-138">Mit dem folgenden Befehl wird das Paket `scl-utils` installiert:</span><span class="sxs-lookup"><span data-stu-id="2e635-138">The following command installs the `scl-utils` package:</span></span>

```bash
sudo yum install scl-utils
```

### <a name="install-the-sdk"></a><span data-ttu-id="2e635-139">Installieren des SDKs</span><span class="sxs-lookup"><span data-stu-id="2e635-139">Install the SDK</span></span>

<span data-ttu-id="2e635-140">Das .NET SDK ermöglicht Ihnen die Entwicklung von Apps mit .NET.</span><span class="sxs-lookup"><span data-stu-id="2e635-140">The .NET SDK allows you to develop apps with .NET .</span></span> <span data-ttu-id="2e635-141">Wenn Sie das .NET SDK installieren, müssen Sie die entsprechende Runtime nicht installieren.</span><span class="sxs-lookup"><span data-stu-id="2e635-141">If you install the .NET SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="2e635-142">Führen Sie die folgenden Befehle aus, um das .NET SDK zu installieren:</span><span class="sxs-lookup"><span data-stu-id="2e635-142">To install .NET SDK, run the following commands:</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet50 -y
scl enable rh-dotnet50 bash
```

<span data-ttu-id="2e635-143">Red Hat empfiehlt nicht die dauerhafte Aktivierung von `rh-dotnet50`, da dies andere Programme beeinträchtigen könnte.</span><span class="sxs-lookup"><span data-stu-id="2e635-143">Red Hat does not recommend permanently enabling `rh-dotnet50` because it may affect other programs.</span></span> <span data-ttu-id="2e635-144">Wenn Sie `rh-dotnet` dauerhaft aktivieren möchten, fügen Sie der Datei _~/.bashrc_ die folgende Zeile hinzu.</span><span class="sxs-lookup"><span data-stu-id="2e635-144">If you want to enable `rh-dotnet` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet50
```

### <a name="install-the-runtime"></a><span data-ttu-id="2e635-145">Installieren der Runtime</span><span class="sxs-lookup"><span data-stu-id="2e635-145">Install the runtime</span></span>

<span data-ttu-id="2e635-146">Die .NET-Runtime ermöglicht Ihnen die Ausführung von Apps, die mit .NET erstellt wurden und die Runtime nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="2e635-146">The .NET Runtime allows you to run apps that were made with .NET that didn't include the runtime.</span></span> <span data-ttu-id="2e635-147">Die folgenden Befehle installieren die ASP.NET Core-Runtime, die die kompatibelste Runtime für .NET Core ist.</span><span class="sxs-lookup"><span data-stu-id="2e635-147">The commands below install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="2e635-148">Führen Sie in Ihrem Terminal die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="2e635-148">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet50-aspnetcore-runtime-5.0 -y
scl enable rh-dotnet50 bash
```

<span data-ttu-id="2e635-149">Red Hat empfiehlt nicht die dauerhafte Aktivierung von `rh-dotnet50`, da dies andere Programme beeinträchtigen könnte.</span><span class="sxs-lookup"><span data-stu-id="2e635-149">Red Hat does not recommend permanently enabling `rh-dotnet50` because it may affect other programs.</span></span> <span data-ttu-id="2e635-150">Wenn Sie `rh-dotnet50` dauerhaft aktivieren möchten, fügen Sie der Datei _~/.bashrc_ die folgende Zeile hinzu.</span><span class="sxs-lookup"><span data-stu-id="2e635-150">If you want to enable `rh-dotnet50` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet50
```

<span data-ttu-id="2e635-151">Als Alternative zur ASP.NET Core-Runtime können Sie die .NET-Runtime installieren, die keine ASP.NET Core-Unterstützung bietet. Ersetzen Sie hierzu im obigen Befehl `rh-dotnet50-aspnetcore-runtime-5.0` durch `rh-dotnet50-dotnet-runtime-5.0`.</span><span class="sxs-lookup"><span data-stu-id="2e635-151">As an alternative to the ASP.NET Core Runtime, you can install the .NET Runtime that doesn't include ASP.NET Core support: replace `rh-dotnet50-aspnetcore-runtime-5.0` in the commands above with `rh-dotnet50-dotnet-runtime-5.0`.</span></span>

## <a name="rhel-7--net-core-31"></a><span data-ttu-id="2e635-152">RHEL 7 ✔️ .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="2e635-152">RHEL 7 ✔️ .NET Core 3.1</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

<span data-ttu-id="2e635-153">Mit dem folgenden Befehl wird das Paket `scl-utils` installiert:</span><span class="sxs-lookup"><span data-stu-id="2e635-153">The following command installs the `scl-utils` package:</span></span>

```bash
sudo yum install scl-utils
```

### <a name="install-the-sdk"></a><span data-ttu-id="2e635-154">Installieren des SDKs</span><span class="sxs-lookup"><span data-stu-id="2e635-154">Install the SDK</span></span>

<span data-ttu-id="2e635-155">Das .NET Core SDK ermöglicht Ihnen die Entwicklung von Apps mit .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2e635-155">.NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="2e635-156">Wenn Sie das .NET Core SDK installieren, müssen Sie die entsprechende Runtime nicht installieren.</span><span class="sxs-lookup"><span data-stu-id="2e635-156">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="2e635-157">Führen Sie die folgenden Befehle aus, um das .NET Core SDK zu installieren:</span><span class="sxs-lookup"><span data-stu-id="2e635-157">To install .NET Core SDK, run the following commands:</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31 -y
scl enable rh-dotnet31 bash
```

<span data-ttu-id="2e635-158">Red Hat empfiehlt nicht die dauerhafte Aktivierung von `rh-dotnet31`, da dies andere Programme beeinträchtigen könnte.</span><span class="sxs-lookup"><span data-stu-id="2e635-158">Red Hat does not recommend permanently enabling `rh-dotnet31` because it may affect other programs.</span></span> <span data-ttu-id="2e635-159">So enthält beispielsweise `rh-dotnet31` eine Version von `libcurl`, die sich von der Basisversion von RHEL unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="2e635-159">For example, `rh-dotnet31` includes a version of `libcurl` that differs from the base RHEL version.</span></span> <span data-ttu-id="2e635-160">Dies kann zu Problemen in Programmen führen, die keine andere Version von `libcurl` erwarten.</span><span class="sxs-lookup"><span data-stu-id="2e635-160">This may lead to issues in programs that do not expect a different version of `libcurl`.</span></span> <span data-ttu-id="2e635-161">Wenn Sie `rh-dotnet` dauerhaft aktivieren möchten, fügen Sie der Datei _~/.bashrc_ die folgende Zeile hinzu.</span><span class="sxs-lookup"><span data-stu-id="2e635-161">If you want to enable `rh-dotnet` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet31
```

### <a name="install-the-runtime"></a><span data-ttu-id="2e635-162">Installieren der Runtime</span><span class="sxs-lookup"><span data-stu-id="2e635-162">Install the runtime</span></span>

<span data-ttu-id="2e635-163">Die .NET Core-Runtime ermöglicht Ihnen die Ausführung von Apps, die mit .NET Core erstellt wurden und die Runtime nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="2e635-163">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="2e635-164">Die folgenden Befehle installieren die ASP.NET Core-Runtime, die die kompatibelste Runtime für .NET Core ist.</span><span class="sxs-lookup"><span data-stu-id="2e635-164">The commands below install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="2e635-165">Führen Sie in Ihrem Terminal die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="2e635-165">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31-aspnetcore-runtime-3.1 -y
scl enable rh-dotnet31 bash
```

<span data-ttu-id="2e635-166">Red Hat empfiehlt nicht die dauerhafte Aktivierung von `rh-dotnet31`, da dies andere Programme beeinträchtigen könnte.</span><span class="sxs-lookup"><span data-stu-id="2e635-166">Red Hat does not recommend permanently enabling `rh-dotnet31` because it may affect other programs.</span></span> <span data-ttu-id="2e635-167">So enthält beispielsweise `rh-dotnet31` eine Version von `libcurl`, die sich von der Basisversion von RHEL unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="2e635-167">For example, `rh-dotnet31` includes a version of `libcurl` that differs from the base RHEL version.</span></span> <span data-ttu-id="2e635-168">Dies kann zu Problemen in Programmen führen, die keine andere Version von `libcurl` erwarten.</span><span class="sxs-lookup"><span data-stu-id="2e635-168">This may lead to issues in programs that do not expect a different version of `libcurl`.</span></span> <span data-ttu-id="2e635-169">Wenn Sie `rh-dotnet31` dauerhaft aktivieren möchten, fügen Sie der Datei _~/.bashrc_ die folgende Zeile hinzu.</span><span class="sxs-lookup"><span data-stu-id="2e635-169">If you want to enable `rh-dotnet31` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet31
```

<span data-ttu-id="2e635-170">Als Alternative zur ASP.NET Core-Runtime können Sie die .NET Core-Runtime installieren, die keine ASP.NET Core-Unterstützung bietet. Ersetzen Sie im obigen Befehl `rh-dotnet31-aspnetcore-runtime-3.1` durch `rh-dotnet31-dotnet-runtime-3.1`.</span><span class="sxs-lookup"><span data-stu-id="2e635-170">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime that doesn't include ASP.NET Core support: replace `rh-dotnet31-aspnetcore-runtime-3.1` in the commands above with `rh-dotnet31-dotnet-runtime-3.1`.</span></span>

## <a name="snap"></a><span data-ttu-id="2e635-171">Snap</span><span class="sxs-lookup"><span data-stu-id="2e635-171">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="2e635-172">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="2e635-172">Dependencies</span></span>

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="2e635-173">Per Skript gesteuerte Installation</span><span class="sxs-lookup"><span data-stu-id="2e635-173">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="2e635-174">Manuelle Installation</span><span class="sxs-lookup"><span data-stu-id="2e635-174">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="2e635-175">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="2e635-175">Next steps</span></span>

- [<span data-ttu-id="2e635-176">Tutorial: Erstellen einer Konsolenanwendung mit dem .NET SDK in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="2e635-176">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
