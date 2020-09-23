---
title: Arithmetische Operatoren
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
ms.openlocfilehash: 023e479736285aa2d04509e05f49fe930cb4721d
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91090078"
---
# <a name="arithmetic-operators-in-visual-basic"></a>Arithmetische Operatoren in Visual Basic

Arithmetische Operatoren werden verwendet, um viele der vertrauten arithmetischen Operationen auszuführen, die die Berechnung numerischer Werte beinhalten, die durch Literale, Variablen, andere Ausdrücke, Funktions-und Eigenschafts Aufrufe und Konstanten dargestellt werden. Auch mit arithmetischen Operatoren klassifiziert sind die BitShift-Operatoren, die auf der Ebene der einzelnen Bits der Operanden agieren und ihre Bitmuster nach links oder rechts verschieben.  
  
## <a name="arithmetic-operations"></a>Arithmetische Operationen  

 Sie können zwei Werte in einem Ausdruck mit dem +- [Operator](../../../language-reference/operators/addition-operator.md)hinzufügen oder von einem anderen mit dem [-Operator (Visual Basic)](../../../language-reference/operators/subtraction-operator.md)subtrahieren, wie im folgenden Beispiel veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#57)]  
  
 Negation verwendet auch den [-Operator (Visual Basic)](../../../language-reference/operators/subtraction-operator.md), jedoch mit nur einem Operanden, wie im folgenden Beispiel veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#58)]  
  
 Multiplikation und Division verwenden den [Operator *](../../../language-reference/operators/multiplication-operator.md) bzw. [/Operator (Visual Basic)](../../../language-reference/operators/floating-point-division-operator.md), wie im folgenden Beispiel veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#59](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#59)]  
  
 Die exponentiierung verwendet den [^-Operator](../../../language-reference/operators/exponentiation-operator.md), wie im folgenden Beispiel veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#60)]  
  
 Die ganzzahlige Division erfolgt mithilfe des [Operators \ (Visual Basic)](../../../language-reference/operators/integer-division-operator.md). Die ganzzahlige Division gibt den Quotienten zurück, d. h. die ganze Zahl, die angibt, wie oft der Divisor ohne Berücksichtigung eines Restwerts in die Dividende dividieren kann. Der Divisor und die Dividende müssen ganzzahlige Typen ( `SByte` , `Byte` , `Short` , `UShort` , `Integer` , `UInteger` , `Long` und `ULong` ) für diesen Operator sein. Alle anderen Typen müssen zuerst in einen ganzzahligen Typ konvertiert werden. Im folgenden Beispiel wird die ganzzahlige Division veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#61)]  
  
 Die arithmetische Modulus-Operation wird mithilfe des [Mod-Operators](../../../language-reference/operators/mod-operator.md)ausgeführt. Dieser Operator gibt den Rest zurück, nachdem er den Divisor in die Dividende als ganzzahlige Anzahl von Vorkommen aufgeteilt hat. Wenn Divisor und Dividende ganzzahlige Typen sind, ist der zurückgegebene Wert ganzzahlig. Wenn Divisor und Dividende Gleit Komma Typen sind, ist der zurückgegebene Wert auch ein Gleit Komma Wert. In folgendem Beispiel wird dieses Verhalten veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#62)]  
  
 [!code-vb[VbVbalrOperators#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#63)]  
  
### <a name="attempted-division-by-zero"></a>Versuchte Division durch Null  

 Die Division durch 0 (null) hat abhängig von den beteiligten Datentypen unterschiedliche Ergebnisse. In ganzzahligen Abteilungen ( `SByte` , `Byte` , `Short` , `UShort` , `Integer` , `UInteger` , `Long` , `ULong` ) löst die .NET Framework eine- <xref:System.DivideByZeroException> Ausnahme aus. Bei Divisions Vorgängen für den- `Decimal` Datentyp oder den- `Single` Datentyp löst die .NET Framework auch eine- <xref:System.DivideByZeroException> Ausnahme aus.  
  
 In Gleit Komma Teilungen, die den- `Double` Datentyp betreffen, wird keine Ausnahme ausgelöst, und das Ergebnis ist der Klassenmember, der <xref:System.Double.NaN> , <xref:System.Double.PositiveInfinity> oder darstellt <xref:System.Double.NegativeInfinity> , abhängig von der Dividende. In der folgenden Tabelle werden die verschiedenen Ergebnisse beim Versuch, einen Wert durch Null zu teilen, zusammengefasst `Double` .  
  
|Dividenden Datentyp|Divisor-Datentyp|Dividendenwert|Ergebnis|  
|---|---|---|---|  
|`Double`|`Double`|0|<xref:System.Double.NaN> (keine mathematisch definierte Zahl)|  
|`Double`|`Double`|> 0|<xref:System.Double.PositiveInfinity>|  
|`Double`|`Double`|\< 0|<xref:System.Double.NegativeInfinity>|  
  
 Wenn Sie eine- <xref:System.DivideByZeroException> Ausnahme abfangen, können Sie die zugehörigen Member verwenden, um Sie zu behandeln. Die- <xref:System.Exception.Message%2A> Eigenschaft enthält z. b. den Nachrichtentext für die Ausnahme. Weitere Informationen finden Sie unter [Try...Catch...Finally-Anweisung](../../../language-reference/statements/try-catch-finally-statement.md).  
  
## <a name="bit-shift-operations"></a>Bitverschiebungs Vorgänge  

 Ein Bitverschiebungs Vorgang führt eine arithmetische Verschiebung für ein Bitmuster aus. Das Muster ist im Operanden auf der linken Seite enthalten, während der Operand auf der rechten Seite die Anzahl der Positionen angibt, um das Muster zu verschieben. Sie können das Muster mit dem [>> -Operator](../../../language-reference/operators/right-shift-operator.md) oder Links mit dem [<< Operator](../../../language-reference/operators/left-shift-operator.md)nach rechts verschieben.  
  
 Der Datentyp des pattern-Operanden muss `SByte` , `Byte` , `Short` , `UShort` , `Integer` , `UInteger` , oder sein `Long` `ULong` . Der Datentyp des Shift Amount-Operanden muss sein `Integer` oder den Wert in erweitern `Integer` .  
  
 Arithmetische Verschiebungen sind nicht zirkulär, d. h., dass die Bits, die von einem Ende des Ergebnisses entfernt wurden, nicht erneut am anderen Ende eingefügt werden. Die durch eine Verschiebung frei gewordenen Bitpositionen werden wie folgt festgelegt:  
  
- 0 für eine arithmetische linke Verschiebung  
  
- 0 für eine arithmetische Rechtsverschiebung einer positiven Zahl  
  
- 0 für eine arithmetische Rechtsverschiebung eines Datentyps ohne Vorzeichen ( `Byte` , `UShort` , `UInteger` , `ULong` )  
  
- 1 für eine arithmetische Rechtsverschiebung einer negativen Zahl ( `SByte` , `Short` , `Integer` oder `Long` )  
  
 Im folgenden Beispiel wird ein `Integer` -Wert sowohl Links als auch rechts verschoben.  
  
 [!code-vb[VbVbalrOperators#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#64)]  
  
 Arithmetische Verschiebungen generieren niemals Überlauf Ausnahmen.  
  
## <a name="bitwise-operations"></a>Bitweise Vorgänge  

 Zusätzlich zu logischen Operatoren führen, `Not` , `Or` `And` und `Xor` auch bitweise Arithmetik aus, wenn Sie für numerische Werte verwendet werden. Weitere Informationen finden Sie unter "bitweise Vorgänge" in [logischen und bitweisen Operatoren in Visual Basic](logical-and-bitwise-operators.md).  
  
## <a name="type-safety"></a>Typsicherheit  

 Operanden sollten normalerweise denselben Typ aufweisen. Wenn Sie z. b. eine-Variable hinzu `Integer` fügen, sollten Sie Sie einer anderen Variablen hinzufügen `Integer` , und Sie sollten das Ergebnis auch einer Variablen des Typs zuweisen `Integer` .  
  
 Eine Möglichkeit, eine gute typsichere Codierungs Übung sicherzustellen, besteht darin, die [Option Strict-Anweisung](../../../language-reference/statements/option-strict-statement.md)zu verwenden. Wenn Sie festlegen `Option Strict On` , führt Visual Basic automatisch *typsichere* Konvertierungen aus. Wenn Sie z. b. versuchen, einer Variablen eine Variable hinzuzufügen `Integer` `Double` und den Wert einer `Double` Variablen zuzuweisen, wird der Vorgang normal fortgesetzt, da ein `Integer` Wert ohne Datenverlust in konvertiert werden kann `Double` . Typunsichere Konvertierungen hingegen verursachen einen Compilerfehler mit `Option Strict On` . Wenn Sie z. b. versuchen, einer Variablen eine Variable hinzuzufügen `Integer` `Double` und den Wert einer `Integer` Variablen zuzuweisen, führt dies zu einem Compilerfehler, da eine `Double` Variable nicht implizit in den Typ konvertiert werden kann `Integer` .  
  
 Wenn Sie jedoch festlegen, werden `Option Strict Off` Visual Basic implizite einschränkende Konvertierungen durchführen, obwohl Sie zu unerwartetem Datenverlust oder Genauigkeits Verlust führen können. Aus diesem Grund wird empfohlen, `Option Strict On` beim Schreiben von Produktionscode zu verwenden. Weitere Informationen finden Sie unter [Widening and Narrowing Conversions](../data-types/widening-and-narrowing-conversions.md).  
  
## <a name="see-also"></a>Siehe auch

- [Arithmetic Operators (Arithmetische Operatoren)](../../../language-reference/operators/arithmetic-operators.md)
- [Bitschiebeoperatoren](../../../language-reference/operators/bit-shift-operators.md)
- [Comparison Operators in Visual Basic](comparison-operators.md)
- [Verkettungsoperatoren in Visual Basic](concatenation-operators.md)
- [Logische und bitweise Operatoren in Visual Basic](logical-and-bitwise-operators.md)
- [Effiziente Kombination von Operatoren](efficient-combination-of-operators.md)
