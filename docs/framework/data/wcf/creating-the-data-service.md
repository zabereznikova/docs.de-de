---
title: Erstellen Sie einen WCF-Datendienst in Visual Studio
ms.date: 08/24/2018
dev_langs:
- csharp
- vb
ms.assetid: 34d1d971-5e18-4c22-9bf6-d3612e27ea59
ms.openlocfilehash: e04f64338eaa87755510a84e7c84773c7fede807
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634665"
---
# <a name="create-the-data-service"></a>Erstellen des Datendiensts

In diesem Thema erstellen Sie einen beispieldatendienst, der WCF Data Services verwendet, um verfügbar zu machen eine [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] -Feed, der auf die Beispieldatenbank Northwind basiert. Die Aufgabe umfasst die folgenden grundlegenden Schritte:

1. Erstellen Sie eine ASP.NET-Webanwendung.

2. Definieren Sie das Datenmodell mit den Entity Data Model-Tools.

3. Fügen Sie den Datendienst der Webanwendung hinzu.

4. Aktivieren Sie den Zugriff auf den Datendienst.

## <a name="create-the-aspnet-web-app"></a>Die ASP.NET Web-app erstellen

1. In Visual Studio auf die **Datei** , wählen Sie im Menü **neu** > **Projekt**.

1. In der **neues Projekt** im Dialogfeld unter Visual Basic oder Visual C#-Option der **Web** Kategorie, und wählen Sie dann **ASP.NET-Webanwendung**.

1. Geben Sie `NorthwindService` als Namen für das Projekt und wählen Sie dann **OK**.

1. In der **neue ASP.NET-Webanwendung** wählen Sie im Dialogfeld **leere** und wählen Sie dann **OK**.

1. (Optional) Geben Sie eine bestimmte Portnummer für die Webanwendung an. Hinweis: die Nummer des Ports `12345` wird in dieser Reihe von schnellstartthemen verwendet.

    1. In **Projektmappen-Explorer**mit der rechten Maustaste auf das ASP.NET-Projekt, die Sie gerade erstellt haben, und wählen Sie dann **Eigenschaften**.

    2. Wählen Sie die **Web** Registerkarte, und legen Sie den Wert des der **bestimmten Port** Textfeld `12345`.

## <a name="define-the-data-model"></a>Definieren des Datenmodells

1. In **Projektmappen-Explorer**mit der rechten Maustaste auf den Namen des ASP.NET-Projekts,, und klicken Sie dann auf **hinzufügen** > **neues Element**.

2. In der **neues Element hinzufügen** wählen Sie im Dialogfeld die **Daten** Kategorie, und wählen Sie dann **ADO.NET Entity Data Model**.

3. Geben Sie den Namen des Datenmodells `Northwind.edmx`.

4. In der **Entity Data Model-Assistenten**Option **EF Designer aus Datenbank**, und klicken Sie dann auf **Weiter**.

5. Verbinden Sie das Datenmodell mit der Datenbank, indem er einen der folgenden Schritte aus, und klicken Sie dann auf **Weiter**:

    - Wenn Sie eine datenbankverbindung, die bereits konfiguriert haben, klicken Sie auf **neue Verbindung** , und erstellen Sie eine neue Verbindung. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von Verbindungen zu SQL Server-Datenbanken](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)). Dieser SQL Server-Instanz muss die Northwind-Beispieldatenbank angefügt sein.

         \- oder –

    - Wenn bereits eine Datenbankverbindung für die Northwind-Datenbank konfiguriert wurde, wählen Sie diese Verbindung in der Liste der Verbindungen aus.

6. Aktivieren Sie auf der letzten Seite des Assistenten die Kontrollkästchen für alle Tabellen in der Datenbank, und deaktivieren Sie die Kontrollkästchen für Sichten und gespeicherte Prozeduren.

7. Klicken Sie auf **Fertig stellen** um den Assistenten zu schließen.

## <a name="create-the-wcf-data-service"></a>Erstellen von WCF Data service

1. In **Projektmappen-Explorer**mit der rechten Maustaste auf das ASP.NET-Projekt, und wählen Sie dann **hinzufügen** > **neues Element**.

2. In der **neues Element hinzufügen** wählen Sie im Dialogfeld die **WCF Data Service** Item-Vorlage aus der **Web** Kategorie.

   ![WCF Data Service-Elementvorlage in Visual Studio 2015](media/wcf-data-service-item-template.png)

   > [!NOTE]
   > Die **WCF Data Service** Vorlage ist in Visual Studio 2015, aber nicht in Visual Studio 2017 verfügbar.

3. Geben Sie den Namen des Diensts zu `Northwind`.

     Visual Studio erstellt das XML-Markup und die Codedateien für den neuen Dienst. In der Standardeinstellung wird das Fenster des Code-Editors geöffnet. In **Projektmappen-Explorer**, der Dienst hat den Namen "Northwind" mit der Erweiterung *. svc.cs* oder *. svc.vb*.

4. Ersetzen Sie im Code für den Datendienst in der Definition der Klasse, die den Datendienst definiert, den Kommentar `/* TODO: put your data source class name here */` durch den Typ des Entitätscontainers des Datenmodells, in diesem Fall `NorthwindEntities`. Die Klassendefinition sollte wie folgt aussehen:

     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

## <a name="enable-access-to-data-service-resources"></a>Aktivieren des Zugriffs auf datendienstressourcen

1. Ersetzen Sie im Code für den Datendienst den Platzhaltercode in der `InitializeService`-Funktion durch Folgendes:

     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#allreadconfig)]

     So können autorisierte Clients, Lese- und Schreibzugriff auf Ressourcen für die angegebenen Entitätenmengen erhalten.

    > [!NOTE]
    > Jeder Client, der auf die ASP.NET-Anwendung zugreifen kann, kann auch auf die vom Datendienst verfügbar gemachten Ressourcen zugreifen. Sie sollten in einem Produktionsdatendienst auch die Anwendung selbst sichern, um nicht autorisierten Zugriff auf Ressourcen zu verhindern. Weitere Informationen finden Sie unter [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).

## <a name="next-steps"></a>Nächste Schritte

Sie haben erfolgreich einen neuen Datendienst, der einen OData-feed verfügbar macht, die auf der Northwind-Beispieldatenbank basiert, und Sie Zugriff auf den Feed für Clients, die Berechtigungen für die ASP.NET-Webanwendung verfügen aktiviert haben. Sie werden als Nächstes starten den Datendienst aus Visual Studio und Zugriff auf den OData-feed, die durch das Senden von HTTP GET-Anforderungen über einen Webbrowser:

> [!div class="nextstepaction"]
> [Auf den Dienst über einen Webbrowser zugreifen.](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

## <a name="see-also"></a>Siehe auch

- [ADO.NET Entity Data Model-Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
