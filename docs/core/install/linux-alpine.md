---
title: 'Installieren von .NET unter Alpine: .NET'
description: In diesem Artikel werden verschiedene Möglichkeiten veranschaulicht, das .NET SDK und die .NET-Runtime unter Alpine zu installieren.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: 6adaa905c400b45526ebbc3d8e2606522863eec3
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970849"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-alpine"></a><span data-ttu-id="6bb24-103">Installieren des .NET SDK oder der .NET-Runtime unter Alpine</span><span class="sxs-lookup"><span data-stu-id="6bb24-103">Install the .NET SDK or the .NET Runtime on Alpine</span></span>

<span data-ttu-id="6bb24-104">In diesem Artikel wird beschrieben, wie Sie .NET unter Alpine installieren.</span><span class="sxs-lookup"><span data-stu-id="6bb24-104">This article describes how to install .NET on Alpine.</span></span> <span data-ttu-id="6bb24-105">Wenn für eine Alpine-Version kein Support mehr geboten wird, wird .NET mit dieser Version nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6bb24-105">When an Alpine version falls out of support, .NET is no longer supported with that version.</span></span> <span data-ttu-id="6bb24-106">Diese Anweisungen können Ihnen jedoch helfen, .NET in diesen Versionen auszuführen, auch wenn sie nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="6bb24-106">However, these instructions may help you to get .NET running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="install"></a><span data-ttu-id="6bb24-107">Installieren</span><span class="sxs-lookup"><span data-stu-id="6bb24-107">Install</span></span>

<span data-ttu-id="6bb24-108">Installationsprogramme sind für Alpine Linux nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6bb24-108">Installers aren't available for Alpine Linux.</span></span> <span data-ttu-id="6bb24-109">.NET muss auf eine der folgenden Arten installiert werden:</span><span class="sxs-lookup"><span data-stu-id="6bb24-109">You must install .NET in one of the following ways:</span></span>

