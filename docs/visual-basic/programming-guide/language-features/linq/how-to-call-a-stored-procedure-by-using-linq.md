---
title: 'Gewusst wie: Aufrufen einer gespeicherten Prozedur mithilfe von LINQ (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- queries [LINQ in Visual Basic], stored procedure calls
- stored procedures sample [Visual Basic]
- stored procedures [LINQ to SQL]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 6436d384-d1e0-40aa-8afd-451007477260
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 943bf4c80d88633cad857896381efcbef69683cc
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2017
---
# <a name="how-to-call-a-stored-procedure-by-using-linq-visual-basic"></a><span data-ttu-id="f730b-102">Gewusst wie: Aufrufen einer gespeicherten Prozedur mithilfe von LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f730b-102">How to: Call a Stored Procedure by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="f730b-103">Language-Integrated Query (LINQ) erleichtert die Datenbankinformationen, einschließlich Datenbankobjekten wie z. B. gespeicherte Prozeduren zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f730b-103">Language-Integrated Query (LINQ) makes it easy to access database information, including database objects such as stored procedures.</span></span>  
  
 <span data-ttu-id="f730b-104">Das folgende Beispiel zeigt, wie eine Anwendung erstellen, die in einer SQL Server-Datenbank eine gespeicherte Prozedur aufruft.</span><span class="sxs-lookup"><span data-stu-id="f730b-104">The following example shows how to create an application that calls a stored procedure in a SQL Server database.</span></span> <span data-ttu-id="f730b-105">Das Beispiel zeigt, wie zwei verschiedene gespeicherte Prozeduren in der Datenbank aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="f730b-105">The sample shows how to call two different stored procedures in the database.</span></span> <span data-ttu-id="f730b-106">Jede Prozedur gibt die Ergebnisse einer Abfrage zurück.</span><span class="sxs-lookup"><span data-stu-id="f730b-106">Each procedure returns the results of a query.</span></span> <span data-ttu-id="f730b-107">Eine Prozedur verwendet die Eingabeparameter, und die andere Prozedur akzeptiert Parameter.</span><span class="sxs-lookup"><span data-stu-id="f730b-107">One procedure takes input parameters, and the other procedure does not take parameters.</span></span>  
  
 <span data-ttu-id="f730b-108">In den Beispielen in diesem Thema verwenden die Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="f730b-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="f730b-109">Wenn Sie die Beispieldatenbank Northwind nicht auf Ihrem Computer verfügen, können Sie laden Sie es der [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Website.</span><span class="sxs-lookup"><span data-stu-id="f730b-109">If you do not have the Northwind sample database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web site.</span></span> <span data-ttu-id="f730b-110">Anweisungen hierzu finden Sie unter [Herunterladen von Beispieldatenbanken](../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="f730b-110">For instructions, see [Downloading Sample Databases](../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="f730b-111">So erstellen eine Verbindung mit einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="f730b-111">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="f730b-112">Öffnen Sie in Visual Studio **Server-Explorer**/**Datenbank-Explorer** durch Klicken auf **Server-Explorer**/**Datenbank Explorer** auf die **Ansicht** Menü.</span><span class="sxs-lookup"><span data-stu-id="f730b-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="f730b-113">Mit der rechten Maustaste **Datenverbindungen** in **Server-Explorer**/**Datenbank-Explorer** , und klicken Sie dann auf **Verbindung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f730b-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="f730b-114">Geben Sie eine gültige Verbindung mit der Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="f730b-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="f730b-115">Ein Projekt hinzufügen, die eine LINQ to SQL-Datei enthält.</span><span class="sxs-lookup"><span data-stu-id="f730b-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="f730b-116">Zeigen Sie in Visual Studio im Menü **Datei** auf **Neu**, und klicken Sie auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="f730b-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="f730b-117">Wählen Sie Visual Basic **Windows Forms-Anwendung** als Projekttyp.</span><span class="sxs-lookup"><span data-stu-id="f730b-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="f730b-118">Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f730b-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="f730b-119">Wählen Sie die **LINQ to SQL-Klassen** Elementvorlage.</span><span class="sxs-lookup"><span data-stu-id="f730b-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="f730b-120">Nennen Sie die Datei `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="f730b-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="f730b-121">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f730b-121">Click **Add**.</span></span> <span data-ttu-id="f730b-122">Der Object Relational Designer (O/R-Designer) wird für die Datei northwind.dbml geöffnet.</span><span class="sxs-lookup"><span data-stu-id="f730b-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-stored-procedures-to-the-or-designer"></a><span data-ttu-id="f730b-123">Gespeicherte Prozeduren in den O/R-Designer hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f730b-123">To add stored procedures to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="f730b-124">In **Server-Explorer**/**Datenbank-Explorer**, erweitern Sie die Verbindung mit der Datenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="f730b-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="f730b-125">Erweitern Sie die **gespeicherte Prozeduren** Ordner.</span><span class="sxs-lookup"><span data-stu-id="f730b-125">Expand the **Stored Procedures** folder.</span></span>  
  
     <span data-ttu-id="f730b-126">Wenn Sie im O/R-Designer geschlossen haben, können Sie es durch Doppelklicken auf die Datei northwind.dbml, die Sie zuvor hinzugefügt haben erneut öffnen.</span><span class="sxs-lookup"><span data-stu-id="f730b-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="f730b-127">Klicken Sie auf die **Umsatz nach Jahr** gespeicherte Prozedur, und ziehen Sie es in den rechten Bereich des Designers.</span><span class="sxs-lookup"><span data-stu-id="f730b-127">Click the **Sales by Year** stored procedure and drag it to the right pane of the designer.</span></span> <span data-ttu-id="f730b-128">Klicken Sie auf die **zehn teuersten Artikel** gespeicherte Prozedur ziehen Sie es in den rechten Bereich des Designers.</span><span class="sxs-lookup"><span data-stu-id="f730b-128">Click the **Ten Most Expensive Products** stored procedure drag it to the right pane of the designer.</span></span>  
  
