---
title: 'Gewusst wie: Schreiben von Ereignisinformationen in eine Textdatei (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- event logs [Visual Studio], writing event information
- text files [Visual Basic], writing event information to a text file
- events [Visual Basic], writing event information to a text file
ms.assetid: 9ca7cc03-bf99-4933-9e5e-61ee28e9a6b4
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 944d874de5c3872f9efe5e287e5354c94c792b95
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-event-information-to-a-text-file-visual-basic"></a>Gewusst wie: Schreiben von Ereignisinformationen in eine Textdatei (Visual Basic)
Sie können die Objekte `My.Application.Log` und `My.Log` verwenden, um Informationen über Ereignisse zu protokollieren, die in Ihrer Anwendung auftreten. Dieses Beispiel zeigt die Verwendung der `My.Application.Log.WriteEntry`-Methode zum Protokollieren von Nachverfolgungsinformationen, um eine Datei zu protokollieren.  
  
### <a name="to-add-and-configure-the-file-log-listener"></a>Hinzufügen und Konfigurieren des Dateiprotokolllisteners  
  
1.  Klicken Sie im **Projektmappen-Explorer** auf "app.config", und wählen Sie **Öffnen**aus.  
  
     \- oder –  
  
     Wenn keine app.config-Datei vorhanden ist:  
  
    1.  Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.  
  
    2.  Wählen Sie im Dialogfeld **Neues Element hinzufügen** den Eintrag **Anwendungskonfigurationsdatei**aus.  
  
    3.  Klicken Sie auf **Hinzufügen**.  
  
2.  Suchen Sie den Abschnitt `<listeners>` in der Anwendungskonfigurationsdatei.  
  
     Sie finden den Abschnitt \<listeners> im Abschnitt \<source> mit dem Namensattribute „DefaultScource“, das sich im Abschnitt \<system.diagnostics> befindet, der wiederum unter dem Abschnitt der höchsten Ebene \<configuration> zu finden ist.  
  
3.  Fügen Sie dem `<listeners>` -Abschnitt dieses Element hinzu:  
  
    ```xml  
    <add name="FileLogListener" />  
    ```  
  
4.  Machen Sie den Abschnitt `<sharedListeners>` im Abschnitt `<system.diagnostics>`, der sich unter dem Abschnitt der höchsten Ebene `<configuration>` befindet.  
  
5.  Fügen Sie dem `<sharedListeners>` -Abschnitt dieses Element hinzu:  
  
    ```xml  
    <add name="FileLogListener"   
        type="Microsoft.VisualBasic.Logging.FileLogTraceListener,   
              Microsoft.VisualBasic, Version=8.0.0.0, Culture=neutral,   
              PublicKeyToken=b03f5f7f11d50a3a"  
        initializeData="FileLogListenerWriter"  
        location="Custom"  
        customlocation="c:\temp\" />  
    ```  
  
     Ändern Sie den Wert des `customlocation`-Attributs in das Protokollverzeichnis.  
  
    > [!NOTE]
    >  Verwenden Sie ein Attribut, dass denselben Namen wie die Eigenschaft in Kleinbuchstaben hat, um den Wert einer Listenereigenschaft festzulegen. Die Attribute `location` und `customlocation` legen z.B. die Werte der Eigenschaften <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.Location%2A> und <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.CustomLocation%2A> fest.  
  
### <a name="to-write-event-information-to-the-file-log"></a>Schreiben von Ereignisinformationen in das Dateiprotokoll  
  
-   Verwenden Sie die `My.Application.Log.WriteEntry`- oder `My.Application.Log.WriteException`-Methode, um Informationen in das Dateiprotokoll zu schreiben. Weitere Informationen finden Sie unter [Vorgehensweise: Schreiben von Protokollmeldungen](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) und [Vorgehensweise: Protokollieren von Ausnahmen](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md).  
  
     Nachdem Sie den Dateiprotokolllistener für eine Assembly konfiguriert haben, empfängt er alle Meldungen, die `My.Application.Log` von der betreffenden Assembly schreibt.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>  
 <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>  
 <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>  
 [Arbeiten mit Anwendungsprotokollen](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)  
 [Gewusst wie: Protokollieren von Ausnahmen](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)
