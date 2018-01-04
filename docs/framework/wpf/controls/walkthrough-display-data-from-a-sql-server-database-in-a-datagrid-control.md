---
title: 'Exemplarische Vorgehensweise: Anzeigen von Daten aus einer SQL Server-Datenbank in einem DataGrid-Steuerelement'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], displaying data from SQL Server
- controls [WPF], DataGrid
ms.assetid: 6810b048-0a23-4f86-bfa5-97f92b3cfab4
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3c8ed596706c8d656842191262c25301db595ee3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control"></a><span data-ttu-id="416b1-102">Exemplarische Vorgehensweise: Anzeigen von Daten aus einer SQL Server-Datenbank in einem DataGrid-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="416b1-102">Walkthrough: Display Data from a SQL Server Database in a DataGrid Control</span></span>
<span data-ttu-id="416b1-103">In dieser exemplarischen Vorgehensweise können Sie auch Daten aus einer SQL Server-Datenbank abgerufen und Daten angezeigt werden, in einem <xref:System.Windows.Controls.DataGrid> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="416b1-103">In this walkthrough, you retrieve data from a SQL Server database and display that data in a <xref:System.Windows.Controls.DataGrid> control.</span></span> <span data-ttu-id="416b1-104">Sie verwenden das ADO.NET Entity Framework, um die Entitätsklassen erstellt wurden, die die Daten darstellen, und Verwenden von LINQ eine Abfrage schreiben, die die angegebenen Daten aus einer Entitätsklasse abruft.</span><span class="sxs-lookup"><span data-stu-id="416b1-104">You use the ADO.NET Entity Framework to create the entity classes that represent the data, and use LINQ to write a query that retrieves the specified data from an entity class.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="416b1-105">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="416b1-105">Prerequisites</span></span>  
 <span data-ttu-id="416b1-106">Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="416b1-106">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)]  
  
