---
title: 'Gewusst wie: Erstellen eines Datendiensts mit einer ADO.NET-Entity Framework-Datenquelle (WCF Data Services)'
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, providers
- WCF Data Services, Entity Framework
ms.assetid: 6d11fec8-0108-42f5-8719-2a7866d04428
ms.openlocfilehash: 1e559488a3260fafe6c211ff47226a258fc1289a
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557696"
---
# <a name="how-to-create-a-data-service-using-an-adonet-entity-framework-data-source-wcf-data-services"></a>Gewusst wie: Erstellen eines Datendiensts mit einer ADO.NET-Entity Framework-Datenquelle (WCF Data Services)

WCF Data Services macht Entitäts Daten als Datendienst verfügbar. Diese Entitäts Daten werden vom ADO. ntentity-Framework bereitgestellt, wenn die Datenquelle eine relationale Datenbank ist. In diesem Thema wird gezeigt, wie ein Entity Framework-basiertes Datenmodell in einer Visual Studio-Webanwendung erstellt wird, die auf einer vorhandenen Datenbank basiert, und wie mit diesem Datenmodell ein neuer Datendienst erstellt wird.

Das Entity Framework stellt auch ein Befehlszeilentool bereit, das ein Entity Framework-Modell außerhalb eines Visual Studio-Projekts generieren kann. Weitere Informationen finden Sie unter Gewusst [wie: Verwenden von EdmGen.exe zum Generieren von Modell-und Mapping-Dateien](../adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).

## <a name="to-add-an-entity-framework-model-that-is-based-on-an-existing-database-to-an-existing-web-application"></a>So fügen Sie einer vorhandenen Webanwendung ein Entity Framework-Modell hinzu, das auf einer vorhandenen Datenbank basiert

1. Klicken Sie im Menü **Projekt** auf **Add**  >  **Neues Element**hinzufügen.

2. Klicken Sie im Bereich **Vorlagen** auf die Kategorie **Daten** , und wählen Sie dann **ADO.NET Entity Data Model**aus.

3. Geben Sie den Modellnamen ein, und klicken Sie auf **Hinzufügen**.

     Die erste Seite des Entity Data Model-Assistenten wird angezeigt.

4. Wählen Sie im Dialogfeld **Modell Inhalte auswählen** die Option **aus Datenbank generieren aus**. Klicken Sie dann auf **Weiter**.

5. Klicken Sie auf die Schaltfläche **neue Verbindung** .

6. Geben Sie im Dialogfeld **Verbindungs Eigenschaften** den Servernamen ein, wählen Sie die Authentifizierungsmethode aus, geben Sie den Datenbanknamen ein, und klicken Sie dann auf **OK**.

     Das Dialogfeld **Wählen Sie Ihre Datenverbindung** aus wird mit den Einstellungen für die Datenbankverbindung aktualisiert.

7. Stellen Sie sicher, dass das Kontrollkästchen **Entitäts Verbindungseinstellungen in App.Config unter: Speichern** aktiviert ist. Klicken Sie dann auf **Weiter**.

8. Wählen Sie im Dialogfeld **Wählen Sie Ihre Datenbankobjekte** aus alle Datenbankobjekte aus, die im Datendienst verfügbar gemacht werden sollen.

    > [!NOTE]
    > Im Datenmodell enthaltene Objekte werden nicht automatisch vom Datendienst verfügbar gemacht. Sie müssen explizit vom Dienst selbst verfügbar gemacht werden. Weitere Informationen finden Sie unter [Konfigurieren des Daten Dienstanbieter](configuring-the-data-service-wcf-data-services.md).

9. Klicken Sie auf **Fertig stellen**, um den Assistenten abzuschließen.

     Dadurch wird ein Standarddatenmodell auf Grundlage der bestimmten Datenbank erstellt. Das Entity Framework ermöglicht das Anpassen des Datenmodells. Weitere Informationen finden Sie unter [Entity Data Model Tools Tasks](/previous-versions/dotnet/netframework-4.0/bb738480(v=vs.100)).

## <a name="to-create-the-data-service-by-using-the-new-data-model"></a>So erstellen Sie den Datendienst mit dem neuen Datenmodell

1. Öffnen Sie in Visual Studio die EDMX-Datei, die das Datenmodell darstellt.

2. Klicken Sie im **Modell Browser**mit der rechten Maustaste auf das Modell, klicken Sie auf **Eigenschaften**, und notieren Sie dann den Namen des Entitätencontainers.

3. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf den Namen Ihres ASP.NET-Projekts, und klicken Sie dann auf **Add**  >  **Neues Element**hinzufügen.

4. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Vorlage **WCF Data Service** in der Kategorie **Web** aus.

   ![WCF Data Service-Element Vorlage in Visual Studio 2015](./media/wcf-data-service-item-template.png)

   > [!NOTE]
   > Die **WCF Data Service** -Vorlage ist in Visual Studio 2015 verfügbar, aber nicht in Visual Studio 2017 oder höher.

5. Geben Sie einen Namen für den Dienst an, und klicken Sie dann auf **OK**.

     Visual Studio erstellt das XML-Markup und die Codedateien für den neuen Dienst. In der Standardeinstellung wird das Fenster des Code-Editors geöffnet.

6. Ersetzen Sie im Code für den Datendienst den Kommentar `/* TODO: put your data source class name here */` in der Definition der Klasse, die den Datendienst definiert, durch den Typ, der von der <xref:System.Data.Objects.ObjectContext>-Klasse erbt und der Entitätscontainer des Datenmodells ist, der in Schritt 2 notiert wurde.

7. Ermöglichen Sie im Code für den Datendienst berechtigten Clients, auf die Entitätenmengen zuzugreifen, die der Datendienst verfügbar macht. Weitere Informationen finden Sie unter [Erstellen des Daten Dienstanbieter](creating-the-data-service.md).

8. Befolgen Sie die Anweisungen im Thema [zugreifen auf den Dienst über einen Webbrowser](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md), um den Datendienst Northwind. svc mithilfe eines Webbrowsers zu testen.

## <a name="see-also"></a>Weitere Informationen

- [Definieren von WCF Data Services](defining-wcf-data-services.md)
- [Datendienstanbieter](data-services-providers-wcf-data-services.md)
- [Vorgehensweise: Erstellen eines Datendiensts mit dem Reflektionsanbieter](create-a-data-service-using-rp-wcf-data-services.md)
- [Vorgehensweise: Erstellen eines Datendiensts mit einer LINQ to SQL-Datenquelle](create-a-data-service-using-linq-to-sql-wcf.md)
