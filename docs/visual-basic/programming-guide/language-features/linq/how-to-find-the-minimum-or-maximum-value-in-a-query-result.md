---
title: 'Vorgehensweise: Suchen des minimalen oder maximalen Werts in einem Abfrageergebnis mithilfe von LINQ'
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
ms.openlocfilehash: e397ccd6fe21caaeb9d56ff3b0cc1ce16032639a
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91084007"
---
# <a name="how-to-find-the-minimum-or-maximum-value-in-a-query-result-by-using-linq-visual-basic"></a><span data-ttu-id="2a0fb-102">Gewusst wie: Suchen des minimalen oder maximalen Werts in einem Abfrageergebnis mithilfe von LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2a0fb-102">How to: Find the Minimum or Maximum Value in a Query Result by Using LINQ (Visual Basic)</span></span>

<span data-ttu-id="2a0fb-103">Language-Integrated Query (LINQ) vereinfacht den Zugriff auf Datenbankinformationen und das Ausführen von Abfragen.</span><span class="sxs-lookup"><span data-stu-id="2a0fb-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="2a0fb-104">Im folgenden Beispiel wird gezeigt, wie eine neue Anwendung erstellt wird, die Abfragen für eine SQL Server Datenbank ausführt.</span><span class="sxs-lookup"><span data-stu-id="2a0fb-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span> <span data-ttu-id="2a0fb-105">Im Beispiel werden die Mindest-und Maximalwerte für die Ergebnisse mithilfe der `Aggregate` -Klausel und der- `Group By` Klausel bestimmt.</span><span class="sxs-lookup"><span data-stu-id="2a0fb-105">The sample determines the minimum and maximum values for the results by using the `Aggregate` and `Group By` clauses.</span></span> <span data-ttu-id="2a0fb-106">Weitere Informationen finden Sie unter [Aggregat Klausel](../../../language-reference/queries/aggregate-clause.md) und [Group By-Klausel](../../../language-reference/queries/group-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="2a0fb-106">For more information, see [Aggregate Clause](../../../language-reference/queries/aggregate-clause.md) and [Group By Clause](../../../language-reference/queries/group-by-clause.md).</span></span>  
  
 <span data-ttu-id="2a0fb-107">In den Beispielen in diesem Thema wird die Beispieldatenbank Northwind verwendet.</span><span class="sxs-lookup"><span data-stu-id="2a0fb-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="2a0fb-108">Befindet sich diese Datenbank nicht auf Ihrem Entwicklungscomputer, können Sie sie aus dem Microsoft Download Center herunterladen.</span><span class="sxs-lookup"><span data-stu-id="2a0fb-108">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="2a0fb-109">Anweisungen hierzu finden Sie unter [Herunterladen von Beispiel Datenbanken](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="2a0fb-109">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="create-a-connection-to-a-database"></a><span data-ttu-id="2a0fb-110">Herstellen einer Verbindung mit einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="2a0fb-110">Create a connection to a database</span></span>  
  
1. <span data-ttu-id="2a0fb-111">Öffnen Sie in Visual Studio **Server-Explorer** / **Datenbank-Explorer** , indem **Server Explorer**Sie / im Menü **Ansicht** auf Server-Explorer**Datenbank-Explorer** klicken.</span><span class="sxs-lookup"><span data-stu-id="2a0fb-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="2a0fb-112">Klicken Sie in **Server-Explorer**Datenbank-Explorer mit der rechten Maustaste auf **Datenverbindungen** / **Database Explorer** und dann auf **Verbindung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="2a0fb-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="2a0fb-113">Geben Sie eine gültige Verbindung mit der Northwind-Beispieldatenbank an.</span><span class="sxs-lookup"><span data-stu-id="2a0fb-113">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="2a0fb-114">So fügen Sie ein Projekt hinzu, das eine LINQ to SQL Datei enthält</span><span class="sxs-lookup"><span data-stu-id="2a0fb-114">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="2a0fb-115">Zeigen Sie in Visual Studio im Menü **Datei** auf **Neu**, und klicken Sie auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="2a0fb-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="2a0fb-116">Wählen Sie Visual Basic **Windows Forms Anwendung** als Projekttyp aus.</span><span class="sxs-lookup"><span data-stu-id="2a0fb-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="2a0fb-117">Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="2a0fb-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="2a0fb-118">Wählen Sie die Element Vorlage **LINQ to SQL Klassen** aus.</span><span class="sxs-lookup"><span data-stu-id="2a0fb-118">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="2a0fb-119">Benennen Sie die Datei mit `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="2a0fb-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="2a0fb-120">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="2a0fb-120">Click **Add**.</span></span> <span data-ttu-id="2a0fb-121">Der objektrelationaler Designer (O/R-Designer) wird für die Datei Northwind. dbml geöffnet.</span><span class="sxs-lookup"><span data-stu-id="2a0fb-121">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
## <a name="add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="2a0fb-122">Hinzufügen von Tabellen zum Abfragen an den O/R-Designer</span><span class="sxs-lookup"><span data-stu-id="2a0fb-122">Add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="2a0fb-123">Erweitern Sie in **Server-Explorer** / **Datenbank-Explorer**die Verbindung mit der Northwind-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="2a0fb-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="2a0fb-124">Erweitern Sie den Ordner **Tabellen** .</span><span class="sxs-lookup"><span data-stu-id="2a0fb-124">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="2a0fb-125">Wenn Sie den O/R-Designer geschlossen haben, können Sie ihn erneut öffnen, indem Sie auf die Datei Northwind. dbml, die Sie zuvor hinzugefügt haben, doppelklicken.</span><span class="sxs-lookup"><span data-stu-id="2a0fb-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="2a0fb-126">Klicken Sie auf die Tabelle Customers, und ziehen Sie Sie in den linken Bereich des Designers.</span><span class="sxs-lookup"><span data-stu-id="2a0fb-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="2a0fb-127">Klicken Sie auf die Tabelle Orders, und ziehen Sie Sie in den linken Bereich des Designers.</span><span class="sxs-lookup"><span data-stu-id="2a0fb-127">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="2a0fb-128">Der Designer erstellt neue `Customer` - `Order` Objekte und-Objekte für Ihr Projekt.</span><span class="sxs-lookup"><span data-stu-id="2a0fb-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="2a0fb-129">Beachten Sie, dass der Designer automatisch Beziehungen zwischen den Tabellen erkennt und untergeordnete Eigenschaften für verbundene Objekte erstellt.</span><span class="sxs-lookup"><span data-stu-id="2a0fb-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="2a0fb-130">IntelliSense zeigt beispielsweise, dass das- `Customer` Objekt über eine- `Orders` Eigenschaft für alle Bestellungen verfügt, die mit diesem Kunden verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="2a0fb-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3. <span data-ttu-id="2a0fb-131">Speichern Sie die Änderungen, und schließen Sie den Designer.</span><span class="sxs-lookup"><span data-stu-id="2a0fb-131">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="2a0fb-132">Speichern Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="2a0fb-132">Save your project.</span></span>  
  
## <a name="add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="2a0fb-133">Hinzufügen von Code zum Abfragen der Datenbank und Anzeigen der Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="2a0fb-133">Add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="2a0fb-134">Ziehen Sie aus der **Toolbox**ein- <xref:System.Windows.Forms.DataGridView> Steuerelement auf das Windows-Standardformular für das Projekt, Form1.</span><span class="sxs-lookup"><span data-stu-id="2a0fb-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="2a0fb-135">Doppelklicken Sie auf Form1, um dem- `Load` Ereignis des Formulars Code hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="2a0fb-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3. <span data-ttu-id="2a0fb-136">Wenn Sie dem O/R-Designer Tabellen hinzugefügt haben, hat der Designer ein- <xref:System.Data.Linq.DataContext> Objekt für das Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2a0fb-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="2a0fb-137">Dieses Objekt enthält den Code, den Sie für den Zugriff auf diese Tabellen benötigen, zusätzlich zu den einzelnen Objekten und Auflistungen für jede Tabelle.</span><span class="sxs-lookup"><span data-stu-id="2a0fb-137">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="2a0fb-138">Das- <xref:System.Data.Linq.DataContext> Objekt für das Projekt wird basierend auf dem Namen der DBML-Datei benannt.</span><span class="sxs-lookup"><span data-stu-id="2a0fb-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="2a0fb-139">Für dieses Projekt hat das <xref:System.Data.Linq.DataContext> Objekt den Namen `northwindDataContext` .</span><span class="sxs-lookup"><span data-stu-id="2a0fb-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="2a0fb-140">Sie können eine Instanz von <xref:System.Data.Linq.DataContext> im Code erstellen und die im O/R-Designer angegebenen Tabellen Abfragen.</span><span class="sxs-lookup"><span data-stu-id="2a0fb-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="2a0fb-141">Fügen Sie dem-Ereignis den folgenden Code hinzu `Load` .</span><span class="sxs-lookup"><span data-stu-id="2a0fb-141">Add the following code to the `Load` event.</span></span> <span data-ttu-id="2a0fb-142">Dieser Code fragt die Tabellen ab, die als Eigenschaften des Daten Kontexts verfügbar gemacht werden, und bestimmt die minimalen und maximalen Werte für die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="2a0fb-142">This code queries the tables that are exposed as properties of your data context and determines the minimum and maximum values for the results.</span></span> <span data-ttu-id="2a0fb-143">Das Beispiel verwendet die `Aggregate` -Klausel, um ein einzelnes Ergebnis abzufragen, und die- `Group By` Klausel, um einen Durchschnitt für gruppierte Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2a0fb-143">The sample uses the `Aggregate` clause to query for a single result, and the `Group By` clause to show an average for grouped results.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form7.vb#14)]  
  
4. <span data-ttu-id="2a0fb-144">Drücken Sie **F5** , um das Projekt auszuführen und die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2a0fb-144">Press **F5** to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a0fb-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2a0fb-145">See also</span></span>

- [<span data-ttu-id="2a0fb-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="2a0fb-146">LINQ</span></span>](index.md)
- [<span data-ttu-id="2a0fb-147">Abfragen</span><span class="sxs-lookup"><span data-stu-id="2a0fb-147">Queries</span></span>](../../../language-reference/queries/index.md)
- [<span data-ttu-id="2a0fb-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="2a0fb-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="2a0fb-149">DataContext-Methoden (O/R-Designer)</span><span class="sxs-lookup"><span data-stu-id="2a0fb-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
