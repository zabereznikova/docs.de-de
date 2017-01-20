---
title: "Data Types of Operator Results (Visual Basic) | Microsoft Docs"
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
  - "data types [Visual Basic], operator result data types"
  - "result data types"
  - "operator result data types"
  - "operators [Visual Basic], data types"
  - "data types [Visual Basic], ranges"
  - "operators [Visual Basic], result data types"
ms.assetid: 9d524533-e1a1-4aa8-b1b8-622068173d06
caps.latest.revision: 27
caps.handback.revision: 27
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Data Types of Operator Results (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] bestimmt den Ergebnisdatentyp einer Operation anhand der Datentypen der Operanden.  In einigen Fällen kann der Ergebnisdatentyp einen größeren Bereich haben als die Datentypen der beiden Operanden.  
  
## Datentypbereiche  
 Nachfolgend sind die Bereiche der relevanten Datentypen in der Reihenfolge von kleinsten zum größten aufgeführt:  
  
-   [Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md) – zwei mögliche Werte  
  
-   [SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md) – 256 mögliche ganzzahlige Werte  
  
-   [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md) – 65.536 \(6,5... E\+4\) mögliche ganzzahlige Werte  
  
-   [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md) – 4.294.967.296 \(4,2... E\+9\) mögliche ganzzahlige Werte  
  
-   [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md) – 18.446.744.073.709.551.615 \(1,8... E\+19\) mögliche ganzzahlige Werte  
  
-   [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) – 1,5... E\+29 mögliche ganzzahlige Werte, maximaler Bereich 7,9... E\+28 \(absoluter Wert\)  
  
-   [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) – maximaler Bereich 3,4... E\+38 \(absoluter Wert\)  
  
-   [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) – maximaler Bereich 1,7... E\+308 \(absoluter Wert\)  
  
 Weitere Informationen zu den Datentypen von [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] finden Sie unter [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
 Wenn ein Operand [Nothing](../../../visual-basic/language-reference/nothing.md) ergibt, wird er von den arithmetischen Operatoren in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] wie 0 \(null\) behandelt.  
  
## Arithmetische Operationen mit dem Decimal\-Datentyp  
 Beachten Sie, dass der [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)\-Datentyp weder Gleitkommazahlen noch ganze Zahlen darstellt.  
  
 Wenn ein Operand einer `+`\-, `–`\-, `*`\-, `/`\- oder `Mod`\-Operation den `Decimal`\-Datentyp aufweist und der andere Operand nicht den `Single`\-Datentyp oder den `Double`\-Datentyp, dann erweitert [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] den anderen Operanden zum `Decimal`\-Datentyp.  Die Operation wird mit dem `Decimal`\-Datentyp ausgeführt, und der Ergebnisdatentyp ist `Decimal`.  
  
## Gleitkommaarithmetik  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] führt den Großteil der Gleitkommaarithmetik mit dem [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)\-Datentyp aus, der für solche Operationen am effizientesten ist.  Wenn ein Operand jedoch den [Single](../../../visual-basic/language-reference/data-types/single-data-type.md)\-Datentyp und der andere den `Double`\-Datentyp hat, führt [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] die Operation unter Verwendung des `Single`\-Datentyps aus.  Vor der Operation wird jeder Operand nach Bedarf zum geeigneten Datentyp erweitert, und das Ergebnis hat diesen Datentyp.  
  
### Operatoren \/ und ^  
 Der `/`\-Operator wird nur für die Datentypen [Dezimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md), [Einfach](../../../visual-basic/language-reference/data-types/single-data-type.md) und [Doppelt](../../../visual-basic/language-reference/data-types/double-data-type.md) definiert.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] erweitert jeden Operand nach Bedarf zum geeigneten Datentyp, und das Ergebnis hat diesen Datentyp.  
  
 In der folgenden Tabelle werden die Ergebnisdatentypen für den Operator `/` aufgeführt.  Beachten Sie, dass diese Tabelle symmetrisch ist. Der Datentyp des Ergebnisses ist für jede gegebene Kombination von Operandendatentypen der gleiche und zwar unabhängig von der Reihenfolge der Operanden.  
  
