---
title: Installieren von .NET Core unter RHEL (.NET Core)
description: Veranschaulicht verschiedene Möglichkeiten, das .NET Core SDK und die NET Core-Runtime unter RHEL zu installieren.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 4a406fe1834c16bab9a5548b69206b51270b33fa
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324714"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-rhel"></a><span data-ttu-id="38743-103">Installieren des .NET Core SDK oder der .NET Core-Runtime unter RHEL</span><span class="sxs-lookup"><span data-stu-id="38743-103">Install .NET Core SDK or .NET Core Runtime on RHEL</span></span>

<span data-ttu-id="38743-104">.NET Core wird unter RHEL unterstützt.</span><span class="sxs-lookup"><span data-stu-id="38743-104">.NET Core is supported on RHEL.</span></span> <span data-ttu-id="38743-105">In diesem Artikel wird beschrieben, wie Sie .NET Core unter RHEL installieren.</span><span class="sxs-lookup"><span data-stu-id="38743-105">This article describes how to install .NET Core on RHEL.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="38743-106">Registrieren Ihres Red Hat-Abonnements</span><span class="sxs-lookup"><span data-stu-id="38743-106">Register your Red Hat subscription</span></span>

<span data-ttu-id="38743-107">Sie müssen sich zuerst mit dem Red Hat-Abonnement-Manager registrieren, um .NET Core von Red Hat auf RHEL zu installieren.</span><span class="sxs-lookup"><span data-stu-id="38743-107">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="38743-108">Wenn Sie dies auf Ihrem System noch nicht getan haben oder Sie unsicher sind, finden Sie weitere Informationen in der [Red Hat-Produktdokumentation für .NET Core](https://access.redhat.com/documentation/net_core/).</span><span class="sxs-lookup"><span data-stu-id="38743-108">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="supported-distributions"></a><span data-ttu-id="38743-109">Unterstützte Distributionen</span><span class="sxs-lookup"><span data-stu-id="38743-109">Supported distributions</span></span>

<span data-ttu-id="38743-110">Die folgende Tabelle ist eine Liste der derzeit unter RHEL 7 und RHEL 8 unterstützten .NET Core-Versionen.</span><span class="sxs-lookup"><span data-stu-id="38743-110">The following table is a list of currently supported .NET Core releases on both RHEL 7 and RHEL 8.</span></span> <span data-ttu-id="38743-111">Diese Versionen werden weiterhin unterstützt, bis entweder die Version von [.NET Core das Ende des Supports](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) erreicht oder die Version von RHEL nicht mehr unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="38743-111">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of RHEL is no longer supported.</span></span>

- <span data-ttu-id="38743-112">✔️ gibt an, dass die Version von RHEL oder .NET Core weiterhin unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="38743-112">A ✔️ indicates that the version of RHEL or .NET Core is still supported.</span></span>
- <span data-ttu-id="38743-113">❌ gibt an, dass die Version von RHEL oder .NET Core in dieser RHEL-Version nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="38743-113">A ❌ indicates that the version of RHEL or .NET Core isn't supported on that RHEL release.</span></span>
- <span data-ttu-id="38743-114">Wenn sowohl eine Version von RHEL als auch eine Version von .NET Core über ✔️ verfügen, wird diese Kombination aus Betriebssystem und .NET unterstützt.</span><span class="sxs-lookup"><span data-stu-id="38743-114">When both a version of RHEL and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="38743-115">RHEL</span><span class="sxs-lookup"><span data-stu-id="38743-115">RHEL</span></span>                   | <span data-ttu-id="38743-116">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="38743-116">.NET Core 2.1</span></span> | <span data-ttu-id="38743-117">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="38743-117">.NET Core 3.1</span></span> | <span data-ttu-id="38743-118">.NET 5 Preview (nur manuelle Installation)</span><span class="sxs-lookup"><span data-stu-id="38743-118">.NET 5 Preview (manual install only)</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="38743-119">✔️ [8](#rhel-8-)</span><span class="sxs-lookup"><span data-stu-id="38743-119">✔️ [8](#rhel-8-)</span></span> | <span data-ttu-id="38743-120">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="38743-120">✔️ 2.1</span></span>        | <span data-ttu-id="38743-121">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="38743-121">✔️ 3.1</span></span>        | <span data-ttu-id="38743-122">✔️ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="38743-122">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="38743-123">✔️ [7](#rhel-7-)</span><span class="sxs-lookup"><span data-stu-id="38743-123">✔️ [7](#rhel-7-)</span></span> | <span data-ttu-id="38743-124">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="38743-124">✔️ 2.1</span></span>        | <span data-ttu-id="38743-125">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="38743-125">✔️ 3.1</span></span>        | <span data-ttu-id="38743-126">✔️ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="38743-126">✔️ 5.0 Preview</span></span> |

<span data-ttu-id="38743-127">Die folgenden Versionen von .NET Core werden nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="38743-127">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="38743-128">Die Downloads dafür bleiben weiterhin veröffentlicht:</span><span class="sxs-lookup"><span data-stu-id="38743-128">The downloads for these still remain published:</span></span>

- <span data-ttu-id="38743-129">3.0</span><span class="sxs-lookup"><span data-stu-id="38743-129">3.0</span></span>
- <span data-ttu-id="38743-130">2.2</span><span class="sxs-lookup"><span data-stu-id="38743-130">2.2</span></span>
- <span data-ttu-id="38743-131">2.0</span><span class="sxs-lookup"><span data-stu-id="38743-131">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="38743-132">Installieren anderer Versionen</span><span class="sxs-lookup"><span data-stu-id="38743-132">How to install other versions</span></span>

<span data-ttu-id="38743-133">Konsultieren Sie die [Red Hat-Dokumentation zu .NET Core](https://access.redhat.com/documentation/net_core/) hinsichtlich der Schritte, die zur Installation anderer Versionen von .NET Core erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="38743-133">Consult the [Red Hat documentation for .NET Core](https://access.redhat.com/documentation/net_core/) on the steps required to install other releases of .NET Core.</span></span>

## <a name="rhel-8-"></a><span data-ttu-id="38743-134">RHEL 8 ✔️</span><span class="sxs-lookup"><span data-stu-id="38743-134">RHEL 8 ✔️</span></span>

<span data-ttu-id="38743-135">NET Core ist in den AppStream-Repositorys für RHEL 8 enthalten.</span><span class="sxs-lookup"><span data-stu-id="38743-135">.NET Core is included in the AppStream repositories for RHEL 8.</span></span>

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="rhel-7-"></a><span data-ttu-id="38743-136">RHEL 7 ✔️</span><span class="sxs-lookup"><span data-stu-id="38743-136">RHEL 7 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

<span data-ttu-id="38743-137">Mit dem folgenden Befehl wird das Paket `scl-utils` installiert:</span><span class="sxs-lookup"><span data-stu-id="38743-137">The following command installs the `scl-utils` package:</span></span>

```bash
sudo yum install scl-utils
```

### <a name="install-the-sdk"></a><span data-ttu-id="38743-138">Installieren des SDKs</span><span class="sxs-lookup"><span data-stu-id="38743-138">Install the SDK</span></span>

<span data-ttu-id="38743-139">Das .NET Core SDK ermöglicht Ihnen die Entwicklung von Apps mit .NET Core.</span><span class="sxs-lookup"><span data-stu-id="38743-139">.NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="38743-140">Wenn Sie das .NET Core SDK installieren, müssen Sie die entsprechende Runtime nicht installieren.</span><span class="sxs-lookup"><span data-stu-id="38743-140">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="38743-141">Führen Sie die folgenden Befehle aus, um das .NET Core SDK zu installieren:</span><span class="sxs-lookup"><span data-stu-id="38743-141">To install .NET Core SDK, run the following commands:</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31 -y
scl enable rh-dotnet31 bash
```

<span data-ttu-id="38743-142">Red Hat empfiehlt nicht die dauerhafte Aktivierung von `rh-dotnet31`, da dies andere Programme beeinträchtigen könnte.</span><span class="sxs-lookup"><span data-stu-id="38743-142">Red Hat does not recommend permanently enabling `rh-dotnet31` because it may affect other programs.</span></span> <span data-ttu-id="38743-143">`rh-dotnet31` enthält beispielsweise eine Version von `libcurl`, die sich von der Basisversion von RHEL unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="38743-143">For example, `rh-dotnet31` includes a version of `libcurl` that differs from the base RHEL version.</span></span> <span data-ttu-id="38743-144">Dies kann zu Problemen in Programmen führen, die keine andere Version von `libcurl` erwarten.</span><span class="sxs-lookup"><span data-stu-id="38743-144">This may lead to issues in programs that do not expect a different version of `libcurl`.</span></span> <span data-ttu-id="38743-145">Wenn Sie `rh-dotnet` dauerhaft aktivieren möchten, fügen Sie der Datei _~/.bashrc_ die folgende Zeile hinzu.</span><span class="sxs-lookup"><span data-stu-id="38743-145">If you want to enable `rh-dotnet` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet31
```

### <a name="install-the-runtime"></a><span data-ttu-id="38743-146">Installieren der Runtime</span><span class="sxs-lookup"><span data-stu-id="38743-146">Install the runtime</span></span>

<span data-ttu-id="38743-147">Die .NET Core-Runtime ermöglicht Ihnen die Ausführung von Apps, die mit .NET Core erstellt wurden und die Runtime nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="38743-147">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="38743-148">Die folgenden Befehle installieren die ASP.NET Core-Runtime, die die kompatibelste Runtime für .NET Core ist.</span><span class="sxs-lookup"><span data-stu-id="38743-148">The commands below install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="38743-149">Führen Sie in Ihrem Terminal die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="38743-149">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31-aspnetcore-runtime-3.1 -y
scl enable rh-dotnet31-aspnetcore-runtime-3.1 bash
```

<span data-ttu-id="38743-150">Red Hat empfiehlt nicht die dauerhafte Aktivierung von `rh-dotnet31-aspnetcore-runtime-3.1`, da dies andere Programme beeinträchtigen könnte.</span><span class="sxs-lookup"><span data-stu-id="38743-150">Red Hat does not recommend permanently enabling `rh-dotnet31-aspnetcore-runtime-3.1` because it may affect other programs.</span></span> <span data-ttu-id="38743-151">So enthält beispielsweise `rh-dotnet31-aspnetcore-runtime-3.1` eine Version von `libcurl`, die sich von der Basisversion von RHEL unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="38743-151">For example, `rh-dotnet31-aspnetcore-runtime-3.1` includes a version of `libcurl` that differs from the base RHEL version.</span></span> <span data-ttu-id="38743-152">Dies kann zu Problemen in Programmen führen, die keine andere Version von `libcurl` erwarten.</span><span class="sxs-lookup"><span data-stu-id="38743-152">This may lead to issues in programs that do not expect a different version of `libcurl`.</span></span> <span data-ttu-id="38743-153">Wenn Sie `rh-dotnet31-aspnetcore-runtime-3.1` dauerhaft aktivieren möchten, fügen Sie der Datei _~/.bashrc_ die folgende Zeile hinzu.</span><span class="sxs-lookup"><span data-stu-id="38743-153">If you want to enable `rh-dotnet31-aspnetcore-runtime-3.1` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet31-aspnetcore-runtime-3.1
```

<span data-ttu-id="38743-154">Als Alternative zur ASP.NET Core-Runtime können Sie die .NET Core-Runtime installieren, die keine ASP.NET Core-Unterstützung bietet. Ersetzen Sie im obigen Befehl `rh-dotnet31-aspnetcore-runtime-3.1` durch `rh-dotnet31-dotnet-runtime-3.1`.</span><span class="sxs-lookup"><span data-stu-id="38743-154">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime that doesn't include ASP.NET Core support: replace `rh-dotnet31-aspnetcore-runtime-3.1` in the commands above with `rh-dotnet31-dotnet-runtime-3.1`.</span></span>

## <a name="snap"></a><span data-ttu-id="38743-155">Snap</span><span class="sxs-lookup"><span data-stu-id="38743-155">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="38743-156">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="38743-156">Dependencies</span></span>

[!INCLUDE [linux-install-dependencies](includes/linux-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="38743-157">Per Skript gesteuerte Installation</span><span class="sxs-lookup"><span data-stu-id="38743-157">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="38743-158">Manuelle Installation</span><span class="sxs-lookup"><span data-stu-id="38743-158">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="38743-159">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="38743-159">Next steps</span></span>

- [<span data-ttu-id="38743-160">Tutorial: Erstellen einer Konsolenanwendung mit dem .NET Core SDK in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="38743-160">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
