---
title: 'Gewusst wie: Suchen des minimalen oder maximalen Werts in einem Abfrageergebnis mithilfe von LINQ'
ms.date: 07/20/2015
helpviewer_keywords:
- max operator [LINQ in Visual Basic]
- aggregate operator [LINQ in Visual Basic]
- aggregate queries
- minimum values [LINQ in Visual Basic]
- min operator [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], minimum and maximum values
- Max property
- maximum values [LINQ in Visual Basic]
- Aggregate clause [Visual Basic]
- queries [LINQ in Visual Basic], aggregate queries
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 238b763b-7dcd-4b14-8050-b65500a4f71c
ms.openlocfilehash: ef5f218cdcc7275f616486110825ad0b9df11cc3
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112361"
---
# <a name="how-to-find-the-minimum-or-maximum-value-in-a-query-result-by-using-linq-visual-basic"></a><span data-ttu-id="fe1dd-102">Gewusst wie: Suchen des minimalen oder maximalen Werts in einem Abfrageergebnis mithilfe von LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fe1dd-102">How to: Find the Minimum or Maximum Value in a Query Result by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="fe1dd-103">Language-Integrated Query (LINQ) erleichtert den Zugriff auf Datenbankinformationen und das Ausführen von Abfragen.</span><span class="sxs-lookup"><span data-stu-id="fe1dd-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="fe1dd-104">Das folgende Beispiel zeigt, wie Sie eine neue Anwendung erstellen, die Abfragen für eine SQL Server-Datenbank ausführt.</span><span class="sxs-lookup"><span data-stu-id="fe1dd-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span> <span data-ttu-id="fe1dd-105">Die Stichprobe bestimmt die minimalen und maximalen `Aggregate` `Group By` Werte für die Ergebnisse mithilfe der und-Klauseln.</span><span class="sxs-lookup"><span data-stu-id="fe1dd-105">The sample determines the minimum and maximum values for the results by using the `Aggregate` and `Group By` clauses.</span></span> <span data-ttu-id="fe1dd-106">Weitere Informationen finden Sie unter [Aggregatklausel](../../../../visual-basic/language-reference/queries/aggregate-clause.md) und [Gruppenklausel](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="fe1dd-106">For more information, see [Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) and [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
 <span data-ttu-id="fe1dd-107">In den Beispielen in diesem Thema wird die Northwind-Beispieldatenbank verwendet.</span><span class="sxs-lookup"><span data-stu-id="fe1dd-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="fe1dd-108">Befindet sich diese Datenbank nicht auf Ihrem Entwicklungscomputer, können Sie sie aus dem Microsoft Download Center herunterladen.</span><span class="sxs-lookup"><span data-stu-id="fe1dd-108">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="fe1dd-109">Anweisungen finden Sie unter [Herunterladen von Beispieldatenbanken](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="fe1dd-109">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="create-a-connection-to-a-database"></a><span data-ttu-id="fe1dd-110">Erstellen einer Verbindung zu einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="fe1dd-110">Create a connection to a database</span></span>  
  
1. <span data-ttu-id="fe1dd-111">Öffnen Sie in Visual Studio den/Server**Explorer-Datenbank-Explorer,** **Server Explorer**/indem Sie im Menü **Ansicht** auf den **Server-Explorer-Datenbank-Explorer**klicken.**Database Explorer**</span><span class="sxs-lookup"><span data-stu-id="fe1dd-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="fe1dd-112">Klicken Sie im **Server**/**Explorer-Datenbank-Explorer** mit der rechten Maustaste auf **Datenverbindungen,** und klicken Sie dann auf **Verbindung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="fe1dd-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="fe1dd-113">Geben Sie eine gültige Verbindung zur Northwind-Beispieldatenbank an.</span><span class="sxs-lookup"><span data-stu-id="fe1dd-113">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="fe1dd-114">So fügen Sie ein Projekt hinzu, das eine LINQ zu SQL-Datei enthält</span><span class="sxs-lookup"><span data-stu-id="fe1dd-114">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="fe1dd-115">Zeigen Sie in Visual Studio im Menü **Datei** auf **Neu,** und klicken Sie dann auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="fe1dd-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="fe1dd-116">Wählen Sie Visual Basic **Windows Forms Application** als Projekttyp aus.</span><span class="sxs-lookup"><span data-stu-id="fe1dd-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="fe1dd-117">Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="fe1dd-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="fe1dd-118">Wählen Sie die Elementvorlage **LINQ zu SQL Classes** aus.</span><span class="sxs-lookup"><span data-stu-id="fe1dd-118">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="fe1dd-119">Benennen Sie die Datei `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="fe1dd-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="fe1dd-120">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="fe1dd-120">Click **Add**.</span></span> <span data-ttu-id="fe1dd-121">Der Object Relational Designer (O/R Designer) wird für die Datei northwind.dbml geöffnet.</span><span class="sxs-lookup"><span data-stu-id="fe1dd-121">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
## <a name="add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="fe1dd-122">Hinzufügen von Tabellen zur Abfrage zum O/R-Designer</span><span class="sxs-lookup"><span data-stu-id="fe1dd-122">Add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="fe1dd-123">Erweitern Sie im Server/**Explorer-Datenbank-Explorer**die Verbindung zur Northwind-Datenbank. **Server Explorer**</span><span class="sxs-lookup"><span data-stu-id="fe1dd-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="fe1dd-124">Erweitern Sie den Ordner **Tabellen** .</span><span class="sxs-lookup"><span data-stu-id="fe1dd-124">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="fe1dd-125">Wenn Sie den O/R-Designer geschlossen haben, können Sie ihn erneut öffnen, indem Sie auf die Datei northwind.dbml doppelklicken, die Sie zuvor hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="fe1dd-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="fe1dd-126">Klicken Sie auf die Tabelle Kunden, und ziehen Sie sie in den linken Bereich des Designers.</span><span class="sxs-lookup"><span data-stu-id="fe1dd-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="fe1dd-127">Klicken Sie auf die Tabelle Aufträge, und ziehen Sie sie in den linken Bereich des Designers.</span><span class="sxs-lookup"><span data-stu-id="fe1dd-127">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="fe1dd-128">Der Designer `Customer` erstellt `Order` neue Objekte und Objekte für Ihr Projekt.</span><span class="sxs-lookup"><span data-stu-id="fe1dd-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="fe1dd-129">Beachten Sie, dass der Designer automatisch Beziehungen zwischen den Tabellen erkennt und untergeordnete Eigenschaften für verwandte Objekte erstellt.</span><span class="sxs-lookup"><span data-stu-id="fe1dd-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="fe1dd-130">IntelliSense zeigt beispielsweise an, `Customer` dass `Orders` das Objekt über eine Eigenschaft für alle Aufträge verfügt, die sich auf diesen Kunden beziehen.</span><span class="sxs-lookup"><span data-stu-id="fe1dd-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3. <span data-ttu-id="fe1dd-131">Speichern Sie Ihre Änderungen, und schließen Sie den Designer.</span><span class="sxs-lookup"><span data-stu-id="fe1dd-131">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="fe1dd-132">Speichern Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="fe1dd-132">Save your project.</span></span>  
  