||||||  
|-|-|-|-|-|  
||`Decimal`|`Single`|`Double`|Ein beliebiger ganzzahliger Typ|  
|`Decimal`|Decimal|Single|Double|Decimal|  
|`Single`|Single|Single|Double|Single|  
|`Double`|Double|Double|Double|Double|  
|Ein beliebiger ganzzahliger Typ|Decimal|Single|Double|Double|  
  
 Der `^`\-Operator wird nur für den `Double`\-Datentyp definiert.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] erweitert jeden Operand wie nötig zu `Double` vor dem Vorgang, und der resultierende Datentyp ist immer `Double`.  
  
## Ganzzahlarithmetik  
 Der Ergebnisdatentyp einer Ganzzahloperation hängt von den Datentypen der Operanden ab.  Im Allgemeinen wird in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] der Ergebnisdatentyp nach folgenden Richtlinien bestimmt:  
  
-   Wenn beide Operanden eines binären Operators den gleichen Datentyp haben, weist das Ergebnis diesen Datentyp auf.  Eine Ausnahme ist der `Boolean`\-Datentyp, der in `Short` umgewandelt wird.  
  
-   Wenn die Operation einen Operanden ohne Vorzeichen und einen Operanden mit Vorzeichen beinhaltet, ist das Ergebnis ein Datentyp mit Vorzeichen und einem Bereich, der mindestens genauso groß ist wie jeder der beiden Operanden.  
  
-   Andernfalls hat das Ergebnis normalerweise den größeren Datentyp der beiden Operandendatentypen.  
  
 Beachten Sie, dass der Ergebnisdatentyp nicht dem Datentyp eines der beiden Operanden entsprechen muss.  
  
> [!NOTE]
>  Der Ergebnisdatentyp ist nicht immer groß genug, um alle möglichen Ergebniswerte der Operation speichern zu können.  Es kann eine <xref:System.OverflowException>\-Ausnahme auftreten, wenn der Wert für den Ergebnisdatentyp zu groß ist.  
  
### Unäre Operatoren \+ und –  
 Die folgende Tabelle enthält die Ergebnisdatentypen für die beiden unären Operatoren `+` und `–`.  
  
|||||||||||  
|-|-|-|-|-|-|-|-|-|-|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|Unäres `+`|Short|SByte|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
|Unäres `–`|Short|SByte|Short|Short|Integer|Integer|Long|Long|Decimal|  
  
### Operatoren \<\< und \>\>  
 In der folgenden Tabelle sind die Ergebnisdatentypen für die beiden Bitschiebeoperatoren `<<` und `>>` aufgeführt.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] behandelt jeden Bitschiebeoperator als unären Operator für seinen linken Operanden \(das zu verschiebende Bitmuster\).  
  
|||||||||||  
|-|-|-|-|-|-|-|-|-|-|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`<<`, `>>`|Short|SByte|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
  
 Wenn der linke Operand den Datentyp `Decimal`, `Single`, `Double` oder `String` hat, versucht [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], den Datentyp vor der Operation in `Long` umzuwandeln. Das Ergebnis hat den `Long`\-Datentyp.  Der rechte Operand \(die Anzahl der zu verschiebenden Bitpositionen\) muss den `Integer`\-Datentyp oder einen Typ haben, der zu `Integer` erweitert werden kann.  
  
### Binäre Operatoren '\+' und '–', '\*' und 'Mod'  
 In der folgenden Tabelle sind die Ergebnisdatentypen der binären Operatoren `+` und `–` sowie des Operators `*` und des Operators `Mod` aufgeführt.  Beachten Sie, dass diese Tabelle symmetrisch ist. Der Datentyp des Ergebnisses ist für jede gegebene Kombination von Operandendatentypen der gleiche und zwar unabhängig von der Reihenfolge der Operanden.  
  
|||||||||||  
|-|-|-|-|-|-|-|-|-|-|  
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
  
