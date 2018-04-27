---
title: Vergleichsoperatoren in Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 77c5520be63d6d05cc4b895b99b466cd8e486f6a
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="comparison-operators-in-visual-basic"></a>Vergleichsoperatoren in Visual Basic
Vergleichsoperatoren vergleichen zwei Ausdrücke und Zurückgeben einer `Boolean` Wert, der die Beziehung zwischen ihren Werten darstellt. Es sind Operatoren zum Vergleichen von numerischen Werten, Operatoren zum Vergleichen von Zeichenfolgen und Operatoren zum Vergleichen von Objekten. Alle drei Typen von Operatoren werden in diesem Dokument erläutert.  
  
## <a name="comparing-numeric-values"></a>Vergleichen von numerischen Werten  
 Visual Basic werden numerische Werte mit sechs numerischen Vergleichsoperatoren verglichen. Jeder Operator akzeptiert zwei Ausdrücke, die numerische Werte ergeben, als Operanden aus. In der folgenden Tabelle werden die Operatoren aufgeführt, und zeigt Beispiele für jeden.  
  
|Operator|Bedingung getestet|Beispiele|  
|--------------|----------------------|--------------|  
|`=` (Gleich)|Ist der Wert des ersten Ausdrucks gleich dem Wert des zweiten?|`23`   `=`   `33    ' False`<br /><br /> `23`   `=`   `23    ' True`<br /><br /> `23`   `=`   `12    ' False`|  
|`<>` (Ungleichheit)|Ist der Wert des ersten Ausdrucks ungleich dem Wert des zweiten?|`23`   `<>`   `33    ' True`<br /><br /> `23`   `<>`   `23    ' False`<br /><br /> `23`   `<>`   `12    ' True`|  
|`<` (Kleiner als)|Ist der Wert des ersten Ausdrucks kleiner als der Wert des zweiten?|`23`   `<`   `33    ' True`<br /><br /> `23`   `<`   `23    ' False`<br /><br /> `23`   `<`   `12    ' False`|  
|`>` (Größer als)|Ist der Wert des ersten Ausdrucks größer als der Wert des zweiten?|`23`   `>`   `33    ' False`<br /><br /> `23`   `>`   `23    ' False`<br /><br /> `23`   `>`   `12    ' True`|  
|`<=` (Kleiner als oder gleich)|Ist der Wert des ersten Ausdrucks kleiner oder gleich dem Wert des zweiten?|`23`   `<=`   `33    ' True`<br /><br /> `23`   `<=`   `23    ' True`<br /><br /> `23`   `<=`   `12    ' False`|  
|`>=` (Größer als oder gleich)|Ist der Wert des ersten Ausdrucks, größer als oder gleich dem Wert des zweiten?|`23`   `>=`   `33    ' False`<br /><br /> `23`   `>=`   `23    ' True`<br /><br /> `23`   `>=`   `12    ' True`|  
  
## <a name="comparing-strings"></a>Vergleichen von Zeichenfolgen  
 Visual Basic vergleicht Zeichenfolgen mithilfe der [Like-Operator](../../../../visual-basic/language-reference/operators/like-operator.md) sowie die numerische Vergleichsoperatoren. Die `Like` Operators können Sie ein Muster angeben. Die Zeichenfolge wird dann mit dem Muster verglichen, und wenn es übereinstimmt, ist das Ergebnis `True`. Andernfalls entsteht `False`. Numerische Operatoren können Sie die vergleichen `String` Werte basierend auf ihrer Sortierreihenfolge wie im folgenden Beispiel gezeigt.  
  
 `"73" < "9"`  
  
 `' The result of the preceding comparison is True.`  
  
 Das Ergebnis im vorherigen Beispiel ist `True` , da das erste Zeichen in der ersten Zeichenfolge vor dem ersten Zeichen in der zweiten Zeichenfolge sortiert. Wären die ersten Zeichen entspricht, würde der Vergleich weiterhin das nächste Zeichen in Zeichenfolgen und so weiter. Sie können auch Testen der Gleichheit von Zeichenfolgen, die mit dem Gleichheitsoperator, wie im folgenden Beispiel gezeigt.  
  
 `"734" = "734"`  
  
 `' The result of the preceding comparison is True.`  
  
 Ist eine Zeichenfolge einer anderen vorangestellt, z. B. "aa" und "aaa", gilt die längere Zeichenfolge größer als die kürzere Zeichenfolge sein. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 `"aaa" > "aa"`  
  
 `' The result of the preceding comparison is True.`  
  
 Die Sortierreihenfolge basiert auf einen binären Vergleich oder ein Textvergleich entsprechend der Einstellung von `Option Compare`. Weitere Informationen finden Sie unter [Option Compare-Anweisung](../../../../visual-basic/language-reference/statements/option-compare-statement.md).  
  
## <a name="comparing-objects"></a>Vergleichen von Objekten  
 Visual Basic vergleicht zwei Objektverweisvariablen mit der [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) und [IsNot-Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md). Sie können entweder diese Operatoren verwenden, um festzustellen, ob die beiden Verweisvariablen auf die gleiche Objektinstanz verweisen. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#65](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_1.vb)]  
  
 Im vorherigen Beispiel `x Is y` ergibt `True`, da beide Variablen auf dieselbe Instanz verweisen. Vergleichen Sie dieses Ergebnis durch den folgenden Beispielcode.  
  
 [!code-vb[VbVbalrOperators#66](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_2.vb)]  
  
 Im vorherigen Beispiel `x Is y` ergibt `False`, da Sie zwar die Variablen auf Objekte vom gleichen Typ zu verweisen, jedoch auf unterschiedliche Instanzen dieses Typs verweisen.  
  
 Wenn Sie für zwei Objekte, die nicht auf dieselbe Instanz verweisen testen möchten die `IsNot` -Operators können Sie eine umständliche Grammatik einer Kombination von vermeiden `Not` und `Is`. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#67](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_3.vb)]  
  
 Im vorherigen Beispiel `If a IsNot b` entspricht `If Not a Is b`.  
  
### <a name="comparing-object-type"></a>Vergleichen des Objekttyps  
 Sie können testen, ob ein Objekt eines bestimmten Typs mit dem `TypeOf`... `Is` Ausdruck. Die Syntax lautet wie folgt:  
  
 `TypeOf <objectexpression> Is <typename>`  
  
 Wenn `typename` gibt einen Schnittstellentyp, und klicken Sie dann die `TypeOf`... `Is` Ausdruck gibt `True` , wenn das Objekt den Schnittstellentyp implementiert. Wenn `typename` ein Klassentyp ist, gibt der Ausdruck `True` Wenn das Objekt eine Instanz der angegebenen Klasse oder einer Klasse, die von der angegebenen Klasse abgeleitet ist. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#68](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_4.vb)]  
  
 Im vorherigen Beispiel der `TypeOf x Is Control` Ausdruck wird zu `True` da der Typ des `x` ist `Button`, geerbt von `Control`.  
  
 Weitere Informationen finden Sie unter [TypeOf-Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Wertvergleiche](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [Vergleichsoperatoren](../../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [Operatoren](../../../../visual-basic/language-reference/operators/index.md)  
 [Arithmetische Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [Verkettungsoperatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)  
 [Logische und bitweise Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
