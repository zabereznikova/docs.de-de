---
title: 'Vorgehensweise: Aufrufen einer gespeicherten Prozedur mithilfe von LINQ (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], stored procedure calls
- stored procedures sample [Visual Basic]
- stored procedures [LINQ to SQL]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 6436d384-d1e0-40aa-8afd-451007477260
ms.openlocfilehash: af25ebe10681ebb1c346f90afc0291e53224833a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59319572"
---
# <a name="how-to-call-a-stored-procedure-by-using-linq-visual-basic"></a><span data-ttu-id="76040-102">Vorgehensweise: Aufrufen einer gespeicherten Prozedur mithilfe von LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="76040-102">How to: Call a Stored Procedure by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="76040-103">Language Integrated Query (LINQ) erleichtert Ihnen den Zugriff auf Datenbankinformationen, einschließlich Datenbankobjekten, z. B. gespeicherte Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="76040-103">Language-Integrated Query (LINQ) makes it easy to access database information, including database objects such as stored procedures.</span></span>  
  
 <span data-ttu-id="76040-104">Das folgende Beispiel zeigt, wie Sie eine Anwendung erstellen, die in einer SQL Server-Datenbank eine gespeicherte Prozedur aufruft.</span><span class="sxs-lookup"><span data-stu-id="76040-104">The following example shows how to create an application that calls a stored procedure in a SQL Server database.</span></span> <span data-ttu-id="76040-105">Das Beispiel zeigt, wie Sie zwei verschiedene gespeicherte Prozeduren in der Datenbank aufrufen.</span><span class="sxs-lookup"><span data-stu-id="76040-105">The sample shows how to call two different stored procedures in the database.</span></span> <span data-ttu-id="76040-106">Jede Prozedur gibt die Ergebnisse einer Abfrage zurück.</span><span class="sxs-lookup"><span data-stu-id="76040-106">Each procedure returns the results of a query.</span></span> <span data-ttu-id="76040-107">Eine Prozedur die Eingabeparameter akzeptiert, und die andere Prozedur nimmt keine Parameter.</span><span class="sxs-lookup"><span data-stu-id="76040-107">One procedure takes input parameters, and the other procedure does not take parameters.</span></span>  
  
 <span data-ttu-id="76040-108">In die Beispielen in diesem Thema verwenden die Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="76040-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="76040-109">Wenn Sie diese Datenbank nicht auf dem Entwicklungscomputer gespeichert haben, können Sie es aus dem Microsoft Download Center herunterladen.</span><span class="sxs-lookup"><span data-stu-id="76040-109">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="76040-110">Anweisungen hierzu finden Sie unter [Herunterladen von Beispieldatenbanken](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="76040-110">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="76040-111">Um eine Verbindung mit einer Datenbank zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="76040-111">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="76040-112">Öffnen Sie in Visual Studio **Server-Explorer**/**Datenbank-Explorer** durch Klicken auf **Server-Explorer**/**Datenbank Explorer** auf die **Ansicht** Menü.</span><span class="sxs-lookup"><span data-stu-id="76040-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="76040-113">Mit der rechten Maustaste **Datenverbindungen** in **Server-Explorer**/**Datenbank-Explorer** , und klicken Sie dann auf **Verbindung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="76040-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="76040-114">Geben Sie eine gültige Verbindung mit der Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="76040-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="76040-115">Zum Hinzufügen eines Projekts, das eine LINQ to SQL-Datei enthält.</span><span class="sxs-lookup"><span data-stu-id="76040-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="76040-116">Zeigen Sie in Visual Studio im Menü **Datei** auf **Neu**, und klicken Sie auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="76040-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="76040-117">Wählen Sie Visual Basic **Windows Forms-Anwendung** als Projekttyp.</span><span class="sxs-lookup"><span data-stu-id="76040-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="76040-118">Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="76040-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="76040-119">Wählen Sie die **LINQ to SQL-Klassen** Elementvorlage.</span><span class="sxs-lookup"><span data-stu-id="76040-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="76040-120">Nennen Sie die Datei `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="76040-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="76040-121">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="76040-121">Click **Add**.</span></span> <span data-ttu-id="76040-122">Der Object Relational Designer (O/R Designer) wird für die Datei northwind.dbml geöffnet.</span><span class="sxs-lookup"><span data-stu-id="76040-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-stored-procedures-to-the-or-designer"></a><span data-ttu-id="76040-123">Hinzufügen von gespeicherten Prozeduren in den O/R-Designer</span><span class="sxs-lookup"><span data-stu-id="76040-123">To add stored procedures to the O/R Designer</span></span>  
  
1. <span data-ttu-id="76040-124">In **Server-Explorer**/**Datenbank-Explorer**, erweitern Sie die Verbindung zur Northwind-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="76040-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="76040-125">Erweitern Sie die **gespeicherte Prozeduren** Ordner.</span><span class="sxs-lookup"><span data-stu-id="76040-125">Expand the **Stored Procedures** folder.</span></span>  
  
     <span data-ttu-id="76040-126">Wenn Sie den O/R-Designer geschlossen haben, können Sie sie durch Doppelklicken auf die Datei northwind.dbml, die Sie zuvor hinzugefügt haben erneut öffnen.</span><span class="sxs-lookup"><span data-stu-id="76040-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="76040-127">Klicken Sie auf die **Umsatz nach Jahr** gespeicherte Prozedur aus, und ziehen Sie es in den rechten Bereich des Designers.</span><span class="sxs-lookup"><span data-stu-id="76040-127">Click the **Sales by Year** stored procedure and drag it to the right pane of the designer.</span></span> <span data-ttu-id="76040-128">Klicken Sie auf die **Ten Most Expensive Products** gespeicherte Prozedur, ziehen Sie es in den rechten Bereich des Designers.</span><span class="sxs-lookup"><span data-stu-id="76040-128">Click the **Ten Most Expensive Products** stored procedure drag it to the right pane of the designer.</span></span>  
  
