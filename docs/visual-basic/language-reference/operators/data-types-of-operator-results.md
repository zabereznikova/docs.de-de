---
title: Datentypen von Operatorergebnissen
ms.date: 07/20/2015
helpviewer_keywords:
- data types [Visual Basic], operator result data types
- result data types [Visual Basic]
- operator result data types [Visual Basic]
- operators [Visual Basic], data types
- data types [Visual Basic], ranges
- operators [Visual Basic], result data types
ms.assetid: 9d524533-e1a1-4aa8-b1b8-622068173d06
ms.openlocfilehash: 3867d433ea5f9a6effe70db0ff4162390fb50b5c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331471"
---
# <a name="data-types-of-operator-results-visual-basic"></a>Datentypen von Operatorergebnissen (Visual Basic)
Visual Basic bestimmt den Ergebnis Datentyp eines Vorgangs auf der Grundlage der Datentypen der Operanden. In einigen Fällen kann dies ein Datentyp mit einem größeren Bereich sein als der eines der beiden Operanden.  
  
## <a name="data-type-ranges"></a>Datentypbereiche  
 Die Bereiche der relevanten Datentypen, von der niedrigsten zum größten, sind wie folgt:  
  
- [Boolescher](../../../visual-basic/language-reference/data-types/boolean-data-type.md) Wert – zwei mögliche Werte  
  
- [SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md) – 256 mögliche ganzzahlige Werte  
  
- [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md) – 65.536 (6.5... E + 4) mögliche ganzzahlige Werte  
  
- [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md) – 4.294.967.296 (4.2... E + 9) mögliche ganzzahlige Werte  
  
- [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ulong](../../../visual-basic/language-reference/data-types/ulong-data-type.md) – 18446744073709551615 (1.8... E + 19) mögliche ganzzahlige Werte  
  
- [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) – 1.5... e + 29 mögliche ganzzahlige Werte, maximaler Bereich 7,9... e + 28 (absoluter Wert)  
  
- [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) – maximaler Bereich von 3.4... E + 38 (absoluter Wert)  
  
- [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) – maximaler Bereich 1.7... E + 308 (absoluter Wert)  
  
 Weitere Informationen zu Visual Basic-Datentypen finden Sie unter [Datentypen](../../../visual-basic/language-reference/data-types/index.md).  
  
 Wenn ein Operand als " [Nothing](../../../visual-basic/language-reference/nothing.md)" ausgewertet wird, wird er von den Visual Basic arithmetischen Operatoren als NULL behandelt.  
  
## <a name="decimal-arithmetic"></a>Dezimal Arithmetik  
 Beachten Sie, dass der [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) -Datentyp weder Gleit Komma noch Integer ist.  
  
 Wenn einer der Operanden eines `+`-, `–`-, `*`-, `/`-oder `Mod` Vorgangs `Decimal` und der andere nicht `Single` oder `Double`ist, wird der andere Operand in Visual Basic erweitert.`Decimal` Der Vorgang wird in `Decimal`durchführt, und der Ergebnis Datentyp ist `Decimal`.  
  
## <a name="floating-point-arithmetic"></a>Gleit Komma Arithmetik  
 Visual Basic führt die meisten Gleit Komma Arithmetik in [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)aus. Dies ist der effizienteste Datentyp für solche Vorgänge. Wenn ein Operand jedoch [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) und der andere nicht `Double`ist, führt Visual Basic den Vorgang in `Single`aus. Er erweitert jeden Operanden nach Bedarf auf den entsprechenden Datentyp vor dem Vorgang, und das Ergebnis hat diesen Datentyp.  
  
