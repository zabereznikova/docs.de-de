---
title: 'Vorgehensweise: Aufrufen einer gespeicherten Prozedur mithilfe von LINQ'
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], stored procedure calls
- stored procedures sample [Visual Basic]
- stored procedures [LINQ to SQL]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 6436d384-d1e0-40aa-8afd-451007477260
ms.openlocfilehash: 7e5fecf0c4c0d3a561ec7d0c4ac03c9d9ce7f759
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075134"
---
# <a name="how-to-call-a-stored-procedure-by-using-linq-visual-basic"></a><span data-ttu-id="81e9e-102">Gewusst wie: Aufrufen einer gespeicherten Prozedur mithilfe von LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="81e9e-102">How to: Call a Stored Procedure by Using LINQ (Visual Basic)</span></span>

<span data-ttu-id="81e9e-103">Language-Integrated Query (LINQ) vereinfacht den Zugriff auf Datenbankinformationen, einschließlich Datenbankobjekten wie z. b. gespeicherter Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="81e9e-103">Language-Integrated Query (LINQ) makes it easy to access database information, including database objects such as stored procedures.</span></span>  
  
 <span data-ttu-id="81e9e-104">Im folgenden Beispiel wird gezeigt, wie eine Anwendung erstellt wird, die eine gespeicherte Prozedur in einer SQL Server Datenbank aufruft.</span><span class="sxs-lookup"><span data-stu-id="81e9e-104">The following example shows how to create an application that calls a stored procedure in a SQL Server database.</span></span> <span data-ttu-id="81e9e-105">Das Beispiel zeigt, wie zwei verschiedene gespeicherte Prozeduren in der Datenbank aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="81e9e-105">The sample shows how to call two different stored procedures in the database.</span></span> <span data-ttu-id="81e9e-106">Jede Prozedur gibt die Ergebnisse einer Abfrage zurück.</span><span class="sxs-lookup"><span data-stu-id="81e9e-106">Each procedure returns the results of a query.</span></span> <span data-ttu-id="81e9e-107">Eine Prozedur übernimmt Eingabeparameter, und die andere Prozedur übernimmt keine Parameter.</span><span class="sxs-lookup"><span data-stu-id="81e9e-107">One procedure takes input parameters, and the other procedure does not take parameters.</span></span>  
  
 <span data-ttu-id="81e9e-108">In den Beispielen in diesem Thema wird die Beispieldatenbank Northwind verwendet.</span><span class="sxs-lookup"><span data-stu-id="81e9e-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="81e9e-109">Befindet sich diese Datenbank nicht auf Ihrem Entwicklungscomputer, können Sie sie aus dem Microsoft Download Center herunterladen.</span><span class="sxs-lookup"><span data-stu-id="81e9e-109">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="81e9e-110">Anweisungen hierzu finden Sie unter [Herunterladen von Beispiel Datenbanken](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="81e9e-110">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="81e9e-111">So erstellen Sie eine Verbindung mit einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="81e9e-111">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="81e9e-112">Öffnen Sie in Visual Studio **Server-Explorer** / **Datenbank-Explorer** , indem **Server Explorer**Sie / im Menü **Ansicht** auf Server-Explorer**Datenbank-Explorer** klicken.</span><span class="sxs-lookup"><span data-stu-id="81e9e-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="81e9e-113">Klicken Sie in **Server-Explorer**Datenbank-Explorer mit der rechten Maustaste auf **Datenverbindungen** / **Database Explorer** und dann auf **Verbindung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="81e9e-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="81e9e-114">Geben Sie eine gültige Verbindung mit der Northwind-Beispieldatenbank an.</span><span class="sxs-lookup"><span data-stu-id="81e9e-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="81e9e-115">So fügen Sie ein Projekt hinzu, das eine LINQ to SQL Datei enthält</span><span class="sxs-lookup"><span data-stu-id="81e9e-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="81e9e-116">Zeigen Sie in Visual Studio im Menü **Datei** auf **Neu**, und klicken Sie auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="81e9e-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="81e9e-117">Wählen Sie Visual Basic **Windows Forms Anwendung** als Projekttyp aus.</span><span class="sxs-lookup"><span data-stu-id="81e9e-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="81e9e-118">Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="81e9e-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="81e9e-119">Wählen Sie die Element Vorlage **LINQ to SQL Klassen** aus.</span><span class="sxs-lookup"><span data-stu-id="81e9e-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="81e9e-120">Benennen Sie die Datei mit `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="81e9e-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="81e9e-121">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="81e9e-121">Click **Add**.</span></span> <span data-ttu-id="81e9e-122">Der objektrelationaler Designer (O/R-Designer) wird für die Datei Northwind. dbml geöffnet.</span><span class="sxs-lookup"><span data-stu-id="81e9e-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-stored-procedures-to-the-or-designer"></a><span data-ttu-id="81e9e-123">So fügen Sie dem O/R-Designer gespeicherte Prozeduren hinzu</span><span class="sxs-lookup"><span data-stu-id="81e9e-123">To add stored procedures to the O/R Designer</span></span>  
  
