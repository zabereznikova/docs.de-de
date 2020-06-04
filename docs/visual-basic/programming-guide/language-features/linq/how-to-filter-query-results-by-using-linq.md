---
title: 'Vorgehensweise: Filtern von Abfrageergebnissen unter Verwendung von LINQ'
ms.date: 07/20/2015
helpviewer_keywords:
- filtering [Visual Basic]
- filtering data [LINQ in Visual Basic]
- filtering [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], filtering results
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
- filtering data [Visual Basic]
ms.assetid: ef103092-9bed-4134-97f4-2db696e83c12
ms.openlocfilehash: 4d91783429f24abfe4149217542f8f7a6073bfef
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404990"
---
# <a name="how-to-filter-query-results-by-using-linq-visual-basic"></a><span data-ttu-id="c598f-102">Gewusst wie: Filtern von Abfrageergebnissen unter Verwendung von LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c598f-102">How to: Filter Query Results by Using LINQ (Visual Basic)</span></span>

<span data-ttu-id="c598f-103">Language-Integrated Query (LINQ) vereinfacht den Zugriff auf Datenbankinformationen und das Ausführen von Abfragen.</span><span class="sxs-lookup"><span data-stu-id="c598f-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>

<span data-ttu-id="c598f-104">Im folgenden Beispiel wird gezeigt, wie eine neue Anwendung erstellt wird, die Abfragen für eine SQL Server Datenbank ausführt und die Ergebnisse mithilfe der-Klausel nach einem bestimmten Wert filtert `Where` .</span><span class="sxs-lookup"><span data-stu-id="c598f-104">The following example shows how to create a new application that performs queries against a SQL Server database and filters the results by a particular value by using the `Where` clause.</span></span> <span data-ttu-id="c598f-105">Weitere Informationen finden Sie unter [WHERE-Klausel](../../../language-reference/queries/where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="c598f-105">For more information, see [Where Clause](../../../language-reference/queries/where-clause.md).</span></span>

<span data-ttu-id="c598f-106">In den Beispielen in diesem Thema wird die Beispieldatenbank Northwind verwendet.</span><span class="sxs-lookup"><span data-stu-id="c598f-106">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="c598f-107">Befindet sich diese Datenbank nicht auf Ihrem Entwicklungscomputer, können Sie sie aus dem Microsoft Download Center herunterladen.</span><span class="sxs-lookup"><span data-stu-id="c598f-107">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="c598f-108">Anweisungen hierzu finden Sie unter [Herunterladen von Beispiel Datenbanken](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="c598f-108">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="c598f-109">So erstellen Sie eine Verbindung mit einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="c598f-109">To create a connection to a database</span></span>

1. <span data-ttu-id="c598f-110">Öffnen Sie in Visual Studio **Server-Explorer** / **Datenbank-Explorer** , indem **Server Explorer**Sie / im Menü **Ansicht** auf Server-Explorer**Datenbank-Explorer** klicken.</span><span class="sxs-lookup"><span data-stu-id="c598f-110">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>

2. <span data-ttu-id="c598f-111">Klicken Sie in **Server-Explorer**Datenbank-Explorer mit der rechten Maustaste auf **Datenverbindungen** / **Database Explorer** und dann auf **Verbindung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="c598f-111">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>

3. <span data-ttu-id="c598f-112">Geben Sie eine gültige Verbindung mit der Northwind-Beispieldatenbank an.</span><span class="sxs-lookup"><span data-stu-id="c598f-112">Specify a valid connection to the Northwind sample database.</span></span>

## <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="c598f-113">So fügen Sie ein Projekt hinzu, das eine LINQ to SQL Datei enthält</span><span class="sxs-lookup"><span data-stu-id="c598f-113">To add a project that contains a LINQ to SQL file</span></span>

1. <span data-ttu-id="c598f-114">Zeigen Sie in Visual Studio im Menü **Datei** auf **neu** , und klicken Sie dann auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="c598f-114">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="c598f-115">Wählen Sie Visual Basic **Windows Forms Anwendung** als Projekttyp aus.</span><span class="sxs-lookup"><span data-stu-id="c598f-115">Select Visual Basic **Windows Forms Application** as the project type.</span></span>

2. <span data-ttu-id="c598f-116">Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="c598f-116">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="c598f-117">Wählen Sie die Element Vorlage **LINQ to SQL Klassen** aus.</span><span class="sxs-lookup"><span data-stu-id="c598f-117">Select the **LINQ to SQL Classes** item template.</span></span>

3. <span data-ttu-id="c598f-118">Benennen Sie die Datei mit `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="c598f-118">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="c598f-119">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="c598f-119">Click **Add**.</span></span> <span data-ttu-id="c598f-120">Der objektrelationaler Designer (O/R-Designer) wird für die Datei "Northwind. dbml" geöffnet.</span><span class="sxs-lookup"><span data-stu-id="c598f-120">The Object Relational Designer (O/R Designer) opens for the northwind.dbml file.</span></span>

## <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="c598f-121">So fügen Sie dem O/R-Designer abzufragende Tabellen hinzu</span><span class="sxs-lookup"><span data-stu-id="c598f-121">To add tables to query to the O/R Designer</span></span>

1. <span data-ttu-id="c598f-122">Erweitern Sie in **Server-Explorer** / **Datenbank-Explorer**die Verbindung mit der Northwind-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="c598f-122">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="c598f-123">Erweitern Sie den Ordner **Tabellen** .</span><span class="sxs-lookup"><span data-stu-id="c598f-123">Expand the **Tables** folder.</span></span>

     <span data-ttu-id="c598f-124">Wenn Sie den O/R-Designer geschlossen haben, können Sie ihn erneut öffnen, indem Sie auf die Datei Northwind. dbml, die Sie zuvor hinzugefügt haben, doppelklicken.</span><span class="sxs-lookup"><span data-stu-id="c598f-124">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>

2. <span data-ttu-id="c598f-125">Klicken Sie auf die Tabelle Customers, und ziehen Sie Sie in den linken Bereich des Designers.</span><span class="sxs-lookup"><span data-stu-id="c598f-125">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="c598f-126">Klicken Sie auf die Tabelle Orders, und ziehen Sie Sie in den linken Bereich des Designers.</span><span class="sxs-lookup"><span data-stu-id="c598f-126">Click the Orders table and drag it to the left pane of the designer.</span></span>

     <span data-ttu-id="c598f-127">Der Designer erstellt neue `Customer` - `Order` Objekte und-Objekte für Ihr Projekt.</span><span class="sxs-lookup"><span data-stu-id="c598f-127">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="c598f-128">Beachten Sie, dass der Designer automatisch Beziehungen zwischen den Tabellen erkennt und untergeordnete Eigenschaften für verbundene Objekte erstellt.</span><span class="sxs-lookup"><span data-stu-id="c598f-128">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="c598f-129">IntelliSense zeigt beispielsweise, dass das- `Customer` Objekt über eine- `Orders` Eigenschaft für alle Bestellungen verfügt, die mit diesem Kunden verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="c598f-129">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>

3. <span data-ttu-id="c598f-130">Speichern Sie die Änderungen, und schließen Sie den Designer.</span><span class="sxs-lookup"><span data-stu-id="c598f-130">Save your changes and close the designer.</span></span>

4. <span data-ttu-id="c598f-131">Speichern Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="c598f-131">Save your project.</span></span>

## <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="c598f-132">So fügen Sie Code hinzu, um die Datenbank abzufragen und die Ergebnisse anzuzeigen</span><span class="sxs-lookup"><span data-stu-id="c598f-132">To add code to query the database and display the results</span></span>

1. <span data-ttu-id="c598f-133">Ziehen Sie aus der **Toolbox**ein- <xref:System.Windows.Forms.DataGridView> Steuerelement auf das Windows-Standardformular für das Projekt, Form1.</span><span class="sxs-lookup"><span data-stu-id="c598f-133">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>

2. <span data-ttu-id="c598f-134">Doppelklicken Sie auf Form1, um dem- `Load` Ereignis des Formulars Code hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="c598f-134">Double-click Form1 to add code to the `Load` event of the form.</span></span>

3. <span data-ttu-id="c598f-135">Wenn Sie dem O/R-Designer Tabellen hinzugefügt haben, hat der Designer ein- <xref:System.Data.Linq.DataContext> Objekt für das Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c598f-135">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="c598f-136">Dieses Objekt enthält den Code, den Sie für den Zugriff auf diese Tabellen benötigen, zusätzlich zu den einzelnen Objekten und Auflistungen für jede Tabelle.</span><span class="sxs-lookup"><span data-stu-id="c598f-136">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="c598f-137">Das- <xref:System.Data.Linq.DataContext> Objekt für das Projekt wird basierend auf dem Namen der DBML-Datei benannt.</span><span class="sxs-lookup"><span data-stu-id="c598f-137">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="c598f-138">Für dieses Projekt hat das <xref:System.Data.Linq.DataContext> Objekt den Namen `northwindDataContext` .</span><span class="sxs-lookup"><span data-stu-id="c598f-138">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>

    <span data-ttu-id="c598f-139">Sie können eine Instanz von <xref:System.Data.Linq.DataContext> im Code erstellen und die im O/R-Designer angegebenen Tabellen Abfragen.</span><span class="sxs-lookup"><span data-stu-id="c598f-139">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>

    <span data-ttu-id="c598f-140">Fügen Sie dem-Ereignis den folgenden Code hinzu `Load` , um die Tabellen abzufragen, die als Eigenschaften des Daten Kontexts verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="c598f-140">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context.</span></span> <span data-ttu-id="c598f-141">Die Abfrage filtert die Ergebnisse und gibt nur Kunden zurück, die sich in befinden `London` .</span><span class="sxs-lookup"><span data-stu-id="c598f-141">The query filters the results and returns only customers that are located in `London`.</span></span>

    [!code-vb[VbLINQToSQLHowTos#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form5.vb#11)]

4. <span data-ttu-id="c598f-142">Drücken Sie F5, um das Projekt auszuführen und die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c598f-142">Press F5 to run your project and view the results.</span></span>

5. <span data-ttu-id="c598f-143">Im folgenden finden Sie einige weitere Filter, die Sie ausprobieren können.</span><span class="sxs-lookup"><span data-stu-id="c598f-143">Following are some other filters that you can try.</span></span>

    [!code-vb[VbLINQToSQLHowTos#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form5.vb#12)]

## <a name="see-also"></a><span data-ttu-id="c598f-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c598f-144">See also</span></span>

- [<span data-ttu-id="c598f-145">LINQ</span><span class="sxs-lookup"><span data-stu-id="c598f-145">LINQ</span></span>](index.md)
- [<span data-ttu-id="c598f-146">Abfragen</span><span class="sxs-lookup"><span data-stu-id="c598f-146">Queries</span></span>](../../../language-reference/queries/index.md)
- [<span data-ttu-id="c598f-147">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="c598f-147">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="c598f-148">DataContext-Methoden (O/R-Designer)</span><span class="sxs-lookup"><span data-stu-id="c598f-148">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
