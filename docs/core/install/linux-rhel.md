---
title: 'Installieren von .NET unter RHEL: .NET'
description: In diesem Artikel werden verschiedene Möglichkeiten veranschaulicht, das .NET SDK und die NET-Runtime für RHEL zu installieren.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 931cad51ff8e35ff16b67ff9b795feb36010a66b
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96031765"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-rhel"></a><span data-ttu-id="80cbd-103">Installieren des .NET SDK oder der .NET-Runtime unter RHEL</span><span class="sxs-lookup"><span data-stu-id="80cbd-103">Install the .NET SDK or the .NET Runtime on RHEL</span></span>

<span data-ttu-id="80cbd-104">.NET wird unter RHEL unterstützt.</span><span class="sxs-lookup"><span data-stu-id="80cbd-104">.NET is supported on RHEL.</span></span> <span data-ttu-id="80cbd-105">In diesem Artikel wird beschrieben, wie Sie .NET unter RHEL installieren.</span><span class="sxs-lookup"><span data-stu-id="80cbd-105">This article describes how to install .NET on RHEL.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="80cbd-106">Registrieren Ihres Red Hat-Abonnements</span><span class="sxs-lookup"><span data-stu-id="80cbd-106">Register your Red Hat subscription</span></span>

<span data-ttu-id="80cbd-107">Sie müssen sich zuerst mit dem Red Hat-Abonnement-Manager registrieren, um .NET von Red Hat unter RHEL installieren zu können.</span><span class="sxs-lookup"><span data-stu-id="80cbd-107">To install .NET from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="80cbd-108">Wenn Sie dies auf Ihrem System noch nicht getan haben oder Sie unsicher sind, finden Sie weitere Informationen in der [Red Hat-Produktdokumentation für .NET](https://access.redhat.com/documentation/net/5.0/).</span><span class="sxs-lookup"><span data-stu-id="80cbd-108">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET](https://access.redhat.com/documentation/net/5.0/).</span></span>

## <a name="supported-distributions"></a><span data-ttu-id="80cbd-109">Unterstützte Distributionen</span><span class="sxs-lookup"><span data-stu-id="80cbd-109">Supported distributions</span></span>

<span data-ttu-id="80cbd-110">Die folgende Tabelle enthält die derzeit unter RHEL 7 und RHEL 8 unterstützten .NET-Releases.</span><span class="sxs-lookup"><span data-stu-id="80cbd-110">The following table is a list of currently supported .NET releases on both RHEL 7 and RHEL 8.</span></span> <span data-ttu-id="80cbd-111">Diese Versionen werden weiterhin unterstützt, bis entweder die Version von [.NET das Ende des Supports](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) erreicht oder die Version von RHEL nicht mehr unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="80cbd-111">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of RHEL is no longer supported.</span></span>

- <span data-ttu-id="80cbd-112">✔️ gibt an, dass die Version von RHEL oder .NET weiterhin unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="80cbd-112">A ✔️ indicates that the version of RHEL or .NET is still supported.</span></span>
- <span data-ttu-id="80cbd-113">❌ gibt an, dass die Version von RHEL oder .NET in diesem RHEL-Release nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="80cbd-113">A ❌ indicates that the version of RHEL or .NET isn't supported on that RHEL release.</span></span>
- <span data-ttu-id="80cbd-114">Wenn sowohl eine Version von RHEL als auch eine Version von .NET mit ✔️ markiert sind, wird diese Kombination aus Betriebssystem und .NET unterstützt.</span><span class="sxs-lookup"><span data-stu-id="80cbd-114">When both a version of RHEL and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="80cbd-115">RHEL</span><span class="sxs-lookup"><span data-stu-id="80cbd-115">RHEL</span></span>                     | <span data-ttu-id="80cbd-116">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="80cbd-116">.NET Core 2.1</span></span> | <span data-ttu-id="80cbd-117">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="80cbd-117">.NET Core 3.1</span></span> | <span data-ttu-id="80cbd-118">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="80cbd-118">.NET 5.0</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="80cbd-119">✔️ [8](#rhel-8-)</span><span class="sxs-lookup"><span data-stu-id="80cbd-119">✔️ [8](#rhel-8-)</span></span>        | <span data-ttu-id="80cbd-120">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="80cbd-120">✔️ 2.1</span></span>        | <span data-ttu-id="80cbd-121">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="80cbd-121">✔️ 3.1</span></span>        | <span data-ttu-id="80cbd-122">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="80cbd-122">✔️ 5.0</span></span> |
| <span data-ttu-id="80cbd-123">✔️ [7](#rhel-7--net-50)</span><span class="sxs-lookup"><span data-stu-id="80cbd-123">✔️ [7](#rhel-7--net-50)</span></span> | <span data-ttu-id="80cbd-124">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="80cbd-124">✔️ 2.1</span></span>        | <span data-ttu-id="80cbd-125">✔️ [3.1](#rhel-7--net-core-31)</span><span class="sxs-lookup"><span data-stu-id="80cbd-125">✔️ [3.1](#rhel-7--net-core-31)</span></span>        | <span data-ttu-id="80cbd-126">✔️ [5.0](#rhel-7--net-50)</span><span class="sxs-lookup"><span data-stu-id="80cbd-126">✔️ [5.0](#rhel-7--net-50)</span></span> |

<span data-ttu-id="80cbd-127">Die folgenden Versionen von .NET werden nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="80cbd-127">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="80cbd-128">Die Downloads dafür bleiben weiterhin veröffentlicht:</span><span class="sxs-lookup"><span data-stu-id="80cbd-128">The downloads for these still remain published:</span></span>

- <span data-ttu-id="80cbd-129">3.0</span><span class="sxs-lookup"><span data-stu-id="80cbd-129">3.0</span></span>
- <span data-ttu-id="80cbd-130">2.2</span><span class="sxs-lookup"><span data-stu-id="80cbd-130">2.2</span></span>
- <span data-ttu-id="80cbd-131">2.0</span><span class="sxs-lookup"><span data-stu-id="80cbd-131">2.0</span></span>

## <a name="remove-preview-versions"></a><span data-ttu-id="80cbd-132">Entfernen von Vorschauversionen</span><span class="sxs-lookup"><span data-stu-id="80cbd-132">Remove preview versions</span></span>

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="80cbd-133">Installieren anderer Versionen</span><span class="sxs-lookup"><span data-stu-id="80cbd-133">How to install other versions</span></span>

<span data-ttu-id="80cbd-134">Konsultieren Sie die [Red Hat-Dokumentation zu .NET](https://access.redhat.com/documentation/net/5.0/) hinsichtlich der Schritte, die zur Installation anderer Releases von .NET erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="80cbd-134">Consult the [Red Hat documentation for .NET](https://access.redhat.com/documentation/net/5.0/) on the steps required to install other releases of .NET.</span></span>

## <a name="rhel-8-"></a><span data-ttu-id="80cbd-135">RHEL 8 ✔️</span><span class="sxs-lookup"><span data-stu-id="80cbd-135">RHEL 8 ✔️</span></span>

> [!TIP]
> <span data-ttu-id="80cbd-136">.NET 5.0 ist in den AppStream-Repositorys noch nicht verfügbar, .NET Core 3.1 dahingegen schon.</span><span class="sxs-lookup"><span data-stu-id="80cbd-136">.NET 5.0 isn't yet available in the AppStream repositories, but .NET Core 3.1 is.</span></span> <span data-ttu-id="80cbd-137">Verwenden Sie zur Installation von .NET Core 3.1 den `dnf install`-Befehl mit entsprechendem Paket, z. B. `aspnetcore-runtime-3.1` oder `dotnet-sdk-3.1`.</span><span class="sxs-lookup"><span data-stu-id="80cbd-137">To install .NET Core 3.1, use the `dnf install` command with the appropriate package, such as `aspnetcore-runtime-3.1` or `dotnet-sdk-3.1`.</span></span> <span data-ttu-id="80cbd-138">Die folgenden Anweisungen beziehen sich auf .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="80cbd-138">The following instructions are for .NET 5.0.</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/rhel/8/prod.repo
```

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="rhel-7--net-50"></a><span data-ttu-id="80cbd-139">RHEL 7 ✔️ .NET 5.0</span><span class="sxs-lookup"><span data-stu-id="80cbd-139">RHEL 7 ✔️ .NET 5.0</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/rhel/7/prod.repo
```

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-yum.md)]

## <a name="rhel-7--net-core-31"></a><span data-ttu-id="80cbd-140">RHEL 7 ✔️ .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="80cbd-140">RHEL 7 ✔️ .NET Core 3.1</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

<span data-ttu-id="80cbd-141">Mit dem folgenden Befehl wird das Paket `scl-utils` installiert:</span><span class="sxs-lookup"><span data-stu-id="80cbd-141">The following command installs the `scl-utils` package:</span></span>

```bash
sudo yum install scl-utils
```

### <a name="install-the-sdk"></a><span data-ttu-id="80cbd-142">Installieren des SDKs</span><span class="sxs-lookup"><span data-stu-id="80cbd-142">Install the SDK</span></span>

<span data-ttu-id="80cbd-143">Das .NET Core SDK ermöglicht Ihnen die Entwicklung von Apps mit .NET Core.</span><span class="sxs-lookup"><span data-stu-id="80cbd-143">.NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="80cbd-144">Wenn Sie das .NET Core SDK installieren, müssen Sie die entsprechende Runtime nicht installieren.</span><span class="sxs-lookup"><span data-stu-id="80cbd-144">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="80cbd-145">Führen Sie die folgenden Befehle aus, um das .NET Core SDK zu installieren:</span><span class="sxs-lookup"><span data-stu-id="80cbd-145">To install .NET Core SDK, run the following commands:</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31 -y
scl enable rh-dotnet31 bash
```

<span data-ttu-id="80cbd-146">Red Hat empfiehlt nicht die dauerhafte Aktivierung von `rh-dotnet31`, da dies andere Programme beeinträchtigen könnte.</span><span class="sxs-lookup"><span data-stu-id="80cbd-146">Red Hat does not recommend permanently enabling `rh-dotnet31` because it may affect other programs.</span></span> <span data-ttu-id="80cbd-147">So enthält beispielsweise `rh-dotnet31` eine Version von `libcurl`, die sich von der Basisversion von RHEL unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="80cbd-147">For example, `rh-dotnet31` includes a version of `libcurl` that differs from the base RHEL version.</span></span> <span data-ttu-id="80cbd-148">Dies kann zu Problemen in Programmen führen, die keine andere Version von `libcurl` erwarten.</span><span class="sxs-lookup"><span data-stu-id="80cbd-148">This may lead to issues in programs that do not expect a different version of `libcurl`.</span></span> <span data-ttu-id="80cbd-149">Wenn Sie `rh-dotnet` dauerhaft aktivieren möchten, fügen Sie der Datei _~/.bashrc_ die folgende Zeile hinzu.</span><span class="sxs-lookup"><span data-stu-id="80cbd-149">If you want to enable `rh-dotnet` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet31
```

### <a name="install-the-runtime"></a><span data-ttu-id="80cbd-150">Installieren der Runtime</span><span class="sxs-lookup"><span data-stu-id="80cbd-150">Install the runtime</span></span>

<span data-ttu-id="80cbd-151">Die .NET Core-Runtime ermöglicht Ihnen die Ausführung von Apps, die mit .NET Core erstellt wurden und die Runtime nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="80cbd-151">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="80cbd-152">Die folgenden Befehle installieren die ASP.NET Core-Runtime, die die kompatibelste Runtime für .NET Core ist.</span><span class="sxs-lookup"><span data-stu-id="80cbd-152">The commands below install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="80cbd-153">Führen Sie in Ihrem Terminal die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="80cbd-153">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31-aspnetcore-runtime-3.1 -y
scl enable rh-dotnet31-aspnetcore-runtime-3.1 bash
```

<span data-ttu-id="80cbd-154">Red Hat empfiehlt nicht die dauerhafte Aktivierung von `rh-dotnet31-aspnetcore-runtime-3.1`, da dies andere Programme beeinträchtigen könnte.</span><span class="sxs-lookup"><span data-stu-id="80cbd-154">Red Hat does not recommend permanently enabling `rh-dotnet31-aspnetcore-runtime-3.1` because it may affect other programs.</span></span> <span data-ttu-id="80cbd-155">So enthält beispielsweise `rh-dotnet31-aspnetcore-runtime-3.1` eine Version von `libcurl`, die sich von der Basisversion von RHEL unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="80cbd-155">For example, `rh-dotnet31-aspnetcore-runtime-3.1` includes a version of `libcurl` that differs from the base RHEL version.</span></span> <span data-ttu-id="80cbd-156">Dies kann zu Problemen in Programmen führen, die keine andere Version von `libcurl` erwarten.</span><span class="sxs-lookup"><span data-stu-id="80cbd-156">This may lead to issues in programs that do not expect a different version of `libcurl`.</span></span> <span data-ttu-id="80cbd-157">Wenn Sie `rh-dotnet31-aspnetcore-runtime-3.1` dauerhaft aktivieren möchten, fügen Sie der Datei _~/.bashrc_ die folgende Zeile hinzu.</span><span class="sxs-lookup"><span data-stu-id="80cbd-157">If you want to enable `rh-dotnet31-aspnetcore-runtime-3.1` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet31-aspnetcore-runtime-3.1
```

<span data-ttu-id="80cbd-158">Als Alternative zur ASP.NET Core-Runtime können Sie die .NET Core-Runtime installieren, die keine ASP.NET Core-Unterstützung bietet. Ersetzen Sie im obigen Befehl `rh-dotnet31-aspnetcore-runtime-3.1` durch `rh-dotnet31-dotnet-runtime-3.1`.</span><span class="sxs-lookup"><span data-stu-id="80cbd-158">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime that doesn't include ASP.NET Core support: replace `rh-dotnet31-aspnetcore-runtime-3.1` in the commands above with `rh-dotnet31-dotnet-runtime-3.1`.</span></span>

## <a name="snap"></a><span data-ttu-id="80cbd-159">Snap</span><span class="sxs-lookup"><span data-stu-id="80cbd-159">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="80cbd-160">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="80cbd-160">Dependencies</span></span>

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="80cbd-161">Per Skript gesteuerte Installation</span><span class="sxs-lookup"><span data-stu-id="80cbd-161">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="80cbd-162">Manuelle Installation</span><span class="sxs-lookup"><span data-stu-id="80cbd-162">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="80cbd-163">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="80cbd-163">Next steps</span></span>

- [<span data-ttu-id="80cbd-164">Tutorial: Erstellen einer Konsolenanwendung mit dem .NET SDK in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="80cbd-164">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
