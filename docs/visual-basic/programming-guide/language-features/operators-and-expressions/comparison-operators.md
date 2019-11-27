---
title: Vergleichsoperatoren
ms.date: 07/20/2015
helpviewer_keywords:
- comparison operators [Visual Basic], comparing strings
- comparison operators [Visual Basic], comparing objects
- strings [Visual Basic], comparing
- comparison operators [Visual Basic]
- string comparison [Visual Basic], operators
- objects [Visual Basic], comparing
- numbers [Visual Basic], comparing
- Visual Basic code, operators
- string comparison [Visual Basic]
- numeric values [Visual Basic], comparing
- comparison operators [Visual Basic], comparing numeric values
- operators [Visual Basic], comparison
ms.assetid: 0b570339-5407-474f-8421-e183a8b303ee
ms.openlocfilehash: e1feb08539e47ec6fda64aa1a1f8ec2cc19f7b62
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346066"
---
# <a name="comparison-operators-in-visual-basic"></a>Vergleichsoperatoren in Visual Basic
Vergleichs Operatoren vergleichen zwei Ausdrücke und geben einen `Boolean` Wert zurück, der die Beziehung ihrer Werte darstellt. Es gibt Operatoren zum Vergleichen numerischer Werte, Operatoren zum Vergleichen von Zeichen folgen und Operatoren zum Vergleichen von Objekten. Alle drei Typen von Operatoren werden in diesem Artikel erläutert.  
  
## <a name="comparing-numeric-values"></a>Vergleichen von numerischen Werten  
 Visual Basic vergleicht numerische Werte mithilfe von sechs numerischen Vergleichs Operatoren. Jeder Operator übernimmt zwei Ausdrücke, die zu numerischen Werten ausgewertet werden. In der folgenden Tabelle werden die Operatoren aufgelistet und Beispiele für jeden angezeigt.  
  
|Operator|Bedingung getestet|Beispiele|  
|--------------|----------------------|--------------|  
|`=` (Gleichheit)|Ist der Wert des ersten Ausdrucks gleich dem Wert des zweiten Ausdrucks?|`23`   `=`   `33    ' False`<br /><br /> `23`   `=`   `23    ' True`<br /><br /> `23`   `=`   `12    ' False`|  
|`<>` (Ungleichheit)|Ist der Wert des ersten Ausdrucks ungleich dem Wert des zweiten Ausdrucks?|`23`   `<>`   `33    ' True`<br /><br /> `23`   `<>`   `23    ' False`<br /><br /> `23`   `<>`   `12    ' True`|  
|`<` (kleiner als)|Ist der Wert des ersten Ausdrucks kleiner als der Wert des zweiten Ausdrucks?|`23`   `<`   `33    ' True`<br /><br /> `23`   `<`   `23    ' False`<br /><br /> `23`   `<`   `12    ' False`|  
|`>` (größer als)|Ist der Wert des ersten Ausdrucks größer als der Wert des zweiten Ausdrucks?|`23`   `>`   `33    ' False`<br /><br /> `23`   `>`   `23    ' False`<br /><br /> `23`   `>`   `12    ' True`|  
|`<=` (kleiner als oder gleich)|Ist der Wert des ersten Ausdrucks kleiner oder gleich dem Wert des zweiten Ausdrucks?|`23`   `<=`   `33    ' True`<br /><br /> `23`   `<=`   `23    ' True`<br /><br /> `23`   `<=`   `12    ' False`|  
|`>=` (größer als oder gleich)|Ist der Wert des ersten Ausdrucks größer oder gleich dem Wert des zweiten Ausdrucks?|`23`   `>=`   `33    ' False`<br /><br /> `23`   `>=`   `23    ' True`<br /><br /> `23`   `>=`   `12    ' True`|  
  
