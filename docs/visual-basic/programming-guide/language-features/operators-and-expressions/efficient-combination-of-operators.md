---
title: Effiziente Kombination von Operatoren (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- expressions [Visual Basic], parentheses
- operators [Visual Basic], associativity
- expressions [Visual Basic], operators
- operators [Visual Basic], precedence
- Visual Basic code, operators
- Visual Basic code, expressions
- operators [Visual Basic], complex expressions
- expressions [Visual Basic], complex
- parentheses [Visual Basic], complex expressions
- numeric expressions
ms.assetid: bd22340e-b5be-458b-8772-3916c02309a4
ms.openlocfilehash: 8f5dd6c56b3e4576b9d798e0e5e10b2996f558dc
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58841254"
---
# <a name="efficient-combination-of-operators-visual-basic"></a>Effiziente Kombination von Operatoren (Visual Basic)
Komplexe Ausdrücke können viele verschiedene Operatoren enthalten. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 `x = (45 * (y + z)) ^ (2 / 85) * 5 + z`  
  
 Erstellen von komplexen Ausdrücken wie im vorherigen Beispiel erfordert ein tiefgreifendes Verständnis der Regeln der Operatorrangfolge. Weitere Informationen finden Sie unter [Operatorrangfolge in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).  
  
## <a name="parenthetical-expressions"></a>Ausdrücke in Klammern  
 Häufig möchten Sie die Vorgänge, die weitere Vorgehensweise in einer anderen Reihenfolge aus, die vom Operatorrangfolge bestimmt. Betrachten Sie das folgende Beispiel.  
  
 `x = z * y + 4`  
  
 Im vorherige Beispiel multipliziert `z` von `y`, fügt dann das Ergebnis an `4`. Aber wenn Sie hinzufügen möchten `y` und `4` vor dem Multiplizieren des Ergebnisses von `z`, Sie können normale Operatorrangfolge überschreiben, indem Sie Klammern verwenden. Einen Ausdruck in Klammern einschließen, erzwingen Sie, dass dieser Ausdruck unabhängig von der Operatorrangfolge zuerst ausgewertet werden. Um das vorangehende Beispiel so führen Sie zuerst das Hinzufügen zu erzwingen, können Sie ihn wie im folgenden Beispiel umschreiben.  
  
 `x = z * (y + 4)`  
  
 Im vorherige Beispiel fügt `y` und `4`, klicken Sie dann multipliziert die Summe von `z`.  
  
### <a name="nested-parenthetical-expressions"></a>Geschachtelte Ausdrücke  
 Sie können Ausdrücke in mehrere Ebenen von Klammern, um die Rangfolge noch überschrieben schachteln. Die Ausdrücke, die am tiefsten geschachtelte in Klammern werden zuerst ausgewertet, gefolgt von der nächsten am tiefsten geschachtelt, und so weiter, die am wenigsten tief verschachtelte und schließlich die Ausdrücke außerhalb der Klammern. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 `x = (z * 4) ^ (y * (z + 2))`  
  
 Im vorherigen Beispiel `z + 2` wird zuerst ausgewertet, und klicken Sie dann auf die andere Ausdrücke in Klammern. Potenzierung, die normalerweise Vorrang vor Addition oder Multiplikation hat, ist in diesem Beispiel zuletzt ausgewertet, da die anderen Ausdrücke in Klammern eingeschlossen werden.  
  
## <a name="see-also"></a>Siehe auch

- [Arithmetische Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Vergleichsoperatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Logische und bitweise Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [Logische/bitweise Operatoren (Visual Basic)](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Boolesche Ausdrücke](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [Wertvergleiche](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [Vorgehensweise: Berechnen von numerischen Werten](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../../visual-basic/language-reference/operators/operator-precedence.md)
