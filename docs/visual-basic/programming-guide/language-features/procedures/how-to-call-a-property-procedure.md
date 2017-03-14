---
title: "How to: Call a Property Procedure (Visual Basic) | Microsoft Docs"
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
  - "Visual Basic code, procedures"
  - "Visual Basic code, properties"
  - "procedures, calling"
  - "properties [Visual Basic], property procedures"
  - "procedure calls, property procedures"
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# How to: Call a Property Procedure (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Eine Eigenschaftenprozedur wird aufgerufen, wenn Sie in der Eigenschaft einen Wert speichern oder deren Wert abrufen.  Auf Eigenschaften wird auf die gleiche Weise zugegriffen wie auf Variablen.  
  
 Mit der `Set`\-Prozedur der Eigenschaft wird ein Wert gespeichert, und mit der `Get`\-Prozedur der Eigenschaft wird ihr Wert abgerufen.  Sie rufen diese Prozeduren jedoch nicht explizit über ihren Namen auf.  Sie verwenden stattdessen die Eigenschaft in einer Zuweisungsanweisung oder einem Ausdruck wie beim Speichern oder Abrufen eines Variablenwerts.  [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] ruft die Prozeduren der Eigenschaft auf.  
  
### So rufen Sie die Get\-Prozedur einer Eigenschaft auf  
  
1.  Verwenden Sie den Eigenschaftennamen in einem Ausdruck auf die gleiche Weise, wie Sie einen Variablennamen verwenden würden.  Sie können eine Eigenschaft überall dort verwenden, wo Sie eine Variable oder eine Konstante verwenden können.  
  
     \- oder \-  
  
     Fügen Sie den Eigenschaftennamen hinter dem Gleichheitszeichen \(`=`\) in einer Zuweisungsanweisung ein.  
  
     Im folgenden Beispiel wird der Wert der <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>\-Eigenschaft gelesen, und die zugehörige `Get`\-Prozedur wird implizit aufgerufen.  
  
     [!code-vb[VbVbalrDateProperties#4](./codesnippet/VisualBasic/how-to-call-a-property-procedure_1.vb)]  
  
2.  Wenn die Eigenschaft Argumente annimmt, fügen Sie nach dem Eigenschaftennamen runde Klammern ein, die die Argumentliste einschließen.  Wenn keine Argumente vorliegen, können Sie die Klammern auch weglassen.  
  
3.  Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern, und trennen Sie die Argumente durch Kommas.  Geben Sie die Argumente unbedingt in genau der Reihenfolge an, in der die Eigenschaft die entsprechenden Parameter definiert.  
  
 Der Wert der Eigenschaft hat im Ausdruck die gleiche Funktion wie eine Variable oder Konstante. Andernfalls wird er in der Variablen oder Eigenschaft auf der linken Seite der Zuweisungsanweisung gespeichert.  
  
### So rufen Sie die Set\-Prozedur einer Eigenschaft auf  
  
1.  Verwenden Sie den Namen der Eigenschaft auf der linken Seite einer Zuweisungsanweisung.  
  
     Im folgenden Beispiel wird der Wert der <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>\-Eigenschaft festgelegt, wobei die `Set`\-Prozedur implizit aufgerufen wird.  
  
     [!code-vb[VbVbcnProcedures#11](./codesnippet/VisualBasic/how-to-call-a-property-procedure_2.vb)]  
  
2.  Wenn die Eigenschaft Argumente annimmt, fügen Sie nach dem Eigenschaftennamen runde Klammern ein, die die Argumentliste einschließen.  Wenn keine Argumente vorliegen, können Sie die Klammern auch weglassen.  
  
3.  Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern, und trennen Sie die Argumente durch Kommas.  Geben Sie die Argumente unbedingt in genau der Reihenfolge an, in der die Eigenschaft die entsprechenden Parameter definiert.  
  
 Der Wert, der auf der rechten Seite der Zuweisungsanweisung generiert wird, wird in der Eigenschaft gespeichert.  
  
## Siehe auch  
 [Eigenschaftenprozeduren](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md)   
 [Differences Between Properties and Variables in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)   
 [How to: Create a Property](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-property.md)   
 [How to: Declare a Property with Mixed Access Levels](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)   
 [How to: Declare and Call a Default Property in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)   
 [How to: Put a Value in a Property](../../../../visual-basic/programming-guide/language-features/procedures/how-to-put-a-value-in-a-property.md)   
 [How to: Get a Value from a Property](../../../../visual-basic/programming-guide/language-features/procedures/how-to-get-a-value-from-a-property.md)   
 [Get Statement](../../../../visual-basic/language-reference/statements/get-statement.md)   
 [Set Statement](../../../../visual-basic/language-reference/statements/set-statement.md)