-   <span data-ttu-id="416b1-108">Zugriff auf eine ausgeführte Instanz von SQL Server oder SQL Server Express, die AdventureWorks-Beispieldatenbank angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="416b1-108">Access to a running instance of SQL Server or SQL Server Express that has the AdventureWorks sample database attached to it.</span></span> <span data-ttu-id="416b1-109">Sie können die AdventureWorks-Datenbank aus der [GitHub](https://github.com/Microsoft/sql-server-samples/releases).</span><span class="sxs-lookup"><span data-stu-id="416b1-109">You can download the AdventureWorks database from the [GitHub](https://github.com/Microsoft/sql-server-samples/releases).</span></span>  
  
### <a name="to-create-entity-classes"></a><span data-ttu-id="416b1-110">Erstellen von Entitätsklassen</span><span class="sxs-lookup"><span data-stu-id="416b1-110">To create entity classes</span></span>  
  
1.  <span data-ttu-id="416b1-111">Erstellen Sie in Visual Basic oder c# ein neues WPF-Anwendungsprojekt, und nennen Sie sie `DataGridSQLExample`.</span><span class="sxs-lookup"><span data-stu-id="416b1-111">Create a new WPF Application project in Visual Basic or C#, and name it `DataGridSQLExample`.</span></span>  
  
2.  <span data-ttu-id="416b1-112">Im Projektmappen-Explorer mit der Maustaste des Projekts, zeigen Sie auf **hinzufügen**, und wählen Sie dann **neues Element**.</span><span class="sxs-lookup"><span data-stu-id="416b1-112">In Solution Explorer, right-click your project, point to **Add**, and then select **New Item**.</span></span>  
  
     <span data-ttu-id="416b1-113">Das Dialogfeld "Neues Element hinzufügen" angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="416b1-113">The Add New Item dialog box appears.</span></span>  
  
3.  <span data-ttu-id="416b1-114">Wählen Sie im Bereich installierte Vorlagen **Daten** , und wählen Sie in der Liste der Vorlagen, **ADO.NET Entity Data Modus**l.</span><span class="sxs-lookup"><span data-stu-id="416b1-114">In the Installed Templates pane, select **Data** and in the list of templates, select **ADO.NET Entity Data Mode**l.</span></span>  
  
     <span data-ttu-id="416b1-115">![Wählen Sie ADO.NET Entity Data Model](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step1.png "DataGrid_SQL_EF_Step1")</span><span class="sxs-lookup"><span data-stu-id="416b1-115">![Select ADO.NET Entity Data Model](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step1.png "DataGrid_SQL_EF_Step1")</span></span>  
  
4.  <span data-ttu-id="416b1-116">Nennen Sie die Datei `AdventureWorksModel.edmx` , und klicken Sie dann auf **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="416b1-116">Name the file `AdventureWorksModel.edmx` and then click **Add**.</span></span>  
  
     <span data-ttu-id="416b1-117">Der Assistent für Entity Data Model wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="416b1-117">The Entity Data Model Wizard appears.</span></span>  
  
5.  <span data-ttu-id="416b1-118">Wählen Sie im Bildschirm Modellinhalt **aus Datenbank generieren** , und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="416b1-118">In the Choose Model Contents screen, select **Generate from database** and then click **Next**.</span></span>  
  
     <span data-ttu-id="416b1-119">![Wählen Sie aus der Datenbankoption generieren](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step2.png "DataGrid_SQL_EF_Step2")</span><span class="sxs-lookup"><span data-stu-id="416b1-119">![Select Generate from database option](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step2.png "DataGrid_SQL_EF_Step2")</span></span>  
  
6.  <span data-ttu-id="416b1-120">Geben Sie die Verbindung mit der Datenbank AdventureWorksLT2008, auf dem Bildschirm Wählen Sie Ihre Datenverbindung.</span><span class="sxs-lookup"><span data-stu-id="416b1-120">In the Choose Your Data Connection screen, provide the connection to your AdventureWorksLT2008 database.</span></span> <span data-ttu-id="416b1-121">Weitere Informationen finden Sie unter [wählen Sie Ihre Daten Verbindungsdialogfeld](http://go.microsoft.com/fwlink/?LinkId=160190).</span><span class="sxs-lookup"><span data-stu-id="416b1-121">For more information, see [Choose Your Data Connection Dialog Box](http://go.microsoft.com/fwlink/?LinkId=160190).</span></span>  
  
     <span data-ttu-id="416b1-122">![Geben Sie die Verbindung zur Datenbank](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step3.png "DataGrid_SQL_EF_Step3")</span><span class="sxs-lookup"><span data-stu-id="416b1-122">![Provide connection to database](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step3.png "DataGrid_SQL_EF_Step3")</span></span>  
  
7.  <span data-ttu-id="416b1-123">Stellen Sie sicher, dass der Name `AdventureWorksLT2008Entities` und dass die **Entität Speichern der Verbindungseinstellungen in app.config-Datei als** Kontrollkästchen ausgewählt ist, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="416b1-123">Make sure that the name is `AdventureWorksLT2008Entities` and that the **Save entity connection settings in App.Config as** check box is selected, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="416b1-124">Klicken Sie im Bildschirm Datenbankobjekte auswählen, erweitern Sie den Knoten "Tabellen", und wählen die **Produkt** und **"ProductCategory"** Tabellen.</span><span class="sxs-lookup"><span data-stu-id="416b1-124">In the Choose Your Database Objects screen, expand the Tables node, and select the **Product** and **ProductCategory** tables.</span></span>  
  
     <span data-ttu-id="416b1-125">Sie können Entitätsklassen für alle Tabellen generieren; Allerdings rufen Sie in diesem Beispiel nur Daten aus diesen beiden Tabellen.</span><span class="sxs-lookup"><span data-stu-id="416b1-125">You can generate entity classes for all of the tables; however, in this example you only retrieve data from those two tables.</span></span>  
  
     <span data-ttu-id="416b1-126">![Wählen Sie Product und ProductCategory aus Tabellen](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step4.png "DataGrid_SQL_EF_Step4")</span><span class="sxs-lookup"><span data-stu-id="416b1-126">![Select Product and ProductCategory from tables](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step4.png "DataGrid_SQL_EF_Step4")</span></span>  
  
9. <span data-ttu-id="416b1-127">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="416b1-127">Click **Finish**.</span></span>  
  
     <span data-ttu-id="416b1-128">Die Entitäten Product und ProductCategory sind im Entity Designer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="416b1-128">The Product and ProductCategory entities are displayed in the Entity Designer.</span></span>  
  
     <span data-ttu-id="416b1-129">![Product und ProductCategory Entitätsmodelle](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step5.png "DataGrid_SQL_EF_Step5")</span><span class="sxs-lookup"><span data-stu-id="416b1-129">![Product and ProductCategory entity models](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step5.png "DataGrid_SQL_EF_Step5")</span></span>  
  
### <a name="to-retrieve-and-present-the-data"></a><span data-ttu-id="416b1-130">Zum Abrufen und präsentieren der Daten</span><span class="sxs-lookup"><span data-stu-id="416b1-130">To retrieve and present the data</span></span>  
  
1.  <span data-ttu-id="416b1-131">Öffnen Sie die Datei "MainWindow.xaml".</span><span class="sxs-lookup"><span data-stu-id="416b1-131">Open the MainWindow.xaml file.</span></span>  
  
2.  <span data-ttu-id="416b1-132">Legen Sie die <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaft auf die <xref:System.Windows.Window> auf 450.</span><span class="sxs-lookup"><span data-stu-id="416b1-132">Set the <xref:System.Windows.FrameworkElement.Width%2A> property on the <xref:System.Windows.Window> to 450.</span></span>  
  
3.  <span data-ttu-id="416b1-133">In der XAML-Editor, fügen Sie die folgenden <xref:System.Windows.Controls.DataGrid> -Tag zwischen der `<Grid>` und `</Grid>` von Tags zum Hinzufügen einer <xref:System.Windows.Controls.DataGrid> mit dem Namen `dataGrid1`.</span><span class="sxs-lookup"><span data-stu-id="416b1-133">In the XAML editor, add the following <xref:System.Windows.Controls.DataGrid> tag between the `<Grid>` and `</Grid>` tags to add a <xref:System.Windows.Controls.DataGrid> named `dataGrid1`.</span></span>  
  
     [!code-xaml[DataGrid_SQL_EF_Walkthrough#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#3)]  
  
     <span data-ttu-id="416b1-134">![Fenster mit DataGrid](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step6.png "DataGrid_SQL_EF_Step6")</span><span class="sxs-lookup"><span data-stu-id="416b1-134">![Window with DataGrid](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step6.png "DataGrid_SQL_EF_Step6")</span></span>  
  
4.  <span data-ttu-id="416b1-135">Wählen Sie das <xref:System.Windows.Window>-Steuerelement aus.</span><span class="sxs-lookup"><span data-stu-id="416b1-135">Select the <xref:System.Windows.Window>.</span></span>  
  
5.  <span data-ttu-id="416b1-136">Im Fenster "Eigenschaften" oder XAML-Editor, erstellen Sie einen Ereignishandler für das <xref:System.Windows.Window> mit dem Namen `Window_Loaded` für die <xref:System.Windows.FrameworkElement.Loaded> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="416b1-136">Using the Properties window or XAML editor, create an event handler for the <xref:System.Windows.Window> named `Window_Loaded` for the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span> <span data-ttu-id="416b1-137">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen einer einfachen Ereignishandler](http://msdn.microsoft.com/en-us/b1456e07-9dec-4354-99cf-18666b64f480).</span><span class="sxs-lookup"><span data-stu-id="416b1-137">For more information, see [How to: Create a Simple Event Handler](http://msdn.microsoft.com/en-us/b1456e07-9dec-4354-99cf-18666b64f480).</span></span>  
  
     <span data-ttu-id="416b1-138">Das folgende Beispiel zeigt die XAML für "MainWindow.xaml".</span><span class="sxs-lookup"><span data-stu-id="416b1-138">The following shows the XAML for MainWindow.xaml.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="416b1-139">Ersetzen Sie bei Verwendung von Visual Basic, in der ersten Zeile von "MainWindow.xaml" `x:Class="DataGridSQLExample.MainWindow"` mit `x:Class="MainWindow"`.</span><span class="sxs-lookup"><span data-stu-id="416b1-139">If you are using Visual Basic, in the first line of MainWindow.xaml, replace `x:Class="DataGridSQLExample.MainWindow"` with `x:Class="MainWindow"`.</span></span>  
  
     [!code-xaml[DataGrid_SQL_EF_Walkthrough#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#1)]  
  
6.  <span data-ttu-id="416b1-140">Öffnen Sie die Code-Behind-Datei ("MainWindow.Xaml.vb" bzw. "MainWindow.Xaml.cs") für die <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="416b1-140">Open the code-behind file (MainWindow.xaml.vb or MainWindow.xaml.cs) for the <xref:System.Windows.Window>.</span></span>  
  
7.  <span data-ttu-id="416b1-141">Fügen Sie den folgenden Code aus, um nur bestimmte Werte aus den verknüpften Tabellen abzurufen, und legen Sie die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> Eigenschaft der <xref:System.Windows.Controls.DataGrid> mit den Ergebnissen der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="416b1-141">Add the following code to retrieve only specific values from the joined tables and set the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.DataGrid> to the results of the query.</span></span>  
  
     [!code-csharp[DataGrid_SQL_EF_Walkthrough#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml.cs#2)]
     [!code-vb[DataGrid_SQL_EF_Walkthrough#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/VB/MainWindow.xaml.vb#2)]  
  
8.  <span data-ttu-id="416b1-142">Führen Sie das Beispiel aus.</span><span class="sxs-lookup"><span data-stu-id="416b1-142">Run the example.</span></span>  
  
     <span data-ttu-id="416b1-143">Daraufhin sollte eine <xref:System.Windows.Controls.DataGrid> , die Daten anzeigt.</span><span class="sxs-lookup"><span data-stu-id="416b1-143">You should see a <xref:System.Windows.Controls.DataGrid> that displays data.</span></span>  
  
     <span data-ttu-id="416b1-144">![DataGrid mit Daten aus SQL-Datenbank](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step7.png "DataGrid_SQL_EF_Step7")</span><span class="sxs-lookup"><span data-stu-id="416b1-144">![DataGrid with data from SQL database](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step7.png "DataGrid_SQL_EF_Step7")</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="416b1-145">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="416b1-145">Next Steps</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="416b1-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="416b1-146">See Also</span></span>  
 <xref:System.Windows.Controls.DataGrid>  
 [<span data-ttu-id="416b1-147">Wie beginne I: mit Entity Framework in WPF-Anwendungen?</span><span class="sxs-lookup"><span data-stu-id="416b1-147">How Do I: Get Started with Entity Framework in WPF Applications?</span></span>](http://go.microsoft.com/fwlink/?LinkId=159868)