1. <span data-ttu-id="81e9e-124">Erweitern Sie in **Server-Explorer** / **Datenbank-Explorer**die Verbindung mit der Northwind-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="81e9e-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="81e9e-125">Erweitern Sie den Ordner **Gespeicherte Prozeduren** .</span><span class="sxs-lookup"><span data-stu-id="81e9e-125">Expand the **Stored Procedures** folder.</span></span>  
  
     <span data-ttu-id="81e9e-126">Wenn Sie den O/R-Designer geschlossen haben, können Sie ihn erneut öffnen, indem Sie auf die Datei Northwind. dbml, die Sie zuvor hinzugefügt haben, doppelklicken.</span><span class="sxs-lookup"><span data-stu-id="81e9e-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="81e9e-127">Klicken Sie auf die gespeicherte Prozedur **Sales by Year** , und ziehen Sie Sie in den rechten Bereich des Designers.</span><span class="sxs-lookup"><span data-stu-id="81e9e-127">Click the **Sales by Year** stored procedure and drag it to the right pane of the designer.</span></span> <span data-ttu-id="81e9e-128">Wenn Sie auf die gespeicherte Prozedur mit den **zehn teuersten Produkten** klicken, ziehen Sie Sie in den rechten Bereich des Designers.</span><span class="sxs-lookup"><span data-stu-id="81e9e-128">Click the **Ten Most Expensive Products** stored procedure drag it to the right pane of the designer.</span></span>  
  
3. <span data-ttu-id="81e9e-129">Speichern Sie die Änderungen, und schließen Sie den Designer.</span><span class="sxs-lookup"><span data-stu-id="81e9e-129">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="81e9e-130">Speichern Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="81e9e-130">Save your project.</span></span>  
  
### <a name="to-add-code-to-display-the-results-of-the-stored-procedures"></a><span data-ttu-id="81e9e-131">So fügen Sie Code hinzu, um die Ergebnisse der gespeicherten Prozeduren anzuzeigen</span><span class="sxs-lookup"><span data-stu-id="81e9e-131">To add code to display the results of the stored procedures</span></span>  
  
1. <span data-ttu-id="81e9e-132">Ziehen Sie aus der **Toolbox**ein- <xref:System.Windows.Forms.DataGridView> Steuerelement auf das Windows-Standardformular für das Projekt, Form1.</span><span class="sxs-lookup"><span data-stu-id="81e9e-132">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="81e9e-133">Doppelklicken Sie auf Form1, um dem Ereignis Code hinzuzufügen `Load` .</span><span class="sxs-lookup"><span data-stu-id="81e9e-133">Double-click Form1 to add code to its `Load` event.</span></span>  
  
3. <span data-ttu-id="81e9e-134">Wenn Sie dem O/R-Designer gespeicherte Prozeduren hinzugefügt haben, hat der Designer ein- <xref:System.Data.Linq.DataContext> Objekt für das Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="81e9e-134">When you added stored procedures to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="81e9e-135">Dieses Objekt enthält den Code, den Sie für den Zugriff auf diese Prozeduren benötigen.</span><span class="sxs-lookup"><span data-stu-id="81e9e-135">This object contains the code that you must have to access those procedures.</span></span> <span data-ttu-id="81e9e-136">Das- <xref:System.Data.Linq.DataContext> Objekt für das Projekt wird basierend auf dem Namen der DBML-Datei benannt.</span><span class="sxs-lookup"><span data-stu-id="81e9e-136">The <xref:System.Data.Linq.DataContext> object for the project is named based on the name of the .dbml file.</span></span> <span data-ttu-id="81e9e-137">Für dieses Projekt hat das <xref:System.Data.Linq.DataContext> Objekt den Namen `northwindDataContext` .</span><span class="sxs-lookup"><span data-stu-id="81e9e-137">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="81e9e-138">Sie können eine Instanz von <xref:System.Data.Linq.DataContext> im Code erstellen und die im O/R-Designer angegebenen Methoden der gespeicherten Prozedur aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="81e9e-138">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and call the stored procedure methods specified by the O/R Designer.</span></span> <span data-ttu-id="81e9e-139">Zum Binden an das- <xref:System.Windows.Forms.DataGridView> Objekt müssen Sie möglicherweise erzwingen, dass die Abfrage sofort ausgeführt wird, indem Sie die- <xref:System.Linq.Enumerable.ToList%2A> Methode für die Ergebnisse der gespeicherten Prozedur aufrufen.</span><span class="sxs-lookup"><span data-stu-id="81e9e-139">To bind to the <xref:System.Windows.Forms.DataGridView> object, you may have to force the query to execute immediately by calling the <xref:System.Linq.Enumerable.ToList%2A> method on the results of the stored procedure.</span></span>  
  
     <span data-ttu-id="81e9e-140">Fügen Sie dem-Ereignis folgenden Code hinzu `Load` , um eine der gespeicherten Prozeduren aufzurufen, die als Methoden für den Datenkontext verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="81e9e-140">Add the following code to the `Load` event to call either of the stored procedures exposed as methods for your data context.</span></span>  
  
     [!code-vb[VbLINQtoSQLHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form3.vb#1)]  
    [!code-vb[VbLINQtoSQLHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form3.vb#2)]  
  
4. <span data-ttu-id="81e9e-141">Drücken Sie F5, um das Projekt auszuführen und die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="81e9e-141">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81e9e-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="81e9e-142">See also</span></span>

- [<span data-ttu-id="81e9e-143">LINQ</span><span class="sxs-lookup"><span data-stu-id="81e9e-143">LINQ</span></span>](index.md)
- [<span data-ttu-id="81e9e-144">Abfragen</span><span class="sxs-lookup"><span data-stu-id="81e9e-144">Queries</span></span>](../../../language-reference/queries/index.md)
- [<span data-ttu-id="81e9e-145">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="81e9e-145">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="81e9e-146">DataContext-Methoden (O/R-Designer)</span><span class="sxs-lookup"><span data-stu-id="81e9e-146">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [<span data-ttu-id="81e9e-147">Vorgehensweise: Zuweisen von gespeicherten Prozeduren zum Durchführen von Aktionen zum Aktualisieren, Einfügen und Löschen (O/R-Designer)</span><span class="sxs-lookup"><span data-stu-id="81e9e-147">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
