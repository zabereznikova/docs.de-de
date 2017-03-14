---
title: "Return Statement (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Return"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Return statement, syntax"
  - "control flow, returning control to expressions"
  - "Return statement"
  - "expressions [Visual Basic], returning control to"
ms.assetid: ac86e7f0-5a67-42c3-9834-0e0381efa3ec
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Return Statement (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Gibt die Steuerung an den Code zurück, mit dem eine der Prozeduren `Function`, `Sub`, `Get`, `Set` oder `Operator` aufgerufen wurde.  
  
## Syntax  
  
```  
Return  
-or-  
Return expression  
```  
  
## Bestandteil  
 `expression`  
 In den Prozeduren `Function`, `Get` oder `Operator` erforderlich.  Ausdruck, der den Wert darstellt, der an den aufrufenden Code zurückgegeben werden soll.  
  
## Hinweise  
 In einer `Sub`\-Prozedur oder einer `Set`\-Prozedur entspricht die `Return`\-Anweisung einer `Exit Sub`\-Anweisung oder einer `Exit Property`\-Anweisung, und `expression` muss nicht angegeben werden.  
  
 In den Prozeduren `Function`, `Get` oder `Operator` muss die `Return`\-Anweisung `expression` enthalten, und `expression` muss einen Datentyp ergeben, der in den Rückgabetyp der Prozedur konvertiert werden kann.  In einer `Function`\-Prozedur oder einer `Get`\-Prozedur können Sie auch stattdessen dem Prozedurnamen einen Ausdruck zuweisen, der als Rückgabewert fungiert, und anschließend eine `Exit Function`\-Anweisung oder eine `Exit Property`\-Anweisung ausführen.  In einer `Operator`\-Prozedur müssen Sie `Return` `expression` verwenden.  
  
 Sie können in eine Prozedur so viele `Return`\-Anweisungen wie erforderlich einfügen.  
  
> [!NOTE]
>  Der Code in einem `Finally`\-Block wird ausgeführt, nachdem eine `Return`\-Anweisung in einem `Try`\-Block oder einem `Catch`\-Block erreicht wurde, jedoch vor dem Ausführen der `Return`\-Anweisung.  Eine `Return`\-Anweisung kann nicht in einem `Finally`\-Block eingeschlossen werden.  
  
## Beispiel  
 Im folgenden Beispiel kehrt die Prozedur mehrmals mit der `Return`\-Anweisung zum aufrufenden Code zurück, wenn keine weiteren Aufgaben auszuführen sind.  
  
 [!code-vb[VbVbalrStatements#53](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/return-statement_1.vb)]  
  
## Siehe auch  
 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Get Statement](../../../visual-basic/language-reference/statements/get-statement.md)   
 [Set Statement](../../../visual-basic/language-reference/statements/set-statement.md)   
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)   
 [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md)   
 [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)