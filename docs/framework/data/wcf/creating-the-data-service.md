---
title: Erstellen des Datendiensts
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 34d1d971-5e18-4c22-9bf6-d3612e27ea59
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 57e305fd8b03e8d46c1fdcb7dd551f32062a1009
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="creating-the-data-service"></a>Erstellen des Datendiensts
In dieser Aufgabe erstellen Sie einen beispieldatendienst, der verwendet [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] verfügbar machen eine [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] Feed, die auf die Beispieldatenbank Northwind basiert. Die Aufgabe umfasst die folgenden grundlegenden Schritte:  
  
1.  Erstellen Sie eine [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Webanwendung.  
  
2.  Definieren Sie mit den [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)]-Tools das Datenmodell.  
  
3.  Fügen Sie den Datendienst der Webanwendung hinzu.  
  
4.  Aktivieren Sie den Zugriff auf den Datendienst.  
  
> [!NOTE]
>  Die beim Durchführen dieser Aufgabe erstellte [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Webanwendung wird auf dem von [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] bereitgestellten [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] Development Server ausgeführt. [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Development Server unterstützt nur Zugriff vom lokalen Computer. Um außerdem das Testen und die Problembehebung des Datendiensts während der Entwicklung zu vereinfachen, sollte die Anwendung, die den Datendienst hostet, möglicherweise mithilfe von Internetinformationsdienste (IIS) ausgeführt werden. Weitere Informationen finden Sie unter [How to: Develop a WCF Data Service Running on IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md).  
  
### <a name="to-create-the-aspnet-web-application"></a>So erstellen Sie die ASP.NET-Webanwendung  
  
1.  In [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]auf die **Datei** klicken Sie im Menü **neu**, und wählen Sie dann **Projekt**.  
  
2.  In der **neues Projekt** im Dialogfeld unter entweder [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] oder [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] wählen Sie die **Web** Vorlage, und wählen Sie dann **ASP.NET-Webanwendung**.  
  
    > [!NOTE]
    >  Wenn Sie [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] Web Developer verwenden, müssen Sie anstelle einer neuen Webanwendung eine neue Website erstellen.  
  
3.  Typ `NorthwindService` als den Namen des Projekts.  
  
4.  Klicken Sie auf **OK**.  
  
5.  (Optional) Geben Sie eine bestimmte Portnummer für die Webanwendung an. Hinweis: Im weiteren Verlauf des Schnellstarts wird die Portnummer `12345` verwendet.  
  
    1.  In **Projektmappen-Explorer**, mit der rechten Maustaste in des Namens der [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Projekt, die Sie gerade erstellt haben, und klicken Sie dann auf **Eigenschaften**.  
  
    2.  Wählen Sie die **Web** Registerkarte, und legen Sie den Wert von der **bestimmten Port** Textfeld `12345`.  
  
### <a name="to-define-the-data-model"></a>So definieren Sie das Datenmodell  
  
1.  In **Projektmappen-Explorer**, mit der rechten Maustaste in des Namens der [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Projekt, und klicken Sie dann auf **neues Element hinzufügen.**  
  
2.  In der **neues Element hinzufügen** (Dialogfeld), klicken Sie auf die **Daten** Vorlage, und wählen Sie dann **ADO.NET Entity Data Model**.  
  
3.  Geben Sie für den Namen des Datenmodells, `Northwind.edmx`.  
  
4.  In der [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] -Assistenten die Option **aus Datenbank generieren**, und klicken Sie dann auf **Weiter**.  
  
5.  Das Datenmodell mit der Datenbank zu verbinden, indem Sie einen der folgenden Schritte aus, und klicken Sie dann auf **Weiter**:  
  
    -   Wenn Sie keine datenbankverbindung, die bereits konfiguriert haben, klicken Sie auf **neue Verbindung** und erstellen Sie eine neue Verbindung. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von Verbindungen mit SQL Server-Datenbanken](http://go.microsoft.com/fwlink/?LinkId=123631). Dieser [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]-Instanz muss die Northwind-Beispieldatenbank angefügt worden sein.  
  
         \- oder –  
  
    -   Wenn bereits eine Datenbankverbindung für die Northwind-Datenbank konfiguriert wurde, wählen Sie diese Verbindung in der Liste der Verbindungen aus.  
  
6.  Aktivieren Sie auf der letzten Seite des Assistenten die Kontrollkästchen für alle Tabellen in der Datenbank, und deaktivieren Sie die Kontrollkästchen für Sichten und gespeicherte Prozeduren.  
  
7.  Klicken Sie auf **Fertig stellen** um den Assistenten zu schließen.  
  
    > [!NOTE]
    >  Das erstellte Datenmodell macht Fremdschlüsseleigenschaften von Entitätstypen verfügbar. Mit [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 2008 erstellte Datenmodelle enthalten diese Fremdschlüsseleigenschaften nicht. Aus diesem Grund müssen Sie die Clientdatendienstklassen jeglicher Clientanwendungen aktualisieren, die für den Zugriff auf den mit [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 2008 erstellten Northwind-Datendienst erstellt wurden, bevor Sie auf diese Version des Northwind-Datendiensts zugreifen.  
  
### <a name="to-create-the-data-service"></a>So erstellen Sie den Datendienst  
  
1.  In **Projektmappen-Explorer**, mit der rechten Maustaste in des Namens Ihrer [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Projekt, und klicken Sie dann auf **neues Element hinzufügen**.  
  
2.  In der **neues Element hinzufügen** wählen Sie im Dialogfeld **WCF Data Service**.  
  
3.  Geben Sie den Namen des Diensts zu `Northwind`.  
  
     [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]Visual Studio erstellt das XML-Markup und die Codedateien für den neuen Dienst. In der Standardeinstellung wird das Fenster des Code-Editors geöffnet. In **Projektmappen-Explorer**, der Dienst müssen die Namen "Northwind", mit der Erweiterung. svc.cs oder. svc.vb.  
  
4.  Ersetzen Sie im Code für den Datendienst in der Definition der Klasse, die den Datendienst definiert, den Kommentar `/* TODO: put your data source class name here */` durch den Typ des Entitätscontainers des Datenmodells, in diesem Fall `NorthwindEntities`. Die Klassendefinition sollte wie folgt aussehen:  
  
     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#servicedefinition)]  
  
### <a name="to-enable-access-to-data-service-resources"></a>So aktivieren Sie den Zugriff auf Datendienstressourcen  
  
1.  Ersetzen Sie im Code für den Datendienst den Platzhaltercode in der `InitializeService`-Funktion durch Folgendes:  
  
     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#allreadconfig)]  
  
     So können autorisierte Clients, Lese- und Schreibzugriff auf Ressourcen für die angegebenen Entitätenmengen erhalten.  
  
    > [!NOTE]
    >  Jeder Client, der auf die [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Anwendung zugreifen kann, kann auch auf die vom Datendienst verfügbar gemachten Ressourcen zugreifen. Sie sollten in einem Produktionsdatendienst auch die Anwendung selbst sichern, um nicht autorisierten Zugriff auf Ressourcen zu verhindern. Weitere Informationen finden Sie unter [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).  
  
## <a name="next-steps"></a>Nächste Schritte  
 Einen neuer Datendienst, die verfügbar gemacht wurde erfolgreich erstellt ein [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] Feed, die auf die Beispieldatenbank Northwind, und Sie basiert aktiviert haben Zugriff auf den Feed für Clients, die über Berechtigungen verfügen, auf die [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Webanwendung. Als Nächstes starten Sie den Datendienst aus [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] und greifen Sie auf die [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed von einer HTTP-GET-Anforderungen über einen Webbrowser senden:  
  
 [Zugreifen auf den Dienst mit einem Webbrowser](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)  
  
## <a name="see-also"></a>Siehe auch  
 [ADO.NET Entity Data Model Tools (ADO.NET Entity Data Model-Tools)](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527)
