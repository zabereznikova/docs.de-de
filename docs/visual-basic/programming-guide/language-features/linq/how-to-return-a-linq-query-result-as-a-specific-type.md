---
title: 'Vorgehensweise: Zurückgeben eines LINQ-Abfrageergebnisses als bestimmter Typ'
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], specific type returned
- projection [LINQ in Visual Basic]
- anonymous types [Visual Basic]
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: 621bb10a-e5d7-44fb-a025-317964b19d92
ms.openlocfilehash: 249c3eebaeec3d09a297fead07ab056caff1b618
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071806"
---
# <a name="how-to-return-a-linq-query-result-as-a-specific-type-visual-basic"></a><span data-ttu-id="d5cb1-102">Gewusst wie: Zurückgeben eines LINQ-Abfrageergebnisses als ein bestimmter Typ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d5cb1-102">How to: Return a LINQ Query Result as a Specific Type (Visual Basic)</span></span>

<span data-ttu-id="d5cb1-103">Language-Integrated Query (LINQ) vereinfacht den Zugriff auf Datenbankinformationen und das Ausführen von Abfragen.</span><span class="sxs-lookup"><span data-stu-id="d5cb1-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span> <span data-ttu-id="d5cb1-104">LINQ-Abfragen geben standardmäßig eine Liste von Objekten als anonymen Typ zurück.</span><span class="sxs-lookup"><span data-stu-id="d5cb1-104">By default, LINQ queries return a list of objects as an anonymous type.</span></span> <span data-ttu-id="d5cb1-105">Sie können auch angeben, dass eine Abfrage mithilfe der-Klausel eine Liste eines bestimmten Typs zurückgeben soll `Select` .</span><span class="sxs-lookup"><span data-stu-id="d5cb1-105">You can also specify that a query return a list of a specific type by using the `Select` clause.</span></span>  
  
 <span data-ttu-id="d5cb1-106">Im folgenden Beispiel wird gezeigt, wie eine neue Anwendung erstellt wird, die Abfragen für eine SQL Server Datenbank ausführt und die Ergebnisse als einen bestimmten benannten Typ projiziert.</span><span class="sxs-lookup"><span data-stu-id="d5cb1-106">The following example shows how to create a new application that performs queries against a SQL Server database and projects the results as a specific named type.</span></span> <span data-ttu-id="d5cb1-107">Weitere Informationen finden Sie unter [Anonyme Typen](../objects-and-classes/anonymous-types.md) und [SELECT-Klausel](../../../language-reference/queries/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="d5cb1-107">For more information, see [Anonymous Types](../objects-and-classes/anonymous-types.md) and [Select Clause](../../../language-reference/queries/select-clause.md).</span></span>  
  
 <span data-ttu-id="d5cb1-108">In den Beispielen in diesem Thema wird die Beispieldatenbank Northwind verwendet.</span><span class="sxs-lookup"><span data-stu-id="d5cb1-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="d5cb1-109">Befindet sich diese Datenbank nicht auf Ihrem Entwicklungscomputer, können Sie sie aus dem Microsoft Download Center herunterladen.</span><span class="sxs-lookup"><span data-stu-id="d5cb1-109">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="d5cb1-110">Anweisungen hierzu finden Sie unter [Herunterladen von Beispiel Datenbanken](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="d5cb1-110">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="d5cb1-111">So erstellen Sie eine Verbindung mit einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="d5cb1-111">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="d5cb1-112">Öffnen Sie in Visual Studio **Server-Explorer** / **Datenbank-Explorer** , indem **Server Explorer**Sie / im Menü **Ansicht** auf Server-Explorer**Datenbank-Explorer** klicken.</span><span class="sxs-lookup"><span data-stu-id="d5cb1-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="d5cb1-113">Klicken Sie in **Server-Explorer**Datenbank-Explorer mit der rechten Maustaste auf **Datenverbindungen** / **Database Explorer** und dann auf **Verbindung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="d5cb1-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="d5cb1-114">Geben Sie eine gültige Verbindung mit der Northwind-Beispieldatenbank an.</span><span class="sxs-lookup"><span data-stu-id="d5cb1-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="d5cb1-115">So fügen Sie ein Projekt hinzu, das eine LINQ to SQL Datei enthält</span><span class="sxs-lookup"><span data-stu-id="d5cb1-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="d5cb1-116">Zeigen Sie in Visual Studio im Menü **Datei** auf **Neu**, und klicken Sie auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="d5cb1-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="d5cb1-117">Wählen Sie Visual Basic **Windows Forms Anwendung** als Projekttyp aus.</span><span class="sxs-lookup"><span data-stu-id="d5cb1-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="d5cb1-118">Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="d5cb1-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="d5cb1-119">Wählen Sie die Element Vorlage **LINQ to SQL Klassen** aus.</span><span class="sxs-lookup"><span data-stu-id="d5cb1-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="d5cb1-120">Benennen Sie die Datei mit `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="d5cb1-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="d5cb1-121">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="d5cb1-121">Click **Add**.</span></span> <span data-ttu-id="d5cb1-122">Der objektrelationaler Designer (O/R-Designer) wird für die Datei Northwind. dbml geöffnet.</span><span class="sxs-lookup"><span data-stu-id="d5cb1-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="d5cb1-123">So fügen Sie dem O/R-Designer abzufragende Tabellen hinzu</span><span class="sxs-lookup"><span data-stu-id="d5cb1-123">To add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="d5cb1-124">Erweitern Sie in **Server-Explorer** / **Datenbank-Explorer**die Verbindung mit der Northwind-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="d5cb1-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="d5cb1-125">Erweitern Sie den Ordner **Tabellen** .</span><span class="sxs-lookup"><span data-stu-id="d5cb1-125">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="d5cb1-126">Wenn Sie den O/R-Designer geschlossen haben, können Sie ihn erneut öffnen, indem Sie auf die Datei Northwind. dbml, die Sie zuvor hinzugefügt haben, doppelklicken.</span><span class="sxs-lookup"><span data-stu-id="d5cb1-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="d5cb1-127">Klicken Sie auf die Tabelle Customers, und ziehen Sie Sie in den linken Bereich des Designers.</span><span class="sxs-lookup"><span data-stu-id="d5cb1-127">Click the Customers table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="d5cb1-128">Der Designer erstellt ein neues- `Customer` Objekt für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="d5cb1-128">The designer creates a new `Customer` object for your project.</span></span> <span data-ttu-id="d5cb1-129">Sie können ein Abfrageergebnis als `Customer` Typ oder als Typ projizieren, den Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="d5cb1-129">You can project a query result as the `Customer` type or as a type that you create.</span></span> <span data-ttu-id="d5cb1-130">In diesem Beispiel wird in einer späteren Prozedur ein neuer Typ erstellt und ein Abfrageergebnis als dieser Typ verwendet.</span><span class="sxs-lookup"><span data-stu-id="d5cb1-130">This sample will create a new type in a later procedure and project a query result as that type.</span></span>  
  
3. <span data-ttu-id="d5cb1-131">Speichern Sie die Änderungen, und schließen Sie den Designer.</span><span class="sxs-lookup"><span data-stu-id="d5cb1-131">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="d5cb1-132">Speichern Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="d5cb1-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="d5cb1-133">So fügen Sie Code hinzu, um die Datenbank abzufragen und die Ergebnisse anzuzeigen</span><span class="sxs-lookup"><span data-stu-id="d5cb1-133">To add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="d5cb1-134">Ziehen Sie aus der **Toolbox**ein- <xref:System.Windows.Forms.DataGridView> Steuerelement auf das Windows-Standardformular für das Projekt, Form1.</span><span class="sxs-lookup"><span data-stu-id="d5cb1-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="d5cb1-135">Doppelklicken Sie auf Form1, um die Form1-Klasse zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d5cb1-135">Double-click Form1 to modify the Form1 class.</span></span>  
  
3. <span data-ttu-id="d5cb1-136">`End Class`Fügen Sie nach der Anweisung der Form1-Klasse den folgenden Code hinzu, um einen `CustomerInfo` Typ zum Speichern der Abfrageergebnisse für dieses Beispiel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d5cb1-136">After the `End Class` statement of the Form1 class, add the following code to create a `CustomerInfo` type to hold the query results for this sample.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form8.vb#16)]  
  
4. <span data-ttu-id="d5cb1-137">Wenn Sie dem O/R-Designer Tabellen hinzugefügt haben, hat der Designer dem Projekt ein-Objekt hinzugefügt <xref:System.Data.Linq.DataContext> .</span><span class="sxs-lookup"><span data-stu-id="d5cb1-137">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="d5cb1-138">Dieses Objekt enthält den Code, den Sie für den Zugriff auf diese Tabellen benötigen, und für den Zugriff auf einzelne Objekte und Auflistungen für jede Tabelle.</span><span class="sxs-lookup"><span data-stu-id="d5cb1-138">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="d5cb1-139">Das- <xref:System.Data.Linq.DataContext> Objekt für das Projekt wird basierend auf dem Namen der DBML-Datei benannt.</span><span class="sxs-lookup"><span data-stu-id="d5cb1-139">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="d5cb1-140">Für dieses Projekt hat das <xref:System.Data.Linq.DataContext> Objekt den Namen `northwindDataContext` .</span><span class="sxs-lookup"><span data-stu-id="d5cb1-140">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="d5cb1-141">Sie können eine Instanz von <xref:System.Data.Linq.DataContext> im Code erstellen und die im O/R-Designer angegebenen Tabellen Abfragen.</span><span class="sxs-lookup"><span data-stu-id="d5cb1-141">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="d5cb1-142">`Load`Fügen Sie im-Ereignis der Form1-Klasse den folgenden Code hinzu, um die Tabellen abzufragen, die als Eigenschaften des Daten Kontexts verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="d5cb1-142">In the `Load` event of the Form1 class, add the following code to query the tables that are exposed as properties of your data context.</span></span> <span data-ttu-id="d5cb1-143">Die- `Select` Klausel der Abfrage erstellt `CustomerInfo` für jedes Element des Abfrage Ergebnisses einen neuen Typ anstelle eines anonymen Typs.</span><span class="sxs-lookup"><span data-stu-id="d5cb1-143">The `Select` clause of the query will create a new `CustomerInfo` type instead of an anonymous type for each item of the query result.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form8.vb#15)]  
  
5. <span data-ttu-id="d5cb1-144">Drücken Sie F5, um das Projekt auszuführen und die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d5cb1-144">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5cb1-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d5cb1-145">See also</span></span>

- [<span data-ttu-id="d5cb1-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="d5cb1-146">LINQ</span></span>](index.md)
- [<span data-ttu-id="d5cb1-147">Abfragen</span><span class="sxs-lookup"><span data-stu-id="d5cb1-147">Queries</span></span>](../../../language-reference/queries/index.md)
- [<span data-ttu-id="d5cb1-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="d5cb1-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="d5cb1-149">DataContext-Methoden (O/R-Designer)</span><span class="sxs-lookup"><span data-stu-id="d5cb1-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
