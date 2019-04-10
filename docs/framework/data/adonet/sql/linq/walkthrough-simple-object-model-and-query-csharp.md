---
title: 'Exemplarische Vorgehensweise: Einfaches Objektmodell und Abfrage (C#)'
ms.date: 03/30/2017
ms.assetid: 419961cc-92d6-45f5-ae8a-d485bdde3a37
ms.openlocfilehash: dc56f1e7886a1a1391d94b512ba5c91ca8c9092a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59309458"
---
# <a name="walkthrough-simple-object-model-and-query-c"></a><span data-ttu-id="94655-102">Exemplarische Vorgehensweise: Einfaches Objektmodell und Abfrage (C#)</span><span class="sxs-lookup"><span data-stu-id="94655-102">Walkthrough: Simple Object Model and Query (C#)</span></span>
<span data-ttu-id="94655-103">Diese exemplarische Vorgehensweise stellt ein grundlegendes End-to-End-Szenario für [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] mit minimaler Komplexität bereit.</span><span class="sxs-lookup"><span data-stu-id="94655-103">This walkthrough provides a fundamental end-to-end [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] scenario with minimal complexities.</span></span> <span data-ttu-id="94655-104">Sie erstellen eine Entitätsklasse, die die Customers-Tabelle in der Beispieldatenbank Northwind modelliert.</span><span class="sxs-lookup"><span data-stu-id="94655-104">You will create an entity class that models the Customers table in the sample Northwind database.</span></span> <span data-ttu-id="94655-105">Sie erstellen dann eine einfache Abfrage, um Kunden aus London aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="94655-105">You will then create a simple query to list customers who are located in London.</span></span>  
  
 <span data-ttu-id="94655-106">Diese exemplarische Vorgehensweise ist codeorientiert, um [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Konzepte zu verdeutlichen.</span><span class="sxs-lookup"><span data-stu-id="94655-106">This walkthrough is code-oriented by design to help show [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] concepts.</span></span> <span data-ttu-id="94655-107">In der Regel verwenden Sie [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] zum Erstellen des Objektmodells.</span><span class="sxs-lookup"><span data-stu-id="94655-107">Normally speaking, you would use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to create your object model.</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="94655-108">Diese exemplarische Vorgehensweise wurde mithilfe von Visual C#-Entwicklungseinstellungen geschrieben.</span><span class="sxs-lookup"><span data-stu-id="94655-108">This walkthrough was written by using Visual C# Development Settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="94655-109">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="94655-109">Prerequisites</span></span>  
  
-   <span data-ttu-id="94655-110">Diese exemplarische Vorgehensweise verwendet einen dedizierten Ordner ("c:\linqtest5") als Speicherort für Dateien.</span><span class="sxs-lookup"><span data-stu-id="94655-110">This walkthrough uses a dedicated folder ("c:\linqtest5") to hold files.</span></span> <span data-ttu-id="94655-111">Erstellen Sie diesen Ordner, bevor Sie die exemplarische Vorgehensweise starten.</span><span class="sxs-lookup"><span data-stu-id="94655-111">Create this folder before you begin the walkthrough.</span></span>  
  
-   <span data-ttu-id="94655-112">Für dieses Beispiel wird die Beispieldatenbank Northwind benötigt.</span><span class="sxs-lookup"><span data-stu-id="94655-112">This walkthrough requires the Northwind sample database.</span></span> <span data-ttu-id="94655-113">Befindet sich diese Datenbank nicht auf Ihrem Entwicklungscomputer, können Sie diese von der Microsoft Downloadsite herunterladen.</span><span class="sxs-lookup"><span data-stu-id="94655-113">If you do not have this database on your development computer, you can download it from the Microsoft download site.</span></span> <span data-ttu-id="94655-114">Anweisungen hierzu finden Sie unter [Herunterladen von Beispieldatenbanken](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="94655-114">For instructions, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span> <span data-ttu-id="94655-115">Nachdem Sie die Datenbank heruntergeladen haben, kopieren Sie die Datei in den Ordner c:\linqtest5.</span><span class="sxs-lookup"><span data-stu-id="94655-115">After you have downloaded the database, copy the file to the c:\linqtest5 folder.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="94655-116">Übersicht</span><span class="sxs-lookup"><span data-stu-id="94655-116">Overview</span></span>  
 <span data-ttu-id="94655-117">Diese exemplarische Vorgehensweise umfasst sechs Hauptaufgaben:</span><span class="sxs-lookup"><span data-stu-id="94655-117">This walkthrough consists of six main tasks:</span></span>  
  
-   <span data-ttu-id="94655-118">Erstellen einer [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Projektmappe in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="94655-118">Creating a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solution in Visual Studio.</span></span>  
  
-   <span data-ttu-id="94655-119">Zuordnen einer Datenbanktabelle zu einer Klasse.</span><span class="sxs-lookup"><span data-stu-id="94655-119">Mapping a class to a database table.</span></span>  
  
-   <span data-ttu-id="94655-120">Festlegen von Eigenschaften für die Klasse, um Datenbankspalten darzustellen.</span><span class="sxs-lookup"><span data-stu-id="94655-120">Designating properties on the class to represent database columns.</span></span>  
  
-   <span data-ttu-id="94655-121">Herstellen einer Verbindung zur Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="94655-121">Specifying the connection to the Northwind database.</span></span>  
  
-   <span data-ttu-id="94655-122">Erstellen einer einfachen Abfrage der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="94655-122">Creating a simple query to run against the database.</span></span>  
  
-   <span data-ttu-id="94655-123">Ausführen der Abfrage und Prüfen der Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="94655-123">Executing the query and observing the results.</span></span>  
  
## <a name="creating-a-linq-to-sql-solution"></a><span data-ttu-id="94655-124">Erstellen einer LINQ to SQL-Lösung</span><span class="sxs-lookup"><span data-stu-id="94655-124">Creating a LINQ to SQL Solution</span></span>  
 <span data-ttu-id="94655-125">In dieser ersten Aufgabe erstellen Sie eine Visual Studio-Projektmappe, die die erforderlichen Verweise zur Erstellung und Ausführung enthält eine [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Projekt.</span><span class="sxs-lookup"><span data-stu-id="94655-125">In this first task, you create a Visual Studio solution that contains the necessary references to build and run a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project.</span></span>  
  
#### <a name="to-create-a-linq-to-sql-solution"></a><span data-ttu-id="94655-126">So erstellen Sie eine LINQ to SQL-Lösung</span><span class="sxs-lookup"><span data-stu-id="94655-126">To create a LINQ to SQL solution</span></span>  
  
1. <span data-ttu-id="94655-127">Visual Studio **Datei** Startmenü **neu**, und klicken Sie dann auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="94655-127">On the Visual Studio **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2. <span data-ttu-id="94655-128">In der **Projekttypen** im Bereich der **neues Projekt** Dialogfeld klicken Sie auf **Visual C#** .</span><span class="sxs-lookup"><span data-stu-id="94655-128">In the **Project types** pane of the **New Project** dialog box, click **Visual C#**.</span></span>  
  
3. <span data-ttu-id="94655-129">Klicken Sie im Bereich **Vorlagen** auf **Konsolenanwendung**.</span><span class="sxs-lookup"><span data-stu-id="94655-129">In the **Templates** pane, click **Console Application**.</span></span>  
  
4. <span data-ttu-id="94655-130">In der **Namen** geben **LinqConsoleApp**.</span><span class="sxs-lookup"><span data-stu-id="94655-130">In the **Name** box, type **LinqConsoleApp**.</span></span>  
  
5. <span data-ttu-id="94655-131">In der **Speicherort** Vergewissern Sie sich, in der Sie die Projektdateien speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="94655-131">In the **Location** box, verify where you want to store your project files.</span></span>  
  
6. <span data-ttu-id="94655-132">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="94655-132">Click **OK**.</span></span>  
  
## <a name="adding-linq-references-and-directives"></a><span data-ttu-id="94655-133">Hinzufügen von LINQ-Verweisen und Anweisungen</span><span class="sxs-lookup"><span data-stu-id="94655-133">Adding LINQ References and Directives</span></span>  
 <span data-ttu-id="94655-134">Diese exemplarische Vorgehensweise verwendet Assemblys, die im Projekt u. U. nicht standardmäßig installiert sind.</span><span class="sxs-lookup"><span data-stu-id="94655-134">This walkthrough uses assemblies that might not be installed by default in your project.</span></span> <span data-ttu-id="94655-135">Wenn System.Data.Linq nicht als Verweis im Projekt aufgeführt ist (Erweitern Sie die **Verweise** Knoten **Projektmappen-Explorer**), fügen Sie diesen wie nachfolgend beschrieben hinzu.</span><span class="sxs-lookup"><span data-stu-id="94655-135">If System.Data.Linq is not listed as a reference in your project (expand the **References** node in **Solution Explorer**), add it, as explained in the following steps.</span></span>  
  
#### <a name="to-add-systemdatalinq"></a><span data-ttu-id="94655-136">So fügen Sie System.Data.Linq hinzu</span><span class="sxs-lookup"><span data-stu-id="94655-136">To add System.Data.Linq</span></span>  
  
1. <span data-ttu-id="94655-137">In **Projektmappen-Explorer**, mit der rechten Maustaste **Verweise**, und klicken Sie dann auf **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="94655-137">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>  
  
2. <span data-ttu-id="94655-138">In der **Verweis hinzufügen** Dialogfeld klicken Sie auf **.NET**, klicken Sie auf die System.Data.Linq-Assembly, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="94655-138">In the **Add Reference** dialog box, click **.NET**, click the System.Data.Linq assembly, and then click **OK**.</span></span>  
  
     <span data-ttu-id="94655-139">Dem Projekt wird die Assembly hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="94655-139">The assembly is added to the project.</span></span>  
  
3. <span data-ttu-id="94655-140">Fügen Sie die folgenden Direktiven am Anfang **"Program.cs"**:</span><span class="sxs-lookup"><span data-stu-id="94655-140">Add the following directives at the top of **Program.cs**:</span></span>  
  
     [!code-csharp[DLinqWalk1CS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1CS/cs/Program.cs#1)]  
  
## <a name="mapping-a-class-to-a-database-table"></a><span data-ttu-id="94655-141">Zuordnen einer Klasse zu einer Datenbanktabelle.</span><span class="sxs-lookup"><span data-stu-id="94655-141">Mapping a Class to a Database Table</span></span>  
 <span data-ttu-id="94655-142">In diesem Schritt erstellen Sie eine Klasse und ordnen diese einer Datenbanktabelle zu.</span><span class="sxs-lookup"><span data-stu-id="94655-142">In this step, you create a class and map it to a database table.</span></span> <span data-ttu-id="94655-143">Eine solche Klasse wird als bezeichnet ein *Entitätsklasse*.</span><span class="sxs-lookup"><span data-stu-id="94655-143">Such a class is termed an *entity class*.</span></span> <span data-ttu-id="94655-144">Beachten Sie, dass die Zuordnung durch Hinzufügen des <xref:System.Data.Linq.Mapping.TableAttribute>-Attributs erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="94655-144">Note that the mapping is accomplished by just adding the <xref:System.Data.Linq.Mapping.TableAttribute> attribute.</span></span> <span data-ttu-id="94655-145">Die <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A>-Eigenschaft gibt den Namen der Tabelle in der Datenbank an.</span><span class="sxs-lookup"><span data-stu-id="94655-145">The <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> property specifies the name of the table in the database.</span></span>  
  
#### <a name="to-create-an-entity-class-and-map-it-to-a-database-table"></a><span data-ttu-id="94655-146">So erstellen Sie eine Entitätsklasse und weisen diese einer Datenbanktabelle zu</span><span class="sxs-lookup"><span data-stu-id="94655-146">To create an entity class and map it to a database table</span></span>  
  
-   <span data-ttu-id="94655-147">Geben Sie den folgenden Code direkt oberhalb der `Program`-Klassendeklaration in Program.cs ein, oder fügen Sie ihn ein:</span><span class="sxs-lookup"><span data-stu-id="94655-147">Type or paste the following code into Program.cs immediately above the `Program` class declaration:</span></span>  
  
     [!code-csharp[DLinqWalk1CS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1CS/cs/Program.cs#2)]  
  
## <a name="designating-properties-on-the-class-to-represent-database-columns"></a><span data-ttu-id="94655-148">Festlegen von Eigenschaften für die Klasse, um Datenbankspalten darzustellen</span><span class="sxs-lookup"><span data-stu-id="94655-148">Designating Properties on the Class to Represent Database Columns</span></span>  
 <span data-ttu-id="94655-149">In diesem Schritt erledigen Sie mehrere Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="94655-149">In this step, you accomplish several tasks.</span></span>  
  
-   <span data-ttu-id="94655-150">Sie verwenden das <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut, um die `CustomerID`-Eigenschaft und die `City`-Eigenschaft der Entitätsklasse für die Darstellung von Spalten in der Datenbanktabelle festzulegen.</span><span class="sxs-lookup"><span data-stu-id="94655-150">You use the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate `CustomerID` and `City` properties on the entity class as representing columns in the database table.</span></span>  
  
-   <span data-ttu-id="94655-151">Sie legen die `CustomerID`-Eigenschaft zur Darstellung einer Primärschlüsselspalte in der Datenbank fest.</span><span class="sxs-lookup"><span data-stu-id="94655-151">You designate the `CustomerID` property as representing a primary key column in the database.</span></span>  
  
-   <span data-ttu-id="94655-152">Sie legen `_CustomerID`- und `_City`-Felder für den privaten Speicher fest.</span><span class="sxs-lookup"><span data-stu-id="94655-152">You designate `_CustomerID` and `_City` fields for private storage.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="94655-153">Speichern und können Werte direkt abrufen, statt öffentliche Accessoren, die möglicherweise Geschäftslogik umfassen.</span><span class="sxs-lookup"><span data-stu-id="94655-153">can then store and retrieve values directly, instead of using public accessors that might include business logic.</span></span>  
  
#### <a name="to-represent-characteristics-of-two-database-columns"></a><span data-ttu-id="94655-154">So stellen Sie Eigenschaften von zwei Datenbankspalten dar</span><span class="sxs-lookup"><span data-stu-id="94655-154">To represent characteristics of two database columns</span></span>  
  
-   <span data-ttu-id="94655-155">Geben Sie den folgenden Code in die geschweiften Klammern der `Customer`-Klasse in Program.cs ein, oder fügen Sie ihn ein.</span><span class="sxs-lookup"><span data-stu-id="94655-155">Type or paste the following code into Program.cs inside the curly braces for the `Customer` class.</span></span>  
  
     [!code-csharp[DLinqWalk1CS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1CS/cs/Program.cs#3)]  
  
## <a name="specifying-the-connection-to-the-northwind-database"></a><span data-ttu-id="94655-156">Herstellen einer Verbindung zur Beispieldatenbank Northwind</span><span class="sxs-lookup"><span data-stu-id="94655-156">Specifying the Connection to the Northwind Database</span></span>  
 <span data-ttu-id="94655-157">In diesem Schritt verwenden Sie ein <xref:System.Data.Linq.DataContext>-Objekt zur Einrichtung einer Verbindung zwischen Ihren codebasierten Datenstrukturen und der Datenbank selbst.</span><span class="sxs-lookup"><span data-stu-id="94655-157">In this step you use a <xref:System.Data.Linq.DataContext> object to establish a connection between your code-based data structures and the database itself.</span></span> <span data-ttu-id="94655-158">Der <xref:System.Data.Linq.DataContext> ist der Hauptkanal, durch den Sie Objekte von der Datenbank abrufen und Änderungen übergeben.</span><span class="sxs-lookup"><span data-stu-id="94655-158">The <xref:System.Data.Linq.DataContext> is the main channel through which you retrieve objects from the database and submit changes.</span></span>  
  
 <span data-ttu-id="94655-159">Sie deklarieren außerdem eine `Table<Customer>` als logische, typisierte Tabelle für Ihre Abfragen der Customers-Tabelle in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="94655-159">You also declare a `Table<Customer>` to act as the logical, typed table for your queries against the Customers table in the database.</span></span> <span data-ttu-id="94655-160">Die Erstellung und Ausführung dieser Abfragen erfolgt später.</span><span class="sxs-lookup"><span data-stu-id="94655-160">You will create and execute these queries in later steps.</span></span>  
  
#### <a name="to-specify-the-database-connection"></a><span data-ttu-id="94655-161">So definieren Sie die Datenbankverbindung</span><span class="sxs-lookup"><span data-stu-id="94655-161">To specify the database connection</span></span>  
  
-   <span data-ttu-id="94655-162">Geben Sie den folgenden Code in die `Main`-Methode ein, oder fügen Sie ihn ein:</span><span class="sxs-lookup"><span data-stu-id="94655-162">Type or paste the following code into the `Main` method.</span></span>  
  
     <span data-ttu-id="94655-163">Beachten Sie, dass die Datei `northwnd.mdf` im Ordner linqtest5 angenommen wird.</span><span class="sxs-lookup"><span data-stu-id="94655-163">Note that the `northwnd.mdf` file is assumed to be in the linqtest5 folder.</span></span> <span data-ttu-id="94655-164">Weitere Informationen finden Sie im Abschnitt zu Voraussetzungen weiter oben in dieser exemplarischen Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="94655-164">For more information, see the Prerequisites section earlier in this walkthrough.</span></span>  
  
     [!code-csharp[DLinqWalk1CS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1CS/cs/Program.cs#4)]  
  
## <a name="creating-a-simple-query"></a><span data-ttu-id="94655-165">Erstellen einer einfachen Abfrage</span><span class="sxs-lookup"><span data-stu-id="94655-165">Creating a Simple Query</span></span>  
 <span data-ttu-id="94655-166">In diesem Schritt erstellen Sie eine Abfrage, um zu ermitteln, welche Kunden in der Customers-Datenbanktabelle aus London stammen.</span><span class="sxs-lookup"><span data-stu-id="94655-166">In this step, you create a query to find which customers in the database Customers table are located in London.</span></span> <span data-ttu-id="94655-167">Im Abfragecode in diesem Schritt wird nur die Abfrage beschrieben.</span><span class="sxs-lookup"><span data-stu-id="94655-167">The query code in this step just describes the query.</span></span> <span data-ttu-id="94655-168">Die Abfrage wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="94655-168">It does not execute it.</span></span> <span data-ttu-id="94655-169">Dieser Ansatz wird bezeichnet als *verzögerte Ausführung*.</span><span class="sxs-lookup"><span data-stu-id="94655-169">This approach is known as *deferred execution*.</span></span> <span data-ttu-id="94655-170">Weitere Informationen finden Sie unter [Introduction to LINQ queries (C#) (Einführung in LINQ-Abfragen (C#))](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="94655-170">For more information, see [Introduction to LINQ Queries (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 <span data-ttu-id="94655-171">Sie erzeugen auch eine Protokollausgabe, um die SQL-Befehle anzuzeigen, die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] erzeugt.</span><span class="sxs-lookup"><span data-stu-id="94655-171">You will also produce a log output to show the SQL commands that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates.</span></span> <span data-ttu-id="94655-172">Diese Protokolllierungsfunktion (die <xref:System.Data.Linq.DataContext.Log%2A> verwendet), eignet sich für das Debugging. Sie stellt außerdem sicher, dass die an die Datenbank übergebenen Befehle Ihre Abfrage genau wiedergeben.</span><span class="sxs-lookup"><span data-stu-id="94655-172">This logging feature (which uses <xref:System.Data.Linq.DataContext.Log%2A>) is helpful in debugging, and in determining that the commands being sent to the database accurately represent your query.</span></span>  
  
#### <a name="to-create-a-simple-query"></a><span data-ttu-id="94655-173">So erstellen Sie eine einfache Abfrage</span><span class="sxs-lookup"><span data-stu-id="94655-173">To create a simple query</span></span>  
  
-   <span data-ttu-id="94655-174">Geben Sie den folgenden Code in die `Main`-Methode nach der `Table<Customer>`-Deklaration ein, oder fügen Sie ihn ein:</span><span class="sxs-lookup"><span data-stu-id="94655-174">Type or paste the following code into the `Main` method after the `Table<Customer>` declaration.</span></span>  
  
     [!code-csharp[DLinqWalk1ACS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1ACS/cs/Program.cs#5)]  
  
## <a name="executing-the-query"></a><span data-ttu-id="94655-175">Ausführen der Abfrage</span><span class="sxs-lookup"><span data-stu-id="94655-175">Executing the Query</span></span>  
 <span data-ttu-id="94655-176">In diesem Schritt führen Sie die Abfrage aus.</span><span class="sxs-lookup"><span data-stu-id="94655-176">In this step, you actually execute the query.</span></span> <span data-ttu-id="94655-177">Die in den vorherigen Schritten erstellten Abfrageausdrücke werden erst ausgewertet, wenn die Ergebnisse benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="94655-177">The query expressions you created in the previous steps are not evaluated until the results are needed.</span></span> <span data-ttu-id="94655-178">Wenn Sie die `foreach`-Iteration beginnen, wird ein SQL-Befehl in der Datenbank ausgeführt, und Objekte werden erstellt.</span><span class="sxs-lookup"><span data-stu-id="94655-178">When you begin the `foreach` iteration, a SQL command is executed against the database and objects are materialized.</span></span>  
  
#### <a name="to-execute-the-query"></a><span data-ttu-id="94655-179">So führen Sie die Abfrage aus</span><span class="sxs-lookup"><span data-stu-id="94655-179">To execute the query</span></span>  
  
1. <span data-ttu-id="94655-180">Geben Sie den folgenden Code am Ende der `Main`-Methode (nach der Abfragebeschreibung) ein. oder fügen Sie ihn ein:</span><span class="sxs-lookup"><span data-stu-id="94655-180">Type or paste the following code at the end of the `Main` method (after the query description).</span></span>  
  
     [!code-csharp[DLinqWalk1ACS#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1ACS/cs/Program.cs#6)]  
  
2. <span data-ttu-id="94655-181">Drücken Sie F5, um die Anwendung zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="94655-181">Press F5 to debug the application.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="94655-182">Wenn die Anwendung einen Laufzeitfehler erzeugt, finden Sie im Abschnitt zur Problembehandlung [lernen durch Exemplarische Vorgehensweisen](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md).</span><span class="sxs-lookup"><span data-stu-id="94655-182">If your application generates a run-time error, see the Troubleshooting section of [Learning by Walkthroughs](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md).</span></span>  
  
     <span data-ttu-id="94655-183">Die Abfrageergebnisse im Konsolenfenster werden wie folgt angezeigt:</span><span class="sxs-lookup"><span data-stu-id="94655-183">The query results in the console window should appear as follows:</span></span>  
  
     `ID=AROUT, City=London`  
  
     `ID=BSBEV, City=London`  
  
     `ID=CONSH, City=London`  
  
     `ID=EASTC, City=London`  
  
     `ID=NORTS, City=London`  
  
     `ID=SEVES, City=London`  
  
3. <span data-ttu-id="94655-184">Drücken Sie die EINGABETASTE im Konsolenfenster, um die Anwendung zu schließen.</span><span class="sxs-lookup"><span data-stu-id="94655-184">Press Enter in the console window to close the application.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="94655-185">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="94655-185">Next Steps</span></span>  
 <span data-ttu-id="94655-186">Die [Exemplarische Vorgehensweise: Erstellen von Abfragen für Beziehungen (C#)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-querying-across-relationships-csharp.md) -Thema schließt, in dieser exemplarischen Vorgehensweise endet.</span><span class="sxs-lookup"><span data-stu-id="94655-186">The [Walkthrough: Querying Across Relationships (C#)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-querying-across-relationships-csharp.md) topic continues where this walkthrough ends.</span></span> <span data-ttu-id="94655-187">Die exemplarische Vorgehensweise zu beziehungsübergreifenden Abfragen zeigt, wie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] können Abfragen auf Tabellen, ähnlich wie *Joins* in einer relationalen Datenbank.</span><span class="sxs-lookup"><span data-stu-id="94655-187">The Query Across Relationships walkthrough demonstrates how [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] can query across tables, similar to *joins* in a relational database.</span></span>  
  
 <span data-ttu-id="94655-188">Wenn Sie die exemplarische Vorgehensweise zu beziehungsübergreifenden Abfragen absolvieren möchten, stellen Sie sicher, dass Sie die gerade erstellte Lösung speichern, da diese benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="94655-188">If you want to do the Query Across Relationships walkthrough, make sure to save the solution for the walkthrough you have just completed, which is a prerequisite.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94655-189">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94655-189">See also</span></span>

- [<span data-ttu-id="94655-190">Lernen durch exemplarische Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="94655-190">Learning by Walkthroughs</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
