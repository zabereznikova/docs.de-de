---
title: Arithmetische Operatoren in Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- type safety
- operators [Visual Basic], bitwise
- operators [Visual Basic], bit-shift
- bitwise operators [Visual Basic]
- bit-shift operators [Visual Basic]
- zero, division by zero
- operators [Visual Basic], arithmetic
- division [Visual Basic], by zero
- Visual Basic code, operators
- arithmetic operators [Visual Basic], about arithmetic operators
ms.assetid: 325dac7a-ea4f-41d5-8b48-f6e904211569
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7fec98c38eebc34a0f84e051dc7c0914f537418f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="arithmetic-operators-in-visual-basic"></a>Arithmetische Operatoren in Visual Basic
Arithmetische Operatoren werden verwendet, um viele bekannte arithmetischen Operationen ausführen, die die Berechnung von numerischen Werten, die durch die Literale, Variablen, andere Ausdrücke, Funktion und Eigenschaftenaufrufe und Konstanten dargestellt einschließen. Auch mit arithmetischen Operatoren klassifiziert sind Bitschiebeoperatoren, die auf der Ebene der einzelnen Bits der Operanden fungieren und ihre Bitmuster nach links oder rechts.  
  
## <a name="arithmetic-operations"></a>Arithmetische Operationen  
 Können Sie zwei Werte hinzufügen, in einem Ausdruck zusammen mit den [+-Operator](../../../../visual-basic/language-reference/operators/addition-operator.md), oder Subtrahieren von einem anderen mit der [-Operator (Visual Basic)](../../../../visual-basic/language-reference/operators/subtraction-operator.md), wie im folgenden Beispiel wird veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#57](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_1.vb)]  
  
 Negation verwendet ebenfalls die [-Operator (Visual Basic)](../../../../visual-basic/language-reference/operators/subtraction-operator.md), jedoch mit nur einem Operanden, wie im folgenden Beispiel veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#58](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_2.vb)]  
  
 Multiplikation und Division der [* Operator](../../../../visual-basic/language-reference/operators/multiplication-operator.md) und [/-Operator (Visual Basic)](../../../../visual-basic/language-reference/operators/floating-point-division-operator.md)zugeordnet, wie im folgende Beispiel veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#59](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_3.vb)]  
  
 Potenzierung verwendet die [^ Operator](../../../../visual-basic/language-reference/operators/exponentiation-operator.md), wie das folgende Beispiel veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#60](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_4.vb)]  
  
 Ganzzahldivision erfolgt mit der [\-Operator (Visual Basic)](../../../../visual-basic/language-reference/operators/integer-division-operator.md). Ganzzahldivision gibt den Quotienten zurück, d. h. die ganze Zahl, die die Anzahl der Male darstellt der Divisor kann in unterteilt der Dividend ohne Berücksichtigung der Rest. Sowohl der Divisor als auch der Dividend muss Ganzzahltypen (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, und `ULong`) für diesen Operator. Alle anderen Typen müssen zuerst in einen ganzzahligen Typ konvertiert werden. Das folgende Beispiel zeigt eine Ganzzahldivision.  
  
 [!code-vb[VbVbalrOperators#61](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_5.vb)]  
  
 Modulo erfolgt mithilfe der [Mod Operator](../../../../visual-basic/language-reference/operators/mod-operator.md). Dieser Operator gibt den Rest nach der Division des Divisors in der Dividend geteilt wie oft eine ganze Zahl zurück. Wenn sowohl der Divisor als auch der Dividend geteilt werden ganzzahlige Typen sind, ist der zurückgegebene Wert ganzzahligen. Wenn der Divisor und Dividend Gleitkommatypen sind, ist der zurückgegebene Wert auch Gleitkommawert. Das folgende Beispiel veranschaulicht dieses Verhalten.  
  
 [!code-vb[VbVbalrOperators#62](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_6.vb)]  
  
 [!code-vb[VbVbalrOperators#63](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_7.vb)]  
  
### <a name="attempted-division-by-zero"></a>Versuchte Division durch 0 (null)  
 Division durch 0 (null) hat unterschiedliche Ergebnisse abhängig von den beteiligten Datentypen. Bei der ganzzahligen Division (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`), wird die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] löst eine <xref:System.DivideByZeroException> Ausnahme. Bei Divisionen der `Decimal` oder `Single` -Datentyp, der [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] löst außerdem eine <xref:System.DivideByZeroException> Ausnahme.  
  
 In Gleitkommazahlen Abteilungen, die im Zusammenhang mit der `Double` Datentyp, wird keine Ausnahme ausgelöst, und das Ergebnis ist die Klassenmember darstellt <xref:System.Double.NaN>, <xref:System.Double.PositiveInfinity>, oder <xref:System.Double.NegativeInfinity>, je nachdem, auf der Dividend geteilt. Die folgende Tabelle enthält die verschiedenen Ergebnisse beim Aufteilen einer `Double` Wert von 0 (null).  
  
|Dividend-Datentyp|Divisor-Datentyp|Wert der Dividend geteilt werden|Ergebnis|  
|---|---|---|---|  
|`Double`|`Double`|0|<xref:System.Double.NaN>(keine mathematisch definierte Zahl)|  
|`Double`|`Double`|> 0|<xref:System.Double.PositiveInfinity>|  
|`Double`|`Double`|\< 0|<xref:System.Double.NegativeInfinity>|  
  
 Wenn Sie Abfangen einer <xref:System.DivideByZeroException> Ausnahme können Sie ihre Member können Sie die er behandeln. Z. B. die <xref:System.Exception.Message%2A> Eigenschaft enthält den Meldungstext für die Ausnahme. Weitere Informationen finden Sie unter [Try...Catch...Finally-Anweisung](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## <a name="bit-shift-operations"></a>Bitverschiebung Vorgänge  
 Ein bitverschiebung Vorgang führt eine arithmetische Verschiebung in einem Bitmuster. Das Muster ist in der Operand auf der linken Seite enthalten, während der Operand auf der rechten Seite die Anzahl von Bitpositionen das Muster angibt. Schalten Sie das Muster, um die rechte Seite mit den [>> Operator](../../../../visual-basic/language-reference/operators/right-shift-operator.md) oder auf der linken Seite mit den [<< Operator](../../../../visual-basic/language-reference/operators/left-shift-operator.md).  
  
 Der Datentyp des Operanden für das Muster muss `SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, oder `ULong`. Der Datentyp des Operanden für die Verschiebung muss `Integer` oder Indikatorvariablen `Integer`.  
  
 Arithmetische Schichten sind nicht zirkulär, d. h. die Bits verschobene ein Ende des Resultsets nicht am anderen Ende wieder hinzugefügt werden. Die Bitpositionen durch eine Verschiebung werden wie folgt festgelegt:  
  
-   0 für eine arithmetische Verschiebung nach links  
  
-   0 für eine arithmetische rechtsverschiebung einer positiven Zahl  
  
-   0 für eine arithmetische Verschiebung nach rechts ein Datentyp ohne Vorzeichen (`Byte`, `UShort`, `UInteger`, `ULong`)  
  
-   1 für eine arithmetische Verschiebung nach rechts eine negative Zahl (`SByte`, `Short`, `Integer`, oder `Long`)  
  
 Im folgenden Beispiel wird der nächste Schritt ein `Integer` Wert links und rechts.  
  
 [!code-vb[VbVbalrOperators#64](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_8.vb)]  
  
 Arithmetische Schichten generieren nie Stapelüberlauf-Ausnahmen.  
  
## <a name="bitwise-operations"></a>Bitweise Operationen  
 Abgesehen davon, dass logische Operatoren `Not`, `Or`, `And`, und `Xor` auch ausführen bitweiser Arithmetik auf numerische Werte. Weitere Informationen finden Sie unter "Bitweise Operationen" in [logische und bitweise Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md).  
  
## <a name="type-safety"></a>Typsicherheit  
 Operanden sollten normalerweise vom selben Typ sein. Angenommen, Sie außerdem mit auf diese Weise werden ein `Integer` Variablen, Sie sollten ihn hinzufügen zu einem anderen `Integer` Variable und Sie weisen das Ergebnis einer Variablen vom Typ `Integer` ebenfalls.  
  
 Eine Möglichkeit, typsichere gute Programmierpraxis ist die Verwendung der [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md). Wenn Sie festlegen, `Option Strict On`, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] führt automatisch eine *als typsicherer* Konvertierungen. Z. B., wenn Sie versuchen, hinzuzufügen ein `Integer` Variable auf ein `Double` Variable und weisen Sie den Wert einer `Double` Variablen, der Vorgang normal ausgeführt, weil ein `Integer` Wert konvertiert werden kann, um `Double` ohne Verlust von Daten. Typ-unsichere Konvertierungen andererseits, verursachen einen Compilerfehler mit `Option Strict On`. Z. B., wenn Sie versuchen, Sie fügen ein `Integer` Variable auf eine `Double` Variable und weisen Sie den Wert ein `Integer` Variable, ein Compilerfehler verursacht, weil eine `Double` Variable kann nicht Typ implizit konvertiert werden `Integer`.  
  
 Wenn Sie festlegen, `Option Strict Off`, allerdings [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] ermöglicht implizite einschränkende Konvertierungen erfolgen, obwohl sie zu unerwarteten Datenverlust oder Genauigkeitsverlust führen können. Aus diesem Grund empfehlen wir die Verwendung `Option Strict On` beim Produktionscode zu schreiben. Weitere Informationen finden Sie unter [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Arithmetische Operatoren](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Bitverschiebungsoperatoren](../../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [Vergleichsoperatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [Verkettungsoperatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)  
 [Logische und bitweise Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)  
 [Effiziente Kombination von Operatoren](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
