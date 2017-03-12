---
title: "Is Operator (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.is"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "comparison operators"
  - "equivalent objects"
  - "TypeOf...Is expression"
  - "Is operator [Visual Basic]"
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# Is Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Vergleicht zwei Objektverweisvariablen.  
  
## Syntax  
  
```  
  
result = object1 Is object2  
```  
  
## Teile  
 `result`  
 Erforderlich.  Beliebiger `Boolean`\-Wert.  
  
 `object1`  
 Erforderlich.  Beliebiger `Object`\-Name.  
  
 `object2`  
 Erforderlich.  Beliebiger `Object`\-Name.  
  
## Hinweise  
 Der Operator `Is` ermittelt, ob zwei Objektverweise auf dasselbe Objekt verweisen.  Jedoch werden keine Wertvergleiche ausgeführt.  Wenn sowohl `object1` als auch `object2` auf dieselbe Objektinstanz verweisen, dann ist `result` gleich `True`; verweisen sie nicht auf dieselbe Objektinstanz, dann ist `result` gleich `False`.  
  
 `Is` kann auch mit dem `TypeOf`\-Schlüsselwort zur Bildung eines `TypeOf`...`Is`\-Ausdrucks verwendet werden. Dieser prüft, ob eine Objektvariable mit einem Datentyp kompatibel ist.  
  
> [!NOTE]
>  Das `Is`\-Schlüsselwort wird auch in der [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md) verwendet.  
  
## Beispiel  
 Im folgenden Beispiel wird der Operator `Is` verwendet, um Paare von Objektverweisen zu vergleichen.  Die Ergebnisse werden einem `Boolean`\-Wert zugewiesen, der darstellt, ob die beiden Objekte identisch sind.  
  
 [!code-vb[VbVbalrOperators#27](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/is-operator_1.vb)]  
  
 Wie im vorangehenden Beispiel veranschaulicht wird, können Sie den Operator `Is` verwenden, um sowohl früh gebundene, als auch spät gebundene Objekte zu testen.  
  
## Siehe auch  
 [TypeOf Operator](../../../visual-basic/language-reference/operators/typeof-operator.md)   
 [IsNot Operator](../../../visual-basic/language-reference/operators/isnot-operator.md)   
 [Comparison Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Operators and Expressions](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)