---
title: 'Gewusst wie: Abfragen einer Datenbank mit LINQ (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- query samples [LINQ]
- database querying [LINQ]
- queries [LINQ in Visual Basic], database querying
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: bcf5e9c3-a236-4399-9a7f-3991eca7cf56
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9949b5f6f670c66463c42a71434c0cdd941c995b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-query-a-database-by-using-linq-visual-basic"></a><span data-ttu-id="91c42-102">Gewusst wie: Abfragen einer Datenbank mit LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="91c42-102">How to: Query a Database by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="91c42-103">Language-Integrated Query (LINQ) erleichtert die Datenbankinformationen zugreifen und Ausführen von Abfragen.</span><span class="sxs-lookup"><span data-stu-id="91c42-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="91c42-104">Im folgende Beispiel wird gezeigt, wie eine neue Anwendung zu erstellen, die Abfragen für eine SQL Server-Datenbank ausführt.</span><span class="sxs-lookup"><span data-stu-id="91c42-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span>  
  
 <span data-ttu-id="91c42-105">In den Beispielen in diesem Thema verwenden die Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="91c42-105">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="91c42-106">Wenn Sie die Beispieldatenbank Northwind nicht auf Ihrem Computer verfügen, können Sie laden Sie es der [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Website.</span><span class="sxs-lookup"><span data-stu-id="91c42-106">If you do not have the Northwind sample database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web site.</span></span> <span data-ttu-id="91c42-107">Anweisungen hierzu finden Sie unter [Herunterladen von Beispieldatenbanken](https://msdn.microsoft.com/library/bb399411).</span><span class="sxs-lookup"><span data-stu-id="91c42-107">For instructions, see [Downloading Sample Databases](https://msdn.microsoft.com/library/bb399411).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="91c42-108">So erstellen eine Verbindung mit einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="91c42-108">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="91c42-109">Öffnen Sie in Visual Studio **Server-Explorer**/**Datenbank-Explorer** durch Klicken auf **Server-Explorer**/**Datenbank Explorer** auf die **Ansicht** Menü.</span><span class="sxs-lookup"><span data-stu-id="91c42-109">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="91c42-110">Mit der rechten Maustaste **Datenverbindungen** in **Server-Explorer**/**Datenbank-Explorer** , und klicken Sie dann auf **Verbindung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="91c42-110">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="91c42-111">Geben Sie eine gültige Verbindung mit der Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="91c42-111">Specify a valid connection to the Northwind sample database.</span></span>  
  
## <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="91c42-112">Ein Projekt hinzufügen, die eine LINQ to SQL-Datei enthält.</span><span class="sxs-lookup"><span data-stu-id="91c42-112">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="91c42-113">Zeigen Sie in Visual Studio im Menü **Datei** auf **Neu**, und klicken Sie auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="91c42-113">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="91c42-114">Wählen Sie Visual Basic **Windows Forms-Anwendung** als Projekttyp.</span><span class="sxs-lookup"><span data-stu-id="91c42-114">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="91c42-115">Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="91c42-115">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="91c42-116">Wählen Sie die **LINQ to SQL-Klassen** Elementvorlage.</span><span class="sxs-lookup"><span data-stu-id="91c42-116">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="91c42-117">Nennen Sie die Datei `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="91c42-117">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="91c42-118">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="91c42-118">Click **Add**.</span></span> <span data-ttu-id="91c42-119">Der Object Relational Designer (O/R-Designer) wird für die Datei northwind.dbml geöffnet.</span><span class="sxs-lookup"><span data-stu-id="91c42-119">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
## <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="91c42-120">Hinzufügen von Tabellen zu Abfragen in den O/R-Designer</span><span class="sxs-lookup"><span data-stu-id="91c42-120">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="91c42-121">In **Server-Explorer**/**Datenbank-Explorer**, erweitern Sie die Verbindung mit der Datenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="91c42-121">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="91c42-122">Erweitern Sie die **Tabellen** Ordner.</span><span class="sxs-lookup"><span data-stu-id="91c42-122">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="91c42-123">Wenn Sie im O/R-Designer geschlossen haben, können Sie es durch Doppelklicken auf die Datei northwind.dbml, die Sie zuvor hinzugefügt haben erneut öffnen.</span><span class="sxs-lookup"><span data-stu-id="91c42-123">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="91c42-124">Klicken Sie auf der Customers-Tabelle, und ziehen Sie es in den linken Bereich des Designers.</span><span class="sxs-lookup"><span data-stu-id="91c42-124">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="91c42-125">Klicken Sie auf die Orders-Tabelle, und ziehen Sie es in den linken Bereich des Designers.</span><span class="sxs-lookup"><span data-stu-id="91c42-125">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="91c42-126">Der Designer erstellt neue `Customer` und `Order` Objekte für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="91c42-126">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="91c42-127">Beachten Sie, dass der Designer Beziehungen zwischen den Tabellen erkennt automatisch und untergeordneten Eigenschaften für verwandte Objekte erstellt.</span><span class="sxs-lookup"><span data-stu-id="91c42-127">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="91c42-128">Z. B. IntelliSense wird angezeigt, die `Customer` Objekt verfügt über eine `Orders` -Eigenschaft für alle Aufträge im Zusammenhang mit diesen Kunden.</span><span class="sxs-lookup"><span data-stu-id="91c42-128">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3.  <span data-ttu-id="91c42-129">Speichern Sie die Änderungen zu und schließen Sie den Designer.</span><span class="sxs-lookup"><span data-stu-id="91c42-129">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="91c42-130">Speichern Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="91c42-130">Save your project.</span></span>  
  
## <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="91c42-131">Hinzufügen von Code aus, um die Datenbank abzufragen und die Ergebnisse werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="91c42-131">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="91c42-132">Aus der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.DataGridView> -Steuerelement auf die Standard-Windows Form für das Projekt, Form1.</span><span class="sxs-lookup"><span data-stu-id="91c42-132">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="91c42-133">Doppelklicken Sie auf Form1, um zum Hinzufügen von Code die `Load` -Ereignis des Formulars.</span><span class="sxs-lookup"><span data-stu-id="91c42-133">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3.  <span data-ttu-id="91c42-134">Wenn Sie Tabellen in den O/R-Designer hinzugefügt haben, wird der Designer hinzugefügt ein <xref:System.Data.Linq.DataContext> Objekt für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="91c42-134">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="91c42-135">Dieses Objekt enthält den Code, den Sie für den Zugriff auf diese Tabellen, zusätzlich zu den einzelnen Objekte und Sammlungen für jede Tabelle benötigen.</span><span class="sxs-lookup"><span data-stu-id="91c42-135">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="91c42-136">Die <xref:System.Data.Linq.DataContext> Objekt für das Projekt mit der Bezeichnung wird anhand des Namens der DBML-Datei.</span><span class="sxs-lookup"><span data-stu-id="91c42-136">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="91c42-137">Für dieses Projekt die <xref:System.Data.Linq.DataContext> Objekt heißt `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="91c42-137">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="91c42-138">Erstellen eine Instanz von der <xref:System.Data.Linq.DataContext> in Ihren Code und die Abfrage die Tabellen, die vom O/R-Designer angegeben.</span><span class="sxs-lookup"><span data-stu-id="91c42-138">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="91c42-139">Fügen Sie folgenden Code, der `Load` Ereignis, um die Tabellen Abfragen, die als Eigenschaften des Datenkontexts verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="91c42-139">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#3](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_1.vb)]  
  
4.  <span data-ttu-id="91c42-140">Drücken Sie F5, um das Projekt auszuführen und die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="91c42-140">Press F5 to run your project and view the results.</span></span>  
  
5.  <span data-ttu-id="91c42-141">Es folgen einige zusätzlichen Abfragen, die Sie ausprobieren können:</span><span class="sxs-lookup"><span data-stu-id="91c42-141">Following are some additional queries that you can try:</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#4](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_2.vb)]  
    [!code-vb[VbLINQToSQLHowTos#5](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="91c42-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91c42-142">See Also</span></span>  
 [<span data-ttu-id="91c42-143">LINQ</span><span class="sxs-lookup"><span data-stu-id="91c42-143">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="91c42-144">Abfragen</span><span class="sxs-lookup"><span data-stu-id="91c42-144">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="91c42-145">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="91c42-145">LINQ to SQL</span></span>](https://msdn.microsoft.com/library/bb386976)  
 [<span data-ttu-id="91c42-146">DataContext-Methoden (O/R-Designer)</span><span class="sxs-lookup"><span data-stu-id="91c42-146">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
