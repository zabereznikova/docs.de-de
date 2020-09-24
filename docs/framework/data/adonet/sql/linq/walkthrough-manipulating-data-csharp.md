---
title: 'Exemplarische Vorgehensweise: Bearbeiten von Daten (C#)'
ms.date: 03/30/2017
ms.assetid: 24adfbe0-0ad6-449f-997d-8808e0770d2e
ms.openlocfilehash: fefbee533634ee42785c65e0265ce1e0567561b5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164063"
---
# <a name="walkthrough-manipulating-data-c"></a><span data-ttu-id="f3e07-102">Exemplarische Vorgehensweise: Bearbeiten von Daten (C#)</span><span class="sxs-lookup"><span data-stu-id="f3e07-102">Walkthrough: Manipulating Data (C#)</span></span>

<span data-ttu-id="f3e07-103">Diese exemplarische Vorgehensweise stellt ein grundlegendes End-to-End-Szenario für [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] zum Hinzufügen, Ändern und Löschen von Daten in einer Datenbank bereit.</span><span class="sxs-lookup"><span data-stu-id="f3e07-103">This walkthrough provides a fundamental end-to-end [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] scenario for adding, modifying, and deleting data in a database.</span></span> <span data-ttu-id="f3e07-104">Sie werden eine Kopie der Beispieldatenbank Northwind verwenden, um einen Kunden hinzuzufügen, den Namen des Kunden zu ändern und eine Bestellung zu löschen.</span><span class="sxs-lookup"><span data-stu-id="f3e07-104">You will use a copy of the sample Northwind database to add a customer, change the name of a customer, and delete an order.</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="f3e07-105">Diese exemplarische Vorgehensweise wurde mithilfe von Visual C#-Entwicklungseinstellungen geschrieben.</span><span class="sxs-lookup"><span data-stu-id="f3e07-105">This walkthrough was written by using Visual C# Development Settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f3e07-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="f3e07-106">Prerequisites</span></span>  

 <span data-ttu-id="f3e07-107">Für diese exemplarische Vorgehensweise wird Folgendes vorausgesetzt:</span><span class="sxs-lookup"><span data-stu-id="f3e07-107">This walkthrough requires the following:</span></span>  
  
- <span data-ttu-id="f3e07-108">Diese exemplarische Vorgehensweise verwendet einen dedizierten Ordner ("c:\linqtest6") als Speicherort für Dateien.</span><span class="sxs-lookup"><span data-stu-id="f3e07-108">This walkthrough uses a dedicated folder ("c:\linqtest6") to hold files.</span></span> <span data-ttu-id="f3e07-109">Erstellen Sie diesen Ordner, bevor Sie die exemplarische Vorgehensweise starten.</span><span class="sxs-lookup"><span data-stu-id="f3e07-109">Create this folder before you begin the walkthrough.</span></span>  
  
