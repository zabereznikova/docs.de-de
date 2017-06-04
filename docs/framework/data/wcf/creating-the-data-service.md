---
title: "Erstellen des Datendiensts | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 34d1d971-5e18-4c22-9bf6-d3612e27ea59
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Erstellen des Datendiensts
In dieser Aufgabe erstellen Sie einen Beispieldatendienst, der mithilfe von [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] einen auf der Northwind\-Beispieldatenbank basierenden [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]\-Feed verfügbar macht. Die Aufgabe umfasst die folgenden grundlegenden Schritte:  
  
1.  Erstellen Sie eine [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Webanwendung.  
  
2.  Definieren Sie mit den [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)]\-Tools das Datenmodell.  
  
3.  Fügen Sie den Datendienst der Webanwendung hinzu.  
  
4.  Aktivieren Sie den Zugriff auf den Datendienst.  
  
> [!NOTE]
>  Die beim Durchführen dieser Aufgabe erstellte [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Webanwendung wird auf dem von [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] bereitgestellten [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Development Server ausgeführt.  [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Development Server unterstützt nur Zugriff vom lokalen Computer.  Um außerdem das Testen und die Problembehebung des Datendiensts während der Entwicklung zu vereinfachen, sollte die Anwendung, die den Datendienst hostet, möglicherweise mithilfe von Internetinformationsdienste \(IIS\) ausgeführt werden.  Weitere Informationen finden Sie unter [Vorgehensweise: Entwickeln eines WCF\-Datendiensts, der auf IIS ausgeführt wird](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md).  
  
### So erstellen Sie die ASP.NET\-Webanwendung  
  
1.  Wählen Sie in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] im Menü **Datei** die Option **Neu** aus, und klicken Sie dann auf **Projekt**.  
  
2.  Wählen Sie im Dialogfeld **Neues Projekt** unter [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] oder [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] die Vorlage **Web** und dann **ASP.NET\-Webanwendung** aus.  
  
    > [!NOTE]
    >  Wenn Sie [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] Web Developer verwenden, müssen Sie anstelle einer neuen Webanwendung eine neue Website erstellen.  
  
3.  Geben Sie `NorthwindService` als Namen des Projekts ein.  
  
4.  Klicken Sie auf **OK**.  
  
5.  \(Optional\) Geben Sie eine bestimmte Portnummer für die Webanwendung an.  Hinweis: Im weiteren Verlauf des Schnellstarts wird die Portnummer `12345` verwendet.  
  
    1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf den Namen des von Ihnen erstellten [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Projekts, und klicken Sie dann auf **Eigenschaften**.  
  
    2.  Wählen Sie die Registerkarte **Web** aus, und legen Sie den Wert des Textfelds **Bestimmter Anschluss** auf `12345` fest.  
  
### So definieren Sie das Datenmodell  
  
1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf den Namen des [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Projekts, und klicken Sie anschließend auf **Neues Element hinzufügen**.  
  
2.  Klicken Sie im Dialogfeld **Neues Element hinzufügen** auf die Vorlage **Daten**, und wählen Sie dann **ADO.NET Entity Data Model** aus.  
  
3.  Geben Sie als Name des Datenmodells `Northwind.edmx` ein.  
  
4.  Wählen Sie im Assistenten für [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] die Option **Aus Datenbank generieren** aus, und klicken Sie dann auf **Weiter**.  
  
5.  Verbinden Sie das Datenmodell mit der Datenbank, indem Sie einen der folgenden Schritte ausführen, und klicken Sie dann auf **Weiter**:  
  
    -   Wenn noch keine Datenbankverbindung konfiguriert wurde, klicken Sie auf **Neue Verbindung**, um eine neue Verbindung zu erstellen.  Weitere Informationen finden Sie unter [Gewusst wie: Erstellen von Verbindungen mit SQL Server\-Datenbanken](http://go.microsoft.com/fwlink/?LinkId=123631).  Dieser [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]\-Instanz muss die Northwind\-Beispieldatenbank angefügt worden sein.  
  
         \- oder \-  
  
    -   Wenn bereits eine Datenbankverbindung für die Northwind\-Datenbank konfiguriert wurde, wählen Sie diese Verbindung in der Liste der Verbindungen aus.  
  
6.  Aktivieren Sie auf der letzten Seite des Assistenten die Kontrollkästchen für alle Tabellen in der Datenbank, und deaktivieren Sie die Kontrollkästchen für Sichten und gespeicherte Prozeduren.  
  
7.  Klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen.  
  
    > [!NOTE]
    >  Das erstellte Datenmodell macht Fremdschlüsseleigenschaften von Entitätstypen verfügbar.  Mit [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 2008 erstellte Datenmodelle enthalten diese Fremdschlüsseleigenschaften nicht.  Aus diesem Grund müssen Sie die Clientdatendienstklassen jeglicher Clientanwendungen aktualisieren, die für den Zugriff auf den mit [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 2008 erstellten Northwind\-Datendienst erstellt wurden, bevor Sie auf diese Version des Northwind\-Datendiensts zugreifen.  
  
### So erstellen Sie den Datendienst  
  
1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf den Namen des [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Projekts, und klicken Sie dann auf **Neues Element hinzufügen**.  
  
2.  Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **WCF Data Service** aus.  
  
3.  Geben Sie als Name des Diensts `Northwind` ein.  
  
     [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]Visual Studio erstellt das XML\-Markup und die Codedateien für den neuen Dienst.  In der Standardeinstellung wird das Fenster des Code\-Editors geöffnet.  Im **Projektmappen\-Explorer** wird der Dienst mit dem Namen "Northwind" und der Erweiterung ".svc.cs" oder ".svc.vb" angezeigt.  
  
4.  Ersetzen Sie im Code für den Datendienst in der Definition der Klasse, die den Datendienst definiert, den Kommentar `/* TODO: put your data source class name here */` durch den Typ des Entitätscontainers des Datenmodells, in diesem Fall `NorthwindEntities`.  Die Klassendefinition sollte wie folgt aussehen:  
  
     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#servicedefinition)]  
  
### So aktivieren Sie den Zugriff auf Datendienstressourcen  
  
1.  Ersetzen Sie im Code für den Datendienst den Platzhaltercode in der `InitializeService`\-Funktion durch Folgendes:  
  
     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#allreadconfig)]  
  
     So können autorisierte Clients, Lese\- und Schreibzugriff auf Ressourcen für die angegebenen Entitätenmengen erhalten.  
  
    > [!NOTE]
    >  Jeder Client, der auf die [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Anwendung zugreifen kann, kann auch auf die vom Datendienst verfügbar gemachten Ressourcen zugreifen.  Sie sollten in einem Produktionsdatendienst auch die Anwendung selbst sichern, um nicht autorisierten Zugriff auf Ressourcen zu verhindern.  Weitere Informationen finden Sie unter [Sichern von WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).  
  
## Nächste Schritte  
 Sie haben erfolgreich einen neuen Datendienst erstellt, der einen auf der Northwind\-Beispieldatenbank basierenden [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-Feed verfügbar macht. Sie haben außerdem den Zugriff auf den Feed für Clients aktiviert, die über Berechtigungen für die [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Webanwendung verfügen.  Als Nächstes starten Sie den Datendienst aus [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] und greifen auf den [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-Feed zu, indem Sie über einen Webbrowser HTTP GET\-Anforderungen senden:  
  
 [Zugreifen auf den Dienst mit einem Webbrowser](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)  
  
## Siehe auch  
 [ADO.NET Entity Data Model  Tools](http://msdn.microsoft.com/de-de/91076853-0881-421b-837a-f582f36be527)