---
title: Arithmetische Operatoren in Visual Basic
ms.date: 07/20/2015
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
ms.openlocfilehash: 635c791f81107a1800e2ef381f6bea78cbc18e18
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58820775"
---
# <a name="arithmetic-operators-in-visual-basic"></a>Arithmetische Operatoren in Visual Basic
Arithmetische Operatoren werden viele der vertrauten arithmetischen Operationen ausführen, bei denen die Berechnung von numerischen Werten, die durch Literale, Variablen, andere Ausdrücke, Funktion und eigenschaftsaufrufen und Konstanten dargestellt verwendet. Sind Sie auch mit arithmetischen Operatoren klassifiziert Bitschiebeoperatoren, die auf der Ebene der einzelbits der Operanden werden und ihre Bitmuster nach links oder rechts.  
  
## <a name="arithmetic-operations"></a>Arithmetische Operationen  
 Sie können zwei Werte hinzufügen, in einem Ausdruck zusammen mit der [+ (Operator)](../../../../visual-basic/language-reference/operators/addition-operator.md), oder entfernen Sie eine von einem anderen mit der [--Operator (Visual Basic)](../../../../visual-basic/language-reference/operators/subtraction-operator.md), wie im folgende Beispiel wird veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#57)]  
  
 Negation verwendet ebenfalls die [-Operator (Visual Basic)](../../../../visual-basic/language-reference/operators/subtraction-operator.md), jedoch mit nur einem Operanden, wie im folgenden Beispiel veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#58)]  
  
 Multiplikation und Division verwenden die [* Operator](../../../../visual-basic/language-reference/operators/multiplication-operator.md) und [/-Operator (Visual Basic)](../../../../visual-basic/language-reference/operators/floating-point-division-operator.md)bzw., wie im folgende Beispiel wird veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#59](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#59)]  
  
 Potenzierung verwendet die [^-Operator](../../../../visual-basic/language-reference/operators/exponentiation-operator.md), wie das folgende Beispiel veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#60)]  
  
 Division ganzer Zahlen erfolgt mit der [\-Operator (Visual Basic)](../../../../visual-basic/language-reference/operators/integer-division-operator.md). Division ganzer Zahlen gibt den Quotienten, d. h. die ganze Zahl, die die Anzahl der Male darstellt. der Divisor geteilt werden kann der Dividend geteilt werden ohne Rest. Sowohl der Divisor als auch der Dividend muss Ganzzahltypen (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, und `ULong`) für diesen Operator. Alle anderen Typen müssen zuerst in einen ganzzahligen Typ konvertiert werden. Das folgende Beispiel zeigt die Division ganzer Zahlen.  
  
 [!code-vb[VbVbalrOperators#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#61)]  
  
 Arithmetischer Modulo erfolgt unter Verwendung der [Mod-Operator](../../../../visual-basic/language-reference/operators/mod-operator.md). Dieser Operator gibt den Rest nach der Division des Divisors in der Dividend geteilt eine ganzzahlige Anzahl von Malen zurück. Wenn sowohl der Divisor als auch der Dividend geteilt werden ganzzahlige Typen sind, ist der zurückgegebene Wert ganzzahligen. Wenn der Divisor und Dividend Gleitkomma-Datentypen handelt, ist der zurückgegebene Wert auch Gleitkommazahl. Das folgende Beispiel veranschaulicht dieses Verhalten.  
  
 [!code-vb[VbVbalrOperators#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#62)]  
  
 [!code-vb[VbVbalrOperators#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#63)]  
  
### <a name="attempted-division-by-zero"></a>Versuchte Division durch 0 (null)  
 Division durch 0 (null) verfügt über unterschiedliche Ergebnisse abhängig von den beteiligten Datentypen. Bei der ganzzahligen Division (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`), wird die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] löst eine <xref:System.DivideByZeroException> Ausnahme. Bei Divisionen der `Decimal` oder `Single` -Datentyp, der [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] löst auch eine <xref:System.DivideByZeroException> Ausnahme.  
  
 Bei Gleitkommadivisionen mit die `Double` -Datentyp, wird keine Ausnahme ausgelöst, und das Ergebnis ist der Klassenmember darstellt <xref:System.Double.NaN>, <xref:System.Double.PositiveInfinity>, oder <xref:System.Double.NegativeInfinity>, je nachdem, auf der Dividend geteilt. Die folgende Tabelle enthält die verschiedenen Ergebnisse beim Aufteilen einer `Double` Wert von 0 (null).  
  
|Dividend-Datentyp|Divisor-Datentyp|Wert der Dividend geteilt werden|Ergebnis|  
|---|---|---|---|  
|`Double`|`Double`|0|<xref:System.Double.NaN> (keine mathematisch definierte Zahl)|  
|`Double`|`Double`|> 0|<xref:System.Double.PositiveInfinity>|  
|`Double`|`Double`|\< 0|<xref:System.Double.NegativeInfinity>|  
  
 Wenn Sie Abfangen einer <xref:System.DivideByZeroException> Ausnahme können Sie ihre Member können Sie sie verarbeiten. Z. B. die <xref:System.Exception.Message%2A> Eigenschaft enthält den Meldungstext für die Ausnahme. Weitere Informationen finden Sie unter [Try...Catch...Finally-Anweisung](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## <a name="bit-shift-operations"></a>Bitverschiebung Vorgänge  
 Ein bitverschiebung Vorgang führt eine arithmetische Verschiebung in einem Bitmuster. Das Muster ist in der Operand auf der linken Seite enthalten, während der Operand auf der rechten Seite die Anzahl der Bitpositionen das Muster angibt. Schalten Sie das Muster, auf der rechten Seite mit den [>> Operator](../../../../visual-basic/language-reference/operators/right-shift-operator.md) oder auf der linken Seite mit den [<< Operator](../../../../visual-basic/language-reference/operators/left-shift-operator.md).  
  
 Der Datentyp des Operanden für das Muster muss `SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, oder `ULong`. Es muss der Datentyp des Operanden für die Verschiebung `Integer` oder muss erweitert werden, um `Integer`.  
  
 Arithmetische Verschiebungen sind nicht zirkuläre, was bedeutet die Bits verschoben aus einem Ende des Resultsets nicht am anderen Ende wieder eingeführt werden. Die Bitpositionen, die von einer Schicht werden wie folgt festgelegt:  
  
-   0 für die eine arithmetische Verschiebung nach links  
  
-   0 für die eine arithmetische rechtsverschiebung einer positiven Zahl  
  
-   0 für die eine arithmetische Verschiebung nach rechts ein Datentyp ohne Vorzeichen (`Byte`, `UShort`, `UInteger`, `ULong`)  
  
-   1 für die eine arithmetische rechtsverschiebung einer negativen Zahl (`SByte`, `Short`, `Integer`, oder `Long`)  
  
 Im folgende Beispiel wechselt ein `Integer` Wert nach rechts und Links.  
  
 [!code-vb[VbVbalrOperators#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#64)]  
  
 Arithmetische Schichten generieren keine Stapelüberlauf-Ausnahmen.  
  
## <a name="bitwise-operations"></a>Bitweise Operationen  
 Abgesehen davon, dass logische Operatoren, `Not`, `Or`, `And`, und `Xor` auch ausführen bitweiser Arithmetik, bei der Verwendung von numerischen Werten. Weitere Informationen finden Sie unter "Bitweise Vorgänge" in [logische und bitweise Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md).  
  
## <a name="type-safety"></a>Typsicherheit  
 Operanden sollten normalerweise vom gleichen Typ sein. Z. B., wenn Sie außerdem mit Durchführen einer `Integer` Variablen, addieren Sie sie in eine andere `Integer` Variable, und Sie weisen das Ergebnis einer Variablen vom Typ `Integer` ebenfalls.  
  
 Eine Möglichkeit, um sicherzustellen, dass typsichere gute Vorgehensweise bei der Codierung ist die Verwendung der [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md). Setzen Sie `Option Strict On`, Visual Basic automatisch führt *typsichere* Konvertierungen. Z. B., wenn Sie versuchen, Sie fügen ein `Integer` Variable eine `Double` Variable und weisen Sie den Wert ein `Double` Variablen, die Operation normal ausgeführt, weil ein `Integer` Wert konvertiert werden kann `Double` ohne Datenverlust. Typ-unsichere Konvertierungen, die auf der anderen Seite verursachen einen Compilerfehler mit `Option Strict On`. Z. B., wenn Sie versuchen, das Hinzufügen einer `Integer` Variable eine `Double` Variable und weisen Sie den Wert ein `Integer` Variable, ein Compilerfehler verursacht, weil eine `Double` Variable kann nicht Typ implizit konvertiert werden `Integer`.  
  
 Setzen Sie `Option Strict Off`, Visual Basic ermöglicht implizite einschränkende Konvertierungen erfolgen, jedoch auch unerwarteten Verlust von Daten oder Genauigkeit führen können. Aus diesem Grund empfehlen wir die Verwendung `Option Strict On` beim Schreiben von Produktionscode. Weitere Informationen finden Sie unter [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
## <a name="see-also"></a>Siehe auch

- [Arithmetische Operatoren](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Bitverschiebungsoperatoren](../../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [Vergleichsoperatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Verkettungsoperatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
- [Logische und bitweise Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [Effiziente Kombination von Operatoren](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
