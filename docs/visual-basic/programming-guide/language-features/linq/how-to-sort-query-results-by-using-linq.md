---
title: 'Gewusst wie: Sortieren von Abfrageergebnissen unter Verwendung von LINQ (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- sorting query results, multiple columns
- sorting data [Visual Basic]
- sorting data [LINQ in Visual Basic]
- sorting query results [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], sorting results
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: 07a4584d-9fd8-4a1d-b7d9-ccf2efa5c84e
ms.openlocfilehash: 5104ef5714819bd69cfd5b6d754e81b97f235e31
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2018
ms.locfileid: "43000201"
---
# <a name="how-to-sort-query-results-by-using-linq-visual-basic"></a><span data-ttu-id="9a546-102">Gewusst wie: Sortieren von Abfrageergebnissen unter Verwendung von LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9a546-102">How to: Sort Query Results by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="9a546-103">Language Integrated Query (LINQ) erleichtert den Zugriff auf Informationen und Ausführen von Abfragen.</span><span class="sxs-lookup"><span data-stu-id="9a546-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="9a546-104">Das folgende Beispiel zeigt, wie Sie eine neue Anwendung zu erstellen, führt Abfragen in SQL Server-Datenbank und die Ergebnisse nach mehreren Feldern sortiert, mithilfe, der `Order By` Klausel.</span><span class="sxs-lookup"><span data-stu-id="9a546-104">The following example shows how to create a new application that performs queries against a SQL Server database and sorts the results by multiple fields by using the `Order By` clause.</span></span> <span data-ttu-id="9a546-105">Die Sortierreihenfolge für jedes Feld kann aufsteigend oder absteigend werden.</span><span class="sxs-lookup"><span data-stu-id="9a546-105">The sort order for each field can be ascending order or descending order.</span></span> <span data-ttu-id="9a546-106">Weitere Informationen finden Sie unter [Order By-Klausel](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="9a546-106">For more information, see [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="9a546-107">In die Beispielen in diesem Thema verwenden die Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="9a546-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="9a546-108">Wenn Sie diese Datenbank nicht auf dem Entwicklungscomputer gespeichert haben, können Sie es aus dem Microsoft Download Center herunterladen.</span><span class="sxs-lookup"><span data-stu-id="9a546-108">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="9a546-109">Anweisungen hierzu finden Sie unter [Herunterladen von Beispieldatenbanken](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="9a546-109">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="9a546-110">Um eine Verbindung mit einer Datenbank zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9a546-110">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="9a546-111">Öffnen Sie in Visual Studio **Server-Explorer**/**Datenbank-Explorer** durch Klicken auf **Server-Explorer**/**Datenbank Explorer** auf die **Ansicht** Menü.</span><span class="sxs-lookup"><span data-stu-id="9a546-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="9a546-112">Mit der rechten Maustaste **Datenverbindungen** in **Server-Explorer**/**Datenbank-Explorer** , und klicken Sie dann auf **Verbindung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="9a546-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="9a546-113">Geben Sie eine gültige Verbindung mit der Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="9a546-113">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="9a546-114">Zum Hinzufügen eines Projekts, das eine LINQ to SQL-Datei enthält.</span><span class="sxs-lookup"><span data-stu-id="9a546-114">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="9a546-115">Zeigen Sie in Visual Studio im Menü **Datei** auf **Neu**, und klicken Sie auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="9a546-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="9a546-116">Wählen Sie Visual Basic **Windows Forms-Anwendung** als Projekttyp.</span><span class="sxs-lookup"><span data-stu-id="9a546-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="9a546-117">Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="9a546-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="9a546-118">Wählen Sie die **LINQ to SQL-Klassen** Elementvorlage.</span><span class="sxs-lookup"><span data-stu-id="9a546-118">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="9a546-119">Nennen Sie die Datei `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="9a546-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="9a546-120">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="9a546-120">Click **Add**.</span></span> <span data-ttu-id="9a546-121">Der Object Relational Designer (O/R Designer) wird für die Datei northwind.dbml geöffnet.</span><span class="sxs-lookup"><span data-stu-id="9a546-121">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="9a546-122">Hinzufügen von Tabellen zu Abfragen in den O/R-Designer</span><span class="sxs-lookup"><span data-stu-id="9a546-122">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="9a546-123">In **Server-Explorer**/**Datenbank-Explorer**, erweitern Sie die Verbindung zur Northwind-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="9a546-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="9a546-124">Erweitern Sie die **Tabellen** Ordner.</span><span class="sxs-lookup"><span data-stu-id="9a546-124">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="9a546-125">Wenn Sie den O/R-Designer geschlossen haben, können Sie sie durch Doppelklicken auf die Datei northwind.dbml, die Sie zuvor hinzugefügt haben erneut öffnen.</span><span class="sxs-lookup"><span data-stu-id="9a546-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="9a546-126">Klicken Sie auf der Customers-Tabelle aus, und ziehen Sie es in den linken Bereich des Designers.</span><span class="sxs-lookup"><span data-stu-id="9a546-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="9a546-127">Klicken Sie auf der Orders-Tabelle aus, und ziehen Sie es in den linken Bereich des Designers.</span><span class="sxs-lookup"><span data-stu-id="9a546-127">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="9a546-128">Der Designer erstellt neue `Customer` und `Order` Objekte für Ihr Projekt.</span><span class="sxs-lookup"><span data-stu-id="9a546-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="9a546-129">Beachten Sie, dass der Designer Beziehungen zwischen den Tabellen erkennt und untergeordnete Eigenschaften für verknüpfte Objekte erstellt automatisch aus.</span><span class="sxs-lookup"><span data-stu-id="9a546-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="9a546-130">Z. B. IntelliSense angezeigt, die die `Customer` Objekt verfügt über eine `Orders` -Eigenschaft für alle Bestellungen für diesen Kunden beziehen.</span><span class="sxs-lookup"><span data-stu-id="9a546-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3.  <span data-ttu-id="9a546-131">Speichern Sie die Änderungen zu und schließen Sie den Designer.</span><span class="sxs-lookup"><span data-stu-id="9a546-131">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="9a546-132">Speichern Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="9a546-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="9a546-133">Hinzufügen von Code aus, um die Datenbank abzufragen und die Ergebnisse werden angezeigt</span><span class="sxs-lookup"><span data-stu-id="9a546-133">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="9a546-134">Von der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.DataGridView> Steuerelement auf das Standard-Windows-Formular für das Projekt, Form1.</span><span class="sxs-lookup"><span data-stu-id="9a546-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="9a546-135">Doppelklicken Sie auf Form1, um zum Hinzufügen von Code die `Load` -Ereignis des Formulars.</span><span class="sxs-lookup"><span data-stu-id="9a546-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3.  <span data-ttu-id="9a546-136">Wenn Sie Tabellen in den O/R-Designer hinzugefügt haben, wird der Designer hinzugefügt eine <xref:System.Data.Linq.DataContext> Objekt, das Ihr Projekt.</span><span class="sxs-lookup"><span data-stu-id="9a546-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="9a546-137">Dieses Objekt enthält den Code, den auf diese Tabellen zugreifen und den Zugriff auf einzelne Objekte und Auflistungen für jede Tabelle erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="9a546-137">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="9a546-138">Die <xref:System.Data.Linq.DataContext> Objekt für das Projekt mit dem Namen wird anhand des Namens der DBML-Datei.</span><span class="sxs-lookup"><span data-stu-id="9a546-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="9a546-139">Für dieses Projekt die <xref:System.Data.Linq.DataContext> Objekt mit dem Namen `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="9a546-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="9a546-140">Sie können eine Instanz von erstellen die <xref:System.Data.Linq.DataContext> in Ihrem Code und die Abfrage der Tabellen, die vom O/R-Designer angegeben.</span><span class="sxs-lookup"><span data-stu-id="9a546-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="9a546-141">Fügen Sie den folgenden Code der `Load` Ereignis, um die Tabellen zu Abfragen, die als Eigenschaften des Datenkontexts verfügbar gemacht werden und die Ergebnisse sortieren.</span><span class="sxs-lookup"><span data-stu-id="9a546-141">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context and sort the results.</span></span> <span data-ttu-id="9a546-142">Durch die Anzahl der Bestellungen für Kunden, in absteigender Reihenfolge sortiert die Abfrage die Ergebnisse auf.</span><span class="sxs-lookup"><span data-stu-id="9a546-142">The query sorts the results by the number of customer orders, in descending order.</span></span> <span data-ttu-id="9a546-143">Kunden, die die gleiche von Bestellungen Anzahl sind nach Unternehmensnamen in aufsteigender Reihenfolge (Standard) sortiert.</span><span class="sxs-lookup"><span data-stu-id="9a546-143">Customers that have the same number of orders are ordered by company name in ascending order (the default).</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#10](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-sort-query-results-by-using-linq_1.vb)]  
  
4.  <span data-ttu-id="9a546-144">Drücken Sie F5, um das Projekt ausführen und die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9a546-144">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a546-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a546-145">See Also</span></span>  
 [<span data-ttu-id="9a546-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="9a546-146">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="9a546-147">Abfragen</span><span class="sxs-lookup"><span data-stu-id="9a546-147">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)  
 [<span data-ttu-id="9a546-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="9a546-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)  
 [<span data-ttu-id="9a546-149">DataContext-Methoden (O/R-Designer)</span><span class="sxs-lookup"><span data-stu-id="9a546-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
