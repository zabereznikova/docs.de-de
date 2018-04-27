---
title: 'Gewusst wie: Erstellen eines Datendiensts mit einer ADO.NET-Entity Framework-Datenquelle (WCF Data Services)'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF Data Services, providers
- WCF Data Services, Entity Framework
ms.assetid: 6d11fec8-0108-42f5-8719-2a7866d04428
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5993837546b28742756ed4a5ec323e6f1a5ef782
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-a-data-service-using-an-adonet-entity-framework-data-source-wcf-data-services"></a>Gewusst wie: Erstellen eines Datendiensts mit einer ADO.NET-Entity Framework-Datenquelle (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] macht Entitätsdaten als Datendienst verfügbar. Diese Entitätsdaten erfolgt durch die [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] Wenn die Datenquelle eine relationale Datenbank ist. Dieses Thema veranschaulicht das Erstellen einer [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]--basiertes Datenmodell in einer Visual Studio-Web-Anwendung, die auf einer vorhandenen Datenbank basiert und diese Datenmodell verwendet, um einen neuen Datendienst zu erstellen.  
  
 Die [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] bietet auch ein Befehlszeilentool, das generiert wird, kann ein [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] -Modell außerhalb von Visual Studio-Projekt. Weitere Informationen finden Sie unter [Vorgehensweise: verwenden EdmGen.exe generiert die Modell- und Zuordnen von Dateien](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
### <a name="to-add-an-entity-framework-model-that-is-based-on-an-existing-database-to-an-existing-web-application"></a>So fügen Sie einer vorhandenen Webanwendung ein Entity Framework-Modell hinzu, das auf einer vorhandenen Datenbank basiert  
  
1.  Auf der **Projekt** Menü klicken Sie auf **neues Element hinzufügen**.  
  
2.  In der **Vorlagen** Bereich, klicken Sie auf die **Daten** Kategorie, und wählen Sie dann **ADO.NET Entity Data Model**.  
  
3.  Geben Sie den Modellnamen, und klicken Sie dann auf **hinzufügen**.  
  
     Die erste Seite des Assistenten für [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] wird angezeigt.  
  
4.  In der **Modellinhalte** wählen Sie im Dialogfeld **aus Datenbank generieren**. Klicken Sie dann auf **Weiter**.  
  
5.  Klicken Sie auf die **neue Verbindung** Schaltfläche.  
  
6.  In der **Verbindungseigenschaften** (Dialogfeld), geben Sie Ihren Server ein, wählen Sie die Authentifizierungsmethode aus, geben Sie den Datenbanknamen ein und klicken Sie dann auf **OK**.  
  
     Die **wählen Sie Ihre Datenverbindung**im Dialogfeld mit den Verbindungseinstellungen des Datenbank aktualisiert wird.  
  
7.  Sicherstellen, dass die **Entität Verbindungseinstellungen in app.config-Datei als speichern:** aktiviert ist. Klicken Sie dann auf **Weiter**.  
  
8.  In der **Datenbankobjekte auswählen** (Dialogfeld), wählen Sie alle Datenbankobjekte aus, dass Sie im Datendienst verfügbar machen möchten.  
  
    > [!NOTE]
    >  Im Datenmodell enthaltene Objekte werden nicht automatisch vom Datendienst verfügbar gemacht. Sie müssen explizit vom Dienst selbst verfügbar gemacht werden. Weitere Informationen finden Sie unter [Konfigurieren des Datendiensts](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).  
  
9. Klicken Sie auf **Fertig stellen** um den Assistenten abzuschließen.  
  
     Dadurch wird ein Standarddatenmodell auf Grundlage der bestimmten Datenbank erstellt. Das [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] ermöglicht das Anpassen des Datenmodells. Weitere Informationen finden Sie unter [MSBuild-Aufgaben](http://msdn.microsoft.com/library/7166f1f1-4de8-4bd4-86b5-5e20a2ebaccb).  
  
### <a name="to-create-the-data-service-by-using-the-new-data-model"></a>So erstellen Sie den Datendienst mit dem neuen Datenmodell  
  
1.  Öffnen Sie in Visual Studio die EDMX-Datei, die das Datenmodell darstellt.  
  
2.  In der **Modellbrowser**mit der rechten Maustaste auf das Modell, klicken Sie auf **Eigenschaften**, und notieren Sie den Namen des Entitätscontainers handelt.  
  
3.  In **Projektmappen-Explorer**, mit der rechten Maustaste in des Namens Ihrer [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Projekt, und klicken Sie dann auf **neues Element hinzufügen**.  
  
4.  In der **neues Element hinzufügen** wählen Sie im Dialogfeld **WCF Data Service**.  
  
5.  Geben Sie einen Namen für den Dienst, und klicken Sie dann auf **OK**.  
  
     Visual Studio erstellt das XML-Markup und die Codedateien für den neuen Dienst. In der Standardeinstellung wird das Fenster des Code-Editors geöffnet.  
  
6.  Ersetzen Sie im Code für den Datendienst den Kommentar `/* TODO: put your data source class name here */` in der Definition der Klasse, die den Datendienst definiert, durch den Typ, der von der <xref:System.Data.Objects.ObjectContext>-Klasse erbt und der Entitätscontainer des Datenmodells ist, der in Schritt 2 notiert wurde.  
  
7.  Ermöglichen Sie im Code für den Datendienst berechtigten Clients, auf die Entitätenmengen zuzugreifen, die der Datendienst verfügbar macht. Weitere Informationen finden Sie unter [Erstellen des Datendiensts](../../../../docs/framework/data/wcf/creating-the-data-service.md).  
  
8.  Um den Datendienst Northwind.svc mithilfe eines Webbrowsers zu testen, führen Sie die Anweisungen im Thema [Zugriff auf den Dienst über einen Webbrowser](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 [Datendienstanbieter](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)  
 [: Erstellen eines Datendiensts mit dem Reflektionsanbieter](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)  
 [Vorgehensweise: Erstellen eines Datendiensts mit einer LINQ to SQL-Datenquelle](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md)
