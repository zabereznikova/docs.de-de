---
title: "Walkthrough: Creating Custom Log Listeners (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "custom log listeners"
  - "My.Application.Log object, custom log listeners"
ms.assetid: 0e019115-4b25-4820-afb1-af8c6e391698
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Walkthrough: Creating Custom Log Listeners (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

In dieser exemplarische Vorgehensweise wird erläutert, wie Sie einen benutzerdefinierten Protokolllistener erstellen und so konfigurieren können, dass dieser die Ausgaben des `My.Application.Log`\-Objekts überwacht.  
  
## Erste Schritte  
 Protokolllistener müssen von der <xref:System.Diagnostics.TraceListener>\-Klasse erben.  
  
#### So erstellen Sie den Listener  
  
-   Erstellen Sie in der Anwendung eine Klasse mit dem Namen `SimpleListener`, die von <xref:System.Diagnostics.TraceListener> erbt.  
  
     [!code-vb[VbVbalrMyApplicationLog#16](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/VbVbalrMyApplicationLog/Form1.vb#16)]  
  
     Die <xref:System.Diagnostics.TraceListener.Write%2A>\-Methode und die <xref:System.Diagnostics.TraceListener.WriteLine%2A>\-Methode, die für die Basisklasse erforderlich sind, rufen `MsgBox` auf, um die Eingaben für diese Methoden anzuzeigen.  
  
     Das <xref:System.Security.Permissions.HostProtectionAttribute>\-Attribut wird auf die <xref:System.Diagnostics.TraceListener.Write%2A>\-Methode und die <xref:System.Diagnostics.TraceListener.WriteLine%2A>\-Methode angewendet, sodass deren Attribute den Methoden der Basisklasse entsprechen.  Durch das <xref:System.Security.Permissions.HostProtectionAttribute>\-Attribut kann der Host, auf dem der Code ausgeführt wird, ermitteln, dass der Code Hostschutzsynchronisierung verfügbar macht.  
  
    > [!NOTE]
    >  Das <xref:System.Security.Permissions.HostProtectionAttribute>\-Attribut gilt nur für nicht verwaltete Anwendungen, bei denen die Common Language Runtime ausgeführt wird und die Hostschutz implementieren, z. B. SQL Server.  
  
 Geben Sie der Assembly, die den Protokolllistener enthält, einen starken Namen, um sicherzustellen, dass `My.Application.Log` den Protokolllistener verwendet.  
  
 Im nächsten Verfahren werden einige einfache Schritte für das Erstellen einer Protokolllistenerassembly mit starkem Namen aufgeführt.  Weitere Informationen finden Sie unter [Erstellen und Verwenden von Assemblys mit starkem Namen](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md).  
  
#### So weisen Sie der Protokolllistenerassembly einen starken Namen zu  
  
1.  Wählen Sie im **Projektmappen\-Explorer** ein Projekt aus.  Klicken Sie im Menü **Projekt** auf **Eigenschaften**.  Weitere Informationen finden Sie unter [Introduction to the Project Designer](http://msdn.microsoft.com/de-de/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Klicken Sie auf die Registerkarte **Signierung**.  
  
3.  Wählen Sie das Feld **Assembly signieren** aus.  
  
4.  Wählen Sie in der Dropdownliste **Schlüsseldatei mit starkem Namen auswählen** die Option **\<Neu\>** aus.  
  
     Das Dialogfeld **Schlüssel für einen starken Namen erstellen** wird geöffnet.  
  
5.  Geben Sie im Feld **Schlüsseldateiname** einen Namen für die Schlüsseldatei an.  
  
6.  Geben Sie in den Feldern **Kennwort eingeben** und **Kennwort bestätigen** ein Kennwort ein.  
  
7.  Klicken Sie auf **OK**.  
  
8.  Erstellen Sie die Anwendung neu.  
  
## Hinzufügen des Listeners  
 Da die Assembly jetzt über einen starken Namen verfügt, müssen Sie den starken Namen des Listeners ermitteln, damit `My.Application.Log` den Protokolllistener verwendet.  
  
 Das Format eines Typs mit starkem Namen ist wie folgt.  
  
 \<Typname\>, \<Assemblyname\>, \<Versionsnummer\>, \<Kultur\>, \<starker Name\>  
  
#### So bestimmen Sie den starken Namen des Listeners  
  
-   Im folgenden Code wird gezeigt, wie der Name des Typs mit starkem Namen für `SimpleListener` bestimmt wird.  
  
     [!code-vb[VbVbalrMyApplicationLog#17](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/VbVbalrMyApplicationLog/Form1.vb#17)]  
  
     Der starke Name des Typs hängt vom Projekt ab.  
  
 Mithilfe des starken Namens können Sie den Listener der `My.Application.Log`\-Protokolllistenerauflistung hinzufügen.  
  
#### So fügen Sie den Listener My.Application.Log hinzu  
  
1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf app.config, und wählen Sie **Öffnen**.  
  
     \- oder \-  
  
     Wenn eine app.config\-Datei vorhanden ist:  
  
    1.  Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.  
  
    2.  Klicken Sie im Dialogfeld **Neues Element hinzufügen** auf **Anwendungskonfigurationsdatei**.  
  
    3.  Klicken Sie auf **Hinzufügen**.  
  
2.  Suchen Sie im `<source>`\-Abschnitt mit dem `name`\-Attribut "DefaultSource" \(innerhalb des `<sources>`\-Abschnitts\) den `<listeners>`\-Abschnitt.  Der `<sources>`\-Abschnitt befindet sich im `<system.diagnostics>`\-Abschnitt \(innerhalb des `<configuration>`\-Abschnitts auf der obersten Ebene\).  
  
3.  Fügen Sie dem `<listeners>`\-Abschnitt dieses Element hinzu:  
  
    ```  
    <add name="SimpleLog" />  
    ```  
  
4.  Suchen Sie den `<sharedListeners>`\-Abschnitt im `<system.diagnostics>`\-Abschnitt im `<configuration>`\-Abschnitt auf der obersten Ebene.  
  
5.  Fügen Sie diesem `<sharedListeners>`\-Abschnitt dieses Element hinzu:  
  
    ```  
    <add name="SimpleLog" type="SimpleLogStrongName" />  
    ```  
  
     Ändern Sie den Wert von `SimpleLogStrongName` in den starken Namen des Listeners.  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName>   
 [Arbeiten mit Anwendungsprotokollen](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)   
 [How to: Log Exceptions](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)   
 [Gewusst wie: Schreiben von Protokollmeldungen](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)   
 [Exemplarische Vorgehensweise: Ändern des Ortes, in den "My.Application.Log" Informationen schreibt](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)