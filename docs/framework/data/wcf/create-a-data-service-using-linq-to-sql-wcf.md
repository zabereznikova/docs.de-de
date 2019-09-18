---
title: 'Vorgehensweise: Erstellen eines Daten Dienstanbieter mit einer LINQ to SQL Datenquelle (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, LINQ to SQL
- WCF Data Services, providers
ms.assetid: 3b01c2fd-8c6e-4bf5-b38f-9e61bdc3c328
ms.openlocfilehash: 6489e451f3790e38ea821104fd2aca5a8c091ba6
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053000"
---
# <a name="how-to-create-a-data-service-using-a-linq-to-sql-data-source-wcf-data-services"></a><span data-ttu-id="6f616-102">Vorgehensweise: Erstellen eines Daten Dienstanbieter mit einer LINQ to SQL Datenquelle (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="6f616-102">How to: Create a Data Service Using a LINQ to SQL Data Source (WCF Data Services)</span></span>

<span data-ttu-id="6f616-103">WCF Data Services macht Entitäts Daten als Datendienst verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6f616-103">WCF Data Services exposes entity data as a data service.</span></span> <span data-ttu-id="6f616-104">Der reflektionsanbieter ermöglicht es Ihnen, ein Datenmodell zu definieren, das auf jeder Klasse basiert, die <xref:System.Linq.IQueryable%601> Member verfügbar macht, die eine-Implementierung zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="6f616-104">The reflection provider enables you to define a data model that is based on any class that exposes members that return an <xref:System.Linq.IQueryable%601> implementation.</span></span> <span data-ttu-id="6f616-105">Damit diese Klassen Aktualisierungen an Daten in der Datenquelle vornehmen können, müssen sie auch die <xref:System.Data.Services.IUpdatable>-Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="6f616-105">To be able to make updates to data in the data source, these classes must also implement the <xref:System.Data.Services.IUpdatable> interface.</span></span> <span data-ttu-id="6f616-106">Weitere Informationen finden Sie unter [Data Services-Anbietern](data-services-providers-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="6f616-106">For more information, see [Data Services Providers](data-services-providers-wcf-data-services.md).</span></span> <span data-ttu-id="6f616-107">In diesem Thema wird gezeigt, wie LINQ to SQL-Klassen erstellt werden, die mit dem Reflektionsanbieter auf die Northwind-Beispieldatenbank zugreifen, und wie der Datendienst erstellt wird, der auf diesen Datenklassen basiert.</span><span class="sxs-lookup"><span data-stu-id="6f616-107">This topic shows you how to create LINQ to SQL classes that access the Northwind sample database by using the reflection provider, as well as how to create the data service that is based on these data classes.</span></span>

## <a name="to-add-linq-to-sql-classes-to-a-project"></a><span data-ttu-id="6f616-108">So fügen Sie einem Projekt LINQ to SQL-Klassen hinzu</span><span class="sxs-lookup"><span data-stu-id="6f616-108">To add LINQ to SQL classes to a project</span></span>

1. <span data-ttu-id="6f616-109">Klicken Sie in einem Visual Basic C# oder einer Anwendung im Menü **Projekt** auf**Neues Element** **Hinzufügen** > .</span><span class="sxs-lookup"><span data-stu-id="6f616-109">From within a Visual Basic or C# application, on the **Project** menu, click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="6f616-110">Klicken Sie auf die Vorlage **LINQ to SQL Klassen** .</span><span class="sxs-lookup"><span data-stu-id="6f616-110">Click the **LINQ to SQL Classes** template.</span></span>

3. <span data-ttu-id="6f616-111">Ändern Sie den Namen in **Northwind. dbml**.</span><span class="sxs-lookup"><span data-stu-id="6f616-111">Change the name to **Northwind.dbml**.</span></span>

4. <span data-ttu-id="6f616-112">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="6f616-112">Click **Add**.</span></span>

     <span data-ttu-id="6f616-113">Die Datei Northwind.dbml wird dem Projekt hinzugefügt, und der Object Relational Designer (O/R-Designer) wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="6f616-113">The Northwind.dbml file is added to the project and the Object Relational Designer (O/R Designer) opens.</span></span>

5. <span data-ttu-id="6f616-114">Erweitern Sie in **Server**/**Datenbank-Explorer**unter Northwind den Knoten **Tabellen** , und `Customers` ziehen Sie die Tabelle auf den objektrelationaler Designer (O/R-Designer).</span><span class="sxs-lookup"><span data-stu-id="6f616-114">In **Server**/**Database Explorer**, under Northwind, expand **Tables** and drag the `Customers` table onto the Object Relational Designer (O/R Designer).</span></span>

     <span data-ttu-id="6f616-115">Eine `Customer`-Entitätsklasse wird erstellt und auf der Entwurfsoberfläche angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6f616-115">A `Customer` entity class is created and appears on the design surface.</span></span>

6. <span data-ttu-id="6f616-116">Wiederholen Sie Schritt 6 für die Tabellen `Orders`, `Order_Details` und `Products`.</span><span class="sxs-lookup"><span data-stu-id="6f616-116">Repeat step 6 for the `Orders`, `Order_Details`, and `Products` tables.</span></span>

