---
title: "How to: Pass Procedures to Another Procedure in Visual Basic | Microsoft Docs"
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
  - "AddressOf operator"
  - "delegates [Visual Basic], passing procedures"
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# How to: Pass Procedures to Another Procedure in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

In diesem Beispiel wird veranschaulicht, wie mithilfe von Delegaten eine Prozedur an eine andere Prozedur übergeben wird.  
  
 Ein Delegat ist ein Typ, den Sie wie jeden anderen Typ in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] verwenden können.  Wenn der Operator `AddressOf` auf einen Prozedurnamen angewendet wird, gibt er ein Delegatobjekt zurück.  
  
 Im vorliegenden Beispiel liegt eine Prozedur mit einem Delegatparameter vor. Dieser kann eine Referenz an eine andere Prozedur enthalten, die mit dem Operator `AddressOf` abgerufen wird.  
  
### Erstellen des Delegaten und entsprechender Prozeduren  
  
1.  Erstellen Sie einen Delegaten mit dem Namen `MathOperator`.  
  
     [!code-vb[VbVbalrDelegates#1](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/how-to-pass-procedures-t_1.vb)]  
  
2.  Erstellen Sie eine Prozedur mit dem Namen `AddNumbers` mit Parametern und einem Rückgabewert. Diese müssen mit denjenigen von `MathOperator` übereinstimmen, da andernfalls unterschiedliche Signaturen vorliegen.  
  
     [!code-vb[VbVbalrDelegates#2](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/how-to-pass-procedures-t_2.vb)]  
  
3.  Erstellen Sie eine Prozedur mit dem Namen `SubtractNumbers` mit einer Signatur, die der von `MathOperator` entspricht.  
  
     [!code-vb[VbVbalrDelegates#3](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/how-to-pass-procedures-t_3.vb)]  
  
4.  Erstellen Sie eine Prozedur mit dem Namen `DelegateTest`, der als Parameter ein Delegat übergeben wird.  
  
     Dieser Prozedur kann ein Verweis auf `AddNumbers` oder `SubtractNumbers` übergeben werden, weil deren Signaturen der Signatur von `MathOperator` entsprechen.  
  
     [!code-vb[VbVbalrDelegates#4](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/how-to-pass-procedures-t_4.vb)]  
  
5.  Erstellen Sie eine Prozedur mit dem Namen `Test`, die `DelegateTest` einmal mit dem Delegaten für `AddNumbers` als Parameter und ein zweites Mal mit dem Delegaten für `SubtractNumbers` als Parameter aufruft.  
  
     [!code-vb[VbVbalrDelegates#5](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/how-to-pass-procedures-t_5.vb)]  
  
     Beim Aufruf von `Test` wird zuerst das Ergebnis von `AddNumbers` angezeigt. Dabei wird die Summe aus `5` und `3` gebildet, also 8.  Anschließend wird das Ergebnis des Vorgangs `SubtractNumbers` angezeigt. Dabei wird die Differenz zwischen `9` und `3` ermittelt, also 6.  
  
## Siehe auch  
 [Delegates](../../../../visual-basic/programming-guide/language-features/delegates/delegates.md)   
 [AddressOf Operator](../../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Delegate Statement](../../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [How to: Invoke a Delegate Method](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)