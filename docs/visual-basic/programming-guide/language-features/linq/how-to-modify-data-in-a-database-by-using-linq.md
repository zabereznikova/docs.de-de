---
title: 'Gewusst wie: Ändern von Daten in einer Datenbank mit LINQ (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- inserting rows [LINQ to SQL]
- deleting rows [LINQ to SQL]
- updating rows [LINQ to SQL]
- inserting data [Visual Basic]
- deleting data
- data [Visual Basic], updating
- updating data [LINQ]
- queries [LINQ in Visual Basic], data changes in database
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: cf52635f-0c1b-46c3-aff1-bdf181cf19b1
ms.openlocfilehash: 617bb62f9009c507658b5d1262657cb4dfa860e9
ms.sourcegitcommit: d955cb4c681d68cf301d410925d83f25172ece86
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/07/2018
ms.locfileid: "34827110"
---
# <a name="how-to-modify-data-in-a-database-by-using-linq-visual-basic"></a><span data-ttu-id="9dec8-102">Gewusst wie: Ändern von Daten in einer Datenbank mit LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9dec8-102">How to: Modify Data in a Database by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="9dec8-103">Language-Integrated Query (LINQ) Abfragen erleichtern die Datenbankinformationen zugreifen und ändern Sie die Werte in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="9dec8-103">Language-Integrated Query (LINQ) queries make it easy to access database information and modify values in the database.</span></span>  
  
 <span data-ttu-id="9dec8-104">Das folgende Beispiel zeigt, wie Sie eine neue Anwendung erstellen, die abruft und Updates Informationen in einer SQL Server-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="9dec8-104">The following example shows how to create a new application that retrieves and updates information in a SQL Server database.</span></span>  
  
 <span data-ttu-id="9dec8-105">In den Beispielen in diesem Thema verwenden die Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="9dec8-105">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="9dec8-106">Wenn Sie diese Datenbank nicht auf Ihrem Computer verfügen, können Sie es aus dem Microsoft Download Center herunterladen.</span><span class="sxs-lookup"><span data-stu-id="9dec8-106">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="9dec8-107">Anweisungen hierzu finden Sie unter [Herunterladen von Beispieldatenbanken](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="9dec8-107">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="9dec8-108">So erstellen eine Verbindung mit einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="9dec8-108">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="9dec8-109">Öffnen Sie in Visual Studio **Server-Explorer**/**Datenbank-Explorer** durch Klicken auf die **Ansicht** Menü, und wählen Sie dann **Server-Explorer** / **Datenbank-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="9dec8-109">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking the **View** menu, and then select **Server Explorer**/**Database Explorer**.</span></span>  
  
2.  <span data-ttu-id="9dec8-110">Mit der rechten Maustaste **Datenverbindungen** in **Server-Explorer**/**Datenbank-Explorer**, und klicken Sie auf **Verbindung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="9dec8-110">Right-click **Data Connections** in **Server Explorer**/**Database Explorer**, and click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="9dec8-111">Geben Sie eine gültige Verbindung mit der Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="9dec8-111">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-with-a-linq-to-sql-file"></a><span data-ttu-id="9dec8-112">Ein Projekt mit einer LINQ to SQL-Datei hinzufügen</span><span class="sxs-lookup"><span data-stu-id="9dec8-112">To add a Project with a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="9dec8-113">Zeigen Sie in Visual Studio im Menü **Datei** auf **Neu**, und klicken Sie auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="9dec8-113">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="9dec8-114">Wählen Sie Visual Basic **Windows Forms-Anwendung** als Projekttyp.</span><span class="sxs-lookup"><span data-stu-id="9dec8-114">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="9dec8-115">Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="9dec8-115">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="9dec8-116">Wählen Sie die **LINQ to SQL-Klassen** Elementvorlage.</span><span class="sxs-lookup"><span data-stu-id="9dec8-116">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="9dec8-117">Nennen Sie die Datei `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="9dec8-117">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="9dec8-118">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="9dec8-118">Click **Add**.</span></span> <span data-ttu-id="9dec8-119">Der Object Relational Designer (O/R-Designer) wird geöffnet, für die `northwind.dbml` Datei.</span><span class="sxs-lookup"><span data-stu-id="9dec8-119">The Object Relational Designer (O/R Designer) is opened for the `northwind.dbml` file.</span></span>  
  
### <a name="to-add-tables-to-query-and-modify-to-the-designer"></a><span data-ttu-id="9dec8-120">So fügen Sie Tabellen, um Abfragen und ändern in den Designer hinzu.</span><span class="sxs-lookup"><span data-stu-id="9dec8-120">To add tables to query and modify to the designer</span></span>  
  
1.  <span data-ttu-id="9dec8-121">In **Server-Explorer**/**Datenbank-Explorer**, erweitern Sie die Verbindung mit der Datenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="9dec8-121">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="9dec8-122">Erweitern Sie die **Tabellen** Ordner.</span><span class="sxs-lookup"><span data-stu-id="9dec8-122">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="9dec8-123">Wenn Sie im O/R-Designer geschlossen haben, können Sie es öffnen, durch Doppelklicken auf die `northwind.dbml` -Datei, die Sie zuvor hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="9dec8-123">If you have closed the O/R Designer, you can reopen it by double-clicking the `northwind.dbml` file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="9dec8-124">Klicken Sie auf der Customers-Tabelle, und ziehen Sie es in den linken Bereich des Designers.</span><span class="sxs-lookup"><span data-stu-id="9dec8-124">Click the Customers table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="9dec8-125">Der Designer erstellt ein neues Customer-Objekt für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="9dec8-125">The designer creates a new Customer object for your project.</span></span>  
  
3.  <span data-ttu-id="9dec8-126">Speichern Sie die Änderungen zu und schließen Sie den Designer.</span><span class="sxs-lookup"><span data-stu-id="9dec8-126">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="9dec8-127">Speichern Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="9dec8-127">Save your project.</span></span>  
  
### <a name="to-add-code-to-modify-the-database-and-display-the-results"></a><span data-ttu-id="9dec8-128">Fügen Sie Code zum Ändern der Datenbank und die Ergebnisse werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9dec8-128">To add code to modify the database and display the results</span></span>  
  
1.  <span data-ttu-id="9dec8-129">Aus der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.DataGridView> -Steuerelement auf die Standard-Windows Form für das Projekt, Form1.</span><span class="sxs-lookup"><span data-stu-id="9dec8-129">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="9dec8-130">Wenn Sie Tabellen in den O/R-Designer hinzugefügt haben, wird der Designer hinzugefügt ein <xref:System.Data.Linq.DataContext> -Objekt, das Projekt.</span><span class="sxs-lookup"><span data-stu-id="9dec8-130">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="9dec8-131">Dieses Objekt enthält Code, die Sie zum Zugreifen auf die Customers-Tabelle verwenden können.</span><span class="sxs-lookup"><span data-stu-id="9dec8-131">This object contains code that you can use to access the Customers table.</span></span> <span data-ttu-id="9dec8-132">Außerdem enthält Code, der ein lokales Customer-Objekt und eine Kunden-Auflistung für die Tabelle definiert.</span><span class="sxs-lookup"><span data-stu-id="9dec8-132">It also contains code that defines  a local Customer object and a Customers collection for the table.</span></span> <span data-ttu-id="9dec8-133">Die <xref:System.Data.Linq.DataContext> Objekt für das Projekt mit der Bezeichnung wird anhand des Namens der DBML-Datei.</span><span class="sxs-lookup"><span data-stu-id="9dec8-133">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="9dec8-134">Für dieses Projekt die <xref:System.Data.Linq.DataContext> Objekt heißt `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="9dec8-134">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="9dec8-135">Erstellen eine Instanz von der <xref:System.Data.Linq.DataContext> Objekt in Ihrem Code und die Abfrage, und ändern Sie die Customers-Auflistung, die vom O/R-Designer angegeben.</span><span class="sxs-lookup"><span data-stu-id="9dec8-135">You can create an instance of the <xref:System.Data.Linq.DataContext> object in your code and query and modify the Customers collection specified by the O/R Designer.</span></span> <span data-ttu-id="9dec8-136">Auf die Auflistung der Kunden vorgenommene Änderungen werden nicht in der Datenbank wiedergegeben, bis Sie sie, durch Aufrufen Senden der <xref:System.Data.Linq.DataContext.SubmitChanges%2A> Methode der <xref:System.Data.Linq.DataContext> Objekt.</span><span class="sxs-lookup"><span data-stu-id="9dec8-136">Changes that you make to the Customers collection are not reflected in the database until you submit them by calling the <xref:System.Data.Linq.DataContext.SubmitChanges%2A> method of the <xref:System.Data.Linq.DataContext> object.</span></span>  
  
     <span data-ttu-id="9dec8-137">Doppelklicken Sie auf das Windows Form, Form1, um zum Hinzufügen von Code die <xref:System.Windows.Forms.Form.Load> Ereignis, um die Abfrage, die die Customers-Tabelle als eine Eigenschaft verfügbar gemacht wird Ihre <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="9dec8-137">Double-click the Windows Form, Form1, to add code to the <xref:System.Windows.Forms.Form.Load> event to query the Customers table that is exposed as a property of your <xref:System.Data.Linq.DataContext>.</span></span> <span data-ttu-id="9dec8-138">Fügen Sie den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="9dec8-138">Add the following code:</span></span>  
  
    ```vb  
    Private db As northwindDataContext  
  
    Private Sub Form1_Load(ByVal sender As System.Object,   
                           ByVal e As System.EventArgs  
                          ) Handles MyBase.Load  
      db = New northwindDataContext()  
  
      RefreshData()  
    End Sub  
  
    Private Sub RefreshData()  
      Dim customers = From cust In db.Customers   
                      Where cust.City(0) = "W"   
                      Select cust  
  
      DataGridView1.DataSource = customers  
    End Sub  
    ```  
  
3.  <span data-ttu-id="9dec8-139">Aus der **Toolbox**, ziehen Sie drei <xref:System.Windows.Forms.Button> Steuerelemente auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="9dec8-139">From the **Toolbox**, drag three <xref:System.Windows.Forms.Button> controls onto the form.</span></span> <span data-ttu-id="9dec8-140">Wählen Sie die erste `Button` Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="9dec8-140">Select the first `Button` control.</span></span> <span data-ttu-id="9dec8-141">In der **Eigenschaften** legen der `Name` von der `Button` die Steuerung an `AddButton` und die `Text` zu `Add`.</span><span class="sxs-lookup"><span data-stu-id="9dec8-141">In the **Properties** window, set the `Name` of the `Button` control to `AddButton` and the `Text` to `Add`.</span></span> <span data-ttu-id="9dec8-142">Wählen Sie die zweite Schaltfläche, und legen die `Name` Eigenschaft `UpdateButton` und die `Text` Eigenschaft `Update`.</span><span class="sxs-lookup"><span data-stu-id="9dec8-142">Select the second button and set the `Name` property to `UpdateButton` and the `Text` property to `Update`.</span></span> <span data-ttu-id="9dec8-143">Wählen Sie die dritte Schaltfläche, und legen die `Name` Eigenschaft `DeleteButton` und die `Text` Eigenschaft `Delete`.</span><span class="sxs-lookup"><span data-stu-id="9dec8-143">Select the third button and set the `Name` property to `DeleteButton` and the `Text` property to `Delete`.</span></span>  
  
4.  <span data-ttu-id="9dec8-144">Doppelklicken Sie auf die **hinzufügen** Schaltfläche zum Hinzufügen von Code, dessen `Click` Ereignis.</span><span class="sxs-lookup"><span data-stu-id="9dec8-144">Double-click the **Add** button to add code to its `Click` event.</span></span> <span data-ttu-id="9dec8-145">Fügen Sie den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="9dec8-145">Add the following code:</span></span>  
  
    ```vb  
    Private Sub AddButton_Click(ByVal sender As System.Object,   
                                ByVal e As System.EventArgs  
                               ) Handles AddButton.Click  
      Dim cust As New Customer With {   
        .City = "Wellington",   
        .CompanyName = "Blue Yonder Airlines",   
        .ContactName = "Jill Frank",   
        .Country = "New Zealand",   
        .CustomerID = "JILLF"}  
  
      db.Customers.InsertOnSubmit(cust)  
  
      Try  
        db.SubmitChanges()  
      Catch  
        ' Handle exception.  
      End Try  
  
      RefreshData()  
    End Sub  
    ```  
  
5.  <span data-ttu-id="9dec8-146">Doppelklicken Sie auf die **Update** Schaltfläche zum Hinzufügen von Code, dessen `Click` Ereignis.</span><span class="sxs-lookup"><span data-stu-id="9dec8-146">Double-click the **Update** button to add code to its `Click` event.</span></span> <span data-ttu-id="9dec8-147">Fügen Sie den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="9dec8-147">Add the following code:</span></span>  
  
    ```vb  
    Private Sub UpdateButton_Click(ByVal sender As System.Object, _  
                                   ByVal e As System.EventArgs  
                                  ) Handles UpdateButton.Click  
      Dim updateCust = (From cust In db.Customers   
                        Where cust.CustomerID = "JILLF").ToList()(0)  
  
      updateCust.ContactName = "Jill Shrader"  
  
      Try  
        db.SubmitChanges()  
      Catch  
        ' Handle exception.  
      End Try  
  
      RefreshData()  
    End Sub  
    ```  
  
6.  <span data-ttu-id="9dec8-148">Doppelklicken Sie auf die **löschen** Schaltfläche zum Hinzufügen von Code, dessen `Click` Ereignis.</span><span class="sxs-lookup"><span data-stu-id="9dec8-148">Double-click the **Delete** button to add code to its `Click` event.</span></span> <span data-ttu-id="9dec8-149">Fügen Sie den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="9dec8-149">Add the following code:</span></span>  
  
    ```vb  
    Private Sub DeleteButton_Click(ByVal sender As System.Object, _  
                                   ByVal e As System.EventArgs  
                                  ) Handles DeleteButton.Click  
      Dim deleteCust = (From cust In db.Customers   
                        Where cust.CustomerID = "JILLF").ToList()(0)  
  
      db.Customers.DeleteOnSubmit(deleteCust)  
  
      Try  
        db.SubmitChanges()  
      Catch  
        ' Handle exception.  
      End Try  
  
      RefreshData()  
    End Sub  
    ```  
  
7.  <span data-ttu-id="9dec8-150">Drücken Sie F5, um das Projekt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="9dec8-150">Press F5 to run your project.</span></span> <span data-ttu-id="9dec8-151">Klicken Sie auf **hinzufügen** beim Hinzufügen eines neuen Datensatzes.</span><span class="sxs-lookup"><span data-stu-id="9dec8-151">Click **Add** to add a new record.</span></span> <span data-ttu-id="9dec8-152">Klicken Sie auf **Update** so ändern Sie den neuen Datensatz.</span><span class="sxs-lookup"><span data-stu-id="9dec8-152">Click **Update** to modify the new record.</span></span> <span data-ttu-id="9dec8-153">Klicken Sie auf **löschen** beim Löschen des neuen Datensatzes.</span><span class="sxs-lookup"><span data-stu-id="9dec8-153">Click **Delete** to delete the new record.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dec8-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9dec8-154">See Also</span></span>  
 [<span data-ttu-id="9dec8-155">LINQ</span><span class="sxs-lookup"><span data-stu-id="9dec8-155">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="9dec8-156">Abfragen</span><span class="sxs-lookup"><span data-stu-id="9dec8-156">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="9dec8-157">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="9dec8-157">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)  
 [<span data-ttu-id="9dec8-158">DataContext-Methoden (O/R-Designer)</span><span class="sxs-lookup"><span data-stu-id="9dec8-158">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)  
 [<span data-ttu-id="9dec8-159">Vorgehensweise: Zuweisen von gespeicherten Prozeduren zum Ausführen von Updates, einfügungen und löschen (O/R-Designer)</span><span class="sxs-lookup"><span data-stu-id="9dec8-159">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](http://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)
