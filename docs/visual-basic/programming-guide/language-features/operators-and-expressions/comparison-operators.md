---
title: "Comparison Operators in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "comparison operators, comparing strings"
  - "comparison operators, comparing objects"
  - "strings [Visual Basic], comparing"
  - "comparison operators"
  - "string comparison [Visual Basic], operators"
  - "objects [Visual Basic], comparing"
  - "numbers, comparing"
  - "Visual Basic code, operators"
  - "string comparison [Visual Basic]"
  - "numeric values, comparing"
  - "comparison operators, comparing numeric values"
  - "operators [Visual Basic], comparison"
ms.assetid: 0b570339-5407-474f-8421-e183a8b303ee
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Comparison Operators in Visual Basic
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Vergleichsoperatoren vergleichen zwei Ausdrücke und geben einen `Boolean`\-Wert zurück, der die Beziehung zwischen ihren Werten darstellt.  Es gibt Operatoren für das Vergleichen von numerischen Werten, Operatoren für Zeichenfolgen und Operatoren für Objekte.  Alle drei Typen werden an dieser Stelle erläutert.  
  
## Vergleichen von numerischen Werten  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] vergleicht numerische Werte mithilfe von sechs numerischen Vergleichsoperatoren.  Jeder Operator akzeptiert zwei Ausdrücke als Operanden, die numerische Werte ergeben.  In der folgenden Tabelle werden die Operatoren aufgelistet und für jeden Operator Beispiele dargestellt.  
  
|Operator|Getestete Bedingung|Beispiele|  
|--------------|-------------------------|---------------|  
|`=` \(Gleich\)|Ist der Wert des ersten Ausdrucks gleich dem Wert des zweiten Ausdrucks?|`23`   `=`   `33    ' False`<br /><br /> `23`   `=`   `23    ' True`<br /><br /> `23`   `=`   `12    ' False`|  
|`<>` \(Ungleich\)|Ist der Wert des ersten Ausdrucks ungleich dem Wert des zweiten Ausdrucks?|`23`   `<>`   `33    ' True`<br /><br /> `23`   `<>`   `23    ' False`<br /><br /> `23`   `<>`   `12    ' True`|  
|`<` \(Kleiner als\)|Ist der Wert des ersten Ausdrucks kleiner als der Wert des zweiten Ausdrucks?|`23`   `<`   `33    ' True`<br /><br /> `23`   `<`   `23    ' False`<br /><br /> `23`   `<`   `12    ' False`|  
|`>` \(Größer als\)|Ist der Wert des ersten Ausdrucks größer als der Wert des zweiten Ausdrucks?|`23`   `>`   `33    ' False`<br /><br /> `23`   `>`   `23    ' False`<br /><br /> `23`   `>`   `12    ' True`|  
|`<=` \(Kleiner oder gleich\)|Ist der Wert des ersten Ausdrucks kleiner oder gleich dem Wert des zweiten Ausdrucks?|`23`   `<=`   `33    ' True`<br /><br /> `23`   `<=`   `23    ' True`<br /><br /> `23`   `<=`   `12    ' False`|  
|`>=` \(Größer oder gleich\)|Ist der Wert des ersten Ausdrucks größer oder gleich dem Wert des zweiten Ausdrucks?|`23`   `>=`   `33    ' False`<br /><br /> `23`   `>=`   `23    ' True`<br /><br /> `23`   `>=`   `12    ' True`|  
  