- [<span data-ttu-id="6bb24-110">Snap-Paket</span><span class="sxs-lookup"><span data-stu-id="6bb24-110">Snap package</span></span>](linux-snap.md)
- [<span data-ttu-id="6bb24-111">Skriptgesteuerte Installation mit _install-dotnet.sh_</span><span class="sxs-lookup"><span data-stu-id="6bb24-111">Scripted install with _install-dotnet.sh_</span></span>](linux-scripted-manual.md#scripted-install)
- [<span data-ttu-id="6bb24-112">Manuelle binäre Extraktion</span><span class="sxs-lookup"><span data-stu-id="6bb24-112">Manual binary extraction</span></span>](linux-scripted-manual.md#manual-install)

## <a name="supported-distributions"></a><span data-ttu-id="6bb24-113">Unterstützte Distributionen</span><span class="sxs-lookup"><span data-stu-id="6bb24-113">Supported distributions</span></span>

<span data-ttu-id="6bb24-114">Die folgende Tabelle enthält die derzeit unterstützten .NET-Releases und die Alpine-Versionen, die diese unterstützen.</span><span class="sxs-lookup"><span data-stu-id="6bb24-114">The following table is a list of currently supported .NET releases and the versions of Alpine they're supported on.</span></span> <span data-ttu-id="6bb24-115">Diese Versionen werden weiterhin unterstützt, bis entweder die Version von [.NET das Ende des Supports](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) oder die Version von [Alpine das Ende ihrer Lebensdauer](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases) erreicht.</span><span class="sxs-lookup"><span data-stu-id="6bb24-115">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Alpine reaches end-of-life](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases).</span></span>

- <span data-ttu-id="6bb24-116">✔️ gibt an, dass die Version von Alpine oder .NET weiterhin unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="6bb24-116">A ✔️ indicates that the version of Alpine or .NET is still supported.</span></span>
- <span data-ttu-id="6bb24-117">❌ gibt an, dass die Version von Alpine oder .NET in diesem Alpine-Release nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="6bb24-117">A ❌ indicates that the version of Alpine or .NET isn't supported on that Alpine release.</span></span>
- <span data-ttu-id="6bb24-118">Wenn sowohl eine Version von Alpine als auch eine Version von .NET mit ✔️ markiert sind, wird diese Kombination aus Betriebssystem und .NET unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6bb24-118">When both a version of Alpine and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="6bb24-119">Alpine</span><span class="sxs-lookup"><span data-stu-id="6bb24-119">Alpine</span></span>  | <span data-ttu-id="6bb24-120">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="6bb24-120">.NET Core 2.1</span></span> | <span data-ttu-id="6bb24-121">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="6bb24-121">.NET Core 3.1</span></span> | <span data-ttu-id="6bb24-122">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="6bb24-122">.NET 5.0</span></span> |
|-------- |---------------|---------------|----------------|
| <span data-ttu-id="6bb24-123">✔️ 3.12</span><span class="sxs-lookup"><span data-stu-id="6bb24-123">✔️ 3.12</span></span> | <span data-ttu-id="6bb24-124">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="6bb24-124">✔️ 2.1</span></span>        | <span data-ttu-id="6bb24-125">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="6bb24-125">✔️ 3.1</span></span>        | <span data-ttu-id="6bb24-126">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="6bb24-126">✔️ 5.0</span></span> |
| <span data-ttu-id="6bb24-127">✔️ 3.11</span><span class="sxs-lookup"><span data-stu-id="6bb24-127">✔️ 3.11</span></span> | <span data-ttu-id="6bb24-128">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="6bb24-128">✔️ 2.1</span></span>        | <span data-ttu-id="6bb24-129">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="6bb24-129">✔️ 3.1</span></span>        | <span data-ttu-id="6bb24-130">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="6bb24-130">✔️ 5.0</span></span> |
| <span data-ttu-id="6bb24-131">✔️ 3.10</span><span class="sxs-lookup"><span data-stu-id="6bb24-131">✔️ 3.10</span></span> | <span data-ttu-id="6bb24-132">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="6bb24-132">✔️ 2.1</span></span>        | <span data-ttu-id="6bb24-133">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="6bb24-133">✔️ 3.1</span></span>        | <span data-ttu-id="6bb24-134">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="6bb24-134">❌ 5.0</span></span> |
| <span data-ttu-id="6bb24-135">❌ 3.9</span><span class="sxs-lookup"><span data-stu-id="6bb24-135">❌ 3.9</span></span>  | <span data-ttu-id="6bb24-136">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="6bb24-136">✔️ 2.1</span></span>        | <span data-ttu-id="6bb24-137">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="6bb24-137">✔️ 3.1</span></span>        | <span data-ttu-id="6bb24-138">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="6bb24-138">❌ 5.0</span></span> |
| <span data-ttu-id="6bb24-139">❌ 3.8</span><span class="sxs-lookup"><span data-stu-id="6bb24-139">❌ 3.8</span></span>  | <span data-ttu-id="6bb24-140">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="6bb24-140">✔️ 2.1</span></span>        | <span data-ttu-id="6bb24-141">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="6bb24-141">✔️ 3.1</span></span>        | <span data-ttu-id="6bb24-142">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="6bb24-142">❌ 5.0</span></span> |

<span data-ttu-id="6bb24-143">Die folgenden Versionen von .NET werden nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6bb24-143">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="6bb24-144">Die Downloads dafür bleiben weiterhin veröffentlicht:</span><span class="sxs-lookup"><span data-stu-id="6bb24-144">The downloads for these still remain published:</span></span>

- <span data-ttu-id="6bb24-145">3.0</span><span class="sxs-lookup"><span data-stu-id="6bb24-145">3.0</span></span>
- <span data-ttu-id="6bb24-146">2.2</span><span class="sxs-lookup"><span data-stu-id="6bb24-146">2.2</span></span>
- <span data-ttu-id="6bb24-147">2.0</span><span class="sxs-lookup"><span data-stu-id="6bb24-147">2.0</span></span>

## <a name="dependencies"></a><span data-ttu-id="6bb24-148">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="6bb24-148">Dependencies</span></span>

<span data-ttu-id="6bb24-149">.NET unter Alpine Linux erfordert die Installation der folgenden Abhängigkeiten:</span><span class="sxs-lookup"><span data-stu-id="6bb24-149">.NET on Alpine Linux requires the following dependencies installed:</span></span>

- <span data-ttu-id="6bb24-150">icu-libs</span><span class="sxs-lookup"><span data-stu-id="6bb24-150">icu-libs</span></span>
- <span data-ttu-id="6bb24-151">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="6bb24-151">krb5-libs</span></span>
- <span data-ttu-id="6bb24-152">libgcc</span><span class="sxs-lookup"><span data-stu-id="6bb24-152">libgcc</span></span>
- <span data-ttu-id="6bb24-153">libintl</span><span class="sxs-lookup"><span data-stu-id="6bb24-153">libintl</span></span>
- <span data-ttu-id="6bb24-154">libssl1.1 (Alpine 3.9 oder höher)</span><span class="sxs-lookup"><span data-stu-id="6bb24-154">libssl1.1 (Alpine v3.9 or greater)</span></span>
- <span data-ttu-id="6bb24-155">libssl1.0 (Alpine 3.8 oder weniger)</span><span class="sxs-lookup"><span data-stu-id="6bb24-155">libssl1.0 (Alpine v3.8 or lower)</span></span>
- <span data-ttu-id="6bb24-156">libstdc++</span><span class="sxs-lookup"><span data-stu-id="6bb24-156">libstdc++</span></span>
- <span data-ttu-id="6bb24-157">zlib</span><span class="sxs-lookup"><span data-stu-id="6bb24-157">zlib</span></span>

## <a name="next-steps"></a><span data-ttu-id="6bb24-158">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="6bb24-158">Next steps</span></span>

- [<span data-ttu-id="6bb24-159">Aktivieren der Vervollständigung mit der TAB-TASTE für die .NET-CLI</span><span class="sxs-lookup"><span data-stu-id="6bb24-159">How to enable TAB completion for the .NET CLI</span></span>](../tools/enable-tab-autocomplete.md)
- [<span data-ttu-id="6bb24-160">Tutorial: Erstellen einer Konsolenanwendung mit dem .NET SDK in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="6bb24-160">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
