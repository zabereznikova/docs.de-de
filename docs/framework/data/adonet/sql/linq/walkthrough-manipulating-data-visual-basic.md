---
title: 'Exemplarische Vorgehensweise: Bearbeiten von Daten (Visual Basic)'
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: 1f6a54f6-ec33-452a-a37d-48122207bf14
ms.openlocfilehash: a74216c53c45790b974938c7155e0b5e1043ac13
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792287"
---
# <a name="walkthrough-manipulating-data-visual-basic"></a><span data-ttu-id="631af-102">Exemplarische Vorgehensweise: Bearbeiten von Daten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="631af-102">Walkthrough: Manipulating Data (Visual Basic)</span></span>
<span data-ttu-id="631af-103">Diese exemplarische Vorgehensweise stellt ein grundlegendes End-to-End-Szenario für [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] zum Hinzufügen, Ändern und Löschen von Daten in einer Datenbank bereit.</span><span class="sxs-lookup"><span data-stu-id="631af-103">This walkthrough provides a fundamental end-to-end [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] scenario for adding, modifying, and deleting data in a database.</span></span> <span data-ttu-id="631af-104">Sie werden eine Kopie der Beispieldatenbank Northwind verwenden, um einen Kunden hinzuzufügen, den Namen des Kunden zu ändern und eine Bestellung zu löschen.</span><span class="sxs-lookup"><span data-stu-id="631af-104">You will use a copy of the sample Northwind database to add a customer, change the name of a customer, and delete an order.</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="631af-105">Diese exemplarische Vorgehensweise wurde mithilfe von Visual Basic-Entwicklungseinstellungen geschrieben.</span><span class="sxs-lookup"><span data-stu-id="631af-105">This walkthrough was written by using Visual Basic Development Settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="631af-106">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="631af-106">Prerequisites</span></span>  
 <span data-ttu-id="631af-107">Für diese exemplarische Vorgehensweise wird Folgendes vorausgesetzt:</span><span class="sxs-lookup"><span data-stu-id="631af-107">This walkthrough requires the following:</span></span>  
  
- <span data-ttu-id="631af-108">Diese exemplarische Vorgehensweise verwendet einen dedizierten Ordner ("c:\linqtest2") als Speicherort für Dateien.</span><span class="sxs-lookup"><span data-stu-id="631af-108">This walkthrough uses a dedicated folder ("c:\linqtest2") to hold files.</span></span> <span data-ttu-id="631af-109">Erstellen Sie diesen Ordner, bevor Sie die exemplarische Vorgehensweise starten.</span><span class="sxs-lookup"><span data-stu-id="631af-109">Create this folder before you begin the walkthrough.</span></span>  
  
