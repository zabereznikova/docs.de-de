---
ms.openlocfilehash: 24b88b3ba1b6cfe9fb9fb1f6398a6daeb57596a9
ms.sourcegitcommit: a8a205034eeffc7c3e1bdd6f506a75b0f7099ebf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2020
ms.locfileid: "91756108"
---
### <a name="order-of-tags-in-activitytags-is-reversed"></a><span data-ttu-id="f9b6d-101">Die Reihenfolge der Tags in Activity.Tags wird umgekehrt</span><span class="sxs-lookup"><span data-stu-id="f9b6d-101">Order of tags in Activity.Tags is reversed</span></span>

<span data-ttu-id="f9b6d-102"><xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> speichert Elemente in der Liste nun entsprechend der Reihenfolge, in der sie hinzugefügt wurden. Das zuerst hinzugefügte Element ist also das erste Element der Liste.</span><span class="sxs-lookup"><span data-stu-id="f9b6d-102"><xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> now stores items in the list according to the order they are added, that is, the first item that's added is first in the list.</span></span> <span data-ttu-id="f9b6d-103">Diese Änderung wurde vorgenommen, um für eine Übereinstimmung mit der [Spezifikation von OpenTelemetry-Attributen](https://github.com/open-telemetry/opentelemetry-specification/blob/master/specification/common/common.md#attributes) zu sorgen.</span><span class="sxs-lookup"><span data-stu-id="f9b6d-103">This change was made to match the [OpenTelemetry Attributes specification](https://github.com/open-telemetry/opentelemetry-specification/blob/master/specification/common/common.md#attributes).</span></span>

#### <a name="change-description"></a><span data-ttu-id="f9b6d-104">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="f9b6d-104">Change description</span></span>

<span data-ttu-id="f9b6d-105">In früheren .NET-Versionen wurden Elemente in <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> in umgekehrter Reihenfolge dazu gespeichert, wie sie hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="f9b6d-105">In previous .NET versions, <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> stores items in the reverse order from which they're added.</span></span> <span data-ttu-id="f9b6d-106">Das zuerst hinzugefügte Element war also das letzte in der Liste.</span><span class="sxs-lookup"><span data-stu-id="f9b6d-106">That is, the first item added is last in the list.</span></span> <span data-ttu-id="f9b6d-107">Ab .NET 5.0 wird die Reihenfolge der Elemente umgekehrt, und das zuerst hinzugefügte Element ist immer auch das erste in der Liste.</span><span class="sxs-lookup"><span data-stu-id="f9b6d-107">Starting in .NET 5.0, the order of the items is reversed, and the first item added is always first in the list.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f9b6d-108">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="f9b6d-108">Version introduced</span></span>

<span data-ttu-id="f9b6d-109">5.0</span><span class="sxs-lookup"><span data-stu-id="f9b6d-109">5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f9b6d-110">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="f9b6d-110">Recommended action</span></span>

<span data-ttu-id="f9b6d-111">Wenn Ihre App eine Abhängigkeit von der Reihenfolge in der <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType>-Liste aufweist und Sie ein Upgrade auf .NET 5.0 oder höher durchführen, müssen Sie diesen Teil Ihres Codes ändern.</span><span class="sxs-lookup"><span data-stu-id="f9b6d-111">If your app has a dependency on the <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> list order and you're upgrading to .NET 5.0 or later, you'll need to change this part of your code.</span></span>

#### <a name="category"></a><span data-ttu-id="f9b6d-112">Kategorie</span><span class="sxs-lookup"><span data-stu-id="f9b6d-112">Category</span></span>

<span data-ttu-id="f9b6d-113">Core .NET-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="f9b6d-113">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f9b6d-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="f9b6d-114">Affected APIs</span></span>

- <xref:System.Diagnostics.Activity.Tags?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Diagnostics.Activity.Tags`

-->
