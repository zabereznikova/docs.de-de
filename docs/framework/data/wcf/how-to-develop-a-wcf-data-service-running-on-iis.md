---
title: "Vorgehensweise: Entwickeln eines WCF-Datendiensts, der auf IIS ausgef&#252;hrt wird | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "WCF Data Services, Bereitstellen"
  - "WCF Data Services, Entwickeln"
  - "WCF Data Services, Hosting"
ms.assetid: f6f768c5-4989-49e3-a36f-896ab4ded86e
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Vorgehensweise: Entwickeln eines WCF-Datendiensts, der auf IIS ausgef&#252;hrt wird
In diesem Thema wird gezeigt, wie [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] zum Erstellen eines Datendiensts verwendet wird, der auf der Northwind\-Beispieldatenbank basiert, die von einer in Internetinformationsdienste \(ISS\) ausgeführten ASP.NET\-Webanwendung gehostet wird.  Ein Beispiel zum Erstellen desselben Northwind\-Datendiensts als ASP.NET\-Webanwendung, die auf dem ASP.NET Development Server ausgeführt wird, finden Sie unter [WCF Data Services\-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
> [!NOTE]
>  Um den Northwind\-Datendienst zu erstellen, muss die Northwind\-Beispieldatenbank auf dem lokalen Computer installiert sein.  Diese Beispieldatenbank kann von der Downloadseite [Beispieldatenbanken für SQL Server](http://go.microsoft.com/fwlink/?linkid=24758) heruntergeladen werden.  
  
 In diesem Thema wird gezeigt, wie ein Datendienst mithilfe des Entity Framework\-Anbieters erstellt wird.  Weitere Datendiensteanbieter sind verfügbar.  Weitere Informationen finden Sie unter [Datendiensteanbieter](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).  
  
 Nach dem Erstellen des Diensts, müssen Sie explizit den Zugriff auf Datendienstressourcen bereitstellen.  Weitere Informationen finden Sie unter [Vorgehensweise: Aktivieren des Zugriffs auf den Datendienst](../../../../docs/framework/data/wcf/how-to-enable-access-to-the-data-service-wcf-data-services.md).  
  
### So erstellen Sie die in IIS ausgeführte ASP.NET\-Webanwendung  
  
1.  Wählen Sie in Visual Studio im Menü **Datei** die Option **Neu** aus, und wählen Sie dann **Projekt** aus.  
  
2.  Wählen Sie im Dialogfeld **Neues Projekt** entweder Visual Basic oder Visual C\# als Programmiersprache aus.  
  
3.  Wählen Sie im Bereich **Vorlagen** die Option **ASP.NET\-Webanwendung** aus.  Hinweis: Wenn Sie Visual Studio Web Developer verwenden, müssen Sie anstelle einer neuen Webanwendung eine neue Website erstellen.  
  
4.  Geben Sie `NorthwindService` als Namen des Projekts ein.  
  
5.  Klicken Sie auf **OK**.  
  
6.  Wählen Sie im Menü **Projekt** die Option **NorthwindService\-Eigenschaften** aus.  
  
7.  Wählen Sie die Registerkarte **Web** und anschließend die Option **Lokalen IIS\-Webserver verwenden** aus.  
  
8.  Klicken Sie auf **Virtuelles Verzeichnis erstellen** und anschließend auf **OK**.  
  
9. Führen Sie an der Eingabeaufforderung mit Administratorrechten einen der folgenden Befehle aus \(je nach Betriebssystem\):  
  
    -   32\-Bit\-Systeme:  
  
        ```ms-dos  
        "%windir%\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i  
        ```  
  
    -   64\-Bit\-Systeme:  
  
        ```ms-dos  
        "%windir%\Microsoft.NET\Framework64\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i  
        ```  
  
     Hierdurch wird sichergestellt, dass Windows Communication Foundation \(WCF\) auf dem Computer registriert wird.  
  
10. Führen Sie an der Eingabeaufforderung mit Administratorrechten einen der folgenden Befehle aus \(je nach Betriebssystem\):  
  
    -   32\-Bit\-Systeme:  
  
        ```ms-dos  
        "%windir%\Microsoft.NET\Framework\v4.0.30319\aspnet_regiis.exe" -i -enable  
        ```  
  
    -   64\-Bit\-Systeme:  
  
        ```ms-dos  
        "%windir%\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe" -i -enable  
        ```  
  
     Dadurch wird sichergestellt, dass ISS ordnungsgemäß ausgeführt wird, nachdem WCF auf dem Computer installiert wurde.  Möglicherweise müssen Sie außerdem einen Neustart von IIS ausführen.  
  
11. Wenn die ASP.NET\-Anwendung in IIS7 ausgeführt wird, müssen Sie außerdem die folgenden Schritte ausführen:  
  
    1.  Öffnen Sie den ISS\-Manager, und navigieren Sie unter **Standardwebsite** zur Anwendung PhotoService.  
  
    2.  Doppelklicken Sie in der Ansicht **Features** auf **Authentifizierung**.  
  
    3.  Wählen Sie auf der Seite **Authentifizierung** die Option **Anonyme Authentifizierung** aus.  
  
    4.  Klicken Sie im Bereich **Aktionen** auf **Bearbeiten**, um den Sicherheitsprinzipal festzulegen, unter dem anonyme Benutzer eine Verbindung mit der Site herstellen.  
  
    5.  Wählen Sie im Dialogfeld **Anmeldeinformationen für anonyme Authentifizierung bearbeiten** die Option **Identität des Anwendungspools** aus.  
  
    > [!IMPORTANT]
    >  Wenn Sie das Netzwerkdienstkonto verwenden, gewähren Sie anonymen Benutzern alle Zugriffsrechte dieses Kontos für das interne Netzwerk.  
  
12. Führen Sie mit SQL Server Management Studio, dem SQLCMD\-Hilfsprogramm oder dem Transact\-SQL\-Editor in Visual Studio den folgenden Transact\-SQL\-Befehl für die Instanz von SQL Server aus, der die Northwind\-Datenbank angefügt ist:  
  
    ```sql  
    CREATE LOGIN [NT AUTHORITY\NETWORK SERVICE] FROM WINDOWS;  
    GO   
    ```  
  
     Dadurch wird in der SQL Server\-Instanz eine Anmeldung für das Windows\-Konto erstellt, das verwendet wurde, um IIS auszuführen.  Dies ermöglicht es IIS, eine Verbindung mit der SQL Server\-Instanz herzustellen.  
  
13. Führen Sie mit der angefügten Northwind\-Datenbank, die folgenden Transact\-SQL\-Befehle aus:  
  
    ```sql  
    USE Northwind  
    GO  
    CREATE USER [NT AUTHORITY\NETWORK SERVICE]   
    FOR LOGIN [NT AUTHORITY\NETWORK SERVICE] WITH DEFAULT_SCHEMA=[dbo];  
    GO  
    ALTER LOGIN [NT AUTHORITY\NETWORK SERVICE]   
    WITH DEFAULT_DATABASE=[Northwind];   
    GO  
    EXEC sp_addrolemember 'db_datareader', 'NT AUTHORITY\NETWORK SERVICE'  
    GO  
    EXEC sp_addrolemember 'db_datawriter', 'NT AUTHORITY\NETWORK SERVICE'  
    GO   
    ```  
  
     Hierdurch werden der neuen Anmeldung Rechte erteilt, die IIS den Lese\- und Schreibzugriff für Daten der Northwind\-Datenbank zu gewähren.  
  
### So definieren Sie das Datenmodell  
  
1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf den Namen des ASP.NET\-Projekts, und klicken Sie dann auf **Neues Element hinzufügen**.  
  
2.  Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **ADO.NET Entity Data Model** aus.  
  
3.  Geben Sie als Name des Datenmodells `Northwind.edmx` ein.  
  
4.  Wählen Sie im Assistent für Entity Data Model die Option **Aus Datenbank generieren** aus, und klicken Sie auf **Weiter**.  
  
5.  Verbinden Sie das Datenmodell mit der Datenbank, indem Sie einen der folgenden Schritte ausführen, und klicken Sie dann auf **Weiter**:  
  
    -   Wenn noch keine Datenbankverbindung konfiguriert wurde, klicken Sie auf **Neue Verbindung**, um eine neue Verbindung zu erstellen.  Weitere Informationen finden Sie unter [Gewusst wie: Erstellen von Verbindungen mit SQL Server\-Datenbanken](http://go.microsoft.com/fwlink/?LinkId=123631).  Dieser [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]\-Instanz muss die Northwind\-Beispieldatenbank angefügt worden sein.  
  
         \- oder \-  
  
    -   Wenn bereits eine Datenbankverbindung für die Northwind\-Datenbank konfiguriert wurde, wählen Sie diese Verbindung in der Liste der Verbindungen aus.  
  
6.  Aktivieren Sie auf der letzten Seite des Assistenten die Kontrollkästchen für alle Tabellen in der Datenbank, und deaktivieren Sie die Kontrollkästchen für Sichten und gespeicherte Prozeduren.  
  
7.  Klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen.  
  
    > [!NOTE]
    >  Das erstellte Datenmodell macht Fremdschlüsseleigenschaften von Entitätstypen verfügbar.  Mit Visual Studio 2008 erstellte Datenmodelle enthalten diese Fremdschlüsseleigenschaften nicht.  Aus diesem Grund müssen Sie die Clientdatendienstklassen jeglicher Clientanwendungen aktualisieren, die für den Zugriff auf den mit Visual Studio 2008 erstellten Northwind\-Datendienst erstellt wurden, bevor Sie auf diese Version des Northwind\-Datendiensts zugreifen.  
  
### So erstellen Sie den Datendienst  
  
1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf den Namen des ASP.NET\-Projekts, und klicken Sie dann auf **Neues Element hinzufügen**.  
  
2.  Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **ADO.NET Data Service** aus.  
  
3.  Geben Sie als Name des Diensts `Northwind` ein.  
  
     Visual Studio erstellt das XML\-Markup und die Codedateien für den neuen Dienst.  In der Standardeinstellung wird das Fenster des Code\-Editors geöffnet.  Im **Projektmappen\-Explorer** wird der Dienst mit dem Namen "Northwind" und der Erweiterung ".svc.cs" oder ".svc.vb" angezeigt.  
  
4.  Ersetzen Sie im Code für den Datendienst in der Definition der Klasse, die den Datendienst definiert, den Kommentar `/* TODO: put your data source class name here */` durch den Typ des Entitätscontainers des Datenmodells, in diesem Fall `NorthwindEntities`.  Die Klassendefinition sollte wie folgt aussehen:  
  
     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#servicedefinition)]  
  
## Siehe auch  
 [Verfügbarmachen der Daten als Dienst](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md)