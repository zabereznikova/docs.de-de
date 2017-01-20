---
title: "How to: Return a Value from a Procedure (Visual Basic) | Microsoft Docs"
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
  - "Visual Basic code, procedures"
  - "procedures, returning from"
  - "procedures, returning a value"
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Return a Value from a Procedure (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Eine `Function`\-Prozedur gibt an den Aufrufcode einen Wert zurück. Dies geschieht entweder durch Ausführen einer `Return`\-Anweisung oder weil eine `Exit Function`\-Anweisung oder eine `End Function`\-Anweisung auftritt.  
  
### So geben Sie mit der Return\-Anweisung einen Wert zurück  
  
1.  Fügen Sie eine `Return`\-Anweisung an dem Punkt ein, an dem die Aufgabe der Prozedur abgeschlossen ist.  
  
2.  Geben Sie nach dem `Return`\-Schlüsselwort einen Ausdruck ein, der den Wert ergibt, den Sie an den Aufrufcode zurückgeben möchten.  
  
3.  Die gleiche Prozedur kann mehrere `Return`\-Anweisungen enthalten.  
  
     Mit der folgenden `Function`\-Prozedur wird die längste Seite \(die Hypotenuse\) eines rechtwinkligen Dreiecks berechnet und an den Aufrufcode zurückgegeben.  
  
     [!code-vb[VbVbcnProcedures#1](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-return-a-value-from-_1.vb)]  
  
     Das folgende Beispiel enthält einen typischen Aufruf von `hypotenuse`, mit dem der zurückgegebene Wert gespeichert wird.  
  
     [!code-vb[VbVbcnProcedures#6](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-return-a-value-from-_2.vb)]  
  
### So geben Sie mithilfe der Exit\-Funktion oder der End\-Funktion einen Wert zurück  
  
1.  Weisen Sie an wenigstens einer Stelle in der `Function`\-Prozedur dem Namen der Prozedur einen Wert zu.  
  
2.  Wenn Sie eine `Exit Function`\-Anweisung oder eine `End Function`\-Anweisung ausführen, gibt [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] den Wert zurück, der dem Namen der Prozedur zuletzt zugewiesen wurde.  
  
3.  Eine Prozedur kann mehrere `Exit Function`\-Anweisungen enthalten, und Sie können `Return`\-Anweisungen sowie `Exit Function`\-Anweisungen in einer Prozedur gleichzeitig verwenden.  
  
4.  Eine `Function`\-Prozedur darf nur eine `End Function`\-Anweisung enthalten.  
  
     Weitere Informationen und ein Beispiel finden Sie im Abschnitt "Rückgabewert" unter [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
## Siehe auch  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Sub Procedures](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Eigenschaftenprozeduren](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Operator Procedures](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md)   
 [Return Statement](../../../../visual-basic/language-reference/statements/return-statement.md)   
 [How to: Create a Procedure that Returns a Value](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-procedure-that-returns-a-value.md)   
 [How to: Call a Procedure That Returns a Value](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-procedure-that-returns-a-value.md)