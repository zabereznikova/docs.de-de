---
title: 'Vorgehensweise: Vergleichen einer Zeichenfolge mit einem Muster'
ms.date: 07/20/2015
helpviewer_keywords:
- comparison operators [Visual Basic], comparing strings
- pattern matching
- strings [Visual Basic], comparing
- string comparison [Visual Basic], operators
- Visual Basic code, operators
- pattern matching [Visual Basic], string comparison
- string comparison [Visual Basic]
- Like operator [Visual Basic], pattern matching
- pattern matching, empty strings
- operators [Visual Basic], comparison
ms.assetid: 19a83804-b5af-4739-928b-ac93e64e457f
ms.openlocfilehash: d8a3c363d1a443db4a0b7633e380562af1913aca
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403445"
---
# <a name="how-to-match-a-string-against-a-pattern-visual-basic"></a>Gewusst wie: Vergleichen einer Zeichenfolge mit einem Muster (Visual Basic)

Wenn Sie herausfinden möchten, ob ein Ausdruck des [String-Datentyps](../../../language-reference/data-types/string-data-type.md) ein Muster erfüllt, können Sie den [Like-Operator](../../../language-reference/operators/like-operator.md)verwenden.

`Like`erfordert zwei Operanden. Der linke Operand ist ein Zeichen folgen Ausdruck, und der rechte Operand ist eine Zeichenfolge mit dem Muster, das für den Abgleich verwendet werden soll. `Like`Gibt einen Wert zurück, der `Boolean` angibt, ob der Zeichen folgen Ausdruck dem Muster entspricht.

Sie können jedes Zeichen im Zeichen folgen Ausdruck mit einem bestimmten Zeichen, einem Platzhalter Zeichen, einer Zeichen Liste oder einem Zeichenbereich vergleichen. Die Positionen der Spezifikationen in der Muster Zeichenfolge entsprechen den Positionen der Zeichen, die im Zeichen folgen Ausdruck abgeglichen werden sollen.

## <a name="to-match-a-character-in-the-string-expression-against-a-specific-character"></a>So passen Sie ein Zeichen im Zeichen folgen Ausdruck mit einem bestimmten Zeichen an

Fügen Sie das jeweilige Zeichen direkt in die Muster Zeichenfolge ein. Bestimmte Sonderzeichen müssen in eckige Klammern () eingeschlossen werden `[ ]` . Weitere Informationen finden Sie unter [Like-Operator](../../../language-reference/operators/like-operator.md).

Im folgenden Beispiel wird getestet, ob `myString` genau aus dem einzelnen Zeichen besteht `H` .

[!code-vb[VbVbalrOperators#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#70)]

## <a name="to-match-a-character-in-the-string-expression-against-a-wildcard-character"></a>So passen Sie ein Zeichen im Zeichen folgen Ausdruck mit einem Platzhalter Zeichen an

Legen Sie ein Fragezeichen ( `?` ) in der Muster Zeichenfolge ab. Ein beliebiges gültiges Zeichen an dieser Position stimmt erfolgreich ab.

Im folgenden Beispiel wird getestet, ob `myString` aus dem einzelnen Zeichen besteht, auf das `W` genau zwei Zeichen von Werten folgen.

[!code-vb[VbVbalrOperators#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#71)]

## <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters"></a>So passen Sie ein Zeichen im Zeichen folgen Ausdruck mit einer Liste von Zeichen an

Legen Sie eckige Klammern ( `[ ]` ) in der Muster Zeichenfolge ab, und legen Sie in den Klammern die Zeichen Liste ab. Trennen Sie die Zeichen nicht durch Kommas oder andere Trennzeichen. Alle einzelnen Zeichen in der Liste Stimmen erfolgreich ab.

Im folgenden Beispiel wird getestet `myString` , ob aus einem gültigen Zeichen, gefolgt von genau einem der Zeichen `A` , oder, besteht `C` `E` .

[!code-vb[VbVbalrOperators#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#72)]

Beachten Sie, dass die Groß-/Kleinschreibung beachtet wird.

## <a name="to-match-a-character-in-the-string-expression-against-a-range-of-characters"></a>So passen Sie ein Zeichen im Zeichen folgen Ausdruck mit einem Zeichenbereich an

Legen Sie eckige Klammern ( `[ ]` ) in der Muster Zeichenfolge ab, und legen Sie in den Klammern die niedrigsten und höchsten Zeichen im Bereich ab, getrennt durch einen Bindestrich ( `–` ). Alle einzelnen Zeichen innerhalb des Bereichs Stimmen erfolgreich ab.

Im folgenden Beispiel wird getestet, ob `myString` aus den Zeichen besteht, auf die `num` genau eines der Zeichen `i` , `j` , `k` ,, oder folgt `l` `m` `n` .

[!code-vb[VbVbalrOperators#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#73)]

Beachten Sie, dass die Groß-/Kleinschreibung beachtet wird.

## <a name="matching-empty-strings"></a>Vergleichen von leeren Zeichen folgen

`Like`behandelt die Sequenz `[]` als Zeichenfolge der Länge 0 (NULL `""` ). Sie können verwenden, `[]` um zu testen, ob der gesamte Zeichen folgen Ausdruck leer ist, Sie können ihn jedoch nicht verwenden, um zu testen, ob eine bestimmte Position im Zeichen folgen Ausdruck leer ist. Wenn eine leere Position eine der Optionen ist, die Sie testen müssen, können Sie mehrmals verwenden `Like` .

### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters-or-no-character"></a>So passen Sie ein Zeichen im Zeichen folgen Ausdruck mit einer Liste von Zeichen oder ohne Zeichen an

1. Rufen Sie den `Like` Operator zweimal für denselben Zeichen folgen Ausdruck auf, und verbinden Sie die beiden Aufrufe entweder mit dem [OR-Operator](../../../language-reference/operators/or-operator.md) oder dem [OrElse-Operator](../../../language-reference/operators/orelse-operator.md).

2. Fügen Sie in der Muster Zeichenfolge für die erste `Like` Klausel die Zeichen Liste in eckige Klammern ( `[ ]` ) ein.

3. Fügen Sie in der Muster Zeichenfolge für die zweite `Like` Klausel kein Zeichen an der fraglichen Position ein.

    Im folgenden Beispiel wird die siebenstellige Telefonnummer `phoneNum` für genau drei numerische Ziffern, gefolgt von einem Leerzeichen, einem Bindestrich ( `–` ), einem Punkte ( `.` ) oder keinem Zeichen, gefolgt von genau vier numerischen Ziffern getestet.

    [!code-vb[VbVbalrOperators#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#74)]

## <a name="see-also"></a>Weitere Informationen

- [Vergleichs Operatoren](../../../language-reference/operators/comparison-operators.md)
- [Operatoren und Ausdrücke](index.md)
- [Like-Operator](../../../language-reference/operators/like-operator.md)
- [String-Datentyp](../../../language-reference/data-types/string-data-type.md)
