---
title: "^ Operator (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.^"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "raising numbers to powers"
  - "^ operator [Visual Basic], exponention"
  - "square operator"
  - "^ operator [Visual Basic]"
  - "exponentiation operator [Visual Basic]"
  - "exponent"
  - "numbers, rasing"
  - "powers"
  - "arithmetic operators, exponentiation"
ms.assetid: d89a1ca8-83da-4784-a87b-a9d7dceb3f62
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# ^ Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Erhebt eine Zahl zur Potenz einer anderen Zahl.  
  
## Syntax  
  
```  
  
number ^ exponent  
```  
  
## Teile  
 `number`  
 Erforderlich.  Ein beliebiger numerischer Ausdruck.  
  
 `exponent`  
 Erforderlich.  Ein beliebiger numerischer Ausdruck.  
  
## Ergebnis  
 Das Ergebnis ist `number` hoch `exponent`. Hierbei wird immer ein `Double`\-Wert verwendet.  
  
## Unterstützte Typen  
 `Double`.  Operanden eines anderen Typs werden in `Double` konvertiert.  
  
## Hinweise  
 Visual Basic führt eine Potenzierung immer mit dem [Double Data Type](../../../visual-basic/language-reference/data-types/double-data-type.md) aus.  
  
 Der Wert von `exponent` kann eine Nachkommastelle, ein negativer Wert oder beides sein.  
  
 Wenn mehrere Potenzierungen in einem einzigen Ausdruck durchgeführt werden, werden die Operatoren `^` nacheinander von links nach rechts ausgewertet.  
  
> [!NOTE]
>  Der Operator `^` kann *überladen* werden. Das bedeutet, dass eine Klasse oder Struktur sein Verhalten neu definiert, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.  Wenn Sie diesen Operator im Code auf eine solche Klasse oder Struktur anwenden, sollten Sie auf jeden Fall sein neu definiertes Verhalten verstehen.  Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Beispiel  
 Im folgenden Beispiel wird der Operator `^` verwendet, um eine Zahl zur Potenz eines Exponenten zu erheben.  Das Ergebnis ist der erste Operand, mit dem der zweite potenziert wird.  
  
 [!code-vb[VbVbalrOperators#20](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/exponentiation-operator_1.vb)]  
  
 Das vorhergehende Beispiel erzeugt folgende Ergebnisse:  
  
 `exp1` wird auf 4 festgelegt \(2 zum Quadrat\).  
  
 `exp2` wird auf 19683 festgelegt \(3 hoch 3, daraus resultierendes Ergebnis hoch 3\).  
  
 `exp3` wird auf \-125 festgelegt \(\-5 hoch 3\).  
  
 `exp4` wird auf 625 festgelegt \(\-5 hoch 4\).  
  
 `exp5` wird auf 2 festgelegt \(Kubikwurzel aus 8\).  
  
 `exp6` wird auf 0,5 festgelegt \(1,0 dividiert durch die Kubikwurzel aus 8\).  
  
 Beachten Sie die Bedeutung der runden Klammern in den Ausdrücken des vorhergehenden Beispiels.  Aufgrund der *Operatorrangfolge* führt Visual Basic normalerweise den Operator `^` vor allen anderen, auch dem unären Operator `–`, aus.  Wenn `exp4` und `exp6` ohne Klammern berechnet worden wären, hätte dies Folgendes ergeben:  
  
 `exp4 = -5 ^ 4` würde z. B. – \(5\) vierten Potenz berechnet, die \-625 führen würde.  
  
 `exp6 = 8 ^ -1.0 / 3.0` würde als \(8 hoch \-1 oder 0,125\) dividiert durch 3,0 berechnet werden, was 0,041666666666666666666666666666667 ergeben würde.  
  
## Siehe auch  
 [^\= Operator](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)   
 [Arithmetic Operators](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Arithmetic Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)