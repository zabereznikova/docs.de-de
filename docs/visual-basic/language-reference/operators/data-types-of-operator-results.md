---
title: Datentypen von Operatorergebnissen (Visual Basic) | Microsoft-Dokumentation
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
- data types [Visual Basic], operator result data types
- result data types
- operator result data types
- operators [Visual Basic], data types
- data types [Visual Basic], ranges
- operators [Visual Basic], result data types
ms.assetid: 9d524533-e1a1-4aa8-b1b8-622068173d06
caps.latest.revision: 27
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
ms.openlocfilehash: 577be6330cb76da436470c383841a717dd6e3200
ms.lasthandoff: 03/13/2017

---
# <a name="data-types-of-operator-results-visual-basic"></a>Datentypen von Operatorergebnissen (Visual Basic)
[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Bestimmt den Ergebnisdatentyp einer Operation anhand der Datentypen der Operanden. In einigen Fällen kann dies einen Datentyp mit einem größeren Bereich als der Operand sein.  
  
## <a name="data-type-ranges"></a>Datentypbereiche  
 Die Bereiche der relevanten Datentypen in der Reihenfolge von kleinsten zum größten lauten wie folgt:  
  
-   [Boolesche](../../../visual-basic/language-reference/data-types/boolean-data-type.md) – zwei mögliche Werte  
  
-   [SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md) – 256 mögliche ganzzahlige Werte  
  
-   [Kurze](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md) – 65.536 (6.5... E + 4) mögliche ganzzahlige Werte  
  
-   [Ganze Zahl](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md) – 4.294.967.296 (4.2... E + 9) mögliche ganzzahlige Werte  
  
-   [Lange](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md) – 18.446.744.073.709.551.615 (1.8... E + 19) mögliche ganzzahlige Werte  
  
-   [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) – 1.5... E + 29 mögliche ganzzahlige Werte, maximaler Bereich 7,9... E + 28 (absoluter Wert)  
  
-   [Einzelne](../../../visual-basic/language-reference/data-types/single-data-type.md) – maximaler Bereich 3.4.. E + 38 (absoluter Wert)  
  
-   [Doppelte](../../../visual-basic/language-reference/data-types/double-data-type.md) – maximaler Bereich 1.7.. E + 308 (absoluter Wert)  
  
 Weitere Informationen zu [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Datentypen finden Sie in [Datentypen](../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
 Wenn ein Operand als [nichts](../../../visual-basic/language-reference/nothing.md)der [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] arithmetische Operatoren als&0; (null) behandelt.  
  
## <a name="decimal-arithmetic"></a>Dezimale arithmetische Operationen  
 Beachten Sie, dass die [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) Datentyp ist weder Gleitkommazahlen noch ganze Zahlen darstellt.  
  
 Wenn ein Operand ein `+`, `–`, `*`, `/`, oder `Mod` Vorgang ist `Decimal` und der andere Operand nicht `Single` oder `Double`, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] erweitert wird der andere Operand `Decimal`. Er führt den Vorgang im `Decimal`, und der resultierende Datentyp ist `Decimal`.  
  
## <a name="floating-point-arithmetic"></a>Gleitkommazahlen  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]führt die meisten in der Gleitkommaarithmetik [doppelte](../../../visual-basic/language-reference/data-types/double-data-type.md), die der effizienteste Datentyp für Vorgänge. Allerdings ist einer der Operanden [einzelne](../../../visual-basic/language-reference/data-types/single-data-type.md) und der andere Operand nicht `Double`, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] führt den Vorgang im `Single`. Jeder Operand nach Bedarf in den entsprechenden Datentyp vor der Operation erweitert werden kann, und das Ergebnis hat diesen Datentyp.  
  
### <a name="-and--operators"></a>/ und ^ Operatoren  
 Die `/` Operator wird nur für definiert die [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md), [einzelne](../../../visual-basic/language-reference/data-types/single-data-type.md), und [doppelte](../../../visual-basic/language-reference/data-types/double-data-type.md) Datentypen. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]wird erweitert jeden Operanden nach Bedarf in den entsprechenden Datentyp aus, bevor Sie den Vorgang, und das Ergebnis hat diesen Datentyp.  
  
 Die folgende Tabelle zeigt das Ergebnis von Datentypen für die `/` Operator. Beachten Sie, dass diese Tabelle symmetrisch ist. für jede dieser Kombinationen von Operandentypen Daten ist der Datentyp des Ergebnisses unabhängig von der Reihenfolge der Operanden.  
  
||||||  
|---|---|---|---|---|  
||`Decimal`|`Single`|`Double`|Jeden ganzzahligen Typ|  
|`Decimal`|Decimal|Single|Double|Decimal|  
|`Single`|Single|Single|Double|Single|  
|`Double`|Double|Double|Double|Double|  
|Jeden ganzzahligen Typ|Decimal|Single|Double|Double|  
  
 Die `^` Operator definiert ist, nur für die `Double` -Datentyp. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]erweitert jeden Operand nach Bedarf `Double` vor dem Vorgang, und der resultierende Datentyp ist immer `Double`.  
  
