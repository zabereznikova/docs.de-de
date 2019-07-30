---
title: Typableitung
description: Erfahren Sie, F# wie der Compiler die Typen von Werten, Variablen, Parametern und Rückgabe Werten leitet.
ms.date: 05/16/2016
ms.openlocfilehash: 4b18c1a67a8b7ddadb4fb334ea4736e9fd29feb0
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630181"
---
# <a name="type-inference"></a>Typableitung

In diesem Thema wird beschrieben F# , wie der Compiler die Typen von Werten, Variablen, Parametern und Rückgabe Werten leitet.

## <a name="type-inference-in-general"></a>Typrückschluss im allgemeinen

Das Konzept der Typrückschluss ist, dass Sie keine geben die Art der F#-Konstrukte, außer wenn der Compiler allerdings den Typ hergeleitet werden kann. Explizite Typinformationen auslassen bedeutet nicht, dass F# einer dynamisch typisierten Sprache ist oder des typisierten, dass die Werte in F# sind. F#ist eine statisch typisierte Sprache. Dies bedeutet, dass der Compiler während der Kompilierung einen exakten Typ für jedes Konstrukt herleitet. Wenn nicht genügend Informationen vorhanden sind, damit der Compiler die Typen der einzelnen Konstrukte ableiten kann, müssen zusätzliche Typinformationen bereitgestellt werden, in der Regel durch das Hinzufügen von expliziten Typanmerkungen an einer beliebigen Stelle im Code.

## <a name="inference-of-parameter-and-return-types"></a>Ableiten von Parameter-und Rückgabe Typen

In einer Parameterliste müssen Sie nicht den Typ jedes Parameters angeben. Und noch F# ist eine statisch typisierte Sprache, und jeder Wert und der Ausdruck hat daher einen eindeutigen Typ zum Zeitpunkt der Kompilierung. Für die Typen, die Sie nicht explizit angeben, leitet der Compiler den Typ auf Grundlage des Kontexts ab. Wenn der Typ nicht anderweitig angegeben ist, wird er als generisch abgeleitet. Wenn der Code einen Wert inkonsistent verwendet, gibt der Compiler einen Fehler aus, wenn es keinen einzelnen, abgelegten Typ gibt, der alle Verwendungen eines Werts erfüllt.

Der Rückgabetyp einer Funktion wird durch den Typ des letzten Ausdrucks in der Funktion bestimmt.

Im folgenden Code werden z. b. die Parametertypen `a` und `b` und der Rückgabetyp als abgeleitet `int` , weil der Literaltyp `100` `int`ist.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet301.fs)]

Sie können den Typrückschluss beeinflussen, indem Sie die Literale ändern. `100` Wenn Sie das `uint32` -Suffix `u`durch Anhängen des Suffixes durch Anhängen, werden `a`die `b`Typen von `uint32`, und der Rückgabewert als abgeleitet.

Sie können den Typrückschluss auch beeinflussen, indem Sie andere Konstrukte verwenden, die Einschränkungen für den Typ implizieren, wie z. b. Funktionen und Methoden, die nur mit einem bestimmten Typ funktionieren.

Außerdem können Sie explizite Typanmerkungen auf Funktions-oder Methoden Parameter oder auf Variablen in Ausdrücken anwenden, wie in den folgenden Beispielen gezeigt. Fehler treten auf, wenn Konflikte zwischen verschiedenen Einschränkungen auftreten.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet302.fs)]

Sie können den Rückgabewert einer Funktion auch explizit angeben, indem Sie eine Typanmerkung nach allen Parametern bereitstellen.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet303.fs)]

Ein gängiger Fall, bei dem eine Typanmerkung für einen Parameter nützlich ist, ist, wenn der Parameter ein Objekttyp ist und Sie einen Member verwenden möchten.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet304.fs)]

## <a name="automatic-generalization"></a>Automatische Verallgemeinerung

Wenn der Funktionscode nicht vom Typ eines Parameters abhängt, betrachtet der Compiler den Parameter als generisch. Dies wird als *Automatische Generalisierung*bezeichnet und kann eine leistungsstarke Hilfe beim Schreiben von generischem Code sein, ohne die Komplexität zu erhöhen.

Die folgende Funktion kombiniert z. b. zwei Parameter eines beliebigen Typs in einem Tupel.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet305.fs)]

Der Typ wird als

```fsharp
'a -> 'b -> 'a * 'b
```

## <a name="additional-information"></a>Zusätzliche Informationen

Der Typrückschluss wird in der F# -Sprachspezifikation ausführlicher beschrieben.

## <a name="see-also"></a>Siehe auch

- [Automatische Verallgemeinerung](./generics/automatic-generalization.md)
