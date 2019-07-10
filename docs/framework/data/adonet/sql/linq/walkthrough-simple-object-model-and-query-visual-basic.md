---
title: 'Exemplarische Vorgehensweise: Einfaches Objektmodell und Abfrage (Visual Basic)'
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: c878e457-f715-46e4-a136-ff14d6c86018
ms.openlocfilehash: 9bf97263bf8ae0ac3ece187e81a51edfaef48a54
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742579"
---
# <a name="walkthrough-simple-object-model-and-query-visual-basic"></a><span data-ttu-id="5df3f-102">Exemplarische Vorgehensweise: Einfaches Objektmodell und Abfrage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5df3f-102">Walkthrough: Simple Object Model and Query (Visual Basic)</span></span>
<span data-ttu-id="5df3f-103">Diese exemplarische Vorgehensweise stellt ein grundlegendes End-to-End-Szenario für [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] mit minimaler Komplexität bereit.</span><span class="sxs-lookup"><span data-stu-id="5df3f-103">This walkthrough provides a fundamental end-to-end [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] scenario with minimal complexities.</span></span> <span data-ttu-id="5df3f-104">Sie erstellen eine Entitätsklasse, die die Customers-Tabelle in der Beispieldatenbank Northwind modelliert.</span><span class="sxs-lookup"><span data-stu-id="5df3f-104">You will create an entity class that models the Customers table in the sample Northwind database.</span></span> <span data-ttu-id="5df3f-105">Sie erstellen dann eine einfache Abfrage, um Kunden aus London aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="5df3f-105">You will then create a simple query to list customers who are located in London.</span></span>  
  
 <span data-ttu-id="5df3f-106">Diese exemplarische Vorgehensweise ist codeorientiert, um [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Konzepte zu verdeutlichen.</span><span class="sxs-lookup"><span data-stu-id="5df3f-106">This walkthrough is code-oriented by design to help show [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] concepts.</span></span> <span data-ttu-id="5df3f-107">Normalerweise würde der Object Relational Designer können Sie um Ihr Objektmodell zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5df3f-107">Normally speaking, you would use the Object Relational Designer to create your object model.</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="5df3f-108">Diese exemplarische Vorgehensweise wurde mithilfe von Visual Basic-Entwicklungseinstellungen geschrieben.</span><span class="sxs-lookup"><span data-stu-id="5df3f-108">This walkthrough was written by using Visual Basic Development Settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5df3f-109">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="5df3f-109">Prerequisites</span></span>  
  
- <span data-ttu-id="5df3f-110">Diese exemplarische Vorgehensweise verwendet einen dedizierten Ordner ("c:\linqtest") als Speicherort für Dateien.</span><span class="sxs-lookup"><span data-stu-id="5df3f-110">This walkthrough uses a dedicated folder ("c:\linqtest") to hold files.</span></span> <span data-ttu-id="5df3f-111">Erstellen Sie diesen Ordner, bevor Sie die exemplarische Vorgehensweise starten.</span><span class="sxs-lookup"><span data-stu-id="5df3f-111">Create this folder before you begin the walkthrough.</span></span>  
  
- <span data-ttu-id="5df3f-112">Für dieses Beispiel wird die Beispieldatenbank Northwind benötigt.</span><span class="sxs-lookup"><span data-stu-id="5df3f-112">This walkthrough requires the Northwind sample database.</span></span> <span data-ttu-id="5df3f-113">Befindet sich diese Datenbank nicht auf Ihrem Entwicklungscomputer, können Sie diese von der Microsoft Downloadsite herunterladen.</span><span class="sxs-lookup"><span data-stu-id="5df3f-113">If you do not have this database on your development computer, you can download it from the Microsoft download site.</span></span> <span data-ttu-id="5df3f-114">Anweisungen hierzu finden Sie unter [Herunterladen von Beispieldatenbanken](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="5df3f-114">For instructions, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span> <span data-ttu-id="5df3f-115">Nachdem Sie die Datenbank heruntergeladen haben, kopieren Sie die Datei in den Ordner c:\linqtest.</span><span class="sxs-lookup"><span data-stu-id="5df3f-115">After you have downloaded the database, copy the file to the c:\linqtest folder.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="5df3f-116">Übersicht</span><span class="sxs-lookup"><span data-stu-id="5df3f-116">Overview</span></span>  
 <span data-ttu-id="5df3f-117">Diese exemplarische Vorgehensweise umfasst sechs Hauptaufgaben:</span><span class="sxs-lookup"><span data-stu-id="5df3f-117">This walkthrough consists of six main tasks:</span></span>  
  
- <span data-ttu-id="5df3f-118">Erstellen einer [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Projektmappe in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5df3f-118">Creating a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solution in Visual Studio.</span></span>  
  
- <span data-ttu-id="5df3f-119">Zuordnen einer Datenbanktabelle zu einer Klasse.</span><span class="sxs-lookup"><span data-stu-id="5df3f-119">Mapping a class to a database table.</span></span>  
  
- <span data-ttu-id="5df3f-120">Festlegen von Eigenschaften für die Klasse, um Datenbankspalten darzustellen.</span><span class="sxs-lookup"><span data-stu-id="5df3f-120">Designating properties on the class to represent database columns.</span></span>  
  
- <span data-ttu-id="5df3f-121">Herstellen einer Verbindung zur Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="5df3f-121">Specifying the connection to the Northwind database.</span></span>  
  
- <span data-ttu-id="5df3f-122">Erstellen einer einfachen Abfrage der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="5df3f-122">Creating a simple query to run against the database.</span></span>  
  
- <span data-ttu-id="5df3f-123">Ausführen der Abfrage und Prüfen der Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="5df3f-123">Executing the query and observing the results.</span></span>  
  
## <a name="creating-a-linq-to-sql-solution"></a><span data-ttu-id="5df3f-124">Erstellen einer LINQ to SQL-Lösung</span><span class="sxs-lookup"><span data-stu-id="5df3f-124">Creating a LINQ to SQL Solution</span></span>  
 <span data-ttu-id="5df3f-125">In dieser ersten Aufgabe erstellen Sie eine Visual Studio-Projektmappe, die die erforderlichen Verweise zur Erstellung und Ausführung enthält eine [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Projekt.</span><span class="sxs-lookup"><span data-stu-id="5df3f-125">In this first task, you create a Visual Studio solution that contains the necessary references to build and run a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project.</span></span>  
  
#### <a name="to-create-a-linq-to-sql-solution"></a><span data-ttu-id="5df3f-126">So erstellen Sie eine LINQ to SQL-Lösung</span><span class="sxs-lookup"><span data-stu-id="5df3f-126">To create a LINQ to SQL solution</span></span>  
  
1. <span data-ttu-id="5df3f-127">Klicken Sie im Menü **Datei** auf **Neues Projekt**.</span><span class="sxs-lookup"><span data-stu-id="5df3f-127">On the **File** menu, click **New Project**.</span></span>  
  
2. <span data-ttu-id="5df3f-128">In der **Projekttypen** im Bereich der **neues Projekt** Dialogfeld klicken Sie auf **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="5df3f-128">In the **Project types** pane of the **New Project** dialog box, click **Visual Basic**.</span></span>  
  
3. <span data-ttu-id="5df3f-129">Klicken Sie im Bereich **Vorlagen** auf **Konsolenanwendung**.</span><span class="sxs-lookup"><span data-stu-id="5df3f-129">In the **Templates** pane, click **Console Application**.</span></span>  
  
4. <span data-ttu-id="5df3f-130">In der **Namen** geben **LinqConsoleApp**.</span><span class="sxs-lookup"><span data-stu-id="5df3f-130">In the **Name** box, type **LinqConsoleApp**.</span></span>  
  
5. <span data-ttu-id="5df3f-131">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5df3f-131">Click **OK**.</span></span>  
  
## <a name="adding-linq-references-and-directives"></a><span data-ttu-id="5df3f-132">Hinzufügen von LINQ-Verweisen und Anweisungen</span><span class="sxs-lookup"><span data-stu-id="5df3f-132">Adding LINQ References and Directives</span></span>  
 <span data-ttu-id="5df3f-133">Diese exemplarische Vorgehensweise verwendet Assemblys, die im Projekt u. U. nicht standardmäßig installiert sind.</span><span class="sxs-lookup"><span data-stu-id="5df3f-133">This walkthrough uses assemblies that might not be installed by default in your project.</span></span> <span data-ttu-id="5df3f-134">Wenn `System.Data.Linq` ist nicht als Verweis im Projekt aufgeführt (klicken Sie auf **alle Dateien anzeigen** in **Projektmappen-Explorer** und erweitern Sie die **Verweise** Knoten), fügen Sie, wie beschrieben hinzu die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="5df3f-134">If `System.Data.Linq` is not listed as a reference in your project (click **Show All Files** in **Solution Explorer** and expand the **References** node), add it, as explained in the following steps.</span></span>  
  
#### <a name="to-add-systemdatalinq"></a><span data-ttu-id="5df3f-135">So fügen Sie System.Data.Linq hinzu</span><span class="sxs-lookup"><span data-stu-id="5df3f-135">To add System.Data.Linq</span></span>  
  
1. <span data-ttu-id="5df3f-136">In **Projektmappen-Explorer**, mit der rechten Maustaste **Verweise**, und klicken Sie dann auf **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="5df3f-136">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>  
  
2. <span data-ttu-id="5df3f-137">In der **Verweis hinzufügen** Dialogfeld klicken Sie auf **.NET**, klicken Sie auf die System.Data.Linq-Assembly, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5df3f-137">In the **Add Reference** dialog box, click **.NET**, click the System.Data.Linq assembly, and then click **OK**.</span></span>  
  
     <span data-ttu-id="5df3f-138">Dem Projekt wird die Assembly hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5df3f-138">The assembly is added to the project.</span></span>  
  
3. <span data-ttu-id="5df3f-139">Auch in der **Verweis hinzufügen** Dialogfeld klicken Sie auf **.NET**, scrollen Sie zu, und klicken Sie auf "System.Windows.Forms" und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5df3f-139">Also in the **Add Reference** dialog box, click **.NET**, scroll to and click System.Windows.Forms, and then click **OK**.</span></span>  
  
     <span data-ttu-id="5df3f-140">Dem Projekt wird diese Assembly, die das Meldungsfeld in der exemplarischen Vorgehensweise unterstützt, hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5df3f-140">This assembly, which supports the message box in the walkthrough, is added to the project.</span></span>  
  
4. <span data-ttu-id="5df3f-141">Fügen Sie die folgenden Direktiven oberhalb von `Module1` hinzu:</span><span class="sxs-lookup"><span data-stu-id="5df3f-141">Add the following directives above `Module1`:</span></span>  
  
     [!code-vb[DLinqWalk1VB#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1VB/vb/Module1.vb#1)]  
  
## <a name="mapping-a-class-to-a-database-table"></a><span data-ttu-id="5df3f-142">Zuordnen einer Klasse zu einer Datenbanktabelle.</span><span class="sxs-lookup"><span data-stu-id="5df3f-142">Mapping a Class to a Database Table</span></span>  
 <span data-ttu-id="5df3f-143">In diesem Schritt erstellen Sie eine Klasse und ordnen diese einer Datenbanktabelle zu.</span><span class="sxs-lookup"><span data-stu-id="5df3f-143">In this step, you create a class and map it to a database table.</span></span> <span data-ttu-id="5df3f-144">Eine solche Klasse wird als bezeichnet ein *Entitätsklasse*.</span><span class="sxs-lookup"><span data-stu-id="5df3f-144">Such a class is termed an *entity class*.</span></span> <span data-ttu-id="5df3f-145">Beachten Sie, dass die Zuordnung durch Hinzufügen des <xref:System.Data.Linq.Mapping.TableAttribute>-Attributs erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="5df3f-145">Note that the mapping is accomplished by just adding the <xref:System.Data.Linq.Mapping.TableAttribute> attribute.</span></span> <span data-ttu-id="5df3f-146">Die <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A>-Eigenschaft gibt den Namen der Tabelle in der Datenbank an.</span><span class="sxs-lookup"><span data-stu-id="5df3f-146">The <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> property specifies the name of the table in the database.</span></span>  
  
#### <a name="to-create-an-entity-class-and-map-it-to-a-database-table"></a><span data-ttu-id="5df3f-147">So erstellen Sie eine Entitätsklasse und weisen diese einer Datenbanktabelle zu</span><span class="sxs-lookup"><span data-stu-id="5df3f-147">To create an entity class and map it to a database table</span></span>  
  
- <span data-ttu-id="5df3f-148">Geben Sie den folgenden Code in Module1.vb direkt oberhalb von `Sub Main` ein, oder fügen Sie ihn ein:</span><span class="sxs-lookup"><span data-stu-id="5df3f-148">Type or paste the following code into Module1.vb immediately above `Sub Main`:</span></span>  
  
     [!code-vb[DLinqWalk1VB#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1VB/vb/Module1.vb#2)]  
  
## <a name="designating-properties-on-the-class-to-represent-database-columns"></a><span data-ttu-id="5df3f-149">Festlegen von Eigenschaften für die Klasse, um Datenbankspalten darzustellen</span><span class="sxs-lookup"><span data-stu-id="5df3f-149">Designating Properties on the Class to Represent Database Columns</span></span>  
 <span data-ttu-id="5df3f-150">In diesem Schritt erledigen Sie mehrere Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="5df3f-150">In this step, you accomplish several tasks.</span></span>  
  
- <span data-ttu-id="5df3f-151">Sie verwenden das <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut, um die `CustomerID`-Eigenschaft und die `City`-Eigenschaft der Entitätsklasse für die Darstellung von Spalten in der Datenbanktabelle festzulegen.</span><span class="sxs-lookup"><span data-stu-id="5df3f-151">You use the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate `CustomerID` and `City` properties on the entity class as representing columns in the database table.</span></span>  
  
- <span data-ttu-id="5df3f-152">Sie legen die `CustomerID`-Eigenschaft zur Darstellung einer Primärschlüsselspalte in der Datenbank fest.</span><span class="sxs-lookup"><span data-stu-id="5df3f-152">You designate the `CustomerID` property as representing a primary key column in the database.</span></span>  
  
- <span data-ttu-id="5df3f-153">Sie legen `_CustomerID`- und `_City`-Felder für den privaten Speicher fest.</span><span class="sxs-lookup"><span data-stu-id="5df3f-153">You designate `_CustomerID` and `_City` fields for private storage.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="5df3f-154">kann Werte dann direkt speichern und abrufen, statt öffentliche Accessoren zu verwenden, die möglicherweise Geschäftslogik umfassen.</span><span class="sxs-lookup"><span data-stu-id="5df3f-154">can then store and retrieve values directly, instead of using public accessors that might include business logic.</span></span>  
  
#### <a name="to-represent-characteristics-of-two-database-columns"></a><span data-ttu-id="5df3f-155">So stellen Sie Eigenschaften von zwei Datenbankspalten dar</span><span class="sxs-lookup"><span data-stu-id="5df3f-155">To represent characteristics of two database columns</span></span>  
  
- <span data-ttu-id="5df3f-156">Geben Sie den folgenden Code in Module1.vb direkt vor `End Class` ein, oder fügen Sie ihn ein:</span><span class="sxs-lookup"><span data-stu-id="5df3f-156">Type or paste the following code into Module1.vb just before `End Class`:</span></span>  
  
     [!code-vb[DLinqWalk1VB#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1VB/vb/Module1.vb#3)]  
  
## <a name="specifying-the-connection-to-the-northwind-database"></a><span data-ttu-id="5df3f-157">Herstellen einer Verbindung zur Beispieldatenbank Northwind</span><span class="sxs-lookup"><span data-stu-id="5df3f-157">Specifying the Connection to the Northwind Database</span></span>  
 <span data-ttu-id="5df3f-158">In diesem Schritt verwenden Sie ein <xref:System.Data.Linq.DataContext>-Objekt zur Einrichtung einer Verbindung zwischen Ihren codebasierten Datenstrukturen und der Datenbank selbst.</span><span class="sxs-lookup"><span data-stu-id="5df3f-158">In this step you use a <xref:System.Data.Linq.DataContext> object to establish a connection between your code-based data structures and the database itself.</span></span> <span data-ttu-id="5df3f-159">Der <xref:System.Data.Linq.DataContext> ist der Hauptkanal, durch den Sie Objekte von der Datenbank abrufen und Änderungen übergeben.</span><span class="sxs-lookup"><span data-stu-id="5df3f-159">The <xref:System.Data.Linq.DataContext> is the main channel through which you retrieve objects from the database and submit changes.</span></span>  
  
 <span data-ttu-id="5df3f-160">Sie deklarieren außerdem eine `Table(Of Customer)` als logische, typisierte Tabelle für Ihre Abfragen der Customers-Tabelle in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="5df3f-160">You also declare a `Table(Of Customer)` to act as the logical, typed table for your queries against the Customers table in the database.</span></span> <span data-ttu-id="5df3f-161">Die Erstellung und Ausführung dieser Abfragen erfolgt später.</span><span class="sxs-lookup"><span data-stu-id="5df3f-161">You will create and execute these queries in later steps.</span></span>  
  
#### <a name="to-specify-the-database-connection"></a><span data-ttu-id="5df3f-162">So definieren Sie die Datenbankverbindung</span><span class="sxs-lookup"><span data-stu-id="5df3f-162">To specify the database connection</span></span>  
  
- <span data-ttu-id="5df3f-163">Geben Sie den folgenden Code in die `Sub Main`-Methode ein, oder fügen Sie ihn ein:</span><span class="sxs-lookup"><span data-stu-id="5df3f-163">Type or paste the following code into the `Sub Main` method.</span></span>  
  
     <span data-ttu-id="5df3f-164">Beachten Sie, dass die Datei `northwnd.mdf` im Ordner linqtest angenommen wird.</span><span class="sxs-lookup"><span data-stu-id="5df3f-164">Note that the `northwnd.mdf` file is assumed to be in the linqtest folder.</span></span> <span data-ttu-id="5df3f-165">Weitere Informationen finden Sie im Abschnitt zu Voraussetzungen weiter oben in dieser exemplarischen Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="5df3f-165">For more information, see the Prerequisites section earlier in this walkthrough.</span></span>  
  
     [!code-vb[DLinqWalk1VB#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1VB/vb/Module1.vb#4)]  
  
## <a name="creating-a-simple-query"></a><span data-ttu-id="5df3f-166">Erstellen einer einfachen Abfrage</span><span class="sxs-lookup"><span data-stu-id="5df3f-166">Creating a Simple Query</span></span>  
 <span data-ttu-id="5df3f-167">In diesem Schritt erstellen Sie eine Abfrage, um zu ermitteln, welche Kunden in der Customers-Datenbanktabelle aus London stammen.</span><span class="sxs-lookup"><span data-stu-id="5df3f-167">In this step, you create a query to find which customers in the database Customers table are located in London.</span></span> <span data-ttu-id="5df3f-168">Im Abfragecode in diesem Schritt wird nur die Abfrage beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5df3f-168">The query code in this step just describes the query.</span></span> <span data-ttu-id="5df3f-169">Die Abfrage wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5df3f-169">It does not execute it.</span></span> <span data-ttu-id="5df3f-170">Dieser Ansatz wird bezeichnet als *verzögerte Ausführung*.</span><span class="sxs-lookup"><span data-stu-id="5df3f-170">This approach is known as *deferred execution*.</span></span> <span data-ttu-id="5df3f-171">Weitere Informationen finden Sie unter [Introduction to LINQ queries (C#) (Einführung in LINQ-Abfragen (C#))](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="5df3f-171">For more information, see [Introduction to LINQ Queries (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 <span data-ttu-id="5df3f-172">Sie erzeugen auch eine Protokollausgabe, um die SQL-Befehle anzuzeigen, die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] erzeugt.</span><span class="sxs-lookup"><span data-stu-id="5df3f-172">You will also produce a log output to show the SQL commands that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates.</span></span> <span data-ttu-id="5df3f-173">Diese Protokolllierungsfunktion (die <xref:System.Data.Linq.DataContext.Log%2A> verwendet), eignet sich für das Debugging. Sie stellt außerdem sicher, dass die an die Datenbank übergebenen Befehle Ihre Abfrage genau wiedergeben.</span><span class="sxs-lookup"><span data-stu-id="5df3f-173">This logging feature (which uses <xref:System.Data.Linq.DataContext.Log%2A>) is helpful in debugging, and in determining that the commands being sent to the database accurately represent your query.</span></span>  
  
#### <a name="to-create-a-simple-query"></a><span data-ttu-id="5df3f-174">So erstellen Sie eine einfache Abfrage</span><span class="sxs-lookup"><span data-stu-id="5df3f-174">To create a simple query</span></span>  
  
- <span data-ttu-id="5df3f-175">Geben Sie den folgenden Code in die `Sub Main`-Methode nach der `Table(Of Customer)`-Deklaration ein, oder fügen Sie ihn ein:</span><span class="sxs-lookup"><span data-stu-id="5df3f-175">Type or paste the following code into the `Sub Main` method after the `Table(Of Customer)` declaration:</span></span>  
  
     [!code-vb[DLinqWalk1AVB#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1AVB/vb/Module1.vb#5)]  
  
## <a name="executing-the-query"></a><span data-ttu-id="5df3f-176">Ausführen der Abfrage</span><span class="sxs-lookup"><span data-stu-id="5df3f-176">Executing the Query</span></span>  
 <span data-ttu-id="5df3f-177">In diesem Schritt führen Sie die Abfrage aus.</span><span class="sxs-lookup"><span data-stu-id="5df3f-177">In this step, you actually execute the query.</span></span> <span data-ttu-id="5df3f-178">Die in den vorherigen Schritten erstellten Abfrageausdrücke werden erst ausgewertet, wenn die Ergebnisse benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="5df3f-178">The query expressions you created in the previous steps are not evaluated until the results are needed.</span></span> <span data-ttu-id="5df3f-179">Wenn Sie die `For Each`-Iteration beginnen, wird ein SQL-Befehl in der Datenbank ausgeführt, und Objekte werden erstellt.</span><span class="sxs-lookup"><span data-stu-id="5df3f-179">When you begin the `For Each` iteration, a SQL command is executed against the database and objects are materialized.</span></span>  
  
#### <a name="to-execute-the-query"></a><span data-ttu-id="5df3f-180">So führen Sie die Abfrage aus</span><span class="sxs-lookup"><span data-stu-id="5df3f-180">To execute the query</span></span>  
  
1. <span data-ttu-id="5df3f-181">Geben Sie den folgenden Code am Ende der `Sub Main`-Methode (nach der Abfragebeschreibung) ein, oder fügen Sie ihn ein:</span><span class="sxs-lookup"><span data-stu-id="5df3f-181">Type or paste the following code at the end of the `Sub Main` method (after the query description):</span></span>  
  
     [!code-vb[DLinqWalk1AVB#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1AVB/vb/Module1.vb#6)]  
  
2. <span data-ttu-id="5df3f-182">Drücken Sie F5, um die Anwendung zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="5df3f-182">Press F5 to debug the application.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5df3f-183">Wenn die Anwendung einen Laufzeitfehler erzeugt, finden Sie im Abschnitt zur Problembehandlung [lernen durch Exemplarische Vorgehensweisen](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md).</span><span class="sxs-lookup"><span data-stu-id="5df3f-183">If your application generates a run-time error, see the Troubleshooting section of [Learning by Walkthroughs](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md).</span></span>  
  
     <span data-ttu-id="5df3f-184">Das Meldungsfeld zeigt eine Liste von sechs Kunden an.</span><span class="sxs-lookup"><span data-stu-id="5df3f-184">The message box displays a list of six customers.</span></span> <span data-ttu-id="5df3f-185">Das Konsolenfenster zeigt den generierten SQL-Code an.</span><span class="sxs-lookup"><span data-stu-id="5df3f-185">The Console window displays the generated SQL code.</span></span>  
  
3. <span data-ttu-id="5df3f-186">Klicken Sie auf **OK**, um das Meldungsfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="5df3f-186">Click **OK** to dismiss the message box.</span></span>  
  
     <span data-ttu-id="5df3f-187">Die Anwendung wird geschlossen.</span><span class="sxs-lookup"><span data-stu-id="5df3f-187">The application closes.</span></span>  
  
4. <span data-ttu-id="5df3f-188">Klicken Sie im Menü **Datei** auf **Alle speichern**.</span><span class="sxs-lookup"><span data-stu-id="5df3f-188">On the **File** menu, click **Save All**.</span></span>  
  
     <span data-ttu-id="5df3f-189">Sie benötigen diese Anwendung, wenn Sie mit der nächsten exemplarischen Vorgehensweise fortfahren.</span><span class="sxs-lookup"><span data-stu-id="5df3f-189">You will need this application if you continue with the next walkthrough.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="5df3f-190">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="5df3f-190">Next Steps</span></span>  
 <span data-ttu-id="5df3f-191">Die [Exemplarische Vorgehensweise: Erstellen von Abfragen für Beziehungen (Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-querying-across-relationships-visual-basic.md) -Thema schließt, in dieser exemplarischen Vorgehensweise endet.</span><span class="sxs-lookup"><span data-stu-id="5df3f-191">The [Walkthrough: Querying Across Relationships (Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-querying-across-relationships-visual-basic.md) topic continues where this walkthrough ends.</span></span> <span data-ttu-id="5df3f-192">Die exemplarische Vorgehensweise zu beziehungsübergreifenden Abfragen zeigt, wie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] können Abfragen auf Tabellen, ähnlich wie *Joins* in einer relationalen Datenbank.</span><span class="sxs-lookup"><span data-stu-id="5df3f-192">The Querying Across Relationships walkthrough demonstrates how [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] can query across tables, similar to *joins* in a relational database.</span></span>  
  
 <span data-ttu-id="5df3f-193">Wenn Sie die exemplarische Vorgehensweise zu beziehungsübergreifenden Abfragen absolvieren möchten, stellen Sie sicher, dass Sie die gerade erstellte Lösung speichern, da diese benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="5df3f-193">If you want to do the Querying Across Relationships walkthrough, make sure to save the solution for the walkthrough you have just completed, which is a prerequisite.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5df3f-194">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5df3f-194">See also</span></span>

- [<span data-ttu-id="5df3f-195">Lernen durch exemplarische Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="5df3f-195">Learning by Walkthroughs</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
