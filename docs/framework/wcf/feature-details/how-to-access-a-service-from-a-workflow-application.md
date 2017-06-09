---
title: "Vorgehensweise: Zugreifen auf einen Dienst aus einer Workflowanwendung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 925ef8ea-5550-4c9d-bb7b-209e20c280ad
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Vorgehensweise: Zugreifen auf einen Dienst aus einer Workflowanwendung
In diesem Thema wird beschrieben, wie Sie einen Workflowdienst in einer Workflowkonsolenanwendung aufrufen.Das Thema baut auf dem Thema [Vorgehensweise: Erstellen eines Workflowdiensts mit Messagingaktivitäten](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md) auf, das vorher abgeschlossen werden muss.Obwohl in diesem Thema beschrieben wird, wie Sie einen Workflowdienst aus einer Workflowanwendung aufrufen, können Sie die gleichen Methoden auch verwenden, um beliebige andere [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Dienste aus einer Workflowanwendung aufzurufen.  
  
### Erstellen eines Workflowkonsolen\-Anwendungsprojekts  
  
1.  Starten Sie [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Laden Sie das MyWFService\-Projekt, das Sie im Thema [Vorgehensweise: Erstellen eines Workflowdiensts mit Messagingaktivitäten](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md) erstellt haben.  
  
3.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf die Projektmappe **MyWFService**, und wählen Sie dann **Hinzufügen** und **Neues Projekt** aus.Wählen Sie unter **Installierte Vorlagen** die Option **Workflow** und aus der Liste der Projekttypen die Option **Konsolenanwendung für Workflows** aus.Geben Sie dem Projekt den Namen "MyWFClient", und verwenden Sie wie in der folgenden Abbildung gezeigt den Standardspeicherort.  
  
     ![Dialogfeld "Neues Projekt hinzufügen"](../../../../docs/framework/wcf/feature-details/media/addnewprojectdlg.JPG "AddNewProjectDlg")  
  
     Klicken Sie auf die Schaltfläche **OK**, um das Dialogfeld **Neues Projekt hinzufügen** zu schließen.  
  
4.  Nachdem das Projekt erstellt wurde, wird die Datei "Workflow1.xaml" im Designer geöffnet.Klicken Sie auf die Registerkarte **Toolbox**, um die Toolbox zu öffnen, falls diese nicht bereits geöffnet ist. Klicken Sie anschließend auf das Pinsymbol, damit das Fenster geöffnet bleibt.  
  
5.  Drücken Sie STRG\+F5, um den Dienst zu erstellen und zu starten.Wie zuvor auch, wird der ASP.NET Development Server gestartet, und Internet Explorer zeigt die WCF\-Hilfeseite an.Merken Sie sich den URI für diese Seite, da Sie diesen im nächsten Schritt verwenden.  
  
     ![IE mit Hilfeseite und URI für WCF](../../../../docs/framework/wcf/feature-details/media/iewcfhelppagewuri.JPG "IEWCFHelpPageWURI")  
  
6.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf das Projekt **MyWFClient**, und wählen Sie **Dienstverweis hinzufügen** aus.Klicken Sie auf die Schaltfläche **Ermitteln**, um die aktuelle Projektmappe nach Diensten zu suchen.Klicken Sie in der Liste "Dienste" auf das Dreieck neben der Datei "Service1.xamlx".Klicken Sie auf das Dreieck neben "Service1", um die vom Dienst "Service1" implementierten Verträge aufzuführen.Erweitern Sie in der Liste **Dienste** den Knoten **Service1**.Der Echo\-Vorgang wird wie in der folgenden Abbildung dargestellt in der Liste **Vorgänge** angezeigt.  
  
     ![Dialogfeld "Dienstverweis hinzufügen"](../../../../docs/framework/wcf/feature-details/media/addservicereference.JPG "AddServiceReference")  
  
     Behalten Sie den Standardnamespace bei, und klicken Sie auf **OK**, um das Dialogfeld **Dienstverweis hinzufügen** zu schließen.Das folgende Dialogfeld wird angezeigt.  
  
     ![Das Benachrichtigungsdialogfeld "Dienstverweis hinzufügen"](../../../../docs/framework/wcf/feature-details/media/asrdlg.JPG "ASRDlg")  
  
     Klicken Sie auf **OK**, um das Dialogfeld zu schließen.Drücken Sie dann STRG\+UMSCHALT\+B, um die Projektmappe zu erstellen.Beachten Sie, dass der Toolbox ein neuer Abschnitt mit dem Namen **MyWFClient.ServiceReference1.Activities** hinzugefügt wurde.Erweitern Sie diesen Abschnitt, und beachten Sie die Echo\-Aktivität, die wie in der folgenden Abbildung dargestellt hinzugefügt wurde.  
  
     ![Echoaktivität in der Toolbox](../../../../docs/framework/wcf/feature-details/media/echoactivity.JPG "EchoActivity")  
  
7.  Ziehen Sie eine <xref:System.ServiceModel.Activities.Sequence>\-Aktivität auf die Designeroberfläche.Diese befindet sich in der Toolbox im Abschnitt **Ablaufsteuerung**.  
  
8.  Klicken Sie bei aktivierter <xref:System.ServiceModel.Activities.Sequence>\-Aktivität auf den Link **Variablen**, und fügen Sie eine Zeichenfolgenvariable mit dem Namen `inString` hinzu.Geben Sie der Variable den Standardwert `"Hello, world"`, und fügen Sie ihr die Zeichenfolgenvariable mit dem Namen `outString` hinzu. Dies ist im folgenden Diagramm dargestellt.  
  
     ![Hinzufügen einer Variable](../../../../docs/framework/wcf/feature-details/media/instringvar.JPG "inStringVar")  
  
9. Ziehen Sie eine **Echo**\-Aktivität auf das <xref:System.ServiceModel.Activities.Sequence>\-Objekt.Binden Sie das "\_string"\-Argument im Eigenschaftenfenster an die `inString`\-Variable und das `out_string`\-Argument an die "outString"\-Variable, wie in der folgenden Abbildung dargestellt.Dadurch wird der Wert der `inString`\-Variable an den Vorgang übergeben und anschließend der Rückgabewert in die `outString`\-Variable eingefügt.  
  
     ![Binden von Argumenten an Variablen](../../../../docs/framework/wcf/feature-details/media/argumentbind.JPG "ArgumentBind")  
  
10. Legen Sie eine **WriteLine**\-Aktivität per Drag & Drop  unter der **Echo**\-Aktivität ab, um die vom Dienstaufruf zurückgegebene Zeichenfolge anzuzeigen.Die **WriteLine**\-Aktivität befindet sich in der Toolbox im Knoten **Primitive**.Binden Sie das **Text**\-Argument der **WriteLine**\-Aktivität an die `outString`\-Variable, indem Sie in das Textfeld der **WriteLine**\-Aktivität den Text `outString` eingeben.Der Workflow sollte jetzt wie die folgende Abbildung aussehen.  
  
     ![Der gesamte Clientworkflow](../../../../docs/framework/wcf/feature-details/media/completeclientwf.JPG "CompleteClientWF")  
  
11. Klicken Sie mit der rechten Maustaste auf die Projektmappe "MyWFService", und wählen Sie **Startprojekte festlegen...** aus.Aktivieren Sie das Optionsfeld **Mehrere Startprojekte**, und wählen Sie in der Spalte **Aktion** für jedes Projekt **Start** aus. Dies ist in der folgenden Abbildung dargestellt.  
  
     ![Optionen des Startobjekts](../../../../docs/framework/wcf/feature-details/media/startupprojects.JPG "StartupProjects")  
  
12. Drücken Sie STRG\+F5, um sowohl den Dienst als auch den Client zu starten.Der ASP.NET Development Server hostet den Dienst, Internet Explorer zeigt die WCF\-Hilfeseite an, und die Clientworkflowanwendung wird in einem Konsolenfenster gestartet und zeigt die vom Dienst zurückgegebene Zeichenfolge \("Hello, world"\) an.  
  
## Siehe auch  
 [Workflowdienste](../../../../docs/framework/wcf/feature-details/workflow-services.md)   
 [Vorgehensweise: Erstellen eines Workflowdiensts mit Messagingaktivitäten](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md)   
 [Verwenden eines WCF\-Diensts von einem Workflow in einem Webprojekt](http://go.microsoft.com/fwlink/?LinkId=207725)