## <a name="integer-arithmetic"></a>Ganzzahlarithmetik  
 Der Ergebnisdatentyp einer Operation ganze Zahl hängt von den Datentypen der Operanden ab. Im allgemeinen [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] die folgenden Richtlinien zur Bestimmung der Datentyp des Ergebnisses verwendet:  
  
-   Wenn beide Operanden des binären Operators denselben Datentyp, das Ergebnis hat diesen Datentyp. Eine Ausnahme ist `Boolean`, gezwungen, `Short`.  
  
-   Wenn ein Operand ohne Vorzeichen mit einem signierten-Operanden beteiligt ist, hat das Ergebnis ein Datentyp mit Vorzeichen mindestens genauso groß wie einer der Operanden.  
  
-   Andernfalls hat das Ergebnis normalerweise den größeren der beiden Operandendatentypen.  
  
 Beachten Sie, dass der Ergebnisdatentyp möglicherweise nicht mit dem entweder der Operanddatentyp identisch.  
  
> [!NOTE]
>  Der Ergebnisdatentyp ist nicht immer groß genug für alle möglichen Ergebniswerte aus dem Vorgang. Ein <xref:System.OverflowException>Ausnahme kann auftreten, wenn der Wert für den Ergebnisdatentyp zu groß ist.</xref:System.OverflowException>  
  
### <a name="unary--and--operators"></a>Unär + und -Operatoren  
 Die folgende Tabelle zeigt das Ergebnis für die zwei unäre Operatoren, `+` und `–`.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|Unäre`+`|Short|SByte|Byte|Short|UShort|Ganze Zahl|UInteger|Long|ULong|  
|Unäre`–`|Short|SByte|Short|Short|Ganze Zahl|Ganze Zahl|Long|Long|Decimal|  
  
### <a name="-and--operators"></a><\<und >> Operatoren  
 Die folgende Tabelle zeigt das Ergebnis für die beiden Bitschiebeoperatoren `<<` und `>>`. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]behandelt jedes Bit Shift-Operator als unärer Operator auf der linke Operand (das Bitmuster verschoben werden).  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`<<`, `>>`|Short|SByte|Byte|Short|UShort|Ganze Zahl|UInteger|Long|ULong|  
  
 Wenn der linke Operand ist `Decimal`, `Single`, `Double`, oder `String`, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] umzuwandeln versucht `Long` vor dem Vorgang, und der resultierende Datentyp ist `Long`. Der Rechte Operand (die Anzahl der Bitpositionen) muss `Integer` oder ein Typ, der erweitert `Integer`.  
  