## Vergleichen von Zeichenfolgen  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] vergleicht Zeichenfolgen mit dem [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md) sowie den numerischen Vergleichsoperatoren.  Mit dem Operator `Like` können Sie ein Muster angeben.  Die Zeichenfolge wird dann mit dem Muster verglichen, und bei Übereinstimmung ist das Ergebnis `True`.  Andernfalls ist das Ergebnis `False`.  Mit den numerischen Operatoren können Sie `String`\-Werte anhand ihrer Sortierreihenfolge vergleichen, wie im folgenden Beispiel veranschaulicht.  
  
 `"73" < "9"`  
  
 `' The result of the preceding comparison is True.`  
  
 Im vorherigen Beispiel ist das Ergebnis `True`, weil in der Sortierreihenfolge das erste Zeichen in der ersten Zeichenfolge vor dem ersten Zeichen in der zweiten Zeichenfolge steht.  Wenn die ersten Zeichen gleich wären, würde das nächste Zeichen in beiden Zeichenfolgen verglichen werden, usw.  Sie können die Gleichheit von Zeichenfolgen auch mit dem Gleichheitsoperator überprüfen, wie im folgenden Beispiel veranschaulicht.  
  
 `"734" = "734"`  
  
 `' The result of the preceding comparison is True.`  
  
 Wenn eine Zeichenfolge einer anderen vorangestellt ist, z. B. "aa" und "aaa", wird die längere Zeichenfolge als größerer Wert als die kürzere Zeichenfolge betrachtet.  Dies wird anhand des folgenden Beispiels veranschaulicht:  
  
 `"aaa" > "aa"`  
  
 `' The result of the preceding comparison is True.`  
  
 Die Sortierreihenfolge beruht entweder auf einem binären Vergleich oder einem Textvergleich. Dies hängt von der Einstellung von `Option Compare` ab.  Weitere Informationen finden Sie unter [Option Compare Statement](../../../../visual-basic/language-reference/statements/option-compare-statement.md).  
  
## Vergleichen von Objekten  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] vergleicht zwei Objektverweisvariablen mit dem [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) und dem [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md).  Sie können mit beiden Operatoren bestimmen, ob zwei Verweisvariablen auf die gleiche Objektinstanz verweisen.  Dies wird anhand des folgenden Beispiels veranschaulicht:  
  
 [!code-vb[VbVbalrOperators#65](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_1.vb)]  
  
 Im vorherigen Beispiel ergibt `x Is y` `True`, da beide Variablen auf dieselbe Instanz verweisen.  Vergleichen Sie dieses Ergebnis im Gegensatz dazu nun mit dem folgenden Beispiel.  
  
 [!code-vb[VbVbalrOperators#66](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_2.vb)]  
  
 Im vorherigen Beispiel ergibt `x Is y` `False`, da die Variablen zwar auf Objekte vom gleichen Typ, jedoch auf unterschiedliche Instanzen dieses Typs verweisen.  
  
 Wenn Sie sicherstellen möchten, dass zwei Objekte nicht auf dieselbe Instanz verweisen, können Sie mit dem Operator `IsNot` die umständliche Grammatik einer Kombination von `Not` und `Is` vermeiden.  Dies wird anhand des folgenden Beispiels veranschaulicht:  
  
 [!code-vb[VbVbalrOperators#67](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_3.vb)]  
  
 Im vorherigen Beispiel entsprechen sich `If a IsNot b` und `If Not a Is b`.  
  
### Vergleichen des Objekttyps  
 Mit dem `TypeOf`...`Is`\-Ausdruck können Sie überprüfen, ob ein Objekt von einem bestimmten Typ ist.  Die Syntax lautet wie folgt:  
  
 `TypeOf <objectexpression> Is <typename>`  
  
 Wenn `typename` einen Schnittstellentyp angibt, gibt der `TypeOf`...`Is`\-Ausdruck `True` zurück, sofern das Objekt den Schnittstellentyp implementiert.  Wenn es sich bei `typename` um einen Klassentyp handelt, gibt der Ausdruck `True` zurück, sofern das Objekt eine Instanz der angegebenen Klasse oder einer Klasse ist, die von der angegebenen Klasse abgeleitet wird.  Dies wird anhand des folgenden Beispiels veranschaulicht:  
  
 [!code-vb[VbVbalrOperators#68](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_4.vb)]  
  
 Im vorherigen Beispiel ergibt der `TypeOf x Is Control`\-Ausdruck `True`, weil `x` vom Typ `Button` ist, der von `Control` erbt.  
  
 Weitere Informationen finden Sie unter [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md).  
  
## Siehe auch  
 [Value Comparisons](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)   
 [Comparison Operators](../../../../visual-basic/language-reference/operators/comparison-operators.md)   
 [Operators](../../../../visual-basic/language-reference/operators/index.md)   
 [Arithmetic Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)   
 [Concatenation Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)   
 [Logical and Bitwise Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)