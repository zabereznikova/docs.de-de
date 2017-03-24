---
title: Vergleichsoperatoren in Visual Basic | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- comparison operators, comparing strings
- comparison operators, comparing objects
- strings [Visual Basic], comparing
- comparison operators
- string comparison [Visual Basic], operators
- objects [Visual Basic], comparing
- numbers, comparing
- Visual Basic code, operators
- string comparison [Visual Basic]
- numeric values, comparing
- comparison operators, comparing numeric values
- operators [Visual Basic], comparison
ms.assetid: 0b570339-5407-474f-8421-e183a8b303ee
caps.latest.revision: 13
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6185d1676f2cd160c9c3e855cce4a6d2bbe2ffb4
ms.lasthandoff: 03/13/2017

---
# <a name="comparison-operators-in-visual-basic"></a>Comparison Operators in Visual Basic
Vergleichsoperatoren vergleichen zwei Ausdrücke und geben einen `Boolean` Wert, der die Beziehung zwischen ihren Werten darstellt. Es gibt Operatoren für das Vergleichen von numerischen Werten, Operatoren für Zeichenfolgen und Operatoren zum Vergleichen von Objekten. Alle drei Typen von Operatoren werden in diesem Dokument erläutert.  
  
## <a name="comparing-numeric-values"></a>Vergleichen von numerischen Werten  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Vergleicht numerische Werte mithilfe von sechs numerischen Vergleichsoperatoren. Jeder Operator akzeptiert zwei Ausdrücke, die numerische Werte ergeben, als Operanden. In der folgenden Tabelle werden die Operatoren aufgelistet und zeigt Beispiele für jeden.  
  
|Operator|Getestete Bedingung|Beispiele|  
|--------------|----------------------|--------------|  
|`=`(Gleichheit)|Ist der Wert des ersten Ausdrucks gleich dem Wert des zweiten?|`23`   `=`   `33    ' False`<br /><br /> `23`   `=`   `23    ' True`<br /><br /> `23`   `=`   `12    ' False`|  
|`<>`(Ungleichheit)|Ist der Wert des ersten Ausdrucks ungleich dem Wert des zweiten?|`23`   `<>`   `33    ' True`<br /><br /> `23`   `<>`   `23    ' False`<br /><br /> `23`   `<>`   `12    ' True`|  
|`<`(Kleiner als)|Ist der Wert des ersten Ausdrucks kleiner als der Wert des zweiten?|`23`   `<`   `33    ' True`<br /><br /> `23`   `<`   `23    ' False`<br /><br /> `23`   `<`   `12    ' False`|  
|`>`(Größer als)|Ist der Wert des ersten Ausdrucks größer als der Wert des zweiten?|`23`   `>`   `33    ' False`<br /><br /> `23`   `>`   `23    ' False`<br /><br /> `23`   `>`   `12    ' True`|  
|`<=`(Kleiner als oder gleich)|Ist der Wert des ersten Ausdrucks kleiner oder gleich dem Wert des zweiten?|`23`   `<=`   `33    ' True`<br /><br /> `23`   `<=`   `23    ' True`<br /><br /> `23`   `<=`   `12    ' False`|  
|`>=`(Größer als oder gleich)|Ist der Wert des ersten Ausdrucks, größer als oder gleich dem Wert des zweiten?|`23`   `>=`   `33    ' False`<br /><br /> `23`   `>=`   `23    ' True`<br /><br /> `23`   `>=`   `12    ' True`|  
  
