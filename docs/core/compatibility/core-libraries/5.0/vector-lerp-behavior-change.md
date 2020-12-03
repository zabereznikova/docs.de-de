---
title: 'Breaking Change: Behavior Change für Vector2.Lerp und Vector4.Lerp'
description: Hier erfahren Sie mehr über den Breaking Change an den .NET-Kernbibliotheken in .NET 5.0, durch den die Implementierung von Vector2.Lerp und Vector4.Lerp jetzt Rundungsfehler bei Gleitkommazahlen ordnungsgemäß berücksichtigt.
ms.date: 11/01/2020
ms.openlocfilehash: 8e363a559dba8b7563c40637c47f101d59951216
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759233"
---
# <a name="behavior-change-for-vector2lerp-and-vector4lerp"></a>Behavior Change für Vector2.Lerp und Vector4.Lerp

Die Implementierung von <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> und <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> wurde so geändert, dass ein Rundungsfehler bei Gleitkommazahlen nun ordnungsgemäß berücksichtigt wird.

## <a name="change-description"></a>Änderungsbeschreibung

Bisher waren <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> und <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> als `value1 + (value2 - value1) * amount` implementiert. Aufgrund eines Rundungsfehlers bei Gleitkommazahlen gibt dieser Algorithmus nicht immer `value2` zurück, wenn `amount` auf `1.0f` festgelegt ist.

Ab .NET 5.0 verwendet die Implementierung denselben Algorithmus wie <xref:System.Numerics.Vector3.Lerp(System.Numerics.Vector3,System.Numerics.Vector3,System.Single)?displayProperty=nameWithType>, nämlich `(value1 * (1.0f - amount)) + (value2 * amount)`. Dieser Algorithmus berücksichtigt den Rundungsfehler nun ordnungsgemäß. Wenn `amount` nun also auf `1.0f` festgelegt ist, beträgt das Ergebnis genau `value2`. Der aktualisierte Algorithmus ermöglicht es auch, dass der Algorithmus mithilfe von <xref:System.MathF.FusedMultiplyAdd%2A?displayProperty=nameWithType> (wenn verfügbar) frei optimiert werden kann.

## <a name="version-introduced"></a>Eingeführt in Version

5.0

## <a name="recommended-action"></a>Empfohlene Maßnahme

Es ist keine Aktion erforderlich. Wenn Sie das ehemalige Verhalten jedoch beibehalten möchten, können Sie eine eigene `Lerp`-Funktion implementieren, die den vorherigen Algorithmus von `value1 + (value2 - value1) * amount` verwendet.

## <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=fullName>
- <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `M:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)`
- `M:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)`

-->
