---
title: "How to: Match a String against a Pattern (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "comparison operators, comparing strings"
  - "pattern matching"
  - "strings [Visual Basic], comparing"
  - "string comparison [Visual Basic], operators"
  - "Visual Basic code, operators"
  - "pattern matching, string comparison"
  - "string comparison [Visual Basic]"
  - "Like operator [Visual Basic], pattern matching"
  - "pattern matching, empty strings"
  - "operators [Visual Basic], comparison"
ms.assetid: 19a83804-b5af-4739-928b-ac93e64e457f
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# How to: Match a String against a Pattern (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Wenn Sie ermitteln möchten, ob ein Ausdruck vom [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md) einem Muster entspricht, können Sie den [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md) verwenden.  
  
 `Like` akzeptiert zwei Operanden.  Der linke Operand ist ein Zeichenfolgenausdruck, und der rechte Operand ist eine Zeichenfolge, die das für den Vergleich zu verwendende Muster enthält.  `Like` gibt einen `Boolean`\-Wert zurück, der angibt, ob der Zeichenfolgenausdruck dem Muster entspricht.  
  
 Sie können jedes Zeichen in dem Zeichenfolgenausdruck mit einem bestimmten Zeichen, einem Platzhalterzeichen, einer Zeichenliste oder einem Bereich von Zeichen vergleichen.  Die Positionen der Angaben in der Musterzeichenfolge entsprechen den Positionen der Zeichen, die im Zeichenfolgenausdruck verglichen werden sollen.  
  
### So vergleichen Sie ein Zeichen im Zeichenfolgenausdruck mit einem bestimmten Zeichen  
  
-   Fügen Sie das spezielle Zeichen direkt in die Musterzeichenfolge ein.  Bestimmte Sonderzeichen müssen in eckige Klammern \(`[ ]`\) eingeschlossen werden.  Weitere Informationen finden Sie unter [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md).  
  
     Im folgenden Beispiel wird überprüft, ob `myString` genau aus dem einzelnen Zeichen `H` besteht.  
  
     [!code-vb[VbVbalrOperators#70](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/how-to-match-a-string-ag_1.vb)]  
  
### So vergleichen Sie ein Zeichen im Zeichenfolgenausdruck mit einem Platzhalterzeichen  
  
-   Fügen Sie in die Musterzeichenfolge ein Fragezeichen \(`?`\) ein.  Jedes gültiges Zeichen an dieser Position führt zu einer Übereinstimmung.  
  
     Im folgenden Beispiel wird überprüft, ob `myString` aus dem einzelnen Zeichen `W` gefolgt von zwei beliebigen Zeichen besteht.  
  
     [!code-vb[VbVbalrOperators#71](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/how-to-match-a-string-ag_2.vb)]  
  
### So vergleichen Sie ein Zeichen im Zeichenfolgenausdruck mit einer Liste von Zeichen  
  
-   Fügen Sie in die Musterzeichenfolge eckige Klammern \(`[ ]`\) ein, und fügen Sie innerhalb der Klammern die Liste der Zeichen ein.  Trennen Sie die Zeichen weder mit Komma noch einem anderen Trennzeichen.  Jedes einzelne Zeichen in der Liste führt zu einer Übereinstimmung.  
  
     Im folgenden Beispiel wird überprüft, ob `myString` aus einem beliebigen gültigen Zeichen gefolgt von einem der Zeichen `A`, `C` oder `E` besteht.  
  
     [!code-vb[VbVbalrOperators#72](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/how-to-match-a-string-ag_3.vb)]  
  
     Beachten Sie, dass bei diesem Vergleich die Groß\-\/Kleinschreibung beachtet werden muss.  
  
### So vergleichen Sie ein Zeichen im Zeichenfolgenausdruck mit einem Bereich von Zeichen  
  
-   Fügen Sie in die Musterzeichenfolge eckige Klammern \(`[ ]`\) ein, und fügen Sie innerhalb der Klammern das erste und letzte Zeichen im Bereich ein, getrennt durch einen Bindestrich \(`–`\).  Jedes einzelne Zeichen im Bereich ergibt eine Übereinstimmung.  
  
     Im folgenden Beispiel wird überprüft, ob `myString` aus den Zeichen vom Typ `num` gefolgt von genau einem der Zeichen `i`, `j`, `k`, `l`, `m` oder `n` besteht.  
  
     [!code-vb[VbVbalrOperators#73](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/how-to-match-a-string-ag_4.vb)]  
  
     Beachten Sie, dass bei diesem Vergleich die Groß\-\/Kleinschreibung beachtet werden muss.  
  
## Vergleichen leerer Zeichenfolgen  
 `Like` behandelt die Sequenz `[]` als Zeichenfolge der Länge 0 \(null\) \(`""`\).  Mit `[]` können Sie überprüfen, ob der gesamte Zeichenfolgenausdruck leer ist, doch Sie können damit nicht überprüfen, ob eine bestimmte Position im Zeichenfolgenausdruck leer ist.  Wenn Sie u. a. überprüfen müssen, ob eine leere Position vorhanden ist, können Sie `Like` mehrmals verwenden.  
  
#### So vergleichen Sie ein Zeichen im Zeichenfolgenausdruck mit einer Liste von Zeichen oder keinem Zeichen  
  
1.  Rufen Sie den Operator `Like` für denselben Zeichenfolgenausdruck zweimal auf, und verknüpfen Sie die beiden Aufrufe entweder mit dem [Or Operator](../../../../visual-basic/language-reference/operators/or-operator.md) oder dem [OrElse Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md).  
  
2.  Fügen Sie in der Musterzeichenfolge für die erste `Like`\-Klausel die Zeichenfolgenliste in eckigen Klammern \(`[ ]`\) ein.  
  
3.  Fügen Sie in der Musterzeichenfolge für die zweite `Like`\-Klausel an der betreffenden Position kein Zeichen ein.  
  
     Im folgenden Beispiel wird überprüft, ob die siebenstellige Telefonnummer `phoneNum` aus genau drei Ziffern, gefolgt von einem Leerzeichen, einem Bindestrich \(`–`\), einem Punkt \(`.`\) oder keinem Zeichen und genau vier numerischen Ziffern besteht.  
  
     [!code-vb[VbVbalrOperators#74](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/how-to-match-a-string-ag_5.vb)]  
  
## Siehe auch  
 [Comparison Operators](../../../../visual-basic/language-reference/operators/comparison-operators.md)   
 [Operators and Expressions](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)   
 [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md)   
 [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md)