### <a name="binary----and-mod-operators"></a>Binär +, -, *, und Mod-Operator  
 Die folgende Tabelle zeigt das Ergebnis der binären `+` und `–` Operatoren und `*` und `Mod` Operatoren. Beachten Sie, dass diese Tabelle symmetrisch ist. für jede dieser Kombinationen von Operandentypen Daten ist der Datentyp des Ergebnisses unabhängig von der Reihenfolge der Operanden.  
  
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
 Die folgende Tabelle zeigt das Ergebnis von Datentypen für die `\` Operator. Beachten Sie, dass diese Tabelle symmetrisch ist. für jede dieser Kombinationen von Operandentypen Daten ist der Datentyp des Ergebnisses unabhängig von der Reihenfolge der Operanden.  
  
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
  
 Wenn ein Operand den `\` Operator ist [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md), [einzelne](../../../visual-basic/language-reference/data-types/single-data-type.md), oder [doppelte](../../../visual-basic/language-reference/data-types/double-data-type.md), [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] versucht, ihn zu konvertieren [lang](../../../visual-basic/language-reference/data-types/long-data-type.md) vor dem Vorgang, und der resultierende Datentyp ist `Long`.  
  
## <a name="relational-and-bitwise-comparisons"></a>Relationale und bitweise Vergleiche  
 Der Ergebnisdatentyp einer relationalen Operation (`=`, `<>`, `<`, `>`, `<=`, `>=`) ist immer `Boolean` [Boolean-Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md). Dasselbe gilt für logische Operationen (`And`, `AndAlso`, `Not`, `Or`, `OrElse`, `Xor`) auf `Boolean` Operanden.  
  
 Der Ergebnisdatentyp eine bitweise logische Operation hängt von den Datentypen der Operanden ab. Beachten Sie, dass `AndAlso` und `OrElse` sind nur für definiert `Boolean`, und [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] konvertiert jeden Operanden nach Bedarf `Boolean` vor dem Ausführen des Vorgangs.  
  
### <a name="-----and--operators"></a>=, <>, \<, >, \<=, and >= Operators  
 Wenn beide Operanden `Boolean`, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] berücksichtigt `True` zu weniger als `False`. Wenn mit ein numerischer Typ verglichen wird ein `String`, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] versucht, konvertieren die `String` an `Double` vor dem Vorgang. Ein `Char` oder `Date` Operand kann nur mit einem anderen Operanden des gleichen Datentyps verglichen werden. Der resultierende Datentyp ist immer `Boolean`.  
  
### <a name="bitwise-not-operator"></a>Bitweise Not-Operator  
 In der folgenden Tabelle werden die Ergebnisdatentypen für den bitweisen `Not` Operator.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Not`|Boolesch|SByte|Byte|Short|UShort|Ganze Zahl|UInteger|Long|ULong|  
  
 Wenn der Operand `Decimal`, `Single`, `Double`, oder `String`, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] umzuwandeln versucht `Long` vor dem Vorgang, und der resultierende Datentyp ist `Long`.  
  
### <a name="bitwise-and-or-and-xor-operators"></a>Bitweises und, oder, und Xor-Operatoren  
 In der folgenden Tabelle werden die Ergebnisdatentypen für den bitweisen `And`, `Or`, und `Xor` Operatoren. Beachten Sie, dass diese Tabelle symmetrisch ist. für jede dieser Kombinationen von Operandentypen Daten ist der Datentyp des Ergebnisses unabhängig von der Reihenfolge der Operanden.  
  
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
  
 Wenn ein Operand `Decimal`, `Single`, `Double`, oder `String`, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] umzuwandeln versucht `Long` vor dem Vorgang, und die Ergebnisdaten Typ stimmt überein, als wäre dieser Operand bereits `Long`.  
  
## <a name="miscellaneous-operators"></a>Verschiedene Operatoren  
 Die `&` Operator ist nur für die Verkettung von definiert `String` Operanden. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Jeder Operand nach Bedarf konvertiert `String` vor dem Vorgang, und der resultierende Datentyp ist immer `String`. Im Rahmen der `&` Operator, alle Konvertierungen, `String` gelten als erweiternde werden, selbst wenn `Option Strict` ist `On`.  
  
 Die `Is` und `IsNot` Operatoren müssen beide Operanden ein Verweistyp sein. The `TypeOf`... `Is` -Ausdruck muss der erste Operand zu einem Verweistyp sein und der zweite Operand den Namen eines Datentyps enthalten. In diesen Fällen die Ergebnisdaten ist `Boolean`.  
  
 Die `Like` Operator wird nur für einen Mustervergleich definiert `String` Operanden. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]versucht, jeden Operanden nach Bedarf konvertieren `String` vor dem Vorgang. Der resultierende Datentyp ist immer `Boolean`.  
  
## <a name="see-also"></a>Siehe auch  
 [Datentypen](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Operatoren und Ausdrücke](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)   
 [Arithmetische Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)   
 [Vergleichsoperatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)   
 [Operatoren](../../../visual-basic/language-reference/operators/index.md)   
 [Operatorrangfolge in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operatoren sortiert nach Funktionalität](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Arithmetische Operatoren](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Vergleichsoperatoren](../../../visual-basic/language-reference/operators/comparison-operators.md)   
 [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md)
