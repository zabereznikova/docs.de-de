---
ms.openlocfilehash: 88a0b7e04c7015ca3fa5abd8a6897dafcbe41c49
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "88557963"
---
### <a name="multicastoptiongroup-doesnt-accept-a-null-value"></a><span data-ttu-id="a8832-101">MulticastOption.Group akzeptiert keine null-Werte</span><span class="sxs-lookup"><span data-stu-id="a8832-101">MulticastOption.Group doesn't accept a null value</span></span>

<span data-ttu-id="a8832-102"><xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> akzeptiert keine `null`-Werte mehr.</span><span class="sxs-lookup"><span data-stu-id="a8832-102"><xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> no longer accepts a value of `null`.</span></span> <span data-ttu-id="a8832-103">Wenn Sie die Eigenschaft auf `null` festlegen, wird eine <xref:System.ArgumentNullException>-Klasse ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="a8832-103">If you set the property to `null`, an <xref:System.ArgumentNullException> is thrown.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a8832-104">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="a8832-104">Version introduced</span></span>

<span data-ttu-id="a8832-105">5.0</span><span class="sxs-lookup"><span data-stu-id="a8832-105">5.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="a8832-106">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="a8832-106">Change description</span></span>

<span data-ttu-id="a8832-107">In früheren Versionen von .NET können Sie die <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType>-Eigenschaft auf `null` festlegen.</span><span class="sxs-lookup"><span data-stu-id="a8832-107">In previous versions of .NET, you can set the <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> property to `null`.</span></span> <span data-ttu-id="a8832-108">Wenn die <xref:System.Net.Sockets.MulticastOption>-Klasse später an die <xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=nameWithType>-Methode weitergegeben wird, löst die Runtime eine <xref:System.NullReferenceException>-Klasse aus.</span><span class="sxs-lookup"><span data-stu-id="a8832-108">If the <xref:System.Net.Sockets.MulticastOption> is later passed to <xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=nameWithType>, the runtime throws a <xref:System.NullReferenceException>.</span></span>

<span data-ttu-id="a8832-109">In .NET 5.0 und höher wird eine <xref:System.ArgumentNullException>-Klasse ausgelöst, wenn Sie die Eigenschaft auf `null` festlegen.</span><span class="sxs-lookup"><span data-stu-id="a8832-109">In .NET 5.0 and later, an <xref:System.ArgumentNullException> is thrown if you set the property to `null`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="a8832-110">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="a8832-110">Reason for change</span></span>

<span data-ttu-id="a8832-111">Die Eigenschaft wurde so aktualisiert, dass sie eine <xref:System.ArgumentNullException>-Klasse ausgibt, wenn der Wert `null` ist, um den Frameworkentwurfsrichtlinien zu entsprechen.</span><span class="sxs-lookup"><span data-stu-id="a8832-111">To be consistent with the Framework Design Guidelines, the property has been updated to throw an <xref:System.ArgumentNullException> if the value is `null`.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a8832-112">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="a8832-112">Recommended action</span></span>

<span data-ttu-id="a8832-113">Stellen Sie sicher, dass Sie die <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType>-Eigenschaft nicht auf `null` festlegen.</span><span class="sxs-lookup"><span data-stu-id="a8832-113">Make sure that you don't set <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> to `null`.</span></span>

#### <a name="category"></a><span data-ttu-id="a8832-114">Kategorie</span><span class="sxs-lookup"><span data-stu-id="a8832-114">Category</span></span>

<span data-ttu-id="a8832-115">Netzwerk</span><span class="sxs-lookup"><span data-stu-id="a8832-115">Networking</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a8832-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="a8832-116">Affected APIs</span></span>

- <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Net.Sockets.MulticastOption.Group`

-->