## <a name="comparing-strings"></a>Vergleichen von Zeichenfolgen  
 Visual Basic vergleicht Zeichen folgen mit dem [Like-Operator](../../../../visual-basic/language-reference/operators/like-operator.md) und den numerischen Vergleichs Operatoren. Mit dem `Like`-Operator können Sie ein Muster angeben. Die Zeichenfolge wird dann mit dem Muster verglichen, und wenn Sie übereinstimmt, wird das Ergebnis `True`. Andernfalls ist das Ergebnis `False`. Mit den numerischen Operatoren können Sie `String` Werte basierend auf Ihrer Sortierreihenfolge vergleichen, wie im folgenden Beispiel gezeigt.  
  
 `"73" < "9"`  
  
 `' The result of the preceding comparison is True.`  
  
 Das Ergebnis im vorangehenden Beispiel ist `True`, da das erste Zeichen in der ersten Zeichenfolge vor dem ersten Zeichen in der zweiten Zeichenfolge sortiert. Wenn die ersten Zeichen gleich sind, wird der Vergleich mit dem nächsten Zeichen in beiden Zeichen folgen usw. fortgesetzt. Sie können auch die Gleichheit von Zeichen folgen mithilfe des Gleichheits Operators testen, wie im folgenden Beispiel gezeigt.  
  
 `"734" = "734"`  
  
 `' The result of the preceding comparison is True.`  
  
 Wenn eine Zeichenfolge ein Präfix einer anderen Zeichenfolge ist, z. b. "AA" und "AAA", wird die längere Zeichenfolge als größer als die kürzere Zeichenfolge betrachtet. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 `"aaa" > "aa"`  
  
 `' The result of the preceding comparison is True.`  
  
 Die Sortierreihenfolge basiert entweder auf einem binären Vergleich oder einem Textvergleich, abhängig von der Einstellung `Option Compare`. Weitere Informationen finden Sie unter [Option Compare-Anweisung](../../../../visual-basic/language-reference/statements/option-compare-statement.md).  
  
## <a name="comparing-objects"></a>Vergleichen von Objekten  
 Visual Basic vergleicht zwei Objekt Verweis Variablen mit dem [is-Operator](../../../../visual-basic/language-reference/operators/is-operator.md) und dem [IsNot-Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md). Sie können einen dieser Operatoren verwenden, um zu bestimmen, ob zwei Verweis Variablen auf dieselbe Objektinstanz verweisen. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#65)]  
  
 Im vorherigen Beispiel wird `x Is y` als `True`ausgewertet, da beide Variablen auf dieselbe Instanz verweisen. Vergleichen Sie dieses Ergebnis mit dem folgenden Beispiel.  
  
 [!code-vb[VbVbalrOperators#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#66)]  
  
 Im vorherigen Beispiel wird `x Is y` als `False`ausgewertet, da die Variablen zwar auf Objekte desselben Typs verweisen, aber auf verschiedene Instanzen dieses Typs verweisen.  
  
 Wenn Sie testen möchten, dass zwei Objekte nicht auf dieselbe Instanz verweisen, können Sie mit dem `IsNot`-Operator eine nicht ungeschickte Kombination von `Not` und `Is`vermeiden. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#67)]  
  
 Im vorhergehenden Beispiel entspricht `If a IsNot b` `If Not a Is b`.  
  
### <a name="comparing-object-type"></a>Vergleichen des Objekt Typs  
 Sie können überprüfen, ob ein Objekt einen bestimmten Typ mit dem `TypeOf`...`Is` Ausdruck hat. Die Syntax lautet wie folgt:  
  
 `TypeOf <objectexpression> Is <typename>`  
  
 Wenn `typename` einen Schnittstellentyp angibt, gibt der `TypeOf`...`Is` Ausdruck `True` zurück, wenn das Objekt den Schnittstellentyp implementiert. Wenn `typename` ein Klassentyp ist, gibt der Ausdruck `True` zurück, wenn das Objekt eine Instanz der angegebenen Klasse oder einer Klasse ist, die von der angegebenen Klasse abgeleitet ist. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#68)]  
  
 Im vorherigen Beispiel wird der `TypeOf x Is Control` Ausdruck zu `True` ausgewertet, da der Typ des `x` `Button`ist, der von `Control`erbt.  
  
 Weitere Informationen finden Sie unter [typeof-Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md).  
  
## <a name="see-also"></a>Siehe auch

- [Wertvergleiche](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [Vergleichsoperatoren](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [Operatoren](../../../../visual-basic/language-reference/operators/index.md)
- [Arithmetische Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Verkettungs Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
- [Logische und bitweise Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
