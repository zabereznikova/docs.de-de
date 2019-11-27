---
title: 'Gewusst wie: Abfragen einer Datenbank mithilfe von LINQ'
ms.date: 07/20/2015
helpviewer_keywords:
- query samples [LINQ]
- database querying [LINQ]
- queries [LINQ in Visual Basic], database querying
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: bcf5e9c3-a236-4399-9a7f-3991eca7cf56
ms.openlocfilehash: f4b2510bad2b23d7a0e179383b34c4e425e6564e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344960"
---
# <a name="how-to-query-a-database-by-using-linq-visual-basic"></a><span data-ttu-id="800f4-102">Gewusst wie: Abfragen einer Datenbank mit LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="800f4-102">How to: Query a Database by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="800f4-103">Language-Integrated Query (LINQ) vereinfacht den Zugriff auf Datenbankinformationen und das Ausführen von Abfragen.</span><span class="sxs-lookup"><span data-stu-id="800f4-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="800f4-104">Im folgenden Beispiel wird gezeigt, wie eine neue Anwendung erstellt wird, die Abfragen für eine SQL Server Datenbank ausführt.</span><span class="sxs-lookup"><span data-stu-id="800f4-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span>  
  
 <span data-ttu-id="800f4-105">In den Beispielen in diesem Thema wird die Beispieldatenbank Northwind verwendet.</span><span class="sxs-lookup"><span data-stu-id="800f4-105">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="800f4-106">Befindet sich diese Datenbank nicht auf Ihrem Entwicklungscomputer, können Sie diese aus dem Microsoft Download Center herunterladen.</span><span class="sxs-lookup"><span data-stu-id="800f4-106">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="800f4-107">Anweisungen hierzu finden Sie unter [Herunterladen von Beispiel Datenbanken](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="800f4-107">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="800f4-108">So erstellen Sie eine Verbindung mit einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="800f4-108">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="800f4-109">Öffnen Sie in Visual Studio **Server-Explorer**/**Datenbank-Explorer** , indem Sie im Menü **Ansicht** auf **Server-Explorer** **/Datenbank-Explorer** klicken.</span><span class="sxs-lookup"><span data-stu-id="800f4-109">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="800f4-110">Klicken Sie in **Server-Explorer** **Datenbank-Explorer**/mit der rechten Maustaste auf **Datenverbindungen** , und klicken Sie dann auf **Verbindung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="800f4-110">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="800f4-111">Geben Sie eine gültige Verbindung mit der Northwind-Beispieldatenbank an.</span><span class="sxs-lookup"><span data-stu-id="800f4-111">Specify a valid connection to the Northwind sample database.</span></span>  
  
## <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="800f4-112">So fügen Sie ein Projekt hinzu, das eine LINQ to SQL Datei enthält</span><span class="sxs-lookup"><span data-stu-id="800f4-112">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="800f4-113">Zeigen Sie in Visual Studio im Menü **Datei** auf **Neu**, und klicken Sie auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="800f4-113">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="800f4-114">Wählen Sie Visual Basic **Windows Forms Anwendung** als Projekttyp aus.</span><span class="sxs-lookup"><span data-stu-id="800f4-114">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="800f4-115">Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="800f4-115">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="800f4-116">Wählen Sie die Element Vorlage **LINQ to SQL Klassen** aus.</span><span class="sxs-lookup"><span data-stu-id="800f4-116">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="800f4-117">Nennen Sie die Datei `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="800f4-117">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="800f4-118">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="800f4-118">Click **Add**.</span></span> <span data-ttu-id="800f4-119">Der objektrelationaler Designer (O/R-Designer) wird für die Datei Northwind. dbml geöffnet.</span><span class="sxs-lookup"><span data-stu-id="800f4-119">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
## <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="800f4-120">So fügen Sie dem O/R-Designer abzufragende Tabellen hinzu</span><span class="sxs-lookup"><span data-stu-id="800f4-120">To add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="800f4-121">Erweitern Sie in **Server-Explorer**/**Datenbank-Explorer**die Verbindung mit der Northwind-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="800f4-121">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="800f4-122">Erweitern Sie den Ordner **Tabellen** .</span><span class="sxs-lookup"><span data-stu-id="800f4-122">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="800f4-123">Wenn Sie den O/R-Designer geschlossen haben, können Sie ihn erneut öffnen, indem Sie auf die Datei Northwind. dbml, die Sie zuvor hinzugefügt haben, doppelklicken.</span><span class="sxs-lookup"><span data-stu-id="800f4-123">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="800f4-124">Klicken Sie auf die Tabelle Customers, und ziehen Sie Sie in den linken Bereich des Designers.</span><span class="sxs-lookup"><span data-stu-id="800f4-124">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="800f4-125">Klicken Sie auf die Tabelle Orders, und ziehen Sie Sie in den linken Bereich des Designers.</span><span class="sxs-lookup"><span data-stu-id="800f4-125">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="800f4-126">Der Designer erstellt neue `Customer` und `Order` Objekte für Ihr Projekt.</span><span class="sxs-lookup"><span data-stu-id="800f4-126">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="800f4-127">Beachten Sie, dass der Designer automatisch Beziehungen zwischen den Tabellen erkennt und untergeordnete Eigenschaften für verbundene Objekte erstellt.</span><span class="sxs-lookup"><span data-stu-id="800f4-127">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="800f4-128">IntelliSense zeigt z. b. an, dass das `Customer` Objekt über eine `Orders`-Eigenschaft für alle Bestellungen verfügt, die mit diesem Kunden verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="800f4-128">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3. <span data-ttu-id="800f4-129">Speichern Sie die Änderungen, und schließen Sie den Designer.</span><span class="sxs-lookup"><span data-stu-id="800f4-129">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="800f4-130">Speichern Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="800f4-130">Save your project.</span></span>  
  
## <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="800f4-131">So fügen Sie Code hinzu, um die Datenbank abzufragen und die Ergebnisse anzuzeigen</span><span class="sxs-lookup"><span data-stu-id="800f4-131">To add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="800f4-132">Ziehen Sie aus der **Toolbox**ein <xref:System.Windows.Forms.DataGridView>-Steuerelement auf das standardmäßige Windows Form für Ihr Projekt, Form1.</span><span class="sxs-lookup"><span data-stu-id="800f4-132">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="800f4-133">Doppelklicken Sie auf Form1, um dem `Load`-Ereignis des Formulars Code hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="800f4-133">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3. <span data-ttu-id="800f4-134">Wenn Sie dem O/R-Designer Tabellen hinzugefügt haben, hat der Designer ein <xref:System.Data.Linq.DataContext>-Objekt für das Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="800f4-134">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="800f4-135">Dieses Objekt enthält den Code, den Sie für den Zugriff auf diese Tabellen benötigen, zusätzlich zu den einzelnen Objekten und Auflistungen für jede Tabelle.</span><span class="sxs-lookup"><span data-stu-id="800f4-135">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="800f4-136">Das <xref:System.Data.Linq.DataContext>-Objekt für das Projekt wird basierend auf dem Namen der DBML-Datei benannt.</span><span class="sxs-lookup"><span data-stu-id="800f4-136">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="800f4-137">Für dieses Projekt wird das <xref:System.Data.Linq.DataContext> Objekt `northwindDataContext`benannt.</span><span class="sxs-lookup"><span data-stu-id="800f4-137">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="800f4-138">Sie können eine Instanz des <xref:System.Data.Linq.DataContext> in Ihrem Code erstellen und die im O/R-Designer angegebenen Tabellen Abfragen.</span><span class="sxs-lookup"><span data-stu-id="800f4-138">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="800f4-139">Fügen Sie dem `Load`-Ereignis den folgenden Code hinzu, um die Tabellen abzufragen, die als Eigenschaften des Daten Kontexts verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="800f4-139">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form2.vb#3)]  
  
4. <span data-ttu-id="800f4-140">Drücken Sie F5, um das Projekt auszuführen und die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="800f4-140">Press F5 to run your project and view the results.</span></span>  
  
5. <span data-ttu-id="800f4-141">Im folgenden finden Sie einige zusätzliche Abfragen, die Sie ausprobieren können:</span><span class="sxs-lookup"><span data-stu-id="800f4-141">Following are some additional queries that you can try:</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form2.vb#4)]  
    [!code-vb[VbLINQToSQLHowTos#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form2.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="800f4-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="800f4-142">See also</span></span>

- [<span data-ttu-id="800f4-143">LINQ</span><span class="sxs-lookup"><span data-stu-id="800f4-143">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="800f4-144">Abfragen</span><span class="sxs-lookup"><span data-stu-id="800f4-144">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="800f4-145">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="800f4-145">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="800f4-146">DataContext-Methoden (O/R-Designer)</span><span class="sxs-lookup"><span data-stu-id="800f4-146">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