3. <span data-ttu-id="76040-129">Speichern Sie die Änderungen zu und schließen Sie den Designer.</span><span class="sxs-lookup"><span data-stu-id="76040-129">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="76040-130">Speichern Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="76040-130">Save your project.</span></span>  
  
### <a name="to-add-code-to-display-the-results-of-the-stored-procedures"></a><span data-ttu-id="76040-131">Hinzufügen von Code zum Anzeigen der Ergebnisse der gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="76040-131">To add code to display the results of the stored procedures</span></span>  
  
1. <span data-ttu-id="76040-132">Von der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.DataGridView> Steuerelement auf das Standard-Windows-Formular für das Projekt, Form1.</span><span class="sxs-lookup"><span data-stu-id="76040-132">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="76040-133">Doppelklicken Sie auf Form1, um zum Hinzufügen von Code die `Load` Ereignis.</span><span class="sxs-lookup"><span data-stu-id="76040-133">Double-click Form1 to add code to its `Load` event.</span></span>  
  
3. <span data-ttu-id="76040-134">Wenn Sie gespeicherte Prozeduren in den O/R-Designer hinzugefügt haben, wird der Designer hinzugefügt eine <xref:System.Data.Linq.DataContext> Objekt für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="76040-134">When you added stored procedures to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="76040-135">Dieses Objekt enthält den Code, der für diese Prozeduren zugreifen.</span><span class="sxs-lookup"><span data-stu-id="76040-135">This object contains the code that you must have to access those procedures.</span></span> <span data-ttu-id="76040-136">Die <xref:System.Data.Linq.DataContext> Objekt für das Projekt mit dem Namen wird anhand des Namens der DBML-Datei.</span><span class="sxs-lookup"><span data-stu-id="76040-136">The <xref:System.Data.Linq.DataContext> object for the project is named based on the name of the .dbml file.</span></span> <span data-ttu-id="76040-137">Für dieses Projekt die <xref:System.Data.Linq.DataContext> Objekt mit dem Namen `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="76040-137">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="76040-138">Sie können eine Instanz von erstellen die <xref:System.Data.Linq.DataContext> in Ihrem Code und der Aufruf die gespeicherte Prozedur-Methoden, die vom O/R-Designer angegeben.</span><span class="sxs-lookup"><span data-stu-id="76040-138">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and call the stored procedure methods specified by the O/R Designer.</span></span> <span data-ttu-id="76040-139">Zum Binden an die <xref:System.Windows.Forms.DataGridView> Objekt ist, wird Sie möglicherweise erzwingen, dass die auszuführende Abfrage sofort durch Aufrufen der <xref:System.Linq.Enumerable.ToList%2A> -Methode für die Ergebnisse der gespeicherten Prozedur.</span><span class="sxs-lookup"><span data-stu-id="76040-139">To bind to the <xref:System.Windows.Forms.DataGridView> object, you may have to force the query to execute immediately by calling the <xref:System.Linq.Enumerable.ToList%2A> method on the results of the stored procedure.</span></span>  
  
     <span data-ttu-id="76040-140">Fügen Sie den folgenden Code der `Load` Ereignis, rufen Sie entweder mit den gespeicherten Prozeduren, die als Methoden für den Data-Kontext verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="76040-140">Add the following code to the `Load` event to call either of the stored procedures exposed as methods for your data context.</span></span>  
  
     [!code-vb[VbLINQtoSQLHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form3.vb#1)]  
    [!code-vb[VbLINQtoSQLHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form3.vb#2)]  
  
4. <span data-ttu-id="76040-141">Drücken Sie F5, um das Projekt ausführen und die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="76040-141">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76040-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="76040-142">See also</span></span>

- [<span data-ttu-id="76040-143">LINQ</span><span class="sxs-lookup"><span data-stu-id="76040-143">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="76040-144">Abfragen</span><span class="sxs-lookup"><span data-stu-id="76040-144">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="76040-145">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="76040-145">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="76040-146">DataContext-Methoden (O/R-Designer)</span><span class="sxs-lookup"><span data-stu-id="76040-146">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [<span data-ttu-id="76040-147">Vorgehensweise: Zuweisen von gespeicherten Prozeduren zum Durchführen von Aktionen zum Aktualisieren, Einfügen und Löschen (O/R-Designer)</span><span class="sxs-lookup"><span data-stu-id="76040-147">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
