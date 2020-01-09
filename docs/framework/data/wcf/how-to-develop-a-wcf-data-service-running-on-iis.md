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
ms.openlocfilehash: 5c75425783d3468ac42ef7cb32cd9c93e812192a
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75338350"
---
# <a name="how-to-develop-a-wcf-data-service-running-on-iis"></a>Vorgehensweise: Entwickeln eines WCF-Daten Dienstanbieter unter IIS

In diesem Thema wird gezeigt, wie WCF Data Services verwendet wird, um einen Datendienst zu erstellen, der auf der Northwind-Beispieldatenbank basiert, die von einer ASP.NET-Webanwendung gehostet wird, die auf Internetinformationsdienste (IIS) ausgeführt wird. Ein Beispiel für das Erstellen desselben Northwind-Daten Diensts als ASP.NET-Webanwendung, die auf dem ASP.NET Development Server ausgeführt wird, finden Sie im [WCF Data Services Schnellstart](quickstart-wcf-data-services.md).

> [!NOTE]
> Um den Northwind-Datendienst zu erstellen, muss die Northwind-Beispieldatenbank auf dem lokalen Computer installiert sein. Diese Beispieldatenbank kann von der Downloadseite [Beispieldatenbanken für SQL Server](https://go.microsoft.com/fwlink/?linkid=24758)heruntergeladen werden.

In diesem Thema wird gezeigt, wie ein Datendienst mithilfe des Entity Framework-Anbieters erstellt wird. Weitere Datendiensteanbieter sind verfügbar. Weitere Informationen finden Sie unter [Data Services-Anbietern](data-services-providers-wcf-data-services.md).

Nach dem Erstellen des Diensts, müssen Sie explizit den Zugriff auf Datendienstressourcen bereitstellen. Weitere Informationen finden Sie unter Gewusst [wie: Aktivieren des Zugriffs auf den Datendienst](how-to-enable-access-to-the-data-service-wcf-data-services.md).

## <a name="create-the-aspnet-web-application-that-runs-on-iis"></a>Erstellen der ASP.NET-Webanwendung, die unter IIS ausgeführt wird

1. Wählen Sie in Visual Studio im Menü **Datei** die Optionen **Neu** > **Projekt** aus.

2. Wählen Sie im Dialogfeld **Neues Projekt** die Kategorie **installierter** > **[ C# Visual** oder **Visual Basic**] > **Web** aus.

3. Wählen Sie die Vorlage **ASP.NET-Webanwendung** .

4. Geben Sie `NorthwindService` als Namen für das Projekt ein.

5. Klicken Sie auf **OK**.

6. Wählen Sie im Menü **Projekt** die Option **NorthwindService-Eigenschaften**aus.

7. Wählen Sie die Registerkarte **Web** aus, und wählen Sie dann **lokalen IIS-Webserver verwenden**aus.

8. Klicken Sie auf **virtuelles Verzeichnis erstellen** , und klicken Sie dann auf **OK**.

9. Führen Sie an der Eingabeaufforderung mit Administratorrechten einen der folgenden Befehle aus (je nach Betriebssystem):

    - 32-Bit-Systeme:

        ```console
        "%windir%\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i
        ```

    - 64-Bit-Systeme:

        ```console
        "%windir%\Microsoft.NET\Framework64\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i
        ```

     Hierdurch wird sichergestellt, dass Windows Communication Foundation (WCF) auf dem Computer registriert wird.

10. Führen Sie an der Eingabeaufforderung mit Administratorrechten einen der folgenden Befehle aus (je nach Betriebssystem):

    - 32-Bit-Systeme:

        ```console
        "%windir%\Microsoft.NET\Framework\v4.0.30319\aspnet_regiis.exe" -i -enable
        ```

    - 64-Bit-Systeme:

        ```console
        "%windir%\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe" -i -enable
        ```

     Dadurch wird sichergestellt, dass ISS ordnungsgemäß ausgeführt wird, nachdem WCF auf dem Computer installiert wurde. Möglicherweise müssen Sie außerdem einen Neustart von IIS ausführen.

11. Wenn die ASP.NET-Anwendung in IIS7 ausgeführt wird, müssen Sie außerdem die folgenden Schritte ausführen:

    1. Öffnen Sie den IIS-Manager, und navigieren Sie zur Anwendung "Photoservice" unter **Default Web Site**.

    2. Doppelklicken Sie in der Ansicht **Features** auf **Authentifizierung**.

    3. Wählen Sie auf der Seite **Authentifizierung** **Anonyme Authentifizierung**.

    4. Klicken Sie im Bereich **Aktionen** auf **Bearbeiten** , um den Sicherheits Prinzipal festzulegen, unter dem anonyme Benutzer eine Verbindung mit der Website herstellen.

    5. Wählen Sie im Dialogfeld Anmelde Informationen für **anonyme Authentifizierung bearbeiten** die Option **Anwendungs Pool Identität**aus.

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

1. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf den Namen des ASP.NET-Projekts, und klicken Sie dann auf > **Neues Element** **Hinzufügen** .

2. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **ADO.NET Entity Data Model**aus.

3. Geben Sie als Name des Datenmodells `Northwind.edmx`ein.

4. Wählen Sie im Assistenten für Entity Data Model die Option **aus Datenbank generieren aus**, und klicken Sie dann auf **weiter**.

5. Verbinden Sie das Datenmodell mit der Datenbank, indem Sie einen der folgenden Schritte ausführen, und klicken Sie dann auf **weiter**:

    - Wenn Sie noch keine Datenbankverbindung konfiguriert haben, klicken Sie auf **neue Verbindung** , und erstellen Sie eine neue Verbindung. Weitere Informationen finden Sie unter [How to: Create Connections to SQL Server Databases](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)). Dieser SQL Server-Instanz muss die Northwind-Beispieldatenbank angefügt sein.

         \- oder -

    - Wenn bereits eine Datenbankverbindung für die Northwind-Datenbank konfiguriert wurde, wählen Sie diese Verbindung in der Liste der Verbindungen aus.

6. Aktivieren Sie auf der letzten Seite des Assistenten die Kontrollkästchen für alle Tabellen in der Datenbank, und deaktivieren Sie die Kontrollkästchen für Sichten und gespeicherte Prozeduren.

7. Klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen.

## <a name="create-the-data-service"></a>Erstellen des Datendiensts

1. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf den Namen Ihres ASP.NET-Projekts, und klicken Sie dann auf > **Neues Element** **Hinzufügen** .

2. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **WCF Data Service**aus.

   ![WCF Data Service-Element Vorlage in Visual Studio 2015](./media/wcf-data-service-item-template.png)

   > [!NOTE]
   > Die **WCF Data Service** -Vorlage ist in Visual Studio 2015 verfügbar, aber nicht in Visual Studio 2017 oder höher.

3. Geben Sie `Northwind`als Namen für den Dienst ein.

     Visual Studio erstellt das XML-Markup und die Codedateien für den neuen Dienst. In der Standardeinstellung wird das Fenster des Code-Editors geöffnet. In **Projektmappen-Explorer**hat der Dienst den Namen "Northwind" und die Erweiterung ". svc.cs" oder ". svc. vb".

4. Ersetzen Sie im Code für den Datendienst in der Definition der Klasse, die den Datendienst definiert, den Kommentar `/* TODO: put your data source class name here */` durch den Typ des Entitätscontainers des Datenmodells, in diesem Fall `NorthwindEntities`. Die Klassendefinition sollte wie folgt aussehen:

     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

## <a name="see-also"></a>Siehe auch

- [Verfügbarmachen der Daten als Dienst](exposing-your-data-as-a-service-wcf-data-services.md)
