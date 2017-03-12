---
title: "How to: Call a Procedure that Does Not Return a Value (Visual Basic) | Microsoft Docs"
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
  - "procedure calls, returning values"
  - "Visual Basic code, procedures"
  - "procedures, calling"
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# How to: Call a Procedure that Does Not Return a Value (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Eine `Sub`\-Prozedur gibt keinen Wert an den Aufrufcode zurück.  Sie wird explizit mit einer eigenständigen Aufrufanweisung aufgerufen.  Sie kann nicht durch Einfügen ihres Namens in einen Ausdruck aufgerufen werden.  
  
### So rufen Sie eine Sub\-Prozedur auf  
  
1.  Geben Sie den Namen der `Sub` Prozedur an.  
  
2.  Auf den Prozedurnamen müssen Klammern folgen, die die Argumentliste einschließen.  Wenn keine Argumente vorliegen, können Sie die Klammern auch weglassen.  Mit den Klammern ist der Code jedoch besser lesbar.  
  
3.  Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern, und trennen Sie die Argumente durch Kommas.  Geben Sie die Argumente unbedingt in genau der Reihenfolge an, in der die `Sub`\-Prozedur die entsprechenden Parameter definiert.  
  
     Im folgenden Beispiel wird die [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>\-Funktion aufgerufen, um ein Anwendungsfenster zu aktivieren.  Die Funktion <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> erfordert als einziges Argument den Fenstertitel.  Sie gibt an den Aufrufcode keinen Wert zurück.  Wenn kein Editor\-Prozess ausgeführt wird, löst das Beispiel eine <xref:System.ArgumentException>\-Ausnahme aus.  Die `Shell`\-Prozedur setzt voraus, dass sich die Anwendungen in den angegebenen Pfaden befinden.  
  
     [!code-vb[VbVbalrCatRef#11](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-call-a-procedure-_1_1.vb)]  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.Interaction.Shell%2A>   
 <xref:System.ArgumentException>   
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Sub Procedures](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [How to: Create a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-procedure.md)   
 [How to: Call a Procedure That Returns a Value](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-procedure-that-returns-a-value.md)   
 [How to: Call an Event Handler in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-event-handler.md)