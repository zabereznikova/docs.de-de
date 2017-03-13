---
title: "&lt;&lt;= Operator (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.<<="
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "operator <<="
  - "assignment statements, compound"
  - "<<= operator [Visual Basic]"
  - "statements [Visual Basic], compound assignment"
  - "operator<<="
  - "compound assignment statements"
ms.assetid: 8ad26613-faff-4e2f-89ee-63feee33bfda
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# &lt;&lt;= Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Führt eine arithmetische Verschiebung nach links für den Wert einer Variablen oder Eigenschaft aus und weist das Ergebnis wieder der Variablen oder Eigenschaft zu.  
  
## Syntax  
  
```  
  
variableorproperty <<= amount  
```  
  
## Teile  
 `variableorproperty`  
 Erforderlich.  Variable oder Eigenschaft eines ganzzahligen Typs \(`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long` oder `ULong`\).  
  
 `amount`  
 Erforderlich.  Numerischer Ausdruck mit einem Datentyp, der zu `Integer` erweitert wird.  
  
## Hinweise  
 Das Element auf der linken Seite des Operators `<<=` kann eine einfache Skalarvariable, eine Eigenschaft oder ein Element eines Arrays sein.  Die Variable oder die Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)sein.  
  
 Der `<<=` Operator führt zuerst eine arithmetische Verschiebung nach links für den Wert der Variablen oder Eigenschaft aus.  Der Operator weist dann das Ergebnis dieses Vorgangs wieder an dieser Variablen oder Eigenschaft zu.  
  
 Arithmetische Verschiebungen sind nicht zyklisch, d. h., die Bits, die an einem Ende des Ergebnisses durch die Verschiebung herausfallen, werden nicht am anderen Ende wieder eingefügt.  In einer arithmetischen Verschiebung nach links werden die Bits, die über den Bereich des Ergebnisdatentyps hinaus verschoben werden, verworfen, und die Bitpositionen, die auf der rechten Seite frei werden, werden auf 0 \(null\) gesetzt.  
  
## Überladen  
 Der [\<\< Operator](../../../visual-basic/language-reference/operators/left-shift-operator.md) kann *überladen* werden. Das bedeutet, dass eine Klasse oder Struktur sein Verhalten neu definiert, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.  Das Überladen des Operators `<<` hat Auswirkungen auf das Verhalten des Operators `<<=`.  Wenn im Code `<<=` auf eine Klasse oder Struktur angewendet wird, die `<<` überlädt, sollten Sie auf jeden Fall sein neu definiertes Verhalten verstehen.  Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Beispiel  
 Im folgenden Beispiel wird der Operator `<<=` verwendet, um das Bitmuster einer `Integer`\-Variablen um den angegebenen Betrag nach links zu verschieben und der Variablen das Ergebnis zuzuweisen.  
  
 [!code-vb[VbVbalrOperators#13](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/left-shift-assignment-operator_1.vb)]  
  
## Siehe auch  
 [\<\< Operator](../../../visual-basic/language-reference/operators/left-shift-operator.md)   
 [Assignment Operators](../../../visual-basic/language-reference/operators/assignment-operators.md)   
 [Bit Shift Operators](../../../visual-basic/language-reference/operators/bit-shift-operators.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Statements](../../../visual-basic/programming-guide/language-features/statements.md)