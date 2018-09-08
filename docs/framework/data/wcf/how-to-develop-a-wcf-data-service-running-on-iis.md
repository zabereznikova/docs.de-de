---
title: 'Vorgehensweise: Entwickeln eines WCF-Datendiensts, der auf IIS ausgeführt wird'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, developing
- WCF Data Services, deploying
- WCF Data Services, hosting
ms.assetid: f6f768c5-4989-49e3-a36f-896ab4ded86e
ms.openlocfilehash: af81e65dfd4661d62d7aa4a3e6075be312765cb7
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44185440"
---
# <a name="how-to-develop-a-wcf-data-service-running-on-iis"></a>Vorgehensweise: Entwickeln von WCF Data Services auf IIS ausgeführt wird

In diesem Thema wird gezeigt, wie mit WCF Data Services einen Datendienst erstellen, der auf der Northwind-Beispieldatenbank basiert, die von einer ASP.NET-Webanwendung gehostet wird, die auf Internet Information Services (IIS) ausgeführt wird. Ein Beispiel zum gleichen Northwind-Datendienst als eine ASP.NET-Webanwendung erstellen, die auf ASP.NET Development Server ausgeführt wird, finden Sie die [WCF Data Services-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).

> [!NOTE]
> Um den Northwind-Datendienst zu erstellen, muss die Northwind-Beispieldatenbank auf dem lokalen Computer installiert sein. Diese Beispieldatenbank, finden Sie unter auf der Downloadseite des [Beispieldatenbanken für SQL Server](https://go.microsoft.com/fwlink/?linkid=24758).

 In diesem Thema wird gezeigt, wie ein Datendienst mithilfe des Entity Framework-Anbieters erstellt wird. Weitere Datendiensteanbieter sind verfügbar. Weitere Informationen finden Sie unter [Datendiensteanbieter](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).

 Nach dem Erstellen des Diensts, müssen Sie explizit den Zugriff auf Datendienstressourcen bereitstellen. Weitere Informationen finden Sie unter [Vorgehensweise: Aktivieren Sie den Zugriff auf den Datendienst](../../../../docs/framework/data/wcf/how-to-enable-access-to-the-data-service-wcf-data-services.md).

## <a name="create-the-aspnet-web-application-that-runs-on-iis"></a>Erstellen der ASP.NET-Webanwendung, die unter IIS ausgeführt wird.

1. In Visual Studio auf die **Datei** , wählen Sie im Menü **neu** > **Projekt**.

2. In der **neues Projekt** wählen Sie im Dialogfeld die **installiert** > [**Visual C#-** oder **Visual Basic**] > **Web** Kategorie.

3. Wählen Sie die **ASP.NET-Webanwendung** Vorlage.

1. Geben Sie `NorthwindService` als den Namen des Projekts.

5. Klicken Sie auf **OK**.

6. Auf der **Projekt** , wählen Sie im Menü **NorthwindService-Eigenschaften**.

7. Wählen Sie die **Web** Registerkarte, und wählen Sie dann **lokalen IIS-Webserver verwenden**.

8. Klicken Sie auf **virtuelles Verzeichnis erstellen** , und klicken Sie dann auf **OK**.

9. Führen Sie an der Eingabeaufforderung mit Administratorrechten einen der folgenden Befehle aus (je nach Betriebssystem):

    -   32-Bit-Systeme:

        ```console
        "%windir%\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i
        ```

    -   64-Bit-Systeme:

        ```console
        "%windir%\Microsoft.NET\Framework64\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i
        ```

     Hierdurch wird sichergestellt, dass Windows Communication Foundation (WCF) auf dem Computer registriert wird.

10. Führen Sie an der Eingabeaufforderung mit Administratorrechten einen der folgenden Befehle aus (je nach Betriebssystem):

    -   32-Bit-Systeme:

        ```console
        "%windir%\Microsoft.NET\Framework\v4.0.30319\aspnet_regiis.exe" -i -enable
        ```

    -   64-Bit-Systeme:

        ```console
        "%windir%\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe" -i -enable
        ```

     Dadurch wird sichergestellt, dass ISS ordnungsgemäß ausgeführt wird, nachdem WCF auf dem Computer installiert wurde. Möglicherweise müssen Sie außerdem einen Neustart von IIS ausführen.

11. Wenn die ASP.NET-Anwendung in IIS7 ausgeführt wird, müssen Sie außerdem die folgenden Schritte ausführen:

    1. Öffnen Sie IIS-Manager, und navigieren Sie zur Anwendung PhotoService unter **Default Web Site**.

    2. In **Ansicht "Features"**, doppelklicken Sie auf **Authentifizierung**.

    3. Auf der **Authentifizierung** Seite **anonyme Authentifizierung**.

    4. In der **Aktionen** Bereich, klicken Sie auf **bearbeiten** um den Sicherheitsprinzipal festzulegen, unter dem anonyme Benutzer der Website hergestellt wird.

    5. In der **Anmeldeinformationen für anonyme Authentifizierung bearbeiten** wählen Sie im Dialogfeld **Identität des Anwendungspools**.

    > [!IMPORTANT]
    > Wenn Sie das Netzwerkdienstkonto verwenden, gewähren Sie anonymen Benutzern alle Zugriffsrechte dieses Kontos für das interne Netzwerk.

12. Führen Sie mit SQL Server Management Studio, dem SQLCMD-Hilfsprogramm oder dem Transact-SQL-Editor in Visual Studio den folgenden Transact-SQL-Befehl für die Instanz von SQL Server aus, der die Northwind-Datenbank angefügt ist:

    ```sql
    CREATE LOGIN [NT AUTHORITY\NETWORK SERVICE] FROM WINDOWS;
    GO
    ```

    Dadurch wird in der SQL Server-Instanz eine Anmeldung für das Windows-Konto erstellt, das verwendet wurde, um IIS auszuführen. Dies ermöglicht es IIS, eine Verbindung mit der SQL Server-Instanz herzustellen.

13. Führen Sie mit der angefügten Northwind-Datenbank, die folgenden Transact-SQL-Befehle aus:

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

    Hierdurch werden der neuen Anmeldung Rechte erteilt, die IIS den Lese- und Schreibzugriff für Daten der Northwind-Datenbank zu gewähren.

## <a name="define-the-data-model"></a>Definieren des Datenmodells

1. In **Projektmappen-Explorer**mit der rechten Maustaste auf den Namen des ASP.NET-Projekts,, und klicken Sie dann auf **hinzufügen** > **neues Element**.

2. In der **neues Element hinzufügen** wählen Sie im Dialogfeld **ADO.NET Entity Data Model**.

3. Geben Sie den Namen des Datenmodells `Northwind.edmx`.

4. Wählen Sie in der Assistent für Entity Data Model **aus Datenbank generieren**, und klicken Sie dann auf **Weiter**.

5. Verbinden Sie das Datenmodell mit der Datenbank, indem er einen der folgenden Schritte aus, und klicken Sie dann auf **Weiter**:

    -   Wenn Sie keine datenbankverbindung, die bereits konfiguriert haben, klicken Sie auf **neue Verbindung** , und erstellen Sie eine neue Verbindung. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von Verbindungen mit SQL Server-Datenbanken](https://go.microsoft.com/fwlink/?LinkId=123631). Dieser SQL Server-Instanz muss die Northwind-Beispieldatenbank angefügt sein.

         \- oder –

    -   Wenn bereits eine Datenbankverbindung für die Northwind-Datenbank konfiguriert wurde, wählen Sie diese Verbindung in der Liste der Verbindungen aus.

6. Aktivieren Sie auf der letzten Seite des Assistenten die Kontrollkästchen für alle Tabellen in der Datenbank, und deaktivieren Sie die Kontrollkästchen für Sichten und gespeicherte Prozeduren.

7. Klicken Sie auf **Fertig stellen** um den Assistenten zu schließen.

## <a name="create-the-data-service"></a>Erstellen des Datendiensts

1. In **Projektmappen-Explorer**mit der rechten Maustaste auf den Namen des ASP.NET-Projekts,, und klicken Sie dann auf **hinzufügen** > **neues Element**.

2. In der **neues Element hinzufügen** wählen Sie im Dialogfeld **WCF Data Service**.

   ![WCF Data Service-Elementvorlage in Visual Studio 2015](media/wcf-data-service-item-template.png)

   > [!NOTE]
   > Die **WCF Data Service** Vorlage ist in Visual Studio 2015, aber nicht in Visual Studio 2017 verfügbar.

3. Geben Sie für den Namen des Diensts, `Northwind`.

     Visual Studio erstellt das XML-Markup und die Codedateien für den neuen Dienst. In der Standardeinstellung wird das Fenster des Code-Editors geöffnet. In **Projektmappen-Explorer**, der Dienst hat den Namen, Northwind und der Erweiterung. svc.cs oder. svc.vb.

4. Ersetzen Sie im Code für den Datendienst in der Definition der Klasse, die den Datendienst definiert, den Kommentar `/* TODO: put your data source class name here */` durch den Typ des Entitätscontainers des Datenmodells, in diesem Fall `NorthwindEntities`. Die Klassendefinition sollte wie folgt aussehen:

     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#servicedefinition)]

## <a name="see-also"></a>Siehe auch

- [Verfügbarmachen der Daten als Dienst](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md)
