---
title: "* Operator (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.*"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "arithmetic operators, multiplication"
  - "operators [Visual Basic], multiplication"
  - "* operator [Visual Basic]"
  - "multiplication operator, syntax"
  - "math operators"
ms.assetid: 2b210382-99da-4195-89ba-b1d06f5e89ad
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# * Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Multipliziert zwei Zahlen miteinander.  
  
## Syntax  
  
```  
  
number1 * number2  
```  
  
## Teile  
  
|||  
|-|-|  
|Begriff|Definition|  
|`number1`|Erforderlich.  Ein beliebiger numerischer Ausdruck.|  
|`number2`|Erforderlich.  Ein beliebiger numerischer Ausdruck.|  
  
## Ergebnis  
 Das Ergebnis ist das Produkt von `number1` und `number2`.  
  
## Unterstützte Typen  
 Alle numerischen Typen, einschließlich Typen ohne Vorzeichen, Gleitkommatypen sowie `Decimal`.  
  
## Hinweise  
 Der Datentyp des Ergebnisses hängt von den Typen der Operanden ab.  Die folgende Tabelle zeigt, wie der Datentyp des Ergebnisses bestimmt wird.  
  
|||  
|-|-|  
|Operandendatentypen|Ergebnisdatentyp|  
|Beide Ausdrücke sind ganzzahlige Datentypen \([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)\).|Ein numerischer Datentyp, der sich für die Datentypen `number1` und `number2` eignet.  Siehe die "Ganzzahlarithmetik"\-Tabellen in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).|  
|Beide Ausdrücke sind [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md).|`Decimal`|  
|Beide Ausdrücke sind [Single](../../../visual-basic/language-reference/data-types/single-data-type.md).|`Single`|  
|Beide Ausdrücke sind Gleitkomma\-Datentypen \(`Single` oder [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)\), sie sind jedoch nicht beide `Single`. \(Beachten Sie, dass `Decimal` keinen Gleitkomma\-Datentyp darstellt.\)|`Double`|  
  
 Wenn ein Ausdruck [Nothing](../../../visual-basic/language-reference/nothing.md) ergibt, wird er wie 0 behandelt.  
  
## Überladen  
 Der Operator `*` kann *überladen* werden. Das bedeutet, dass eine Klasse oder Struktur sein Verhalten neu definiert, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.  Wenn Sie diesen Operator im Code auf eine solche Klasse oder Struktur anwenden, sollten Sie auf jeden Fall sein neu definiertes Verhalten verstehen.  Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Beispiel  
 In diesem Beispiel werden mit dem Operator `*` zwei Zahlen multipliziert.  Das Ergebnis ist das Produkt der zwei Operanden.  
  
 [!code-vb[VbVbalrOperators#4](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/multiplication-operator_1.vb)]  
  
## Siehe auch  
 [\*\= Operator](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)   
 [Arithmetic Operators](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Arithmetic Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)