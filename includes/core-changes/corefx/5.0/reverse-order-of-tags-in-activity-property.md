---
ms.openlocfilehash: 24b88b3ba1b6cfe9fb9fb1f6398a6daeb57596a9
ms.sourcegitcommit: a8a205034eeffc7c3e1bdd6f506a75b0f7099ebf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2020
ms.locfileid: "91756108"
---
### <a name="order-of-tags-in-activitytags-is-reversed"></a>Die Reihenfolge der Tags in Activity.Tags wird umgekehrt

<xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> speichert Elemente in der Liste nun entsprechend der Reihenfolge, in der sie hinzugefügt wurden. Das zuerst hinzugefügte Element ist also das erste Element der Liste. Diese Änderung wurde vorgenommen, um für eine Übereinstimmung mit der [Spezifikation von OpenTelemetry-Attributen](https://github.com/open-telemetry/opentelemetry-specification/blob/master/specification/common/common.md#attributes) zu sorgen.

#### <a name="change-description"></a>Änderungsbeschreibung

In früheren .NET-Versionen wurden Elemente in <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> in umgekehrter Reihenfolge dazu gespeichert, wie sie hinzugefügt wurden. Das zuerst hinzugefügte Element war also das letzte in der Liste. Ab .NET 5.0 wird die Reihenfolge der Elemente umgekehrt, und das zuerst hinzugefügte Element ist immer auch das erste in der Liste.

#### <a name="version-introduced"></a>Eingeführt in Version

5.0

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Wenn Ihre App eine Abhängigkeit von der Reihenfolge in der <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType>-Liste aufweist und Sie ein Upgrade auf .NET 5.0 oder höher durchführen, müssen Sie diesen Teil Ihres Codes ändern.

#### <a name="category"></a>Kategorie

Core .NET-Bibliotheken

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Diagnostics.Activity.Tags?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Diagnostics.Activity.Tags`

-->
