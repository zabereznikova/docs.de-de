---
title: 'Breaking Change: Vector<T> löst „NotSupportedException“ aus.'
description: Hier erfahren Sie mehr über den Breaking Change an den .NET-Kernbibliotheken in .NET 5.0, durch den Vector<T> immer eine Ausnahme für nicht unterstützte Typparameter auslöst.
ms.date: 11/01/2020
ms.openlocfilehash: 63db7c6b720735b180ed11098227b31a14008f74
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759464"
---
# <a name="vectort-always-throws-notsupportedexception-for-unsupported-types"></a>Vector\<T> löst immer eine NotSupportedException für nicht unterstützte Typen aus

<xref:System.Numerics.Vector%601?displayProperty=nameWithType> löst jetzt immer eine <xref:System.NotSupportedException> für nicht unterstützte Typparameter aus.

## <a name="change-description"></a>Änderungsbeschreibung

Früher lösten Member von <xref:System.Numerics.Vector%601> nicht immer eine <xref:System.NotSupportedException> aus, wenn `T` ein [nicht unterstützter Typ](#unsupported-types) war. Die Ausnahme wurde nicht immer ausgelöst, weil Codepfade die Hardwarebeschleunigung unterstützten. Auf Plattformen ohne Hardwarebeschleunigung – wie etwa ARM32 –gab `Vector<bool> + Vector<bool>` beispielsweise `default` zurück, anstatt eine Ausnahme auszulösen. Bei nicht unterstützten Typen zeigten <xref:System.Numerics.Vector%601>-Member für verschiedene Plattformen und Hardwarekonfigurationen ein inkonsistentes Verhalten.

Ab .NET 5.0 lösen <xref:System.Numerics.Vector%601>-Member in allen Hardwarekonfigurationen immer eine <xref:System.NotSupportedException> aus, wenn `T` kein unterstützter Typ ist.

### <a name="unsupported-types"></a>Nicht unterstützte Typen

Der Typparameter von <xref:System.Numerics.Vector%601> unterstützt folgende Typen:

- `byte`
- `sbyte`
- `short`
- `ushort`
- `int`
- `uint`
- `long`
- `ulong`
- `float`
- `double`

Die unterstützten Typen haben sich nicht geändert, eine Änderung in der Zukunft ist jedoch möglich.

## <a name="version-introduced"></a>Eingeführt in Version

5.0

## <a name="recommended-action"></a>Empfohlene Maßnahme

Verwenden Sie keinen nicht unterstützten Typ für den Typparameter von <xref:System.Numerics.Vector%601>.

## <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Numerics.Vector%601?displayProperty=fullName> und alle zugehörigen Member

<!--

#### Category

Core .NET libraries

### Affected APIs

- ``T:System.Numerics.Vector`1``

-->
