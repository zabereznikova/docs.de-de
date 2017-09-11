---
title: "Gewusst wie: zurückgeben ein LINQ-Abfrageergebnisses als bestimmter Typ (Visual Basic) | Microsoft-Dokumentation"
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
- queries [LINQ in Visual Basic], specific type returned
- projection [LINQ in Visual Basic]
- anonymous types [Visual Basic]
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: 621bb10a-e5d7-44fb-a025-317964b19d92
caps.latest.revision: 8
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
ms.openlocfilehash: ecbc691a0afeb7ba631949684a0457d9bcdb2728
ms.contentlocale: de-de
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-return-a-linq-query-result-as-a-specific-type-visual-basic"></a><span data-ttu-id="89d89-102">Gewusst wie: Zurückgeben eines LINQ-Abfrageergebnisses als ein bestimmter Typ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="89d89-102">How to: Return a LINQ Query Result as a Specific Type (Visual Basic)</span></span>
<span data-ttu-id="89d89-103">Language-Integrated Query (LINQ) erleichtert den Zugriff auf Datenbankinformationen und Abfragen ausführen.</span><span class="sxs-lookup"><span data-stu-id="89d89-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span> <span data-ttu-id="89d89-104">In der Standardeinstellung zurück LINQ-Abfragen eine Liste von Objekten als anonymer Typ.</span><span class="sxs-lookup"><span data-stu-id="89d89-104">By default, LINQ queries return a list of objects as an anonymous type.</span></span> <span data-ttu-id="89d89-105">Sie können auch angeben, dass eine Abfrage eine Liste eines bestimmten Typs mithilfe der `Select` Klausel.</span><span class="sxs-lookup"><span data-stu-id="89d89-105">You can also specify that a query return a list of a specific type by using the `Select` clause.</span></span>  
  
 <span data-ttu-id="89d89-106">Im folgenden Beispiel wird veranschaulicht, wie eine neue Anwendung erstellen, die eine SQL Server-Datenbank abfragt und die Ergebnisse als einen bestimmten benannten Typ.</span><span class="sxs-lookup"><span data-stu-id="89d89-106">The following example shows how to create a new application that performs queries against a SQL Server database and projects the results as a specific named type.</span></span> <span data-ttu-id="89d89-107">Weitere Informationen finden Sie unter [anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) und [Select-Klausel](../../../../visual-basic/language-reference/queries/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="89d89-107">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) and [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md).</span></span>  
  
 <span data-ttu-id="89d89-108">In den Beispielen in diesem Thema verwenden die Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="89d89-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="89d89-109">Wenn Sie die Beispieldatenbank Northwind auf dem Entwicklungscomputer nicht haben, können Sie herunterladen aus der [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Website.</span><span class="sxs-lookup"><span data-stu-id="89d89-109">If you do not have the Northwind sample database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web site.</span></span> <span data-ttu-id="89d89-110">Eine Anleitung hierzu finden Sie unter [Herunterladen von Beispieldatenbanken](https://msdn.microsoft.com/library/bb399411).</span><span class="sxs-lookup"><span data-stu-id="89d89-110">For instructions, see [Downloading Sample Databases](https://msdn.microsoft.com/library/bb399411).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="89d89-111">Um eine Verbindung mit einer Datenbank zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="89d89-111">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="89d89-112">Öffnen Sie in Visual Studio **Server-Explorer**/**Datenbank-Explorer** durch Klicken auf **Server-Explorer**/**Datenbank-Explorer** auf der **Ansicht** Menü.</span><span class="sxs-lookup"><span data-stu-id="89d89-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="89d89-113">Mit der rechten Maustaste **Datenverbindungen** in **Server-Explorer**/**Datenbank-Explorer** , und klicken Sie dann auf **Verbindung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="89d89-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="89d89-114">Geben Sie eine gültige Verbindung mit der Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="89d89-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="89d89-115">Ein Projekt hinzufügen, die eine LINQ to SQL-Datei enthält.</span><span class="sxs-lookup"><span data-stu-id="89d89-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="89d89-116">In Visual Studio auf die **Datei** auf **neu** , und klicken Sie dann auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="89d89-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="89d89-117">Wählen Sie Visual Basic **Windows Forms-Anwendung** als Projekttyp.</span><span class="sxs-lookup"><span data-stu-id="89d89-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="89d89-118">Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="89d89-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="89d89-119">Wählen Sie die **LINQ to SQL Classes** Elementvorlage.</span><span class="sxs-lookup"><span data-stu-id="89d89-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="89d89-120">Nennen Sie die Datei `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="89d89-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="89d89-121">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="89d89-121">Click **Add**.</span></span> <span data-ttu-id="89d89-122">Der Object Relational Designer (O/R-Designer) wird für die Datei northwind.dbml geöffnet.</span><span class="sxs-lookup"><span data-stu-id="89d89-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="89d89-123">Zum Hinzufügen von Tabellen in den O/R-Designer Abfragen</span><span class="sxs-lookup"><span data-stu-id="89d89-123">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="89d89-124">In **Server-Explorer**/**Datenbank-Explorer**, erweitern Sie die Verbindung zur Northwind-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="89d89-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="89d89-125">Erweitern Sie die **Tabellen** Ordner.</span><span class="sxs-lookup"><span data-stu-id="89d89-125">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="89d89-126">Wenn Sie den O/R-Designer geschlossen haben, können Sie es durch Doppelklicken auf die Sie zuvor hinzugefügte Datei northwind.dbml erneut öffnen.</span><span class="sxs-lookup"><span data-stu-id="89d89-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="89d89-127">Klicken Sie auf die Tabelle Customers, und ziehen Sie es auf den linken Bereich des Designers.</span><span class="sxs-lookup"><span data-stu-id="89d89-127">Click the Customers table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="89d89-128">Der Designer erstellt ein neues `Customer` -Objekt für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="89d89-128">The designer creates a new `Customer` object for your project.</span></span> <span data-ttu-id="89d89-129">Sie können ein Abfrageergebnis als projizieren der `Customer` Typ oder als einen Typ, den Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="89d89-129">You can project a query result as the `Customer` type or as a type that you create.</span></span> <span data-ttu-id="89d89-130">In diesem Beispiel wird einen neuen Typ in einem späteren Verfahren und erstellen ein Abfrageergebnisses als diesen Typ.</span><span class="sxs-lookup"><span data-stu-id="89d89-130">This sample will create a new type in a later procedure and project a query result as that type.</span></span>  
  
