---
title: Datentypen von Operatorergebnissen (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- data types [Visual Basic], operator result data types
- result data types [Visual Basic]
- operator result data types [Visual Basic]
- operators [Visual Basic], data types
- data types [Visual Basic], ranges
- operators [Visual Basic], result data types
ms.assetid: 9d524533-e1a1-4aa8-b1b8-622068173d06
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 61e8fb785830152acfd7e8e2e1784294053ac66e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="data-types-of-operator-results-visual-basic"></a>Datentypen von Operatorergebnissen (Visual Basic)
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]Bestimmt den Datentyp des Ergebnisses eines Vorgangs basierend auf den Datentypen der Operanden an. In einigen Fällen kann dies einen Datentyp mit einem größeren Bereich als der beiden Operanden sein.  
  
## <a name="data-type-ranges"></a>Datentypbereiche  
 Die Bereiche der relevanten Datentypen in der Reihenfolge vom kleinsten zum größten lauten wie folgt:  
  
-   [Boolesche](../../../visual-basic/language-reference/data-types/boolean-data-type.md) – zwei mögliche Werte  
  
-   [SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md) – 256 mögliche ganzzahlige Werte  
  
-   [Kurze](../../../visual-basic/language-reference/data-types/short-data-type.md), ["ushort"](../../../visual-basic/language-reference/data-types/ushort-data-type.md) – 65.536 (6.5... E + 4) mögliche ganzzahlige Werte  
  
-   [Ganze Zahl](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md) – 4.294.967.296 (4.2... E + 9) mögliche ganzzahlige Werte  
  
-   [Lange](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md) – 18.446.744.073.709.551.615 (1.8... E + 19) mögliche ganzzahlige Werte  
  
-   [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) – 1,5... E + 29 mögliche ganzzahlige Werte, maximalen Bereich 7.9... E + 28 (absoluter Wert)  
  
-   [Einzelne](../../../visual-basic/language-reference/data-types/single-data-type.md) – maximaler Bereich 3.4.. E + 38 (absoluter Wert)  
  
-   [Doppelte](../../../visual-basic/language-reference/data-types/double-data-type.md) – maximaler Bereich 1.7.. E + 308 (absoluter Wert)  
  
 Weitere Informationen zu [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] -Datentypen finden Sie unter [Datentypen](../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
 Wenn ein Operand als [nichts](../../../visual-basic/language-reference/nothing.md)die [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] arithmetische Operatoren als 0 (null) behandelt.  
  
## <a name="decimal-arithmetic"></a>Dezimale arithmetische Operationen  
 Beachten Sie, dass die [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) -Datentyp ist weder Gleitkommazahlen noch ganze Zahl.  
  
 Wenn jeder Operand von einem `+`, `–`, `*`, `/`, oder `Mod` Vorgang ist `Decimal` und die andere nicht `Single` oder `Double`, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] erweitert wird der andere Operand `Decimal`. Er führt den Vorgang im `Decimal`, und der Ergebniswert vom Datentyp `Decimal`.  
  
## <a name="floating-point-arithmetic"></a>Gleitkommazahlen  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]führt die meisten in der Gleitkommaarithmetik [doppelte](../../../visual-basic/language-reference/data-types/double-data-type.md), also die effizientesten Daten für diese Vorgänge geben. Jedoch, wenn ein Operand [einzelne](../../../visual-basic/language-reference/data-types/single-data-type.md) und die andere nicht `Double`, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] führt den Vorgang im `Single`. Jeder Operand nach Bedarf in den entsprechenden Datentyp vor dem Vorgang erweitert werden kann, und das Ergebnis hat diesen Datentyp.  
  
### <a name="-and--operators"></a>/ und ^ Operatoren  
 Die `/` Operator definiert ist, nur für die [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md), [einzelne](../../../visual-basic/language-reference/data-types/single-data-type.md), und [doppelte](../../../visual-basic/language-reference/data-types/double-data-type.md) Datentypen. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]erweitert jeden Operanden nach Bedarf in den entsprechenden Datentyp aus, bevor der Vorgang, und das Ergebnis hat diesen Datentyp.  
  
 Die folgende Tabelle zeigt das Ergebnis von Datentypen für die `/` Operator. Beachten Sie, dass diese Tabelle symmetrisch ist. für eine bestimmte Kombination von Operandendatentypen entspricht der Resultset-Datentyp mit dem unabhängig von der Reihenfolge der Operanden.  
  
