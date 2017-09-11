---
title: 'Gewusst wie: Aufrufen einer gespeicherten Prozedur mithilfe von LINQ (Visual Basic) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- queries [LINQ in Visual Basic], stored procedure calls
- stored procedures sample [Visual Basic]
- stored procedures [LINQ to SQL]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 6436d384-d1e0-40aa-8afd-451007477260
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: 40e72ece8399b1ffbe8c5457c63113d563c9f7f8
ms.contentlocale: de-de
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-call-a-stored-procedure-by-using-linq-visual-basic"></a><span data-ttu-id="e772c-102">Gewusst wie: Aufrufen einer gespeicherten Prozedur mithilfe von LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e772c-102">How to: Call a Stored Procedure by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="e772c-103">Language-Integrated Query (LINQ) erleichtert die Datenbankinformationen, einschließlich Datenbankobjekten wie z. B. gespeicherte Prozeduren zugreifen.</span><span class="sxs-lookup"><span data-stu-id="e772c-103">Language-Integrated Query (LINQ) makes it easy to access database information, including database objects such as stored procedures.</span></span>  
  
 <span data-ttu-id="e772c-104">Im folgenden Beispiel wird veranschaulicht, wie eine Anwendung erstellen, die in einer SQL Server-Datenbank eine gespeicherte Prozedur aufruft.</span><span class="sxs-lookup"><span data-stu-id="e772c-104">The following example shows how to create an application that calls a stored procedure in a SQL Server database.</span></span> <span data-ttu-id="e772c-105">Das Beispiel zeigt, wie zwei verschiedene gespeicherte Prozeduren in der Datenbank aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="e772c-105">The sample shows how to call two different stored procedures in the database.</span></span> <span data-ttu-id="e772c-106">Jede Prozedur gibt die Ergebnisse einer Abfrage zurück.</span><span class="sxs-lookup"><span data-stu-id="e772c-106">Each procedure returns the results of a query.</span></span> <span data-ttu-id="e772c-107">Eine Prozedur, die Eingabeparameter akzeptiert, und die andere Prozedur nimmt keine Parameter.</span><span class="sxs-lookup"><span data-stu-id="e772c-107">One procedure takes input parameters, and the other procedure does not take parameters.</span></span>  
  
 <span data-ttu-id="e772c-108">In den Beispielen in diesem Thema verwenden die Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="e772c-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="e772c-109">Wenn Sie die Beispieldatenbank Northwind auf dem Entwicklungscomputer nicht haben, können Sie herunterladen aus der [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Website.</span><span class="sxs-lookup"><span data-stu-id="e772c-109">If you do not have the Northwind sample database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web site.</span></span> <span data-ttu-id="e772c-110">Eine Anleitung hierzu finden Sie unter [Herunterladen von Beispieldatenbanken](https://msdn.microsoft.com/library/bb399411).</span><span class="sxs-lookup"><span data-stu-id="e772c-110">For instructions, see [Downloading Sample Databases](https://msdn.microsoft.com/library/bb399411).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="e772c-111">Um eine Verbindung mit einer Datenbank zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e772c-111">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="e772c-112">Öffnen Sie in Visual Studio **Server-Explorer**/**Datenbank-Explorer** durch Klicken auf **Server-Explorer**/**Datenbank-Explorer** auf der **Ansicht** Menü.</span><span class="sxs-lookup"><span data-stu-id="e772c-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="e772c-113">Mit der rechten Maustaste **Datenverbindungen** in **Server-Explorer**/**Datenbank-Explorer** , und klicken Sie dann auf **Verbindung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="e772c-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="e772c-114">Geben Sie eine gültige Verbindung mit der Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="e772c-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="e772c-115">Ein Projekt hinzufügen, die eine LINQ to SQL-Datei enthält.</span><span class="sxs-lookup"><span data-stu-id="e772c-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="e772c-116">In Visual Studio auf die **Datei** auf **neu** , und klicken Sie dann auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="e772c-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="e772c-117">Wählen Sie Visual Basic **Windows Forms-Anwendung** als Projekttyp.</span><span class="sxs-lookup"><span data-stu-id="e772c-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="e772c-118">Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="e772c-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="e772c-119">Wählen Sie die **LINQ to SQL Classes** Elementvorlage.</span><span class="sxs-lookup"><span data-stu-id="e772c-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="e772c-120">Nennen Sie die Datei `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="e772c-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="e772c-121">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="e772c-121">Click **Add**.</span></span> <span data-ttu-id="e772c-122">Der Object Relational Designer (O/R-Designer) wird für die Datei northwind.dbml geöffnet.</span><span class="sxs-lookup"><span data-stu-id="e772c-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-stored-procedures-to-the-or-designer"></a><span data-ttu-id="e772c-123">Hinzufügen von gespeicherten Prozeduren in den O/R-Designer</span><span class="sxs-lookup"><span data-stu-id="e772c-123">To add stored procedures to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="e772c-124">In **Server-Explorer**/**Datenbank-Explorer**, erweitern Sie die Verbindung zur Northwind-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="e772c-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="e772c-125">Erweitern Sie die **gespeicherte Prozeduren** Ordner.</span><span class="sxs-lookup"><span data-stu-id="e772c-125">Expand the **Stored Procedures** folder.</span></span>  
  
     <span data-ttu-id="e772c-126">Wenn Sie den O/R-Designer geschlossen haben, können Sie es durch Doppelklicken auf die Sie zuvor hinzugefügte Datei northwind.dbml erneut öffnen.</span><span class="sxs-lookup"><span data-stu-id="e772c-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="e772c-127">Klicken Sie auf die **Sales by Year** gespeicherte Prozedur, und ziehen Sie es in den rechten Bereich des Designers.</span><span class="sxs-lookup"><span data-stu-id="e772c-127">Click the **Sales by Year** stored procedure and drag it to the right pane of the designer.</span></span> <span data-ttu-id="e772c-128">Klicken Sie auf die **Ten Most Expensive Products** gespeicherte Prozedur ziehen Sie es in den rechten Bereich des Designers.</span><span class="sxs-lookup"><span data-stu-id="e772c-128">Click the **Ten Most Expensive Products** stored procedure drag it to the right pane of the designer.</span></span>  
  
3.  <span data-ttu-id="e772c-129">Speichern Sie die Änderungen und schließen Sie den Designer.</span><span class="sxs-lookup"><span data-stu-id="e772c-129">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="e772c-130">Speichern Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="e772c-130">Save your project.</span></span>  
  
### <a name="to-add-code-to-display-the-results-of-the-stored-procedures"></a><span data-ttu-id="e772c-131">Hinzufügen von Code zum Anzeigen der Ergebnisse der gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="e772c-131">To add code to display the results of the stored procedures</span></span>  
  
1.  <span data-ttu-id="e772c-132">Aus der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.DataGridView>-Steuerelement auf das Standard-Windows Form für Ihr Projekt, Form1.</xref:System.Windows.Forms.DataGridView></span><span class="sxs-lookup"><span data-stu-id="e772c-132">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="e772c-133">Doppelklicken Sie auf Form1, um Code zum Hinzufügen der `Load` Ereignis.</span><span class="sxs-lookup"><span data-stu-id="e772c-133">Double-click Form1 to add code to its `Load` event.</span></span>  
  
3.  <span data-ttu-id="e772c-134">Wenn Sie gespeicherte Prozeduren in den O/R-Designer hinzugefügt haben, wird der Designer hinzugefügt ein <xref:System.Data.Linq.DataContext>-Objekt für das Projekt.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="e772c-134">When you added stored procedures to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="e772c-135">Dieses Objekt enthält den Code, den Sie benötigen, um diese Prozeduren zugreifen.</span><span class="sxs-lookup"><span data-stu-id="e772c-135">This object contains the code that you must have to access those procedures.</span></span> <span data-ttu-id="e772c-136">Das <xref:System.Data.Linq.DataContext>-Objekt für das Projekt mit dem Namen basierend auf den Namen der DBML-Datei.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="e772c-136">The <xref:System.Data.Linq.DataContext> object for the project is named based on the name of the .dbml file.</span></span> <span data-ttu-id="e772c-137">Für dieses Projekt die <xref:System.Data.Linq.DataContext>-Objekt mit dem Namen `northwindDataContext`.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="e772c-137">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="e772c-138">Erstellen Sie können eine Instanz von der <xref:System.Data.Linq.DataContext>in Ihrem Code und den Aufruf der gespeicherten Prozedur-Methoden, die vom O/R-Designer angegeben.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="e772c-138">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and call the stored procedure methods specified by the O/R Designer.</span></span> <span data-ttu-id="e772c-139">Zum Binden an die <xref:System.Windows.Forms.DataGridView>Objekt möglicherweise müssen Sie erzwingen, dass die auszuführende Abfrage sofort durch Aufrufen der <xref:System.Linq.Enumerable.ToList%2A>-Methode für die Ergebnisse der gespeicherten Prozedur.</xref:System.Linq.Enumerable.ToList%2A> </xref:System.Windows.Forms.DataGridView></span><span class="sxs-lookup"><span data-stu-id="e772c-139">To bind to the <xref:System.Windows.Forms.DataGridView> object, you may have to force the query to execute immediately by calling the <xref:System.Linq.Enumerable.ToList%2A> method on the results of the stored procedure.</span></span>  
  
     <span data-ttu-id="e772c-140">Fügen Sie den folgenden Code der `Load` Ereignis Aufrufen einer der gespeicherten Prozeduren, die als Methoden für Ihren Datenkontext verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="e772c-140">Add the following code to the `Load` event to call either of the stored procedures exposed as methods for your data context.</span></span>  
  
     <span data-ttu-id="e772c-141">[!code-vb[VbLINQtoSQLHowTos&#1;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="e772c-141">[!code-vb[VbLINQtoSQLHowTos#1](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_1.vb)]</span></span>  
    <span data-ttu-id="e772c-142">[!code-vb[VbLINQtoSQLHowTos&#2;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="e772c-142">[!code-vb[VbLINQtoSQLHowTos#2](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_2.vb)]</span></span>  
  
4.  <span data-ttu-id="e772c-143">Drücken Sie F5, um das Projekt auszuführen und die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e772c-143">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e772c-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e772c-144">See Also</span></span>  
 <span data-ttu-id="e772c-145">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="e772c-145">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="e772c-146"> [Abfragen](../../../../visual-basic/language-reference/queries/queries.md) </span><span class="sxs-lookup"><span data-stu-id="e772c-146"> [Queries](../../../../visual-basic/language-reference/queries/queries.md) </span></span>  
<span data-ttu-id="e772c-147"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span><span class="sxs-lookup"><span data-stu-id="e772c-147"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span></span>  
<span data-ttu-id="e772c-148"> [DataContext-Methoden (O/R-Designer)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer) </span><span class="sxs-lookup"><span data-stu-id="e772c-148"> [DataContext Methods (O/R Designer)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer) </span></span>  
<span data-ttu-id="e772c-149"> [Gewusst wie: Zuweisen von gespeicherten Prozeduren zum Aktualisieren, einfügen und löschen (O/R-Designer) ausführen.](http://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)</span><span class="sxs-lookup"><span data-stu-id="e772c-149"> [How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)](http://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)</span></span>

