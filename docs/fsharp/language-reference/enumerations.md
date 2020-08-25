---
title: Enumerationen
description: 'Erfahren Sie, wie Sie F #-Enumerationen anstelle von literalen verwenden, um Ihren Code lesbarer und verwalterbar zu machen.'
ms.date: 08/15/2020
ms.openlocfilehash: 5f298691ce48a06c203930c7742cf007c819dc33
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812106"
---
# <a name="enumerations"></a>Enumerationen

*Enumerationen*, die auch als Enumerationen bezeichnet *werden, sind*ganzzahlige Typen, bei denen Bezeichnungen einer Teilmenge der Werte zugewiesen werden. Sie können diese anstelle von Literalen verwenden, um Code lesbarer und verwaltbarer zu machen.

## <a name="syntax"></a>Syntax

```fsharp
type enum-name =
| value1 = integer-literal1
| value2 = integer-literal2
...
```

## <a name="remarks"></a>Hinweise

Eine Enumeration sieht in etwa wie eine Unterscheidungs-Union mit einfachen Werten aus, mit dem Unterschied, dass die Werte angegeben werden können. Bei den Werten handelt es sich in der Regel um ganze Zahlen, die bei 0 oder 1 beginnen, oder ganze Zahlen, die Bitpositionen darstellen. Wenn eine Enumeration Bitpositionen darstellen soll, sollten Sie auch das [Flags](xref:System.FlagsAttribute) -Attribut verwenden.

Der zugrunde liegende Typ der Enumeration wird vom verwendeten Literaltyp bestimmt, sodass Sie z. b. Literale mit einem Suffix, z. b. `1u` , `2u` usw., für einen ganzzahligen ganzzahligen Typ ( `uint32` ) verwenden können.

Wenn Sie auf die benannten Werte verweisen, müssen Sie den Namen des Enumerationstyps selbst als Qualifizierer verwenden, d `enum-name.value1` . h., nicht nur `value1` . Dieses Verhalten unterscheidet sich von der Unterscheidungs-Unions. Dies liegt daran, dass Enumerationen immer das Attribut "Requirements [qualifiedaccess](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-requirequalifiedaccessattribute.html) " aufweisen.

Der folgende Code zeigt die Deklaration und Verwendung einer Enumeration.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2101.fs)]

Sie können Enumerationen problemlos in den zugrunde liegenden Typ konvertieren, indem Sie den entsprechenden-Operator verwenden, wie im folgenden Code gezeigt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2102.fs)]

Enumerierte Typen können einen der folgenden zugrunde liegenden Typen aufweisen: `sbyte` , `byte` , `int16` , `uint16` , `int32` , `uint32` , `int64` , `uint16` , `uint64` und `char` . Enumerationstypen werden in der .NET Framework als Typen dargestellt, die von geerbt werden `System.Enum` , die wiederum von geerbt werden `System.ValueType` . Daher handelt es sich um Werttypen, die sich auf dem Stapel oder Inline im enthaltenden Objekt befinden, und jeder Wert des zugrunde liegenden Typs ist ein gültiger Wert der Enumeration. Dies ist bei einem Muster Vergleich für Enumerationswerte von Bedeutung, da Sie ein Muster angeben müssen, das die unbenannten Werte abfängt.

Die- `enum` Funktion in der F #-Bibliothek kann verwendet werden, um einen Enumerationswert zu generieren, auch einen anderen Wert als einen der vordefinierten benannten Werte. Sie verwenden die- `enum` Funktion wie folgt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2103.fs)]

Die Standard `enum` Funktion funktioniert mit dem-Typ `int32` . Daher kann Sie nicht mit Enumerationstypen verwendet werden, die andere zugrunde liegende Typen aufweisen. Verwenden Sie stattdessen Folgendes:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2104.fs)]

Außerdem werden Fälle für-Aufgaben immer als ausgegeben `public` . Dies ist der Fall, wenn Sie sich an c# und dem Rest der .NET-Plattform orientieren.

## <a name="see-also"></a>Weitere Informationen

- [F#-Sprachreferenz](index.md)
- [Umwandlung und Konvertierungen](casting-and-conversions.md)
