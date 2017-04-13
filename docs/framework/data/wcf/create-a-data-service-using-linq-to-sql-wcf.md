---
title: "Gewusst wie: Erstellen eines Datendiensts mit einer LINQ to SQL-Datenquelle (WCF Data Services) | Microsoft Docs"
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
  - "WCF Data Services, LINQ to SQL"
  - "WCF Data Services, Anbieter"
ms.assetid: 3b01c2fd-8c6e-4bf5-b38f-9e61bdc3c328
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Gewusst wie: Erstellen eines Datendiensts mit einer LINQ to SQL-Datenquelle (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] macht Entitätsdaten als Datendienst verfügbar.  Der Reflektionsanbieter ermöglicht es Ihnen, ein auf einer Klasse basierendes Datenmodell zu definieren, die Member verfügbar macht, die eine <xref:System.Linq.IQueryable%601>\-Implementierung zurückgeben.  Damit diese Klassen Aktualisierungen an Daten in der Datenquelle vornehmen können, müssen sie auch die <xref:System.Data.Services.IUpdatable>\-Schnittstelle implementieren.  Weitere Informationen finden Sie unter [Datendiensteanbieter](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).  In diesem Thema wird gezeigt, wie LINQ to SQL\-Klassen erstellt werden, die mit dem Reflektionsanbieter auf die Northwind\-Beispieldatenbank zugreifen, und wie der Datendienst erstellt wird, der auf diesen Datenklassen basiert.  
  
### So fügen Sie einem Projekt LINQ to SQL\-Klassen hinzu  
  
1.  Klicken Sie in einer Visual Basic\- oder C\#\-Anwendung im Menü **Projekt** auf **Neues Element hinzufügen**.  
  
2.  Klicken Sie auf die Vorlage **LINQ to SQL\-Klassen**.  
  
3.  Ändern Sie den Namen in Northwind.dbml.  
  
4.  Klicken Sie auf **Hinzufügen**.  
  
     Die Datei Northwind.dbml wird dem Projekt hinzugefügt, und der Object Relational Designer \(O\/R\-Designer\) wird geöffnet.  
  
5.  Erweitern Sie in **Server**\/**Datenbank\-Explorer** unter Northwind den Knoten **Tabellen**, und ziehen Sie die Tabelle `Customers` auf den Object Relational Designer \(O\/R\-Designer\).  
  
     Eine `Customer`\-Entitätsklasse wird erstellt und auf der Entwurfsoberfläche angezeigt.  
  
6.  Wiederholen Sie Schritt 6 für die Tabellen `Orders`, `Order_Details` und `Products`.  
  
7.  Klicken Sie mit der rechten Maustaste auf die neue DBML\-Datei, die die LINQ to SQL\-Klassen darstellt, und klicken Sie auf **Code anzeigen**.  
  
     Dadurch wird die neue Code\-Behind\-Seite Northwind.cs erstellt, die eine partielle Klassendefinition für die Klasse enthält, die von der <xref:System.Data.Linq.DataContext>\-Klasse erbt, in diesem Fall `NorthwindDataContext`.  
  
8.  Ersetzen Sie den Inhalt der Codedatei Northwind.cs durch folgenden Code.  Dieser Code implementiert den Reflektionsanbieter, indem er den <xref:System.Data.Linq.DataContext> und von LINQ to SQL generierte Datenklassen erweitert:  
  
     [!code-csharp[Astoria Linq Provider#Linq2SqlProvider](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria linq provider/cs/northwind.cs#linq2sqlprovider)]
     [!code-vb[Astoria Linq Provider#Linq2SqlProvider](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria linq provider/vb/northwind.vb#linq2sqlprovider)]  
  
### So erstellen Sie einen Datendienst mit einem LINQ to SQL\-basierten Datenmodell  
  
1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf den Namen des ASP.NET\-Projekts, und klicken Sie dann auf **Neues Element hinzufügen**.  
  
2.  Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **WCF Data Service** aus.  
  
3.  Geben Sie einen Namen für den Dienst an, und klicken Sie dann auf **OK**.  
  
     Visual Studio erstellt das XML\-Markup und die Codedateien für den neuen Dienst.  In der Standardeinstellung wird das Fenster des Code\-Editors geöffnet.  
  
4.  Ersetzen Sie im Code für den Datendienst in der Definition der Klasse, die den Datendienst definiert, den Kommentar `/* TODO: put your data source class name here */` durch den Typ des Entitätscontainers des Datenmodells, in diesem Fall `NorthwindDataContext`.  
  
5.  Ersetzen Sie im Code für den Datendienst den Platzhaltercode in der `InitializeService`\-Funktion durch Folgendes:  
  
     [!code-csharp[Astoria Linq Provider#EnableAccess](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria linq provider/cs/northwind.svc.cs#enableaccess)]
     [!code-vb[Astoria Linq Provider#EnableAccess](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria linq provider/vb/northwind.svc.vb#enableaccess)]  
  
     Dies ermöglicht es berechtigten Clients, auf Ressourcen für die drei angegebenen Entitätenmengen zuzugreifen.  
  
6.  Folgen Sie zum Testen des Northwind.svc\-Datendiensts in einem Webbrowser den Anweisungen im Thema [Zugreifen auf den Dienst in einem Webbrowser](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).  
  
## Siehe auch  
 [Gewusst wie: Erstellen eines Datendiensts mit einer ADO.NET Entity Framework\-Datenquelle](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md)   
 [Gewusst wie: Erstellen eines Datendiensts mithilfe des Reflektionsanbieters](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)   
 [Datendiensteanbieter](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)