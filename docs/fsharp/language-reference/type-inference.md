---
title: Typableitung
description: Erfahren Sie, wie die F# leitet der Compiler die Typen von Werten, Variablen, Parameter und Rückgabewerte.
ms.date: 05/16/2016
ms.openlocfilehash: ab1a4aa8df4312287df749d5d6d0ea2858091152
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641678"
---
# <a name="type-inference"></a>Typableitung

In diesem Thema wird beschrieben, wie die F# leitet der Compiler die Typen von Werten, Variablen, Parameter und Rückgabewerte.

## <a name="type-inference-in-general"></a>Im Allgemeinen den Typrückschluss

Das Konzept der Typrückschluss ist, dass Sie keine geben die Art der F#-Konstrukte, außer wenn der Compiler allerdings den Typ hergeleitet werden kann. Explizite Typinformationen auslassen bedeutet nicht, dass F# einer dynamisch typisierten Sprache ist oder des typisierten, dass die Werte in F# sind. F#ist eine statisch typisierte Sprache, was bedeutet, dass der Compiler einen genauen Typ für jedes Konstrukt während der Kompilierung ableitet. Wenn nicht genügend Informationen, damit der Compiler die Typen von jedes Konstrukts Herleiten vorhanden ist, müssen Sie zusätzliche Typinformationen in der Regel angeben, indem Sie explizite Typen an einer beliebigen Stelle im Code hinzufügen.

## <a name="inference-of-parameter-and-return-types"></a>Inferenz von Parameter- und Rückgabetypen

In einer Parameterliste müssen Sie nicht den Typ jedes Parameters angeben. Und noch F# ist eine statisch typisierte Sprache, und jeder Wert und der Ausdruck hat daher einen eindeutigen Typ zum Zeitpunkt der Kompilierung. Für diese Typen, die Sie nicht explizit angeben, leitet der Compiler den Typ auf Grundlage des Kontexts. Wenn der Typ nicht nichts anderes angegeben ist, wird es abgeleitet generisch sein. Wenn der Code einen Wert nicht einheitlich verwendet, dass kein einzelner abgeleitet so Typ, der alle Vorkommen eines Werts, entspricht der Compiler einen Fehler meldet.

Der Rückgabetyp einer Funktion wird durch den Typ des letzten Ausdrucks in der Funktion bestimmt.

Beispielsweise in den folgenden Code, die Parametertypen `a` und `b` und der Rückgabetyp abgeleitet, werden `int` da das Literal `100` ist vom Typ `int`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet301.fs)]

Sie können den Typrückschluss beeinflussen, ändern Sie die Literale. Wenn Sie ändern die `100` eine `uint32` durch Anfügen des Suffixes `u`, die Typen von `a`, `b`, und der zurückgegebene Wert abgeleitet werden `uint32`.

Sie können auch beeinflussen den Typrückschluss mit anderen Konstrukten, die die Einschränkungen für den Typ, z. B. Funktionen und Methoden, die Arbeit mit nur einem bestimmten Typ implizieren.

Außerdem können Sie explizite Typen Funktion oder Methode Parameter oder Variablen in Ausdrücken, gelten wie in den folgenden Beispielen gezeigt. Fehler führen, wenn Konflikte zwischen verschiedenen Einschränkungen auftreten.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet302.fs)]

Sie können auch explizit den Rückgabewert einer Funktion angeben, durch die Bereitstellung einer typanmerkung schließlich die Parameter.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet303.fs)]

Ein häufiges Szenario, in denen eine typanmerkung für einen Parameter eignet, ist der Parameter ist ein Objekt, und Sie ein Element verwenden möchten.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet304.fs)]

## <a name="automatic-generalization"></a>Automatische Verallgemeinerung

Ist der Funktionscode nicht abhängig von dem Typ eines Parameters, betrachtet der Compiler den Parameter, um generisch sein. Dies wird als bezeichnet *automatische Verallgemeinerung*, und es kann sein, eine leistungsstarke Hilfe beim Schreiben von generischem Code ohne die Komplexität erhöhen.

Die folgende Funktion kombiniert beispielsweise zwei Parameter eines beliebigen Typs in ein Tupel.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet305.fs)]

Der Typ wird abgeleitet werden

```fsharp
'a -> 'b -> 'a * 'b
```

## <a name="additional-information"></a>Zusätzliche Informationen

Typrückschluss wird ausführlicher beschrieben. die F# -Sprachspezifikation.

## <a name="see-also"></a>Siehe auch

- [Automatische Verallgemeinerung](generics/automatic-generalization.md)
