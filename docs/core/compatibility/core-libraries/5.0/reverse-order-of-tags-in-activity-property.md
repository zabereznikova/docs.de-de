---
title: 'Breaking Change: Die Reihenfolge der Tags in Activity.Tags wird umgekehrt'
description: Hier erfahren Sie mehr über den Breaking Change an den .NET-Kernbibliotheken in .NET 5.0, durch den Activity.Tags Elemente jetzt in der Reihenfolge, in der sie hinzugefügt werden, in der Liste speichert.
ms.date: 11/01/2020
ms.openlocfilehash: 1ff14dc1a4f7a0bf8cf9e79f3750b819f4d4a5ca
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759445"
---
# <a name="order-of-tags-in-activitytags-is-reversed"></a><span data-ttu-id="3412e-103">Die Reihenfolge der Tags in Activity.Tags wird umgekehrt</span><span class="sxs-lookup"><span data-stu-id="3412e-103">Order of tags in Activity.Tags is reversed</span></span>

<span data-ttu-id="3412e-104"><xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> speichert Elemente in der Liste nun entsprechend der Reihenfolge, in der sie hinzugefügt wurden. Das zuerst hinzugefügte Element ist also das erste Element der Liste.</span><span class="sxs-lookup"><span data-stu-id="3412e-104"><xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> now stores items in the list according to the order they are added, that is, the first item that's added is first in the list.</span></span> <span data-ttu-id="3412e-105">Diese Änderung wurde vorgenommen, um für eine Übereinstimmung mit der [Spezifikation von OpenTelemetry-Attributen](https://github.com/open-telemetry/opentelemetry-specification/blob/master/specification/common/common.md#attributes) zu sorgen.</span><span class="sxs-lookup"><span data-stu-id="3412e-105">This change was made to match the [OpenTelemetry Attributes specification](https://github.com/open-telemetry/opentelemetry-specification/blob/master/specification/common/common.md#attributes).</span></span>

## <a name="change-description"></a><span data-ttu-id="3412e-106">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="3412e-106">Change description</span></span>

<span data-ttu-id="3412e-107">In früheren .NET-Versionen wurden Elemente in <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> in umgekehrter Reihenfolge dazu gespeichert, wie sie hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="3412e-107">In previous .NET versions, <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> stores items in the reverse order from which they're added.</span></span> <span data-ttu-id="3412e-108">Das zuerst hinzugefügte Element war also das letzte in der Liste.</span><span class="sxs-lookup"><span data-stu-id="3412e-108">That is, the first item added is last in the list.</span></span> <span data-ttu-id="3412e-109">Ab .NET 5.0 wird die Reihenfolge der Elemente umgekehrt, und das zuerst hinzugefügte Element ist immer auch das erste in der Liste.</span><span class="sxs-lookup"><span data-stu-id="3412e-109">Starting in .NET 5.0, the order of the items is reversed, and the first item added is always first in the list.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="3412e-110">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="3412e-110">Version introduced</span></span>

<span data-ttu-id="3412e-111">5.0</span><span class="sxs-lookup"><span data-stu-id="3412e-111">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="3412e-112">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="3412e-112">Recommended action</span></span>

<span data-ttu-id="3412e-113">Wenn Ihre App eine Abhängigkeit von der Reihenfolge in der <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType>-Liste aufweist und Sie ein Upgrade auf .NET 5.0 oder höher durchführen, müssen Sie diesen Teil Ihres Codes ändern.</span><span class="sxs-lookup"><span data-stu-id="3412e-113">If your app has a dependency on the <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> list order and you're upgrading to .NET 5.0 or later, you'll need to change this part of your code.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="3412e-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="3412e-114">Affected APIs</span></span>

- <xref:System.Diagnostics.Activity.Tags?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `P:System.Diagnostics.Activity.Tags`

-->
