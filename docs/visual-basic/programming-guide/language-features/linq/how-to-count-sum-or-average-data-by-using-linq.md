---
title: 'Gewusst wie: bestimmen, Summen oder Durchschnittswerten von Daten mithilfe von LINQ (Visual Basic) | Microsoft-Dokumentation'
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
- average operator [LINQ in Visual Basic]
- aggregate operator [LINQ in Visual Basic]
- aggregate queries
- queries [LINQ in Visual Basic], sum results
- Aggregate clause
- sum operator [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], aggregate queries
- queries [LINQ in Visual Basic], counting results
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
- count operator [LINQ in Visual Basic]
ms.assetid: 51ca1f59-7770-4884-8b76-113002e54fc0
caps.latest.revision: 9
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
ms.openlocfilehash: 63ea6cd9eb2942ac80688cec6ea44e89c2a2b7f7
ms.contentlocale: de-de
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-count-sum-or-average-data-by-using-linq-visual-basic"></a><span data-ttu-id="5ea86-102">Gewusst wie: Bestimmen von Zahlen, Summen oder Durchschnittswerten von Daten mithilfe von LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5ea86-102">How to: Count, Sum, or Average Data by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="5ea86-103">Language-Integrated Query (LINQ) erleichtert den Zugriff auf Datenbankinformationen und Abfragen ausführen.</span><span class="sxs-lookup"><span data-stu-id="5ea86-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="5ea86-104">Im folgenden Beispiel wird veranschaulicht, wie eine neue Anwendung erstellen, die Abfragen in einer SQL Server-Datenbank ausführt.</span><span class="sxs-lookup"><span data-stu-id="5ea86-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span> <span data-ttu-id="5ea86-105">Das Beispiel zählt, Summen und Durchschnittswerte der Ergebnisse mithilfe der `Aggregate` und `Group By` Klauseln.</span><span class="sxs-lookup"><span data-stu-id="5ea86-105">The sample counts, sums, and averages the results by using the `Aggregate` and `Group By` clauses.</span></span> <span data-ttu-id="5ea86-106">Weitere Informationen finden Sie unter [Aggregate-Klausel](../../../../visual-basic/language-reference/queries/aggregate-clause.md) und [Group By-Klausel](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="5ea86-106">For more information, see [Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) and [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
 <span data-ttu-id="5ea86-107">In den Beispielen in diesem Thema verwenden die Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="5ea86-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="5ea86-108">Wenn Sie die Beispieldatenbank Northwind auf dem Entwicklungscomputer nicht haben, können Sie herunterladen aus der [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Website.</span><span class="sxs-lookup"><span data-stu-id="5ea86-108">If you do not have the Northwind sample database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web site.</span></span> <span data-ttu-id="5ea86-109">Eine Anleitung hierzu finden Sie unter [Herunterladen von Beispieldatenbanken](https://msdn.microsoft.com/library/bb399411).</span><span class="sxs-lookup"><span data-stu-id="5ea86-109">For instructions, see [Downloading Sample Databases](https://msdn.microsoft.com/library/bb399411).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="5ea86-110">Um eine Verbindung mit einer Datenbank zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5ea86-110">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="5ea86-111">Öffnen Sie in Visual Studio **Server-Explorer**/**Datenbank-Explorer** durch Klicken auf **Server-Explorer**/**Datenbank-Explorer** auf der **Ansicht** Menü.</span><span class="sxs-lookup"><span data-stu-id="5ea86-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="5ea86-112">Mit der rechten Maustaste **Datenverbindungen** in **Server-Explorer**/**Datenbank-Explorer** , und klicken Sie dann auf **Verbindung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="5ea86-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="5ea86-113">Geben Sie eine gültige Verbindung mit der Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="5ea86-113">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="5ea86-114">Ein Projekt hinzufügen, die eine LINQ to SQL-Datei enthält.</span><span class="sxs-lookup"><span data-stu-id="5ea86-114">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="5ea86-115">In Visual Studio auf die **Datei** auf **neu** , und klicken Sie dann auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="5ea86-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="5ea86-116">Wählen Sie Visual Basic **Windows Forms-Anwendung** als Projekttyp.</span><span class="sxs-lookup"><span data-stu-id="5ea86-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="5ea86-117">Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="5ea86-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="5ea86-118">Wählen Sie die **LINQ to SQL Classes** Elementvorlage.</span><span class="sxs-lookup"><span data-stu-id="5ea86-118">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="5ea86-119">Nennen Sie die Datei `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="5ea86-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="5ea86-120">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="5ea86-120">Click **Add**.</span></span> <span data-ttu-id="5ea86-121">Der Object Relational Designer (O/R-Designer) wird für die Datei northwind.dbml geöffnet.</span><span class="sxs-lookup"><span data-stu-id="5ea86-121">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="5ea86-122">Zum Hinzufügen von Tabellen in den O/R-Designer Abfragen</span><span class="sxs-lookup"><span data-stu-id="5ea86-122">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="5ea86-123">In **Server-Explorer**/**Datenbank-Explorer**, erweitern Sie die Verbindung zur Northwind-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="5ea86-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="5ea86-124">Erweitern Sie die **Tabellen** Ordner.</span><span class="sxs-lookup"><span data-stu-id="5ea86-124">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="5ea86-125">Wenn Sie den O/R-Designer geschlossen haben, können Sie es durch Doppelklicken auf die Sie zuvor hinzugefügte Datei northwind.dbml erneut öffnen.</span><span class="sxs-lookup"><span data-stu-id="5ea86-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="5ea86-126">Klicken Sie auf die Tabelle Customers, und ziehen Sie es auf den linken Bereich des Designers.</span><span class="sxs-lookup"><span data-stu-id="5ea86-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="5ea86-127">Klicken Sie auf die Tabelle Orders, und ziehen Sie es auf den linken Bereich des Designers.</span><span class="sxs-lookup"><span data-stu-id="5ea86-127">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="5ea86-128">Der Designer erstellt neue `Customer` und `Order` -Objekte für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="5ea86-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="5ea86-129">Beachten Sie, dass der Designer Beziehungen zwischen den Tabellen erkennt automatisch und untergeordnete Eigenschaften für verknüpfte Objekte erstellt.</span><span class="sxs-lookup"><span data-stu-id="5ea86-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="5ea86-130">Z. B. IntelliSense wird angezeigt, die `Customer` Objekt verfügt über eine `Orders` -Eigenschaft für alle Aufträge im Zusammenhang mit diesen Kunden.</span><span class="sxs-lookup"><span data-stu-id="5ea86-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3.  <span data-ttu-id="5ea86-131">Speichern Sie die Änderungen und schließen Sie den Designer.</span><span class="sxs-lookup"><span data-stu-id="5ea86-131">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="5ea86-132">Speichern Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="5ea86-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="5ea86-133">Hinzufügen von Code, um die Datenbank abzufragen und die Ergebnisse werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5ea86-133">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="5ea86-134">Aus der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.DataGridView>-Steuerelement auf das Standard-Windows Form für Ihr Projekt, Form1.</xref:System.Windows.Forms.DataGridView></span><span class="sxs-lookup"><span data-stu-id="5ea86-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="5ea86-135">Doppelklicken Sie auf Form1, um Code zum Hinzufügen der `Load` -Ereignis des Formulars.</span><span class="sxs-lookup"><span data-stu-id="5ea86-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3.  <span data-ttu-id="5ea86-136">Wenn Sie den O/R-Designer Tabellen hinzugefügt haben, wird der Designer hinzugefügt ein <xref:System.Data.Linq.DataContext>-Objekt für das Projekt.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="5ea86-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="5ea86-137">Dieses Objekt enthält den Code, den auf diese Tabellen zugreifen und den Zugriff auf einzelne Objekte und Sammlungen für jede Tabelle erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="5ea86-137">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="5ea86-138">Das <xref:System.Data.Linq.DataContext>-Objekt für das Projekt mit dem Namen basierend auf den Namen der DBML-Datei.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="5ea86-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="5ea86-139">Für dieses Projekt die <xref:System.Data.Linq.DataContext>-Objekt mit dem Namen `northwindDataContext`.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="5ea86-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="5ea86-140">Erstellen Sie können eine Instanz von der <xref:System.Data.Linq.DataContext>in Ihrem Code und die Abfrage der Tabellen, die vom O/R-Designer angegeben.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="5ea86-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="5ea86-141">Fügen Sie den folgenden Code der `Load` Ereignis, um die Tabellen zu Abfragen, die als Eigenschaften verfügbar gemacht werden Ihre <xref:System.Data.Linq.DataContext>und Anzahl, Summe und Durchschnitt der Ergebnisse.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="5ea86-141">Add the following code to the `Load` event to query the tables that are exposed as properties of your <xref:System.Data.Linq.DataContext> and count, sum, and average the results.</span></span> <span data-ttu-id="5ea86-142">Das Beispiel verwendet die `Aggregate` -Klausel, um die Abfrage für ein einzelnes Ergebnis und die `Group By` -Klausel, um die Anzeige des Durchschnitts für gruppierte Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="5ea86-142">The sample uses the `Aggregate` clause to query for a single result, and the `Group By` clause to show an average for grouped results.</span></span>  
  
     <span data-ttu-id="5ea86-143">[!code-vb[VbLINQToSQLHowTos&#13;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-count-sum-or-average-data-by-using-linq_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="5ea86-143">[!code-vb[VbLINQToSQLHowTos#13](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-count-sum-or-average-data-by-using-linq_1.vb)]</span></span>  
  
4.  <span data-ttu-id="5ea86-144">Drücken Sie F5, um das Projekt auszuführen und die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5ea86-144">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ea86-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5ea86-145">See Also</span></span>  
 <span data-ttu-id="5ea86-146">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="5ea86-146">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="5ea86-147"> [Abfragen](../../../../visual-basic/language-reference/queries/queries.md) </span><span class="sxs-lookup"><span data-stu-id="5ea86-147"> [Queries](../../../../visual-basic/language-reference/queries/queries.md) </span></span>  
<span data-ttu-id="5ea86-148"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span><span class="sxs-lookup"><span data-stu-id="5ea86-148"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span></span>  
<span data-ttu-id="5ea86-149"> [DataContext-Methoden (O/R-Designer)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)</span><span class="sxs-lookup"><span data-stu-id="5ea86-149"> [DataContext Methods (O/R Designer)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)</span></span>  
<span data-ttu-id="5ea86-150"> [Aggregate-Klausel](../../../../visual-basic/language-reference/queries/aggregate-clause.md) </span><span class="sxs-lookup"><span data-stu-id="5ea86-150"> [Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) </span></span>  
<span data-ttu-id="5ea86-151"> [Group By-Klausel](../../../../visual-basic/language-reference/queries/group-by-clause.md)</span><span class="sxs-lookup"><span data-stu-id="5ea86-151"> [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md)</span></span>

