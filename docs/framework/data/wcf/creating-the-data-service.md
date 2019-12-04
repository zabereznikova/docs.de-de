---
title: Erstellen eines WCF Data Service in Visual Studio
ms.date: 08/24/2018
dev_langs:
- csharp
- vb
ms.assetid: 34d1d971-5e18-4c22-9bf6-d3612e27ea59
ms.openlocfilehash: 72e3b35465968674a20aa48262d3425a2190ff74
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802267"
---
# <a name="create-the-data-service"></a>Erstellen des Datendiensts

In diesem Thema erstellen Sie einen Beispiel Datendienst, der WCF Data Services verwendet, um einen Open Data Protocol-Feed (odata) verfügbar zu machen, der auf der Beispieldatenbank Northwind basiert. Die Aufgabe umfasst die folgenden grundlegenden Schritte:

1. Erstellen Sie eine ASP.NET-Webanwendung.

2. Definieren Sie das Datenmodell mit den Entity Data Model-Tools.

3. Fügen Sie den Datendienst der Webanwendung hinzu.

4. Aktivieren Sie den Zugriff auf den Datendienst.

## <a name="create-the-aspnet-web-app"></a>Erstellen der ASP.net-Web-App

1. Wählen Sie in Visual Studio im Menü **Datei** die Optionen **Neu** > **Projekt** aus.

1. Wählen Sie im Dialogfeld **Neues Projekt** unter entweder Visual Basic oder Visual C# die Kategorie **Web** aus, und wählen Sie dann **ASP.NET Webanwendung**aus.

1. Geben Sie `NorthwindService` als Namen für das Projekt ein, und klicken Sie dann auf **OK**.

1. Wählen Sie im Dialogfeld **neue ASP.NET Webanwendung** die Option **leer** aus, und klicken Sie dann auf **OK**.

1. (Optional) Geben Sie eine bestimmte Portnummer für die Webanwendung an. Hinweis: in dieser Reihe von Schnellstart Themen wird die Portnummer `12345` verwendet.

    1. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf das ASP.net-Projekt, das Sie gerade erstellt haben, und wählen Sie dann **Eigenschaften**aus.

    2. Wählen Sie die Registerkarte **Web** aus, und legen Sie den Wert des Textfelds **spezieller Port** auf `12345`fest.

## <a name="define-the-data-model"></a>Definieren des Datenmodells

1. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf den Namen des ASP.NET-Projekts, und klicken Sie dann auf > **Neues Element** **Hinzufügen** .

2. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Kategorie **Daten** aus, und wählen Sie dann **ADO.NET Entity Data Model**aus.

3. Geben Sie `Northwind.edmx`für den Namen des Datenmodells ein.

4. Wählen Sie im **Entity Data Model-Assistenten**die Option EF- **Designer aus Datenbank aus**, und klicken Sie dann auf **weiter**.

5. Verbinden Sie das Datenmodell mit der Datenbank, indem Sie einen der folgenden Schritte ausführen, und klicken Sie dann auf **weiter**:

    - Wenn Sie noch keine Datenbankverbindung konfiguriert haben, klicken Sie auf **neue Verbindung** , und erstellen Sie eine neue Verbindung. Weitere Informationen finden Sie unter [How to: Create Connections to SQL Server Databases](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)). Dieser SQL Server-Instanz muss die Northwind-Beispieldatenbank angefügt sein.

         \- oder -

    - Wenn bereits eine Datenbankverbindung für die Northwind-Datenbank konfiguriert wurde, wählen Sie diese Verbindung in der Liste der Verbindungen aus.

6. Aktivieren Sie auf der letzten Seite des Assistenten die Kontrollkästchen für alle Tabellen in der Datenbank, und deaktivieren Sie die Kontrollkästchen für Sichten und gespeicherte Prozeduren.

7. Klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen.

## <a name="create-the-wcf-data-service"></a>Erstellen des WCF-Daten Dienstanbieter

1. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt ASP.net, und wählen Sie dann > **Neues Element** **Hinzufügen** aus.

2. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Element Vorlage **WCF-Datendienst** aus der Kategorie **Web** aus.

   ![WCF Data Service-Element Vorlage in Visual Studio 2015](./media/wcf-data-service-item-template.png)

   > [!NOTE]
   > Die **WCF Data Service** -Vorlage ist in Visual Studio 2015 verfügbar, aber nicht in Visual Studio 2017 oder höher.

3. Geben Sie `Northwind`als Namen für den Dienst ein.

     Visual Studio erstellt das XML-Markup und die Codedateien für den neuen Dienst. In der Standardeinstellung wird das Fenster des Code-Editors geöffnet. In **Projektmappen-Explorer**hat der Dienst den Namen "Northwind" mit der Erweiterung " *. svc.cs* " oder " *. svc. vb*".

4. Ersetzen Sie im Code für den Datendienst in der Definition der Klasse, die den Datendienst definiert, den Kommentar `/* TODO: put your data source class name here */` durch den Typ des Entitätscontainers des Datenmodells, in diesem Fall `NorthwindEntities`. Die Klassendefinition sollte wie folgt aussehen:

     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

## <a name="enable-access-to-data-service-resources"></a>Aktivieren des Zugriffs auf Datendienst Ressourcen

1. Ersetzen Sie im Code für den Datendienst den Platzhaltercode in der `InitializeService`-Funktion durch Folgendes:

     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#allreadconfig)]

     So können autorisierte Clients, Lese- und Schreibzugriff auf Ressourcen für die angegebenen Entitätenmengen erhalten.

    > [!NOTE]
    > Jeder Client, der auf die ASP.NET-Anwendung zugreifen kann, kann auch auf die vom Datendienst verfügbar gemachten Ressourcen zugreifen. Sie sollten in einem Produktionsdatendienst auch die Anwendung selbst sichern, um nicht autorisierten Zugriff auf Ressourcen zu verhindern. Weitere Informationen finden Sie unter [Securing WCF Data Services](securing-wcf-data-services.md).

## <a name="next-steps"></a>Nächste Schritte

Sie haben erfolgreich einen neuen Datendienst erstellt, der einen auf der Northwind-Beispieldatenbank basierenden odata-Feed verfügbar macht. Sie haben den Zugriff auf den Feed für Clients aktiviert, die über Berechtigungen für die ASP.NET-Webanwendung verfügen. Als nächstes starten Sie den Datendienst aus Visual Studio und greifen auf den odata-Feed zu, indem Sie HTTP GET-Anforderungen über einen Webbrowser senden:

> [!div class="nextstepaction"]
> [Zugreifen auf den Dienst über einen Webbrowser](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

## <a name="see-also"></a>Siehe auch

- [ADO.NET-Entity Data Model Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