### <a name="-and--operators"></a>/und ^-Operatoren  
 Der `/`-Operator ist nur für die Datentypen [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md), [Single](../../../visual-basic/language-reference/data-types/single-data-type.md)und [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) definiert. Visual Basic jeden Operanden nach Bedarf auf den entsprechenden Datentyp vor dem Vorgang erweitert, und das Ergebnis hat diesen Datentyp.  
  
 In der folgenden Tabelle werden die Ergebnis Datentypen für den `/`-Operator angezeigt. Beachten Sie, dass diese Tabelle symmetrisch ist. für eine bestimmte Kombination von operanddatentypen ist der Ergebnis Datentyp unabhängig von der Reihenfolge der Operanden identisch.  
  
||||||  
|---|---|---|---|---|  
||`Decimal`|`Single`|`Double`|Beliebige ganzzahlige Typen|  
|`Decimal`|Decimal|Single|Double|Decimal|  
|`Single`|Single|Single|Double|Single|  
|`Double`|Double|Double|Double|Double|  
|Beliebige ganzzahlige Typen|Decimal|Single|Double|Double|  
  
 Der `^`-Operator ist nur für den `Double` Datentyp definiert. Visual Basic alle Operanden nach Bedarf erweitert, um vor dem Vorgang zu `Double`, und der Ergebnis Datentyp ist immer `Double`.  
  
## <a name="integer-arithmetic"></a>Arithmetische Ganzzahl  
 Der Ergebnis Datentyp einer ganzzahligen Operation hängt von den Datentypen der Operanden ab. Im Allgemeinen verwendet Visual Basic die folgenden Richtlinien zur Bestimmung des Ergebnis Datentyps:  
  
- Wenn beide Operanden eines binären Operators denselben Datentyp aufweisen, hat das Ergebnis diesen Datentyp. Eine Ausnahme ist `Boolean`, die erzwungen wird, um zu `Short`.  
  
- Wenn ein nicht signierter Operand an einem signierten Operanden teilnimmt, verfügt das Ergebnis über einen signierten Typ, der mindestens so groß ist wie der Operand.  
  
- Andernfalls verfügt das Ergebnis in der Regel über den größeren der beiden Operanden Datentypen.  
  
 Beachten Sie, dass der Ergebnis Datentyp möglicherweise nicht mit dem Datentyp "Operand" identisch ist.  
  
> [!NOTE]
> Der Ergebnis Datentyp ist nicht immer groß genug, um alle möglichen Werte zu speichern, die sich aus dem Vorgang ergeben. Eine <xref:System.OverflowException> Ausnahme kann auftreten, wenn der Wert für den Ergebnis Datentyp zu groß ist.  
  
### <a name="unary--and--operators"></a>Unäre +-und –-Operatoren  
 In der folgenden Tabelle werden die Ergebnis Datentypen für die beiden unären Operatoren, `+` und `–`, angezeigt.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|Unärer `+`|Short|SByte|Byte|Short|UShort|Ganze Zahl|UInteger|Long|ULong|  
|Unärer `–`|Short|SByte|Short|Short|Ganze Zahl|Ganze Zahl|Long|Long|Decimal|  
  
### <a name="-and--operators"></a><\< und > > Operatoren  
 In der folgenden Tabelle werden die Ergebnis Datentypen für die beiden BitShift-Operatoren, `<<` und `>>`, angezeigt. Visual Basic behandelt jeden Bitverschiebungs Operator als unären Operator für den linken Operanden (das Bitmuster, das verschoben werden soll).  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`<<`, `>>`|Short|SByte|Byte|Short|UShort|Ganze Zahl|UInteger|Long|ULong|  
  
 Wenn der linke Operand `Decimal`, `Single`, `Double`oder `String`ist, versucht Visual Basic, ihn vor dem Vorgang in `Long` zu konvertieren, und der Ergebnis Datentyp ist `Long`. Der rechte Operand (die Anzahl der zu Verschiebungs enden Bitpositionen) muss `Integer` oder ein Typ sein, der zu `Integer`erweitert wird.  
  