- <span data-ttu-id="f3e07-110">Die Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="f3e07-110">The Northwind sample database.</span></span>  
  
     <span data-ttu-id="f3e07-111">Befindet sich diese Datenbank nicht auf Ihrem Entwicklungscomputer, können Sie diese von der Microsoft Downloadsite herunterladen.</span><span class="sxs-lookup"><span data-stu-id="f3e07-111">If you do not have this database on your development computer, you can download it from the Microsoft download site.</span></span> <span data-ttu-id="f3e07-112">Anweisungen hierzu finden Sie unter [Herunterladen von Beispiel Datenbanken](downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="f3e07-112">For instructions, see [Downloading Sample Databases](downloading-sample-databases.md).</span></span> <span data-ttu-id="f3e07-113">Nachdem Sie die Datenbank heruntergeladen haben, kopieren Sie die Datei northwnd.mdf in den Ordner c:\linqtest6.</span><span class="sxs-lookup"><span data-stu-id="f3e07-113">After you have downloaded the database, copy the northwnd.mdf file to the c:\linqtest6 folder.</span></span>  
  
- <span data-ttu-id="f3e07-114">Eine von der Datenbank Northwind generierte C#-Codedatei.</span><span class="sxs-lookup"><span data-stu-id="f3e07-114">A C# code file generated from the Northwind database.</span></span>  
  
     <span data-ttu-id="f3e07-115">Sie können diese Datei mit dem-objektrelationaler Designer oder dem SQLMetal-Tool generieren.</span><span class="sxs-lookup"><span data-stu-id="f3e07-115">You can generate this file by using either the Object Relational Designer or the SQLMetal tool.</span></span> <span data-ttu-id="f3e07-116">Diese exemplarische Vorgehensweise wurde mithilfe des SQLMetal-Tools mit der folgenden Befehlszeile geschrieben:</span><span class="sxs-lookup"><span data-stu-id="f3e07-116">This walkthrough was written by using the SQLMetal tool with the following command line:</span></span>  
  
     <span data-ttu-id="f3e07-117">**sqlmetal /code:"c:\linqtest6\northwind.cs" /language:csharp "C:\linqtest6\northwnd.mdf" /pluralize**</span><span class="sxs-lookup"><span data-stu-id="f3e07-117">**sqlmetal /code:"c:\linqtest6\northwind.cs" /language:csharp "C:\linqtest6\northwnd.mdf" /pluralize**</span></span>  
  
     <span data-ttu-id="f3e07-118">Weitere Informationen finden Sie unter [SqlMetal.exe (Tool zur Codegenerierung)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="f3e07-118">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="overview"></a><span data-ttu-id="f3e07-119">Übersicht</span><span class="sxs-lookup"><span data-stu-id="f3e07-119">Overview</span></span>  

 <span data-ttu-id="f3e07-120">Diese exemplarische Vorgehensweise umfasst sechs Hauptaufgaben:</span><span class="sxs-lookup"><span data-stu-id="f3e07-120">This walkthrough consists of six main tasks:</span></span>  
  
- <span data-ttu-id="f3e07-121">Erstellen der Projekt Mappe [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f3e07-121">Creating the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solution in Visual Studio.</span></span>  
  
- <span data-ttu-id="f3e07-122">Hinzufügen der Datenbank-Codedatei zum Projekt.</span><span class="sxs-lookup"><span data-stu-id="f3e07-122">Adding the database code file to the project.</span></span>  
  
- <span data-ttu-id="f3e07-123">Erstellen eines neuen Kundenobjekts.</span><span class="sxs-lookup"><span data-stu-id="f3e07-123">Creating a new customer object.</span></span>  
  
- <span data-ttu-id="f3e07-124">Ändern des Kontaktnamens eines Kunden.</span><span class="sxs-lookup"><span data-stu-id="f3e07-124">Modifying the contact name of a customer.</span></span>  
  
- <span data-ttu-id="f3e07-125">Löschen einer Bestellung.</span><span class="sxs-lookup"><span data-stu-id="f3e07-125">Deleting an order.</span></span>  
  
- <span data-ttu-id="f3e07-126">Übergeben dieser Änderungen an der Datenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="f3e07-126">Submitting these changes to the Northwind database.</span></span>  
  
## <a name="creating-a-linq-to-sql-solution"></a><span data-ttu-id="f3e07-127">Erstellen einer LINQ to SQL-Lösung</span><span class="sxs-lookup"><span data-stu-id="f3e07-127">Creating a LINQ to SQL Solution</span></span>  

 <span data-ttu-id="f3e07-128">In dieser ersten Aufgabe erstellen Sie eine Visual Studio-Projekt Mappe, die die erforderlichen Verweise zum Erstellen und Ausführen eines [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Projekts enthält.</span><span class="sxs-lookup"><span data-stu-id="f3e07-128">In this first task, you create a Visual Studio solution that contains the necessary references to build and run a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project.</span></span>  
  
#### <a name="to-create-a-linq-to-sql-solution"></a><span data-ttu-id="f3e07-129">So erstellen Sie eine LINQ to SQL-Lösung</span><span class="sxs-lookup"><span data-stu-id="f3e07-129">To create a LINQ to SQL solution</span></span>  
  
1. <span data-ttu-id="f3e07-130">Zeigen Sie im Menü **Datei** von Visual Studio auf **neu**, und klicken Sie dann auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="f3e07-130">On the Visual Studio **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2. <span data-ttu-id="f3e07-131">Klicken Sie im Bereich **Projekttypen** im Dialogfeld **Neues Projekt** auf **Visual c#**.</span><span class="sxs-lookup"><span data-stu-id="f3e07-131">In the **Project types** pane in the **New Project** dialog box, click **Visual C#**.</span></span>  
  
3. <span data-ttu-id="f3e07-132">Klicken Sie im Bereich **Vorlagen** auf **Konsolenanwendung**.</span><span class="sxs-lookup"><span data-stu-id="f3e07-132">In the **Templates** pane, click **Console Application**.</span></span>  
  
4. <span data-ttu-id="f3e07-133">Geben Sie im Feld **Name den Namen** **LinqDataManipulationApp**ein.</span><span class="sxs-lookup"><span data-stu-id="f3e07-133">In the **Name** box, type **LinqDataManipulationApp**.</span></span>  
  
5. <span data-ttu-id="f3e07-134">Überprüfen Sie im Feld **Speicherort** , wo die Projektdateien gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f3e07-134">In the **Location** box, verify where you want to store your project files.</span></span>  
  
6. <span data-ttu-id="f3e07-135">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3e07-135">Click **OK**.</span></span>  
  
## <a name="adding-linq-references-and-directives"></a><span data-ttu-id="f3e07-136">Hinzufügen von LINQ-Verweisen und Anweisungen</span><span class="sxs-lookup"><span data-stu-id="f3e07-136">Adding LINQ References and Directives</span></span>  

 <span data-ttu-id="f3e07-137">Diese exemplarische Vorgehensweise verwendet Assemblys, die im Projekt u. U. nicht standardmäßig installiert sind.</span><span class="sxs-lookup"><span data-stu-id="f3e07-137">This walkthrough uses assemblies that might not be installed by default in your project.</span></span> <span data-ttu-id="f3e07-138">Wird System.Data.Linq in Ihrem Projekt nicht als Verweis aufgeführt, fügen Sie diesen wie nachfolgend beschrieben hinzu.</span><span class="sxs-lookup"><span data-stu-id="f3e07-138">If System.Data.Linq is not listed as a reference in your project, add it, as explained in the following steps:</span></span>  
  
#### <a name="to-add-systemdatalinq"></a><span data-ttu-id="f3e07-139">So fügen Sie System.Data.Linq hinzu</span><span class="sxs-lookup"><span data-stu-id="f3e07-139">To add System.Data.Linq</span></span>  
  
1. <span data-ttu-id="f3e07-140">Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf **Verweise**, und klicken Sie dann auf **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f3e07-140">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>  
  
2. <span data-ttu-id="f3e07-141">Klicken Sie im Dialogfeld **Verweis hinzufügen** auf **.net**, klicken Sie auf die Assembly System. Data. Linq, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3e07-141">In the **Add Reference** dialog box, click **.NET**, click the System.Data.Linq assembly, and then click **OK**.</span></span>  
  
     <span data-ttu-id="f3e07-142">Dem Projekt wird die Assembly hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f3e07-142">The assembly is added to the project.</span></span>  
  
3. <span data-ttu-id="f3e07-143">Fügen Sie die folgenden Direktiven am oberen Rand von Program.cs hinzu:</span><span class="sxs-lookup"><span data-stu-id="f3e07-143">Add the following directives at the top of Program.cs:</span></span>  
  
     [!code-csharp[DLinqWalk3CS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#1)]  
  
## <a name="adding-the-northwind-code-file-to-the-project"></a><span data-ttu-id="f3e07-144">Hinzufügen der Northwind-Codedatei zum Projekt.</span><span class="sxs-lookup"><span data-stu-id="f3e07-144">Adding the Northwind Code File to the Project</span></span>  

 <span data-ttu-id="f3e07-145">Bei diesen Schritten wird davon ausgegangen, dass Sie das SQLMetal-Tool zum Erzeugen einer Codedatei aus der Beispieldatenbank Northwind verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="f3e07-145">These steps assume that you have used the SQLMetal tool to generate a code file from the Northwind sample database.</span></span> <span data-ttu-id="f3e07-146">Weitere Informationen finden Sie im Abschnitt zu Voraussetzungen weiter oben in dieser exemplarischen Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="f3e07-146">For more information, see the Prerequisites section earlier in this walkthrough.</span></span>  
  
#### <a name="to-add-the-northwind-code-file-to-the-project"></a><span data-ttu-id="f3e07-147">So fügen Sie die Northwind-Codedatei dem Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="f3e07-147">To add the northwind code file to the project</span></span>  
  
1. <span data-ttu-id="f3e07-148">Klicken Sie im Menü **Projekt** auf **Vorhandenes Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f3e07-148">On the **Project** menu, click **Add Existing Item**.</span></span>  
  
2. <span data-ttu-id="f3e07-149">Navigieren Sie im Dialogfeld **Vorhandenes Element hinzufügen** zu c:\linqtest6\northwind.cs, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f3e07-149">In the **Add Existing Item** dialog box, navigate to c:\linqtest6\northwind.cs, and then click **Add**.</span></span>  
  
     <span data-ttu-id="f3e07-150">Die Datei northwind.cs wird dem Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f3e07-150">The northwind.cs file is added to the project.</span></span>  
  
## <a name="setting-up-the-database-connection"></a><span data-ttu-id="f3e07-151">Einrichten der Datenverbindungen</span><span class="sxs-lookup"><span data-stu-id="f3e07-151">Setting Up the Database Connection</span></span>  

 <span data-ttu-id="f3e07-152">Testen Sie zuerst die Verbindung zur Datenbank.</span><span class="sxs-lookup"><span data-stu-id="f3e07-152">First, test your connection to the database.</span></span> <span data-ttu-id="f3e07-153">Beachten Sie vor allem, dass die Datenbank, Northwnd, kein i-Zeichen hat.</span><span class="sxs-lookup"><span data-stu-id="f3e07-153">Note especially that the database, Northwnd, has no i character.</span></span> <span data-ttu-id="f3e07-154">Sollten im nächsten Schritt Fehler auftreten, prüfen Sie in der Datei northwind.cs die Schreibweise der partiellen Klasse Northwind.</span><span class="sxs-lookup"><span data-stu-id="f3e07-154">If you generate errors in the next steps, review the northwind.cs file to determine how the Northwind partial class is spelled.</span></span>  
  
#### <a name="to-set-up-and-test-the-database-connection"></a><span data-ttu-id="f3e07-155">So richten Sie die Datenbankverbindung ein und testen diese</span><span class="sxs-lookup"><span data-stu-id="f3e07-155">To set up and test the database connection</span></span>  
  
1. <span data-ttu-id="f3e07-156">Geben Sie den folgenden Code in die `Main`-Methode in der Programmklasse ein, oder fügen Sie ihn ein:</span><span class="sxs-lookup"><span data-stu-id="f3e07-156">Type or paste the following code into the `Main` method in the Program class:</span></span>  
  
     [!code-csharp[DLinqWalk3CS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#2)]  
  
2. <span data-ttu-id="f3e07-157">Drücken Sie die Taste F5, um die Anwendung an diesem Punkt zu testen.</span><span class="sxs-lookup"><span data-stu-id="f3e07-157">Press F5 to test the application at this point.</span></span>  
  
     <span data-ttu-id="f3e07-158">Ein **Konsolen** Fenster wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="f3e07-158">A **Console** window opens.</span></span>  
  
     <span data-ttu-id="f3e07-159">Sie können die Anwendung schließen, indem Sie im **Konsolen** Fenster die EINGABETASTE drücken, oder indem Sie im Visual Studio-Menü **Debuggen** auf **Debuggen beenden** klicken.</span><span class="sxs-lookup"><span data-stu-id="f3e07-159">You can close the application by pressing Enter in the **Console** window, or by clicking **Stop Debugging** on the Visual Studio **Debug** menu.</span></span>  
  
## <a name="creating-a-new-entity"></a><span data-ttu-id="f3e07-160">Erstellen einer neuen Entität</span><span class="sxs-lookup"><span data-stu-id="f3e07-160">Creating a New Entity</span></span>  

 <span data-ttu-id="f3e07-161">Eine neue Entität zu erstellen, ist einfach.</span><span class="sxs-lookup"><span data-stu-id="f3e07-161">Creating a new entity is straightforward.</span></span> <span data-ttu-id="f3e07-162">Sie können Objekte (z. B. `Customer`) erstellen, indem Sie das `new`-Schlüsselwort verwenden.</span><span class="sxs-lookup"><span data-stu-id="f3e07-162">You can create objects (such as `Customer`) by using the `new` keyword.</span></span>  
  
 <span data-ttu-id="f3e07-163">In diesem und den folgenden Abschnitten nehmen Sie Änderungen nur am lokalen Cache vor.</span><span class="sxs-lookup"><span data-stu-id="f3e07-163">In this and the following sections, you are making changes only to the local cache.</span></span> <span data-ttu-id="f3e07-164">Es werden keine Änderungen an die Datenbank gesendet, bis Sie zum Ende dieser exemplarischen Vorgehensweise <xref:System.Data.Linq.DataContext.SubmitChanges%2A> aufrufen.</span><span class="sxs-lookup"><span data-stu-id="f3e07-164">No changes are sent to the database until you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> toward the end of this walkthrough.</span></span>  
  
#### <a name="to-add-a-new-customer-entity-object"></a><span data-ttu-id="f3e07-165">So fügen Sie ein neues Kundenentitätsobjekt hinzu</span><span class="sxs-lookup"><span data-stu-id="f3e07-165">To add a new Customer entity object</span></span>  
  
1. <span data-ttu-id="f3e07-166">Erstellen Sie einen neuen `Customer`, indem Sie den folgenden Code vor `Console.ReadLine();` in der `Main`-Methode hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="f3e07-166">Create a new `Customer` by adding the following code before `Console.ReadLine();` in the `Main` method:</span></span>  
  
     [!code-csharp[DLinqWalk3CS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#3)]  
  
2. <span data-ttu-id="f3e07-167">Drücken Sie die Taste F5, um die Lösung zu Debuggen.</span><span class="sxs-lookup"><span data-stu-id="f3e07-167">Press F5 to debug the solution.</span></span>  
  
3. <span data-ttu-id="f3e07-168">Drücken Sie im **Konsolen** Fenster die EINGABETASTE, um das Debuggen zu verhindern und die exemplarische Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="f3e07-168">Press Enter in the **Console** window to stop debugging and continue the walkthrough.</span></span>  
  
## <a name="updating-an-entity"></a><span data-ttu-id="f3e07-169">Aktualisieren einer Entität</span><span class="sxs-lookup"><span data-stu-id="f3e07-169">Updating an Entity</span></span>  

 <span data-ttu-id="f3e07-170">In den folgenden Schritten rufen Sie ein `Customer`-Objekt ab und ändern eine seiner Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="f3e07-170">In the following steps, you will retrieve a `Customer` object and modify one of its properties.</span></span>  
  
#### <a name="to-change-the-name-of-a-customer"></a><span data-ttu-id="f3e07-171">So ändern Sie den Namen eines Kunden</span><span class="sxs-lookup"><span data-stu-id="f3e07-171">To change the name of a Customer</span></span>  
  
- <span data-ttu-id="f3e07-172">Fügen Sie den folgenden Code oberhalb von `Console.ReadLine();` ein:</span><span class="sxs-lookup"><span data-stu-id="f3e07-172">Add the following code above `Console.ReadLine();`:</span></span>  
  
     [!code-csharp[DLinqWalk3CS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#4)]  
  
## <a name="deleting-an-entity"></a><span data-ttu-id="f3e07-173">Löschen einer Entität</span><span class="sxs-lookup"><span data-stu-id="f3e07-173">Deleting an Entity</span></span>  

 <span data-ttu-id="f3e07-174">Unter Verwendung des gleichen Kundenobjekts können Sie die erste Bestellung löschen.</span><span class="sxs-lookup"><span data-stu-id="f3e07-174">Using the same customer object, you can delete the first order.</span></span>  
  
 <span data-ttu-id="f3e07-175">Der folgende Code zeigt, wie Beziehungen zwischen Zeilen getrennt werden und wie eine Zeile aus der Datenbank Northwind gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="f3e07-175">The following code demonstrates how to sever relationships between rows, and how to delete a row from the database.</span></span> <span data-ttu-id="f3e07-176">Fügen Sie den folgenden Code vor `Console.ReadLine` hinzu, um zu sehen, wie Objekte gelöscht werden können:</span><span class="sxs-lookup"><span data-stu-id="f3e07-176">Add the following code before `Console.ReadLine` to see how objects can be deleted:</span></span>  
  
#### <a name="to-delete-a-row"></a><span data-ttu-id="f3e07-177">So löschen Sie eine Zeile</span><span class="sxs-lookup"><span data-stu-id="f3e07-177">To delete a row</span></span>  
  
- <span data-ttu-id="f3e07-178">Fügen Sie den folgenden Code genau oberhalb von `Console.ReadLine();` ein.</span><span class="sxs-lookup"><span data-stu-id="f3e07-178">Add the following code just above `Console.ReadLine();`:</span></span>  
  
     [!code-csharp[DLinqWalk3CS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#5)]  
  
## <a name="submitting-changes-to-the-database"></a><span data-ttu-id="f3e07-179">Übergeben von Änderungen an die Datenbank</span><span class="sxs-lookup"><span data-stu-id="f3e07-179">Submitting Changes to the Database</span></span>  

 <span data-ttu-id="f3e07-180">Der letzte Schritt beim Erstellen, Aktualisieren und Löschen von Objekten besteht in der eigentlichen Übergabe der Änderungen an die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="f3e07-180">The final step required for creating, updating, and deleting objects, is to actually submit the changes to the database.</span></span> <span data-ttu-id="f3e07-181">Ohne diesen Schritt sind die Änderungen nur lokal und werden nicht in Abfrageergebnissen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f3e07-181">Without this step, your changes are only local and will not appear in query results.</span></span>  
  
#### <a name="to-submit-changes-to-the-database"></a><span data-ttu-id="f3e07-182">So übergeben Sie die Änderungen an die Datenbank</span><span class="sxs-lookup"><span data-stu-id="f3e07-182">To submit changes to the database</span></span>  
  
1. <span data-ttu-id="f3e07-183">Fügen Sie den folgenden Code genau oberhalb von `Console.ReadLine` ein:</span><span class="sxs-lookup"><span data-stu-id="f3e07-183">Insert the following code just above `Console.ReadLine`:</span></span>  
  
     [!code-csharp[DLinqWalk3CS#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#6)]  
  
2. <span data-ttu-id="f3e07-184">Fügen Sie den folgenden Code (nach `SubmitChanges`) ein, um den Vorher-Nachher-Effekt der Änderungsübergabe zu zeigen:</span><span class="sxs-lookup"><span data-stu-id="f3e07-184">Insert the following code (after `SubmitChanges`) to show the before and after effects of submitting the changes:</span></span>  
  
     [!code-csharp[DLinqWalk3CS#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#7)]  
  
3. <span data-ttu-id="f3e07-185">Drücken Sie die Taste F5, um die Lösung zu Debuggen.</span><span class="sxs-lookup"><span data-stu-id="f3e07-185">Press F5 to debug the solution.</span></span>  
  
4. <span data-ttu-id="f3e07-186">Drücken Sie im **Konsolen** Fenster die EINGABETASTE, um die Anwendung zu schließen.</span><span class="sxs-lookup"><span data-stu-id="f3e07-186">Press Enter in the **Console** window to close the application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f3e07-187">Wenn Sie den neuen Kunden durch Übergeben der Änderungen hinzugefügt haben, können Sie diese Lösung nicht einfach wieder ausführen.</span><span class="sxs-lookup"><span data-stu-id="f3e07-187">After you have added the new customer by submitting the changes, you cannot execute this solution again as is.</span></span> <span data-ttu-id="f3e07-188">Um die Lösung erneut auszuführen, ändern Sie den Namen und die ID des hinzuzufügenden Kunden.</span><span class="sxs-lookup"><span data-stu-id="f3e07-188">To execute the solution again, change the name of the customer and customer ID to be added.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3e07-189">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f3e07-189">See also</span></span>

- [<span data-ttu-id="f3e07-190">Lernen durch exemplarische Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="f3e07-190">Learning by Walkthroughs</span></span>](learning-by-walkthroughs.md)