3.  <span data-ttu-id="f730b-129">Speichern Sie die Änderungen zu und schließen Sie den Designer.</span><span class="sxs-lookup"><span data-stu-id="f730b-129">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="f730b-130">Speichern Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="f730b-130">Save your project.</span></span>  
  
### <a name="to-add-code-to-display-the-results-of-the-stored-procedures"></a><span data-ttu-id="f730b-131">Hinzufügen von Code zum Anzeigen der Ergebnisse der gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="f730b-131">To add code to display the results of the stored procedures</span></span>  
  
1.  <span data-ttu-id="f730b-132">Aus der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.DataGridView> -Steuerelement auf die Standard-Windows Form für das Projekt, Form1.</span><span class="sxs-lookup"><span data-stu-id="f730b-132">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="f730b-133">Doppelklicken Sie auf Form1, um zum Hinzufügen von Code die `Load` Ereignis.</span><span class="sxs-lookup"><span data-stu-id="f730b-133">Double-click Form1 to add code to its `Load` event.</span></span>  
  
3.  <span data-ttu-id="f730b-134">Wenn Sie gespeicherte Prozeduren in den O/R-Designer hinzugefügt haben, wird der Designer hinzugefügt ein <xref:System.Data.Linq.DataContext> Objekt für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="f730b-134">When you added stored procedures to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="f730b-135">Dieses Objekt enthält den Code, den Sie benötigen diese Prozeduren zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f730b-135">This object contains the code that you must have to access those procedures.</span></span> <span data-ttu-id="f730b-136">Die <xref:System.Data.Linq.DataContext> Objekt für das Projekt mit der Bezeichnung wird anhand des Namens der DBML-Datei.</span><span class="sxs-lookup"><span data-stu-id="f730b-136">The <xref:System.Data.Linq.DataContext> object for the project is named based on the name of the .dbml file.</span></span> <span data-ttu-id="f730b-137">Für dieses Projekt die <xref:System.Data.Linq.DataContext> Objekt heißt `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="f730b-137">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="f730b-138">Erstellen eine Instanz von der <xref:System.Data.Linq.DataContext> in Ihrem Code, und rufen die gespeicherte Prozedur-Methoden, die vom O/R-Designer angegeben.</span><span class="sxs-lookup"><span data-stu-id="f730b-138">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and call the stored procedure methods specified by the O/R Designer.</span></span> <span data-ttu-id="f730b-139">Zum Binden an die <xref:System.Windows.Forms.DataGridView> Objekt möglicherweise so erzwingen die auszuführende Abfrage sofort durch Aufrufen der <xref:System.Linq.Enumerable.ToList%2A> -Methode für die Ergebnisse der gespeicherten Prozedur.</span><span class="sxs-lookup"><span data-stu-id="f730b-139">To bind to the <xref:System.Windows.Forms.DataGridView> object, you may have to force the query to execute immediately by calling the <xref:System.Linq.Enumerable.ToList%2A> method on the results of the stored procedure.</span></span>  
  
     <span data-ttu-id="f730b-140">Fügen Sie folgenden Code, der `Load` Ereignis aufrufen, entweder die gespeicherten Prozeduren, die als Methoden für Ihren Datenkontext verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="f730b-140">Add the following code to the `Load` event to call either of the stored procedures exposed as methods for your data context.</span></span>  
  
     [!code-vb[VbLINQtoSQLHowTos#1](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_1.vb)]  
    [!code-vb[VbLINQtoSQLHowTos#2](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_2.vb)]  
  
4.  <span data-ttu-id="f730b-141">Drücken Sie F5, um das Projekt auszuführen und die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f730b-141">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f730b-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f730b-142">See Also</span></span>  
 [<span data-ttu-id="f730b-143">LINQ</span><span class="sxs-lookup"><span data-stu-id="f730b-143">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="f730b-144">Abfragen</span><span class="sxs-lookup"><span data-stu-id="f730b-144">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="f730b-145">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="f730b-145">LINQ to SQL</span></span>](../../../../../docs/framework/data/adonet/sql/linq/index.md)  
 [<span data-ttu-id="f730b-146">DataContext-Methoden (O/R-Designer)</span><span class="sxs-lookup"><span data-stu-id="f730b-146">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)  
 [<span data-ttu-id="f730b-147">Vorgehensweise: Zuweisen von gespeicherten Prozeduren zum Ausführen von Updates, einfügungen und löschen (O/R-Designer)</span><span class="sxs-lookup"><span data-stu-id="f730b-147">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](http://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)
