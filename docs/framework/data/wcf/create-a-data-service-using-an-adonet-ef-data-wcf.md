---
title: 'Gewusst wie: Erstellen eines Datendiensts mit einer ADO.NET-Entity Framework-Datenquelle (WCF Data Services)'
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, providers
- WCF Data Services, Entity Framework
ms.assetid: 6d11fec8-0108-42f5-8719-2a7866d04428
ms.openlocfilehash: 4bccd1e4655786ae24166cdc32619b420c4a54d3
ms.sourcegitcommit: f513a91160b3fec289dd06646d0d6f81f8fcf910
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46009229"
---
# <a name="how-to-create-a-data-service-using-an-adonet-entity-framework-data-source-wcf-data-services"></a>Gewusst wie: Erstellen eines Datendiensts mit einer ADO.NET-Entity Framework-Datenquelle (WCF Data Services)

WCF Data Services macht Entitätsdaten als Datendienst verfügbar. Diese Entitätsdaten erfolgt über die [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] Wenn die Datenquelle eine relationale Datenbank ist. In diesem Thema erfahren Sie, wie zum Erstellen einer [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]--basiertes Datenmodell in einer Visual Studio Web-Anwendung, die auf einer vorhandenen Datenbank basiert dieses Datenmodell zu verwenden, um einen neuen Datendienst zu erstellen.

Die [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] bietet auch ein Befehlszeilentool, das Generieren einer [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] Modell außerhalb eines Visual Studio-Projekts. Weitere Informationen finden Sie unter [wie: Generieren Sie das Modell und die Mapping-Dateien mithilfe von EdmGen.exe](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).

## <a name="to-add-an-entity-framework-model-that-is-based-on-an-existing-database-to-an-existing-web-application"></a>So fügen Sie einer vorhandenen Webanwendung ein Entity Framework-Modell hinzu, das auf einer vorhandenen Datenbank basiert

1. Auf der **Projekt** Menü klicken Sie auf **hinzufügen** > **neues Element**.

2. In der **Vorlagen** Bereich, klicken Sie auf die **Daten** Kategorie, und wählen Sie dann **ADO.NET Entity Data Model**.

3. Geben Sie den Modellnamen ein, und klicken Sie dann auf **hinzufügen**.

     Die erste Seite des Assistenten für [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] wird angezeigt.

4. In der **auswählen des Modellinhalts** wählen Sie im Dialogfeld **aus Datenbank generieren**. Klicken Sie dann auf **Weiter**.

5. Klicken Sie auf die **neue Verbindung** Schaltfläche.

6. In der **Verbindungseigenschaften** im Dialogfeld Geben Sie Ihren Server ein, wählen Sie die Authentifizierungsmethode aus, geben Sie den Datenbanknamen, und klicken Sie dann auf **OK**.

     Die **wählen Sie Ihre Datenverbindung** im Dialogfeld mit der Datenbank-Verbindungseinstellungen aktualisiert.

7. Sicherstellen, dass die **Entitätsverbindungseinstellungen in App.Config speichern als:** aktiviert ist. Klicken Sie dann auf **Weiter**.

8. In der **Datenbankobjekte auswählen** im Dialogfeld auf alle Datenbankobjekte aus, dass im Datendienst verfügbar gemacht werden sollen.

    > [!NOTE]
    > Im Datenmodell enthaltene Objekte werden nicht automatisch vom Datendienst verfügbar gemacht. Sie müssen explizit vom Dienst selbst verfügbar gemacht werden. Weitere Informationen finden Sie unter [Konfigurieren des Datendiensts](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).

9. Klicken Sie auf **Fertig stellen** um den Assistenten abzuschließen.

     Dadurch wird ein Standarddatenmodell auf Grundlage der bestimmten Datenbank erstellt. Das [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] ermöglicht das Anpassen des Datenmodells. Weitere Informationen finden Sie unter [MSBuild-Aufgaben](https://msdn.microsoft.com/library/7166f1f1-4de8-4bd4-86b5-5e20a2ebaccb).

## <a name="to-create-the-data-service-by-using-the-new-data-model"></a>So erstellen Sie den Datendienst mit dem neuen Datenmodell

1. Öffnen Sie in Visual Studio die EDMX-Datei, die das Datenmodell darstellt.

2. In der **Modellbrowser**mit der rechten Maustaste auf das Modell, klicken Sie auf **Eigenschaften**, und notieren Sie den Namen des Entitätscontainers handelt.

3. In **Projektmappen-Explorer**, mit der rechten Maustaste in des Namens Ihrer [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Projekt, und klicken Sie dann auf **hinzufügen** > **neues Element**.

4. In der **neues Element hinzufügen** wählen Sie im Dialogfeld die **WCF Data Service** Vorlage in der **Web** Kategorie.

   ![WCF Data Service-Elementvorlage in Visual Studio 2015](media/wcf-data-service-item-template.png)

   > [!NOTE]
   > Die **WCF Data Service** Vorlage ist in Visual Studio 2015, aber nicht in Visual Studio 2017 verfügbar.

5. Geben Sie einen Namen für den Dienst, und klicken Sie dann auf **OK**.

     Visual Studio erstellt das XML-Markup und die Codedateien für den neuen Dienst. In der Standardeinstellung wird das Fenster des Code-Editors geöffnet.

6. Ersetzen Sie im Code für den Datendienst den Kommentar `/* TODO: put your data source class name here */` in der Definition der Klasse, die den Datendienst definiert, durch den Typ, der von der <xref:System.Data.Objects.ObjectContext>-Klasse erbt und der Entitätscontainer des Datenmodells ist, der in Schritt 2 notiert wurde.

7. Ermöglichen Sie im Code für den Datendienst berechtigten Clients, auf die Entitätenmengen zuzugreifen, die der Datendienst verfügbar macht. Weitere Informationen finden Sie unter [Erstellen des Datendiensts](../../../../docs/framework/data/wcf/creating-the-data-service.md).

8. Führen Sie die Anweisungen im Thema, um den Northwind.svc-Datendienst mit einem Webbrowser zu testen, [Zugriff auf den Dienst über einen Webbrowser](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).

## <a name="see-also"></a>Siehe auch

- [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
- [Datendienstanbieter](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)
- [: Erstellen eines Datendiensts mit dem Reflektionsanbieter](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)
- [Vorgehensweise: Erstellen eines Datendiensts mit einer LINQ to SQL-Datenquelle](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md)