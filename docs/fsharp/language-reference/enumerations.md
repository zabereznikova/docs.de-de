---
title: Enumerationen (F#)
description: Informationen Sie zum F#-Enumerationen anstelle von literalen zu verwenden, um den Code besser lesbar und unterhaltbar zu gestalten.
ms.date: 05/16/2016
ms.openlocfilehash: 00faf6e2ad08a7b232a8ae35aa0f7deb1ba3e76a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="enumerations"></a>Enumerationen

*Enumerationen*, auch bekannt als *Enumerationen*,, sind ganzzahlige Typen, in dem Bezeichnungen auf eine Teilmenge der Werte zugewiesen werden. Sie können diese anstelle von Literalen verwenden, um Code lesbarer und verwaltbarer zu machen.


## <a name="syntax"></a>Syntax

```fsharp
type enum-name =
| value1 = integer-literal1
| value2 = integer-literal2
...
```

## <a name="remarks"></a>Hinweise
Eine Enumeration sieht ähnlich wie eine Unterscheidungs-Union, die einfache Werte verfügt, mit dem Unterschied, dass die Werte angegeben werden können. Die Werte sind in der Regel ganze Zahlen, die mit 0 oder 1 beginnen, oder ganze Zahlen enthält, die Bitpositionen darstellen. Wenn eine Enumeration Bitpositionen darstellen soll, verwenden Sie zudem die [Flags](xref:System.FlagsAttribute) Attribut.

Der zugrunde liegende Typ der Enumeration wird durch das Literal, das verwendet wird, bestimmt, sodass z. B. Sie z. B. Literale mit Suffix verwenden können `1u`, `2u`und so weiter für ganze Zahl ohne Vorzeichen (`uint32`) Typ.

Wenn Sie auf der benannten Werte verweisen, müssen Sie den Namen des Enumerationstyps selbst als verwenden einen Qualifizierer, also `enum-name.value1`, nicht nur `value1`. Dieses Verhalten unterscheidet sich von dem der Unterscheidungs-Unions. Dies ist immer Schreibberechtigung Enumerationen der [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) Attribut.

Der folgende Code zeigt die Deklaration und Verwendung einer Enumeration.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2101.fs)]

Sie können einfach Enumerationen in den zugrunde liegenden Typ konvertieren mit dem entsprechenden Operator, wie im folgenden Code gezeigt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2102.fs)]

Enumerationstypen können einen der folgenden zugrunde liegenden Typen aufweisen: `sbyte`, `byte`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`, und `char`. Enumerationstypen werden als Typen, die vom geerbt sind in .NET Framework dargestellt `System.Enum`, die wiederum geerbt wird von `System.ValueType`. Daher werden auf Werttypen, die auf dem Stapel oder Inline in dem Objekt gespeichert sind, und jeden Wert von der zugrunde liegende Typ ist ein gültiger Wert der Enumeration. Dies ist wichtig, wenn einen Mustervergleich für Enumeration Werte, weil Sie müssen ein Muster angeben, der die unbenannten Werte abfängt.

Die `enum` Funktion in der f#-Bibliothek dienen zum Generieren der einem Enumerationswert entspricht, auch einen anderen Wert als eine der vordefinierten benannten Werte. Sie verwenden die `enum` -Funktion wie folgt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2103.fs)]

Die Standardeinstellung `enum` Funktion kann mit Datentyp `int32`. Aus diesem Grund, Sie kann nicht mit Enumerationstypen verwendet werden, die andere zugrunde liegende Typen aufweisen. Verwenden Sie stattdessen die folgenden Schritte aus.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2104.fs)]
    
## <a name="see-also"></a>Siehe auch
[F#-Sprachreferenz](index.md)

[Umwandlung und Konvertierungen](casting-and-conversions.md)
