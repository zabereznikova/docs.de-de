---
title: 'Gewusst wie: Filtern von Abfrageergebnissen unter Verwendung von LINQ (Visual Basic)'
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
ms.openlocfilehash: 8e051d583cdaeb04190e4499834a052fa41d1c48
ms.sourcegitcommit: d955cb4c681d68cf301d410925d83f25172ece86
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/07/2018
ms.locfileid: "34827208"
---
# <a name="how-to-filter-query-results-by-using-linq-visual-basic"></a><span data-ttu-id="f0119-102">Gewusst wie: Filtern von Abfrageergebnissen unter Verwendung von LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f0119-102">How to: Filter Query Results by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="f0119-103">Language-Integrated Query (LINQ) erleichtert die Datenbankinformationen zugreifen und Ausführen von Abfragen.</span><span class="sxs-lookup"><span data-stu-id="f0119-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="f0119-104">Im folgende Beispiel wird gezeigt, wie eine neue Anwendung erstellen, die eine SQL Server-Datenbank abfragt und filtert die Ergebnisse nach einem bestimmten Wert mithilfe der `Where` Klausel.</span><span class="sxs-lookup"><span data-stu-id="f0119-104">The following example shows how to create a new application that performs queries against a SQL Server database and filters the results by a particular value by using the `Where` clause.</span></span> <span data-ttu-id="f0119-105">Weitere Informationen finden Sie unter [Where-Klausel](../../../../visual-basic/language-reference/queries/where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="f0119-105">For more information, see [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).</span></span>  
  
 <span data-ttu-id="f0119-106">In den Beispielen in diesem Thema verwenden die Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="f0119-106">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="f0119-107">Wenn Sie diese Datenbank nicht auf Ihrem Computer verfügen, können Sie es aus dem Microsoft Download Center herunterladen.</span><span class="sxs-lookup"><span data-stu-id="f0119-107">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="f0119-108">Anweisungen hierzu finden Sie unter [Herunterladen von Beispieldatenbanken](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="f0119-108">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="f0119-109">So erstellen eine Verbindung mit einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="f0119-109">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="f0119-110">Öffnen Sie in Visual Studio **Server-Explorer**/**Datenbank-Explorer** durch Klicken auf **Server-Explorer**/**Datenbank Explorer** auf die **Ansicht** Menü.</span><span class="sxs-lookup"><span data-stu-id="f0119-110">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="f0119-111">Mit der rechten Maustaste **Datenverbindungen** in **Server-Explorer**/**Datenbank-Explorer** , und klicken Sie dann auf **Verbindung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f0119-111">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="f0119-112">Geben Sie eine gültige Verbindung mit der Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="f0119-112">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="f0119-113">Ein Projekt hinzufügen, die eine LINQ to SQL-Datei enthält.</span><span class="sxs-lookup"><span data-stu-id="f0119-113">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="f0119-114">Zeigen Sie in Visual Studio im Menü **Datei** auf **Neu**, und klicken Sie auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="f0119-114">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="f0119-115">Wählen Sie Visual Basic **Windows Forms-Anwendung** als Projekttyp.</span><span class="sxs-lookup"><span data-stu-id="f0119-115">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="f0119-116">Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f0119-116">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="f0119-117">Wählen Sie die **LINQ to SQL-Klassen** Elementvorlage.</span><span class="sxs-lookup"><span data-stu-id="f0119-117">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="f0119-118">Nennen Sie die Datei `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="f0119-118">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="f0119-119">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f0119-119">Click **Add**.</span></span> <span data-ttu-id="f0119-120">Der Object Relational Designer (O/R-Designer) wird für die Datei northwind.dbml geöffnet.</span><span class="sxs-lookup"><span data-stu-id="f0119-120">The Object Relational Designer (O/R Designer) opens for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="f0119-121">Hinzufügen von Tabellen zu Abfragen in den O/R-Designer</span><span class="sxs-lookup"><span data-stu-id="f0119-121">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="f0119-122">In **Server-Explorer**/**Datenbank-Explorer**, erweitern Sie die Verbindung mit der Datenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="f0119-122">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="f0119-123">Erweitern Sie die **Tabellen** Ordner.</span><span class="sxs-lookup"><span data-stu-id="f0119-123">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="f0119-124">Wenn Sie im O/R-Designer geschlossen haben, können Sie es durch Doppelklicken auf die Datei northwind.dbml, die Sie zuvor hinzugefügt haben erneut öffnen.</span><span class="sxs-lookup"><span data-stu-id="f0119-124">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="f0119-125">Klicken Sie auf der Customers-Tabelle, und ziehen Sie es in den linken Bereich des Designers.</span><span class="sxs-lookup"><span data-stu-id="f0119-125">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="f0119-126">Klicken Sie auf die Orders-Tabelle, und ziehen Sie es in den linken Bereich des Designers.</span><span class="sxs-lookup"><span data-stu-id="f0119-126">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="f0119-127">Der Designer erstellt neue `Customer` und `Order` Objekte für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="f0119-127">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="f0119-128">Beachten Sie, dass der Designer Beziehungen zwischen den Tabellen erkennt automatisch und untergeordneten Eigenschaften für verwandte Objekte erstellt.</span><span class="sxs-lookup"><span data-stu-id="f0119-128">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="f0119-129">Z. B. IntelliSense wird angezeigt, die `Customer` Objekt verfügt über eine `Orders` -Eigenschaft für alle Aufträge im Zusammenhang mit diesen Kunden.</span><span class="sxs-lookup"><span data-stu-id="f0119-129">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3.  <span data-ttu-id="f0119-130">Speichern Sie die Änderungen zu und schließen Sie den Designer.</span><span class="sxs-lookup"><span data-stu-id="f0119-130">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="f0119-131">Speichern Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="f0119-131">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="f0119-132">Hinzufügen von Code aus, um die Datenbank abzufragen und die Ergebnisse werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f0119-132">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="f0119-133">Aus der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.DataGridView> -Steuerelement auf die Standard-Windows Form für das Projekt, Form1.</span><span class="sxs-lookup"><span data-stu-id="f0119-133">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="f0119-134">Doppelklicken Sie auf Form1, um zum Hinzufügen von Code die `Load` -Ereignis des Formulars.</span><span class="sxs-lookup"><span data-stu-id="f0119-134">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3.  <span data-ttu-id="f0119-135">Wenn Sie Tabellen in den O/R-Designer hinzugefügt haben, wird der Designer hinzugefügt ein <xref:System.Data.Linq.DataContext> Objekt für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="f0119-135">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="f0119-136">Dieses Objekt enthält den Code, den Sie für den Zugriff auf diese Tabellen, zusätzlich zu den einzelnen Objekte und Sammlungen für jede Tabelle benötigen.</span><span class="sxs-lookup"><span data-stu-id="f0119-136">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="f0119-137">Die <xref:System.Data.Linq.DataContext> Objekt für das Projekt mit der Bezeichnung wird anhand des Namens der DBML-Datei.</span><span class="sxs-lookup"><span data-stu-id="f0119-137">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="f0119-138">Für dieses Projekt die <xref:System.Data.Linq.DataContext> Objekt heißt `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="f0119-138">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="f0119-139">Erstellen eine Instanz von der <xref:System.Data.Linq.DataContext> in Ihren Code und die Abfrage die Tabellen, die vom O/R-Designer angegeben.</span><span class="sxs-lookup"><span data-stu-id="f0119-139">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="f0119-140">Fügen Sie folgenden Code, der `Load` Ereignis, um die Tabellen Abfragen, die als Eigenschaften des Datenkontexts verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="f0119-140">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context.</span></span> <span data-ttu-id="f0119-141">Die Abfrage filtert die Ergebnisse und gibt nur die Kunden, die in befinden `London`.</span><span class="sxs-lookup"><span data-stu-id="f0119-141">The query filters the results and returns only customers that are located in `London`.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#11](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-filter-query-results-by-using-linq_1.vb)]  
  
4.  <span data-ttu-id="f0119-142">Drücken Sie F5, um das Projekt auszuführen und die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f0119-142">Press F5 to run your project and view the results.</span></span>  
  
5.  <span data-ttu-id="f0119-143">Im folgenden werden einige andere Filter, die Sie ausprobieren können.</span><span class="sxs-lookup"><span data-stu-id="f0119-143">Following are some other filters that you can try.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#12](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-filter-query-results-by-using-linq_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="f0119-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0119-144">See Also</span></span>  
 [<span data-ttu-id="f0119-145">LINQ</span><span class="sxs-lookup"><span data-stu-id="f0119-145">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="f0119-146">Abfragen</span><span class="sxs-lookup"><span data-stu-id="f0119-146">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="f0119-147">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="f0119-147">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)  
 [<span data-ttu-id="f0119-148">DataContext-Methoden (O/R-Designer)</span><span class="sxs-lookup"><span data-stu-id="f0119-148">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
