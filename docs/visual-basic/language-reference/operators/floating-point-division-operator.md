---
title: "/ Operator (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb./"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "division operator, floating point"
  - "floating-point numbers, division operator"
  - "slash (/) operator"
  - "zero, division by zero"
  - "operators [Visual Basic], arithmetic"
  - "arithmetic operators, division"
  - "division, by zero"
  - "operators [Visual Basic], division"
  - "division operator, syntax"
  - "/ operator [Visual Basic]"
  - "math operators"
ms.assetid: 335e97f2-c434-439e-9064-76973a051101
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# / Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Dividiert zwei Zahlen und gibt ein Gleitkommaergebnis zurück.  
  
## Syntax  
  
```  
  
expression1 / expression2  
```  
  
## Teile  
 `expression1`  
 Erforderlich.  Ein beliebiger numerischer Ausdruck.  
  
 `expression2`  
 Erforderlich.  Ein beliebiger numerischer Ausdruck.  
  
## Unterstützte Typen  
 Alle numerischen Typen, einschließlich Typen ohne Vorzeichen, Gleitkommatypen sowie `Decimal`.  
  
## Ergebnis  
 Das Ergebnis ist der volle Quotient von `expression1` geteilt durch `expression2` einschließlich eines Rests.  
  
 Der [\\ Operator](../../../visual-basic/language-reference/operators/integer-division-operator.md) gibt den ganzzahligen Quotienten zurück, wobei der Rest entfällt.  
  
## Hinweise  
 Der Datentyp des Ergebnisses hängt von den Typen der Operanden ab.  Die folgende Tabelle zeigt, wie der Datentyp des Ergebnisses bestimmt wird.  
  
|Operandendatentypen|Ergebnisdatentyp|  
|-------------------------|----------------------|  
|Beide Ausdrücke sind ganzzahlige Datentypen \([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)\).|`Double`|  
|Ein Ausdruck ist ein [Single](../../../visual-basic/language-reference/data-types/single-data-type.md)\-Datentyp, während der andere kein [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)\-Datentyp ist.|`Single`|  
|Ein Ausdruck ist ein [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)\-Datentyp, während der andere kein [Single](../../../visual-basic/language-reference/data-types/single-data-type.md)\-Datentyp oder [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)\-Datentyp ist.|`Decimal`|  
|Einer der beiden Ausdrücke ist ein [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)\-Datentyp.|`Double`|  
  
 Vor der Division werden alle ganzzahligen numerischen Ausdrücke zu `Double` erweitert.  Wenn Sie das Ergebnis einem ganzzahligen Datentyp zuweisen, versucht Visual Basic, es vom `Double`\-Typ in diesen Typ zu konvertieren.  Dadurch wird unter Umständen eine Ausnahme ausgelöst, wenn das Ergebnis diesem Typ nicht entspricht.  Beachten Sie insbesondere den Abschnitt "Versuchte Division durch 0 \(null\)" auf dieser Hilfeseite.  
  
 Wenn `expression1` oder `expression2` [Nothing](../../../visual-basic/language-reference/nothing.md) ergibt, wird der Ausdruck als 0 \(null\) behandelt.  
  
## Versuchte Division durch 0 \(null\)  
 Wenn `expression2` 0 \(null\) ergibt, verhält sich der Operator `/` bei anderen Operandendatentypen anders.  In der folgenden Tabelle sind die möglichen Verhaltensweisen aufgeführt.  
  
|Operandendatentypen|Verhalten, wenn `expression2` 0 \(null\) ergibt|  
|-------------------------|-----------------------------------------------------|  
|Gleitkomma \(`Single` oder `Double`\)|Gibt Unendlich \(<xref:System.Double.PositiveInfinity> oder <xref:System.Double.NegativeInfinity>\) zurück oder <xref:System.Double.NaN> \(keine Zahl\), wenn `expression1` ebenfalls 0 \(null\) ist.|  
|`Decimal`|Löst <xref:System.DivideByZeroException> aus.|  
|Ganzzahlig \(mit oder ohne Vorzeichen\)|Durch eine versuchte Rückkonvertierung in den Ganzzahltyp wird <xref:System.OverflowException> ausgelöst, da <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity> und <xref:System.Double.NaN> von Ganzzahltypen nicht angenommen werden können.|  
  
> [!NOTE]
>  Der Operator `/` kann *überladen* werden. Das bedeutet, dass eine Klasse oder Struktur sein Verhalten neu definiert, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.  Wenn Sie diesen Operator im Code auf eine solche Klasse oder Struktur anwenden, sollten Sie auf jeden Fall sein neu definiertes Verhalten verstehen.  Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Beispiel  
 In diesem Beispiel wird der Operator `/` für Gleitkommadivisionen verwendet.  Das Ergebnis ist der Quotient der zwei Operanden.  
  
 [!code-vb[VbVbalrOperators#16](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/floating-point-division-_1_1.vb)]  
  
 Die Ausdrücke im vorhergehenden Beispiel geben die Werte 2,5 und 3,333333 zurück.  Das Ergebnis ist stets ein Gleitkommawert \(`Double`\), obwohl beide Operanden ganzzahlige Konstanten sind.  
  
## Siehe auch  
 [\/\= Operator](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)   
 [\\ Operator](../../../visual-basic/language-reference/operators/integer-division-operator.md)   
 [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)   
 [Arithmetic Operators](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Arithmetic Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)