---
title: 'Vorgehensweise: Ändern von Daten in einer Datenbank mithilfe von LINQ'
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
ms.openlocfilehash: 9a10efef5ae92dd21888594ae80a3fc07869a8c0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344946"
---
# <a name="how-to-modify-data-in-a-database-by-using-linq-visual-basic"></a><span data-ttu-id="2ee54-102">Gewusst wie: Ändern von Daten in einer Datenbank mit LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2ee54-102">How to: Modify Data in a Database by Using LINQ (Visual Basic)</span></span>

<span data-ttu-id="2ee54-103">LINQ-Abfragen (Language-Integrated Query) erleichtern den Zugriff auf Datenbankinformationen und das Ändern von Werten in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="2ee54-103">Language-Integrated Query (LINQ) queries make it easy to access database information and modify values in the database.</span></span>

<span data-ttu-id="2ee54-104">Im folgenden Beispiel wird gezeigt, wie Sie eine neue Anwendung erstellen, die Informationen in einer SQL Server-Datenbank abruft und aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="2ee54-104">The following example shows how to create a new application that retrieves and updates information in a SQL Server database.</span></span>

<span data-ttu-id="2ee54-105">In den Beispielen in diesem Thema wird die Beispieldatenbank Northwind verwendet.</span><span class="sxs-lookup"><span data-stu-id="2ee54-105">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="2ee54-106">Befindet sich diese Datenbank nicht auf Ihrem Entwicklungscomputer, können Sie diese aus dem Microsoft Download Center herunterladen.</span><span class="sxs-lookup"><span data-stu-id="2ee54-106">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="2ee54-107">Anweisungen hierzu finden Sie unter [Herunterladen von Beispiel Datenbanken](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="2ee54-107">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>

### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="2ee54-108">So erstellen Sie eine Verbindung mit einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="2ee54-108">To create a connection to a database</span></span>

1. <span data-ttu-id="2ee54-109">Öffnen Sie in Visual Studio **Server-Explorer**/**Datenbank-Explorer** , indem Sie auf das Menü **Ansicht** und dann auf **Server-Explorer**/**Datenbank-Explorer**klicken.</span><span class="sxs-lookup"><span data-stu-id="2ee54-109">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking the **View** menu, and then select **Server Explorer**/**Database Explorer**.</span></span>

2. <span data-ttu-id="2ee54-110">Klicken Sie in **Server-Explorer**/**Datenbank-Explorer**mit der rechten Maustaste auf **Datenverbindungen** , und klicken Sie auf **Verbindung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="2ee54-110">Right-click **Data Connections** in **Server Explorer**/**Database Explorer**, and click **Add Connection**.</span></span>

3. <span data-ttu-id="2ee54-111">Geben Sie eine gültige Verbindung mit der Northwind-Beispieldatenbank an.</span><span class="sxs-lookup"><span data-stu-id="2ee54-111">Specify a valid connection to the Northwind sample database.</span></span>

### <a name="to-add-a-project-with-a-linq-to-sql-file"></a><span data-ttu-id="2ee54-112">So fügen Sie ein Projekt mit einer LINQ to SQL Datei hinzu</span><span class="sxs-lookup"><span data-stu-id="2ee54-112">To add a Project with a LINQ to SQL file</span></span>

1. <span data-ttu-id="2ee54-113">Zeigen Sie in Visual Studio im Menü **Datei** auf **Neu**, und klicken Sie auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="2ee54-113">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="2ee54-114">Wählen Sie Visual Basic **Windows Forms Anwendung** als Projekttyp aus.</span><span class="sxs-lookup"><span data-stu-id="2ee54-114">Select Visual Basic **Windows Forms Application** as the project type.</span></span>

2. <span data-ttu-id="2ee54-115">Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="2ee54-115">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="2ee54-116">Wählen Sie die Element Vorlage **LINQ to SQL Klassen** aus.</span><span class="sxs-lookup"><span data-stu-id="2ee54-116">Select the **LINQ to SQL Classes** item template.</span></span>

3. <span data-ttu-id="2ee54-117">Nennen Sie die Datei `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="2ee54-117">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="2ee54-118">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="2ee54-118">Click **Add**.</span></span> <span data-ttu-id="2ee54-119">Der objektrelationaler Designer (O/R-Designer) wird für die `northwind.dbml`-Datei geöffnet.</span><span class="sxs-lookup"><span data-stu-id="2ee54-119">The Object Relational Designer (O/R Designer) is opened for the `northwind.dbml` file.</span></span>

### <a name="to-add-tables-to-query-and-modify-to-the-designer"></a><span data-ttu-id="2ee54-120">So fügen Sie Tabellen zum Abfragen und Ändern des Designers hinzu</span><span class="sxs-lookup"><span data-stu-id="2ee54-120">To add tables to query and modify to the designer</span></span>

1. <span data-ttu-id="2ee54-121">Erweitern Sie in **Server-Explorer**/**Datenbank-Explorer**die Verbindung mit der Northwind-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="2ee54-121">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="2ee54-122">Erweitern Sie den Ordner **Tabellen** .</span><span class="sxs-lookup"><span data-stu-id="2ee54-122">Expand the **Tables** folder.</span></span>

     <span data-ttu-id="2ee54-123">Wenn Sie den O/R-Designer geschlossen haben, können Sie ihn erneut öffnen, indem Sie auf die `northwind.dbml` Datei doppelklicken, die Sie zuvor hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="2ee54-123">If you have closed the O/R Designer, you can reopen it by double-clicking the `northwind.dbml` file that you added earlier.</span></span>

2. <span data-ttu-id="2ee54-124">Klicken Sie auf die Tabelle Customers, und ziehen Sie Sie in den linken Bereich des Designers.</span><span class="sxs-lookup"><span data-stu-id="2ee54-124">Click the Customers table and drag it to the left pane of the designer.</span></span>

     <span data-ttu-id="2ee54-125">Der Designer erstellt ein neues Customer-Objekt für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="2ee54-125">The designer creates a new Customer object for your project.</span></span>

3. <span data-ttu-id="2ee54-126">Speichern Sie die Änderungen, und schließen Sie den Designer.</span><span class="sxs-lookup"><span data-stu-id="2ee54-126">Save your changes and close the designer.</span></span>

4. <span data-ttu-id="2ee54-127">Speichern Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="2ee54-127">Save your project.</span></span>

### <a name="to-add-code-to-modify-the-database-and-display-the-results"></a><span data-ttu-id="2ee54-128">So fügen Sie Code hinzu, um die Datenbank zu ändern und die Ergebnisse anzuzeigen</span><span class="sxs-lookup"><span data-stu-id="2ee54-128">To add code to modify the database and display the results</span></span>

1. <span data-ttu-id="2ee54-129">Ziehen Sie aus der **Toolbox**ein <xref:System.Windows.Forms.DataGridView>-Steuerelement auf das standardmäßige Windows Form für Ihr Projekt, Form1.</span><span class="sxs-lookup"><span data-stu-id="2ee54-129">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>

2. <span data-ttu-id="2ee54-130">Wenn Sie dem O/R-Designer Tabellen hinzugefügt haben, hat der Designer dem Projekt ein <xref:System.Data.Linq.DataContext> Objekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2ee54-130">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="2ee54-131">Dieses Objekt enthält Code, den Sie für den Zugriff auf die Customers-Tabelle verwenden können.</span><span class="sxs-lookup"><span data-stu-id="2ee54-131">This object contains code that you can use to access the Customers table.</span></span> <span data-ttu-id="2ee54-132">Sie enthält auch Code, der ein lokales Kunden Objekt und eine Kunden Auflistung für die Tabelle definiert.</span><span class="sxs-lookup"><span data-stu-id="2ee54-132">It also contains code that defines  a local Customer object and a Customers collection for the table.</span></span> <span data-ttu-id="2ee54-133">Das <xref:System.Data.Linq.DataContext>-Objekt für das Projekt wird basierend auf dem Namen der DBML-Datei benannt.</span><span class="sxs-lookup"><span data-stu-id="2ee54-133">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="2ee54-134">Für dieses Projekt wird das <xref:System.Data.Linq.DataContext> Objekt `northwindDataContext`benannt.</span><span class="sxs-lookup"><span data-stu-id="2ee54-134">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>

     <span data-ttu-id="2ee54-135">Sie können eine Instanz des <xref:System.Data.Linq.DataContext> Objekts im Code erstellen und die vom O/R-Designer angegebene Kunden Auflistung Abfragen und ändern.</span><span class="sxs-lookup"><span data-stu-id="2ee54-135">You can create an instance of the <xref:System.Data.Linq.DataContext> object in your code and query and modify the Customers collection specified by the O/R Designer.</span></span> <span data-ttu-id="2ee54-136">Änderungen, die Sie an der Customers-Sammlung vornehmen, werden erst dann in der Datenbank wiedergegeben, wenn Sie Sie durch Aufrufen der <xref:System.Data.Linq.DataContext.SubmitChanges%2A>-Methode des <xref:System.Data.Linq.DataContext>-Objekts übermitteln.</span><span class="sxs-lookup"><span data-stu-id="2ee54-136">Changes that you make to the Customers collection are not reflected in the database until you submit them by calling the <xref:System.Data.Linq.DataContext.SubmitChanges%2A> method of the <xref:System.Data.Linq.DataContext> object.</span></span>

     <span data-ttu-id="2ee54-137">Doppelklicken Sie auf das Windows Form Form1, um dem <xref:System.Windows.Forms.Form.Load>-Ereignis Code zum Abfragen der Customers-Tabelle hinzuzufügen, die als Eigenschaft ihrer <xref:System.Data.Linq.DataContext>verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="2ee54-137">Double-click the Windows Form, Form1, to add code to the <xref:System.Windows.Forms.Form.Load> event to query the Customers table that is exposed as a property of your <xref:System.Data.Linq.DataContext>.</span></span> <span data-ttu-id="2ee54-138">Fügen Sie den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="2ee54-138">Add the following code:</span></span>

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

3. <span data-ttu-id="2ee54-139">Ziehen Sie aus der **Toolbox**drei <xref:System.Windows.Forms.Button>-Steuerelemente auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="2ee54-139">From the **Toolbox**, drag three <xref:System.Windows.Forms.Button> controls onto the form.</span></span> <span data-ttu-id="2ee54-140">Wählen Sie das erste `Button` Steuerelement aus.</span><span class="sxs-lookup"><span data-stu-id="2ee54-140">Select the first `Button` control.</span></span> <span data-ttu-id="2ee54-141">Legen Sie im Fenster **Eigenschaften** die `Name` des `Button` Steuer Elements auf `AddButton` und die `Text` auf `Add`fest.</span><span class="sxs-lookup"><span data-stu-id="2ee54-141">In the **Properties** window, set the `Name` of the `Button` control to `AddButton` and the `Text` to `Add`.</span></span> <span data-ttu-id="2ee54-142">Wählen Sie die zweite Schaltfläche aus, und legen Sie die `Name`-Eigenschaft auf `UpdateButton` und die Eigenschaft `Text` auf `Update`fest.</span><span class="sxs-lookup"><span data-stu-id="2ee54-142">Select the second button and set the `Name` property to `UpdateButton` and the `Text` property to `Update`.</span></span> <span data-ttu-id="2ee54-143">Wählen Sie die dritte Schaltfläche aus, und legen Sie die `Name`-Eigenschaft auf `DeleteButton` und die Eigenschaft `Text` auf `Delete`fest.</span><span class="sxs-lookup"><span data-stu-id="2ee54-143">Select the third button and set the `Name` property to `DeleteButton` and the `Text` property to `Delete`.</span></span>

4. <span data-ttu-id="2ee54-144">Doppelklicken Sie auf die Schaltfläche **Hinzufügen** , um dem `Click` Ereignis Code hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="2ee54-144">Double-click the **Add** button to add code to its `Click` event.</span></span> <span data-ttu-id="2ee54-145">Fügen Sie den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="2ee54-145">Add the following code:</span></span>

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

5. <span data-ttu-id="2ee54-146">Doppelklicken Sie auf die Schaltfläche **Aktualisieren** , um dem `Click` Ereignis Code hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="2ee54-146">Double-click the **Update** button to add code to its `Click` event.</span></span> <span data-ttu-id="2ee54-147">Fügen Sie den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="2ee54-147">Add the following code:</span></span>

    ```vb
    Private Sub UpdateButton_Click(ByVal sender As System.Object, _
                                   ByVal e As System.EventArgs
                                  ) Handles UpdateButton.Click
      Dim updateCust = (From cust In db.Customers
                        Where cust.CustomerID = "JILLF").ToList()(0)

      updateCust.ContactName = "Jill Shrader"
      updateCust.Country = "Wales"
      updateCust.CompanyName = "Red Yonder Airlines"
      updateCust.City = "Cardiff"

      Try
        db.SubmitChanges()
      Catch
        ' Handle exception.
      End Try

      RefreshData()
    End Sub
    ```

6. <span data-ttu-id="2ee54-148">Doppelklicken Sie auf die Schaltfläche **Löschen** , um dem `Click` Ereignis Code hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="2ee54-148">Double-click the **Delete** button to add code to its `Click` event.</span></span> <span data-ttu-id="2ee54-149">Fügen Sie den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="2ee54-149">Add the following code:</span></span>

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

7. <span data-ttu-id="2ee54-150">Drücken Sie F5, um das Projekt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2ee54-150">Press F5 to run your project.</span></span> <span data-ttu-id="2ee54-151">Klicken Sie auf **Add** , um einen neuen Datensatz hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="2ee54-151">Click **Add** to add a new record.</span></span> <span data-ttu-id="2ee54-152">Klicken Sie auf **Aktualisieren** , um den neuen Datensatz zu ändern.</span><span class="sxs-lookup"><span data-stu-id="2ee54-152">Click **Update** to modify the new record.</span></span> <span data-ttu-id="2ee54-153">Klicken Sie auf **Löschen** , um den neuen Datensatz zu löschen.</span><span class="sxs-lookup"><span data-stu-id="2ee54-153">Click **Delete** to delete the new record.</span></span>

## <a name="see-also"></a><span data-ttu-id="2ee54-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ee54-154">See also</span></span>

- [<span data-ttu-id="2ee54-155">LINQ</span><span class="sxs-lookup"><span data-stu-id="2ee54-155">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="2ee54-156">Abfragen</span><span class="sxs-lookup"><span data-stu-id="2ee54-156">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="2ee54-157">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="2ee54-157">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="2ee54-158">DataContext-Methoden (O/R-Designer)</span><span class="sxs-lookup"><span data-stu-id="2ee54-158">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [<span data-ttu-id="2ee54-159">Vorgehensweise: Zuweisen von gespeicherten Prozeduren zum Durchführen von Aktionen zum Aktualisieren, Einfügen und Löschen (O/R-Designer)</span><span class="sxs-lookup"><span data-stu-id="2ee54-159">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
