---
title: Datentypen von Operatorergebnissen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- data types [Visual Basic], operator result data types
- result data types [Visual Basic]
- operator result data types [Visual Basic]
- operators [Visual Basic], data types
- data types [Visual Basic], ranges
- operators [Visual Basic], result data types
ms.assetid: 9d524533-e1a1-4aa8-b1b8-622068173d06
ms.openlocfilehash: 1169a30f25db6084b8d232c0696991b040e7ea59
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662533"
---
# <a name="data-types-of-operator-results-visual-basic"></a>Datentypen von Operatorergebnissen (Visual Basic)
Visual Basic bestimmt den Datentyp des Ergebnisses eines Vorgangs auf Grundlage der Datentypen der Operanden. In einigen Fällen kann dies einen Datentyp mit einem größeren Bereich als ein Operand sein.  
  
## <a name="data-type-ranges"></a>Datentypbereiche  
 Die Bereiche der relevanten Datentypen, in der Reihenfolge vom kleinsten zum größten, lauten wie folgt aus:  
  
- [Boolesche](../../../visual-basic/language-reference/data-types/boolean-data-type.md) – zwei mögliche Werte  
  
- [SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md) – 256 mögliche ganzzahlige Werte  
  
- [Kurze](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md) – 65.536 (6.5... E + 4) mögliche ganzzahlige Werte  
  
- [Ganze Zahl](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md) – 4.294.967.296 (4.2... E + 9) mögliche ganzzahlige Werte  
  
- [Lange](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md) – 18.446.744.073.709.551.615 (1.8... E + 19) mögliche ganzzahlige Werte  
  
- [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) – 1,5... E + 29 möglich ganzzahlige Werte, maximalen Bereich 7.9... E + 28 (absoluter Wert)  
  
- [Einzelne](../../../visual-basic/language-reference/data-types/single-data-type.md) – maximalbereich 3.4... E + 38 (absoluter Wert)  
  
- [Doppelte](../../../visual-basic/language-reference/data-types/double-data-type.md) – maximalbereich 1.7... E + 308 (absoluter Wert)  
  
 Weitere Informationen zu Visual Basic-Datentypen, finden Sie unter [Datentypen](../../../visual-basic/language-reference/data-types/index.md).  
  
 Wenn ein Operand als [nichts](../../../visual-basic/language-reference/nothing.md), die Visual Basic arithmetischen Operatoren als 0 (null) behandelt.  
  
## <a name="decimal-arithmetic"></a>Dezimale arithmetische Operationen  
 Beachten Sie, dass die [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) -Datentyp ist weder Gleitkomma oder ganze Zahl.  
  
 Wenn einer der Operanden des eine `+`, `–`, `*`, `/`, oder `Mod` Vorgang ist `Decimal` und der andere nicht `Single` oder `Double`, Visual Basic wird der andere Operand `Decimal`. Er führt den Vorgang im `Decimal`, und der Ergebniswert vom Datentyp `Decimal`.  
  
## <a name="floating-point-arithmetic"></a>Gleitkomma-Arithmetik  
 Führt die meisten Gleitkommaoperatoren in Visual Basic [doppelte](../../../visual-basic/language-reference/data-types/double-data-type.md), die die effizienteste Datentyp für Vorgänge dieser Art. Allerdings ist einer der Operanden [einzelne](../../../visual-basic/language-reference/data-types/single-data-type.md) und der andere nicht `Double`, führt den Vorgang in Visual Basic `Single`. Operanden in den entsprechenden Datentyp vor dem Bedarf erweitert werden kann, und das Ergebnis hat, dass der Datentyp.  
  
### <a name="-and--operators"></a>/ und ^ Operatoren  
 Die `/` Operator ist definiert, nur für die [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md), [einzelne](../../../visual-basic/language-reference/data-types/single-data-type.md), und [doppelte](../../../visual-basic/language-reference/data-types/double-data-type.md) -Datentypen. Visual Basic wird jeder Operand Bedarf, um den entsprechenden Datentyp, bevor Sie den Vorgang, und das Ergebnis hat, dass der Datentyp.  
  
 Die folgende Tabelle zeigt das Ergebnis von Datentypen für die `/` Operator. Beachten Sie, dass diese Tabelle symmetrisch ist. für eine bestimmte Kombination von Operandendatentypen werden soll ist der Ergebnistyp für die Daten unabhängig von der Reihenfolge der Operanden.  
  
