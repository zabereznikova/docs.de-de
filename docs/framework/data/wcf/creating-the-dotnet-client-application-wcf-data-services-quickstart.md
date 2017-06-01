---
title: "Erstellen der .NET Framework-Clientanwendung (WCF Data Services-Schnellstart) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 41ade767-eeab-437d-9121-9797e8fb8045
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Erstellen der .NET Framework-Clientanwendung (WCF Data Services-Schnellstart)
Dies ist die letzte Aufgabe des [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]\-Schnellstarts.  In dieser Aufgabe fügen Sie der Projektmappe eine Konsolenanwendung hinzu, fügen dieser neuen Clientanwendung einen Verweis auf den [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]\-Feed hinzu und greifen aus der Clientanwendung mit den generierten Clientdatendienstklassen und Clientbibliotheken auf den [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-Feed zu.  
  
> [!NOTE]
>  Eine .NET Framework\-basierte Clientanwendung ist für den Zugriff auf einen Datenfeed nicht erforderlich.  Auf den Datendienst kann jede Anwendungskomponente zugreifen, die einen [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-Feed nutzt.  Weitere Informationen finden Sie unter [Verwenden eines Datendiensts in einer Clientanwendung](../../../../docs/framework/data/wcf/using-a-data-service-in-a-client-application-wcf-data-services.md).  
  
### So erstellen Sie die Clientanwendung mit Visual Studio  
  
1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf die Projektmappe, klicken Sie auf **Hinzufügen** und dann auf **Neues Projekt**.  
  
2.  Klicken Sie in **Projekttypen** auf **Windows**, und wählen Sie dann im Bereich **Vorlagen** die Option **WPF\-Anwendung** aus.  
  
3.  Geben Sie `NorthwindClient` als Projektnamen ein, und klicken Sie dann auf **OK**.  
  
4.  Öffnen Sie die Datei MainWindow.xaml, und ersetzen Sie den XAML\-Code durch folgenden Code:  
  
     [!code-xml[Astoria Quickstart Client#Window1Xaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml#window1xaml)]  
  
### So fügen Sie dem Projekt einen Datendienstverweis hinzu  
  
1.  Klicken Sie mit der rechten Maustaste auf das NorthwindClient\-Projekt, klicken Sie auf **Dienstverweis hinzufügen** und dann auf **Ermitteln**.  
  
     Dadurch wird der Northwind\-Datendienst angezeigt, den Sie in der ersten Aufgabe erstellt haben.  
  
2.  Geben Sie im Textfeld **Namespace** `Northwind` ein, und klicken Sie auf **OK**.  
  
     Dadurch wird dem Projekt, das die zum Zugriff auf und zur Interaktion mit Datendienstressourcen als Objekte verwendeten Datenklassen enthält, eine neue Codedatei hinzugefügt.  Die Datenklassen werden im Namespace `NorthwindClient.Northwind` erstellt.  
  
### So greifen Sie auf Datendienstdaten in der WPF\-Anwendung zu  
  
1.  Klicken Sie im **Projektmappen\-Explorer** unter **NorthwindClient** mit der rechten Maustaste auf das Projekt, und klicken Sie dann auf **Verweis hinzufügen**.  
  
2.  Wählen Sie im Dialogfeld "Verweis hinzufügen" auf der Registerkarte **.NET** die System.Data.Services.Client.dll\-Assembly aus, und klicken Sie anschließend auf **OK**.  Öffnen Sie im **Projektmappen\-Explorer** unter **NorthwindClient** die Codepage für die Datei MainWindow.xaml, und fügen Sie die folgende `using`\-Anweisung \(`Imports` in Visual Basic\) hinzu.  
  
     [!code-csharp[Astoria Quickstart Client#Using](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart client/cs/window1.xaml.cs#using)]
     [!code-vb[Astoria Quickstart Client#Using](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml.vb#using)]  
  
3.  Fügen Sie den folgenden Code ein, der diesen Datendienst abfragt und das Ergebnis an eine <xref:System.Data.Services.Client.DataServiceCollection%601> in der `MainWindow`\-Klasse bindet:  
  
    > [!NOTE]
    >  Sie müssen den Hostnamen `localhost:12345` durch den Server und den Anschluss ersetzen, der die Instanz des Northwind\-Datendiensts hostet.  
  
     [!code-csharp[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart client/cs/window1.xaml.cs#querycode)]
     [!code-vb[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml.vb#querycode)]  
  
4.  Fügen Sie den folgenden Code zum Speichern von Änderungen in der `MainWindow`\-Klasse hinzu:  
  
     [!code-csharp[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart client/cs/window1.xaml.cs#savechanges)]
     [!code-vb[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml.vb#savechanges)]  
  
### So erstellen Sie die NorthwindClient\-Anwendung und führen sie aus  
  
1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf das NorthwindClient\-Projekt, und wählen Sie **Als Startprojekt festlegen** aus.  
  
2.  Drücken Sie F5, um die Anwendung zu starten.  
  
     Die Projektmappe wird erstellt und die Clientanwendung wird gestartet.  Daten werden vom Dienst angefordert und in der Konsole angezeigt.  
  
3.  Bearbeiten Sie in der Spalte **Quantity** des Datenrasters einen Wert, und klicken Sie dann auf **Speichern**.  
  
     Die Änderungen werden im Datendienst gespeichert.  
  
    > [!NOTE]
    >  In dieser Version der Anwendung NorthwindClient wird das Hinzufügen und Löschen von Entitäten nicht unterstützt.  
  
## Nächste Schritte  
 Sie haben die Clientanwendung, die auf den Northwind [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-Beispielfeed zugreift, erfolgreich erstellt.  Der [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]\-Schnellstart ist damit abgeschlossen.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zum Zugreifen auf einen [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-Feed in einer [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Anwendung finden Sie unter [WCF Data Services\-Clientbibliothek](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md).  
  
## Siehe auch  
 [Erste Schritte](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)   
 [Ressourcen](../../../../docs/framework/data/wcf/wcf-data-services-resources.md)