## <a name="add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="fe1dd-133">Hinzufügen von Code zum Abfragen der Datenbank und Anzeigen der Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="fe1dd-133">Add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="fe1dd-134">Ziehen **Toolbox**Sie aus <xref:System.Windows.Forms.DataGridView> der Toolbox ein Steuerelement auf das Standard-Windows-Formular für Ihr Projekt, Form1.</span><span class="sxs-lookup"><span data-stu-id="fe1dd-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="fe1dd-135">Doppelklicken Sie auf Form1, `Load` um code zum Ereignis des Formulars hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="fe1dd-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3. <span data-ttu-id="fe1dd-136">Beim Hinzugefügt von Tabellen zum O/R-Designer <xref:System.Data.Linq.DataContext> hat der Designer ein Objekt für Ihr Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="fe1dd-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="fe1dd-137">Dieses Objekt enthält den Code, auf den Sie für diese Tabellen zugreifen müssen, zusätzlich zu einzelnen Objekten und Auflistungen für jede Tabelle.</span><span class="sxs-lookup"><span data-stu-id="fe1dd-137">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="fe1dd-138">Das <xref:System.Data.Linq.DataContext> Objekt für Ihr Projekt wird basierend auf dem Namen Ihrer DBml-Datei benannt.</span><span class="sxs-lookup"><span data-stu-id="fe1dd-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="fe1dd-139">Für dieses Projekt <xref:System.Data.Linq.DataContext> heißt `northwindDataContext`das Objekt .</span><span class="sxs-lookup"><span data-stu-id="fe1dd-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="fe1dd-140">Sie können eine Instanz <xref:System.Data.Linq.DataContext> des in Ihrem Code erstellen und die vom O/R-Designer angegebenen Tabellen abfragen.</span><span class="sxs-lookup"><span data-stu-id="fe1dd-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="fe1dd-141">Fügen Sie dem `Load` Ereignis den folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="fe1dd-141">Add the following code to the `Load` event.</span></span> <span data-ttu-id="fe1dd-142">Dieser Code fragt die Tabellen ab, die als Eigenschaften des Datenkontexts verfügbar gemacht werden, und bestimmt die minimalen und maximalen Werte für die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="fe1dd-142">This code queries the tables that are exposed as properties of your data context and determines the minimum and maximum values for the results.</span></span> <span data-ttu-id="fe1dd-143">Das Beispiel `Aggregate` verwendet die Klausel, um ein `Group By` einzelnes Ergebnis abzufragen, und die Klausel, um einen Durchschnitt für gruppierte Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fe1dd-143">The sample uses the `Aggregate` clause to query for a single result, and the `Group By` clause to show an average for grouped results.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form7.vb#14)]  
  
4. <span data-ttu-id="fe1dd-144">Drücken Sie **F5,** um das Projekt auszuführen und die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fe1dd-144">Press **F5** to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe1dd-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fe1dd-145">See also</span></span>

- [<span data-ttu-id="fe1dd-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="fe1dd-146">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="fe1dd-147">Abfragen</span><span class="sxs-lookup"><span data-stu-id="fe1dd-147">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="fe1dd-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="fe1dd-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="fe1dd-149">DataContext-Methoden (O/R-Designer)</span><span class="sxs-lookup"><span data-stu-id="fe1dd-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
