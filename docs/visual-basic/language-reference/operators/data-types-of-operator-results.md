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
ms.openlocfilehash: f7a1249cec159f98ede48b960fadc5e2ff4a75f3
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867097"
---
# <a name="data-types-of-operator-results-visual-basic"></a>Datentypen von Operatorergebnissen (Visual Basic)

Visual Basic bestimmt den Ergebnis Datentyp eines Vorgangs auf der Grundlage der Datentypen der Operanden. In einigen Fällen kann dies ein Datentyp mit einem größeren Bereich sein als der eines der beiden Operanden.  
  
## <a name="data-type-ranges"></a>Datentypbereiche  

 Die Bereiche der relevanten Datentypen, von der niedrigsten zum größten, sind wie folgt:  
  
- [Boolescher](../data-types/boolean-data-type.md) Wert – zwei mögliche Werte  
  
- [SByte](../data-types/sbyte-data-type.md), [Byte](../data-types/byte-data-type.md) – 256 mögliche ganzzahlige Werte  
  
- [Short](../data-types/short-data-type.md), [UShort](../data-types/ushort-data-type.md) – 65.536 (6.5... E + 4) mögliche ganzzahlige Werte  
  
- [Integer](../data-types/integer-data-type.md), [UInteger](../data-types/uinteger-data-type.md) – 4.294.967.296 (4.2... E + 9) mögliche ganzzahlige Werte  
  
- [Long](../data-types/long-data-type.md), [ulong](../data-types/ulong-data-type.md) – 18446744073709551615 (1.8... E + 19) mögliche ganzzahlige Werte  
  
- [Decimal](../data-types/decimal-data-type.md) – 1.5... e + 29 mögliche ganzzahlige Werte, maximaler Bereich 7,9... e + 28 (absoluter Wert)  
  
- [Single](../data-types/single-data-type.md) – maximaler Bereich von 3.4... E + 38 (absoluter Wert)  
  
- [Double](../data-types/double-data-type.md) – maximaler Bereich 1.7... E + 308 (absoluter Wert)  
  
 Weitere Informationen zu Visual Basic-Datentypen finden Sie unter [Datentypen](../data-types/index.md).  
  
 Wenn ein Operand als " [Nothing](../nothing.md)" ausgewertet wird, wird er von den Visual Basic arithmetischen Operatoren als NULL behandelt.  
  
## <a name="decimal-arithmetic"></a>Dezimal Arithmetik  

 Beachten Sie, dass der [Decimal](../data-types/decimal-data-type.md) -Datentyp weder Gleit Komma noch Integer ist.  
  
 Wenn einer der Operanden eines `+` -,-,-, `–` `*` `/` `Mod` -oder-Vorgangs ist `Decimal` und der andere nicht `Single` oder ist, wird `Double` Visual Basic den anderen Operanden auf erweitert `Decimal` . Der Vorgang `Decimal` wird in durchführt, und der Ergebnis Datentyp ist `Decimal` .  
  
## <a name="floating-point-arithmetic"></a>Gleit Komma Arithmetik  

 Visual Basic führt die meisten Gleit Komma Arithmetik in [Double](../data-types/double-data-type.md)aus. Dies ist der effizienteste Datentyp für solche Vorgänge. Wenn ein Operand jedoch [Single](../data-types/single-data-type.md) und der andere nicht ist `Double` , führt Visual Basic den Vorgang in aus `Single` . Er erweitert jeden Operanden nach Bedarf auf den entsprechenden Datentyp vor dem Vorgang, und das Ergebnis hat diesen Datentyp.  
  
### <a name="-and--operators"></a>/und ^-Operatoren  

 Der `/` -Operator ist nur für die Datentypen [Decimal](../data-types/decimal-data-type.md), [Single](../data-types/single-data-type.md)und [Double](../data-types/double-data-type.md) definiert. Visual Basic jeden Operanden nach Bedarf auf den entsprechenden Datentyp vor dem Vorgang erweitert, und das Ergebnis hat diesen Datentyp.  
  
 In der folgenden Tabelle werden die Ergebnis Datentypen für den- `/` Operator angezeigt. Beachten Sie, dass diese Tabelle symmetrisch ist. für eine bestimmte Kombination von operanddatentypen ist der Ergebnis Datentyp unabhängig von der Reihenfolge der Operanden identisch.  
  
||||||  
|---|---|---|---|---|  
||`Decimal`|`Single`|`Double`|Beliebige ganzzahlige Typen|  
|`Decimal`|Decimal|Single|Double|Decimal|  
|`Single`|Single|Single|Double|Single|  
|`Double`|Double|Double|Double|Double|  
|Beliebige ganzzahlige Typen|Decimal|Single|Double|Double|  
  
 Der- `^` Operator ist nur für den- `Double` Datentyp definiert. Visual Basic den einzelnen Operanden nach Bedarf `Double` vor dem-Vorgang erweitert, und der Ergebnis Datentyp lautet immer `Double` .  
  
