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
# <a name="order-of-tags-in-activitytags-is-reversed"></a>Die Reihenfolge der Tags in Activity.Tags wird umgekehrt

<xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> speichert Elemente in der Liste nun entsprechend der Reihenfolge, in der sie hinzugefügt wurden. Das zuerst hinzugefügte Element ist also das erste Element der Liste. Diese Änderung wurde vorgenommen, um für eine Übereinstimmung mit der [Spezifikation von OpenTelemetry-Attributen](https://github.com/open-telemetry/opentelemetry-specification/blob/master/specification/common/common.md#attributes) zu sorgen.

## <a name="change-description"></a>Änderungsbeschreibung

In früheren .NET-Versionen wurden Elemente in <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> in umgekehrter Reihenfolge dazu gespeichert, wie sie hinzugefügt wurden. Das zuerst hinzugefügte Element war also das letzte in der Liste. Ab .NET 5.0 wird die Reihenfolge der Elemente umgekehrt, und das zuerst hinzugefügte Element ist immer auch das erste in der Liste.

## <a name="version-introduced"></a>Eingeführt in Version

5.0

## <a name="recommended-action"></a>Empfohlene Maßnahme

Wenn Ihre App eine Abhängigkeit von der Reihenfolge in der <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType>-Liste aufweist und Sie ein Upgrade auf .NET 5.0 oder höher durchführen, müssen Sie diesen Teil Ihres Codes ändern.

## <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Diagnostics.Activity.Tags?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `P:System.Diagnostics.Activity.Tags`

-->
