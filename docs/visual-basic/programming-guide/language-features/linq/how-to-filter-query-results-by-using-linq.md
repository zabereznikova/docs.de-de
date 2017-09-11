---
title: 'Gewusst wie: Filtern von Abfrageergebnissen unter Verwendung von LINQ (Visual Basic) | Microsoft-Dokumentation'
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
- filtering [Visual Basic]
- filtering data [LINQ in Visual Basic]
- filtering [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], filtering results
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
- filtering data [Visual Basic]
ms.assetid: ef103092-9bed-4134-97f4-2db696e83c12
caps.latest.revision: 6
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
ms.openlocfilehash: d6197e39ffef5b09b87b1b47cab04d4339bcaf3f
ms.contentlocale: de-de
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-filter-query-results-by-using-linq-visual-basic"></a><span data-ttu-id="a5dbc-102">Gewusst wie: Filtern von Abfrageergebnissen unter Verwendung von LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a5dbc-102">How to: Filter Query Results by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="a5dbc-103">Language-Integrated Query (LINQ) erleichtert den Zugriff auf Datenbankinformationen und Abfragen ausführen.</span><span class="sxs-lookup"><span data-stu-id="a5dbc-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="a5dbc-104">Im folgenden Beispiel wird veranschaulicht, wie eine neue Anwendung erstellen, die eine SQL Server-Datenbank abfragt und filtert die Ergebnisse nach einem bestimmten Wert mithilfe der `Where` Klausel.</span><span class="sxs-lookup"><span data-stu-id="a5dbc-104">The following example shows how to create a new application that performs queries against a SQL Server database and filters the results by a particular value by using the `Where` clause.</span></span> <span data-ttu-id="a5dbc-105">Weitere Informationen finden Sie unter [Where-Klausel](../../../../visual-basic/language-reference/queries/where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="a5dbc-105">For more information, see [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).</span></span>  
  
 <span data-ttu-id="a5dbc-106">In den Beispielen in diesem Thema verwenden die Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="a5dbc-106">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="a5dbc-107">Wenn Sie die Beispieldatenbank Northwind auf dem Entwicklungscomputer nicht haben, können Sie herunterladen aus der [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Website.</span><span class="sxs-lookup"><span data-stu-id="a5dbc-107">If you do not have the Northwind sample database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web site.</span></span> <span data-ttu-id="a5dbc-108">Eine Anleitung hierzu finden Sie unter [Herunterladen von Beispieldatenbanken](https://msdn.microsoft.com/library/bb399411).</span><span class="sxs-lookup"><span data-stu-id="a5dbc-108">For instructions, see [Downloading Sample Databases](https://msdn.microsoft.com/library/bb399411).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="a5dbc-109">Um eine Verbindung mit einer Datenbank zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a5dbc-109">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="a5dbc-110">Öffnen Sie in Visual Studio **Server-Explorer**/**Datenbank-Explorer** durch Klicken auf **Server-Explorer**/**Datenbank-Explorer** auf der **Ansicht** Menü.</span><span class="sxs-lookup"><span data-stu-id="a5dbc-110">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="a5dbc-111">Mit der rechten Maustaste **Datenverbindungen** in **Server-Explorer**/**Datenbank-Explorer** , und klicken Sie dann auf **Verbindung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a5dbc-111">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="a5dbc-112">Geben Sie eine gültige Verbindung mit der Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="a5dbc-112">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="a5dbc-113">Ein Projekt hinzufügen, die eine LINQ to SQL-Datei enthält.</span><span class="sxs-lookup"><span data-stu-id="a5dbc-113">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="a5dbc-114">In Visual Studio auf die **Datei** auf **neu** , und klicken Sie dann auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="a5dbc-114">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="a5dbc-115">Wählen Sie Visual Basic **Windows Forms-Anwendung** als Projekttyp.</span><span class="sxs-lookup"><span data-stu-id="a5dbc-115">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="a5dbc-116">Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a5dbc-116">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="a5dbc-117">Wählen Sie die **LINQ to SQL Classes** Elementvorlage.</span><span class="sxs-lookup"><span data-stu-id="a5dbc-117">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="a5dbc-118">Nennen Sie die Datei `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="a5dbc-118">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="a5dbc-119">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a5dbc-119">Click **Add**.</span></span> <span data-ttu-id="a5dbc-120">Der Object Relational Designer (O/R-Designer) wird für die Datei northwind.dbml geöffnet.</span><span class="sxs-lookup"><span data-stu-id="a5dbc-120">The Object Relational Designer (O/R Designer) opens for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="a5dbc-121">Zum Hinzufügen von Tabellen in den O/R-Designer Abfragen</span><span class="sxs-lookup"><span data-stu-id="a5dbc-121">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="a5dbc-122">In **Server-Explorer**/**Datenbank-Explorer**, erweitern Sie die Verbindung zur Northwind-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="a5dbc-122">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="a5dbc-123">Erweitern Sie die **Tabellen** Ordner.</span><span class="sxs-lookup"><span data-stu-id="a5dbc-123">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="a5dbc-124">Wenn Sie den O/R-Designer geschlossen haben, können Sie es durch Doppelklicken auf die Sie zuvor hinzugefügte Datei northwind.dbml erneut öffnen.</span><span class="sxs-lookup"><span data-stu-id="a5dbc-124">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="a5dbc-125">Klicken Sie auf die Tabelle Customers, und ziehen Sie es auf den linken Bereich des Designers.</span><span class="sxs-lookup"><span data-stu-id="a5dbc-125">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="a5dbc-126">Klicken Sie auf die Tabelle Orders, und ziehen Sie es auf den linken Bereich des Designers.</span><span class="sxs-lookup"><span data-stu-id="a5dbc-126">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="a5dbc-127">Der Designer erstellt neue `Customer` und `Order` -Objekte für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="a5dbc-127">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="a5dbc-128">Beachten Sie, dass der Designer Beziehungen zwischen den Tabellen erkennt automatisch und untergeordnete Eigenschaften für verknüpfte Objekte erstellt.</span><span class="sxs-lookup"><span data-stu-id="a5dbc-128">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="a5dbc-129">Z. B. IntelliSense wird angezeigt, die `Customer` Objekt verfügt über eine `Orders` -Eigenschaft für alle Aufträge im Zusammenhang mit diesen Kunden.</span><span class="sxs-lookup"><span data-stu-id="a5dbc-129">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3.  <span data-ttu-id="a5dbc-130">Speichern Sie die Änderungen und schließen Sie den Designer.</span><span class="sxs-lookup"><span data-stu-id="a5dbc-130">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="a5dbc-131">Speichern Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="a5dbc-131">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="a5dbc-132">Hinzufügen von Code, um die Datenbank abzufragen und die Ergebnisse werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a5dbc-132">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="a5dbc-133">Aus der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.DataGridView>-Steuerelement auf das Standard-Windows Form für Ihr Projekt, Form1.</xref:System.Windows.Forms.DataGridView></span><span class="sxs-lookup"><span data-stu-id="a5dbc-133">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="a5dbc-134">Doppelklicken Sie auf Form1, um Code zum Hinzufügen der `Load` -Ereignis des Formulars.</span><span class="sxs-lookup"><span data-stu-id="a5dbc-134">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3.  <span data-ttu-id="a5dbc-135">Wenn Sie den O/R-Designer Tabellen hinzugefügt haben, wird der Designer hinzugefügt ein <xref:System.Data.Linq.DataContext>-Objekt für das Projekt.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="a5dbc-135">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="a5dbc-136">Dieses Objekt enthält den Code, den zum Zugriff auf die Tabellen, neben der einzelnen Objekte und Sammlungen für jede Tabelle.</span><span class="sxs-lookup"><span data-stu-id="a5dbc-136">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="a5dbc-137">Das <xref:System.Data.Linq.DataContext>-Objekt für das Projekt mit dem Namen basierend auf den Namen der DBML-Datei.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="a5dbc-137">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="a5dbc-138">Für dieses Projekt die <xref:System.Data.Linq.DataContext>-Objekt mit dem Namen `northwindDataContext`.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="a5dbc-138">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="a5dbc-139">Erstellen Sie können eine Instanz von der <xref:System.Data.Linq.DataContext>in Ihrem Code und die Abfrage der Tabellen, die vom O/R-Designer angegeben.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="a5dbc-139">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="a5dbc-140">Fügen Sie den folgenden Code der `Load` Ereignis, um die Tabellen zu Abfragen, die als Eigenschaften des Datenkontexts verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="a5dbc-140">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context.</span></span> <span data-ttu-id="a5dbc-141">Die Abfrage filtert die Ergebnisse und gibt nur die Kunden, die in gespeichert sind `London`.</span><span class="sxs-lookup"><span data-stu-id="a5dbc-141">The query filters the results and returns only customers that are located in `London`.</span></span>  
  
     <span data-ttu-id="a5dbc-142">[!code-vb[VbLINQToSQLHowTos&#11;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-filter-query-results-by-using-linq_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="a5dbc-142">[!code-vb[VbLINQToSQLHowTos#11](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-filter-query-results-by-using-linq_1.vb)]</span></span>  
  
4.  <span data-ttu-id="a5dbc-143">Drücken Sie F5, um das Projekt auszuführen und die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a5dbc-143">Press F5 to run your project and view the results.</span></span>  
  
5.  <span data-ttu-id="a5dbc-144">Im folgenden werden einige weitere Filter, die Sie ausprobieren können.</span><span class="sxs-lookup"><span data-stu-id="a5dbc-144">Following are some other filters that you can try.</span></span>  
  
     <span data-ttu-id="a5dbc-145">[!code-vb[VbLINQToSQLHowTos&#12;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-filter-query-results-by-using-linq_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="a5dbc-145">[!code-vb[VbLINQToSQLHowTos#12](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-filter-query-results-by-using-linq_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5dbc-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a5dbc-146">See Also</span></span>  
 <span data-ttu-id="a5dbc-147">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="a5dbc-147">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="a5dbc-148"> [Abfragen](../../../../visual-basic/language-reference/queries/queries.md) </span><span class="sxs-lookup"><span data-stu-id="a5dbc-148"> [Queries](../../../../visual-basic/language-reference/queries/queries.md) </span></span>  
<span data-ttu-id="a5dbc-149"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span><span class="sxs-lookup"><span data-stu-id="a5dbc-149"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span></span>  
<span data-ttu-id="a5dbc-150"> [DataContext-Methoden (O/R-Designer)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)</span><span class="sxs-lookup"><span data-stu-id="a5dbc-150"> [DataContext Methods (O/R Designer)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)</span></span>