## <a name="integer-arithmetic"></a>Arithmetische Ganzzahl  

 Der Ergebnis Datentyp einer ganzzahligen Operation hängt von den Datentypen der Operanden ab. Im Allgemeinen verwendet Visual Basic die folgenden Richtlinien zur Bestimmung des Ergebnis Datentyps:  
  
- Wenn beide Operanden eines binären Operators denselben Datentyp aufweisen, hat das Ergebnis diesen Datentyp. Eine Ausnahme ist `Boolean` , die zu erzwungen wird `Short` .  
  
- Wenn ein nicht signierter Operand an einem signierten Operanden teilnimmt, verfügt das Ergebnis über einen signierten Typ, der mindestens so groß ist wie der Operand.  
  
- Andernfalls verfügt das Ergebnis in der Regel über den größeren der beiden Operanden Datentypen.  
  
 Beachten Sie, dass der Ergebnis Datentyp möglicherweise nicht mit dem Datentyp "Operand" identisch ist.  
  
> [!NOTE]
> Der Ergebnis Datentyp ist nicht immer groß genug, um alle möglichen Werte zu speichern, die sich aus dem Vorgang ergeben. Eine <xref:System.OverflowException> Ausnahme kann auftreten, wenn der Wert für den Ergebnis Datentyp zu groß ist.  
  
### <a name="unary--and--operators"></a>Unäre +-und –-Operatoren  

 In der folgenden Tabelle werden die Ergebnis Datentypen für die beiden unären Operatoren `+` und angezeigt `–` .  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|Unären `+`|Short|SByte|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
|Unären `–`|Short|SByte|Short|Short|Integer|Integer|Long|Long|Decimal|  
  
### <a name="-and--operators"></a><\< and >>-Operatoren  

 In der folgenden Tabelle werden die Ergebnis Datentypen für die beiden BitShift-Operatoren, und, angezeigt `<<` `>>` . Visual Basic behandelt jeden Bitverschiebungs Operator als unären Operator für den linken Operanden (das Bitmuster, das verschoben werden soll).  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`<<`, `>>`|Short|SByte|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
  
 Wenn der linke Operand `Decimal` ,, `Single` oder ist `Double` `String` , Visual Basic versucht, ihn `Long` vor dem-Vorgang in zu konvertieren, und der Ergebnis Datentyp ist `Long` . Der rechte Operand (die Anzahl der zu Verschiebungs enden Bitpositionen) muss `Integer` oder ein Typ sein, der zu erweitert wird `Integer` .  
  
### <a name="binary----and-mod-operators"></a>Binäre Operatoren +, –, \* und mod  

 In der folgenden Tabelle werden die Ergebnis Datentypen für die binären `+` -und- `–` Operatoren sowie die `*` `Mod` Operatoren und angezeigt. Beachten Sie, dass diese Tabelle symmetrisch ist. für eine bestimmte Kombination von operanddatentypen ist der Ergebnis Datentyp unabhängig von der Reihenfolge der Operanden identisch.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Short|SByte|Short|Short|Integer|Integer|Long|Long|Decimal|  
|`SByte`|SByte|SByte|Short|Short|Integer|Integer|Long|Long|Decimal|  
|`Byte`|Short|Short|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|Integer|Integer|Long|Long|Decimal|  
|`UShort`|Integer|Integer|UShort|Integer|UShort|Integer|UInteger|Long|ULong|  
|`Integer`|Integer|Integer|Integer|Integer|Integer|Integer|Long|Long|Decimal|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Decimal|  
|`ULong`|Decimal|Decimal|ULong|Decimal|ULong|Decimal|ULong|Decimal|ULong|  
  