7. <span data-ttu-id="6f616-117">Klicken Sie mit der rechten Maustaste auf die neue DBML-Datei, die die LINQ to SQL Klassen darstellt, und klicken Sie auf **Code anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="6f616-117">Right-click the new .dbml file that represents the LINQ to SQL classes and click **View Code**.</span></span>

     <span data-ttu-id="6f616-118">Dadurch wird die neue Code-Behind-Seite Northwind.cs erstellt, die eine partielle Klassendefinition für die Klasse enthält, die von der <xref:System.Data.Linq.DataContext>-Klasse erbt, in diesem Fall `NorthwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="6f616-118">This creates a new code-behind page named Northwind.cs that contains a partial class definition for the class that inherits from the <xref:System.Data.Linq.DataContext> class, which in this case is `NorthwindDataContext`.</span></span>

8. <span data-ttu-id="6f616-119">Ersetzen Sie den Inhalt der Codedatei Northwind.cs durch folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="6f616-119">Replace the contents of the Northwind.cs code file with the following code.</span></span> <span data-ttu-id="6f616-120">Dieser Code implementiert den Reflektionsanbieter, indem er den <xref:System.Data.Linq.DataContext> und von LINQ to SQL generierte Datenklassen erweitert:</span><span class="sxs-lookup"><span data-stu-id="6f616-120">This code implements the reflection provider by extending the <xref:System.Data.Linq.DataContext> and data classes generated by LINQ to SQL:</span></span>

     [!code-csharp[Astoria Linq Provider#Linq2SqlProvider](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_linq_provider/cs/northwind.cs#linq2sqlprovider)]
     [!code-vb[Astoria Linq Provider#Linq2SqlProvider](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_linq_provider/vb/northwind.vb#linq2sqlprovider)]

### <a name="to-create-a-data-service-by-using-a-linq-to-sql-based-data-model"></a><span data-ttu-id="6f616-121">So erstellen Sie einen Datendienst mit einem LINQ to SQL-basierten Datenmodell</span><span class="sxs-lookup"><span data-stu-id="6f616-121">To create a data service by using a LINQ to SQL-based data model</span></span>

1. <span data-ttu-id="6f616-122">Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf den Namen Ihres ASP.NET-Projekts, und klicken Sie dann auf**Neues Element** **Hinzufügen** > .</span><span class="sxs-lookup"><span data-stu-id="6f616-122">In **Solution Explorer**, right-click the name of your ASP.NET project, and then click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="6f616-123">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Vorlage **WCF Data Service** aus der Kategorie **Web** aus.</span><span class="sxs-lookup"><span data-stu-id="6f616-123">In the **Add New Item** dialog box, select the **WCF Data Service** template from the **Web** category.</span></span>

   ![WCF Data Service-Element Vorlage in Visual Studio 2015](./media/wcf-data-service-item-template.png)

   > [!NOTE]
   > <span data-ttu-id="6f616-125">Die **WCF Data Service** -Vorlage ist in Visual Studio 2015 verfügbar, aber nicht in Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="6f616-125">The **WCF Data Service** template is available in Visual Studio 2015, but not in Visual Studio 2017.</span></span>

3. <span data-ttu-id="6f616-126">Geben Sie einen Namen für den Dienst an, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="6f616-126">Supply a name for the service, and then click **OK**.</span></span>

     <span data-ttu-id="6f616-127">Visual Studio erstellt das XML-Markup und die Codedateien für den neuen Dienst.</span><span class="sxs-lookup"><span data-stu-id="6f616-127">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="6f616-128">In der Standardeinstellung wird das Fenster des Code-Editors geöffnet.</span><span class="sxs-lookup"><span data-stu-id="6f616-128">By default, the code-editor window opens.</span></span>

4. <span data-ttu-id="6f616-129">Ersetzen Sie im Code für den Datendienst in der Definition der Klasse, die den Datendienst definiert, den Kommentar `/* TODO: put your data source class name here */` durch den Typ des Entitätscontainers des Datenmodells, in diesem Fall `NorthwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="6f616-129">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that is the entity container of the data model, which in this case is `NorthwindDataContext`.</span></span>

5. <span data-ttu-id="6f616-130">Ersetzen Sie im Code für den Datendienst den Platzhaltercode in der `InitializeService`-Funktion durch Folgendes:</span><span class="sxs-lookup"><span data-stu-id="6f616-130">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>

     [!code-csharp[Astoria Linq Provider#EnableAccess](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_linq_provider/cs/northwind.svc.cs#enableaccess)]
     [!code-vb[Astoria Linq Provider#EnableAccess](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_linq_provider/vb/northwind.svc.vb#enableaccess)]

     <span data-ttu-id="6f616-131">Dies ermöglicht es berechtigten Clients, auf Ressourcen für die drei angegebenen Entitätenmengen zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="6f616-131">This enables authorized clients to access resources for the three specified entity sets.</span></span>

6. <span data-ttu-id="6f616-132">Befolgen Sie die Anweisungen im Thema [zugreifen auf den Dienst über einen Webbrowser](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md), um den Datendienst Northwind. svc mithilfe eines Webbrowsers zu testen.</span><span class="sxs-lookup"><span data-stu-id="6f616-132">To test the Northwind.svc data service by using a Web browser, follow the instructions in the topic [Accessing the Service from a Web Browser](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6f616-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6f616-133">See also</span></span>

- [<span data-ttu-id="6f616-134">Vorgehensweise: Erstellen eines Daten Dienstanbieter mit einer ADO.NET-Entity Framework Datenquelle</span><span class="sxs-lookup"><span data-stu-id="6f616-134">How to: Create a Data Service Using an ADO.NET Entity Framework Data Source</span></span>](create-a-data-service-using-an-adonet-ef-data-wcf.md)
- [<span data-ttu-id="6f616-135">Vorgehensweise: Erstellen eines Daten Dienes mithilfe des reflektionsanbieters</span><span class="sxs-lookup"><span data-stu-id="6f616-135">How to: Create a Data Service Using the Reflection Provider</span></span>](create-a-data-service-using-rp-wcf-data-services.md)
- [<span data-ttu-id="6f616-136">Datendienstanbieter</span><span class="sxs-lookup"><span data-stu-id="6f616-136">Data Services Providers</span></span>](data-services-providers-wcf-data-services.md)
