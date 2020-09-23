---
title: 'Vorgehensweise: Aufrufen einer Prozedur, die keinen Wert zurückgibt'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
ms.openlocfilehash: 2686a4d9dc10cde209f558771feeb5ba4f4ccb21
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075004"
---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a>Gewusst wie: Aufrufen einer Prozedur, die keinen Wert zurückgibt (Visual Basic)

Eine `Sub` Prozedur gibt keinen Wert an den aufrufenden Code zurück. Sie rufen Sie explizit mit einer eigenständigen aufrufenden Anweisung auf. Sie können ihn nicht durch einfaches Verwenden des Namens innerhalb eines Ausdrucks abrufen.  
  
### <a name="to-call-a-sub-procedure"></a>So wenden Sie eine unter Prozedur an  
  
1. Geben Sie den Namen der `Sub` Prozedur an.  
  
2. Befolgen Sie den Namen der Prozedur mit Klammern, um die Argumentliste einzuschließen. Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen. Durch die Verwendung der Klammern wird der Code jedoch leichter lesbar.  
  
3. Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern, getrennt durch Kommas. Stellen Sie sicher, dass Sie die Argumente in derselben Reihenfolge bereitstellen, in der die `Sub` Prozedur die entsprechenden Parameter definiert.  
  
     Im folgenden Beispiel wird die Visual Basic- <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> Funktion aufgerufen, um ein Anwendungsfenster zu aktivieren. <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> nimmt den Fenstertitel als einziges Argument an. Er gibt keinen Wert an den aufrufenden Code zurück. Wenn ein Notepad-Prozess nicht ausgeführt wird, wird im Beispiel eine ausgelöst <xref:System.ArgumentException> . Die `Shell` Prozedur geht davon aus, dass sich die Anwendungen in den angegebenen Pfaden befinden.  
  
     [!code-vb[VbVbalrCatRef#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCatRef/VB/Class1.vb#11)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:System.ArgumentException>
- [Vorgehensweisen](./index.md)
- [Sub-Prozeduren](./sub-procedures.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Sub-Anweisung](../../../language-reference/statements/sub-statement.md)
- [Vorgehensweise: Erstellen einer Prozedur](./how-to-create-a-procedure.md)
- [Vorgehensweise: Aufrufen einer Prozedur, die einen Wert zurückgibt](./how-to-call-a-procedure-that-returns-a-value.md)
- [Gewusst wie: Aufrufen eines Ereignishandlers in Visual Basic](./how-to-call-an-event-handler.md)