- <span data-ttu-id="631af-110">Die Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="631af-110">The Northwind sample database.</span></span>  
  
     <span data-ttu-id="631af-111">Befindet sich diese Datenbank nicht auf Ihrem Entwicklungscomputer, können Sie diese von der Microsoft Downloadsite herunterladen.</span><span class="sxs-lookup"><span data-stu-id="631af-111">If you do not have this database on your development computer, you can download it from the Microsoft download site.</span></span> <span data-ttu-id="631af-112">Anweisungen hierzu finden Sie unter [Herunterladen von Beispiel Datenbanken](downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="631af-112">For instructions, see [Downloading Sample Databases](downloading-sample-databases.md).</span></span> <span data-ttu-id="631af-113">Nachdem Sie die Datenbank heruntergeladen haben, kopieren Sie die Datei northwnd.mdf in den Ordner c:\linqtest2.</span><span class="sxs-lookup"><span data-stu-id="631af-113">After you have downloaded the database, copy the northwnd.mdf file to the c:\linqtest2 folder.</span></span>  
  
- <span data-ttu-id="631af-114">Eine von der Datenbank Northwind generierte Visual Basic-Codedatei.</span><span class="sxs-lookup"><span data-stu-id="631af-114">A Visual Basic code file generated from the Northwind database.</span></span>  
  
     <span data-ttu-id="631af-115">Sie können diese Datei mit dem-objektrelationaler Designer oder dem SQLMetal-Tool generieren.</span><span class="sxs-lookup"><span data-stu-id="631af-115">You can generate this file by using either the Object Relational Designer or the SQLMetal tool.</span></span> <span data-ttu-id="631af-116">Diese exemplarische Vorgehensweise wurde mithilfe des SQLMetal-Tools mit der folgenden Befehlszeile geschrieben:</span><span class="sxs-lookup"><span data-stu-id="631af-116">This walkthrough was written by using the SQLMetal tool with the following command line:</span></span>  
  
     <span data-ttu-id="631af-117">**sqlmetal /code:"c:\linqtest2\northwind.vb" /language:vb "C:\linqtest2\northwnd.mdf" /pluralize**</span><span class="sxs-lookup"><span data-stu-id="631af-117">**sqlmetal /code:"c:\linqtest2\northwind.vb" /language:vb "C:\linqtest2\northwnd.mdf" /pluralize**</span></span>  
  
     <span data-ttu-id="631af-118">Weitere Informationen finden Sie unter [SqlMetal.exe (Tool zur Codegenerierung)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="631af-118">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="overview"></a><span data-ttu-id="631af-119">Übersicht</span><span class="sxs-lookup"><span data-stu-id="631af-119">Overview</span></span>  
 <span data-ttu-id="631af-120">Diese exemplarische Vorgehensweise umfasst sechs Hauptaufgaben:</span><span class="sxs-lookup"><span data-stu-id="631af-120">This walkthrough consists of six main tasks:</span></span>  
  
- <span data-ttu-id="631af-121">Erstellen der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Projekt Mappe in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="631af-121">Creating the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solution in Visual Studio.</span></span>  
  
- <span data-ttu-id="631af-122">Hinzufügen der Datenbank-Codedatei zum Projekt.</span><span class="sxs-lookup"><span data-stu-id="631af-122">Adding the database code file to the project.</span></span>  
  
- <span data-ttu-id="631af-123">Erstellen eines neuen Kundenobjekts.</span><span class="sxs-lookup"><span data-stu-id="631af-123">Creating a new customer object.</span></span>  
  
- <span data-ttu-id="631af-124">Ändern des Kontaktnamens eines Kunden.</span><span class="sxs-lookup"><span data-stu-id="631af-124">Modifying the contact name of a customer.</span></span>  
  
- <span data-ttu-id="631af-125">Löschen einer Bestellung.</span><span class="sxs-lookup"><span data-stu-id="631af-125">Deleting an order.</span></span>  
  
- <span data-ttu-id="631af-126">Übergeben dieser Änderungen an der Datenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="631af-126">Submitting these changes to the Northwind database.</span></span>  
  
## <a name="creating-a-linq-to-sql-solution"></a><span data-ttu-id="631af-127">Erstellen einer LINQ to SQL-Lösung</span><span class="sxs-lookup"><span data-stu-id="631af-127">Creating a LINQ to SQL Solution</span></span>  
 <span data-ttu-id="631af-128">In dieser ersten Aufgabe erstellen Sie eine Visual Studio-Projekt Mappe, die die erforderlichen Verweise zum Erstellen und Ausführen [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] eines Projekts enthält.</span><span class="sxs-lookup"><span data-stu-id="631af-128">In this first task, you create a Visual Studio solution that contains the necessary references to build and run a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project.</span></span>  
  
#### <a name="to-create-a-linq-to-sql-solution"></a><span data-ttu-id="631af-129">So erstellen Sie eine LINQ to SQL-Lösung</span><span class="sxs-lookup"><span data-stu-id="631af-129">To create a LINQ to SQL solution</span></span>  
  
1. <span data-ttu-id="631af-130">Klicken Sie in Visual Studio im Menü **Datei** auf **Neues Projekt**.</span><span class="sxs-lookup"><span data-stu-id="631af-130">On the Visual Studio **File** menu, click **New Project**.</span></span>  
  
2. <span data-ttu-id="631af-131">Klicken Sie im Bereich **Projekttypen** im Dialogfeld **Neues Projekt** auf **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="631af-131">In the **Project types** pane in the **New Project** dialog box, click **Visual Basic**.</span></span>  
  
3. <span data-ttu-id="631af-132">Klicken Sie im Bereich **Vorlagen** auf **Konsolenanwendung**.</span><span class="sxs-lookup"><span data-stu-id="631af-132">In the **Templates** pane, click **Console Application**.</span></span>  
  
4. <span data-ttu-id="631af-133">Geben Sie im Feld **Name den Namen** **LinqDataManipulationApp**ein.</span><span class="sxs-lookup"><span data-stu-id="631af-133">In the **Name** box, type **LinqDataManipulationApp**.</span></span>  
  
5. <span data-ttu-id="631af-134">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="631af-134">Click **OK**.</span></span>  
  
## <a name="adding-linq-references-and-directives"></a><span data-ttu-id="631af-135">Hinzufügen von LINQ-Verweisen und Anweisungen</span><span class="sxs-lookup"><span data-stu-id="631af-135">Adding LINQ References and Directives</span></span>  
 <span data-ttu-id="631af-136">Diese exemplarische Vorgehensweise verwendet Assemblys, die im Projekt u. U. nicht standardmäßig installiert sind.</span><span class="sxs-lookup"><span data-stu-id="631af-136">This walkthrough uses assemblies that might not be installed by default in your project.</span></span> <span data-ttu-id="631af-137">Wenn `System.Data.Linq` in Ihrem Projekt nicht als Verweis aufgeführt ist (Klicken Sie in **Projektmappen-Explorer** auf **alle Dateien anzeigen** , und erweitern Sie den Knoten **Verweise** ), fügen Sie ihn hinzu, wie in den folgenden Schritten erläutert.</span><span class="sxs-lookup"><span data-stu-id="631af-137">If `System.Data.Linq` is not listed as a reference in your project (click **Show All Files** in **Solution Explorer** and expand the **References** node), add it, as explained in the following steps.</span></span>  
  
#### <a name="to-add-systemdatalinq"></a><span data-ttu-id="631af-138">So fügen Sie System.Data.Linq hinzu</span><span class="sxs-lookup"><span data-stu-id="631af-138">To add System.Data.Linq</span></span>  
  
1. <span data-ttu-id="631af-139">Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf **Verweise**, und klicken Sie dann auf **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="631af-139">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>  
  
2. <span data-ttu-id="631af-140">Klicken Sie im Dialogfeld **Verweis hinzufügen** auf **.net**, klicken Sie auf die Assembly System. Data. Linq, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="631af-140">In the **Add Reference** dialog box, click **.NET**, click the System.Data.Linq assembly, and then click **OK**.</span></span>  
  
     <span data-ttu-id="631af-141">Dem Projekt wird die Assembly hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="631af-141">The assembly is added to the project.</span></span>  
  
3. <span data-ttu-id="631af-142">Fügen Sie im Code-Editor die folgenden Direktiven oberhalb von **Module1**hinzu:</span><span class="sxs-lookup"><span data-stu-id="631af-142">In the code editor, add the following directives above **Module1**:</span></span>  
  
     [!code-vb[DLinqWalk3VB#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#1)]  
  
## <a name="adding-the-northwind-code-file-to-the-project"></a><span data-ttu-id="631af-143">Hinzufügen der Northwind-Codedatei zum Projekt.</span><span class="sxs-lookup"><span data-stu-id="631af-143">Adding the Northwind Code File to the Project</span></span>  
 <span data-ttu-id="631af-144">Bei diesen Schritten wird davon ausgegangen, dass Sie das SQLMetal-Tool zum Erzeugen einer Codedatei aus der Beispieldatenbank Northwind verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="631af-144">These steps assume that you have used the SQLMetal tool to generate a code file from the Northwind sample database.</span></span> <span data-ttu-id="631af-145">Weitere Informationen finden Sie im Abschnitt zu Voraussetzungen weiter oben in dieser exemplarischen Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="631af-145">For more information, see the Prerequisites section earlier in this walkthrough.</span></span>  
  
#### <a name="to-add-the-northwind-code-file-to-the-project"></a><span data-ttu-id="631af-146">So fügen Sie die Northwind-Codedatei dem Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="631af-146">To add the northwind code file to the project</span></span>  
  
1. <span data-ttu-id="631af-147">Klicken Sie im Menü **Projekt** auf **Vorhandenes Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="631af-147">On the **Project** menu, click **Add Existing Item**.</span></span>  
  
2. <span data-ttu-id="631af-148">Navigieren Sie im Dialogfeld **Vorhandenes Element hinzufügen** zu c:\linqtest2\northwind.vb, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="631af-148">In the **Add Existing Item** dialog box, navigate to c:\linqtest2\northwind.vb, and then click **Add**.</span></span>  
  
     <span data-ttu-id="631af-149">Die Datei northwind.vb wird dem Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="631af-149">The northwind.vb file is added to the project.</span></span>  
  
## <a name="setting-up-the-database-connection"></a><span data-ttu-id="631af-150">Einrichten der Datenverbindungen</span><span class="sxs-lookup"><span data-stu-id="631af-150">Setting Up the Database Connection</span></span>  
 <span data-ttu-id="631af-151">Testen Sie zuerst die Verbindung zur Datenbank.</span><span class="sxs-lookup"><span data-stu-id="631af-151">First, test your connection to the database.</span></span> <span data-ttu-id="631af-152">Beachten Sie vor allem, dass der Name der Datenbank, Northwnd, kein i-Zeichen hat.</span><span class="sxs-lookup"><span data-stu-id="631af-152">Note especially that the name of the database, Northwnd, has no i character.</span></span> <span data-ttu-id="631af-153">Sollten im nächsten Schritt Fehler auftreten, prüfen Sie in der Datei northwind.vb die Schreibweise der partiellen Klasse Northwind.</span><span class="sxs-lookup"><span data-stu-id="631af-153">If you generate errors in the next steps, review the northwind.vb file to determine how the Northwind partial class is spelled.</span></span>  
  
#### <a name="to-set-up-and-test-the-database-connection"></a><span data-ttu-id="631af-154">So richten Sie die Datenbankverbindung ein und testen diese</span><span class="sxs-lookup"><span data-stu-id="631af-154">To set up and test the database connection</span></span>  
  
1. <span data-ttu-id="631af-155">Geben Sie den folgenden Code in `Sub Main` ein, oder fügen Sie ihn ein:</span><span class="sxs-lookup"><span data-stu-id="631af-155">Type or paste the following code into `Sub Main`:</span></span>  
  
     [!code-vb[DLinqWalk3VB#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#2)]  
  
2. <span data-ttu-id="631af-156">Drücken Sie die Taste F5, um die Anwendung an diesem Punkt zu testen.</span><span class="sxs-lookup"><span data-stu-id="631af-156">Press F5 to test the application at this point.</span></span>  
  
     <span data-ttu-id="631af-157">Ein **Konsolen** Fenster wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="631af-157">A **Console** window opens.</span></span>  
  
     <span data-ttu-id="631af-158">Schließen Sie die Anwendung, indem Sie im **Konsolen** Fenster die EINGABETASTE drücken, oder klicken Sie im Visual Studio-Menü **Debuggen** auf **Debuggen beenden** .</span><span class="sxs-lookup"><span data-stu-id="631af-158">Close the application by pressing Enter in the **Console** window, or by clicking **Stop Debugging** on the Visual Studio **Debug** menu.</span></span>  
  
## <a name="creating-a-new-entity"></a><span data-ttu-id="631af-159">Erstellen einer neuen Entität</span><span class="sxs-lookup"><span data-stu-id="631af-159">Creating a New Entity</span></span>  
 <span data-ttu-id="631af-160">Eine neue Entität zu erstellen, ist einfach.</span><span class="sxs-lookup"><span data-stu-id="631af-160">Creating a new entity is straightforward.</span></span> <span data-ttu-id="631af-161">Sie können Objekte (z. B. `Customer`) erstellen, indem Sie das `New`-Schlüsselwort verwenden.</span><span class="sxs-lookup"><span data-stu-id="631af-161">You can create objects (such as `Customer`) by using the `New` keyword.</span></span>  
  
 <span data-ttu-id="631af-162">In diesem und den folgenden Abschnitten nehmen Sie Änderungen nur am lokalen Cache vor.</span><span class="sxs-lookup"><span data-stu-id="631af-162">In this and the following sections, you are making changes only to the local cache.</span></span> <span data-ttu-id="631af-163">Es werden keine Änderungen an die Datenbank gesendet, bis Sie zum Ende dieser exemplarischen Vorgehensweise <xref:System.Data.Linq.DataContext.SubmitChanges%2A> aufrufen.</span><span class="sxs-lookup"><span data-stu-id="631af-163">No changes are sent to the database until you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> toward the end of this walkthrough.</span></span>  
  
#### <a name="to-add-a-new-customer-entity-object"></a><span data-ttu-id="631af-164">So fügen Sie ein neues Kundenentitätsobjekt hinzu</span><span class="sxs-lookup"><span data-stu-id="631af-164">To add a new Customer entity object</span></span>  
  
1. <span data-ttu-id="631af-165">Erstellen Sie einen neuen `Customer`, indem Sie den folgenden Code vor `Console.ReadLine` in `Sub Main` hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="631af-165">Create a new `Customer` by adding the following code before `Console.ReadLine` in `Sub Main`:</span></span>  
  
     [!code-vb[DLinqWalk3VB#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#3)]  
  
2. <span data-ttu-id="631af-166">Drücken Sie die Taste F5, um die Lösung zu Debuggen.</span><span class="sxs-lookup"><span data-stu-id="631af-166">Press F5 to debug the solution.</span></span>  
  
     <span data-ttu-id="631af-167">Im Konsolenfenster werden die folgenden Ergebnisse angezeigt:</span><span class="sxs-lookup"><span data-stu-id="631af-167">The results that are shown in the console window are as follows:</span></span>  
  
     `Customers matching CA before insert:`  
  
     `Customer ID: CACTU`  
  
     `Customer ID: RICAR`  
  
     <span data-ttu-id="631af-168">Beachten Sie, dass die neue Zeile nicht in den Ergebnissen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="631af-168">Note that the new row does not appear in the results.</span></span> <span data-ttu-id="631af-169">Die neuen Daten wurden noch nicht an die Datenbank übergeben.</span><span class="sxs-lookup"><span data-stu-id="631af-169">The new data has not yet been submitted to the database.</span></span>  
  
3. <span data-ttu-id="631af-170">Drücken Sie im **Konsolen** Fenster die EINGABETASTE, um das Debugging zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="631af-170">Press Enter in the **Console** window to stop debugging.</span></span>  
  
## <a name="updating-an-entity"></a><span data-ttu-id="631af-171">Aktualisieren einer Entität</span><span class="sxs-lookup"><span data-stu-id="631af-171">Updating an Entity</span></span>  
 <span data-ttu-id="631af-172">In den folgenden Schritten rufen Sie ein `Customer`-Objekt ab und ändern eine seiner Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="631af-172">In the following steps, you will retrieve a `Customer` object and modify one of its properties.</span></span>  
  
#### <a name="to-change-the-name-of-a-customer"></a><span data-ttu-id="631af-173">So ändern Sie den Namen eines Kunden</span><span class="sxs-lookup"><span data-stu-id="631af-173">To change the name of a Customer</span></span>  
  
- <span data-ttu-id="631af-174">Fügen Sie den folgenden Code oberhalb von `Console.ReadLine()` ein:</span><span class="sxs-lookup"><span data-stu-id="631af-174">Add the following code above `Console.ReadLine()`:</span></span>  
  
     [!code-vb[DLinqWalk3VB#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#4)]  
  
## <a name="deleting-an-entity"></a><span data-ttu-id="631af-175">Löschen einer Entität</span><span class="sxs-lookup"><span data-stu-id="631af-175">Deleting an Entity</span></span>  
 <span data-ttu-id="631af-176">Unter Verwendung des gleichen Kundenobjekts können Sie die erste Bestellung löschen.</span><span class="sxs-lookup"><span data-stu-id="631af-176">Using the same customer object, you can delete the first order.</span></span>  
  
 <span data-ttu-id="631af-177">Der folgende Code zeigt, wie Beziehungen zwischen Zeilen getrennt werden und wie eine Zeile aus der Datenbank Northwind gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="631af-177">The following code demonstrates how to sever relationships between rows, and how to delete a row from the database.</span></span>  
  
#### <a name="to-delete-a-row"></a><span data-ttu-id="631af-178">So löschen Sie eine Zeile</span><span class="sxs-lookup"><span data-stu-id="631af-178">To delete a row</span></span>  
  
- <span data-ttu-id="631af-179">Fügen Sie den folgenden Code genau oberhalb von `Console.ReadLine()` ein.</span><span class="sxs-lookup"><span data-stu-id="631af-179">Add the following code just above `Console.ReadLine()`:</span></span>  
  
     [!code-vb[DLinqWalk3VB#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#5)]  
  
## <a name="submitting-changes-to-the-database"></a><span data-ttu-id="631af-180">Übergeben von Änderungen an die Datenbank</span><span class="sxs-lookup"><span data-stu-id="631af-180">Submitting Changes to the Database</span></span>  
 <span data-ttu-id="631af-181">Der letzte Schritt beim Erstellen, Aktualisieren und Löschen von Objekten besteht in der eigentlichen Übergabe der Änderungen an die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="631af-181">The final step required for creating, updating, and deleting objects is to actually submit the changes to the database.</span></span> <span data-ttu-id="631af-182">Ohne diesen Schritt sind die Änderungen nur lokal und werden nicht in Abfrageergebnissen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="631af-182">Without this step, your changes are only local and will not appear in query results.</span></span>  
  
#### <a name="to-submit-changes-to-the-database"></a><span data-ttu-id="631af-183">So übergeben Sie die Änderungen an die Datenbank</span><span class="sxs-lookup"><span data-stu-id="631af-183">To submit changes to the database</span></span>  
  
1. <span data-ttu-id="631af-184">Fügen Sie den folgenden Code genau oberhalb von `Console.ReadLine` ein:</span><span class="sxs-lookup"><span data-stu-id="631af-184">Insert the following code just above `Console.ReadLine`:</span></span>  
  
     [!code-vb[DLinqWalk3VB#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#6)]  
  
2. <span data-ttu-id="631af-185">Fügen Sie den folgenden Code (nach `SubmitChanges`) ein, um den Vorher-Nachher-Effekt der Änderungsübergabe zu zeigen:</span><span class="sxs-lookup"><span data-stu-id="631af-185">Insert the following code (after `SubmitChanges`) to show the before and after effects of submitting the changes:</span></span>  
  
     [!code-vb[DLinqWalk3VB#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#7)]  
  
3. <span data-ttu-id="631af-186">Drücken Sie die Taste F5, um die Lösung zu Debuggen.</span><span class="sxs-lookup"><span data-stu-id="631af-186">Press F5 to debug the solution.</span></span>  
  
     <span data-ttu-id="631af-187">Das Konsolenfenster wird wie folgt angezeigt:</span><span class="sxs-lookup"><span data-stu-id="631af-187">The console window appears as follows:</span></span>  
  
    ```  
    Customers matching CA before update:  
    Customer ID: CACTU  
    Customer ID: RICAR  
  
    The Order Detail to be deleted is: OrderID = 10643  
  
    Customers matching CA after update:  
    Customer ID: A3VCA  
    Customer ID: CACTU  
    Customer ID: RICAR  
    ```  
  
4. <span data-ttu-id="631af-188">Drücken Sie im **Konsolen** Fenster die EINGABETASTE, um das Debugging zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="631af-188">Press Enter in the **Console** window to stop debugging.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="631af-189">Wenn Sie den neuen Kunden durch Übergeben der Änderungen hinzugefügt haben, können Sie diese Lösung nicht einfach wieder ausführen, da Sie den gleichen Kunden nicht erneut hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="631af-189">After you have added the new customer by submitting the changes, you cannot execute this solution again as is, because you cannot add the same customer again as is.</span></span> <span data-ttu-id="631af-190">Um die Lösung erneut auszuführen, ändern Sie den Wert der hinzuzufügenden Kunden-ID.</span><span class="sxs-lookup"><span data-stu-id="631af-190">To execute the solution again, change the value of the customer ID to be added.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="631af-191">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="631af-191">See also</span></span>

- [<span data-ttu-id="631af-192">Lernen durch exemplarische Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="631af-192">Learning by Walkthroughs</span></span>](learning-by-walkthroughs.md)
