---
title: Arithmetische Operatoren in Visual Basic | Microsoft-Dokumentation
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
- type safety
- operators [Visual Basic], bitwise
- operators [Visual Basic], bit-shift
- bitwise operators
- bit-shift operators
- zero, division by zero
- operators [Visual Basic], arithmetic
- division, by zero
- Visual Basic code, operators
- arithmetic operators, about arithmetic operators
ms.assetid: 325dac7a-ea4f-41d5-8b48-f6e904211569
caps.latest.revision: 20
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
ms.openlocfilehash: c724bf8b6794e71d49b32c7d3ce9e010f541f68f
ms.lasthandoff: 03/13/2017

---
# <a name="arithmetic-operators-in-visual-basic"></a>Arithmetische Operatoren in Visual Basic
Arithmetische Operatoren werden viele bekannte arithmetischen Operationen ausführen, die die Berechnung von numerischen Werten, die durch Literale, Variablen, andere Ausdrücke, Funktion und Eigenschaftenaufrufe und Konstanten dargestellt beinhalten verwendet. Auch mit arithmetischen Operatoren klassifiziert sind die Bitschiebeoperatoren, die auf der Ebene der einzelnen Bits der Operanden und ihre Bitmuster nach links oder rechts.  
  
## <a name="arithmetic-operations"></a>Arithmetische Operationen  
 Sie können zwei Werte hinzufügen, in einem Ausdruck zusammen mit der [+-Operator](../../../../visual-basic/language-reference/operators/addition-operator.md), oder einen von einem anderen durch Subtrahieren der [-Operator (Visual Basic)](../../../../visual-basic/language-reference/operators/subtraction-operator.md), wie im folgende Beispiel veranschaulicht.  
  
 [!code-vb[VbVbalrOperators&#57;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_1.vb)]  
  
 Negation verwendet ebenfalls die [-Operator (Visual Basic)](../../../../visual-basic/language-reference/operators/subtraction-operator.md), jedoch mit nur einem Operanden, wie im folgenden Beispiel veranschaulicht.  
  
 [!code-vb[VbVbalrOperators&#58;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_2.vb)]  
  
 Multiplikation und Division der [* Operator](../../../../visual-basic/language-reference/operators/multiplication-operator.md) und [/ Operator (Visual Basic)](../../../../visual-basic/language-reference/operators/floating-point-division-operator.md)zugeordnet, wie im folgende Beispiel veranschaulicht.  
  
 [!code-vb[VbVbalrOperators&#59;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_3.vb)]  
  
 Potenzierung verwendet die [^ Operator](../../../../visual-basic/language-reference/operators/exponentiation-operator.md), wie im folgende Beispiel veranschaulicht.  
  
 [!code-vb[VbVbalrOperators&60;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_4.vb)]  
  
 Division ganzer Zahlen erfolgt mit der [\ Operator (Visual Basic)](../../../../visual-basic/language-reference/operators/integer-division-operator.md). Ganzzahldivision gibt den Quotienten, d. h. die ganze Zahl, die die Anzahl der Male darstellt der Divisor geteilt werden kann der Dividend ohne Rest. Der Divisor und Dividend muss Ganzzahltypen (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, und `ULong`) für diesen Operator. Alle anderen Typen müssen zuerst in einen ganzzahligen Typ konvertiert werden. Das folgende Beispiel zeigt die Ganzzahldivision.  
  
 [!code-vb[VbVbalrOperators&#61;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_5.vb)]  
  
 Modulo-Arithmetik erfolgt unter Verwendung der [Mod-Operator](../../../../visual-basic/language-reference/operators/mod-operator.md). Dieser Operator gibt den Rest nach der Division des Divisors in der Dividend an, wie oft eine ganze Zahl zurück. Wenn Divisor und Dividend ganzzahlige Typen sind, ist der zurückgegebene Wert ganzzahligen. Wenn der Divisor und Dividend Gleitkomma-Datentypen handelt, ist der zurückgegebene Wert auch Gleitkommazahlen. Das folgende Beispiel veranschaulicht dieses Verhalten.  
  
 [!code-vb[VbVbalrOperators&#62;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_6.vb)]  
  
 [!code-vb[VbVbalrOperators&#63;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_7.vb)]  
  
### <a name="attempted-division-by-zero"></a>Versuchte Division durch&0; (null)  
 Division durch&0; kann abhängig von den beteiligten Datentypen unterschiedliche Ergebnisse. In integral divisions (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`), the [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] throws a <xref:System.DivideByZeroException> exception.</xref:System.DivideByZeroException> Bei Divisionen der `Decimal` oder `Single` -Datentyp, der [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] löst auch eine <xref:System.DivideByZeroException>Ausnahme.</xref:System.DivideByZeroException>  
  
 Bei Gleitkommadivisionen mit dem `Double` Datentyp aufweisen, wird keine Ausnahme ausgelöst, und das Ergebnis ist der Klassenmember darstellt <xref:System.Double.NaN>, <xref:System.Double.PositiveInfinity>, oder <xref:System.Double.NegativeInfinity>, abhängig von der Dividend.</xref:System.Double.NegativeInfinity> </xref:System.Double.PositiveInfinity> </xref:System.Double.NaN> In der folgenden Tabelle sind die verschiedenen Ergebnisse beim Dividieren ein `Double` Wert von&0; (null).  
  
|Dividend-Datentyp|Divisor-Datentyp|Dividend Wert|Ergebnis|  
|---|---|---|---|  
|`Double`|`Double`|0|<xref:System.Double.NaN>(keine mathematisch definierte Zahl)</xref:System.Double.NaN>|  
|`Double`|`Double`|> 0|<xref:System.Double.PositiveInfinity></xref:System.Double.PositiveInfinity>|  
|`Double`|`Double`|\< 0|<xref:System.Double.NegativeInfinity></xref:System.Double.NegativeInfinity>|  
  
 Wenn Sie Abfangen einer <xref:System.DivideByZeroException>Ausnahme Membern Hilfestellungen für it. behandeln verwenden können</xref:System.DivideByZeroException> Zum Beispiel die <xref:System.Exception.Message%2A>-Eigenschaft enthält den Meldungstext für die Ausnahme.</xref:System.Exception.Message%2A> Weitere Informationen finden Sie unter [versuchen... Catch... Finally-Anweisung](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## <a name="bit-shift-operations"></a>Bit Verschiebevorgänge  
 Ein Bit Shift-Vorgang führt eine arithmetische Verschiebung für ein Bitmuster. Das Muster ist Bestandteil der Operand auf der linken Seite, während der Operand auf der rechten Seite die Anzahl der Bitpositionen das Muster angibt. Schalten Sie das Muster, um die rechte Seite mit den [>> Operator](../../../../visual-basic/language-reference/operators/right-shift-operator.md) oder auf der linken Seite mit den [ <> </> ](../../../../visual-basic/language-reference/operators/left-shift-operator.md).  
  
 Der Datentyp des Operanden für das Muster muss `SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, oder `ULong`. Der Datentyp des Operanden für die Verschiebung muss `Integer` oder muss erweitert werden, um `Integer`.  
  
 Arithmetische Schichten sind nicht zirkulär, d. h. ein Ende des Resultsets verschobene Bits nicht am anderen Ende wieder hinzugefügt werden. Die Bitpositionen, die durch eine Verschiebung werden wie folgt festgelegt:  
  
-   0 für eine arithmetische Verschiebung nach links  
  
-   0 für eine arithmetische Verschiebung einer positiven Zahl nach rechts  
  
-   0 für eine arithmetische Verschiebung nach rechts ein Datentyp ohne Vorzeichen (`Byte`, `UShort`, `UInteger`, `ULong`)  
  
-   1 für eine arithmetische Verschiebung einer negativen Zahl nach rechts (`SByte`, `Short`, `Integer`, oder `Long`)  
  
 Im folgende Beispiel wird ein `Integer` Wert links und rechts.  
  
 [!code-vb[VbVbalrOperators&#64;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_8.vb)]  
  
 Arithmetische Schichten generieren nie Ausnahmen für Stapelüberläufe.  
  
## <a name="bitwise-operations"></a>Bitweise Operationen  
 Abgesehen davon, dass logische Operatoren `Not`, `Or`, `And`, und `Xor` führen auch bei numerischen Werten verwendet. Weitere Informationen finden Sie unter "Bitweise Operationen" in [logische und bitweise Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md).  
  
## <a name="type-safety"></a>Typsicherheit  
 Operanden sollten normalerweise vom selben Typ sein. Z. B. bei sachgemäß mit einer `Integer` Variable, addieren Sie sie zu einem anderen `Integer` -Variablen und weisen das Ergebnis einer Variablen vom Typ `Integer` sowie.  
  
 Eine Möglichkeit, typsichere gute Programmierpraxis ist die Verwendung der [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md). Wenn Sie festlegen, `Option Strict On`, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] führt automatisch *typsichere* Konvertierungen. Beispielsweise, wenn Sie versuchen, hinzuzufügen ein `Integer` Variable auf ein `Double` Variable und weisen Sie den Wert einer `Double` Variable, der Vorgang normal ausgeführt, weil ein `Integer` Wert konvertiert werden kann, um `Double` ohne Datenverlust. Typ-unsichere Konvertierungen andererseits, verursachen einen Compilerfehler mit `Option Strict On`. Beispielsweise, wenn Sie versuchen, hinzuzufügen ein `Integer` -Variable auf ein `Double` Variable und weisen Sie den Wert einer `Integer` Variable ein Compilerfehler verursacht, weil eine `Double` Variablen kann nicht implizit konvertiert werden, um den Typ `Integer`.  
  
 Wenn Sie festlegen, `Option Strict Off`jedoch [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] ermöglicht die implizite einschränkende Konvertierungen stattfinden, jedoch zu unerwarteten Datenverlust oder Genauigkeitsverlust führen können. Aus diesem Grund empfehlen wir die Verwendung `Option Strict On` beim Schreiben von Produktionscode. Weitere Informationen finden Sie unter [Widening und einschränkende Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Arithmetische Operatoren](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Bitschiebeoperatoren](../../../../visual-basic/language-reference/operators/bit-shift-operators.md)   
 [Vergleichsoperatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)   
 [Verkettungsoperatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)   
 [Logische und bitweise Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)   
 [Effiziente Kombination von Operatoren](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
