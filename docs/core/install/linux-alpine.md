---
title: 'Installieren von .NET Core unter Alpine: .NET Core'
description: Hier werden verschiedene Möglichkeiten veranschaulicht, das.NET Core SDK und die NET Core-Runtime unter Alpine zu installieren.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 92753933cbcedae28867b66293d1044f700d7baa
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324824"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-alpine"></a><span data-ttu-id="249d5-103">Installieren des .NET Core SDK oder der .NET Core-Runtime unter Alpine</span><span class="sxs-lookup"><span data-stu-id="249d5-103">Install .NET Core SDK or .NET Core Runtime on Alpine</span></span>

<span data-ttu-id="249d5-104">In diesem Artikel wird beschrieben, wie Sie .NET Core unter Alpine installieren.</span><span class="sxs-lookup"><span data-stu-id="249d5-104">This article describes how to install .NET Core on Alpine.</span></span> <span data-ttu-id="249d5-105">Wenn für eine Alpine-Version kein Support mehr geboten wird, wird .NET Core mit dieser Version nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="249d5-105">When a Alpine version falls out of support, .NET Core is no longer supported with that version.</span></span> <span data-ttu-id="249d5-106">Diese Anweisungen können Ihnen jedoch helfen, .NET Core in diesen Versionen auszuführen, auch wenn kein Support dafür geboten wird.</span><span class="sxs-lookup"><span data-stu-id="249d5-106">However, these instructions may help you to get .NET Core running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

