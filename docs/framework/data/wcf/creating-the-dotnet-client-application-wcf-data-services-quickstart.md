---
title: Erstellen der .NET Framework-Clientanwendung (WCF Data Services-Schnellstart)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 41ade767-eeab-437d-9121-9797e8fb8045
ms.openlocfilehash: 4beaba24e42b15ebc45ece6e5319a2b14df54ab6
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975382"
---
# <a name="creating-the-net-framework-client-application-wcf-data-services-quickstart"></a>Erstellen der .NET Framework-Clientanwendung (WCF Data Services-Schnellstart)

Dies ist die letzte Aufgabe des WCF Data Services Schnellstarts. In dieser Aufgabe fügen Sie der Projekt Mappe eine Konsolenanwendung hinzu, fügen dieser neuen Client Anwendung einen Verweis auf den Open Data Protocol-Feed (odata) hinzu und greifen mithilfe der generierten Client Datendienst Klassen und des Clients auf den odata-Feed aus der Client Anwendung zu. Bibliotheken.

> [!NOTE]
> Eine .NET Framework-basierte Clientanwendung ist für den Zugriff auf einen Datenfeed nicht erforderlich. Auf den Datendienst kann von jeder Anwendungs Komponente zugegriffen werden, die einen odata-Feed verwendet. Weitere Informationen finden Sie unter [Verwenden eines Daten Dienstanbieter in einer Client Anwendung](using-a-data-service-in-a-client-application-wcf-data-services.md).

## <a name="to-create-the-client-application-by-using-visual-studio"></a>So erstellen Sie die Clientanwendung mit Visual Studio

1. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf die Projekt Mappe, klicken Sie auf **Hinzufügen**und dann auf **Neues Projekt**.

2. Wählen Sie im linken Bereich **installierte** > [**Visual C#**  oder **Visual Basic**] > **Windows-Desktop**aus, und wählen Sie dann die Vorlage **WPF-App** aus.

3. Geben Sie `NorthwindClient` für den Projektnamen ein, und klicken Sie dann auf **OK**.

4. Öffnen Sie die Datei MainWindow.xaml, und ersetzen Sie den XAML-Code durch folgenden Code:

     [!code-xaml[Astoria Quickstart Client#Window1Xaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml#window1xaml)]

## <a name="to-add-a-data-service-reference-to-the-project"></a>So fügen Sie dem Projekt einen Datendienstverweis hinzu

1. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf das NorthwindClient-Projekt, klicken Sie auf > **Dienst Verweis** **Hinzufügen** , und klicken Sie dann auf **ermitteln**.

     Dadurch wird der Northwind-Datendienst angezeigt, den Sie in der ersten Aufgabe erstellt haben.

2. Geben Sie im Textfeld **Namespace** `Northwind`ein, und klicken Sie dann auf **OK**.

     Dadurch wird dem Projekt, das die zum Zugriff auf und zur Interaktion mit Datendienstressourcen als Objekte verwendeten Datenklassen enthält, eine neue Codedatei hinzugefügt. Die Datenklassen werden im Namespace `NorthwindClient.Northwind` erstellt.

## <a name="to-access-data-service-data-in-the-wpf-application"></a>So greifen Sie auf Datendienstdaten in der WPF-Anwendung zu

1. Klicken Sie in **Projektmappen-Explorer** unter **NorthwindClient**mit der rechten Maustaste auf das Projekt, und klicken Sie auf **Verweis hinzufügen**.

2. Klicken Sie im Dialogfeld **Verweis hinzufügen** auf die Registerkarte **.net** , wählen Sie die Assembly System. Data. Services. Client. dll aus, und klicken Sie dann auf **OK**.

3. Öffnen Sie in **Projektmappen-Explorer** unter **NorthwindClient**die Codepage für die Datei "MainWindow. XAML", und fügen Sie die folgende `using` Anweisung (`Imports` in Visual Basic) hinzu.

    [!code-csharp[Astoria Quickstart Client#Using](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_client/cs/window1.xaml.cs#using)]
    [!code-vb[Astoria Quickstart Client#Using](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml.vb#using)]

4. Fügen Sie den folgenden Code ein, der diesen Datendienst abfragt und das Ergebnis an eine <xref:System.Data.Services.Client.DataServiceCollection%601> in der `MainWindow`-Klasse bindet:

    > [!NOTE]
    > Sie müssen den Hostnamen `localhost:12345` durch den Server und den Anschluss ersetzen, der die Instanz des Northwind-Datendiensts hostet.

     [!code-csharp[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_client/cs/window1.xaml.cs#querycode)]
     [!code-vb[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml.vb#querycode)]

5. Fügen Sie den folgenden Code zum Speichern von Änderungen in der `MainWindow`-Klasse hinzu:

     [!code-csharp[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_client/cs/window1.xaml.cs#savechanges)]
     [!code-vb[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml.vb#savechanges)]

## <a name="to-build-and-run-the-northwindclient-application"></a>So erstellen Sie die NorthwindClient-Anwendung und führen sie aus

1. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf das NorthwindClient-Projekt, und wählen Sie **als Startprojekt festlegen**aus.

2. Drücken Sie **F5** , um die Anwendung zu starten.

     Die Projektmappe wird erstellt und die Clientanwendung wird gestartet. Daten werden vom Dienst angefordert und in der Konsole angezeigt.

3. Bearbeiten Sie einen Wert in der Spalte **Menge** des Datenrasters, und klicken Sie dann auf **Speichern**.

     Die Änderungen werden im Datendienst gespeichert.

    > [!NOTE]
    > In dieser Version der Anwendung NorthwindClient wird das Hinzufügen und Löschen von Entitäten nicht unterstützt.

## <a name="next-steps"></a>Nächste Schritte

Sie haben erfolgreich die Client Anwendung erstellt, die auf den Northwind-Beispiel-odata-Feed zugreift. Sie haben auch die WCF Data Services Schnellstart abgeschlossen!

Weitere Informationen zum Zugreifen auf einen odata-Feed aus einer .NET Framework-Anwendung finden Sie unter [WCF Data Services Client Library](wcf-data-services-client-library.md).

## <a name="see-also"></a>Siehe auch

- [Erste Schritte](getting-started-with-wcf-data-services.md)
- [Ressourcen](wcf-data-services-resources.md)
