---
title: 'Gewusst wie: Protokollieren von Meldungen beim Starten oder Beenden der Anwendung'
ms.date: 07/20/2015
helpviewer_keywords:
- event logs, shutdown
- My.Application.Log object, logging
- Startup event [Visual Basic]
- event logs, startup
- Shutdown event [Visual Basic]
- My.Log object, logging
ms.assetid: 67624d05-cddf-48b7-8c36-5c99baa4c621
ms.openlocfilehash: ac5fb17e527bcbcb55f98ec0ced06c152555ce6c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410074"
---
# <a name="how-to-log-messages-when-the-application-starts-or-shuts-down-visual-basic"></a>Gewusst wie: Protokollieren von Meldungen beim Starten oder Beenden der Anwendung (Visual Basic)

Sie können die Objekte `My.Application.Log` und `My.Log` verwenden, um Informationen über Ereignisse zu protokollieren, die in Ihrer Anwendung auftreten. Dieses Beispiel zeigt die Verwendung der `My.Application.Log.WriteEntry` -Methode mit den Ereignissen `Startup` und `Shutdown` zum Erfassen von Ablaufverfolgungsinformationen.  
  
### <a name="to-access-the-applications-event-handler-code"></a>Zugriff auf den Code des Ereignishandlers der Anwendung  
  
1. Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**.  
  
2. Klicken Sie auf die Registerkarte **Anwendung** .  
  
3. Klicken Sie auf die Schaltfläche **Anwendungsereignisse anzeigen** um den Code-Editor zu öffnen.  
  
     Dadurch wird die Datei "ApplicationEvents.vb" geöffnet.  
  
### <a name="to-log-messages-when-the-application-starts"></a>Protokollieren von Meldungen beim Starten der Anwendung  
  
1. Öffnen Sie die Datei "ApplicationEvents.vb" im Code-Editor. Wählen Sie im Menü **Allgemein** den Eintrag **MyApplication-Ereignisse**aus.  
  
2. Wählen Sie im Menü **Deklarationen** den Eintrag **Start**aus.  
  
     Die Anwendung löst das Ereignis <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> aus, bevor die Hauptanwendung ausgeführt wird.  
  
3. Fügen Sie die Methode `My.Application.Log.WriteEntry` zum `Startup` -Ereignishandler hinzu.  
  
     [!code-vb[VbVbalrMyApplicationLog#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/MyEventsFake.vb#1)]  
  
### <a name="to-log-messages-when-the-application-shuts-down"></a>Protokollieren von Meldungen beim Herunterfahren der Anwendung  
  
1. Öffnen Sie die Datei "ApplicationEvents.vb" im Code-Editor. Wählen Sie im Menü **Allgemein** den Eintrag **MyApplication-Ereignisse**aus.  
  
2. Wählen Sie im Menü **Deklarationen** den Eintrag **Herunterfahren**aus.  
  
     Die Anwendung löst das <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> -Ereignis aus, wenn der Hauptthread der Anwendung ausgeführt wird, jedoch bevor er heruntergefahren wird.  
  
3. Fügen Sie die Methode `My.Application.Log.WriteEntry` zum `Shutdown` -Ereignishandler hinzu.  
  
     [!code-vb[VbVbalrMyApplicationLog#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/MyEventsFake.vb#2)]  
  
## <a name="example"></a>Beispiel  

 Sie können den **Projekt-Designer** verwenden, um auf die Anwendungsereignisse im Code-Editor zuzugreifen. Weitere Informationen finden Sie unter [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
 [!code-vb[VbVbalrMyApplicationLog#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/MyEventsFake.vb#3)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [Seite "Anwendung", Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [Arbeiten mit Anwendungsprotokollen](working-with-application-logs.md)
