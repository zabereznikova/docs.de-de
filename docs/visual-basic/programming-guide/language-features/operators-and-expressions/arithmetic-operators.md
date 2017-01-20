---
title: "Arithmetic Operators in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "type safety"
  - "operators [Visual Basic], bitwise"
  - "operators [Visual Basic], bit-shift"
  - "bitwise operators"
  - "bit-shift operators"
  - "zero, division by zero"
  - "operators [Visual Basic], arithmetic"
  - "division, by zero"
  - "Visual Basic code, operators"
  - "arithmetic operators, about arithmetic operators"
ms.assetid: 325dac7a-ea4f-41d5-8b48-f6e904211569
caps.latest.revision: 20
caps.handback.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Arithmetic Operators in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Arithmetische Operatoren werden für viele bekannte arithmetische Operationen verwendet, die numerische Werte berechnen, die durch Literale, Variablen, andere Ausdrücke, Funktions\- und Eigenschaftenaufrufe sowie Konstanten dargestellt werden.  Zu den arithmetischen Operatoren zählen auch die Bitschiebeoperatoren, die auf der Ebene der einzelnen Bits der Operanden ausgeführt werden und ihre Bitmuster nach links oder rechts verschieben.  
  
## Arithmetische Operationen  
 Sie können mit dem [\+ Operator](../../../../visual-basic/language-reference/operators/addition-operator.md) zwei Werte in einem Ausdruck addieren oder mit dem [\- Operator](../../../../visual-basic/language-reference/operators/subtraction-operator.md) einen Wert vom anderen subtrahieren, wie im folgenden Beispiel veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#57](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_1.vb)]  
  
 Der [\- Operator](../../../../visual-basic/language-reference/operators/subtraction-operator.md) wird auch für die Negation verwendet, jedoch mit nur einem Operanden, wie im folgenden Beispiel veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#58](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_2.vb)]  
  
 Für Multiplikation und Division wird der [\* Operator](../../../../visual-basic/language-reference/operators/multiplication-operator.md) bzw. der [\/ Operator](../../../../visual-basic/language-reference/operators/floating-point-division-operator.md) verwendet, wie im folgenden Beispiel veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#59](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_3.vb)]  
  
 Für die Potenzierung wird der [^ Operator](../../../../visual-basic/language-reference/operators/exponentiation-operator.md) verwendet, wie im folgenden Beispiel veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#60](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_4.vb)]  
  
 Die Division ganzer Zahlen erfolgt mit dem [\\ Operator](../../../../visual-basic/language-reference/operators/integer-division-operator.md).  Bei der Division ganzer Zahlen wird der Quotient zurückgegeben, also die ganze Zahl, die angibt, wie oft der Dividend durch den Divisor ohne Rest geteilt werden kann.  Für diesen Operator müssen Divisor und Dividend einen ganzzahligen Datentyp \(`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long` und `ULong`\) aufweisen.  Alle anderen Typen müssen zuerst in einen ganzzahligen Typ konvertiert werden.  Im folgenden Beispiel wird die Division ganzer Zahlen veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#61](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_5.vb)]  
  
 Modulo\-Arithmetik wird mit dem [Operator Mod](../../../../visual-basic/language-reference/operators/mod-operator.md) ausgeführt.  Dieser Operator gibt den Rest zurück, nachdem der Dividend mit einer durch eine ganze Zahl angegegebenen Häufigkeit durch den Divisor geteilt wurde.  Wenn es sich bei dem Divisor und dem Dividend um ganzzahlige Typen handelt, ist der zurückgegebene Wert eine ganze Zahl.  Wenn es sich bei dem Divisor und dem Dividend um einen Gleitkommatyp handelt, ist der zurückgegebene Wert ebenfalls ein Gleitkommatyp.  Im folgenden Beispiel wird dieses Verhalten veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#62](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_6.vb)]  
  
 [!code-vb[VbVbalrOperators#63](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_7.vb)]  
  
### Versuchte Division durch 0 \(null\)  
 Die Division durch 0 kann abhängig von den verwendeten Datentypen unterschiedliche Ergebnisse erzielen.  Bei der ganzzahligen Division \(`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`\), löst [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)] eine <xref:System.DivideByZeroException>\-Ausnahme aus.  Bei Divisionen mit dem `Decimal`\-Datentyp oder dem `Single`\-Datentyp löst [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)] ebenfalls eine <xref:System.DivideByZeroException>\-Ausnahme aus.  
  
 Bei Gleitkommadivisionen mit dem `Double`\-Datentyp wird keine Ausnahme ausgelöst, und das Ergebnis ist der Klassenmember, der je nach Dividend <xref:System.Double.NaN>, <xref:System.Double.PositiveInfinity> oder <xref:System.Double.NegativeInfinity> darstellt.  In der folgenden Tabelle sind die verschiedenen Ergebnisse beim Dividieren eines `Double`\-Werts durch 0 \(null\) zusammengefasst.  
  
