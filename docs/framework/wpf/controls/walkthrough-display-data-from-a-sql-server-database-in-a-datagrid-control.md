---
title: 'Exemplarische Vorgehensweise: Anzeigen von Daten aus einer SQL Server-Datenbank in einem DataGrid-Steuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], displaying data from SQL Server
- controls [WPF], DataGrid
ms.assetid: 6810b048-0a23-4f86-bfa5-97f92b3cfab4
ms.openlocfilehash: 30f3123a70e414e80842f726584623534994ab95
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645655"
---
# <a name="walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control"></a><span data-ttu-id="b2d1a-102">Exemplarische Vorgehensweise: Anzeigen von Daten aus einer SQL Server-Datenbank in einem DataGrid-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="b2d1a-102">Walkthrough: Display data from a SQL Server database in a DataGrid control</span></span>

<span data-ttu-id="b2d1a-103">In dieser exemplarischen Vorgehensweise können Sie auch das Abrufen von Daten aus einer SQL Server-Datenbank und Daten angezeigt werden, in einem <xref:System.Windows.Controls.DataGrid> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="b2d1a-103">In this walkthrough, you retrieve data from a SQL Server database and display that data in a <xref:System.Windows.Controls.DataGrid> control.</span></span> <span data-ttu-id="b2d1a-104">Sie verwenden das ADO.NET Entity Framework, um Entitätsklassen zu erstellen, die die Daten darstellen, und LINQ verwenden, um eine Abfrage schreiben, die die angegebenen Daten aus einer Entitätsklasse abruft.</span><span class="sxs-lookup"><span data-stu-id="b2d1a-104">You use the ADO.NET Entity Framework to create the entity classes that represent the data, and use LINQ to write a query that retrieves the specified data from an entity class.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b2d1a-105">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="b2d1a-105">Prerequisites</span></span>

<span data-ttu-id="b2d1a-106">Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="b2d1a-106">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="b2d1a-107">Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b2d1a-107">Visual Studio.</span></span>

