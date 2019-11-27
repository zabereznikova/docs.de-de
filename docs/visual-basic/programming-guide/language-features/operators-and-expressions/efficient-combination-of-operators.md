---
title: Effiziente Kombination von Operatoren
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
ms.openlocfilehash: 83ad53e4c75490a75eba0f80a6bf0f078aa4d426
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348993"
---
# <a name="efficient-combination-of-operators-visual-basic"></a>Effiziente Kombination von Operatoren (Visual Basic)
Komplexe Ausdrücke können viele verschiedene Operatoren enthalten. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 `x = (45 * (y + z)) ^ (2 / 85) * 5 + z`  
  
 Das Erstellen komplexer Ausdrücke, wie z. b. der im vorherigen Beispiel, erfordert ein umfassendes Verständnis der Regeln der Operator Rangfolge. Weitere Informationen finden Sie unter [Operator Rangfolge in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).  
  
## <a name="parenthetical-expressions"></a>Klammer Ausdrücke  
 Häufig möchten Sie, dass Vorgänge in einer anderen Reihenfolge ausgeführt werden, die von der Operator Rangfolge bestimmt wird. Betrachten Sie das folgende Beispiel.  
  
 `x = z * y + 4`  
  
 Im vorherigen Beispiel wird `z` mit `y`multipliziert und das Ergebnis dann `4`hinzugefügt. Wenn Sie jedoch `y` und `4` hinzufügen möchten, bevor Sie das Ergebnis mit `z`multiplizieren, können Sie die normale Operator Rangfolge mithilfe von Klammern überschreiben. Wenn Sie einen Ausdruck in Klammern einschließen, erzwingen Sie, dass dieser Ausdruck unabhängig von der Operator Rangfolge zuerst ausgewertet wird. Um das vorangehende Beispiel zu erzwingen, müssen Sie es wie im folgenden Beispiel neu schreiben.  
  
 `x = z * (y + 4)`  
  
 Im vorangehenden Beispiel werden `y` und `4`hinzugefügt. Anschließend wird diese Summe mit `z`multipliziert.  
  
### <a name="nested-parenthetical-expressions"></a>Eingeklamlierte Klammer Ausdrücke  
 Sie können Ausdrücke in mehreren Ebenen von Klammern schachteln, um die Rangfolge noch weiter zu überschreiben. Die Ausdrücke, die in Klammern am tiefsten geschachtelt sind, werden zuerst ausgewertet, gefolgt von der nächst tiefen geschachtelten, usw. bis zu der am wenigsten tief geschachtelten und schließlich den Ausdrücken außerhalb der Klammern. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 `x = (z * 4) ^ (y * (z + 2))`  
  
 Im vorherigen Beispiel wird `z + 2` zuerst ausgewertet, dann die anderen Klammer Ausdrücke. Die exponentiierung, bei der normalerweise eine höhere Rangfolge als Addition oder Multiplikation fest steht, wird in diesem Beispiel zuletzt ausgewertet, da die anderen Ausdrücke in Klammern eingeschlossen werden.  
  
## <a name="see-also"></a>Siehe auch

- [Arithmetische Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Vergleichs Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Logische und bitweise Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [Logische/bitweise Operatoren (Visual Basic)](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Boolesche Ausdrücke](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [Wertvergleiche](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [Gewusst wie: Berechnen von numerischen Werten](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../../visual-basic/language-reference/operators/operator-precedence.md)
