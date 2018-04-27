---
title: 'Exemplarische Vorgehensweise: Ausschließliches Verwenden von gespeicherten Prozeduren (C#)'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ecde4bf2-fa4d-4252-b5e4-96a46b9e097d
caps.latest.revision: 4
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 4c13e4c12abf17f995bb819ddd7d6337407e3b28
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-using-only-stored-procedures-c"></a><span data-ttu-id="e1ed6-102">Exemplarische Vorgehensweise: Ausschließliches Verwenden von gespeicherten Prozeduren (C#)</span><span class="sxs-lookup"><span data-stu-id="e1ed6-102">Walkthrough: Using Only Stored Procedures (C#)</span></span>
<span data-ttu-id="e1ed6-103">Diese exemplarische Vorgehensweise stellt ein grundlegendes End-to-End-Szenario für [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] für den Datenzugriff mithilfe von gespeicherten Prozeduren bereit.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-103">This walkthrough provides a basic end-to-end [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] scenario for accessing data by executing stored procedures only.</span></span> <span data-ttu-id="e1ed6-104">Dieser Ansatz wird oft von Datenbankadministratoren verwendet, um den Zugriff auf den Datenspeicher einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-104">This approach is often used by database administrators to limit how the datastore is accessed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e1ed6-105">Sie können gespeicherte Prozeduren außerdem in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Anwendungen verwenden, um das Standardverhalten zu überschreiben. Dies gilt vor allem für die Prozesse `Create`, `Update` und `Delete`.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-105">You can also use stored procedures in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications to override default behavior, especially for `Create`, `Update`, and `Delete` processes.</span></span> <span data-ttu-id="e1ed6-106">Weitere Informationen finden Sie unter [Anpassen von INSERT-, Update- und Delete-Operationen](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="e1ed6-106">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>  
  
 <span data-ttu-id="e1ed6-107">Im Rahmen dieser exemplarischen Vorgehensweise verwenden Sie zwei Methoden, die in der Beispieldatenbank Northwind gespeicherten Prozeduren zugeordnet wurden: CustOrdersDetail und CustOrderHist.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-107">For purposes of this walkthrough, you will use two methods that have been mapped to stored procedures in the Northwind sample database: CustOrdersDetail and CustOrderHist.</span></span> <span data-ttu-id="e1ed6-108">Die Zuordnung tritt auf, wenn Sie das SQLMetal-Befehlszeilentool ausführen, um eine C#-Datei zu generieren.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-108">The mapping occurs when you run the SqlMetal command-line tool to generate a C# file.</span></span> <span data-ttu-id="e1ed6-109">Weitere Informationen finden Sie im Abschnitt zu Voraussetzungen weiter unten in dieser exemplarischen Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-109">For more information, see the Prerequisites section later in this walkthrough.</span></span>  
  
 <span data-ttu-id="e1ed6-110">Diese exemplarische Vorgehensweise basiert nicht auf [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e1ed6-110">This walkthrough does not rely on the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)].</span></span> <span data-ttu-id="e1ed6-111">Entwickler, die mit Visual Studio können auch die [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] zum Implementieren der Funktionalität einer gespeicherten Prozedur.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-111">Developers using Visual Studio can also use the [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] to implement stored procedure functionality.</span></span> <span data-ttu-id="e1ed6-112">Finden Sie unter [LINQ to SQL-Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span><span class="sxs-lookup"><span data-stu-id="e1ed6-112">See [LINQ to SQL Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="e1ed6-113">Diese exemplarische Vorgehensweise wurde mithilfe von Visual C#-Entwicklungseinstellungen geschrieben.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-113">This walkthrough was written by using Visual C# Development Settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e1ed6-114">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="e1ed6-114">Prerequisites</span></span>  
 <span data-ttu-id="e1ed6-115">Für diese exemplarische Vorgehensweise wird Folgendes vorausgesetzt:</span><span class="sxs-lookup"><span data-stu-id="e1ed6-115">This walkthrough requires the following:</span></span>  
  
-   <span data-ttu-id="e1ed6-116">Diese exemplarische Vorgehensweise verwendet einen dedizierten Ordner ("c:\linqtest7") als Speicherort für Dateien.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-116">This walkthrough uses a dedicated folder ("c:\linqtest7") to hold files.</span></span> <span data-ttu-id="e1ed6-117">Erstellen Sie diesen Ordner, bevor Sie die exemplarische Vorgehensweise starten.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-117">Create this folder before you begin the walkthrough.</span></span>  
  
-   <span data-ttu-id="e1ed6-118">Die Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-118">The Northwind sample database.</span></span>  
  
     <span data-ttu-id="e1ed6-119">Befindet sich diese Datenbank nicht auf Ihrem Entwicklungscomputer, können Sie diese von der Microsoft Downloadsite herunterladen.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-119">If you do not have this database on your development computer, you can download it from the Microsoft download site.</span></span> <span data-ttu-id="e1ed6-120">Anweisungen hierzu finden Sie unter [Herunterladen von Beispieldatenbanken](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="e1ed6-120">For instructions, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span> <span data-ttu-id="e1ed6-121">Nachdem Sie die Datenbank heruntergeladen haben, kopieren Sie die Datei northwnd.mdf in den Ordner c:\linqtest7.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-121">After you have downloaded the database, copy the northwnd.mdf file to the c:\linqtest7 folder.</span></span>  
  
-   <span data-ttu-id="e1ed6-122">Eine von der Datenbank Northwind generierte C#-Codedatei.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-122">A C# code file generated from the Northwind database.</span></span>  
  
     <span data-ttu-id="e1ed6-123">Diese exemplarische Vorgehensweise wurde mithilfe des SQLMetal-Tools mit der folgenden Befehlszeile geschrieben:</span><span class="sxs-lookup"><span data-stu-id="e1ed6-123">This walkthrough was written by using the SqlMetal tool with the following command line:</span></span>  
  
     <span data-ttu-id="e1ed6-124">**sqlmetal /code:"c:\linqtest7\northwind.cs" /language:csharp "c:\linqtest7\northwnd.mdf" /sprocs /functions /pluralize**</span><span class="sxs-lookup"><span data-stu-id="e1ed6-124">**sqlmetal /code:"c:\linqtest7\northwind.cs" /language:csharp "c:\linqtest7\northwnd.mdf" /sprocs /functions /pluralize**</span></span>  
  
     <span data-ttu-id="e1ed6-125">Weitere Informationen finden Sie unter [SqlMetal.exe (Tool zur Codegenerierung)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="e1ed6-125">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="overview"></a><span data-ttu-id="e1ed6-126">Übersicht</span><span class="sxs-lookup"><span data-stu-id="e1ed6-126">Overview</span></span>  
 <span data-ttu-id="e1ed6-127">Diese exemplarische Vorgehensweise umfasst sechs Hauptaufgaben:</span><span class="sxs-lookup"><span data-stu-id="e1ed6-127">This walkthrough consists of six main tasks:</span></span>  
  
-   <span data-ttu-id="e1ed6-128">Einrichten der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Projektmappe in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-128">Setting up the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solution in Visual Studio.</span></span>  
  
-   <span data-ttu-id="e1ed6-129">Hinzufügen der System.Data.Linq-Assembly zum Projekt</span><span class="sxs-lookup"><span data-stu-id="e1ed6-129">Adding the System.Data.Linq assembly to the project.</span></span>  
  
-   <span data-ttu-id="e1ed6-130">Hinzufügen der Datenbank-Codedatei zum Projekt.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-130">Adding the database code file to the project.</span></span>  
  
-   <span data-ttu-id="e1ed6-131">Erstellen einer Verbindung mit der Datenbank</span><span class="sxs-lookup"><span data-stu-id="e1ed6-131">Creating a connection with the database.</span></span>  
  
-   <span data-ttu-id="e1ed6-132">Einrichten der Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-132">Setting up the user interface.</span></span>  
  
-   <span data-ttu-id="e1ed6-133">Ausführen und Testen der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-133">Running and testing the application.</span></span>  
  
## <a name="creating-a-linq-to-sql-solution"></a><span data-ttu-id="e1ed6-134">Erstellen einer LINQ to SQL-Lösung</span><span class="sxs-lookup"><span data-stu-id="e1ed6-134">Creating a LINQ to SQL Solution</span></span>  
 <span data-ttu-id="e1ed6-135">In dieser ersten Aufgabe erstellen Sie eine Visual Studio-Projektmappe, enthält die erforderlichen Verweise zur Erstellung und Ausführung, einer [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Projekt.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-135">In this first task, you create a Visual Studio solution that contains the necessary references to build and run a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project.</span></span>  
  
#### <a name="to-create-a-linq-to-sql-solution"></a><span data-ttu-id="e1ed6-136">So erstellen Sie eine LINQ to SQL-Lösung</span><span class="sxs-lookup"><span data-stu-id="e1ed6-136">To create a LINQ to SQL solution</span></span>  
  
1.  <span data-ttu-id="e1ed6-137">Visual Studio **Datei** Sie im Menü **neu**, und klicken Sie dann auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-137">On the Visual Studio **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="e1ed6-138">In der **-Projekttypen** im Bereich der **neues Projekt** (Dialogfeld), klicken Sie auf **Visual C#-**.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-138">In the **Project types** pane in the **New Project** dialog box, click **Visual C#**.</span></span>  
  
3.  <span data-ttu-id="e1ed6-139">Klicken Sie im Bereich **Vorlagen** auf **Windows Forms-Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-139">In the **Templates** pane, click **Windows Forms Application**.</span></span>  
  
4.  <span data-ttu-id="e1ed6-140">In der **Namen** geben **SprocOnlyApp**.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-140">In the **Name** box, type **SprocOnlyApp**.</span></span>  
  
5.  <span data-ttu-id="e1ed6-141">In der **Speicherort** Vergewissern Sie sich, wo die Projektdateien gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-141">In the **Location** box, verify where you want to store your project files.</span></span>  
  
6.  <span data-ttu-id="e1ed6-142">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-142">Click **OK**.</span></span>  
  
     <span data-ttu-id="e1ed6-143">Der Windows Forms Designer wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-143">The Windows Forms Designer opens.</span></span>  
  
## <a name="adding-the-linq-to-sql-assembly-reference"></a><span data-ttu-id="e1ed6-144">Hinzufügen des LINQ to SQL-Assemblyverweises</span><span class="sxs-lookup"><span data-stu-id="e1ed6-144">Adding the LINQ to SQL Assembly Reference</span></span>  
 <span data-ttu-id="e1ed6-145">Die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Assembly ist nicht in der Standardvorlage für Windows Forms-Anwendungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-145">The [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] assembly is not included in the standard Windows Forms Application template.</span></span> <span data-ttu-id="e1ed6-146">Sie müssen die Assembly selbst hinzufügen. Siehe hierzu die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="e1ed6-146">You will have to add the assembly yourself, as explained in the following steps:</span></span>  
  
#### <a name="to-add-systemdatalinqdll"></a><span data-ttu-id="e1ed6-147">So fügen Sie die Datei System.Data.Linq.dll hinzu</span><span class="sxs-lookup"><span data-stu-id="e1ed6-147">To add System.Data.Linq.dll</span></span>  
  
1.  <span data-ttu-id="e1ed6-148">In **Projektmappen-Explorer**, mit der rechten Maustaste **Verweise**, und klicken Sie dann auf **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-148">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="e1ed6-149">In der **Verweis hinzufügen** (Dialogfeld), klicken Sie auf **.NET**, klicken Sie auf die System.Data.Linq-Assembly, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-149">In the **Add Reference** dialog box, click **.NET**, click the System.Data.Linq assembly, and then click **OK**.</span></span>  
  
     <span data-ttu-id="e1ed6-150">Dem Projekt wird die Assembly hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-150">The assembly is added to the project.</span></span>  
  
## <a name="adding-the-northwind-code-file-to-the-project"></a><span data-ttu-id="e1ed6-151">Hinzufügen der Northwind-Codedatei zum Projekt.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-151">Adding the Northwind Code File to the Project</span></span>  
 <span data-ttu-id="e1ed6-152">Bei diesem Schritt wird davon ausgegangen, dass Sie das SQLMetal-Tool zum Erzeugen einer Codedatei aus der Beispieldatenbank Northwind verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-152">This step assumes that you have used the SqlMetal tool to generate a code file from the Northwind sample database.</span></span> <span data-ttu-id="e1ed6-153">Weitere Informationen finden Sie im Abschnitt zu Voraussetzungen weiter oben in dieser exemplarischen Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-153">For more information, see the Prerequisites section earlier in this walkthrough.</span></span>  
  
#### <a name="to-add-the-northwind-code-file-to-the-project"></a><span data-ttu-id="e1ed6-154">So fügen Sie die Northwind-Codedatei dem Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-154">To add the northwind code file to the project</span></span>  
  
1.  <span data-ttu-id="e1ed6-155">Auf der **Projekt** Menü klicken Sie auf **vorhandenes Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-155">On the **Project** menu, click **Add Existing Item**.</span></span>  
  
2.  <span data-ttu-id="e1ed6-156">In der **vorhandenes Element hinzufügen** c:\linqtest7\northwind.cs ANS (Dialogfeld), und klicken Sie dann auf **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-156">In the **Add Existing Item** dialog box, move to c:\linqtest7\northwind.cs, and then click **Add**.</span></span>  
  
     <span data-ttu-id="e1ed6-157">Die Datei northwind.cs wird dem Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-157">The northwind.cs file is added to the project.</span></span>  
  
## <a name="creating-a-database-connection"></a><span data-ttu-id="e1ed6-158">Erstellen von Datenbankverbindungen</span><span class="sxs-lookup"><span data-stu-id="e1ed6-158">Creating a Database Connection</span></span>  
 <span data-ttu-id="e1ed6-159">In diesem Schritt definieren Sie die Verbindung zur Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-159">In this step, you define the connection to the Northwind sample database.</span></span> <span data-ttu-id="e1ed6-160">Diese exemplarische Vorgehensweise verwendet "c:\linqtest7\northwnd.mdf" als Pfad.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-160">This walkthrough uses "c:\linqtest7\northwnd.mdf" as the path.</span></span>  
  
#### <a name="to-create-the-database-connection"></a><span data-ttu-id="e1ed6-161">So erstellen Sie die Datenbankverbindung</span><span class="sxs-lookup"><span data-stu-id="e1ed6-161">To create the database connection</span></span>  
  
1.  <span data-ttu-id="e1ed6-162">In **Projektmappen-Explorer**, mit der rechten Maustaste **"Form1.cs"**, und klicken Sie dann auf **Code anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-162">In **Solution Explorer**, right-click **Form1.cs**, and then click **View Code**.</span></span>  
  
2.  <span data-ttu-id="e1ed6-163">Geben Sie den folgenden Code in die `Form1`-Klasse ein:</span><span class="sxs-lookup"><span data-stu-id="e1ed6-163">Type the following code into the `Form1` class:</span></span>  
  
     [!code-csharp[DLinqWalk4CS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk4CS/cs/Form1.cs#1)]  
  
## <a name="setting-up-the-user-interface"></a><span data-ttu-id="e1ed6-164">Einrichten der Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="e1ed6-164">Setting up the User Interface</span></span>  
 <span data-ttu-id="e1ed6-165">In diesem Schritt richten Sie eine Benutzeroberfläche ein, sodass Benutzer durch Ausführen gespeicherter Prozeduren auf die Daten in der Datenbank zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-165">In this task you set up an interface so that users can execute stored procedures to access data in the database.</span></span> <span data-ttu-id="e1ed6-166">In den von Ihnen hier entwickelten Anwendungen können Benutzer nur mithilfe der in der Anwendung eingebetteten gespeicherten Prozeduren auf die Daten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-166">In the applications that you are developing with this walkthrough, users can access data in the database only by using the stored procedures embedded in the application.</span></span>  
  
#### <a name="to-set-up-the-user-interface"></a><span data-ttu-id="e1ed6-167">So richten Sie die Benutzeroberfläche ein</span><span class="sxs-lookup"><span data-stu-id="e1ed6-167">To set up the user interface</span></span>  
  
1.  <span data-ttu-id="e1ed6-168">Zurück zu den Windows Forms-Designer (**Form1.cs]**).</span><span class="sxs-lookup"><span data-stu-id="e1ed6-168">Return to the Windows Forms Designer (**Form1.cs[Design]**).</span></span>  
  
2.  <span data-ttu-id="e1ed6-169">Klicken Sie im Menü **Ansicht** auf **Toolbox**.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-169">On the **View** menu, click **Toolbox**.</span></span>  
  
     <span data-ttu-id="e1ed6-170">Die Toolbox wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-170">The toolbox opens.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e1ed6-171">Klicken Sie auf die **Taskleisten** PIN Toolbox geöffnet zu lassen, während Sie die folgenden Schritte in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-171">Click the **AutoHide** pushpin to keep the toolbox open while you perform the remaining steps in this section.</span></span>  
  
3.  <span data-ttu-id="e1ed6-172">Ziehen Sie zwei Schaltflächen, zwei Textfelder und zwei Bezeichnungen von der Toolbox auf **Form1**.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-172">Drag two buttons, two text boxes, and two labels from the toolbox onto **Form1**.</span></span>  
  
     <span data-ttu-id="e1ed6-173">Ordnen Sie die Steuerelemente wie in der Abbildung an.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-173">Arrange the controls as in the accompanying illustration.</span></span> <span data-ttu-id="e1ed6-174">Erweitern Sie **Form1** , damit die Steuerelemente problemlos angepasst.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-174">Expand **Form1** so that the controls fit easily.</span></span>  
  
4.  <span data-ttu-id="e1ed6-175">Mit der rechten Maustaste **label1**, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-175">Right-click **label1**, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="e1ed6-176">Ändern der **Text** Eigenschaft von **label1** auf **Enter OrderID:**.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-176">Change the **Text** property from **label1** to **Enter OrderID:**.</span></span>  
  
6.  <span data-ttu-id="e1ed6-177">Auf die gleiche Weise für **label2**, ändern Sie die **Text** Eigenschaft von **label2** zu **Enter CustomerID:**.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-177">In the same way for **label2**, change the **Text** property from **label2** to **Enter CustomerID:**.</span></span>  
  
7.  <span data-ttu-id="e1ed6-178">Ändern Sie auf die gleiche Weise die **Text** -Eigenschaft für **button1** auf **Bestelldetails**.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-178">In the same way, change the **Text** property for **button1** to **Order Details**.</span></span>  
  
8.  <span data-ttu-id="e1ed6-179">Ändern der **Text** -Eigenschaft für **button2** auf **Bestellverlauf**.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-179">Change the **Text** property for **button2** to **Order History**.</span></span>  
  
     <span data-ttu-id="e1ed6-180">Erweitern Sie die Schaltflächen-Steuerelemente, damit der gesamte Text sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-180">Widen the button controls so that all the text is visible.</span></span>  
  
#### <a name="to-handle-button-clicks"></a><span data-ttu-id="e1ed6-181">Verarbeitung von Mausklicks auf die Schaltflächen</span><span class="sxs-lookup"><span data-stu-id="e1ed6-181">To handle button clicks</span></span>  
  
1.  <span data-ttu-id="e1ed6-182">Doppelklicken Sie auf **Bestelldetails** auf **Form1** um den button1-Ereignishandler im Codeeditor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-182">Double-click **Order Details** on **Form1** to open the button1 event handler in the code editor.</span></span>  
  
2.  <span data-ttu-id="e1ed6-183">Geben Sie den folgenden Code in den `button1`-Ereignishandler ein.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-183">Type the following code into the `button1` handler:</span></span>  
  
     [!code-csharp[DLinqWalk4CS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk4CS/cs/Form1.cs#2)]  
  
3.  <span data-ttu-id="e1ed6-184">Doppelklicken Sie jetzt auf **button2** auf **Form1** So öffnen die `button2` Handler</span><span class="sxs-lookup"><span data-stu-id="e1ed6-184">Now double-click **button2** on **Form1** to open the `button2` handler</span></span>  
  
4.  <span data-ttu-id="e1ed6-185">Geben Sie den folgenden Code in den `button2`-Ereignishandler ein.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-185">Type the following code into the `button2` handler:</span></span>  
  
     [!code-csharp[DLinqWalk4CS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk4CS/cs/Form1.cs#3)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="e1ed6-186">Testen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="e1ed6-186">Testing the Application</span></span>  
 <span data-ttu-id="e1ed6-187">Nun können Sie die Anwendung testen.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-187">Now it is time to test your application.</span></span> <span data-ttu-id="e1ed6-188">Beachten Sie, dass die Verbindung zum Datastore auf die Aktionen der beiden gespeicherten Prozeduren beschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-188">Note that your contact with the datastore is limited to whatever actions the two stored procedures can take.</span></span> <span data-ttu-id="e1ed6-189">Diese Aktionen geben die Produkte zu der von Ihnen eingegebenen OrderID und die Produkthistorie zu der von Ihnen eingegebenen CustomerID zurück.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-189">Those actions are to return the products included for any orderID you enter, or to return a history of products ordered for any CustomerID you enter.</span></span>  
  
#### <a name="to-test-the-application"></a><span data-ttu-id="e1ed6-190">So testen Sie die Anwendung</span><span class="sxs-lookup"><span data-stu-id="e1ed6-190">To test the application</span></span>  
  
1.  <span data-ttu-id="e1ed6-191">Drücken Sie die Taste F5, um mit dem Debuggen zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-191">Press F5 to start debugging.</span></span>  
  
     <span data-ttu-id="e1ed6-192">Form1 wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-192">Form1 appears.</span></span>  
  
2.  <span data-ttu-id="e1ed6-193">In der **Enter OrderID** geben `10249`, und klicken Sie dann auf **Bestelldetails**.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-193">In the **Enter OrderID** box, type `10249`, and then click **Order Details**.</span></span>  
  
     <span data-ttu-id="e1ed6-194">Ein Meldungsfeld listet die in Bestellung 10249 enthaltenen Produkte auf.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-194">A message box lists the products included in order 10249.</span></span>  
  
     <span data-ttu-id="e1ed6-195">Klicken Sie auf **OK** um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-195">Click **OK** to close the message box.</span></span>  
  
3.  <span data-ttu-id="e1ed6-196">In der **Enter CustomerID** geben `ALFKI`, und klicken Sie dann auf **Bestellverlauf**.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-196">In the **Enter CustomerID** box, type `ALFKI`, and then click **Order History**.</span></span>  
  
     <span data-ttu-id="e1ed6-197">Ein Meldungsfeld mit der Bestellhistorie für den Kunden ALFKI wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-197">A message box appears that lists the order history for customer ALFKI.</span></span>  
  
     <span data-ttu-id="e1ed6-198">Klicken Sie auf **OK** um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-198">Click **OK** to close the message box.</span></span>  
  
4.  <span data-ttu-id="e1ed6-199">In der **Enter OrderID** geben `123`, und klicken Sie dann auf **Bestelldetails**.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-199">In the **Enter OrderID** box, type `123`, and then click **Order Details**.</span></span>  
  
     <span data-ttu-id="e1ed6-200">Die Meldung "Keine Ergebnisse" erscheint.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-200">A message box appears that displays "No results."</span></span>  
  
     <span data-ttu-id="e1ed6-201">Klicken Sie auf **OK** um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-201">Click **OK** to close the message box.</span></span>  
  
5.  <span data-ttu-id="e1ed6-202">Auf der **Debuggen** Menü klicken Sie auf **Beenden des Debuggens**.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-202">On the **Debug** menu, click **Stop debugging**.</span></span>  
  
     <span data-ttu-id="e1ed6-203">Die Debugsitzung schließt.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-203">The debug session closes.</span></span>  
  
6.  <span data-ttu-id="e1ed6-204">Wenn Sie Ihre Versuche abgeschlossen haben, können Sie klicken **Projekt schließen** auf die **Datei** Menü, und speichern Sie das Projekt aus, wenn Sie aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-204">If you have finished experimenting, you can click **Close Project** on the **File** menu, and save your project when you are prompted.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="e1ed6-205">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="e1ed6-205">Next Steps</span></span>  
 <span data-ttu-id="e1ed6-206">Sie können dieses Projekt mit einigen Änderungen erweitern.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-206">You can enhance this project by making some changes.</span></span> <span data-ttu-id="e1ed6-207">Sie können beispielsweise die verfügbaren gespeicherten Prozeduren in einem Listenfeld aufführen, sodass der Benutzer diese auswählen kann.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-207">For example, you could list available stored procedures in a list box and have the user select which procedures to execute.</span></span> <span data-ttu-id="e1ed6-208">Sie könnten auch die Ausgabe von Berichten in eine Textdatei umleiten.</span><span class="sxs-lookup"><span data-stu-id="e1ed6-208">You could also stream the output of the reports to a text file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1ed6-209">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e1ed6-209">See Also</span></span>  
 [<span data-ttu-id="e1ed6-210">Lernen durch exemplarische Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="e1ed6-210">Learning by Walkthroughs</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)  
 [<span data-ttu-id="e1ed6-211">Gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="e1ed6-211">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
