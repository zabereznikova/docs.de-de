---
title: 'Vorgehensweise: Aufrufen einer Prozedur, die keinen Wert (Visual Basic) zurückgibt'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
ms.openlocfilehash: 05b4b1cb29abff97c44c33d462375fc4d5ab159d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818578"
---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a>Vorgehensweise: Aufrufen einer Prozedur, die keinen Wert (Visual Basic) zurückgibt
Ein `Sub` -Prozedur gibt keinen Wert an den aufrufenden Code zurück. Sie rufen es explizit mit einer eigenständigen aufrufenden Anweisung. Sie können nicht sie aufrufen, indem Sie einfach den Namen in einem Ausdruck.  
  
### <a name="to-call-a-sub-procedure"></a>Eine Sub-Prozedur aufrufen.  
  
1.  Geben Sie den Namen des der `Sub` Verfahren.  
  
2.  Führen Sie den Namen der Prozedur mit Klammern, um die Argumentliste einschließen. Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen. Allerdings wird bei der Klammern verwenden die Ihr Code einfacher zu lesen.  
  
3.  Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt ein. Werden Sie sicher, dass Sie die Argumente in der gleichen Reihenfolge angeben, die die `Sub` Prozedur definiert, die entsprechenden Parameter.  
  
     Im folgenden Beispiel wird die Visual Basic <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> Funktion, um ein Anwendungsfenster aktivieren. <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> wird den Titel des Fensters als einziges Argument. Es gibt einen Wert nicht an den aufrufenden Code zurück. Wenn kein Editor-Prozess nicht ausgeführt wird, löst das Beispiel einer <xref:System.ArgumentException>. Die `Shell` Verfahren wird davon ausgegangen, die Anwendungen, die in den Pfaden, die angegeben werden.  
  
     [!code-vb[VbVbalrCatRef#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCatRef/VB/Class1.vb#11)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:System.ArgumentException>
- [Verfahren](./index.md)
- [Sub-Prozeduren](./sub-procedures.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Sub-Anweisung](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [Vorgehensweise: Erstellen Sie eine Prozedur](./how-to-create-a-procedure.md)
- [Vorgehensweise: Aufrufen einer Prozedur, die einen Wert zurückgibt.](./how-to-call-a-procedure-that-returns-a-value.md)
- [Vorgehensweise: Aufrufen eines Ereignishandlers in Visual Basic](./how-to-call-an-event-handler.md)
