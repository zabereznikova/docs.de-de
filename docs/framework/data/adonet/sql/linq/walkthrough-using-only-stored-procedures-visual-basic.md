---
title: 'Exemplarische Vorgehensweise: Ausschließliches Verwenden von gespeicherten Prozeduren (Visual Basic)'
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: 5a736a30-ba66-4adb-b87c-57d19476e862
ms.openlocfilehash: 1527e3b4b614d4e700ae0c2c0fc555e14c7bc8d2
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59314827"
---
# <a name="walkthrough-using-only-stored-procedures-visual-basic"></a><span data-ttu-id="4c764-102">Exemplarische Vorgehensweise: Ausschließliches Verwenden von gespeicherten Prozeduren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4c764-102">Walkthrough: Using Only Stored Procedures (Visual Basic)</span></span>
<span data-ttu-id="4c764-103">Diese exemplarische Vorgehensweise stellt ein grundlegendes End-to-End-[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Szenario für den Datenzugriff mithilfe von gespeicherten Prozeduren bereit.</span><span class="sxs-lookup"><span data-stu-id="4c764-103">This walkthrough provides a basic end-to-end [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] scenario for accessing data by using stored procedures only.</span></span> <span data-ttu-id="4c764-104">Dieser Ansatz wird oft von Datenbankadministratoren verwendet, um den Zugriff auf den Datenspeicher einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="4c764-104">This approach is often used by database administrators to limit how the datastore is accessed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4c764-105">Sie können gespeicherte Prozeduren außerdem in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Anwendungen verwenden, um das Standardverhalten zu überschreiben. Dies gilt vor allem für die Prozesse `Create`, `Update` und `Delete`.</span><span class="sxs-lookup"><span data-stu-id="4c764-105">You can also use stored procedures in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications to override default behavior, especially for `Create`, `Update`, and `Delete` processes.</span></span> <span data-ttu-id="4c764-106">Weitere Informationen finden Sie unter [Anpassen von INSERT-, Update- und Delete-Operationen](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="4c764-106">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>  
  
 <span data-ttu-id="4c764-107">Für die Zwecke dieser exemplarischen Vorgehensweise verwenden Sie zwei Methoden, die von gespeicherten Prozeduren in der Northwind-Beispieldatenbank zugeordnet wurden: CustOrdersDetail und CustOrderHist.</span><span class="sxs-lookup"><span data-stu-id="4c764-107">For purposes of this walkthrough, you will use two methods that have been mapped to stored procedures in the Northwind sample database: CustOrdersDetail and CustOrderHist.</span></span> <span data-ttu-id="4c764-108">Die Zuordnung tritt auf, wenn Sie das Befehlszeilentool SqlMetal verwenden, generiert Visual Basic-Datei ausführen.</span><span class="sxs-lookup"><span data-stu-id="4c764-108">The mapping occurs when you run the SqlMetal command-line tool to generate a Visual Basic file.</span></span> <span data-ttu-id="4c764-109">Weitere Informationen finden Sie im Abschnitt zu Voraussetzungen weiter unten in dieser exemplarischen Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="4c764-109">For more information, see the Prerequisites section later in this walkthrough.</span></span>  
  
 <span data-ttu-id="4c764-110">Diese exemplarische Vorgehensweise basiert nicht auf [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c764-110">This walkthrough does not rely on the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)].</span></span> <span data-ttu-id="4c764-111">Entwickler, die mit Visual Studio können auch die [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] Funktionalität einer gespeicherten Prozedur zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="4c764-111">Developers using Visual Studio can also use the [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] to implement stored procedure functionality.</span></span> <span data-ttu-id="4c764-112">Finden Sie unter [LINQ to SQL-Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span><span class="sxs-lookup"><span data-stu-id="4c764-112">See [LINQ to SQL Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="4c764-113">Diese exemplarische Vorgehensweise wurde mithilfe von Visual Basic-Entwicklungseinstellungen geschrieben.</span><span class="sxs-lookup"><span data-stu-id="4c764-113">This walkthrough was written by using Visual Basic Development Settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4c764-114">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="4c764-114">Prerequisites</span></span>  
 <span data-ttu-id="4c764-115">Für diese exemplarische Vorgehensweise wird Folgendes vorausgesetzt:</span><span class="sxs-lookup"><span data-stu-id="4c764-115">This walkthrough requires the following:</span></span>  
  
-   <span data-ttu-id="4c764-116">Diese exemplarische Vorgehensweise verwendet einen dedizierten Ordner ("c:\linqtest3") als Speicherort für Dateien.</span><span class="sxs-lookup"><span data-stu-id="4c764-116">This walkthrough uses a dedicated folder ("c:\linqtest3") to hold files.</span></span> <span data-ttu-id="4c764-117">Erstellen Sie diesen Ordner, bevor Sie die exemplarische Vorgehensweise starten.</span><span class="sxs-lookup"><span data-stu-id="4c764-117">Create this folder before you begin the walkthrough.</span></span>  
  
-   <span data-ttu-id="4c764-118">Die Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="4c764-118">The Northwind sample database.</span></span>  
  
     <span data-ttu-id="4c764-119">Befindet sich diese Datenbank nicht auf Ihrem Entwicklungscomputer, können Sie diese von der Microsoft Downloadsite herunterladen.</span><span class="sxs-lookup"><span data-stu-id="4c764-119">If you do not have this database on your development computer, you can download it from the Microsoft download site.</span></span> <span data-ttu-id="4c764-120">Anweisungen hierzu finden Sie unter [Herunterladen von Beispieldatenbanken](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="4c764-120">For instructions, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span> <span data-ttu-id="4c764-121">Nachdem Sie die Datenbank heruntergeladen haben, kopieren Sie die Datei northwnd.mdf in den Ordner c:\linqtest3.</span><span class="sxs-lookup"><span data-stu-id="4c764-121">After you have downloaded the database, copy the northwnd.mdf file to the c:\linqtest3 folder.</span></span>  
  
-   <span data-ttu-id="4c764-122">Eine von der Datenbank Northwind generierte Visual Basic-Codedatei.</span><span class="sxs-lookup"><span data-stu-id="4c764-122">A Visual Basic code file generated from the Northwind database.</span></span>  
  
     <span data-ttu-id="4c764-123">Diese exemplarische Vorgehensweise wurde mithilfe des SQLMetal-Tools mit der folgenden Befehlszeile geschrieben:</span><span class="sxs-lookup"><span data-stu-id="4c764-123">This walkthrough was written by using the SqlMetal tool with the following command line:</span></span>  
  
     **<span data-ttu-id="4c764-124">sqlmetal /code:"c:\linqtest3\northwind.vb" /language:vb "c:\linqtest3\northwnd.mdf" /sprocs /functions /pluralize</span><span class="sxs-lookup"><span data-stu-id="4c764-124">sqlmetal /code:"c:\linqtest3\northwind.vb" /language:vb "c:\linqtest3\northwnd.mdf" /sprocs /functions /pluralize</span></span>**  
  
     <span data-ttu-id="4c764-125">Weitere Informationen finden Sie unter [SqlMetal.exe (Tool zur Codegenerierung)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="4c764-125">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="overview"></a><span data-ttu-id="4c764-126">Übersicht</span><span class="sxs-lookup"><span data-stu-id="4c764-126">Overview</span></span>  
 <span data-ttu-id="4c764-127">Diese exemplarische Vorgehensweise umfasst sechs Hauptaufgaben:</span><span class="sxs-lookup"><span data-stu-id="4c764-127">This walkthrough consists of six main tasks:</span></span>  
  
-   <span data-ttu-id="4c764-128">Einrichten der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Projektmappe in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4c764-128">Setting up the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solution in Visual Studio.</span></span>  
  
-   <span data-ttu-id="4c764-129">Hinzufügen der System.Data.Linq-Assembly zum Projekt</span><span class="sxs-lookup"><span data-stu-id="4c764-129">Adding the System.Data.Linq assembly to the project.</span></span>  
  
-   <span data-ttu-id="4c764-130">Hinzufügen der Datenbank-Codedatei zum Projekt.</span><span class="sxs-lookup"><span data-stu-id="4c764-130">Adding the database code file to the project.</span></span>  
  
-   <span data-ttu-id="4c764-131">Erstellen einer Verbindung mit der Datenbank</span><span class="sxs-lookup"><span data-stu-id="4c764-131">Creating a connection to the database.</span></span>  
  
-   <span data-ttu-id="4c764-132">Einrichten der Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="4c764-132">Setting up the user interface.</span></span>  
  
-   <span data-ttu-id="4c764-133">Ausführen und Testen der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="4c764-133">Running and testing the application.</span></span>  
  
## <a name="creating-a-linq-to-sql-solution"></a><span data-ttu-id="4c764-134">Erstellen einer LINQ to SQL-Lösung</span><span class="sxs-lookup"><span data-stu-id="4c764-134">Creating a LINQ to SQL Solution</span></span>  
 <span data-ttu-id="4c764-135">In dieser ersten Aufgabe erstellen Sie eine Visual Studio-Projektmappe, die die erforderlichen Verweise zur Erstellung und Ausführung enthält eine [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Projekt.</span><span class="sxs-lookup"><span data-stu-id="4c764-135">In this first task, you create a Visual Studio solution that contains the necessary references to build and run a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project.</span></span>  
  
#### <a name="to-create-a-linq-to-sql-solution"></a><span data-ttu-id="4c764-136">So erstellen Sie eine LINQ to SQL-Lösung</span><span class="sxs-lookup"><span data-stu-id="4c764-136">To create a LINQ to SQL solution</span></span>  
  
1. <span data-ttu-id="4c764-137">Klicken Sie in Visual Studio im Menü **Datei** auf **Neues Projekt**.</span><span class="sxs-lookup"><span data-stu-id="4c764-137">On the Visual Studio **File** menu, click **New Project**.</span></span>  
  
2. <span data-ttu-id="4c764-138">Erweitern Sie im Bereich **Projekttypen** des Dialogfelds **Neues Projekt** den Eintrag **Visual Basic**, und klicken Sie dann auf **Windows**.</span><span class="sxs-lookup"><span data-stu-id="4c764-138">In the **Project types** pane in the **New Project** dialog box, expand **Visual Basic**, and then click **Windows**.</span></span>  
  
3. <span data-ttu-id="4c764-139">Klicken Sie im Bereich **Vorlagen** auf **Windows Forms-Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="4c764-139">In the **Templates** pane, click **Windows Forms Application**.</span></span>  
  
4. <span data-ttu-id="4c764-140">In der **Namen** geben **SprocOnlyApp**.</span><span class="sxs-lookup"><span data-stu-id="4c764-140">In the **Name** box, type **SprocOnlyApp**.</span></span>  
  
5. <span data-ttu-id="4c764-141">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c764-141">Click **OK**.</span></span>  
  
     <span data-ttu-id="4c764-142">Der Windows Forms Designer wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="4c764-142">The Windows Forms Designer opens.</span></span>  
  
## <a name="adding-the-linq-to-sql-assembly-reference"></a><span data-ttu-id="4c764-143">Hinzufügen des LINQ to SQL-Assemblyverweises</span><span class="sxs-lookup"><span data-stu-id="4c764-143">Adding the LINQ to SQL Assembly Reference</span></span>  
 <span data-ttu-id="4c764-144">Die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Assembly ist nicht in der Standardvorlage für Windows Forms-Anwendungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="4c764-144">The [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] assembly is not included in the standard Windows Forms Application template.</span></span> <span data-ttu-id="4c764-145">Sie müssen die Assembly selbst hinzufügen. Siehe hierzu die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="4c764-145">You will have to add the assembly yourself, as explained in the following steps:</span></span>  
  
#### <a name="to-add-systemdatalinqdll"></a><span data-ttu-id="4c764-146">So fügen Sie die Datei System.Data.Linq.dll hinzu</span><span class="sxs-lookup"><span data-stu-id="4c764-146">To add System.Data.Linq.dll</span></span>  
  
1. <span data-ttu-id="4c764-147">In **Projektmappen-Explorer**, klicken Sie auf **alle Dateien anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="4c764-147">In **Solution Explorer**, click **Show All Files**.</span></span>  
  
2. <span data-ttu-id="4c764-148">In **Projektmappen-Explorer**, mit der rechten Maustaste **Verweise**, und klicken Sie dann auf **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="4c764-148">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>  
  
3. <span data-ttu-id="4c764-149">In der **Verweis hinzufügen** Dialogfeld klicken Sie auf **.NET**, klicken Sie auf die System.Data.Linq-Assembly, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c764-149">In the **Add Reference** dialog box, click **.NET**, click the System.Data.Linq assembly, and then click **OK**.</span></span>  
  
     <span data-ttu-id="4c764-150">Dem Projekt wird die Assembly hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="4c764-150">The assembly is added to the project.</span></span>  
  
## <a name="adding-the-northwind-code-file-to-the-project"></a><span data-ttu-id="4c764-151">Hinzufügen der Northwind-Codedatei zum Projekt.</span><span class="sxs-lookup"><span data-stu-id="4c764-151">Adding the Northwind Code File to the Project</span></span>  
 <span data-ttu-id="4c764-152">Bei diesem Schritt wird davon ausgegangen, dass Sie das SQLMetal-Tool zum Erzeugen einer Codedatei aus der Beispieldatenbank Northwind verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="4c764-152">This step assumes that you have used the SqlMetal tool to generate a code file from the Northwind sample database.</span></span> <span data-ttu-id="4c764-153">Weitere Informationen finden Sie im Abschnitt zu Voraussetzungen weiter oben in dieser exemplarischen Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="4c764-153">For more information, see the Prerequisites section earlier in this walkthrough.</span></span>  
  
#### <a name="to-add-the-northwind-code-file-to-the-project"></a><span data-ttu-id="4c764-154">So fügen Sie die Northwind-Codedatei dem Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="4c764-154">To add the northwind code file to the project</span></span>  
  
1. <span data-ttu-id="4c764-155">Auf der **Projekt** Menü klicken Sie auf **vorhandenes Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="4c764-155">On the **Project** menu, click **Add Existing Item**.</span></span>  
  
2. <span data-ttu-id="4c764-156">In der **vorhandenes Element hinzufügen** Dialogfeld zu c:\linqtest3\northwind.vb verschieben, und klicken Sie dann auf **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="4c764-156">In the **Add Existing Item** dialog box, move to c:\linqtest3\northwind.vb, and then click **Add**.</span></span>  
  
     <span data-ttu-id="4c764-157">Die Datei northwind.vb wird dem Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="4c764-157">The northwind.vb file is added to the project.</span></span>  
  
## <a name="creating-a-database-connection"></a><span data-ttu-id="4c764-158">Erstellen von Datenbankverbindungen</span><span class="sxs-lookup"><span data-stu-id="4c764-158">Creating a Database Connection</span></span>  
 <span data-ttu-id="4c764-159">In diesem Schritt definieren Sie die Verbindung zur Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="4c764-159">In this step, you define the connection to the Northwind sample database.</span></span> <span data-ttu-id="4c764-160">Diese exemplarische Vorgehensweise verwendet "c:\linqtest3\northwnd.mdf" als Pfad.</span><span class="sxs-lookup"><span data-stu-id="4c764-160">This walkthrough uses "c:\linqtest3\northwnd.mdf" as the path.</span></span>  
  
#### <a name="to-create-the-database-connection"></a><span data-ttu-id="4c764-161">So erstellen Sie die Datenbankverbindung</span><span class="sxs-lookup"><span data-stu-id="4c764-161">To create the database connection</span></span>  
  
1. <span data-ttu-id="4c764-162">In **Projektmappen-Explorer**, mit der rechten Maustaste **Form1.vb**, und klicken Sie dann auf **Ansichtscode**.</span><span class="sxs-lookup"><span data-stu-id="4c764-162">In **Solution Explorer**, right-click **Form1.vb**, and then click **View Code**.</span></span>  
  
     `Class Form1` <span data-ttu-id="4c764-163">wird im Code-Editor angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4c764-163">appears in the code editor.</span></span>  
  
2. <span data-ttu-id="4c764-164">Geben Sie den folgenden Code in den `Form1`-Code-Block ein.</span><span class="sxs-lookup"><span data-stu-id="4c764-164">Type the following code into the `Form1` code block:</span></span>  
  
     [!code-vb[DLinqWalk4VB#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk4VB/vb/Form1.vb#1)]  
  
## <a name="setting-up-the-user-interface"></a><span data-ttu-id="4c764-165">Einrichten der Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="4c764-165">Setting up the User Interface</span></span>  
 <span data-ttu-id="4c764-166">In dieser Aufgabe erstellen Sie eine Benutzeroberfläche, sodass Benutzer durch Ausführen gespeicherter Prozeduren auf die Daten in der Datenbank zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="4c764-166">In this task you create an interface so that users can execute stored procedures to access data in the database.</span></span> <span data-ttu-id="4c764-167">In den von Ihnen hier entwickelten Anwendungen können Benutzer nur mithilfe der in der Anwendung eingebetteten gespeicherten Prozeduren auf die Daten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="4c764-167">In the application that you are developing with this walkthrough, users can access data in the database only by using the stored procedures embedded in the application.</span></span>  
  
#### <a name="to-set-up-the-user-interface"></a><span data-ttu-id="4c764-168">So richten Sie die Benutzeroberfläche ein</span><span class="sxs-lookup"><span data-stu-id="4c764-168">To set up the user interface</span></span>  
  
1. <span data-ttu-id="4c764-169">Wechseln Sie zurück zur der Windows Forms-Designer (**Form1.vb]**).</span><span class="sxs-lookup"><span data-stu-id="4c764-169">Return to the Windows Forms Designer (**Form1.vb[Design]**).</span></span>  
  
2. <span data-ttu-id="4c764-170">Klicken Sie im Menü **Ansicht** auf **Toolbox**.</span><span class="sxs-lookup"><span data-stu-id="4c764-170">On the **View** menu, click **Toolbox**.</span></span>  
  
     <span data-ttu-id="4c764-171">Die Toolbox wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="4c764-171">The toolbox opens.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4c764-172">Klicken Sie auf die **automatisch im Hintergrund** PIN, die Toolbox geöffnet zu lassen, während der folgenden Schritte in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="4c764-172">Click the **AutoHide** pushpin to keep the toolbox open while you perform the remaining steps in this section.</span></span>  
  
3. <span data-ttu-id="4c764-173">Ziehen Sie zwei Schaltflächen, zwei Textfelder und zwei Bezeichnungen aus der Toolbox auf **Form1**.</span><span class="sxs-lookup"><span data-stu-id="4c764-173">Drag two buttons, two text boxes, and two labels from the toolbox onto **Form1**.</span></span>  
  
     <span data-ttu-id="4c764-174">Ordnen Sie die Steuerelemente wie in der Abbildung an.</span><span class="sxs-lookup"><span data-stu-id="4c764-174">Arrange the controls as in the accompanying illustration.</span></span> <span data-ttu-id="4c764-175">Erweitern Sie **Form1** , damit die Steuerelemente platziert.</span><span class="sxs-lookup"><span data-stu-id="4c764-175">Expand **Form1** so that the controls fit easily.</span></span>  
  
4. <span data-ttu-id="4c764-176">Mit der rechten Maustaste **Label1**, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="4c764-176">Right-click **Label1**, and then click **Properties**.</span></span>  
  
5. <span data-ttu-id="4c764-177">Ändern der **Text** Eigenschaft **Label1** zu **Enter OrderID:**.</span><span class="sxs-lookup"><span data-stu-id="4c764-177">Change the **Text** property from **Label1** to **Enter OrderID:**.</span></span>  
  
6. <span data-ttu-id="4c764-178">Für die gleiche Weise **Label2**, ändern Sie die **Text** Eigenschaft aus **Label2** zu **Enter CustomerID:**.</span><span class="sxs-lookup"><span data-stu-id="4c764-178">In the same way for **Label2**, change the **Text** property from **Label2** to **Enter CustomerID:**.</span></span>  
  
7. <span data-ttu-id="4c764-179">Ändern Sie in die gleiche Weise die **Text** -Eigenschaft für **"Button1"** zu **Bestelldetails**.</span><span class="sxs-lookup"><span data-stu-id="4c764-179">In the same way, change the **Text** property for **Button1** to **Order Details**.</span></span>  
  
8. <span data-ttu-id="4c764-180">Ändern der **Text** -Eigenschaft für **Button2** zu **Bestellverlauf**.</span><span class="sxs-lookup"><span data-stu-id="4c764-180">Change the **Text** property for **Button2** to **Order History**.</span></span>  
  
     <span data-ttu-id="4c764-181">Erweitern Sie die Schaltflächen-Steuerelemente, damit der gesamte Text sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="4c764-181">Widen the button controls so that all the text is visible.</span></span>  
  
#### <a name="to-handle-button-clicks"></a><span data-ttu-id="4c764-182">Verarbeitung von Mausklicks auf die Schaltflächen</span><span class="sxs-lookup"><span data-stu-id="4c764-182">To handle button clicks</span></span>  
  
1. <span data-ttu-id="4c764-183">Doppelklicken Sie auf **Bestelldetails** auf **Form1** zum Erstellen der `Button1` -Ereignishandler und den Codeeditor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="4c764-183">Double-click **Order Details** on **Form1** to create the `Button1` event handler and open the code editor.</span></span>  
  
2. <span data-ttu-id="4c764-184">Geben Sie den folgenden Code in den `Button1`-Ereignishandler ein.</span><span class="sxs-lookup"><span data-stu-id="4c764-184">Type the following code into the `Button1` handler:</span></span>  
  
     [!code-vb[DLinqWalk4VB#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk4VB/vb/Form1.vb#2)]  
  
3. <span data-ttu-id="4c764-185">Doppelklicken Sie jetzt auf **Button2** auf Form1 für das Erstellen der `Button2` -Ereignishandler und den Codeeditor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="4c764-185">Now double-click **Button2** on Form1 to create the `Button2` event handler and open the code editor.</span></span>  
  
4. <span data-ttu-id="4c764-186">Geben Sie den folgenden Code in den `Button2`-Ereignishandler ein.</span><span class="sxs-lookup"><span data-stu-id="4c764-186">Type the following code into the `Button2` handler:</span></span>  
  
     [!code-vb[DLinqWalk4VB#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk4VB/vb/Form1.vb#3)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="4c764-187">Testen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="4c764-187">Testing the Application</span></span>  
 <span data-ttu-id="4c764-188">Nun können Sie die Anwendung testen.</span><span class="sxs-lookup"><span data-stu-id="4c764-188">Now it is time to test your application.</span></span> <span data-ttu-id="4c764-189">Beachten Sie, dass die Verbindung zum Datastore auf die Aktionen der beiden gespeicherten Prozeduren beschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="4c764-189">Note that your contact with the datastore is limited to whatever actions the two stored procedures can take.</span></span> <span data-ttu-id="4c764-190">Diese Aktionen geben die Produkte zu der von Ihnen eingegebenen OrderID und die Produkthistorie zu der von Ihnen eingegebenen CustomerID zurück.</span><span class="sxs-lookup"><span data-stu-id="4c764-190">Those actions are to return the products included for any orderID you enter, or to return a history of products ordered for any CustomerID you enter.</span></span>  
  
#### <a name="to-test-the-application"></a><span data-ttu-id="4c764-191">So testen Sie die Anwendung</span><span class="sxs-lookup"><span data-stu-id="4c764-191">To test the application</span></span>  
  
1. <span data-ttu-id="4c764-192">Drücken Sie die Taste F5, um mit dem Debuggen zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="4c764-192">Press F5 to start debugging.</span></span>  
  
     <span data-ttu-id="4c764-193">Form1 wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4c764-193">Form1 appears.</span></span>  
  
2. <span data-ttu-id="4c764-194">In der **Enter OrderID** geben **10249** , und klicken Sie dann auf **Bestelldetails**.</span><span class="sxs-lookup"><span data-stu-id="4c764-194">In the **Enter OrderID** box, type **10249** and then click **Order Details**.</span></span>  
  
     <span data-ttu-id="4c764-195">Ein Meldungsfeld listet die in Bestellung 10249 enthaltenen Produkte auf.</span><span class="sxs-lookup"><span data-stu-id="4c764-195">A message box lists the products included in order 10249.</span></span>  
  
     <span data-ttu-id="4c764-196">Klicken Sie auf **OK** um das Meldungsfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="4c764-196">Click **OK** to close the message box.</span></span>  
  
3. <span data-ttu-id="4c764-197">In der **Enter CustomerID** geben `ALFKI`, und klicken Sie dann auf **Bestellverlauf**.</span><span class="sxs-lookup"><span data-stu-id="4c764-197">In the **Enter CustomerID** box, type `ALFKI`, and then click **Order History**.</span></span>  
  
     <span data-ttu-id="4c764-198">Ein Meldungsfeld mit der Bestellhistorie für Kunde ALFKI wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4c764-198">A message box lists the order history for customer ALFKI.</span></span>  
  
     <span data-ttu-id="4c764-199">Klicken Sie auf **OK** um das Meldungsfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="4c764-199">Click **OK** to close the message box.</span></span>  
  
4. <span data-ttu-id="4c764-200">In der **Enter OrderID** geben `123`, und klicken Sie dann auf **Bestelldetails**.</span><span class="sxs-lookup"><span data-stu-id="4c764-200">In the **Enter OrderID** box, type `123`, and then click **Order Details**.</span></span>  
  
     <span data-ttu-id="4c764-201">Ein Meldungsfeld zeigt "Keine Ergebnisse" an.</span><span class="sxs-lookup"><span data-stu-id="4c764-201">A message box displays "No results."</span></span>  
  
     <span data-ttu-id="4c764-202">Klicken Sie auf **OK** um das Meldungsfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="4c764-202">Click **OK** to close the message box.</span></span>  
  
5. <span data-ttu-id="4c764-203">Auf der **Debuggen** Menü klicken Sie auf **Beenden des Debuggens**.</span><span class="sxs-lookup"><span data-stu-id="4c764-203">On the **Debug** menu, click **Stop debugging**.</span></span>  
  
     <span data-ttu-id="4c764-204">Die Debugsitzung schließt.</span><span class="sxs-lookup"><span data-stu-id="4c764-204">The debug session closes.</span></span>  
  
6. <span data-ttu-id="4c764-205">Wenn Sie mit dem Experimentieren fertig sind, können Sie klicken **Projekt schließen** auf die **Datei** Menü, und speichern Sie das Projekt aus, wenn Sie aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="4c764-205">If you have finished experimenting, you can click **Close Project** on the **File** menu, and save your project when you are prompted.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="4c764-206">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="4c764-206">Next Steps</span></span>  
 <span data-ttu-id="4c764-207">Sie können dieses Projekt mit einigen Änderungen erweitern.</span><span class="sxs-lookup"><span data-stu-id="4c764-207">You can enhance this project by making some changes.</span></span> <span data-ttu-id="4c764-208">Sie können beispielsweise die verfügbaren gespeicherten Prozeduren in einem Listenfeld aufführen, sodass der Benutzer diese auswählen kann.</span><span class="sxs-lookup"><span data-stu-id="4c764-208">For example, you could list available stored procedures in a list box and have the user select which procedures to execute.</span></span> <span data-ttu-id="4c764-209">Sie könnten auch die Ausgabe von Berichten in eine Textdatei umleiten.</span><span class="sxs-lookup"><span data-stu-id="4c764-209">You could also stream the output of the reports to a text file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c764-210">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4c764-210">See also</span></span>

- [<span data-ttu-id="4c764-211">Lernen durch exemplarische Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="4c764-211">Learning by Walkthroughs</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
- [<span data-ttu-id="4c764-212">Gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="4c764-212">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
