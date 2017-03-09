---
title: "How to: Create a Procedure that Returns a Value (Visual Basic) | Microsoft Docs"
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
  - "procedures, defining"
  - "Visual Basic code, procedures"
  - "procedures, returning a value"
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# How to: Create a Procedure that Returns a Value (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Mit einer `Function`\-Prozedur geben Sie einen Wert an den Aufrufcode zurück.  
  
### So erstellen Sie eine Prozedur, die einen Wert zurückgibt  
  
1.  Verwenden Sie außerhalb anderer Prozeduren eine `Function`\-Anweisung, auf die eine `End Function`\-Anweisung folgt.  
  
2.  Geben Sie in der `Function`\-Anweisung nach dem `Function`\-Schlüsselwort den Namen der Prozedur und danach die Parameterliste in Klammern ein.  
  
3.  Geben Sie nach den Klammern eine `As`\-Klausel ein, um den Datentyp des zurückgegebenen Werts anzugeben.  
  
4.  Setzen Sie die Codeanweisungen der Prozedur zwischen die Anweisungen `Function` und `End Function`.  
  
5.  Verwenden Sie eine `Return`\-Anweisung, um den Wert an den Aufrufcode zurückzugeben.  
  
     Mit der folgenden `Function`\-Prozedur wird die längste Seite \(die Hypotenuse\) eines rechtwinkligen Dreiecks anhand der Werte der beiden anderen Seiten berechnet.  
  
     [!code-vb[VbVbcnProcedures#1](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-create-a-procedur_1.vb)]  
  
     Im folgenden Beispiel wird ein typischer Aufruf von `hypotenuse` dargestellt.  
  
     [!code-vb[VbVbcnProcedures#6](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-create-a-procedur_2.vb)]  
  
## Siehe auch  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Sub Procedures](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Eigenschaftenprozeduren](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Operator Procedures](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md)   
 [How to: Return a Value from a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-return-a-value-from-a-procedure.md)   
 [How to: Call a Procedure That Returns a Value](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-procedure-that-returns-a-value.md)