||||||  
|---|---|---|---|---|  
||`Decimal`|`Single`|`Double`|Jeden ganzzahligen Typ|  
|`Decimal`|Decimal|Single|Double|Decimal|  
|`Single`|Single|Single|Double|Single|  
|`Double`|Double|Double|Double|Double|  
|Jeden ganzzahligen Typ|Decimal|Single|Double|Double|  
  
 Die `^` Operator definiert ist, nur für die `Double` -Datentyp. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]Jeder Operand nach Bedarf erweitert `Double` vor dem Vorgang, und der resultierende Datentyp ist immer `Double`.  
  
## <a name="integer-arithmetic"></a>Ganzzahlarithmetik  
 Der Datentyp des Ergebnisses eines Integer-Vorgangs hängt von den Datentypen der Operanden ab. Im allgemeinen [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] die folgenden Richtlinien zur Bestimmung der Datentyp des Ergebnisses verwendet:  
  
-   Wenn beide Operanden des binären Operators identischem-Datentyp, gibt das Ergebnis dieser Datentyp hat. Eine Ausnahme ist `Boolean`, gezwungen, `Short`.  
  
-   Wenn ein Operand ohne Vorzeichen mit einem Operanden und signierte eingebunden ist, hat das Ergebnis ein Datentyp mit Vorzeichen mindestens genauso groß als einer der Operanden.  
  
-   Andernfalls hat das Ergebnis in der Regel das größere der beiden Operandendatentypen.  
  
 Beachten Sie, dass der Datentyp des Ergebnisses möglicherweise nicht mit einem Operanden der Datentypen identisch.  
  
> [!NOTE]
>  Der Ergebnisdatentyp ist nicht immer groß genug für alle möglichen Werte, die sich aus dem Vorgang ergeben. Ein <xref:System.OverflowException> Ausnahme kann auftreten, wenn der Wert für den Ergebnisdatentyp zu groß ist.  
  
### <a name="unary--and--operators"></a>Unäre + "und" – Operatoren  
 Die folgende Tabelle zeigt das Ergebnis für die zwei unäre Operatoren `+` und `–`.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|Unäre`+`|Short|SByte|Byte|Short|UShort|Ganze Zahl|UInteger|Long|ULong|  
|Unäre`–`|Short|SByte|Short|Short|Ganze Zahl|Ganze Zahl|Long|Long|Decimal|  
  
### <a name="-and--operators"></a><\<und >> Operatoren  
 Die folgende Tabelle zeigt das Ergebnis für die beiden Bitschiebeoperatoren `<<` und `>>`. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]behandelt jede Bitverschiebungsoperator als unäroperator auf dem linken Operanden (das Bitmuster verschoben werden sollen).  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`<<`, `>>`|Short|SByte|Byte|Short|UShort|Ganze Zahl|UInteger|Long|ULong|  
  
 Wenn der linke Operand ist `Decimal`, `Single`, `Double`, oder `String`, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] versucht, ihn zu konvertieren, `Long` vor dem Vorgang, und das Ergebnis ist der Datentyp `Long`. Der Rechte Operand (die Anzahl von Bitpositionen) muss `Integer` oder ein Typ, der erweitert `Integer`.  
  
