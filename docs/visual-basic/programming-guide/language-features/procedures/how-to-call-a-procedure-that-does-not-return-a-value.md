---
title: "Gewusst wie: Aufrufen einer Prozedur, die keinen Wert zurückgibt (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bbea50132d1110b38bf9b01397795a2cd51f86d4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a>Gewusst wie: Aufrufen einer Prozedur, die keinen Wert zurückgibt (Visual Basic)
Ein `Sub` Prozedur wird einen Wert nicht an den aufrufenden Code zurückgegeben. Sie rufen es explizit mit einer eigenständigen aufrufende Anweisung. Sie können keine es einfach mit seinen Namen innerhalb eines Ausdrucks aufrufen.  
  
### <a name="to-call-a-sub-procedure"></a>Zum Aufrufen einer Subprozedur  
  
1.  Geben Sie den Namen des der `Sub` Prozedur.  
  
2.  Führen Sie den Namen der Prozedur mit Klammern einschließen, um die Argumentliste einschließen. Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen. Allerdings besser mit den Klammern Code lesen.  
  
3.  Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt ein. Achten Sie darauf geben Sie die Argumente in der gleichen Reihenfolge, die die `Sub` Prozedur definiert, die entsprechenden Parameter.  
  
     Im folgenden Beispiel wird die [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> Funktion, um ein Anwendungsfenster aktivieren. <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>wird den Titel des Fensters als einziges Argument. Es gibt einen Wert nicht an den aufrufenden Code zurück. Wenn kein Editor-Prozess nicht ausgeführt wird, löst das Beispiel ein <xref:System.ArgumentException>. Die `Shell` Verfahren wird davon ausgegangen, die Anwendungen, die in den Pfaden, die angegeben sind.  
  
     [!code-vb[VbVbalrCatRef#11](./codesnippet/VisualBasic/how-to-call-a-procedure-that-does-not-return-a-value_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.Interaction.Shell%2A>  
 <xref:System.ArgumentException>  
 [Verfahren](./index.md)  
 [Sub-Prozeduren](./sub-procedures.md)  
 [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)  
 [Sub-Anweisung](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Gewusst wie: Erstellen einer Prozedur](./how-to-create-a-procedure.md)  
 [Gewusst wie: Aufrufen einer Prozedur, die einen Wert zurückgibt](./how-to-call-a-procedure-that-returns-a-value.md)  
 [Vorgehensweise: Aufrufen eines Ereignishandlers in Visual Basic](./how-to-call-an-event-handler.md)
