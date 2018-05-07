---
title: Erstellen der .NET Framework-Clientanwendung (WCF Data Services-Schnellstart)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 41ade767-eeab-437d-9121-9797e8fb8045
ms.openlocfilehash: 09981a7aee2db24d8464bbc7412b82a57ec8115b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="creating-the-net-framework-client-application-wcf-data-services-quickstart"></a>Erstellen der .NET Framework-Clientanwendung (WCF Data Services-Schnellstart)
Dies ist die letzte Aufgabe des der [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] Schnellstart. In dieser Aufgabe fügen Sie der Projektmappe eine Konsolenanwendung, fügen einen Verweis auf die [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] Zuführung in dieser neuen Clientanwendung und den Zugriff der [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed von der Clientanwendung mithilfe der generierten clientdatendienstklassen und Client Bibliotheken.  
  
> [!NOTE]
>  Eine .NET Framework-basierte Clientanwendung ist für den Zugriff auf einen Datenfeed nicht erforderlich. Auf den Datendienst kann jede Anwendungskomponente zugreifen, die einen [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Feed nutzt. Weitere Informationen finden Sie unter [Verwenden eines Datendiensts in einer Clientanwendung](../../../../docs/framework/data/wcf/using-a-data-service-in-a-client-application-wcf-data-services.md).  
  
### <a name="to-create-the-client-application-by-using-visual-studio"></a>So erstellen Sie die Clientanwendung mit Visual Studio  
  
1.  In **Projektmappen-Explorer**mit der rechten Maustaste auf die Projektmappe, klicken Sie auf **hinzufügen**, und klicken Sie dann auf **neues Projekt**.  
  
2.  In **-Projekttypen**, klicken Sie auf **Windows**, und wählen Sie dann **WPF-Anwendung** in der **Vorlagen** Bereich.  
  
3.  Geben Sie `NorthwindClient` für den Projektnamen, und klicken Sie dann auf **OK**.  
  
4.  Öffnen Sie die Datei MainWindow.xaml, und ersetzen Sie den XAML-Code durch folgenden Code:  
  
     [!code-xaml[Astoria Quickstart Client#Window1Xaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml#window1xaml)]  
  
### <a name="to-add-a-data-service-reference-to-the-project"></a>So fügen Sie dem Projekt einen Datendienstverweis hinzu  
  
1.  Maustaste auf das NorthwindClient-Projekt, klicken Sie auf **Hinzufügen eines Dienstverweises**, und klicken Sie dann auf **Discover**.  
  
     Dadurch wird der Northwind-Datendienst angezeigt, den Sie in der ersten Aufgabe erstellt haben.  
  
2.  In der **Namespace** Textfeld `Northwind`, und klicken Sie dann auf **OK**.  
  
     Dadurch wird dem Projekt, das die zum Zugriff auf und zur Interaktion mit Datendienstressourcen als Objekte verwendeten Datenklassen enthält, eine neue Codedatei hinzugefügt. Die Datenklassen werden im Namespace `NorthwindClient.Northwind` erstellt.  
  
### <a name="to-access-data-service-data-in-the-wpf-application"></a>So greifen Sie auf Datendienstdaten in der WPF-Anwendung zu  
  
1.  In **Projektmappen-Explorer** unter **NorthwindClient**mit der rechten Maustaste auf das Projekt, und klicken Sie auf **Verweis hinzufügen**.  
  
2.  Klicken Sie im Dialogfeld "Verweis hinzufügen" klicken Sie auf die **.NET** Registerkarte, wählen Sie die System.Data.Services.Client.dll-Assembly, und klicken Sie dann auf **OK**. In **Projektmappen-Explorer** unter **NorthwindClient**, öffnen Sie die Codepage für die Datei "MainWindow.xaml", und fügen Sie die folgenden `using` Anweisung (`Imports` in Visual Basic).  
  
     [!code-csharp[Astoria Quickstart Client#Using](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart client/cs/window1.xaml.cs#using)]
     [!code-vb[Astoria Quickstart Client#Using](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml.vb#using)]  
  
3.  Fügen Sie den folgenden Code ein, der diesen Datendienst abfragt und das Ergebnis an eine <xref:System.Data.Services.Client.DataServiceCollection%601> in der `MainWindow`-Klasse bindet:  
  
    > [!NOTE]
    >  Sie müssen den Hostnamen `localhost:12345` durch den Server und den Anschluss ersetzen, der die Instanz des Northwind-Datendiensts hostet.  
  
     [!code-csharp[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart client/cs/window1.xaml.cs#querycode)]
     [!code-vb[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml.vb#querycode)]  
  
4.  Fügen Sie den folgenden Code zum Speichern von Änderungen in der `MainWindow`-Klasse hinzu:  
  
     [!code-csharp[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart client/cs/window1.xaml.cs#savechanges)]
     [!code-vb[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml.vb#savechanges)]  
  
### <a name="to-build-and-run-the-northwindclient-application"></a>So erstellen Sie die NorthwindClient-Anwendung und führen sie aus  
  
1.  In **Projektmappen-Explorer**mit der rechten Maustaste auf das NorthwindClient-Projekt, und wählen Sie **als Startprojekt festlegen**.  
  
2.  Drücken Sie F5, um die Anwendung zu starten.  
  
     Die Projektmappe wird erstellt und die Clientanwendung wird gestartet. Daten werden vom Dienst angefordert und in der Konsole angezeigt.  
  
3.  Bearbeiten eines Werts in der **Menge** Spalte das Datenraster, und klicken Sie dann auf **speichern**.  
  
     Die Änderungen werden im Datendienst gespeichert.  
  
    > [!NOTE]
    >  In dieser Version der Anwendung NorthwindClient wird das Hinzufügen und Löschen von Entitäten nicht unterstützt.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Sie haben die Clientanwendung, die auf den Northwind [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Beispielfeed zugreift, erfolgreich erstellt. Der [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]-Schnellstart ist damit abgeschlossen. Weitere Informationen zum Zugreifen auf eine [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] Feeds aus einer [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Anwendung finden Sie unter [WCF Data Services-Clientbibliothek](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Erste Schritte](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)  
 [Ressourcen](../../../../docs/framework/data/wcf/wcf-data-services-resources.md)
