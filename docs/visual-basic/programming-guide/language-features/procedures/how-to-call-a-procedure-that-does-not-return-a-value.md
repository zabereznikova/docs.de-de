---
title: 'Gewusst wie: Aufrufen einer Prozedur, die keinen Wert zurückgibt'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
ms.openlocfilehash: 3a5de98c6edf795a11bd9f0465aa6919f09eebfa
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74340962"
---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a>Gewusst wie: Aufrufen einer Prozedur, die keinen Wert zurückgibt (Visual Basic)
Eine `Sub` Prozedur gibt keinen Wert an den aufrufenden Code zurück. Sie rufen Sie explizit mit einer eigenständigen aufrufenden Anweisung auf. Sie können ihn nicht durch einfaches Verwenden des Namens innerhalb eines Ausdrucks abrufen.  
  
### <a name="to-call-a-sub-procedure"></a>So wenden Sie eine unter Prozedur an  
  
1. Geben Sie den Namen der `Sub` Prozedur an.  
  
2. Befolgen Sie den Namen der Prozedur mit Klammern, um die Argumentliste einzuschließen. Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen. Durch die Verwendung der Klammern wird der Code jedoch leichter lesbar.  
  
3. Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern, getrennt durch Kommas. Stellen Sie sicher, dass Sie die Argumente in derselben Reihenfolge bereitstellen, in der die `Sub` Prozedur die entsprechenden Parameter definiert.  
  
     Im folgenden Beispiel wird die Visual Basic <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>-Funktion aufgerufen, um ein Anwendungsfenster zu aktivieren. <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> nimmt den Fenstertitel als einziges Argument an. Er gibt keinen Wert an den aufrufenden Code zurück. Wenn ein Notepad-Prozess nicht ausgeführt wird, löst das Beispiel eine <xref:System.ArgumentException>aus. Bei der `Shell` Prozedur wird davon ausgegangen, dass sich die Anwendungen in den angegebenen Pfaden befinden.  
  
     [!code-vb[VbVbalrCatRef#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCatRef/VB/Class1.vb#11)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:System.ArgumentException>
- [Verfahren](./index.md)
- [Sub-Prozeduren](./sub-procedures.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Sub-Anweisung](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [Gewusst wie: Erstellen einer Prozedur](./how-to-create-a-procedure.md)
- [Gewusst wie: Aufrufen einer Prozedur, die einen Wert zurückgibt](./how-to-call-a-procedure-that-returns-a-value.md)
- [Gewusst wie: Abrufen eines Ereignis Handlers in Visual Basic](./how-to-call-an-event-handler.md)
