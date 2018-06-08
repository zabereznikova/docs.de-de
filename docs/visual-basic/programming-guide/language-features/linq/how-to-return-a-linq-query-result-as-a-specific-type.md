---
title: 'Gewusst wie: Zurückgeben eines LINQ-Abfrageergebnisses als ein bestimmter Typ (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], specific type returned
- projection [LINQ in Visual Basic]
- anonymous types [Visual Basic]
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: 621bb10a-e5d7-44fb-a025-317964b19d92
ms.openlocfilehash: 2c3a10ed901832846da058018a91349be0c2495b
ms.sourcegitcommit: d955cb4c681d68cf301d410925d83f25172ece86
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/07/2018
ms.locfileid: "34827084"
---
# <a name="how-to-return-a-linq-query-result-as-a-specific-type-visual-basic"></a><span data-ttu-id="4e0cc-102">Gewusst wie: Zurückgeben eines LINQ-Abfrageergebnisses als ein bestimmter Typ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e0cc-102">How to: Return a LINQ Query Result as a Specific Type (Visual Basic)</span></span>
<span data-ttu-id="4e0cc-103">Language-Integrated Query (LINQ) erleichtert die Datenbankinformationen zugreifen und Ausführen von Abfragen.</span><span class="sxs-lookup"><span data-stu-id="4e0cc-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span> <span data-ttu-id="4e0cc-104">Standardmäßig geben Sie LINQ-Abfragen eine Liste von Objekten als einen anonymen Typ zurück.</span><span class="sxs-lookup"><span data-stu-id="4e0cc-104">By default, LINQ queries return a list of objects as an anonymous type.</span></span> <span data-ttu-id="4e0cc-105">Sie können auch angeben, dass eine Abfrage mit eine Liste eines bestimmten Typs zurückgeben der `Select` Klausel.</span><span class="sxs-lookup"><span data-stu-id="4e0cc-105">You can also specify that a query return a list of a specific type by using the `Select` clause.</span></span>  
  
 <span data-ttu-id="4e0cc-106">Im folgende Beispiel wird gezeigt, wie eine neue Anwendung zu erstellen, die führt Abfragen in einer SQL Server-Datenbank und die Ergebnisse als einen bestimmten benannten Typ projiziert, wird.</span><span class="sxs-lookup"><span data-stu-id="4e0cc-106">The following example shows how to create a new application that performs queries against a SQL Server database and projects the results as a specific named type.</span></span> <span data-ttu-id="4e0cc-107">Weitere Informationen finden Sie unter [anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) und [Select-Klausel](../../../../visual-basic/language-reference/queries/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="4e0cc-107">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) and [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md).</span></span>  
  
 <span data-ttu-id="4e0cc-108">In den Beispielen in diesem Thema verwenden die Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="4e0cc-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="4e0cc-109">Wenn Sie diese Datenbank nicht auf Ihrem Computer verfügen, können Sie es aus dem Microsoft Download Center herunterladen.</span><span class="sxs-lookup"><span data-stu-id="4e0cc-109">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="4e0cc-110">Anweisungen hierzu finden Sie unter [Herunterladen von Beispieldatenbanken](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="4e0cc-110">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="4e0cc-111">So erstellen eine Verbindung mit einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="4e0cc-111">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="4e0cc-112">Öffnen Sie in Visual Studio **Server-Explorer**/**Datenbank-Explorer** durch Klicken auf **Server-Explorer**/**Datenbank Explorer** auf die **Ansicht** Menü.</span><span class="sxs-lookup"><span data-stu-id="4e0cc-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="4e0cc-113">Mit der rechten Maustaste **Datenverbindungen** in **Server-Explorer**/**Datenbank-Explorer** , und klicken Sie dann auf **Verbindung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="4e0cc-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="4e0cc-114">Geben Sie eine gültige Verbindung mit der Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="4e0cc-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="4e0cc-115">Ein Projekt hinzufügen, die eine LINQ to SQL-Datei enthält.</span><span class="sxs-lookup"><span data-stu-id="4e0cc-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="4e0cc-116">Zeigen Sie in Visual Studio im Menü **Datei** auf **Neu**, und klicken Sie auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="4e0cc-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="4e0cc-117">Wählen Sie Visual Basic **Windows Forms-Anwendung** als Projekttyp.</span><span class="sxs-lookup"><span data-stu-id="4e0cc-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="4e0cc-118">Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="4e0cc-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="4e0cc-119">Wählen Sie die **LINQ to SQL-Klassen** Elementvorlage.</span><span class="sxs-lookup"><span data-stu-id="4e0cc-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="4e0cc-120">Nennen Sie die Datei `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="4e0cc-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="4e0cc-121">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="4e0cc-121">Click **Add**.</span></span> <span data-ttu-id="4e0cc-122">Der Object Relational Designer (O/R-Designer) wird für die Datei northwind.dbml geöffnet.</span><span class="sxs-lookup"><span data-stu-id="4e0cc-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="4e0cc-123">Hinzufügen von Tabellen zu Abfragen in den O/R-Designer</span><span class="sxs-lookup"><span data-stu-id="4e0cc-123">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="4e0cc-124">In **Server-Explorer**/**Datenbank-Explorer**, erweitern Sie die Verbindung mit der Datenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="4e0cc-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="4e0cc-125">Erweitern Sie die **Tabellen** Ordner.</span><span class="sxs-lookup"><span data-stu-id="4e0cc-125">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="4e0cc-126">Wenn Sie im O/R-Designer geschlossen haben, können Sie es durch Doppelklicken auf die Datei northwind.dbml, die Sie zuvor hinzugefügt haben erneut öffnen.</span><span class="sxs-lookup"><span data-stu-id="4e0cc-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="4e0cc-127">Klicken Sie auf der Customers-Tabelle, und ziehen Sie es in den linken Bereich des Designers.</span><span class="sxs-lookup"><span data-stu-id="4e0cc-127">Click the Customers table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="4e0cc-128">Der Designer erstellt eine neue `Customer` Objekt für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="4e0cc-128">The designer creates a new `Customer` object for your project.</span></span> <span data-ttu-id="4e0cc-129">Sie können ein Abfrageergebnis als projizieren der `Customer` Typ oder als einen Typ, den Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="4e0cc-129">You can project a query result as the `Customer` type or as a type that you create.</span></span> <span data-ttu-id="4e0cc-130">In diesem Beispiel wird einen neuen Typ in einem späteren Verfahren und erstellen ein Abfrageergebnisses als diesen Typ.</span><span class="sxs-lookup"><span data-stu-id="4e0cc-130">This sample will create a new type in a later procedure and project a query result as that type.</span></span>  
  
