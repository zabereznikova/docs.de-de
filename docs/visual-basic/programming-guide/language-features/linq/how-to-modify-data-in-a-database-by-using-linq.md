---
title: "Gewusst wie: Ändern von Daten in einer Datenbank mit LINQ (Visual Basic) | Microsoft-Dokumentation"
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
caps.latest.revision: 15
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
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2d230594345cff26a83907714e5e8e11b10dde60
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-modify-data-in-a-database-by-using-linq-visual-basic"></a><span data-ttu-id="e4ed2-102">Gewusst wie: Ändern von Daten in einer Datenbank mit LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e4ed2-102">How to: Modify Data in a Database by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="e4ed2-103">Language-Integrated Query (LINQ) Abfragen erleichtern den Zugriff auf Datenbankinformationen und Ändern von Werten in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="e4ed2-103">Language-Integrated Query (LINQ) queries make it easy to access database information and modify values in the database.</span></span>  
  
 <span data-ttu-id="e4ed2-104">Das folgende Beispiel zeigt eine neue Anwendung erstellen, die abruft und Informationen zu Softwareupdates in einer SQL Server-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="e4ed2-104">The following example shows how to create a new application that retrieves and updates information in a SQL Server database.</span></span>  
  
 <span data-ttu-id="e4ed2-105">In den Beispielen in diesem Thema verwenden die Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="e4ed2-105">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="e4ed2-106">Wenn Sie die Beispieldatenbank Northwind auf dem Entwicklungscomputer nicht haben, können Sie herunterladen aus der [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Website.</span><span class="sxs-lookup"><span data-stu-id="e4ed2-106">If you do not have the Northwind sample database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web site.</span></span> <span data-ttu-id="e4ed2-107">Eine Anleitung hierzu finden Sie unter [Herunterladen von Beispieldatenbanken](https://msdn.microsoft.com/library/bb399411).</span><span class="sxs-lookup"><span data-stu-id="e4ed2-107">For instructions, see [Downloading Sample Databases](https://msdn.microsoft.com/library/bb399411).</span></span>  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="e4ed2-108">Um eine Verbindung mit einer Datenbank zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e4ed2-108">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="e4ed2-109">Öffnen Sie in Visual Studio **Server-Explorer**/**Datenbank-Explorer** durch Klicken auf die **Ansicht** , und wählen Sie dann **Server-Explorer**/**Datenbank-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="e4ed2-109">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking the **View** menu, and then select **Server Explorer**/**Database Explorer**.</span></span>  
  
2.  <span data-ttu-id="e4ed2-110">Mit der rechten Maustaste **Datenverbindungen** in **Server-Explorer**/**Datenbank-Explorer**, und klicken Sie auf **Verbindung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="e4ed2-110">Right-click **Data Connections** in **Server Explorer**/**Database Explorer**, and click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="e4ed2-111">Geben Sie eine gültige Verbindung mit der Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="e4ed2-111">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-with-a-linq-to-sql-file"></a><span data-ttu-id="e4ed2-112">Ein Projekt mit einer LINQ to SQL-Datei hinzufügen</span><span class="sxs-lookup"><span data-stu-id="e4ed2-112">To add a Project with a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="e4ed2-113">In Visual Studio auf die **Datei** auf **neu** , und klicken Sie dann auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="e4ed2-113">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="e4ed2-114">Wählen Sie Visual Basic **Windows Forms-Anwendung** als Projekttyp.</span><span class="sxs-lookup"><span data-stu-id="e4ed2-114">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="e4ed2-115">Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="e4ed2-115">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="e4ed2-116">Wählen Sie die **LINQ to SQL Classes** Elementvorlage.</span><span class="sxs-lookup"><span data-stu-id="e4ed2-116">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="e4ed2-117">Nennen Sie die Datei `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="e4ed2-117">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="e4ed2-118">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="e4ed2-118">Click **Add**.</span></span> <span data-ttu-id="e4ed2-119">Der Object Relational Designer (O/R-Designer) geöffnet ist, für die `northwind.dbml` Datei.</span><span class="sxs-lookup"><span data-stu-id="e4ed2-119">The Object Relational Designer (O/R Designer) is opened for the `northwind.dbml` file.</span></span>  
  
### <a name="to-add-tables-to-query-and-modify-to-the-designer"></a><span data-ttu-id="e4ed2-120">Hinzufügen von Tabellen zum Abfragen und ändern in den designer</span><span class="sxs-lookup"><span data-stu-id="e4ed2-120">To add tables to query and modify to the designer</span></span>  
  
1.  <span data-ttu-id="e4ed2-121">In **Server-Explorer**/**Datenbank-Explorer**, erweitern Sie die Verbindung zur Northwind-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="e4ed2-121">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="e4ed2-122">Erweitern Sie die **Tabellen** Ordner.</span><span class="sxs-lookup"><span data-stu-id="e4ed2-122">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="e4ed2-123">Wenn Sie den O/R-Designer geschlossen haben, können Sie es öffnen, durch Doppelklicken auf die `northwind.dbml` -Datei, die Sie zuvor hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="e4ed2-123">If you have closed the O/R Designer, you can reopen it by double-clicking the `northwind.dbml` file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="e4ed2-124">Klicken Sie auf die Tabelle Customers, und ziehen Sie es auf den linken Bereich des Designers.</span><span class="sxs-lookup"><span data-stu-id="e4ed2-124">Click the Customers table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="e4ed2-125">Der Designer erstellt ein neues benutzerdefiniertes Objekt für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="e4ed2-125">The designer creates a new Customer object for your project.</span></span>  
  
3.  <span data-ttu-id="e4ed2-126">Speichern Sie die Änderungen und schließen Sie den Designer.</span><span class="sxs-lookup"><span data-stu-id="e4ed2-126">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="e4ed2-127">Speichern Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="e4ed2-127">Save your project.</span></span>  
  
### <a name="to-add-code-to-modify-the-database-and-display-the-results"></a><span data-ttu-id="e4ed2-128">Fügen Sie Code zum Ändern der Datenbank und die Ergebnisse werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e4ed2-128">To add code to modify the database and display the results</span></span>  
  
1.  <span data-ttu-id="e4ed2-129">Aus der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.DataGridView>-Steuerelement auf das Standard-Windows Form für Ihr Projekt, Form1.</xref:System.Windows.Forms.DataGridView></span><span class="sxs-lookup"><span data-stu-id="e4ed2-129">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="e4ed2-130">Wenn Sie den O/R-Designer Tabellen hinzugefügt haben, wird der Designer hinzugefügt ein <xref:System.Data.Linq.DataContext>Objekt zu Ihrem Projekt.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="e4ed2-130">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="e4ed2-131">Dieses Objekt enthält Code, mit denen Sie Zugriff auf die Customers-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="e4ed2-131">This object contains code that you can use to access the Customers table.</span></span> <span data-ttu-id="e4ed2-132">Außerdem enthält Sie Code, der ein lokales Customer-Objekt und eine Customer-Auflistung für die Tabelle definiert.</span><span class="sxs-lookup"><span data-stu-id="e4ed2-132">It also contains code that defines  a local Customer object and a Customers collection for the table.</span></span> <span data-ttu-id="e4ed2-133">Das <xref:System.Data.Linq.DataContext>-Objekt für das Projekt mit dem Namen basierend auf den Namen der DBML-Datei.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="e4ed2-133">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="e4ed2-134">Für dieses Projekt die <xref:System.Data.Linq.DataContext>-Objekt mit dem Namen `northwindDataContext`.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="e4ed2-134">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="e4ed2-135">Erstellen Sie können eine Instanz von der <xref:System.Data.Linq.DataContext>Objekt in Ihrem Code und die Abfrage, und ändern Sie die vom O/R-Designer angegebene Customers-Auflistung.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="e4ed2-135">You can create an instance of the <xref:System.Data.Linq.DataContext> object in your code and query and modify the Customers collection specified by the O/R Designer.</span></span> <span data-ttu-id="e4ed2-136">Auf die Auflistung der Kunden vornehmen, werden nicht in der Datenbank wiedergegeben, bis durch Aufrufen Senden der <xref:System.Data.Linq.DataContext.SubmitChanges%2A>Methode der <xref:System.Data.Linq.DataContext>Objekt.</xref:System.Data.Linq.DataContext> </xref:System.Data.Linq.DataContext.SubmitChanges%2A></span><span class="sxs-lookup"><span data-stu-id="e4ed2-136">Changes that you make to the Customers collection are not reflected in the database until you submit them by calling the <xref:System.Data.Linq.DataContext.SubmitChanges%2A> method of the <xref:System.Data.Linq.DataContext> object.</span></span>  
  
     <span data-ttu-id="e4ed2-137">Doppelklicken Sie auf das Windows Form, Form1, um Code hinzufügen, auf das <xref:System.Windows.Forms.Form.Load>Ereignis, um die Customers-Tabelle abgefragt, die als eine Eigenschaft von Ihrem <xref:System.Data.Linq.DataContext>.</xref:System.Data.Linq.DataContext> bereitgestellt wird</xref:System.Windows.Forms.Form.Load></span><span class="sxs-lookup"><span data-stu-id="e4ed2-137">Double-click the Windows Form, Form1, to add code to the <xref:System.Windows.Forms.Form.Load> event to query the Customers table that is exposed as a property of your <xref:System.Data.Linq.DataContext>.</span></span> <span data-ttu-id="e4ed2-138">Fügen Sie den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="e4ed2-138">Add the following code:</span></span>  
  
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
  
3.  <span data-ttu-id="e4ed2-139">Aus der **Toolbox**, ziehen Sie drei <xref:System.Windows.Forms.Button>-Steuerelemente auf das Formular.</xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="e4ed2-139">From the **Toolbox**, drag three <xref:System.Windows.Forms.Button> controls onto the form.</span></span> <span data-ttu-id="e4ed2-140">Wählen Sie das erste `Button` Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="e4ed2-140">Select the first `Button` control.</span></span> <span data-ttu-id="e4ed2-141">In der **Eigenschaften** legen die `Name` von der `Button` die Steuerung an `AddButton` und `Text` auf `Add`.</span><span class="sxs-lookup"><span data-stu-id="e4ed2-141">In the **Properties** window, set the `Name` of the `Button` control to `AddButton` and the `Text` to `Add`.</span></span> <span data-ttu-id="e4ed2-142">Wählen Sie die zweite Schaltfläche, und legen die `Name` -Eigenschaft `UpdateButton` und `Text` -Eigenschaft `Update`.</span><span class="sxs-lookup"><span data-stu-id="e4ed2-142">Select the second button and set the `Name` property to `UpdateButton` and the `Text` property to `Update`.</span></span> <span data-ttu-id="e4ed2-143">Wählen Sie die dritte Schaltfläche aus, und legen Sie die `Name` -Eigenschaft `DeleteButton` und `Text` -Eigenschaft `Delete`.</span><span class="sxs-lookup"><span data-stu-id="e4ed2-143">Select the third button and set the `Name` property to `DeleteButton` and the `Text` property to `Delete`.</span></span>  
  
4.  <span data-ttu-id="e4ed2-144">Doppelklicken Sie auf die **hinzufügen** Schaltfläche zum Hinzufügen von Code auf seine `Click` Ereignis.</span><span class="sxs-lookup"><span data-stu-id="e4ed2-144">Double-click the **Add** button to add code to its `Click` event.</span></span> <span data-ttu-id="e4ed2-145">Fügen Sie den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="e4ed2-145">Add the following code:</span></span>  
  
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
  
5.  <span data-ttu-id="e4ed2-146">Doppelklicken Sie auf die **Update** Schaltfläche zum Hinzufügen von Code auf seine `Click` Ereignis.</span><span class="sxs-lookup"><span data-stu-id="e4ed2-146">Double-click the **Update** button to add code to its `Click` event.</span></span> <span data-ttu-id="e4ed2-147">Fügen Sie den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="e4ed2-147">Add the following code:</span></span>  
  
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
  
6.  <span data-ttu-id="e4ed2-148">Doppelklicken Sie auf die **löschen** Schaltfläche zum Hinzufügen von Code auf seine `Click` Ereignis.</span><span class="sxs-lookup"><span data-stu-id="e4ed2-148">Double-click the **Delete** button to add code to its `Click` event.</span></span> <span data-ttu-id="e4ed2-149">Fügen Sie den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="e4ed2-149">Add the following code:</span></span>  
  
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
  
7.  <span data-ttu-id="e4ed2-150">Drücken Sie F5, um das Projekt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e4ed2-150">Press F5 to run your project.</span></span> <span data-ttu-id="e4ed2-151">Klicken Sie auf **hinzufügen** um einen neuen Datensatz hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e4ed2-151">Click **Add** to add a new record.</span></span> <span data-ttu-id="e4ed2-152">Klicken Sie auf **Update** um den neuen Datensatz zu ändern.</span><span class="sxs-lookup"><span data-stu-id="e4ed2-152">Click **Update** to modify the new record.</span></span> <span data-ttu-id="e4ed2-153">Klicken Sie auf **löschen** um den neuen Datensatz zu löschen.</span><span class="sxs-lookup"><span data-stu-id="e4ed2-153">Click **Delete** to delete the new record.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4ed2-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e4ed2-154">See Also</span></span>  
 <span data-ttu-id="e4ed2-155">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="e4ed2-155">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="e4ed2-156"> [Abfragen](../../../../visual-basic/language-reference/queries/queries.md) </span><span class="sxs-lookup"><span data-stu-id="e4ed2-156"> [Queries](../../../../visual-basic/language-reference/queries/queries.md) </span></span>  
<span data-ttu-id="e4ed2-157"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span><span class="sxs-lookup"><span data-stu-id="e4ed2-157"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span></span>  
<span data-ttu-id="e4ed2-158"> [DataContext-Methoden (O/R-Designer)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer) </span><span class="sxs-lookup"><span data-stu-id="e4ed2-158"> [DataContext Methods (O/R Designer)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer) </span></span>  
<span data-ttu-id="e4ed2-159"> [Gewusst wie: Zuweisen von gespeicherten Prozeduren zum Aktualisieren, einfügen und löschen (O/R-Designer) ausführen.](http://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)</span><span class="sxs-lookup"><span data-stu-id="e4ed2-159"> [How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)](http://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)</span></span>
