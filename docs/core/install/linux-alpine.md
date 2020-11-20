---
title: 'Installieren von .NET unter Alpine: .NET'
description: In diesem Artikel werden verschiedene Möglichkeiten veranschaulicht, das .NET SDK und die .NET-Runtime unter Alpine zu installieren.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 29901cc24ddd4bbe8200a36765ddd29f501394c0
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506816"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-alpine"></a><span data-ttu-id="f3e8b-103">Installieren des .NET SDK oder der .NET-Runtime unter Alpine</span><span class="sxs-lookup"><span data-stu-id="f3e8b-103">Install the .NET SDK or the .NET Runtime on Alpine</span></span>

<span data-ttu-id="f3e8b-104">In diesem Artikel wird beschrieben, wie Sie .NET unter Alpine installieren.</span><span class="sxs-lookup"><span data-stu-id="f3e8b-104">This article describes how to install .NET on Alpine.</span></span> <span data-ttu-id="f3e8b-105">Wenn für eine Alpine-Version kein Support mehr geboten wird, wird .NET mit dieser Version nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f3e8b-105">When an Alpine version falls out of support, .NET is no longer supported with that version.</span></span> <span data-ttu-id="f3e8b-106">Diese Anweisungen können Ihnen jedoch helfen, .NET in diesen Versionen auszuführen, auch wenn sie nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="f3e8b-106">However, these instructions may help you to get .NET running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

