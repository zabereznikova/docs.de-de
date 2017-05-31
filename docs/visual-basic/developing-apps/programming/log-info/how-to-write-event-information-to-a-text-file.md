---
title: 'Vorgehensweise: Schreiben von Ereignisinformationen in eine Textdatei (Visual Basic) | Microsoft-Dokumentation'
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
- event logs [Visual Studio], writing event information
- text files, writing event information to a text file
- events [Visual Basic], writing event information to a text file
ms.assetid: 9ca7cc03-bf99-4933-9e5e-61ee28e9a6b4
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2701f634332acdfaa81a6bf4e1d1309968366d7f
ms.contentlocale: de-de
ms.lasthandoff: 05/22/2017

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
  
    ```  
    <add name="FileLogListener" />  
    ```  
  
4.  Machen Sie den Abschnitt `<sharedListeners>` im Abschnitt `<system.diagnostics>`, der sich unter dem Abschnitt der höchsten Ebene `<configuration>` befindet.  
  
5.  Fügen Sie dem `<sharedListeners>` -Abschnitt dieses Element hinzu:  
  
    ```  
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
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>   
 <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>   
 [Arbeiten mit Anwendungsprotokollen](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)   
 [Gewusst wie: Protokollieren von Ausnahmen](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)
