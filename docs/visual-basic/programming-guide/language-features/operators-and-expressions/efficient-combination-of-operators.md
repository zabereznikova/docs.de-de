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
ms.openlocfilehash: 3088072646278dac13e4d483cb4f99297eaad9ca
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403471"
---
# <a name="efficient-combination-of-operators-visual-basic"></a>Effiziente Kombination von Operatoren (Visual Basic)
Komplexe Ausdrücke können viele verschiedene Operatoren enthalten. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 `x = (45 * (y + z)) ^ (2 / 85) * 5 + z`  
  
 Das Erstellen komplexer Ausdrücke, wie z. b. der im vorherigen Beispiel, erfordert ein umfassendes Verständnis der Regeln der Operator Rangfolge. Weitere Informationen finden Sie unter [Operator Rangfolge in Visual Basic](../../../language-reference/operators/operator-precedence.md).  
  
## <a name="parenthetical-expressions"></a>Klammer Ausdrücke  
 Häufig möchten Sie, dass Vorgänge in einer anderen Reihenfolge ausgeführt werden, die von der Operator Rangfolge bestimmt wird. Betrachten Sie das folgende Beispiel.  
  
 `x = z * y + 4`  
  
 Im vorangehenden Beispiel `z` wird mit multipliziert `y` . Anschließend wird das Ergebnis hinzugefügt `4` . Wenn Sie jedoch `y` und `4` vor dem Multiplizieren des Ergebnisses mit hinzufügen möchten `z` , können Sie die normale Operator Rangfolge mithilfe von Klammern überschreiben. Wenn Sie einen Ausdruck in Klammern einschließen, erzwingen Sie, dass dieser Ausdruck unabhängig von der Operator Rangfolge zuerst ausgewertet wird. Um das vorangehende Beispiel zu erzwingen, müssen Sie es wie im folgenden Beispiel neu schreiben.  
  
 `x = z * (y + 4)`  
  
 Im vorangehenden Beispiel `y` werden und addiert `4` . Anschließend wird diese Summe von multipliziert `z` .  
  
### <a name="nested-parenthetical-expressions"></a>Eingeklamlierte Klammer Ausdrücke  
 Sie können Ausdrücke in mehreren Ebenen von Klammern schachteln, um die Rangfolge noch weiter zu überschreiben. Die Ausdrücke, die in Klammern am tiefsten geschachtelt sind, werden zuerst ausgewertet, gefolgt von der nächst tiefen geschachtelten, usw. bis zu der am wenigsten tief geschachtelten und schließlich den Ausdrücken außerhalb der Klammern. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 `x = (z * 4) ^ (y * (z + 2))`  
  
 Im vorherigen Beispiel `z + 2` wird zuerst ausgewertet, dann die anderen Klammer Ausdrücke. Die exponentiierung, bei der normalerweise eine höhere Rangfolge als Addition oder Multiplikation fest steht, wird in diesem Beispiel zuletzt ausgewertet, da die anderen Ausdrücke in Klammern eingeschlossen werden.  
  
## <a name="see-also"></a>Weitere Informationen

- [Arithmetische Operatoren in Visual Basic](arithmetic-operators.md)
- [Comparison Operators in Visual Basic](comparison-operators.md)
- [Logische und bitweise Operatoren in Visual Basic](logical-and-bitwise-operators.md)
- [Logische/bitweise Operatoren (Visual Basic)](../../../language-reference/operators/logical-bitwise-operators.md)
- [Boolesche Ausdrücke](boolean-expressions.md)
- [Wertvergleiche](value-comparisons.md)
- [Vorgehensweise: Berechnen von numerischen Werten](how-to-calculate-numeric-values.md)
- [Operatorrangfolge in Visual Basic](../../../language-reference/operators/operator-precedence.md)
