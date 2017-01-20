---
title: "How to: Call a Procedure That Returns a Value (Visual Basic) | Microsoft Docs"
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
  - "procedure calls, returning values"
  - "Visual Basic code, procedures"
  - "procedures, calling"
  - "procedures, returning a value"
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Call a Procedure That Returns a Value (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`Function`\-Prozeduren geben einen Wert an den Aufrufcode zurück.  Zum Aufrufen einer solchen Prozedur tragen Sie ihren Namen und die Argumente entweder auf der rechten Seite der Zuweisungsanweisung ein oder in einen Ausdruck.  
  
### So rufen Sie eine Function\-Prozedur innerhalb eines Ausdrucks auf  
  
1.  Verwenden Sie den Namen der `Function`\-Prozedur auf die gleiche Weise wie eine Variable.  Sie können einen `Function`\-Prozeduraufruf überall dort verwenden, wo Sie eine Variable oder Konstante in einem Ausdruck verwenden können.  
  
2.  Auf den Prozedurnamen müssen Klammern folgen, die die Argumentliste einschließen.  Wenn keine Argumente vorliegen, können Sie die Klammern auch weglassen.  Mit den Klammern ist der Code jedoch besser lesbar.  
  
3.  Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern, und trennen Sie die Argumente durch Kommas.  Geben Sie die Argumente unbedingt in genau der Reihenfolge an, in der die `Function`\-Prozedur die entsprechenden Parameter definiert.  
  
     Sie können auch ein oder weitere Argumente über den Namen übergeben.  Weitere Informationen finden Sie unter [Passing Arguments by Position and by Name](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).  
  
4.  Der von der Prozedur zurückgegebene Wert gehört ebenso wie der Wert einer Variablen oder Konstante zum Ausdruck.  
  
### So rufen Sie in einer Zuweisungsanweisung eine Function\-Prozedur auf  
  
1.  Fügen Sie den Namen der `Function`\-Prozedur hinter dem Gleichheitszeichen \(`=`\) in die Zuweisungsanweisung ein.  
  
2.  Auf den Prozedurnamen müssen Klammern folgen, die die Argumentliste einschließen.  Wenn keine Argumente vorliegen, können Sie die Klammern auch weglassen.  Mit den Klammern ist der Code jedoch besser lesbar.  
  
3.  Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern, und trennen Sie die Argumente durch Kommas.  Geben Sie die Argumente unbedingt in genau der Reihenfolge an, in der die `Function`\-Prozedur die entsprechenden Parameter definiert, falls Sie die Argumente nicht über den Namen übergeben.  
  
4.  Der von der Prozedur zurückgegebene Wert wird auf der linken Seite der Zuweisungsanweisung in der Variablen oder Eigenschaft gespeichert.  
  
## Beispiel  
 Im folgenden Beispiel wird die <xref:Microsoft.VisualBasic.Interaction.Environ%2A> von [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] aufgerufen, um den Wert einer Umgebungsvariablen des Betriebssystems abzurufen.  Von der ersten Zeile wird `Environ` in einem Ausdruck aufgerufen, von der zweiten Zeile in einer Zuweisungsanweisung.  `Environ` erfordert als einziges Argument den Variablennamen.  Die Funktion gibt den Wert der Variablen an den Aufrufcode zurück.  
  
 [!code-vb[VbVbcnProcedures#7](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-call-a-procedure-_0_1.vb)]  
  
## Siehe auch  
 [Function\-Prozeduren](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md)   
 [How to: Create a Procedure that Returns a Value](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-procedure-that-returns-a-value.md)   
 [How to: Return a Value from a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-return-a-value-from-a-procedure.md)   
 [How to: Call a Procedure that Does Not Return a Value](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-procedure-that-does-not-return-a-value.md)