3.  <span data-ttu-id="4e0cc-131">Speichern Sie die Änderungen zu und schließen Sie den Designer.</span><span class="sxs-lookup"><span data-stu-id="4e0cc-131">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="4e0cc-132">Speichern Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="4e0cc-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="4e0cc-133">Hinzufügen von Code aus, um die Datenbank abzufragen und die Ergebnisse werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4e0cc-133">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="4e0cc-134">Aus der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.DataGridView> -Steuerelement auf die Standard-Windows Form für das Projekt, Form1.</span><span class="sxs-lookup"><span data-stu-id="4e0cc-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="4e0cc-135">Doppelklicken Sie auf Form1, um Sie die Formular1-Klasse ändern.</span><span class="sxs-lookup"><span data-stu-id="4e0cc-135">Double-click Form1 to modify the Form1 class.</span></span>  
  
3.  <span data-ttu-id="4e0cc-136">Nach der `End Class` Anweisung der Formular1-Klasse, fügen Sie folgenden Code zum Erstellen einer `CustomerInfo` Datentyp, um die Abfrageergebnisse für dieses Beispiel zu speichern.</span><span class="sxs-lookup"><span data-stu-id="4e0cc-136">After the `End Class` statement of the Form1 class, add the following code to create a `CustomerInfo` type to hold the query results for this sample.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#16](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-return-a-linq-query-result-as-a-specific-type_1.vb)]  
  
4.  <span data-ttu-id="4e0cc-137">Wenn Sie Tabellen in den O/R-Designer hinzugefügt haben, wird der Designer hinzugefügt ein <xref:System.Data.Linq.DataContext> -Objekt, das Projekt.</span><span class="sxs-lookup"><span data-stu-id="4e0cc-137">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="4e0cc-138">Dieses Objekt enthält den Code, den Sie benötigen Zugriff auf diese Tabellen und den Zugriff auf einzelne Objekte und Sammlungen für jede Tabelle.</span><span class="sxs-lookup"><span data-stu-id="4e0cc-138">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="4e0cc-139">Die <xref:System.Data.Linq.DataContext> Objekt für das Projekt mit der Bezeichnung wird anhand des Namens der DBML-Datei.</span><span class="sxs-lookup"><span data-stu-id="4e0cc-139">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="4e0cc-140">Für dieses Projekt die <xref:System.Data.Linq.DataContext> Objekt heißt `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="4e0cc-140">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="4e0cc-141">Erstellen eine Instanz von der <xref:System.Data.Linq.DataContext> in Ihren Code und die Abfrage die Tabellen, die vom O/R-Designer angegeben.</span><span class="sxs-lookup"><span data-stu-id="4e0cc-141">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="4e0cc-142">In der `Load` Ereignis von der Klasse Form1 steht, fügen Sie folgenden Code, die Tabellen abzufragen, die als Eigenschaften des Datenkontexts verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="4e0cc-142">In the `Load` event of the Form1 class, add the following code to query the tables that are exposed as properties of your data context.</span></span> <span data-ttu-id="4e0cc-143">Die `Select` -Klausel der Abfrage erstellt eine neue `CustomerInfo` Typs statt eines anonymen Typs für jedes Element des Abfrageergebnisses.</span><span class="sxs-lookup"><span data-stu-id="4e0cc-143">The `Select` clause of the query will create a new `CustomerInfo` type instead of an anonymous type for each item of the query result.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#15](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-return-a-linq-query-result-as-a-specific-type_2.vb)]  
  
5.  <span data-ttu-id="4e0cc-144">Drücken Sie F5, um das Projekt auszuführen und die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4e0cc-144">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e0cc-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e0cc-145">See Also</span></span>  
 [<span data-ttu-id="4e0cc-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="4e0cc-146">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="4e0cc-147">Abfragen</span><span class="sxs-lookup"><span data-stu-id="4e0cc-147">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="4e0cc-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="4e0cc-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)  
 [<span data-ttu-id="4e0cc-149">DataContext-Methoden (O/R-Designer)</span><span class="sxs-lookup"><span data-stu-id="4e0cc-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