3.  <span data-ttu-id="89d89-131">Speichern Sie die Änderungen und schließen Sie den Designer.</span><span class="sxs-lookup"><span data-stu-id="89d89-131">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="89d89-132">Speichern Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="89d89-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="89d89-133">Hinzufügen von Code, um die Datenbank abzufragen und die Ergebnisse werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="89d89-133">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="89d89-134">Aus der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.DataGridView>-Steuerelement auf das Standard-Windows Form für Ihr Projekt, Form1.</xref:System.Windows.Forms.DataGridView></span><span class="sxs-lookup"><span data-stu-id="89d89-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="89d89-135">Doppelklicken Sie auf Form1, um die Form1-Klasse ändern.</span><span class="sxs-lookup"><span data-stu-id="89d89-135">Double-click Form1 to modify the Form1 class.</span></span>  
  
3.  <span data-ttu-id="89d89-136">Nach der `End Class` -Anweisung der Form1-Klasse, fügen Sie folgenden Code zum Erstellen einer `CustomerInfo` Typ, der die Abfrageergebnisse für dieses Beispiel enthält.</span><span class="sxs-lookup"><span data-stu-id="89d89-136">After the `End Class` statement of the Form1 class, add the following code to create a `CustomerInfo` type to hold the query results for this sample.</span></span>  
  
     <span data-ttu-id="89d89-137">[!code-vb[VbLINQToSQLHowTos Nr.&16;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-return-a-linq-query-result-as-a-specific-type_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="89d89-137">[!code-vb[VbLINQToSQLHowTos#16](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-return-a-linq-query-result-as-a-specific-type_1.vb)]</span></span>  
  
4.  <span data-ttu-id="89d89-138">Wenn Sie den O/R-Designer Tabellen hinzugefügt haben, wird der Designer hinzugefügt ein <xref:System.Data.Linq.DataContext>Objekt zu Ihrem Projekt.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="89d89-138">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="89d89-139">Dieses Objekt enthält den Code, den auf diese Tabellen zugreifen und den Zugriff auf einzelne Objekte und Sammlungen für jede Tabelle erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="89d89-139">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="89d89-140">Das <xref:System.Data.Linq.DataContext>-Objekt für das Projekt mit dem Namen basierend auf den Namen der DBML-Datei.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="89d89-140">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="89d89-141">Für dieses Projekt die <xref:System.Data.Linq.DataContext>-Objekt mit dem Namen `northwindDataContext`.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="89d89-141">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="89d89-142">Erstellen Sie können eine Instanz von der <xref:System.Data.Linq.DataContext>in Ihrem Code und die Abfrage der Tabellen, die vom O/R-Designer angegeben.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="89d89-142">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="89d89-143">In der `Load` -Ereignis der Klasse Form1, fügen Sie folgenden Code zum Abfragen von Tabellen, die als Eigenschaften des Datenkontexts verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="89d89-143">In the `Load` event of the Form1 class, add the following code to query the tables that are exposed as properties of your data context.</span></span> <span data-ttu-id="89d89-144">Die `Select` -Klausel der Abfrage erstellt eine neue `CustomerInfo` Typ statt eines anonymen Typs für jedes Element des Abfrageergebnisses.</span><span class="sxs-lookup"><span data-stu-id="89d89-144">The `Select` clause of the query will create a new `CustomerInfo` type instead of an anonymous type for each item of the query result.</span></span>  
  
     <span data-ttu-id="89d89-145">[!code-vb[VbLINQToSQLHowTos&#15;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-return-a-linq-query-result-as-a-specific-type_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="89d89-145">[!code-vb[VbLINQToSQLHowTos#15](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-return-a-linq-query-result-as-a-specific-type_2.vb)]</span></span>  
  
5.  <span data-ttu-id="89d89-146">Drücken Sie F5, um das Projekt auszuführen und die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="89d89-146">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89d89-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89d89-147">See Also</span></span>  
 <span data-ttu-id="89d89-148">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="89d89-148">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="89d89-149"> [Abfragen](../../../../visual-basic/language-reference/queries/queries.md) </span><span class="sxs-lookup"><span data-stu-id="89d89-149"> [Queries](../../../../visual-basic/language-reference/queries/queries.md) </span></span>  
<span data-ttu-id="89d89-150"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span><span class="sxs-lookup"><span data-stu-id="89d89-150"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span></span>  
<span data-ttu-id="89d89-151"> [DataContext-Methoden (O/R-Designer)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)</span><span class="sxs-lookup"><span data-stu-id="89d89-151"> [DataContext Methods (O/R Designer)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)</span></span>