### Operator \\  
 In der folgenden Tabelle werden die Ergebnisdatentypen für den Operator `\` aufgeführt.  Beachten Sie, dass diese Tabelle symmetrisch ist. Der Datentyp des Ergebnisses ist für jede gegebene Kombination von Operandendatentypen der gleiche und zwar unabhängig von der Reihenfolge der Operanden.  
  
|||||||||||  
|-|-|-|-|-|-|-|-|-|-|  
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
  
 Wenn ein Operand des Operators `\` den Datentyp [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md), [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) oder [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) hat, versucht [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] vor der Operation, diesen Datentyp in [Long](../../../visual-basic/language-reference/data-types/long-data-type.md) umzuwandeln. Der Ergebnisdatentyp ist `Long`.  
  
## Relationale und bitweise Vergleiche  
 Der Ergebnisdatentyp einer relationalen Operation \(`=`, `<>`, `<`, `>`, `<=`, `>=`\) ist immer `Boolean`[Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md).  Dasselbe gilt für logische Operationen \(`And`, `AndAlso`, `Not`, `Or`, `OrElse`, `Xor`\) mit Operanden vom `Boolean`\-Datentyp.  
  
 Der Ergebnisdatentyp einer bitweisen logischen Operation hängt von den Datentypen der Operanden ab.  Beachten Sie, dass `AndAlso` und `OrElse` nur für `Boolean` definiert sind. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] konvertiert jeden Operanden bei Bedarf in `Boolean`, bevor die Operation ausgeführt wird.  
  
### Operatoren \=, \<\>, \<, \>, \<\= und \>\=  
 Wenn beide Operanden vom Typ `Boolean` sind, gilt in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] der Wert `True` als kleiner als der Wert `False`.  Wenn ein numerischer Typ mit einem `String` verglichen wird, versucht [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] vor der Operation, den `String`\-Operanden in den `Double`\-Datentyp zu konvertieren.  Ein Operand vom Typ `Char` oder `Date` kann nur mit einem anderen Operanden des gleichen Datentyps verglichen werden.  Das Ergebnis hat immer den `Boolean`\-Datentyp.  
  
### Bitweiser Operator Not  
 In der folgenden Tabelle werden die Ergebnisdatentypen für den bitweisen Operator `Not` aufgeführt.  
  
|||||||||||  
|-|-|-|-|-|-|-|-|-|-|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Not`|Boolean|SByte|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
  
 Wenn der Operand den Datentyp `Decimal`, `Single`, `Double` oder `String` hat, versucht [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], den Datentyp vor der Operation in `Long` umzuwandeln. Das Ergebnis hat den `Long`\-Datentyp.  
  
### Bitweise Operatoren And, Or und Xor  
 In der folgenden Tabelle werden die Ergebnisdatentypen für die bitweisen Operatoren `And`, `Or` und `Xor` aufgeführt.  Beachten Sie, dass diese Tabelle symmetrisch ist. Der Datentyp des Ergebnisses ist für jede gegebene Kombination von Operandendatentypen der gleiche und zwar unabhängig von der Reihenfolge der Operanden.  
  
|||||||||||  
|-|-|-|-|-|-|-|-|-|-|  
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
  
 Wenn ein Operand den Datentyp `Decimal`, `Single`, `Double` oder `String` hat, versucht [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], den Datentyp vor der Operation in `Long` umzuwandeln. Das Ergebnis hat den Datentyp, der sich ergäbe, wenn der Operand bereits den `Long`\-Datentyp gehabt hätte.  
  
## Verschiedene Operatoren  
 Der `&`\-Operator wird nur für die Verkettung von `String`\-Operanden definiert.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] konvertiert jeden Operand wie nötig zu `String` vor dem Vorgang, und der resultierende Datentyp ist immer `String`.  Alle im Zusammenhang mit dem Operator `&` durchgeführten Konvertierungen in den `String`\-Datentyp werden als erweiternde Konvertierungen betrachtet, auch wenn `Option Strict` den Wert `On` hat.  
  
 Beim Operator `Is` und beim Operator `IsNot` müssen beide Operanden zum gleichen Verweistyp gehören.  Beim `TypeOf`...`Is`\-Ausdruck muss der erste Operand zu einem Verweistyp gehören und der zweite Operand den Namen eines Datentyps enthalten.  In allen diesen Fällen ist der Ergebnisdatentyp `Boolean`.  
  
 Der `Like`\-Operator wird nur für den Mustervergleich von `String`\-Operanden definiert.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] versucht, vor dem Vorgang jeden Operanden nach Bedarf in `String` zu konvertieren.  Das Ergebnis hat immer den `Boolean`\-Datentyp.  
  
## Siehe auch  
 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Operators and Expressions](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)   
 [Arithmetic Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)   
 [Comparison Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)   
 [Operators](../../../visual-basic/language-reference/operators/index.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Arithmetic Operators](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Comparison Operators](../../../visual-basic/language-reference/operators/comparison-operators.md)   
 [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)