||||||  
|---|---|---|---|---|  
||`Decimal`|`Single`|`Double`|Ein beliebiger ganzzahliger Typ|  
|`Decimal`|Decimal|Single|Double|Decimal|  
|`Single`|Single|Single|Double|Single|  
|`Double`|Double|Double|Double|Double|  
|Ein beliebiger ganzzahliger Typ|Decimal|Single|Double|Double|  
  
 Die `^` Operator ist definiert, nur für die `Double` -Datentyp. Visual Basic wird jeder Operand nach Bedarf `Double` vor dem Vorgang, und der resultierende Datentyp ist immer `Double`.  
  
## <a name="integer-arithmetic"></a>Ganzzahlarithmetik  
 Der Datentyp des Ergebnisses einer ganzzahligen Operation hängt von den Datentypen der Operanden ab. Im Allgemeinen verwendet Visual Basic die folgenden Richtlinien zur Bestimmung der Datentyp des Ergebnisses an:  
  
- Wenn beide Operanden des binären Operators die gleiche haben-Datentyp, gibt das Ergebnis dieser Datentyp hat. Eine Ausnahme ist `Boolean`, die gezwungen, `Short`.  
  
- Wenn ein Operand ohne Vorzeichen mit einem signierten-Operanden beteiligt ist, hat das Ergebnis einen Typ mit Vorzeichen mit mindestens genauso groß wie einer der Operanden.  
  
- Andernfalls hat das Ergebnis in der Regel die größere der beiden Operandendatentypen.  
  
 Beachten Sie, dass der Ergebnistyp für die Daten möglicherweise nicht mit einem Operanden der Datentypen identisch.  
  
> [!NOTE]
>  Der resultierende Datentyp ist nicht immer groß genug für alle möglichen Ergebniswerte aus dem Vorgang. Ein <xref:System.OverflowException> Ausnahme kann auftreten, wenn der Wert für den Datentyp des Ergebnisses zu groß ist.  
  
### <a name="unary--and--operators"></a>Unäre + und -Operatoren  
 Die folgende Tabelle zeigt das Ergebnis für die zwei unäre Operatoren `+` und `–`.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|Unäre `+`|Short|SByte|Byte|Short|UShort|Ganze Zahl|UInteger|Long|ULong|  
|Unäre `–`|Short|SByte|Short|Short|Ganze Zahl|Ganze Zahl|Long|Long|Decimal|  
  
### <a name="-and--operators"></a><\< und >> Operatoren  
 Die folgende Tabelle zeigt das Ergebnis für die zwei Bitschiebeoperatoren `<<` und `>>`. Visual Basic behandelt jede Bitverschiebungsoperator als unäroperator auf der linke Operand (das Bitmuster verschoben werden sollen).  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`<<`, `>>`|Short|SByte|Byte|Short|UShort|Ganze Zahl|UInteger|Long|ULong|  
  
 Wenn der linke Operand ist `Decimal`, `Single`, `Double`, oder `String`, versucht Visual Basic konvertiert `Long` vor dem Vorgang, und das Ergebnis ist der Datentyp `Long`. Der Rechte Operand (die Anzahl der Bitpositionen) muss `Integer` oder ein Typ, der auf Erweitert `Integer`.  
  
### <a name="binary----and-mod-operators"></a>Binär +, -, *, und Mod-Operator  
 Die folgende Tabelle zeigt das Ergebnis der binären `+` und `–` Operatoren und die `*` und `Mod` Operatoren. Beachten Sie, dass diese Tabelle symmetrisch ist. für eine bestimmte Kombination von Operandendatentypen werden soll ist der Ergebnistyp für die Daten unabhängig von der Reihenfolge der Operanden.  
  
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
  