- <span data-ttu-id="b2d1a-108">Zugriff auf eine ausgeführte Instanz von SQL Server oder SQL Server Express, die AdventureWorks-Beispieldatenbank angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="b2d1a-108">Access to a running instance of SQL Server or SQL Server Express that has the AdventureWorks sample database attached to it.</span></span> <span data-ttu-id="b2d1a-109">Sie können die AdventureWorks-Datenbank aus der [GitHub](https://github.com/Microsoft/sql-server-samples/releases).</span><span class="sxs-lookup"><span data-stu-id="b2d1a-109">You can download the AdventureWorks database from the [GitHub](https://github.com/Microsoft/sql-server-samples/releases).</span></span>

## <a name="create-entity-classes"></a><span data-ttu-id="b2d1a-110">Erstellen von Entitätsklassen</span><span class="sxs-lookup"><span data-stu-id="b2d1a-110">Create entity classes</span></span>

1. <span data-ttu-id="b2d1a-111">Erstellen Sie ein neues WPF-Anwendungsprojekt in Visual Basic oder C# -Code, und nennen Sie es `DataGridSQLExample`.</span><span class="sxs-lookup"><span data-stu-id="b2d1a-111">Create a new WPF Application project in Visual Basic or C#, and name it `DataGridSQLExample`.</span></span>

2. <span data-ttu-id="b2d1a-112">Im Projektmappen-Explorer mit der Maustaste des Projekts, zeigen Sie auf **hinzufügen**, und wählen Sie dann **neues Element**.</span><span class="sxs-lookup"><span data-stu-id="b2d1a-112">In Solution Explorer, right-click your project, point to **Add**, and then select **New Item**.</span></span>

     <span data-ttu-id="b2d1a-113">Das Dialogfeld "Neues Element hinzufügen" angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b2d1a-113">The Add New Item dialog box appears.</span></span>

3. <span data-ttu-id="b2d1a-114">Wählen Sie im Bereich Vorlagen installiert **Daten** , und wählen Sie in der Liste der Vorlagen, **ADO.NET Entity Data Model**.</span><span class="sxs-lookup"><span data-stu-id="b2d1a-114">In the Installed Templates pane, select **Data** and in the list of templates, select **ADO.NET Entity Data Model**.</span></span>

     ![ADO.NET Entity Data Model-Elementvorlage](../../wcf/feature-details/./media/ado-net-entity-data-model-item-template.png)

4. <span data-ttu-id="b2d1a-116">Nennen Sie die Datei `AdventureWorksModel.edmx` , und klicken Sie dann auf **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="b2d1a-116">Name the file `AdventureWorksModel.edmx` and then click **Add**.</span></span>

     <span data-ttu-id="b2d1a-117">Der Assistent für Entity Data Model wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b2d1a-117">The Entity Data Model Wizard appears.</span></span>

5. <span data-ttu-id="b2d1a-118">Wählen Sie im Bildschirm Auswählen des Modellinhalts **EF Designer aus Datenbank** , und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="b2d1a-118">In the Choose Model Contents screen, select **EF Designer from database** and then click **Next**.</span></span>

6. <span data-ttu-id="b2d1a-119">Geben Sie die Verbindung mit der AdventureWorksLT2008-Datenbank, auf dem Bildschirm Wählen Sie Ihre Datenverbindung.</span><span class="sxs-lookup"><span data-stu-id="b2d1a-119">In the Choose Your Data Connection screen, provide the connection to your AdventureWorksLT2008 database.</span></span> <span data-ttu-id="b2d1a-120">Weitere Informationen finden Sie unter [wählen Sie Ihre Daten im Dialogfeld Verbindung](https://go.microsoft.com/fwlink/?LinkId=160190).</span><span class="sxs-lookup"><span data-stu-id="b2d1a-120">For more information, see [Choose Your Data Connection Dialog Box](https://go.microsoft.com/fwlink/?LinkId=160190).</span></span>

    <span data-ttu-id="b2d1a-121">Stellen Sie sicher, dass der Name `AdventureWorksLT2008Entities` und dass die **Entitätsverbindungseinstellungen in App.Config speichern als** Kontrollkästchen ausgewählt ist, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="b2d1a-121">Make sure that the name is `AdventureWorksLT2008Entities` and that the **Save entity connection settings in App.Config as** check box is selected, and then click **Next**.</span></span>

7. <span data-ttu-id="b2d1a-122">Klicken Sie auf dem Bildschirm Wählen Sie Ihre Datenbankobjekte erweitern Sie den Knoten "Tabellen", und wählen die **Produkt** und **"ProductCategory"** Tabellen.</span><span class="sxs-lookup"><span data-stu-id="b2d1a-122">In the Choose Your Database Objects screen, expand the Tables node, and select the **Product** and **ProductCategory** tables.</span></span>

     <span data-ttu-id="b2d1a-123">Sie können Entitätsklassen für alle Tabellen generieren; Allerdings rufen Sie in diesem Beispiel nur Daten aus diesen zwei Tabellen.</span><span class="sxs-lookup"><span data-stu-id="b2d1a-123">You can generate entity classes for all of the tables; however, in this example you only retrieve data from those two tables.</span></span>

     <span data-ttu-id="b2d1a-124">![Wählen Sie Product und ProductCategory aus Tabellen](./media/datagrid-sql-ef-step4.png "DataGrid_SQL_EF_Step4")</span><span class="sxs-lookup"><span data-stu-id="b2d1a-124">![Select Product and ProductCategory from tables](./media/datagrid-sql-ef-step4.png "DataGrid_SQL_EF_Step4")</span></span>

8. <span data-ttu-id="b2d1a-125">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="b2d1a-125">Click **Finish**.</span></span>

     <span data-ttu-id="b2d1a-126">Die Entitäten Product und ProductCategory werden im Entity Designer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b2d1a-126">The Product and ProductCategory entities are displayed in the Entity Designer.</span></span>

     <span data-ttu-id="b2d1a-127">![Product und ProductCategory-Entitätsmodellen](./media/datagrid-sql-ef-step5.png "DataGrid_SQL_EF_Step5")</span><span class="sxs-lookup"><span data-stu-id="b2d1a-127">![Product and ProductCategory entity models](./media/datagrid-sql-ef-step5.png "DataGrid_SQL_EF_Step5")</span></span>

## <a name="retrieve-and-present-the-data"></a><span data-ttu-id="b2d1a-128">Abrufen und die Darstellung der Daten</span><span class="sxs-lookup"><span data-stu-id="b2d1a-128">Retrieve and present the data</span></span>

1. <span data-ttu-id="b2d1a-129">Öffnen Sie die Datei "MainWindow.xaml".</span><span class="sxs-lookup"><span data-stu-id="b2d1a-129">Open the MainWindow.xaml file.</span></span>

2. <span data-ttu-id="b2d1a-130">Legen Sie die <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaft für die <xref:System.Windows.Window> auf 450.</span><span class="sxs-lookup"><span data-stu-id="b2d1a-130">Set the <xref:System.Windows.FrameworkElement.Width%2A> property on the <xref:System.Windows.Window> to 450.</span></span>

3. <span data-ttu-id="b2d1a-131">In den XAML-Editor, fügen Sie die folgenden <xref:System.Windows.Controls.DataGrid> tag zwischen der `<Grid>` und `</Grid>` von Tags zum Hinzufügen einer <xref:System.Windows.Controls.DataGrid> mit dem Namen `dataGrid1`.</span><span class="sxs-lookup"><span data-stu-id="b2d1a-131">In the XAML editor, add the following <xref:System.Windows.Controls.DataGrid> tag between the `<Grid>` and `</Grid>` tags to add a <xref:System.Windows.Controls.DataGrid> named `dataGrid1`.</span></span>

     [!code-xaml[DataGrid_SQL_EF_Walkthrough#3](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#3)]

     <span data-ttu-id="b2d1a-132">![Fenster mit DataGrid](./media/datagrid-sql-ef-step6.png "DataGrid_SQL_EF_Step6")</span><span class="sxs-lookup"><span data-stu-id="b2d1a-132">![Window with DataGrid](./media/datagrid-sql-ef-step6.png "DataGrid_SQL_EF_Step6")</span></span>

4. <span data-ttu-id="b2d1a-133">Wählen Sie das <xref:System.Windows.Window>-Steuerelement aus.</span><span class="sxs-lookup"><span data-stu-id="b2d1a-133">Select the <xref:System.Windows.Window>.</span></span>

5. <span data-ttu-id="b2d1a-134">Erstellen Sie mit dem Fenster "Eigenschaften" oder der XAML-Editor, einen Ereignishandler für die <xref:System.Windows.Window> mit dem Namen `Window_Loaded` für die <xref:System.Windows.FrameworkElement.Loaded> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="b2d1a-134">Using the Properties window or XAML editor, create an event handler for the <xref:System.Windows.Window> named `Window_Loaded` for the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span> <span data-ttu-id="b2d1a-135">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines einfachen Ereignishandlers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="b2d1a-135">For more information, see [How to: Create a Simple Event Handler](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span></span>

     <span data-ttu-id="b2d1a-136">Das folgende Beispiel zeigt die XAML für "MainWindow.xaml".</span><span class="sxs-lookup"><span data-stu-id="b2d1a-136">The following shows the XAML for MainWindow.xaml.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b2d1a-137">Ersetzen Sie bei Verwendung von Visual Basic in der ersten Zeile der Datei "MainWindow.xaml" `x:Class="DataGridSQLExample.MainWindow"` mit `x:Class="MainWindow"`.</span><span class="sxs-lookup"><span data-stu-id="b2d1a-137">If you are using Visual Basic, in the first line of MainWindow.xaml, replace `x:Class="DataGridSQLExample.MainWindow"` with `x:Class="MainWindow"`.</span></span>

     [!code-xaml[DataGrid_SQL_EF_Walkthrough#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#1)]

6. <span data-ttu-id="b2d1a-138">Öffnen Sie die CodeBehind-Datei ("MainWindow.Xaml.vb" bzw. "MainWindow.Xaml.cs") für die <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="b2d1a-138">Open the code-behind file (MainWindow.xaml.vb or MainWindow.xaml.cs) for the <xref:System.Windows.Window>.</span></span>

7. <span data-ttu-id="b2d1a-139">Fügen Sie den folgenden Code, um nur bestimmte Werte aus den verknüpften Tabellen abzurufen, und legen Sie die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> Eigenschaft der <xref:System.Windows.Controls.DataGrid> auf die Ergebnisse der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="b2d1a-139">Add the following code to retrieve only specific values from the joined tables and set the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.DataGrid> to the results of the query.</span></span>

     [!code-csharp[DataGrid_SQL_EF_Walkthrough#2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml.cs#2)]
     [!code-vb[DataGrid_SQL_EF_Walkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/VB/MainWindow.xaml.vb#2)]

8. <span data-ttu-id="b2d1a-140">Führen Sie das Beispiel aus.</span><span class="sxs-lookup"><span data-stu-id="b2d1a-140">Run the example.</span></span>

     <span data-ttu-id="b2d1a-141">Daraufhin sollte eine <xref:System.Windows.Controls.DataGrid> , das Daten anzeigt.</span><span class="sxs-lookup"><span data-stu-id="b2d1a-141">You should see a <xref:System.Windows.Controls.DataGrid> that displays data.</span></span>

     <span data-ttu-id="b2d1a-142">![DataGrid mit Daten aus SQL-Datenbank](./media/datagrid-sql-ef-step7.png "DataGrid_SQL_EF_Step7")</span><span class="sxs-lookup"><span data-stu-id="b2d1a-142">![DataGrid with data from SQL database](./media/datagrid-sql-ef-step7.png "DataGrid_SQL_EF_Step7")</span></span>

## <a name="see-also"></a><span data-ttu-id="b2d1a-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b2d1a-143">See also</span></span>

- <xref:System.Windows.Controls.DataGrid>
- [<span data-ttu-id="b2d1a-144">Gewusst wie: Erste Schritte mit Entitätsframework in WPF-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="b2d1a-144">How Do I: Get Started with Entity Framework in WPF Applications?</span></span>](https://go.microsoft.com/fwlink/?LinkId=159868)
