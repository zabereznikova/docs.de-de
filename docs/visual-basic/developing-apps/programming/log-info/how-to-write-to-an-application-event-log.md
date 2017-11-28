---
title: 'Gewusst wie: Schreiben in ein Anwendungsereignisprotokoll (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Computer.EventLog element
- WriteEntry method [Visual Basic]
- My.Computer.EventLog element
- event logs, writing to
ms.assetid: cadbc8c1-87af-4746-934e-55b79a4f6e2b
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 018aff8dc130bfe7217c861a7d7bc8ae275ccc66
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-to-an-application-event-log-visual-basic"></a>Gewusst wie: Schreiben in ein Anwendungsereignisprotokoll (Visual Basic)
Sie können die Objekte `My.Application.Log` und `My.Log` verwenden, um Informationen über Ereignisse zu erfassen, die in Ihrer Anwendung auftreten. Dieses Beispiel veranschaulicht, wie ein Ereignisprotokolllistener konfiguriert wird, damit `My.Application.Log` Ablaufverfolgungsinformationen in das Anwendungsereignisprotokoll schreibt.  
  
 In das Sicherheitsprotokoll kann nicht geschrieben werden. Um in das Systemprotokoll zu schreiben, müssen Sie Mitglied des Kontos "LocalSystem" oder "Administrator" sein.  
  
 Zum Anzeigen von Ereignisprotokollen können Sie den **Server-Explorer** oder die **Windows-Ereignisanzeige**verwenden. Weitere Informationen finden Sie unter [ETW Events in the .NET Framework](http://msdn.microsoft.com/library/d186276f-6afb-4dfd-bf3c-4251edc2c299).  
  
> [!NOTE]
>  Ereignisprotokolle werden unter Windows 95, Windows 98 bzw. Windows Millennium Edition (ME) nicht unterstützt.  
  
### <a name="to-add-and-configure-the-event-log-listener"></a>Hinzufügen und Konfigurieren des Ereignisprotokolllisteners  
  
1.  Klicken Sie im **Projektmappen-Explorer** auf "app.config", und wählen Sie **Öffnen**aus.  
  
     \- oder –  
  
     Wenn keine app.config-Datei vorhanden ist:  
  
    1.  Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.  
  
    2.  Wählen Sie im Dialogfeld **Neues Element hinzufügen** den Eintrag **Anwendungskonfigurationsdatei**aus.  
  
    3.  Klicken Sie auf **Hinzufügen**.  
  
2.  Suchen Sie den Abschnitt `<listeners>` in der Anwendungskonfigurationsdatei.  
  
     Sie finden den Abschnitt `<listeners>` im `<source>` -Abschnitt mit dem Namensattribut "DefaultSource", der in den `<system.diagnostics>` -Abschnitt verschachtelt ist, der seinerseits in den `<configuration>` -Abschnitt der obersten Ebene verschachtelt ist.  
  
3.  Fügen Sie dem `<listeners>` -Abschnitt dieses Element hinzu:  
  
    ```xml  
    <add name="EventLog"/>  
    ```  
  
4.  Suchen Sie den Abschnitt `<sharedListeners>` im `<system.diagnostics>` -Abschnitt im Abschnitt `<configuration>` der obersten Ebene.  
  
5.  Fügen Sie dem `<sharedListeners>` -Abschnitt dieses Element hinzu:  
  
    ```xml  
    <add name="EventLog"  
        type="System.Diagnostics.EventLogTraceListener, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
         initializeData="APPLICATION_NAME"/>  
    ```  
  
     Ersetzen Sie `APPLICATION_NAME` durch den Namen Ihrer Anwendung.  
  
    > [!NOTE]
    >  Normalerweise schreiben Anwendungen nur Fehler in das Ereignisprotokoll. Informationen zum Filtern von Protokollausgaben finden Sie unter [Walkthrough: Filtering My.Application.Log Output](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md).  
  
### <a name="to-write-event-information-to-the-event-log"></a>Schreiben von Ereignisinformationen in das Ereignisprotokoll  
  
-   Verwenden Sie die `My.Application.Log.WriteEntry` - oder die `My.Application.Log.WriteException` -Methode, um Informationen in das Ereignisprotokoll zu schreiben. Weitere Informationen finden Sie unter [Vorgehensweise: Schreiben von Protokollmeldungen](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) und [Vorgehensweise: Protokollieren von Ausnahmen](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md).  
  
     Nachdem Sie den Ereignisprotokolllistener für eine Assembly konfiguriert haben, empfängt er alle Meldungen, die `My.Applcation.Log` für die betreffende Assembly schreibt.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>  
 <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>  
 <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>  
 [Arbeiten mit Anwendungsprotokollen](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)  
 [Gewusst wie: Protokollieren von Ausnahmen](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)  
 [Exemplarische Vorgehensweise: Bestimmen, wohin „My.Application.Log“ Informationen schreibt](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)
