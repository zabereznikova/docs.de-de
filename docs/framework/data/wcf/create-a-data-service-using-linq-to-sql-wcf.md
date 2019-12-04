---
title: 'Gewusst wie: Erstellen eines Datendiensts mit einer LINQ to SQL-Datenquelle (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, LINQ to SQL
- WCF Data Services, providers
ms.assetid: 3b01c2fd-8c6e-4bf5-b38f-9e61bdc3c328
ms.openlocfilehash: cde5b9903a1fd164ce106a6a408ac4bb79976642
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802278"
---
# <a name="how-to-create-a-data-service-using-a-linq-to-sql-data-source-wcf-data-services"></a>Gewusst wie: Erstellen eines Datendiensts mit einer LINQ to SQL-Datenquelle (WCF Data Services)

WCF Data Services macht Entitäts Daten als Datendienst verfügbar. Der reflektionsanbieter ermöglicht es Ihnen, ein Datenmodell zu definieren, das auf einer beliebigen Klasse basiert, die Member verfügbar macht, die eine <xref:System.Linq.IQueryable%601> Implementierung zurückgeben. Damit diese Klassen Aktualisierungen an Daten in der Datenquelle vornehmen können, müssen sie auch die <xref:System.Data.Services.IUpdatable>-Schnittstelle implementieren. Weitere Informationen finden Sie unter [Data Services-Anbietern](data-services-providers-wcf-data-services.md). In diesem Thema wird gezeigt, wie LINQ to SQL-Klassen erstellt werden, die mit dem Reflektionsanbieter auf die Northwind-Beispieldatenbank zugreifen, und wie der Datendienst erstellt wird, der auf diesen Datenklassen basiert.

## <a name="to-add-linq-to-sql-classes-to-a-project"></a>So fügen Sie einem Projekt LINQ to SQL-Klassen hinzu

1. Klicken Sie in einem Visual Basic C# oder einer Anwendung im Menü **Projekt** auf > **Neues Element** **Hinzufügen** .

2. Klicken Sie auf die Vorlage **LINQ to SQL Klassen** .

3. Ändern Sie den Namen in **Northwind. dbml**.

4. Klicken Sie auf **Hinzufügen**.

     Die Datei Northwind.dbml wird dem Projekt hinzugefügt, und der Object Relational Designer (O/R-Designer) wird geöffnet.

5. Erweitern Sie in **Server**/**Datenbank-Explorer**unter Northwind den Knoten **Tabellen** , und ziehen Sie die Tabelle `Customers` auf den objektrelationaler Designer (O/R-Designer).

     Eine `Customer`-Entitätsklasse wird erstellt und auf der Entwurfsoberfläche angezeigt.

6. Wiederholen Sie Schritt 6 für die Tabellen `Orders`, `Order_Details` und `Products`.

7. Klicken Sie mit der rechten Maustaste auf die neue DBML-Datei, die die LINQ to SQL Klassen darstellt, und klicken Sie auf **Code anzeigen**.

     Dadurch wird die neue Code-Behind-Seite Northwind.cs erstellt, die eine partielle Klassendefinition für die Klasse enthält, die von der <xref:System.Data.Linq.DataContext>-Klasse erbt, in diesem Fall `NorthwindDataContext`.

8. Ersetzen Sie den Inhalt der Codedatei Northwind.cs durch folgenden Code. Dieser Code implementiert den Reflektionsanbieter, indem er den <xref:System.Data.Linq.DataContext> und von LINQ to SQL generierte Datenklassen erweitert:

     [!code-csharp[Astoria Linq Provider#Linq2SqlProvider](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_linq_provider/cs/northwind.cs#linq2sqlprovider)]
     [!code-vb[Astoria Linq Provider#Linq2SqlProvider](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_linq_provider/vb/northwind.vb#linq2sqlprovider)]

### <a name="to-create-a-data-service-by-using-a-linq-to-sql-based-data-model"></a>So erstellen Sie einen Datendienst mit einem LINQ to SQL-basierten Datenmodell

1. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf den Namen Ihres ASP.NET-Projekts, und klicken Sie dann auf > **Neues Element** **Hinzufügen** .

2. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Vorlage **WCF Data Service** aus der Kategorie **Web** aus.

   ![WCF Data Service-Element Vorlage in Visual Studio 2015](./media/wcf-data-service-item-template.png)

   > [!NOTE]
   > Die **WCF Data Service** -Vorlage ist in Visual Studio 2015 verfügbar, aber nicht in Visual Studio 2017 oder höher.

3. Geben Sie einen Namen für den Dienst an, und klicken Sie dann auf **OK**.

     Visual Studio erstellt das XML-Markup und die Codedateien für den neuen Dienst. In der Standardeinstellung wird das Fenster des Code-Editors geöffnet.

4. Ersetzen Sie im Code für den Datendienst in der Definition der Klasse, die den Datendienst definiert, den Kommentar `/* TODO: put your data source class name here */` durch den Typ des Entitätscontainers des Datenmodells, in diesem Fall `NorthwindDataContext`.

5. Ersetzen Sie im Code für den Datendienst den Platzhaltercode in der `InitializeService`-Funktion durch Folgendes:

     [!code-csharp[Astoria Linq Provider#EnableAccess](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_linq_provider/cs/northwind.svc.cs#enableaccess)]
     [!code-vb[Astoria Linq Provider#EnableAccess](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_linq_provider/vb/northwind.svc.vb#enableaccess)]

     Dies ermöglicht es berechtigten Clients, auf Ressourcen für die drei angegebenen Entitätenmengen zuzugreifen.

6. Befolgen Sie die Anweisungen im Thema [zugreifen auf den Dienst über einen Webbrowser](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md), um den Datendienst Northwind. svc mithilfe eines Webbrowsers zu testen.

## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Erstellen eines Datendiensts mit einer ADO.NET-Entity Framework-Datenquelle](create-a-data-service-using-an-adonet-ef-data-wcf.md)
- [: Erstellen eines Datendiensts mit dem Reflektionsanbieter](create-a-data-service-using-rp-wcf-data-services.md)
- [Datendienstanbieter](data-services-providers-wcf-data-services.md)
