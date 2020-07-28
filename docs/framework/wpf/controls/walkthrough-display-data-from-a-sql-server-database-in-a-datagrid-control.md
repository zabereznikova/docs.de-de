---
title: 'Exemplarische Vorgehensweise: Anzeigen von Daten aus einer SQL Server-Datenbank in einem DataGrid-Steuerelement'
description: In dieser exemplarischen Vorgehensweise erfahren Sie, wie Sie Daten aus einer SQL Server Datenbank und in einem Windows Presentation Foundation DataGrid-Steuerelement anzeigen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], displaying data from SQL Server
- controls [WPF], DataGrid
ms.assetid: 6810b048-0a23-4f86-bfa5-97f92b3cfab4
ms.openlocfilehash: cc41979c869021c9c363f3f68ce590d4702e068c
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167551"
---
# <a name="walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control"></a><span data-ttu-id="1f029-103">Exemplarische Vorgehensweise: Anzeigen von Daten aus einer SQL Server Datenbank in einem DataGrid-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="1f029-103">Walkthrough: Display data from a SQL Server database in a DataGrid control</span></span>

<span data-ttu-id="1f029-104">In dieser exemplarischen Vorgehensweise rufen Sie Daten aus einer SQL Server Datenbank ab und zeigen diese Daten in einem-Steuerelement an <xref:System.Windows.Controls.DataGrid> .</span><span class="sxs-lookup"><span data-stu-id="1f029-104">In this walkthrough, you retrieve data from a SQL Server database and display that data in a <xref:System.Windows.Controls.DataGrid> control.</span></span> <span data-ttu-id="1f029-105">Verwenden Sie die ADO.NET-Entity Framework, um die Entitäts Klassen zu erstellen, die die Daten darstellen, und verwenden Sie LINQ, um eine Abfrage zu schreiben, mit der die angegebenen Daten aus einer Entitäts Klasse abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1f029-105">You use the ADO.NET Entity Framework to create the entity classes that represent the data, and use LINQ to write a query that retrieves the specified data from an entity class.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1f029-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="1f029-106">Prerequisites</span></span>

<span data-ttu-id="1f029-107">Zum Abschließen dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="1f029-107">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="1f029-108">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1f029-108">Visual Studio.</span></span>