### <a name="-operator"></a>\-Operator  
 Die folgende Tabelle zeigt das Ergebnis von Datentypen für die `\` Operator. Beachten Sie, dass diese Tabelle symmetrisch ist. für eine bestimmte Kombination von Operandendatentypen werden soll ist der Ergebnistyp für die Daten unabhängig von der Reihenfolge der Operanden.  
  
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
  
 Wenn einer der Operanden des der `\` Operator ist [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md), [einzelne](../../../visual-basic/language-reference/data-types/single-data-type.md), oder [doppelte](../../../visual-basic/language-reference/data-types/double-data-type.md), versucht Visual Basic konvertiert [lang](../../../visual-basic/language-reference/data-types/long-data-type.md)vor dem Vorgang, und das Ergebnis ist der Datentyp `Long`.  
  
## <a name="relational-and-bitwise-comparisons"></a>Relationale und bitweise Vergleiche  
 Der Datentyp des Ergebnisses einer relationalen Operation (`=`, `<>`, `<`, `>`, `<=`, `>=`) ist immer `Boolean` [Boolean-Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md). Das gleiche gilt für die logischen Operationen (`And`, `AndAlso`, `Not`, `Or`, `OrElse`, `Xor`) auf `Boolean` Operanden.  
  
 Der Datentyp des Ergebnisses eines bitweisen logischen Vorgangs hängt von den Datentypen der Operanden ab. Beachten Sie, dass `AndAlso` und `OrElse` werden nur für definiert `Boolean`, und Visual Basic konvertiert alle Operanden nach Bedarf `Boolean` vor dem Ausführen des Vorgangs.  
  
### <a name="-----and--operators"></a>=, <>, \<, >, \<= und > = Operatoren  
 Wenn beide Operanden sind `Boolean`, berücksichtigt Visual Basic `True` sich weniger als `False`. Wenn ein numerischer Typ mit dem verglichen wird eine `String`, Visual Basic versucht, konvertieren die `String` zu `Double` vor dem Vorgang. Ein `Char` oder `Date` Operand kann nur mit einem anderen Operanden den gleichen Datentyp verglichen werden. Datentyp des Ergebnisses ist immer `Boolean`.  
  
### <a name="bitwise-not-operator"></a>Bitweiser Not-Operator  
 Die folgende Tabelle zeigt das Ergebnis für den bitweisen `Not` Operator.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Not`|Boolesch|SByte|Byte|Short|UShort|Ganze Zahl|UInteger|Long|ULong|  
  
 Wenn der Operand ist `Decimal`, `Single`, `Double`, oder `String`, versucht Visual Basic konvertiert `Long` vor dem Vorgang, und das Ergebnis ist der Datentyp `Long`.  
  
### <a name="bitwise-and-or-and-xor-operators"></a>Bitweises und und und Xor-Operatoren  
 Die folgende Tabelle zeigt das Ergebnis für den bitweisen `And`, `Or`, und `Xor` Operatoren. Beachten Sie, dass diese Tabelle symmetrisch ist. für eine bestimmte Kombination von Operandendatentypen werden soll ist der Ergebnistyp für die Daten unabhängig von der Reihenfolge der Operanden.  
  
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
  
 Wenn ein Operand `Decimal`, `Single`, `Double`, oder `String`, versucht Visual Basic konvertiert `Long` vor, und die Ergebnisdaten der Vorgang ist vom selben Datentyp wie bei Operanden bereits waren `Long`.  
  
## <a name="miscellaneous-operators"></a>Verschiedene Operatoren  
 Die `&` Operator ist definiert, nur für die Verkettung von `String` Operanden. Visual Basic konvertiert alle Operanden nach Bedarf `String` vor dem Vorgang, und der resultierende Datentyp ist immer `String`. Im Rahmen der `&` Operator, der alle Konvertierungen in `String` gelten erweiternde werden, auch wenn `Option Strict` ist `On`.  
  
 Die `Is` und `IsNot` Operatoren müssen beide Operanden eines Referenztyps sein. Die `TypeOf`... `Is` Ausdruck erfordert der erste Operand eines Referenztyps sein und der zweite Operand, der Name eines Datentyps sein. In all diesen Fällen die Ergebnisdaten der Typ ist `Boolean`.  
  
 Die `Like` Operator ist definiert, nur für den Musterabgleich des `String` Operanden. Visual Basic versucht, jeden Operanden nach Bedarf konvertieren `String` vor dem Vorgang. Datentyp des Ergebnisses ist immer `Boolean`.  
  
## <a name="see-also"></a>Siehe auch

- [Datentypen](../../../visual-basic/language-reference/data-types/index.md)
- [Operatoren und Ausdrücke](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Arithmetische Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Vergleichsoperatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Operatoren](../../../visual-basic/language-reference/operators/index.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Arithmetische Operatoren](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Vergleichsoperatoren](../../../visual-basic/language-reference/operators/comparison-operators.md)
- [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md)