<span data-ttu-id="249d5-107">Es sind keine Installationsprogramme für Alpine vorhanden.</span><span class="sxs-lookup"><span data-stu-id="249d5-107">There are no installers for Alpine.</span></span> <span data-ttu-id="249d5-108">Sie müssen entweder das [Installationsskript](#scripted-install) verwenden oder die Anweisungen zur [manuellen Installation](#manual-install) befolgen.</span><span class="sxs-lookup"><span data-stu-id="249d5-108">You must either use the [install script](#scripted-install) or follow the [manual install](#manual-install) instructions.</span></span>

## <a name="supported-distributions"></a><span data-ttu-id="249d5-109">Unterstützte Distributionen</span><span class="sxs-lookup"><span data-stu-id="249d5-109">Supported distributions</span></span>

<span data-ttu-id="249d5-110">Die folgende Tabelle enthält die derzeit unterstützten .NET Core-Releases und die Alpine-Versionen, die diese unterstützen.</span><span class="sxs-lookup"><span data-stu-id="249d5-110">The following table is a list of currently supported .NET Core releases and the versions of Alpine they're supported on.</span></span> <span data-ttu-id="249d5-111">Diese Versionen werden weiterhin unterstützt, bis entweder die Version von [.NET Core das Ende des Supports](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) oder die Version von [Alpine das Ende ihrer Lebensdauer erreicht](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases).</span><span class="sxs-lookup"><span data-stu-id="249d5-111">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Alpine reaches end-of-life](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases).</span></span>

- <span data-ttu-id="249d5-112">✔️ gibt an, dass die Version von Alpine oder .NET Core weiterhin unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="249d5-112">A ✔️ indicates that the version of Alpine or .NET Core is still supported.</span></span>
- <span data-ttu-id="249d5-113">❌ gibt an, dass die Version von Alpine oder .NET Core in diesem Alpine-Release nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="249d5-113">A ❌ indicates that the version of Alpine or .NET Core isn't supported on that Alpine release.</span></span>
- <span data-ttu-id="249d5-114">Wenn sowohl eine Version von Alpine als auch eine Version von .NET Core mit ✔️ versehen sind, wird diese Kombination aus Betriebssystem und .NET unterstützt.</span><span class="sxs-lookup"><span data-stu-id="249d5-114">When both a version of Alpine and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="249d5-115">Alpine</span><span class="sxs-lookup"><span data-stu-id="249d5-115">Alpine</span></span>                   | <span data-ttu-id="249d5-116">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="249d5-116">.NET Core 2.1</span></span> | <span data-ttu-id="249d5-117">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="249d5-117">.NET Core 3.1</span></span> | <span data-ttu-id="249d5-118">.NET 5 Preview</span><span class="sxs-lookup"><span data-stu-id="249d5-118">.NET 5 Preview</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="249d5-119">✔️ 3.12</span><span class="sxs-lookup"><span data-stu-id="249d5-119">✔️ 3.12</span></span>  | <span data-ttu-id="249d5-120">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="249d5-120">✔️ 2.1</span></span>        | <span data-ttu-id="249d5-121">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="249d5-121">✔️ 3.1</span></span>        | <span data-ttu-id="249d5-122">✔️ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="249d5-122">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="249d5-123">✔️ 3.11</span><span class="sxs-lookup"><span data-stu-id="249d5-123">✔️ 3.11</span></span>  | <span data-ttu-id="249d5-124">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="249d5-124">✔️ 2.1</span></span>        | <span data-ttu-id="249d5-125">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="249d5-125">✔️ 3.1</span></span>        | <span data-ttu-id="249d5-126">✔️ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="249d5-126">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="249d5-127">✔️ 3.10</span><span class="sxs-lookup"><span data-stu-id="249d5-127">✔️ 3.10</span></span>  | <span data-ttu-id="249d5-128">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="249d5-128">✔️ 2.1</span></span>        | <span data-ttu-id="249d5-129">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="249d5-129">✔️ 3.1</span></span>        | <span data-ttu-id="249d5-130">✔️ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="249d5-130">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="249d5-131">✔️ 3.9</span><span class="sxs-lookup"><span data-stu-id="249d5-131">✔️ 3.9</span></span>   | <span data-ttu-id="249d5-132">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="249d5-132">✔️ 2.1</span></span>        | <span data-ttu-id="249d5-133">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="249d5-133">✔️ 3.1</span></span>        | <span data-ttu-id="249d5-134">✔️ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="249d5-134">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="249d5-135">❌ 3.8</span><span class="sxs-lookup"><span data-stu-id="249d5-135">❌ 3.8</span></span>   | <span data-ttu-id="249d5-136">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="249d5-136">✔️ 2.1</span></span>        | <span data-ttu-id="249d5-137">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="249d5-137">❌ 3.1</span></span>        | <span data-ttu-id="249d5-138">❌ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="249d5-138">❌ 5.0 Preview</span></span> |

<span data-ttu-id="249d5-139">Die folgenden Versionen von .NET Core werden nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="249d5-139">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="249d5-140">Die Downloads dafür bleiben weiterhin veröffentlicht:</span><span class="sxs-lookup"><span data-stu-id="249d5-140">The downloads for these still remain published:</span></span>

- <span data-ttu-id="249d5-141">3.0</span><span class="sxs-lookup"><span data-stu-id="249d5-141">3.0</span></span>
- <span data-ttu-id="249d5-142">2.2</span><span class="sxs-lookup"><span data-stu-id="249d5-142">2.2</span></span>
- <span data-ttu-id="249d5-143">2.0</span><span class="sxs-lookup"><span data-stu-id="249d5-143">2.0</span></span>

## <a name="dependencies"></a><span data-ttu-id="249d5-144">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="249d5-144">Dependencies</span></span>

<span data-ttu-id="249d5-145">.NET Core unter Alpine Linux erfordert die Installation der folgenden Abhängigkeiten:</span><span class="sxs-lookup"><span data-stu-id="249d5-145">.NET Core on Alpine Linux requires the following dependencies installed:</span></span>

- <span data-ttu-id="249d5-146">icu-libs</span><span class="sxs-lookup"><span data-stu-id="249d5-146">icu-libs</span></span>
- <span data-ttu-id="249d5-147">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="249d5-147">krb5-libs</span></span>
- <span data-ttu-id="249d5-148">libintl</span><span class="sxs-lookup"><span data-stu-id="249d5-148">libintl</span></span>
- <span data-ttu-id="249d5-149">libssl1.1 (Alpine 3.9 oder höher)</span><span class="sxs-lookup"><span data-stu-id="249d5-149">libssl1.1 (Alpine v3.9 or greater)</span></span>
- <span data-ttu-id="249d5-150">libssl1.0 (Alpine 3.8)</span><span class="sxs-lookup"><span data-stu-id="249d5-150">libssl1.0 (Alpine v3.8)</span></span>
- <span data-ttu-id="249d5-151">libstdc++</span><span class="sxs-lookup"><span data-stu-id="249d5-151">libstdc++</span></span>
- <span data-ttu-id="249d5-152">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="249d5-152">lttng-ust</span></span>
- <span data-ttu-id="249d5-153">numactl (optional)</span><span class="sxs-lookup"><span data-stu-id="249d5-153">numactl (optional)</span></span>
- <span data-ttu-id="249d5-154">zlib</span><span class="sxs-lookup"><span data-stu-id="249d5-154">zlib</span></span>

## <a name="scripted-install"></a><span data-ttu-id="249d5-155">Per Skript gesteuerte Installation</span><span class="sxs-lookup"><span data-stu-id="249d5-155">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="249d5-156">Manuelle Installation</span><span class="sxs-lookup"><span data-stu-id="249d5-156">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="249d5-157">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="249d5-157">Next steps</span></span>

- [<span data-ttu-id="249d5-158">Tutorial: Erstellen einer Konsolenanwendung mit dem .NET Core SDK in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="249d5-158">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