- <span data-ttu-id="1f029-109">Zugriff auf eine laufende Instanz von SQL Server oder SQL Server Express, der die AdventureWorks-Beispieldatenbank angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="1f029-109">Access to a running instance of SQL Server or SQL Server Express that has the AdventureWorks sample database attached to it.</span></span> <span data-ttu-id="1f029-110">Sie können die AdventureWorks-Datenbank von [GitHub](https://github.com/Microsoft/sql-server-samples/releases)herunterladen.</span><span class="sxs-lookup"><span data-stu-id="1f029-110">You can download the AdventureWorks database from the [GitHub](https://github.com/Microsoft/sql-server-samples/releases).</span></span>

## <a name="create-entity-classes"></a><span data-ttu-id="1f029-111">Erstellen von Entitäts Klassen</span><span class="sxs-lookup"><span data-stu-id="1f029-111">Create entity classes</span></span>

1. <span data-ttu-id="1f029-112">Erstellen Sie ein neues WPF-Anwendungsprojekt in Visual Basic oder c#, und nennen Sie es `DataGridSQLExample` .</span><span class="sxs-lookup"><span data-stu-id="1f029-112">Create a new WPF Application project in Visual Basic or C#, and name it `DataGridSQLExample`.</span></span>

2. <span data-ttu-id="1f029-113">Klicken Sie in Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, zeigen Sie auf **Hinzufügen**, und wählen Sie dann **Neues Element**aus.</span><span class="sxs-lookup"><span data-stu-id="1f029-113">In Solution Explorer, right-click your project, point to **Add**, and then select **New Item**.</span></span>

     <span data-ttu-id="1f029-114">Das Dialogfeld Neues Element hinzufügen wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1f029-114">The Add New Item dialog box appears.</span></span>

3. <span data-ttu-id="1f029-115">Wählen Sie im Bereich installierte Vorlagen die Option **Daten** aus, und wählen Sie in der Liste der Vorlagen die Option **ADO.NET Entity Data Model**aus.</span><span class="sxs-lookup"><span data-stu-id="1f029-115">In the Installed Templates pane, select **Data** and in the list of templates, select **ADO.NET Entity Data Model**.</span></span>

     ![ADO.NET Entity Data Model-Element Vorlage](../../wcf/feature-details/media/ado-net-entity-data-model-item-template.png)

4. <span data-ttu-id="1f029-117">Benennen Sie die Datei, `AdventureWorksModel.edmx` und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="1f029-117">Name the file `AdventureWorksModel.edmx` and then click **Add**.</span></span>

     <span data-ttu-id="1f029-118">Der Assistent für Entity Data Model wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1f029-118">The Entity Data Model Wizard appears.</span></span>

5. <span data-ttu-id="1f029-119">Wählen Sie im Bildschirm Modell Inhalt auswählen die Option **EF-Designer aus Datenbank aus** , und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="1f029-119">In the Choose Model Contents screen, select **EF Designer from database** and then click **Next**.</span></span>

6. <span data-ttu-id="1f029-120">Stellen Sie im Bildschirm Wählen Sie Ihre Datenverbindung aus die Verbindung mit der AdventureWorksLT2008-Datenbank her.</span><span class="sxs-lookup"><span data-stu-id="1f029-120">In the Choose Your Data Connection screen, provide the connection to your AdventureWorksLT2008 database.</span></span> <span data-ttu-id="1f029-121">Weitere Informationen finden Sie unter [Auswählen der Datenverbindung (Dialog Feld](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399244(v=vs.100))).</span><span class="sxs-lookup"><span data-stu-id="1f029-121">For more information, see [Choose Your Data Connection Dialog Box](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399244(v=vs.100)).</span></span>

    <span data-ttu-id="1f029-122">Stellen Sie sicher, dass der Name lautet `AdventureWorksLT2008Entities` und dass das Kontrollkästchen **Entitäts Verbindungseinstellungen in App.Config as speichern** aktiviert ist, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="1f029-122">Make sure that the name is `AdventureWorksLT2008Entities` and that the **Save entity connection settings in App.Config as** check box is selected, and then click **Next**.</span></span>

7. <span data-ttu-id="1f029-123">Erweitern Sie im Bildschirm Wählen Sie Ihre Datenbankobjekte aus den Knoten Tabellen, und wählen Sie die Tabelle **Product** und **ProductCategory** aus.</span><span class="sxs-lookup"><span data-stu-id="1f029-123">In the Choose Your Database Objects screen, expand the Tables node, and select the **Product** and **ProductCategory** tables.</span></span>

     <span data-ttu-id="1f029-124">Sie können Entitäts Klassen für alle Tabellen generieren. in diesem Beispiel rufen Sie jedoch nur Daten aus diesen beiden Tabellen ab.</span><span class="sxs-lookup"><span data-stu-id="1f029-124">You can generate entity classes for all of the tables; however, in this example you only retrieve data from those two tables.</span></span>

     <span data-ttu-id="1f029-125">![Product und ProductCategory aus Tabellen auswählen](./media/datagrid-sql-ef-step4.png "DataGrid_SQL_EF_Step4")</span><span class="sxs-lookup"><span data-stu-id="1f029-125">![Select Product and ProductCategory from tables](./media/datagrid-sql-ef-step4.png "DataGrid_SQL_EF_Step4")</span></span>

8. <span data-ttu-id="1f029-126">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="1f029-126">Click **Finish**.</span></span>

     <span data-ttu-id="1f029-127">Die Product-und ProductCategory-Entitäten werden in der Entity Designer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1f029-127">The Product and ProductCategory entities are displayed in the Entity Designer.</span></span>

     <span data-ttu-id="1f029-128">![Entitätsmodelle Product und ProductCategory](./media/datagrid-sql-ef-step5.png "DataGrid_SQL_EF_Step5")</span><span class="sxs-lookup"><span data-stu-id="1f029-128">![Product and ProductCategory entity models](./media/datagrid-sql-ef-step5.png "DataGrid_SQL_EF_Step5")</span></span>

## <a name="retrieve-and-present-the-data"></a><span data-ttu-id="1f029-129">Abrufen und präsentieren der Daten</span><span class="sxs-lookup"><span data-stu-id="1f029-129">Retrieve and present the data</span></span>

1. <span data-ttu-id="1f029-130">Öffnen Sie die Datei "MainWindow. XAML".</span><span class="sxs-lookup"><span data-stu-id="1f029-130">Open the MainWindow.xaml file.</span></span>

2. <span data-ttu-id="1f029-131">Legen Sie die- <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaft für den auf <xref:System.Windows.Window> 450 fest.</span><span class="sxs-lookup"><span data-stu-id="1f029-131">Set the <xref:System.Windows.FrameworkElement.Width%2A> property on the <xref:System.Windows.Window> to 450.</span></span>

3. <span data-ttu-id="1f029-132">Fügen Sie im XAML-Editor das folgende <xref:System.Windows.Controls.DataGrid> -Tag zwischen den `<Grid>` Tags und hinzu, `</Grid>` um einen mit dem Namen hinzuzufügen <xref:System.Windows.Controls.DataGrid> `dataGrid1` .</span><span class="sxs-lookup"><span data-stu-id="1f029-132">In the XAML editor, add the following <xref:System.Windows.Controls.DataGrid> tag between the `<Grid>` and `</Grid>` tags to add a <xref:System.Windows.Controls.DataGrid> named `dataGrid1`.</span></span>

     [!code-xaml[DataGrid_SQL_EF_Walkthrough#3](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#3)]

     <span data-ttu-id="1f029-133">![Fenster mit DataGrid](./media/datagrid-sql-ef-step6.png "DataGrid_SQL_EF_Step6")</span><span class="sxs-lookup"><span data-stu-id="1f029-133">![Window with DataGrid](./media/datagrid-sql-ef-step6.png "DataGrid_SQL_EF_Step6")</span></span>

4. <span data-ttu-id="1f029-134">Wählen Sie <xref:System.Windows.Window> aus.</span><span class="sxs-lookup"><span data-stu-id="1f029-134">Select the <xref:System.Windows.Window>.</span></span>

5. <span data-ttu-id="1f029-135">Erstellen Sie mit dem Eigenschaftenfenster-oder XAML-Editor einen Ereignishandler für das mit <xref:System.Windows.Window> `Window_Loaded` dem Namen für das- <xref:System.Windows.FrameworkElement.Loaded> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="1f029-135">Using the Properties window or XAML editor, create an event handler for the <xref:System.Windows.Window> named `Window_Loaded` for the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span> <span data-ttu-id="1f029-136">Weitere Informationen finden Sie unter Gewusst [wie: Erstellen eines einfachen Ereignis Handlers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="1f029-136">For more information, see [How to: Create a Simple Event Handler](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span></span>

     <span data-ttu-id="1f029-137">Der folgende Code zeigt das XAML für "MainWindow. XAML".</span><span class="sxs-lookup"><span data-stu-id="1f029-137">The following shows the XAML for MainWindow.xaml.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1f029-138">Wenn Sie Visual Basic verwenden, ersetzen Sie in der ersten Zeile der Datei "MainWindow. XAML" `x:Class="DataGridSQLExample.MainWindow"` durch `x:Class="MainWindow"` .</span><span class="sxs-lookup"><span data-stu-id="1f029-138">If you are using Visual Basic, in the first line of MainWindow.xaml, replace `x:Class="DataGridSQLExample.MainWindow"` with `x:Class="MainWindow"`.</span></span>

     [!code-xaml[DataGrid_SQL_EF_Walkthrough#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#1)]

6. <span data-ttu-id="1f029-139">Öffnen Sie die Code Behind-Datei (MainWindow. XAML. vb oder MainWindow.XAML.cs) für das <xref:System.Windows.Window> .</span><span class="sxs-lookup"><span data-stu-id="1f029-139">Open the code-behind file (MainWindow.xaml.vb or MainWindow.xaml.cs) for the <xref:System.Windows.Window>.</span></span>

7. <span data-ttu-id="1f029-140">Fügen Sie den folgenden Code hinzu, um nur bestimmte Werte aus den verbundenen Tabellen abzurufen, und legen Sie die- <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> Eigenschaft des-Objekts <xref:System.Windows.Controls.DataGrid> auf die Ergebnisse der Abfrage fest.</span><span class="sxs-lookup"><span data-stu-id="1f029-140">Add the following code to retrieve only specific values from the joined tables and set the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.DataGrid> to the results of the query.</span></span>

     [!code-csharp[DataGrid_SQL_EF_Walkthrough#2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml.cs#2)]
     [!code-vb[DataGrid_SQL_EF_Walkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/VB/MainWindow.xaml.vb#2)]

8. <span data-ttu-id="1f029-141">Führen Sie das Beispiel aus.</span><span class="sxs-lookup"><span data-stu-id="1f029-141">Run the example.</span></span>

     <span data-ttu-id="1f029-142">Es sollte ein <xref:System.Windows.Controls.DataGrid> angezeigt werden, in dem Daten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1f029-142">You should see a <xref:System.Windows.Controls.DataGrid> that displays data.</span></span>

     <span data-ttu-id="1f029-143">![DataGrid mit Daten aus SQL-Datenbank](./media/datagrid-sql-ef-step7.png "DataGrid_SQL_EF_Step7")</span><span class="sxs-lookup"><span data-stu-id="1f029-143">![DataGrid with data from SQL database](./media/datagrid-sql-ef-step7.png "DataGrid_SQL_EF_Step7")</span></span>

## <a name="see-also"></a><span data-ttu-id="1f029-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1f029-144">See also</span></span>

- <xref:System.Windows.Controls.DataGrid>
