---
title: Typrückschluss (F#)
description: Erfahren Sie, wie der f#-Compiler die Typen von Werten, Variablen, Parameter und Rückgabewerte ableitet.
ms.date: 05/16/2016
ms.openlocfilehash: 93e1568ebe71436ad8f7119ac9d9628cdf58012a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="type-inference"></a>Typableitung

In diesem Thema wird beschrieben, wie der f#-Compiler die Typen von Werten, Variablen, Parameter und Rückgabewerte ableitet.

## <a name="type-inference-in-general"></a>Im Allgemeinen den Typrückschluss
Das Konzept der Typrückschluss ist, dass Sie keine geben die Typen von f#-Konstrukte, außer wenn der Compiler eindeutig den Typ ableiten kann. Weglassen von expliziten Typinformationen bedeutet nicht, dass f# eine dynamisch typisierte Sprache ist, dass Werte in f# schwach typisiert. F# ist eine statisch typisierte Sprache, d. h. leitet der Compiler einen genauen Typ für jedes Konstrukts während der Kompilierung. Wenn es keine ausreichenden Informationen für den Compiler sind an, die Typen von jedes Konstrukts hergeleitet werden, müssen Sie zusätzliche Typinformationen durch Hinzufügen von Anmerkungen zum expliziten Typ an einer beliebigen Stelle im Code in der Regel angeben.


## <a name="inference-of-parameter-and-return-types"></a>Inferenz von Parameter- und Rückgabetypen
In einer Parameterliste müssen Sie nicht den Typ jedes Parameters angeben. Noch f# eine statisch typisierte Sprache ist und daher jeder Wert und einen Ausdruck verfügt über einen bestimmten Typ zum Zeitpunkt der Kompilierung. Für diese Typen, die Sie nicht explizit angeben, leitet der Compiler den Typ auf Grundlage des Kontexts. Wenn der Typ nicht anderweitig angegeben ist, wird er generisch sein abgeleitet. Wenn der Code einen Wert inkonsistent verwendet wird, ergibt sich keine einzelne abgeleitet so Typ, der alle Vorkommen eines Werts entspricht der Compiler einen Fehler meldet.

Der Rückgabetyp einer Funktion wird durch den Typ des letzten Ausdrucks in der Funktion bestimmt.

Beispielsweise in den folgenden Code, der Parametertypen `a` und `b` und der Rückgabetyp abgeleitet, werden `int` da das Literal `100` ist vom Typ `int`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet301.fs)]

Sie können den Typrückschluss beeinflussen, indem Sie die Literale ändern. Wenn Sie stellen die `100` eine `uint32` durch das Suffix Anfügen `u`, die Typen von `a`, `b`, und der Rückgabewert abgeleitet werden `uint32`.

Sie können auch beeinflussen, Typrückschluss mithilfe anderer Konstrukte, die die Einschränkungen für den Typ, z. B. Funktionen und Methoden, die für die Arbeit mit nur einem bestimmten Typ implizieren.

Darüber hinaus können Sie explizite typanmerkungen Funktion oder Methode Parametern oder Variablen in Ausdrücken, anwenden wie in den folgenden Beispielen gezeigt. Fehler führen, wenn Konflikte zwischen verschiedenen Einschränkungen auftreten.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet302.fs)]

Sie können den Rückgabewert einer Funktion auch explizit angeben, indem er einer typanmerkung Startwerte der Parameter.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet303.fs)]

Ein häufiges Szenario, in dem eine typanmerkung hilfreich, wenn ein Parameter ist, ist, wenn der Parameter ein Objekt ist, und Sie ein Element verwenden möchten.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet304.fs)]
    
## <a name="automatic-generalization"></a>Automatische Verallgemeinerung
Wenn Sie der Funktionscode nicht den Typ eines Parameters abhängig ist, betrachtet der Compiler Parameters generisch sein. Hierbei spricht *automatische Verallgemeinerung*, und es kann eine leistungsstarke Hilfe beim Schreiben von generischem Code ohne die Komplexität erhöhen.

Zum Beispiel kombiniert die folgende Funktion zwei Parameter eines beliebigen Typs in ein Tupel.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet305.fs)]

Der Typ wird abgeleitet werden

```fsharp
'a -> 'b -> 'a * 'b
```

## <a name="additional-information"></a>Zusätzliche Informationen
Typrückschluss wird in der f#-Sprachspezifikation ausführlicher beschrieben.


## <a name="see-also"></a>Siehe auch
[Automatische Verallgemeinerung](generics/automatic-generalization.md)