### <a name="binary----and-mod-operators"></a>Binäre Operatoren +, –, \*und mod  
 In der folgenden Tabelle werden die Ergebnis Datentypen für die binären `+` und `–` Operatoren sowie die Operatoren `*` und `Mod` angezeigt. Beachten Sie, dass diese Tabelle symmetrisch ist. für eine bestimmte Kombination von operanddatentypen ist der Ergebnis Datentyp unabhängig von der Reihenfolge der Operanden identisch.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Short|SByte|Short|Short|Ganze Zahl|Ganze Zahl|Long|Long|Decimal|  
|`SByte`|SByte|SByte|Short|Short|Ganze Zahl|Ganze Zahl|Long|Long|Decimal|  
|`Byte`|Short|Short|Byte|Short|UShort|Ganze Zahl|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|Ganze Zahl|Ganze Zahl|Long|Long|Decimal|  
|`UShort`|Ganze Zahl|Ganze Zahl|UShort|Ganze Zahl|UShort|Ganze Zahl|UInteger|Long|ULong|  
|`Integer`|Ganze Zahl|Ganze Zahl|Ganze Zahl|Ganze Zahl|Ganze Zahl|Ganze Zahl|Long|Long|Decimal|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Decimal|  
|`ULong`|Decimal|Decimal|ULong|Decimal|ULong|Decimal|ULong|Decimal|ULong|  
  
### <a name="-operator"></a>\\-Operator  
 In der folgenden Tabelle werden die Ergebnis Datentypen für den `\`-Operator angezeigt. Beachten Sie, dass diese Tabelle symmetrisch ist. für eine bestimmte Kombination von operanddatentypen ist der Ergebnis Datentyp unabhängig von der Reihenfolge der Operanden identisch.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Short|SByte|Short|Short|Ganze Zahl|Ganze Zahl|Long|Long|Long|  
|`SByte`|SByte|SByte|Short|Short|Ganze Zahl|Ganze Zahl|Long|Long|Long|  
|`Byte`|Short|Short|Byte|Short|UShort|Ganze Zahl|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|Ganze Zahl|Ganze Zahl|Long|Long|Long|  
|`UShort`|Ganze Zahl|Ganze Zahl|UShort|Ganze Zahl|UShort|Ganze Zahl|UInteger|Long|ULong|  
|`Integer`|Ganze Zahl|Ganze Zahl|Ganze Zahl|Ganze Zahl|Ganze Zahl|Ganze Zahl|Long|Long|Long|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Long|  
|`ULong`|Long|Long|ULong|Long|ULong|Long|ULong|Long|ULong|  
  
 Wenn einer der Operanden des `\` Operators [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md), [Single](../../../visual-basic/language-reference/data-types/single-data-type.md)oder [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)ist, versucht Visual Basic, ihn in [lange](../../../visual-basic/language-reference/data-types/long-data-type.md) vor dem Vorgang zu konvertieren, und der Ergebnis Datentyp ist `Long`.  
  
## <a name="relational-and-bitwise-comparisons"></a>Relationale und bitweise Vergleiche  
 Der Ergebnis Datentyp eines relationalen Vorgangs (`=`, `<>`, `<`, `>`, `<=``>=`) ist immer `Boolean`[boolescher Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md). Das gleiche gilt für logische Vorgänge (`And`, `AndAlso`, `Not`, `Or`, `OrElse`, `Xor`) auf `Boolean` Operanden.  
  
 Der Ergebnis Datentyp einer bitweisen logischen Operation hängt von den Datentypen der Operanden ab. Beachten Sie, dass `AndAlso` und `OrElse` nur für `Boolean`definiert sind, und Visual Basic jeden Operanden nach Bedarf in `Boolean` konvertieren, bevor der Vorgang durchgeführt wird.  
  
### <a name="-----and--operators"></a>=, < >, \<, >, \<= und > =-Operatoren  
 Wenn beide Operanden `Boolean`sind, betrachtet Visual Basic `True` kleiner als `False`. Wenn ein numerischer Typ mit einem `String`verglichen wird, versucht Visual Basic, die `String` vor dem Vorgang in `Double` zu konvertieren. Ein `Char`-oder `Date` Operand kann nur mit einem anderen Operanden desselben Datentyps verglichen werden. Der Ergebnis Datentyp ist immer `Boolean`.  
  
### <a name="bitwise-not-operator"></a>Bitweiser Not-Operator  
 In der folgenden Tabelle werden die Ergebnis Datentypen für den bitweisen `Not` Operator angezeigt.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Not`|Boolesch|SByte|Byte|Short|UShort|Ganze Zahl|UInteger|Long|ULong|  
  
 Wenn der Operand `Decimal`, `Single`, `Double`oder `String`ist, versucht Visual Basic, ihn vor dem Vorgang in `Long` zu konvertieren, und der Ergebnis Datentyp ist `Long`.  
  
