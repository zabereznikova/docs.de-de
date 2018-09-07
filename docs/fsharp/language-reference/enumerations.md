---
title: Enumerationen (F#)
description: Erfahren Sie, wie Sie F#-Enumerationen anstelle von literalen verwenden, um den Code besser lesbar und verwaltbar zu gestalten.
ms.date: 05/16/2016
ms.openlocfilehash: 47fb353c2698f8b1474834ebbd1b0eff2c7f76e7
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44097086"
---
# <a name="enumerations"></a>Enumerationen

*Enumerationen*, auch bekannt als *Enumerationen*, integrale Typen sind, in dem Bezeichnungen auf eine Teilmenge der Werte zugewiesen werden. Sie können diese anstelle von Literalen verwenden, um Code lesbarer und verwaltbarer zu machen.

## <a name="syntax"></a>Syntax

```fsharp
type enum-name =
| value1 = integer-literal1
| value2 = integer-literal2
...
```

## <a name="remarks"></a>Hinweise

Eine Enumeration sieht ähnlich wie eine Unterscheidungs-Union, die einfache Werte, mit dem Unterschied, dass die Werte angegeben werden können. Die Werte sind in der Regel an ganzen Zahlen, die mit 0 oder 1 beginnen, oder ganze Zahlen, die Bitpositionen darstellen. Wenn eine Enumeration Bitpositionen darstellen soll, verwenden Sie auch die [Flags](xref:System.FlagsAttribute) Attribut.

Der zugrunde liegende Typ der Enumeration wird durch das Literal, das verwendet wird, bestimmt, sodass z. B. Sie z. B. Literale mit Suffix verwenden können `1u`, `2u`usw., für die ganze Zahl ohne Vorzeichen (`uint32`) Typ.

Wenn Sie auf die benannten Werte verweisen, müssen Sie die Namen verwenden des Enumerationstyps selbst als Qualifizierer, d. h. `enum-name.value1`und nicht nur `value1`. Dieses Verhalten unterscheidet sich von der Unterscheidungs-Unions. Dies ist, da-Enumerationen verfügen immer über die [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) Attribut.

Der folgende Code zeigt die Deklaration und Verwendung einer Enumeration.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2101.fs)]

Sie können problemlos Enumerationen in den zugrunde liegenden Typ konvertieren mit den geeigneten Operator an, wie im folgenden Code gezeigt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2102.fs)]

Aufgelistete Typen können einen der folgenden zugrunde liegende Typen aufweisen: `sbyte`, `byte`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`, und `char`. Enumerationstypen werden in .NET Framework dargestellt, wie Typen, die von übernommenen `System.Enum`, die wiederum von geerbt `System.ValueType`. Daher sind sie Werttypen, die auf dem Stapel oder Inline in dem Objekt gespeichert sind, und jeder Wert des zugrunde liegenden Typs ist, einen gültigen Wert der Enumeration. Dies ist wichtig, beim Musterabgleich für Enumeration Werte, denn Sie müssen ein Muster bereit, die die unbenannte Werte abfängt.

Die `enum` -Funktion in der F#-Bibliothek kann verwendet werden, um ein Enumerationswert, der auch einen anderen Wert als eine der vordefinierten, erstellen benannte Werte. Sie verwenden die `enum` -Funktion wie folgt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2103.fs)]

Der Standardwert `enum` Funktion arbeitet mit dem Typ `int32`. Es kann nicht aus diesem Grund mit Enumerationstypen verwendet werden, die andere zugrunde liegende Typen aufweisen. Verwenden Sie stattdessen die folgenden Schritte aus.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2104.fs)]

Darüber hinaus Fällen für Enumerationen immer als ausgegeben werden `public`. Dies ist so, dass sie mit c# und den Rest der .NET-Plattform ausgerichtet sind.

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [Umwandlung und Konvertierungen](casting-and-conversions.md)