<span data-ttu-id="f3e8b-107">Es sind keine Installationsprogramme für Alpine vorhanden.</span><span class="sxs-lookup"><span data-stu-id="f3e8b-107">There are no installers for Alpine.</span></span> <span data-ttu-id="f3e8b-108">Sie müssen entweder das [Installationsskript](#scripted-install) verwenden oder die Anweisungen zur [manuellen Installation](#manual-install) befolgen.</span><span class="sxs-lookup"><span data-stu-id="f3e8b-108">You must either use the [install script](#scripted-install) or follow the [manual install](#manual-install) instructions.</span></span>

## <a name="supported-distributions"></a><span data-ttu-id="f3e8b-109">Unterstützte Distributionen</span><span class="sxs-lookup"><span data-stu-id="f3e8b-109">Supported distributions</span></span>

<span data-ttu-id="f3e8b-110">Die folgende Tabelle enthält die derzeit unterstützten .NET-Releases und die Alpine-Versionen, die diese unterstützen.</span><span class="sxs-lookup"><span data-stu-id="f3e8b-110">The following table is a list of currently supported .NET releases and the versions of Alpine they're supported on.</span></span> <span data-ttu-id="f3e8b-111">Diese Versionen werden weiterhin unterstützt, bis entweder die Version von [.NET das Ende des Supports](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) oder die Version von [Alpine das Ende ihrer Lebensdauer](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases) erreicht.</span><span class="sxs-lookup"><span data-stu-id="f3e8b-111">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Alpine reaches end-of-life](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases).</span></span>

- <span data-ttu-id="f3e8b-112">✔️ gibt an, dass die Version von Alpine oder .NET weiterhin unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="f3e8b-112">A ✔️ indicates that the version of Alpine or .NET is still supported.</span></span>
- <span data-ttu-id="f3e8b-113">❌ gibt an, dass die Version von Alpine oder .NET in diesem Alpine-Release nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="f3e8b-113">A ❌ indicates that the version of Alpine or .NET isn't supported on that Alpine release.</span></span>
- <span data-ttu-id="f3e8b-114">Wenn sowohl eine Version von Alpine als auch eine Version von .NET mit ✔️ markiert sind, wird diese Kombination aus Betriebssystem und .NET unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f3e8b-114">When both a version of Alpine and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="f3e8b-115">Alpine</span><span class="sxs-lookup"><span data-stu-id="f3e8b-115">Alpine</span></span>  | <span data-ttu-id="f3e8b-116">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="f3e8b-116">.NET Core 2.1</span></span> | <span data-ttu-id="f3e8b-117">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="f3e8b-117">.NET Core 3.1</span></span> | <span data-ttu-id="f3e8b-118">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="f3e8b-118">.NET 5.0</span></span> |
|-------- |---------------|---------------|----------------|
| <span data-ttu-id="f3e8b-119">✔️ 3.12</span><span class="sxs-lookup"><span data-stu-id="f3e8b-119">✔️ 3.12</span></span> | <span data-ttu-id="f3e8b-120">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="f3e8b-120">✔️ 2.1</span></span>        | <span data-ttu-id="f3e8b-121">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="f3e8b-121">✔️ 3.1</span></span>        | <span data-ttu-id="f3e8b-122">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="f3e8b-122">✔️ 5.0</span></span> |
| <span data-ttu-id="f3e8b-123">✔️ 3.11</span><span class="sxs-lookup"><span data-stu-id="f3e8b-123">✔️ 3.11</span></span> | <span data-ttu-id="f3e8b-124">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="f3e8b-124">✔️ 2.1</span></span>        | <span data-ttu-id="f3e8b-125">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="f3e8b-125">✔️ 3.1</span></span>        | <span data-ttu-id="f3e8b-126">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="f3e8b-126">✔️ 5.0</span></span> |
| <span data-ttu-id="f3e8b-127">✔️ 3.10</span><span class="sxs-lookup"><span data-stu-id="f3e8b-127">✔️ 3.10</span></span> | <span data-ttu-id="f3e8b-128">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="f3e8b-128">✔️ 2.1</span></span>        | <span data-ttu-id="f3e8b-129">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="f3e8b-129">✔️ 3.1</span></span>        | <span data-ttu-id="f3e8b-130">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="f3e8b-130">❌ 5.0</span></span> |
| <span data-ttu-id="f3e8b-131">❌ 3.9</span><span class="sxs-lookup"><span data-stu-id="f3e8b-131">❌ 3.9</span></span>  | <span data-ttu-id="f3e8b-132">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="f3e8b-132">✔️ 2.1</span></span>        | <span data-ttu-id="f3e8b-133">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="f3e8b-133">✔️ 3.1</span></span>        | <span data-ttu-id="f3e8b-134">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="f3e8b-134">❌ 5.0</span></span> |
| <span data-ttu-id="f3e8b-135">❌ 3.8</span><span class="sxs-lookup"><span data-stu-id="f3e8b-135">❌ 3.8</span></span>  | <span data-ttu-id="f3e8b-136">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="f3e8b-136">✔️ 2.1</span></span>        | <span data-ttu-id="f3e8b-137">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="f3e8b-137">✔️ 3.1</span></span>        | <span data-ttu-id="f3e8b-138">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="f3e8b-138">❌ 5.0</span></span> |

<span data-ttu-id="f3e8b-139">Die folgenden Versionen von .NET werden nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f3e8b-139">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="f3e8b-140">Die Downloads dafür bleiben weiterhin veröffentlicht:</span><span class="sxs-lookup"><span data-stu-id="f3e8b-140">The downloads for these still remain published:</span></span>

- <span data-ttu-id="f3e8b-141">3.0</span><span class="sxs-lookup"><span data-stu-id="f3e8b-141">3.0</span></span>
- <span data-ttu-id="f3e8b-142">2.2</span><span class="sxs-lookup"><span data-stu-id="f3e8b-142">2.2</span></span>
- <span data-ttu-id="f3e8b-143">2.0</span><span class="sxs-lookup"><span data-stu-id="f3e8b-143">2.0</span></span>

## <a name="dependencies"></a><span data-ttu-id="f3e8b-144">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="f3e8b-144">Dependencies</span></span>

<span data-ttu-id="f3e8b-145">.NET unter Alpine Linux erfordert die Installation der folgenden Abhängigkeiten:</span><span class="sxs-lookup"><span data-stu-id="f3e8b-145">.NET on Alpine Linux requires the following dependencies installed:</span></span>

- <span data-ttu-id="f3e8b-146">icu-libs</span><span class="sxs-lookup"><span data-stu-id="f3e8b-146">icu-libs</span></span>
- <span data-ttu-id="f3e8b-147">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="f3e8b-147">krb5-libs</span></span>
- <span data-ttu-id="f3e8b-148">libgcc</span><span class="sxs-lookup"><span data-stu-id="f3e8b-148">libgcc</span></span>
- <span data-ttu-id="f3e8b-149">libintl</span><span class="sxs-lookup"><span data-stu-id="f3e8b-149">libintl</span></span>
- <span data-ttu-id="f3e8b-150">libssl1.1 (Alpine 3.9 oder höher)</span><span class="sxs-lookup"><span data-stu-id="f3e8b-150">libssl1.1 (Alpine v3.9 or greater)</span></span>
- <span data-ttu-id="f3e8b-151">libssl1.0 (Alpine 3.8 oder weniger)</span><span class="sxs-lookup"><span data-stu-id="f3e8b-151">libssl1.0 (Alpine v3.8 or lower)</span></span>
- <span data-ttu-id="f3e8b-152">libstdc++</span><span class="sxs-lookup"><span data-stu-id="f3e8b-152">libstdc++</span></span>
- <span data-ttu-id="f3e8b-153">zlib</span><span class="sxs-lookup"><span data-stu-id="f3e8b-153">zlib</span></span>

## <a name="scripted-install"></a><span data-ttu-id="f3e8b-154">Per Skript gesteuerte Installation</span><span class="sxs-lookup"><span data-stu-id="f3e8b-154">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="f3e8b-155">Manuelle Installation</span><span class="sxs-lookup"><span data-stu-id="f3e8b-155">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="f3e8b-156">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f3e8b-156">Next steps</span></span>

- [<span data-ttu-id="f3e8b-157">Tutorial: Erstellen einer Konsolenanwendung mit dem .NET SDK in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f3e8b-157">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
