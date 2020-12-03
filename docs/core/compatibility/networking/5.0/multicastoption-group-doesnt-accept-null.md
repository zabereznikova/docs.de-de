---
title: 'Breaking Change: MulticastOption.Group akzeptiert keine null-Werte'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, wegen dem MulticastOption.Group keinen NULL-Wert mehr akzeptiert.
ms.date: 08/18/2020
ms.openlocfilehash: 164ac8c2c8dd14f9e0758017e54eeb377f88a7e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759386"
---
# <a name="multicastoptiongroup-doesnt-accept-a-null-value"></a><span data-ttu-id="46fbc-103">MulticastOption.Group akzeptiert keine null-Werte</span><span class="sxs-lookup"><span data-stu-id="46fbc-103">MulticastOption.Group doesn't accept a null value</span></span>

<span data-ttu-id="46fbc-104"><xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> akzeptiert keine `null`-Werte mehr.</span><span class="sxs-lookup"><span data-stu-id="46fbc-104"><xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> no longer accepts a value of `null`.</span></span> <span data-ttu-id="46fbc-105">Wenn Sie die Eigenschaft auf `null` festlegen, wird eine <xref:System.ArgumentNullException>-Klasse ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="46fbc-105">If you set the property to `null`, an <xref:System.ArgumentNullException> is thrown.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="46fbc-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="46fbc-106">Version introduced</span></span>

<span data-ttu-id="46fbc-107">5.0</span><span class="sxs-lookup"><span data-stu-id="46fbc-107">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="46fbc-108">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="46fbc-108">Change description</span></span>

<span data-ttu-id="46fbc-109">In früheren Versionen von .NET können Sie die <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType>-Eigenschaft auf `null` festlegen.</span><span class="sxs-lookup"><span data-stu-id="46fbc-109">In previous versions of .NET, you can set the <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> property to `null`.</span></span> <span data-ttu-id="46fbc-110">Wenn die <xref:System.Net.Sockets.MulticastOption>-Klasse später an die <xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=nameWithType>-Methode weitergegeben wird, löst die Runtime eine <xref:System.NullReferenceException>-Klasse aus.</span><span class="sxs-lookup"><span data-stu-id="46fbc-110">If the <xref:System.Net.Sockets.MulticastOption> is later passed to <xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=nameWithType>, the runtime throws a <xref:System.NullReferenceException>.</span></span>

<span data-ttu-id="46fbc-111">In .NET 5.0 und höher wird eine <xref:System.ArgumentNullException>-Klasse ausgelöst, wenn Sie die Eigenschaft auf `null` festlegen.</span><span class="sxs-lookup"><span data-stu-id="46fbc-111">In .NET 5.0 and later, an <xref:System.ArgumentNullException> is thrown if you set the property to `null`.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="46fbc-112">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="46fbc-112">Reason for change</span></span>

<span data-ttu-id="46fbc-113">Die Eigenschaft wurde so aktualisiert, dass sie eine <xref:System.ArgumentNullException>-Klasse ausgibt, wenn der Wert `null` ist, um den Frameworkentwurfsrichtlinien zu entsprechen.</span><span class="sxs-lookup"><span data-stu-id="46fbc-113">To be consistent with the Framework Design Guidelines, the property has been updated to throw an <xref:System.ArgumentNullException> if the value is `null`.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="46fbc-114">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="46fbc-114">Recommended action</span></span>

<span data-ttu-id="46fbc-115">Stellen Sie sicher, dass Sie die <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType>-Eigenschaft nicht auf `null` festlegen.</span><span class="sxs-lookup"><span data-stu-id="46fbc-115">Make sure that you don't set <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> to `null`.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="46fbc-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="46fbc-116">Affected APIs</span></span>

- <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=fullName>

<!--

### Affected APIs

- `P:System.Net.Sockets.MulticastOption.Group`

### Category

Networking

-->