## <a name="comparing-strings"></a>Vergleichen von Zeichenfolgen  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]vergleicht Zeichenfolgen anhand der [Like-Operator](../../../../visual-basic/language-reference/operators/like-operator.md) sowie den numerischen Vergleichsoperatoren. Die `Like` Operator können Sie ein Muster angeben. Die Zeichenfolge wird dann mit dem Muster verglichen, und bei Übereinstimmung ist das Ergebnis ist `True`. Andernfalls das Ergebnis ist `False`. Mit den numerischen Operatoren können Sie vergleichen `String` Werte basierend auf ihrer Sortierreihenfolge wie im folgenden Beispiel gezeigt.  
  
 `"73" < "9"`  
  
 `' The result of the preceding comparison is True.`  
  
 Das Ergebnis im vorherigen Beispiel ist `True` , da das erste Zeichen in der ersten Zeichenfolge vor dem ersten Zeichen in der zweiten Zeichenfolge sortiert. Wenn die ersten Zeichen gleich wären, würde der Vergleich weiterhin auf das nächste Zeichen in beiden Zeichenfolgen usw.. Sie können auch mit dem Gleichheitsoperator, wie im folgenden Beispiel gezeigt Zeichenfolgen auf Gleichheit testen.  
  
 `"734" = "734"`  
  
 `' The result of the preceding comparison is True.`  
  
 Wenn eine Zeichenfolge einer anderen vorangestellt, z. B. "aa" und "aaa", gilt die längere Zeichenfolge größer als die kürzere Zeichenfolge sein. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 `"aaa" > "aa"`  
  
 `' The result of the preceding comparison is True.`  
  
 Die Sortierreihenfolge basiert auf einem binären Vergleich oder einen Textvergleich abhängig von der Einstellung des `Option Compare`. Weitere Informationen finden Sie unter [Option Compare-Anweisung](../../../../visual-basic/language-reference/statements/option-compare-statement.md).  
  
## <a name="comparing-objects"></a>Vergleichen von Objekten  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Vergleicht zwei Objektverweisvariablen mit dem [Is-Operator](../../../../visual-basic/language-reference/operators/is-operator.md) und [IsNot-Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md). Sie können beiden Operatoren verwenden, um festzustellen, ob zwei Verweisvariablen auf die gleiche Objektinstanz verweisen. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 [!code-vb[VbVbalrOperators&#65;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_1.vb)]  
  
 Im vorangehenden Beispiel `x Is y` ergibt `True`, da beide Variablen auf dieselbe Instanz verweisen. Vergleichen Sie dieses Ergebnis mit dem folgenden Beispiel.  
  
 [!code-vb[VbVbalrOperators&#66;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_2.vb)]  
  
 Im vorangehenden Beispiel `x Is y` ergibt `False`, da die Variablen zwar auf Objekte vom gleichen Typ, jedoch auf unterschiedliche Instanzen dieses Typs verweisen.  
  
 Wenn Sie zwei Objekte nicht auf dieselbe Instanz verweisen möchten die `IsNot` Operator können Sie eine umständliche Grammatik einer Kombination von vermeiden `Not` und `Is`. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 [!code-vb[VbVbalrOperators&#67;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_3.vb)]  
  
 Im vorangehenden Beispiel `If a IsNot b` entspricht `If Not a Is b`.  
  
### <a name="comparing-object-type"></a>Vergleichen des Objekttyps  
 Sie können testen, ob ein Objekt eines bestimmten Typs mit der `TypeOf`... `Is` Ausdruck. Die Syntax lautet wie folgt:  
  
 `TypeOf <objectexpression> Is <typename>`  
  
 Wenn `typename` gibt einen Schnittstellentyp, der `TypeOf`... `Is` gibt `True` , wenn das Objekt den Schnittstellentyp implementiert. Wenn `typename` ein Klassentyp ist, gibt der Ausdruck `True` Wenn das Objekt eine Instanz der angegebenen Klasse oder eine Klasse, die von der angegebenen Klasse abgeleitet wird. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 [!code-vb[VbVbalrOperators&#68;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_4.vb)]  
  
 Im vorhergehenden Beispiel die `TypeOf x Is Control` Ausdruck ergibt `True` da der Typ des `x` ist `Button`, erbt von `Control`.  
  
 Weitere Informationen finden Sie unter [TypeOf-Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Wertvergleiche](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)   
 [Vergleichsoperatoren](../../../../visual-basic/language-reference/operators/comparison-operators.md)   
 [Operatoren](../../../../visual-basic/language-reference/operators/index.md)   
 [Arithmetische Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)   
 [Verkettungsoperatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)   
 [Logische und bitweise Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