### <a name="binary----and-mod-operators"></a>Binär +, -, *, und Mod-Operator  
 Die folgende Tabelle zeigt das Ergebnis der binären `+` und `–` Operatoren und die `*` und `Mod` Operatoren. Beachten Sie, dass diese Tabelle symmetrisch ist. für eine bestimmte Kombination von Operandendatentypen entspricht der Resultset-Datentyp mit dem unabhängig von der Reihenfolge der Operanden.  
  
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
 Die folgende Tabelle zeigt das Ergebnis von Datentypen für die `\` Operator. Beachten Sie, dass diese Tabelle symmetrisch ist. für eine bestimmte Kombination von Operandendatentypen entspricht der Resultset-Datentyp mit dem unabhängig von der Reihenfolge der Operanden.  
  
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
  
 Wenn jeder Operand von der `\` Operator [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md), [einzelne](../../../visual-basic/language-reference/data-types/single-data-type.md), oder [doppelte](../../../visual-basic/language-reference/data-types/double-data-type.md), [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] versucht, ihn zu konvertieren, [lang](../../../visual-basic/language-reference/data-types/long-data-type.md) vor dem Vorgang, und das Ergebnis ist der Datentyp `Long`.  
  
## <a name="relational-and-bitwise-comparisons"></a>Relationale und bitweise Vergleiche  
 Der Datentyp des Ergebnisses eines relationalen-Vorgangs (`=`, `<>`, `<`, `>`, `<=`, `>=`) immer `Boolean` [booleschen Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md). Dasselbe gilt für logische Operationen (`And`, `AndAlso`, `Not`, `Or`, `OrElse`, `Xor`) auf `Boolean` Operanden.  
  
 Der Ergebnisdatentyp des eine bitweise logische Operation hängt von den Datentypen der Operanden ab. Beachten Sie, dass `AndAlso` und `OrElse` werden nur für definiert `Boolean`, und [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] jeder Operand nach Bedarf konvertiert `Boolean` vor dem Ausführen des Vorgangs.  
  
### <a name="-----and--operators"></a>= <>, \<, >, \<= und > = Operatoren  
 Wenn beide Operanden `Boolean`, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] betrachtet `True` werden weniger als `False`. Wenn mit ein numerischer Typ verglichen wird eine `String`, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] versucht, konvertieren die `String` auf `Double` vor dem Vorgang. Ein `Char` oder `Date` Operand kann nur mit einem anderen Operanden des gleichen Datentyps verglichen werden. Datentyp des Ergebnisses ist immer `Boolean`.  
  
### <a name="bitwise-not-operator"></a>Bitweiser Not-Operator  
 Die folgende Tabelle zeigt das Ergebnis von Datentypen für die bitweise `Not` Operator.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Not`|Boolesch|SByte|Byte|Short|UShort|Ganze Zahl|UInteger|Long|ULong|  
  
 Wenn der Operand `Decimal`, `Single`, `Double`, oder `String`, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] versucht, ihn zu konvertieren, `Long` vor dem Vorgang, und das Ergebnis ist der Datentyp `Long`.  
  
### <a name="bitwise-and-or-and-xor-operators"></a>Bitweises und, oder, und Xor-Operatoren  
 Die folgende Tabelle zeigt das Ergebnis von Datentypen für die bitweise `And`, `Or`, und `Xor` Operatoren. Beachten Sie, dass diese Tabelle symmetrisch ist. für eine bestimmte Kombination von Operandendatentypen entspricht der Resultset-Datentyp mit dem unabhängig von der Reihenfolge der Operanden.  
  
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
  
 Wenn ein Operand wird `Decimal`, `Single`, `Double`, oder `String`, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] versucht, ihn zu konvertieren, `Long` vor, und die Ergebnisdaten der Vorgang ist vom selben Datentyp wie bei Operanden bereits zurückging `Long`.  
  
## <a name="miscellaneous-operators"></a>Verschiedene Operatoren  
 Die `&` Operator ist nur für die Verkettung von definiert `String` Operanden. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]Jeder Operand nach Bedarf konvertiert `String` vor dem Vorgang, und der resultierende Datentyp ist immer `String`. Im Rahmen der `&` Operator, alle Konvertierungen in `String` gelten als erweiternde werden, selbst wenn `Option Strict` ist `On`.  
  
 Die `Is` und `IsNot` Operatoren müssen beide Operanden eines Verweistyps sein. Die `TypeOf`... `Is` Ausdruck ist der erste Operand eines Verweistyps sein und der zweite Operand ist der Name eines Datentyps erforderlich. In all diesen Fällen die Ergebnisdaten Typ ist `Boolean`.  
  
 Die `Like` Operator ist nur für den Mustervergleich, der definiert `String` Operanden. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]versucht, jeden Operanden nach Bedarf konvertieren `String` vor dem Vorgang. Datentyp des Ergebnisses ist immer `Boolean`.  
  
## <a name="see-also"></a>Siehe auch  
 [Datentypen](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Operatoren und Ausdrücke](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [Arithmetische Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [Vergleichsoperatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [Operatoren](../../../visual-basic/language-reference/operators/index.md)  
 [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Arithmetische Operatoren](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Vergleichsoperatoren](../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md)
