---
title: 'Vorgehensweise: Anzahl, Summen oder Durchschnittswerten von Daten mithilfe von LINQ (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- average operator [LINQ in Visual Basic]
- aggregate operator [LINQ in Visual Basic]
- aggregate queries
- queries [LINQ in Visual Basic], sum results
- Aggregate clause [Visual Basic]
- sum operator [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], aggregate queries
- queries [LINQ in Visual Basic], counting results
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
- count operator [LINQ in Visual Basic]
ms.assetid: 51ca1f59-7770-4884-8b76-113002e54fc0
ms.openlocfilehash: 9b29c738a953bb6260357b1b67cc46a97eeb4369
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59313631"
---
# <a name="how-to-count-sum-or-average-data-by-using-linq-visual-basic"></a><span data-ttu-id="3bb19-102">Vorgehensweise: Anzahl, Summen oder Durchschnittswerten von Daten mithilfe von LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3bb19-102">How to: Count, Sum, or Average Data by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="3bb19-103">Language Integrated Query (LINQ) erleichtert den Zugriff auf Informationen und Ausführen von Abfragen.</span><span class="sxs-lookup"><span data-stu-id="3bb19-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="3bb19-104">Das folgende Beispiel zeigt, wie Sie eine neue Anwendung zu erstellen, die Abfragen für eine SQL Server-Datenbank ausführt.</span><span class="sxs-lookup"><span data-stu-id="3bb19-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span> <span data-ttu-id="3bb19-105">Das Beispiel zählt, summiert und Durchschnittswerte der Ergebnisse mithilfe der `Aggregate` und `Group By` Klauseln.</span><span class="sxs-lookup"><span data-stu-id="3bb19-105">The sample counts, sums, and averages the results by using the `Aggregate` and `Group By` clauses.</span></span> <span data-ttu-id="3bb19-106">Weitere Informationen finden Sie unter [Aggregate-Klausel](../../../../visual-basic/language-reference/queries/aggregate-clause.md) und [Group By-Klausel](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="3bb19-106">For more information, see [Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) and [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
 <span data-ttu-id="3bb19-107">In die Beispielen in diesem Thema verwenden die Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="3bb19-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="3bb19-108">Wenn Sie diese Datenbank nicht auf dem Entwicklungscomputer gespeichert haben, können Sie es aus dem Microsoft Download Center herunterladen.</span><span class="sxs-lookup"><span data-stu-id="3bb19-108">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="3bb19-109">Anweisungen hierzu finden Sie unter [Herunterladen von Beispieldatenbanken](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="3bb19-109">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="3bb19-110">Um eine Verbindung mit einer Datenbank zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3bb19-110">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="3bb19-111">Öffnen Sie in Visual Studio **Server-Explorer**/**Datenbank-Explorer** durch Klicken auf **Server-Explorer**/**Datenbank Explorer** auf die **Ansicht** Menü.</span><span class="sxs-lookup"><span data-stu-id="3bb19-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="3bb19-112">Mit der rechten Maustaste **Datenverbindungen** in **Server-Explorer**/**Datenbank-Explorer** , und klicken Sie dann auf **Verbindung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="3bb19-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="3bb19-113">Geben Sie eine gültige Verbindung mit der Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="3bb19-113">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="3bb19-114">Zum Hinzufügen eines Projekts, das eine LINQ to SQL-Datei enthält.</span><span class="sxs-lookup"><span data-stu-id="3bb19-114">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="3bb19-115">Zeigen Sie in Visual Studio im Menü **Datei** auf **Neu**, und klicken Sie auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="3bb19-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="3bb19-116">Wählen Sie Visual Basic **Windows Forms-Anwendung** als Projekttyp.</span><span class="sxs-lookup"><span data-stu-id="3bb19-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="3bb19-117">Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="3bb19-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="3bb19-118">Wählen Sie die **LINQ to SQL-Klassen** Elementvorlage.</span><span class="sxs-lookup"><span data-stu-id="3bb19-118">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="3bb19-119">Nennen Sie die Datei `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="3bb19-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="3bb19-120">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="3bb19-120">Click **Add**.</span></span> <span data-ttu-id="3bb19-121">Der Object Relational Designer (O/R Designer) wird für die Datei northwind.dbml geöffnet.</span><span class="sxs-lookup"><span data-stu-id="3bb19-121">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="3bb19-122">Hinzufügen von Tabellen zu Abfragen in den O/R-Designer</span><span class="sxs-lookup"><span data-stu-id="3bb19-122">To add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="3bb19-123">In **Server-Explorer**/**Datenbank-Explorer**, erweitern Sie die Verbindung zur Northwind-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="3bb19-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="3bb19-124">Erweitern Sie die **Tabellen** Ordner.</span><span class="sxs-lookup"><span data-stu-id="3bb19-124">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="3bb19-125">Wenn Sie den O/R-Designer geschlossen haben, können Sie sie durch Doppelklicken auf die Datei northwind.dbml, die Sie zuvor hinzugefügt haben erneut öffnen.</span><span class="sxs-lookup"><span data-stu-id="3bb19-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="3bb19-126">Klicken Sie auf der Customers-Tabelle aus, und ziehen Sie es in den linken Bereich des Designers.</span><span class="sxs-lookup"><span data-stu-id="3bb19-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="3bb19-127">Klicken Sie auf der Orders-Tabelle aus, und ziehen Sie es in den linken Bereich des Designers.</span><span class="sxs-lookup"><span data-stu-id="3bb19-127">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="3bb19-128">Der Designer erstellt neue `Customer` und `Order` Objekte für Ihr Projekt.</span><span class="sxs-lookup"><span data-stu-id="3bb19-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="3bb19-129">Beachten Sie, dass der Designer Beziehungen zwischen den Tabellen erkennt und untergeordnete Eigenschaften für verknüpfte Objekte erstellt automatisch aus.</span><span class="sxs-lookup"><span data-stu-id="3bb19-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="3bb19-130">Z. B. IntelliSense angezeigt, die die `Customer` Objekt verfügt über eine `Orders` -Eigenschaft für alle Bestellungen für diesen Kunden beziehen.</span><span class="sxs-lookup"><span data-stu-id="3bb19-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3. <span data-ttu-id="3bb19-131">Speichern Sie die Änderungen zu und schließen Sie den Designer.</span><span class="sxs-lookup"><span data-stu-id="3bb19-131">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="3bb19-132">Speichern Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="3bb19-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="3bb19-133">Hinzufügen von Code aus, um die Datenbank abzufragen und die Ergebnisse werden angezeigt</span><span class="sxs-lookup"><span data-stu-id="3bb19-133">To add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="3bb19-134">Von der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.DataGridView> Steuerelement auf das Standard-Windows-Formular für das Projekt, Form1.</span><span class="sxs-lookup"><span data-stu-id="3bb19-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="3bb19-135">Doppelklicken Sie auf Form1, um zum Hinzufügen von Code die `Load` -Ereignis des Formulars.</span><span class="sxs-lookup"><span data-stu-id="3bb19-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3. <span data-ttu-id="3bb19-136">Wenn Sie Tabellen in den O/R-Designer hinzugefügt haben, wird der Designer hinzugefügt eine <xref:System.Data.Linq.DataContext> Objekt für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="3bb19-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="3bb19-137">Dieses Objekt enthält den Code, den auf diese Tabellen zugreifen und den Zugriff auf einzelne Objekte und Auflistungen für jede Tabelle erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="3bb19-137">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="3bb19-138">Die <xref:System.Data.Linq.DataContext> Objekt für das Projekt mit dem Namen wird anhand des Namens der DBML-Datei.</span><span class="sxs-lookup"><span data-stu-id="3bb19-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="3bb19-139">Für dieses Projekt die <xref:System.Data.Linq.DataContext> Objekt mit dem Namen `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="3bb19-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="3bb19-140">Sie können eine Instanz von erstellen die <xref:System.Data.Linq.DataContext> in Ihrem Code und die Abfrage der Tabellen, die vom O/R-Designer angegeben.</span><span class="sxs-lookup"><span data-stu-id="3bb19-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="3bb19-141">Fügen Sie den folgenden Code der `Load` Ereignis, um die Tabellen zu Abfragen, die als Eigenschaften verfügbar gemacht werden Ihre <xref:System.Data.Linq.DataContext> und Anzahl, Summe und Mittelwert für die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="3bb19-141">Add the following code to the `Load` event to query the tables that are exposed as properties of your <xref:System.Data.Linq.DataContext> and count, sum, and average the results.</span></span> <span data-ttu-id="3bb19-142">Das Beispiel verwendet die `Aggregate` -Klausel, um die Abfrage für ein einzelnes Ergebnis, und die `Group By` -Klausel, um einen Durchschnittswert für anzeigen gruppiert die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="3bb19-142">The sample uses the `Aggregate` clause to query for a single result, and the `Group By` clause to show an average for grouped results.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form6.vb#13)]  
  
4. <span data-ttu-id="3bb19-143">Drücken Sie F5, um das Projekt ausführen und die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3bb19-143">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bb19-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3bb19-144">See also</span></span>

- [<span data-ttu-id="3bb19-145">LINQ</span><span class="sxs-lookup"><span data-stu-id="3bb19-145">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="3bb19-146">Abfragen</span><span class="sxs-lookup"><span data-stu-id="3bb19-146">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="3bb19-147">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="3bb19-147">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="3bb19-148">DataContext-Methoden (O/R-Designer)</span><span class="sxs-lookup"><span data-stu-id="3bb19-148">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [<span data-ttu-id="3bb19-149">Aggregate-Klausel</span><span class="sxs-lookup"><span data-stu-id="3bb19-149">Aggregate Clause</span></span>](../../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="3bb19-150">Group By-Klausel</span><span class="sxs-lookup"><span data-stu-id="3bb19-150">Group By Clause</span></span>](../../../../visual-basic/language-reference/queries/group-by-clause.md)
