---
title: "How to: Write Event Information to a Text File (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "event logs [Visual Studio], writing event information"
  - "text files, writing event information to a text file"
  - "events [Visual Basic], writing event information to a text file"
ms.assetid: 9ca7cc03-bf99-4933-9e5e-61ee28e9a6b4
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# How to: Write Event Information to a Text File (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Sie können das `My.Application.Log`\-Objekt und das `My.Log`\-Objekt verwenden, um Informationen über in der Anwendung auftretende Ereignisse zu protokollieren.  In diesem Beispiel wird veranschaulicht, wie die `My.Application.Log.WriteEntry`\-Methode verwendet wird, um Ablaufverfolgungsinformationen in einer Protokolldatei zu protokollieren.  
  
### So fügen Sie die Dateiprotokollüberwachung hinzu und konfigurieren diese  
  
1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf app.config, und wählen Sie **Öffnen**.  
  
     \- oder \-  
  
     Wenn keine app.config\-Datei vorhanden ist:  
  
    1.  Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.  
  
    2.  Klicken Sie im Dialogfeld **Neues Element hinzufügen** auf **Anwendungskonfigurationsdatei**.  
  
    3.  Klicken Sie auf **Hinzufügen**.  
  
2.  Suchen Sie den `<listeners>`\-Abschnitt in der Anwendungskonfigurationsdatei.  
  
     Der \<listeners\>\-Abschnitt befindet sich im \<source\>\-Abschnitt mit dem name\-Attribut "DefaultSource". Dieser befindet sich im \<system.diagnostics\>\-Abschnitt im \<configuration\>\-Abschnitt auf der obersten Ebene.  
  
3.  Fügen Sie diesem `<listeners>`\-Abschnitt dieses Element hinzu:  
  
    ```  
    <add name="FileLogListener" />  
    ```  
  
4.  Suchen Sie den `<sharedListeners>`\-Abschnitt im `<system.diagnostics>`\-Abschnitt im `<configuration>`\-Abschnitt auf der obersten Ebene.  
  
5.  Fügen Sie diesem `<sharedListeners>`\-Abschnitt dieses Element hinzu:  
  
    ```  
    <add name="FileLogListener"   
        type="Microsoft.VisualBasic.Logging.FileLogTraceListener,   
              Microsoft.VisualBasic, Version=8.0.0.0, Culture=neutral,   
              PublicKeyToken=b03f5f7f11d50a3a"  
        initializeData="FileLogListenerWriter"  
        location="Custom"  
        customlocation="c:\temp\" />  
    ```  
  
     Geben Sie für das `customlocation`\-Attribut das Protokollverzeichnis an.  
  
    > [!NOTE]
    >  Wenn Sie den Wert einer Listenereigenschaft festlegen möchten, verwenden Sie ein Attribut mit demselben Namen wie die Eigenschaft, wobei alle Buchstaben im Namen Kleinbuchstaben sein müssen.  So wird z. B. mit dem `location`\-Attribut und dem `customlocation`\-Attribut der Wert der <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.Location%2A>\-Eigenschaft und der <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.CustomLocation%2A>\-Eigenschaft festgelegt.  
  
### So schreiben Sie Ereignisinformationen ins Dateiprotokoll  
  
-   Verwenden Sie die `My.Application.Log.WriteEntry`\-Methode oder die `My.Application.Log.WriteException`\-Methode, um Informationen ins Dateiprotokoll zu schreiben.  Weitere Informationen finden Sie unter [Gewusst wie: Schreiben von Protokollmeldungen](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) und unter [How to: Log Exceptions](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md).  
  
     Wenn Sie die Dateiprotokollüberwachung für eine Assembly konfigurieren, empfängt diese alle Meldungen, die `My.Application.Log` schreibt, von dieser Assembly.  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>   
 <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>   
 [Arbeiten mit Anwendungsprotokollen](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)   
 [How to: Log Exceptions](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)