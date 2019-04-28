---
title: Vergleichsoperatoren in Visual Basic
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
ms.openlocfilehash: d08974a929a723d4037300f9d72ae03c072d47fa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61827956"
---
# <a name="comparison-operators-in-visual-basic"></a>Vergleichsoperatoren in Visual Basic
Vergleichsoperatoren vergleichen zwei Ausdrücke und Zurückgeben einer `Boolean` Wert, der die Beziehung zwischen ihren Werten darstellt. Es sind Operatoren zum Vergleichen von numerischen Werten, Operatoren zum Vergleichen von Zeichenfolgen und Operatoren zum Vergleichen von Objekten. Alle drei Arten von Operatoren werden in diesem Dokument erläutert.  
  
## <a name="comparing-numeric-values"></a>Vergleichen numerischer Werte  
 Visual Basic vergleicht numerische Werte, die sechs numerischen Vergleichsoperatoren verwenden. Jeder Operator, die als Operanden akzeptiert zwei Ausdrücke, die numerische Werte ergeben. In der folgende Tabelle sind die Operatoren aufgeführt, und zeigt Beispiele für jeden.  
  
|Operator|Bedingung getestet|Beispiele|  
|--------------|----------------------|--------------|  
|`=` (Gleich)|Ist der Wert des ersten Ausdrucks gleich dem Wert des zweiten an?|`23`   `=`   `33    ' False`<br /><br /> `23`   `=`   `23    ' True`<br /><br /> `23`   `=`   `12    ' False`|  
|`<>` (Ungleichheit)|Ist der Wert des ersten Ausdrucks ungleich dem Wert des zweiten?|`23`   `<>`   `33    ' True`<br /><br /> `23`   `<>`   `23    ' False`<br /><br /> `23`   `<>`   `12    ' True`|  
|`<` (Kleiner als)|Ist der Wert des ersten Ausdrucks kleiner als der Wert des zweiten?|`23`   `<`   `33    ' True`<br /><br /> `23`   `<`   `23    ' False`<br /><br /> `23`   `<`   `12    ' False`|  
|`>` (Größer als)|Ist der Wert des ersten Ausdrucks größer als der Wert des zweiten?|`23`   `>`   `33    ' False`<br /><br /> `23`   `>`   `23    ' False`<br /><br /> `23`   `>`   `12    ' True`|  
|`<=` (Kleiner als oder gleich)|Ist der Wert des ersten Ausdrucks kleiner oder gleich dem Wert des zweiten?|`23`   `<=`   `33    ' True`<br /><br /> `23`   `<=`   `23    ' True`<br /><br /> `23`   `<=`   `12    ' False`|  
|`>=` (Größer als oder gleich)|Ist der Wert des ersten Ausdrucks, größer als oder gleich dem Wert des zweiten?|`23`   `>=`   `33    ' False`<br /><br /> `23`   `>=`   `23    ' True`<br /><br /> `23`   `>=`   `12    ' True`|  
  
## <a name="comparing-strings"></a>Vergleichen von Zeichenfolgen  
 Visual Basic vergleicht Zeichenfolgen unter Verwendung der [Like-Operator](../../../../visual-basic/language-reference/operators/like-operator.md) sowie den numerischen Vergleichsoperatoren. Die `Like` -Operator können Sie ein Muster angegeben. Die Zeichenfolge wird dann mit dem Muster verglichen, und wenn sie übereinstimmt, wird das Ergebnis ist `True`. Andernfalls ist das Ergebnis `False`. Numerischen Operatoren können Sie die vergleichen `String` Werte basierend auf der Sortierreihenfolge auf, wie im folgenden Beispiel gezeigt.  
  
 `"73" < "9"`  
  
 `' The result of the preceding comparison is True.`  
  
 Das Ergebnis im vorherigen Beispiel ist `True` , da das erste Zeichen in der ersten Zeichenfolge vor dem ersten Zeichen in der zweiten Zeichenfolge sortiert. Wenn die erste Zeichen gleich wären, würde der Vergleich weiterhin auf das nächste Zeichen in Zeichenfolgen und so weiter. Sie können auch den Equality-Operator, wie im folgenden Beispiel gezeigt mit Zeichenfolgen auf Gleichheit testen.  
  
 `"734" = "734"`  
  
 `' The result of the preceding comparison is True.`  
  
 Wenn eine Zeichenfolge einer anderen vorangestellt, wie z. B. "aa" und "aaa", gilt die längere Zeichenfolge größer als die kürzere Zeichenfolge sein. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 `"aaa" > "aa"`  
  
 `' The result of the preceding comparison is True.`  
  
 Die Sortierreihenfolge basiert auf einen binären Vergleich oder einen Textvergleich entsprechend der Einstellung von `Option Compare`. Weitere Informationen finden Sie unter [Option Compare-Anweisung](../../../../visual-basic/language-reference/statements/option-compare-statement.md).  
  
## <a name="comparing-objects"></a>Vergleichen von Objekten  
 Visual Basic vergleicht zwei Objektverweisvariablen mit der [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) und [IsNot-Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md). Sie können entweder diese Operatoren verwenden, um festzustellen, ob die beiden Verweisvariablen auf die gleiche Objektinstanz verweisen. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#65)]  
  
 Im vorherigen Beispiel `x Is y` ergibt `True`, da beide Variablen auf dieselbe Instanz verweisen. Vergleichen Sie dieses Ergebnis mit dem folgenden Beispiel an.  
  
 [!code-vb[VbVbalrOperators#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#66)]  
  
 Im vorherigen Beispiel `x Is y` ergibt `False`, da auch die Variablen auf Objekte des gleichen Typs verweisen, verschiedene Instanzen dieses Typs zu verweisen.  
  
 Wenn Sie für zwei Objekte, die nicht auf dieselbe Instanz verweisen testen möchten die `IsNot` -Operator können Sie eine umständliche Grammatik einer Kombination von vermeiden `Not` und `Is`. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#67)]  
  
 Im vorherigen Beispiel `If a IsNot b` entspricht `If Not a Is b`.  
  
### <a name="comparing-object-type"></a>Vergleichen des Objekttyps  
 Sie können testen, ob ein Objekt eines bestimmten Typs mit dem `TypeOf`... `Is` Ausdruck. Die Syntax lautet wie folgt:  
  
 `TypeOf <objectexpression> Is <typename>`  
  
 Wenn `typename` gibt an, einen Schnittstellentyp, und klicken Sie dann die `TypeOf`... `Is` gibt `True` Wenn das Objekt den Schnittstellentyp implementiert. Wenn `typename` ein Klassentyp ist, gibt der Ausdruck `True` Wenn das Objekt eine Instanz der angegebenen Klasse oder einer Klasse, die aus der angegebenen Klasse abgeleitet ist. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#68)]  
  
 Im vorherigen Beispiel das `TypeOf x Is Control` Ausdruck wird zu `True` da der Typ des `x` ist `Button`, erbt von `Control`.  
  
 Weitere Informationen finden Sie unter [TypeOf-Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md).  
  
## <a name="see-also"></a>Siehe auch

- [Wertvergleiche](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [Vergleichsoperatoren](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [Operatoren](../../../../visual-basic/language-reference/operators/index.md)
- [Arithmetische Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Verkettungsoperatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
- [Logische und bitweise Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
