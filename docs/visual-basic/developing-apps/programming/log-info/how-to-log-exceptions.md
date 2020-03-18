---
title: 'Gewusst wie: Protokollieren von Ausnahmen'
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions, logging
- exceptions, tracking
ms.assetid: a26c60e2-ae39-444a-aebb-33eccadc0eeb
ms.openlocfilehash: fe6949d727fae0c230ce7421b32fdaf2a498edbc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "74352086"
---
# <a name="how-to-log-exceptions-in-visual-basic"></a>Gewusst wie: Protokollieren von Ausnahmen in Visual Basic

Sie können die Objekte `My.Application.Log` und `My.Log` verwenden, um Informationen zu Ausnahmen zu protokollieren, die in Ihrer Anwendung auftreten. In diesen Beispielen wird gezeigt, wie Sie die `My.Application.Log.WriteException`-Methode verwenden können, um Ausnahmen zu protokollieren, die Sie explizit abfangen bzw. die unbehandelt sind.  
  
 Verwenden Sie für die Protokollierung von Nachverfolgungsinformationen die Methode `My.Application.Log.WriteEntry`. Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>  
  
### <a name="to-log-a-handled-exception"></a>Protokollieren einer behandelten Ausnahme  
  
1. Erstellen Sie die Methode, die die Ausnahmeinformationen generiert.  
  
     [!code-vb[VbVbalrMyApplicationLog#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#9)]  
  
2. Verwenden Sie einen `Try...Catch`-Block, um die Ausnahme abzufangen.  
  
     [!code-vb[VbVbalrMyApplicationLog#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#6)]  
  
3. Fügen Sie den Code, der eine Ausnahme generieren kann, in den `Try`-Block ein.  
  
     Heben Sie die Auskommentierung der Zeilen `Dim` und `MsgBox` auf, um eine <xref:System.NullReferenceException>-Ausnahme auszulösen.  
  
     [!code-vb[VbVbalrMyApplicationLog#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#7)]  
  
4. Verwenden Sie im `Catch`-Block die `My.Application.Log.WriteException`-Methode, um die Ausnahmeinformationen zu schreiben.  
  
     [!code-vb[VbVbalrMyApplicationLog#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#8)]  
  
     Das folgende Beispiel zeigt den vollständigen Code für das Protokollieren einer behandelten Ausnahme.  
  
     [!code-vb[VbVbalrMyApplicationLog#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#10)]  
  
### <a name="to-log-an-unhandled-exception"></a>Protokollieren einer nicht behandelten Ausnahme  
  
1. Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**.  
  
2. Klicken Sie auf die Registerkarte **Anwendung** .  
  
3. Klicken Sie auf die Schaltfläche **Anwendungsereignisse anzeigen** um den Code-Editor zu öffnen.  
  
     Dadurch wird die Datei "ApplicationEvents.vb" geöffnet.  
  
4. Öffnen Sie die Datei "ApplicationEvents.vb" im Code-Editor. Wählen Sie im Menü **Allgemein** den Eintrag **MyApplication-Ereignisse**aus.  
  
5. Wählen Sie im Menü **Deklarationen** den Eintrag **UnhandledException** aus.  
  
     Die Anwendung löst das Ereignis <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> aus, bevor die Hauptanwendung ausgeführt wird.  
  
6. Fügen Sie die Methode `My.Application.Log.WriteException` zum `UnhandledException` -Ereignishandler hinzu.  
  
     [!code-vb[VbVbalrMyApplicationLog#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/MyEventsFake.vb#4)]  
  
     Das folgende Beispiel zeigt den vollständigen Code für das Protokollieren einer nicht behandelten Ausnahme.  
  
     [!code-vb[VbVbalrMyApplicationLog#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/MyEventsFake.vb#5)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [Arbeiten mit Anwendungsprotokollen](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)
- [Gewusst wie: Schreiben von Protokollmeldungen](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)
- [Exemplarische Vorgehensweise: Bestimmen, wohin „My.Application.Log“ Informationen schreibt](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)
- [Exemplarische Vorgehensweise: Ändern des Orts, in den „My.Application.Log“ Informationen schreibt](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)