### <a name="-operator"></a>\\-Operator  

 In der folgenden Tabelle werden die Ergebnis Datentypen für den- `\` Operator angezeigt. Beachten Sie, dass diese Tabelle symmetrisch ist. für eine bestimmte Kombination von operanddatentypen ist der Ergebnis Datentyp unabhängig von der Reihenfolge der Operanden identisch.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Short|SByte|Short|Short|Integer|Integer|Long|Long|Long|  
|`SByte`|SByte|SByte|Short|Short|Integer|Integer|Long|Long|Long|  
|`Byte`|Short|Short|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|Integer|Integer|Long|Long|Long|  
|`UShort`|Integer|Integer|UShort|Integer|UShort|Integer|UInteger|Long|ULong|  
|`Integer`|Integer|Integer|Integer|Integer|Integer|Integer|Long|Long|Long|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Long|  
|`ULong`|Long|Long|ULong|Long|ULong|Long|ULong|Long|ULong|  
  
 Wenn einer der Operanden des `\` Operators [Decimal](../data-types/decimal-data-type.md), [Single](../data-types/single-data-type.md)oder [Double](../data-types/double-data-type.md)ist, Visual Basic versucht, ihn in [Long](../data-types/long-data-type.md) vor dem Vorgang zu konvertieren, und der Ergebnis Datentyp ist `Long` .  
  
## <a name="relational-and-bitwise-comparisons"></a>Relationale und bitweise Vergleiche  

 Der Ergebnis Datentyp eines relationalen Vorgangs ( `=` , `<>` , `<` , `>` , `<=` , `>=` ) ist immer ein `Boolean` [boolescher Datentyp](../data-types/boolean-data-type.md). Das gleiche gilt für logische Operationen ( `And` , `AndAlso` , `Not` , `Or` , `OrElse` ,) für `Xor` `Boolean` Operanden.  
  
 Der Ergebnis Datentyp einer bitweisen logischen Operation hängt von den Datentypen der Operanden ab. Beachten Sie, dass `AndAlso` und `OrElse` nur für definiert sind `Boolean` , und Visual Basic jeden Operanden nach Bedarf in konvertieren, `Boolean` bevor der Vorgang durchgeführt wird.  
  
### <a name="-----and--operators"></a>=,  <>, \<, > , \<=, and > =-Operatoren  

 Wenn beide Operanden sind `Boolean` , wird Visual Basic `True` als kleiner als betrachtet `False` . Wenn ein numerischer Typ mit einem verglichen wird `String` , versucht Visual Basic, den `String` in `Double` vor dem-Vorgang zu konvertieren. Ein `Char` -oder- `Date` Operand kann nur mit einem anderen Operanden desselben Datentyps verglichen werden. Der Ergebnis Datentyp lautet immer `Boolean` .  
  
### <a name="bitwise-not-operator"></a>Bitweiser Not-Operator  

 In der folgenden Tabelle werden die Ergebnis Datentypen für den bitweisen `Not` Operator angezeigt.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Not`|Boolean|SByte|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
  
 Wenn der Operand ist,, `Decimal` `Single` `Double` oder `String` , Visual Basic versucht, ihn `Long` vor dem-Vorgang in zu konvertieren, und der Ergebnis Datentyp ist `Long` .  
  
### <a name="bitwise-and-or-and-xor-operators"></a>Bitweise and-, or-und XOR-Operatoren  

 In der folgenden Tabelle werden die Ergebnis Datentypen für die bitweisen `And` `Or` Operatoren, und angezeigt `Xor` . Beachten Sie, dass diese Tabelle symmetrisch ist. für eine bestimmte Kombination von operanddatentypen ist der Ergebnis Datentyp unabhängig von der Reihenfolge der Operanden identisch.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Boolean|SByte|Short|Short|Integer|Integer|Long|Long|Long|  
|`SByte`|SByte|SByte|Short|Short|Integer|Integer|Long|Long|Long|  
|`Byte`|Short|Short|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|Integer|Integer|Long|Long|Long|  
|`UShort`|Integer|Integer|UShort|Integer|UShort|Integer|UInteger|Long|ULong|  
|`Integer`|Integer|Integer|Integer|Integer|Integer|Integer|Long|Long|Long|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Long|  
|`ULong`|Long|Long|ULong|Long|ULong|Long|ULong|Long|ULong|  
  
 Wenn ein Operand ist `Decimal` , `Single` , `Double` oder `String` , Visual Basic versucht, ihn `Long` vor dem-Vorgang in zu konvertieren, und der Ergebnis Datentyp entspricht dem, wenn der Operand bereits war `Long` .  
  
## <a name="miscellaneous-operators"></a>Verschiedene Operatoren  

 Der- `&` Operator ist nur für die Verkettung von `String` Operanden definiert. Visual Basic konvertiert jeden Operanden nach Bedarf in `String` vor dem-Vorgang, und der Ergebnis Datentyp lautet immer `String` . Für den-Operator werden `&` alle Konvertierungen in `String` als erweiterter Wert betrachtet, auch wenn gleich `Option Strict` ist `On` .  
  
 Der `Is` -Operator und der- `IsNot` Operator erfordern, dass beide Operanden einen Verweistyp aufweisen. Der `TypeOf` Ausdruck "..." `Is` erfordert, dass der erste Operand ein Verweistyp und der zweite Operand der Name eines Datentyps ist. In all diesen Fällen ist der Ergebnis Datentyp `Boolean` .  
  
 Der- `Like` Operator wird nur für den Musterabgleich von `String` Operanden definiert. Visual Basic versucht, jeden Operanden nach Bedarf in `String` vor dem-Vorgang zu konvertieren. Der Ergebnis Datentyp lautet immer `Boolean` .  
  
## <a name="see-also"></a>Weitere Informationen

- [Datentypen](../data-types/index.md)
- [Operatoren und Ausdrücke](../../programming-guide/language-features/operators-and-expressions/index.md)
- [Arithmetische Operatoren in Visual Basic](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Comparison Operators in Visual Basic](../../programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Operatoren](index.md)
- [Operatorrangfolge in Visual Basic](operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](operators-listed-by-functionality.md)
- [Arithmetic Operators (Arithmetische Operatoren)](arithmetic-operators.md)
- [Comparison Operators (Vergleichsoperatoren)](comparison-operators.md)
- [Option Strict-Anweisung](../statements/option-strict-statement.md)
