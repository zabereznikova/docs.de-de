---
title: "- Operator (Visual Basic) | Microsoft Docs"
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
  - "vb.Negate"
  - "vb.-"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "- operator [Visual Basic]"
  - "operators [Visual Basic], subtraction"
  - "operators [Visual Basic], difference"
  - "negation operator"
  - "operators [Visual Basic], arithmetic"
  - "subtraction operator, syntax"
  - "arithmetic operators, subtraction"
  - "difference operator"
  - "math operators"
  - "operators [Visual Basic], negation"
  - "minus operator [Visual Basic]"
ms.assetid: bff2c368-662d-4c92-ac87-1d9bdfd3426a
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# - Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Gibt die Differenz zwischen zwei numerischen Ausdrücken oder den negativen Wert eines numerischen Ausdrucks zurück.  
  
## Syntax  
  
```  
  
      expression1 – expression2  
- or -  
– expression1  
```  
  
## Teile  
 `expression1`  
 Erforderlich.  Ein beliebiger numerischer Ausdruck.  
  
 `expression2`  
 Erforderlich, es sei denn, der Operator `–` berechnet einen negativen Wert.  Ein beliebiger numerischer Ausdruck.  
  
## Ergebnis  
 Das Ergebnis ist die Differenz zwischen `expression1` und `expression2` oder der negativierte Wert von `expression1`.  
  
 Der Ergebnisdatentyp ist ein numerischer Typ, der sich für die Datentypen von `expression1` und `expression2` eignet.  Siehe die "Ganzzahlarithmetik"\-Tabellen in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
## Unterstützte Typen  
 Alle numerischen Typen.  Dies schließt die Typen ohne Vorzeichen, Gleitkommatypen und `Decimal` ein.  
  
## Hinweise  
 Im ersten Anwendungsbeispiel in der vorhergehenden Syntax ist der Operator `–` der *binäre* arithmetische Subtraktionsoperator für die Differenz zwischen zwei numerischen Ausdrücken.  
  
 Im zweiten Anwendungsbeispiel in der obenstehenden Syntax ist der Operator `–` der *unäre* Negationsoperator für den negativen Wert eines Ausdrucks.  Negation ist also nichts anderes als die Umkehrung des Vorzeichens von `expression1`, wodurch das Ergebnis positiv wird, wenn `expression1` ein negativer Wert ist.  
  
 Wenn einer der beiden Ausdrücke [Nothing](../../../visual-basic/language-reference/nothing.md) ergibt, behandelt der Operator `–` den Ausdruck als 0 \(null\).  
  
> [!NOTE]
>  Der Operator `–` kann *überladen* werden. Das bedeutet, dass eine Klasse oder Struktur sein Verhalten neu definiert, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.  Wenn Sie diesen Operator im Code auf eine solche Klasse oder Struktur anwenden, sollten Sie auf jeden Fall dessen neu definiertes Verhalten kennen.  Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Beispiel  
 Im folgenden Beispiel wird der Operator `–` verwendet, um die Differenz zwischen zwei Zahlen zu berechnen und zurückzugeben und anschließend eine Zahl zu negieren.  
  
 [!code-vb[VbVbalrOperators#10](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/subtraction-operator_1.vb)]  
  
 Nach der Ausführung dieser Anweisungen enthält `binaryResult` den Wert 124,45, und `unaryResult` enthält \-334,90.  
  
## Siehe auch  
 [\-\= Operator](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)   
 [Arithmetic Operators](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Arithmetic Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)