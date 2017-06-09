---
title: "Gewusst wie Erstellen eines Datendiensts mit einer ADO.NET Entity Framework-Datenquelle (WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "WCF Data Services, Entity Framework"
  - "WCF Data Services, Anbieter"
ms.assetid: 6d11fec8-0108-42f5-8719-2a7866d04428
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Gewusst wie Erstellen eines Datendiensts mit einer ADO.NET Entity Framework-Datenquelle (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] macht Entitätsdaten als Datendienst verfügbar.  Wenn die Datenquelle eine relationale Datenbank ist, werden diese Entitätsdaten vom [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] bereitgestellt.  In diesem Thema wird gezeigt, wie ein [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]\-basiertes Datenmodell in einer [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]\-Webanwendung erstellt wird, die auf einer vorhandenen Datenbank basiert, und wie mit diesem Datenmodell ein neuer Datendienst erstellt wird.  
  
 Das [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] stellt auch ein Befehlszeilentool bereit, das ein [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]\-Modell außerhalb eines [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]\-Projekts generieren kann.  Weitere Informationen finden Sie unter [Vorgehensweise: Generieren von Modell\- und Zuordnungsdateien mithilfe von EdmGen.exe](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
### So fügen Sie einer vorhandenen Webanwendung ein Entity Framework\-Modell hinzu, das auf einer vorhandenen Datenbank basiert  
  
1.  Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.  
  
2.  Klicken Sie im Bereich **Vorlagen** auf die Kategorie **Daten**, und wählen Sie dann **ADO.NET Entity Data Model** aus.  
  
3.  Geben Sie den Modellnamen ein, und klicken Sie dann auf **Hinzufügen**.  
  
     Die erste Seite des Assistenten für [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] wird angezeigt.  
  
4.  Wählen Sie im Dialogfeld **Modellinhalte auswählen** die Option **Aus Datenbank generieren** aus.  Klicken Sie dann auf **Weiter**.  
  
5.  Klicken Sie auf die Schaltfläche **Neue Verbindung**.  
  
6.  Geben Sie im Dialogfeld **Verbindungseigenschaften** den Namen des Servers ein, wählen Sie die Authentifizierungsmethode aus, geben Sie den Datenbanknamen ein, und klicken Sie anschließend auf **OK**.  
  
     Das Dialogfeld **Wählen Sie Ihre Datenverbindung aus** wird mit Ihren Verbindungseinstellungen für die Datenbank aktualisiert.  
  
7.  Stellen Sie sicher, dass das Kontrollkästchen **Die Entitätsverbindungseinstellungen in App.Config speichern als:** aktiviert ist.  Klicken Sie dann auf **Weiter**.  
  
8.  Wählen Sie im Dialogfeld **Wählen Sie Ihre Datenbankobjekte aus** alle Datenbankobjekte aus, die im Datendienst verfügbar gemacht werden sollen.  
  
    > [!NOTE]
    >  Im Datenmodell enthaltene Objekte werden nicht automatisch vom Datendienst verfügbar gemacht.  Sie müssen explizit vom Dienst selbst verfügbar gemacht werden.  Weitere Informationen finden Sie unter [Konfigurieren des Datendiensts](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).  
  
9. Klicken Sie auf **Fertig stellen**, um den Assistenten abzuschließen.  
  
     Dadurch wird ein Standarddatenmodell auf Grundlage der bestimmten Datenbank erstellt.  Das [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] ermöglicht das Anpassen des Datenmodells.  Weitere Informationen finden Sie unter [Tasks](http://msdn.microsoft.com/de-de/7166f1f1-4de8-4bd4-86b5-5e20a2ebaccb).  
  
### So erstellen Sie den Datendienst mit dem neuen Datenmodell  
  
1.  Öffnen Sie in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] die EDMX\-Datei, die das Datenmodell darstellt.  
  
2.  Klicken Sie im **Modellbrowser** mit der rechten Maustaste auf das Modell, klicken Sie auf **Eigenschaften**, und notieren Sie den Namen des Entitätscontainers.  
  
3.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf den Namen des [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Projekts, und klicken Sie dann auf **Neues Element hinzufügen**.  
  
4.  Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **WCF Data Service** aus.  
  
5.  Geben Sie einen Namen für den Dienst an, und klicken Sie dann auf **OK**.  
  
     [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] erstellt das XML\-Markup und die Codedateien für den neuen Dienst.  In der Standardeinstellung wird das Fenster des Code\-Editors geöffnet.  
  
6.  Ersetzen Sie im Code für den Datendienst den Kommentar `/* TODO: put your data source class name here */` in der Definition der Klasse, die den Datendienst definiert, durch den Typ, der von der <xref:System.Data.Objects.ObjectContext>\-Klasse erbt und der Entitätscontainer des Datenmodells ist, der in Schritt 2 notiert wurde.  
  
7.  Ermöglichen Sie im Code für den Datendienst berechtigten Clients, auf die Entitätenmengen zuzugreifen, die der Datendienst verfügbar macht.  Weitere Informationen finden Sie unter [Erstellen des Datendiensts](../../../../docs/framework/data/wcf/creating-the-data-service.md).  
  
8.  Folgen Sie zum Testen des Northwind.svc\-Datendiensts in einem Webbrowser den Anweisungen im Thema [Zugreifen auf den Dienst in einem Webbrowser](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).  
  
## Siehe auch  
 [Definieren von WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)   
 [Datendiensteanbieter](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)   
 [Gewusst wie: Erstellen eines Datendiensts mithilfe des Reflektionsanbieters](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)   
 [Gewusst wie: Erstellen eines Datendiensts mit einer LINQ to SQL\-Datenquelle](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md)