|||||  
|-|-|-|-|  
|Dividenddatentyp|Divisordatentyp|Dividendwert|Ergebnis|  
|`Double`|`Double`|0|<xref:System.Double.NaN> \(keine mathematisch definierte Zahl\)|  
|`Double`|`Double`|\> 0|<xref:System.Double.PositiveInfinity>|  
|`Double`|`Double`|\< 0|<xref:System.Double.NegativeInfinity>|  
  
 Wenn Sie eine <xref:System.DivideByZeroException>\-Ausnahme abfangen, können Sie deren Member zum Beheben der Ausnahme verwenden.  Beispielsweise enthält die <xref:System.Exception.Message%2A>\-Eigenschaft den Meldungstext für die Ausnahme.  Weitere Informationen finden Sie unter [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## Bitschiebeoperationen  
 Eine Bitschiebeoperation führt eine arithmetische Verschiebung eines Bitmusters aus.  Der Operand auf der linken Seite enthält das Muster, während der Operand auf der rechten Seite die Anzahl der Positionen angibt, um die das Muster verschoben werden soll.  Das Muster kann mit dem [\>\> Operator](../../../../visual-basic/language-reference/operators/right-shift-operator.md) nach rechts und mit dem [\<\< Operator](../../../../visual-basic/language-reference/operators/left-shift-operator.md) nach links verschoben werden.  
  
 Der Datentyp des Operanden für das Muster muss `SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long` oder `ULong` sein.  Der Datentyp des Operanden für die Verschiebung muss `Integer` sein oder auf `Integer` erweitert werden.  
  
 Arithmetische Verschiebungen sind nicht zyklisch, d. h., die Bits, die an einem Ende des Ergebnisses durch die Verschiebung herausfallen, werden nicht am anderen Ende wieder eingefügt.  Die Bitpositionen, die durch eine Verschiebung freiwerden, werden wie folgt festgelegt:  
  
-   0 für eine arithmetische Verschiebung nach links  
  
-   0 für die arithmetische Verschiebung einer positiven Zahl nach rechts  
  
-   0 für die arithmetische Verschiebung nach rechts eines Datentyps ohne Vorzeichen \(`Byte`, `UShort`, `UInteger`, `ULong`\)  
  
-   1 für die arithmetische Verschiebung einer negativen Zahl \(`SByte`, `Short`, `Integer` oder `Long`\) nach rechts  
  
 Im folgenden Beispiel wird ein `Integer`\-Wert nach rechts und links verschoben  
  
 [!code-vb[VbVbalrOperators#64](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_8.vb)]  
  
 Arithmetische Verschiebungen generieren niemals Überlaufausnahmen.  
  
## Bitweise Operationen  
 Bei `Not`, `Or`, `And` und `Xor` handelt es sich nicht nur um logische Operatoren. Sie führen außerdem bitweise arithmetische Operationen aus, wenn sie mit numerischen Werten verwendet werden.  Weitere Informationen finden Sie in [Logical and Bitwise Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md) unter "Bitweise Operationen".  
  
## Typsicherheit  
 Operanden sollten normalerweise vom selben Typ sein.  Wenn Sie z. B. eine Addition mit einer `Integer`\-Variablen ausführen, addieren Sie sie zu einer anderen `Integer`\-Variablen und weisen das Ergebnis ebenfalls einer Variablen vom Typ `Integer` zu.  
  
 Eine Möglichkeit, eine gute, typsichere Codierung zu garantieren, ist die Verwendung der [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md).  Wenn Sie `Option Strict On` festlegen, führt [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] automatisch *typsichere* Konvertierungen aus.  Wenn Sie beispielsweise versuchen, eine `Integer`\-Variable zu einer `Double`\-Variablen zu addieren und den Wert einer `Double`\-Variablen zuzuweisen, wird der Vorgang normal ausgeführt, weil ein `Integer`\-Wert ohne Datenverlust in `Double` konvertiert werden kann.  Typunsichere Konvertierungen verursachen hingegen mit `Option Strict On` einen Compilerfehler.  Wenn Sie beispielsweise versuchen, eine `Integer`\-Variable zu einer `Double`\-Variablen zu addieren und den Wert einer `Integer`\-Variablen zuzuweisen, wird ein Compilerfehler verursacht, weil eine `Double`\-Variable nicht implizit in den Typ `Integer` konvertiert werden kann.  
  
 Wenn Sie `Option Strict Off` festlegen, lässt [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] jedoch implizite Einschränkungskonvertierungen zu, obwohl sie zu unerwartetem Daten\- oder Genauigkeitsverlust führen können.  Daher empfiehlt es sich, beim Schreiben von Produktionscode `Option Strict On` zu verwenden.  Weitere Informationen finden Sie unter [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
## Siehe auch  
 [Arithmetic Operators](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Bit Shift Operators](../../../../visual-basic/language-reference/operators/bit-shift-operators.md)   
 [Comparison Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)   
 [Concatenation Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)   
 [Logical and Bitwise Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)   
 [Efficient Combination of Operators](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)