### <a name="bitwise-and-or-and-xor-operators"></a>Bitweise and-, or-und XOR-Operatoren  
 In der folgenden Tabelle werden die Ergebnis Datentypen für die bitweisen `And`-, `Or`-und `Xor`-Operatoren angezeigt. Beachten Sie, dass diese Tabelle symmetrisch ist. für eine bestimmte Kombination von operanddatentypen ist der Ergebnis Datentyp unabhängig von der Reihenfolge der Operanden identisch.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Boolesch|SByte|Short|Short|Ganze Zahl|Ganze Zahl|Long|Long|Long|  
|`SByte`|SByte|SByte|Short|Short|Ganze Zahl|Ganze Zahl|Long|Long|Long|  
|`Byte`|Short|Short|Byte|Short|UShort|Ganze Zahl|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|Ganze Zahl|Ganze Zahl|Long|Long|Long|  
|`UShort`|Ganze Zahl|Ganze Zahl|UShort|Ganze Zahl|UShort|Ganze Zahl|UInteger|Long|ULong|  
|`Integer`|Ganze Zahl|Ganze Zahl|Ganze Zahl|Ganze Zahl|Ganze Zahl|Ganze Zahl|Long|Long|Long|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Long|  
|`ULong`|Long|Long|ULong|Long|ULong|Long|ULong|Long|ULong|  
  
 Wenn ein Operand `Decimal`, `Single`, `Double`oder `String`ist, versucht Visual Basic, ihn vor dem Vorgang in `Long` zu konvertieren, und der Ergebnis Datentyp entspricht dem, wenn dieser Operand bereits `Long`war.  
  
## <a name="miscellaneous-operators"></a>Verschiedene Operatoren  
 Der `&`-Operator ist nur für die Verkettung von `String` Operanden definiert. Visual Basic konvertiert jeden Operanden nach Bedarf in `String` vor dem Vorgang, und der Ergebnis Datentyp ist immer `String`. Für den Zweck des `&` Operators werden alle Konvertierungen in `String` als erweiternd angesehen, auch wenn `Option Strict` `On`ist.  
  
 Die `Is`-und `IsNot` Operatoren erfordern, dass beide Operanden einen Verweistyp aufweisen. Der `TypeOf`...`Is` Ausdruck erfordert, dass der erste Operand ein Referenztyp und der zweite Operand der Name eines Datentyps ist. In all diesen Fällen ist der Ergebnis Datentyp `Boolean`.  
  
 Der `Like`-Operator ist nur für den Musterabgleich von `String`-Operanden definiert. Visual Basic versucht, jeden Operanden nach Bedarf zu konvertieren, um vor dem Vorgang `String`. Der Ergebnis Datentyp ist immer `Boolean`.  
  
## <a name="see-also"></a>Siehe auch

- [Datentypen](../../../visual-basic/language-reference/data-types/index.md)
- [Operatoren und Ausdrücke](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Arithmetische Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Vergleichs Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Operatoren](../../../visual-basic/language-reference/operators/index.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Arithmetische Operatoren](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Vergleichsoperatoren](../../../visual-basic/language-reference/operators/comparison-operators.md)
- [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md)
