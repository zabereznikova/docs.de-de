---
title: "Gewusst wie: Aufrufen einer Prozedur, die keinen Wert (Visual Basic) zurückgibt | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- procedure calls, returning values
- Visual Basic code, procedures
- procedures, calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
caps.latest.revision: 17
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 17b2b902f3ee6ab79b2614b7742aa08fefab2420
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a>Gewusst wie: Aufrufen einer Prozedur, die keinen Wert zurückgibt (Visual Basic)
Ein `Sub` -Prozedur gibt keinen Wert an den aufrufenden Code zurück. Sie rufen es explizit mit einer eigenständigen aufrufenden Anweisung. Sie können nicht sie aufrufen, indem Sie einfach den Namen in einen Ausdruck.  
  
### <a name="to-call-a-sub-procedure"></a>Eine Subprozedur aufrufen  
  
1.  Geben Sie den Namen der `Sub` Verfahren.  
  
2.  Führen Sie den Namen der Prozedur mit Klammern um die Argumentliste einschließen. Wenn keine Argumente vorhanden sind, können Sie die Klammern auch weglassen. Allerdings vereinfacht die Verwendung der Klammern Code leichter zu lesen.  
  
3.  Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt. Stellen Sie sicher, geben Sie die Argumente in der gleichen Reihenfolge, die `Sub` -Prozedur die entsprechenden Parameter definiert.  
  
     Im folgenden Beispiel wird die [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>Funktion, um ein Anwendungsfenster aktiviert.</xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>erfordert den Fenstertitel als einziges Argument.</xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> Es keinen Wert an den aufrufenden Code zurück. Wenn kein Editor-Prozess nicht ausgeführt wird, löst das Beispiel eine <xref:System.ArgumentException>.</xref:System.ArgumentException> Die `Shell` Verfahren wird davon ausgegangen, die in den Pfaden angegeben sind.  
  
     [!code-vb[VbVbalrCatRef&#11;](./codesnippet/VisualBasic/how-to-call-a-procedure-that-does-not-return-a-value_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.Interaction.Shell%2A></xref:Microsoft.VisualBasic.Interaction.Shell%2A>   
 <xref:System.ArgumentException></xref:System.ArgumentException>   
 [Verfahren](./index.md)   
 [Sub-Prozeduren](./sub-procedures.md)   
 [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md)   
 [Sub-Anweisung](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Gewusst wie: Erstellen einer Prozedur](./how-to-create-a-procedure.md)   
 [Gewusst wie: Aufrufen einer Prozedur, die einen Wert zurückgibt](./how-to-call-a-procedure-that-returns-a-value.md)   
 [Gewusst wie: Aufrufen von einem Ereignishandler in Visual Basic](./how-to-call-an-event-handler.md)
