---
title: "Exemplarische Vorgehensweise: Ausschließliches Verwenden von gespeicherten Prozeduren (Visual Basic)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: vb
ms.assetid: 5a736a30-ba66-4adb-b87c-57d19476e862
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 800cc7d6a1e4aa836ebe75afcbe29a3532ee173a
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="walkthrough-using-only-stored-procedures-visual-basic"></a><span data-ttu-id="97f5f-102">Exemplarische Vorgehensweise: Ausschließliches Verwenden von gespeicherten Prozeduren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="97f5f-102">Walkthrough: Using Only Stored Procedures (Visual Basic)</span></span>
<span data-ttu-id="97f5f-103">Diese exemplarische Vorgehensweise stellt ein grundlegendes End-to-End-[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Szenario für den Datenzugriff mithilfe von gespeicherten Prozeduren bereit.</span><span class="sxs-lookup"><span data-stu-id="97f5f-103">This walkthrough provides a basic end-to-end [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] scenario for accessing data by using stored procedures only.</span></span> <span data-ttu-id="97f5f-104">Dieser Ansatz wird oft von Datenbankadministratoren verwendet, um den Zugriff auf den Datenspeicher einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="97f5f-104">This approach is often used by database administrators to limit how the datastore is accessed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="97f5f-105">Sie können gespeicherte Prozeduren außerdem in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Anwendungen verwenden, um das Standardverhalten zu überschreiben. Dies gilt vor allem für die Prozesse `Create`, `Update` und `Delete`.</span><span class="sxs-lookup"><span data-stu-id="97f5f-105">You can also use stored procedures in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications to override default behavior, especially for `Create`, `Update`, and `Delete` processes.</span></span> <span data-ttu-id="97f5f-106">Weitere Informationen finden Sie unter [Anpassen von INSERT-, Update- und Delete-Operationen](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="97f5f-106">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>  
  
 <span data-ttu-id="97f5f-107">Im Rahmen dieser exemplarischen Vorgehensweise verwenden Sie zwei Methoden, die in der Beispieldatenbank Northwind gespeicherten Prozeduren zugeordnet wurden: CustOrdersDetail und CustOrderHist.</span><span class="sxs-lookup"><span data-stu-id="97f5f-107">For purposes of this walkthrough, you will use two methods that have been mapped to stored procedures in the Northwind sample database: CustOrdersDetail and CustOrderHist.</span></span> <span data-ttu-id="97f5f-108">Die Zuordnung tritt auf, wenn Sie das SQLMetal-Befehlszeilentool ausführen, um eine [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]-Datei zu generieren.</span><span class="sxs-lookup"><span data-stu-id="97f5f-108">The mapping occurs when you run the SqlMetal command-line tool to generate a [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] file.</span></span> <span data-ttu-id="97f5f-109">Weitere Informationen finden Sie im Abschnitt zu Voraussetzungen weiter unten in dieser exemplarischen Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="97f5f-109">For more information, see the Prerequisites section later in this walkthrough.</span></span>  
  
 <span data-ttu-id="97f5f-110">Diese exemplarische Vorgehensweise basiert nicht auf [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="97f5f-110">This walkthrough does not rely on the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)].</span></span> <span data-ttu-id="97f5f-111">Entwickler, die mit [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] arbeiten, können auch [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] verwenden, um die Funktionalität einer gespeicherten Prozedur zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="97f5f-111">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] can also use the [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] to implement stored procedure functionality.</span></span> <span data-ttu-id="97f5f-112">Finden Sie unter [LINQ to SQL-Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span><span class="sxs-lookup"><span data-stu-id="97f5f-112">See [LINQ to SQL Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="97f5f-113">Diese exemplarische Vorgehensweise wurde mithilfe von Visual Basic-Entwicklungseinstellungen geschrieben.</span><span class="sxs-lookup"><span data-stu-id="97f5f-113">This walkthrough was written by using Visual Basic Development Settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="97f5f-114">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="97f5f-114">Prerequisites</span></span>  
 <span data-ttu-id="97f5f-115">Für diese exemplarische Vorgehensweise wird Folgendes vorausgesetzt:</span><span class="sxs-lookup"><span data-stu-id="97f5f-115">This walkthrough requires the following:</span></span>  
  
-   <span data-ttu-id="97f5f-116">Diese exemplarische Vorgehensweise verwendet einen dedizierten Ordner ("c:\linqtest3") als Speicherort für Dateien.</span><span class="sxs-lookup"><span data-stu-id="97f5f-116">This walkthrough uses a dedicated folder ("c:\linqtest3") to hold files.</span></span> <span data-ttu-id="97f5f-117">Erstellen Sie diesen Ordner, bevor Sie die exemplarische Vorgehensweise starten.</span><span class="sxs-lookup"><span data-stu-id="97f5f-117">Create this folder before you begin the walkthrough.</span></span>  
  
-   <span data-ttu-id="97f5f-118">Die Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="97f5f-118">The Northwind sample database.</span></span>  
  
     <span data-ttu-id="97f5f-119">Befindet sich diese Datenbank nicht auf Ihrem Entwicklungscomputer, können Sie diese von der Microsoft Downloadsite herunterladen.</span><span class="sxs-lookup"><span data-stu-id="97f5f-119">If you do not have this database on your development computer, you can download it from the Microsoft download site.</span></span> <span data-ttu-id="97f5f-120">Anweisungen hierzu finden Sie unter [Herunterladen von Beispieldatenbanken](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="97f5f-120">For instructions, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span> <span data-ttu-id="97f5f-121">Nachdem Sie die Datenbank heruntergeladen haben, kopieren Sie die Datei northwnd.mdf in den Ordner c:\linqtest3.</span><span class="sxs-lookup"><span data-stu-id="97f5f-121">After you have downloaded the database, copy the northwnd.mdf file to the c:\linqtest3 folder.</span></span>  
  
-   <span data-ttu-id="97f5f-122">Eine von der Datenbank Northwind generierte [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]-Codedatei.</span><span class="sxs-lookup"><span data-stu-id="97f5f-122">A [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] code file generated from the Northwind database.</span></span>  
  
     <span data-ttu-id="97f5f-123">Diese exemplarische Vorgehensweise wurde mithilfe des SQLMetal-Tools mit der folgenden Befehlszeile geschrieben:</span><span class="sxs-lookup"><span data-stu-id="97f5f-123">This walkthrough was written by using the SqlMetal tool with the following command line:</span></span>  
  
     <span data-ttu-id="97f5f-124">**sqlmetal /code:"c:\linqtest3\northwind.vb" /language:vb "c:\linqtest3\northwnd.mdf" /sprocs /functions /pluralize**</span><span class="sxs-lookup"><span data-stu-id="97f5f-124">**sqlmetal /code:"c:\linqtest3\northwind.vb" /language:vb "c:\linqtest3\northwnd.mdf" /sprocs /functions /pluralize**</span></span>  
  
     <span data-ttu-id="97f5f-125">Weitere Informationen finden Sie unter [SqlMetal.exe (Tool zur Codegenerierung)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="97f5f-125">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="overview"></a><span data-ttu-id="97f5f-126">Übersicht</span><span class="sxs-lookup"><span data-stu-id="97f5f-126">Overview</span></span>  
 <span data-ttu-id="97f5f-127">Diese exemplarische Vorgehensweise umfasst sechs Hauptaufgaben:</span><span class="sxs-lookup"><span data-stu-id="97f5f-127">This walkthrough consists of six main tasks:</span></span>  
  
-   <span data-ttu-id="97f5f-128">Einrichten der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Lösung in [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="97f5f-128">Setting up the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solution in [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)].</span></span>  
  
-   <span data-ttu-id="97f5f-129">Hinzufügen der System.Data.Linq-Assembly zum Projekt</span><span class="sxs-lookup"><span data-stu-id="97f5f-129">Adding the System.Data.Linq assembly to the project.</span></span>  
  
-   <span data-ttu-id="97f5f-130">Hinzufügen der Datenbank-Codedatei zum Projekt.</span><span class="sxs-lookup"><span data-stu-id="97f5f-130">Adding the database code file to the project.</span></span>  
  
-   <span data-ttu-id="97f5f-131">Erstellen einer Verbindung mit der Datenbank</span><span class="sxs-lookup"><span data-stu-id="97f5f-131">Creating a connection to the database.</span></span>  
  
-   <span data-ttu-id="97f5f-132">Einrichten der Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="97f5f-132">Setting up the user interface.</span></span>  
  
-   <span data-ttu-id="97f5f-133">Ausführen und Testen der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="97f5f-133">Running and testing the application.</span></span>  
  
## <a name="creating-a-linq-to-sql-solution"></a><span data-ttu-id="97f5f-134">Erstellen einer LINQ to SQL-Lösung</span><span class="sxs-lookup"><span data-stu-id="97f5f-134">Creating a LINQ to SQL Solution</span></span>  
 <span data-ttu-id="97f5f-135">In dieser ersten Aufgabe erstellen Sie eine [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]-Lösung, die die erforderlichen Verweise zur Erstellung und Ausführung eines [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Projekts enthält.</span><span class="sxs-lookup"><span data-stu-id="97f5f-135">In this first task, you create a [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] solution that contains the necessary references to build and run a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project.</span></span>  
  
#### <a name="to-create-a-linq-to-sql-solution"></a><span data-ttu-id="97f5f-136">So erstellen Sie eine LINQ to SQL-Lösung</span><span class="sxs-lookup"><span data-stu-id="97f5f-136">To create a LINQ to SQL solution</span></span>  
  
1.  <span data-ttu-id="97f5f-137">Auf der [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] **Datei** Menü klicken Sie auf **neues Projekt**.</span><span class="sxs-lookup"><span data-stu-id="97f5f-137">On the [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] **File** menu, click **New Project**.</span></span>  
  
2.  <span data-ttu-id="97f5f-138">Erweitern Sie im Bereich **Projekttypen** des Dialogfelds **Neues Projekt** den Eintrag **Visual Basic**, und klicken Sie dann auf **Windows**.</span><span class="sxs-lookup"><span data-stu-id="97f5f-138">In the **Project types** pane in the **New Project** dialog box, expand **Visual Basic**, and then click **Windows**.</span></span>  
  
3.  <span data-ttu-id="97f5f-139">Klicken Sie im Bereich **Vorlagen** auf **Windows Forms-Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="97f5f-139">In the **Templates** pane, click **Windows Forms Application**.</span></span>  
  
4.  <span data-ttu-id="97f5f-140">In der **Namen** geben **SprocOnlyApp**.</span><span class="sxs-lookup"><span data-stu-id="97f5f-140">In the **Name** box, type **SprocOnlyApp**.</span></span>  
  
5.  <span data-ttu-id="97f5f-141">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="97f5f-141">Click **OK**.</span></span>  
  
     <span data-ttu-id="97f5f-142">Der Windows Forms Designer wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="97f5f-142">The Windows Forms Designer opens.</span></span>  
  
## <a name="adding-the-linq-to-sql-assembly-reference"></a><span data-ttu-id="97f5f-143">Hinzufügen des LINQ to SQL-Assemblyverweises</span><span class="sxs-lookup"><span data-stu-id="97f5f-143">Adding the LINQ to SQL Assembly Reference</span></span>  
 <span data-ttu-id="97f5f-144">Die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Assembly ist nicht in der Standardvorlage für Windows Forms-Anwendungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="97f5f-144">The [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] assembly is not included in the standard Windows Forms Application template.</span></span> <span data-ttu-id="97f5f-145">Sie müssen die Assembly selbst hinzufügen. Siehe hierzu die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="97f5f-145">You will have to add the assembly yourself, as explained in the following steps:</span></span>  
  
#### <a name="to-add-systemdatalinqdll"></a><span data-ttu-id="97f5f-146">So fügen Sie die Datei System.Data.Linq.dll hinzu</span><span class="sxs-lookup"><span data-stu-id="97f5f-146">To add System.Data.Linq.dll</span></span>  
  
1.  <span data-ttu-id="97f5f-147">In **Projektmappen-Explorer**, klicken Sie auf **alle Dateien anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="97f5f-147">In **Solution Explorer**, click **Show All Files**.</span></span>  
  
2.  <span data-ttu-id="97f5f-148">In **Projektmappen-Explorer**, mit der rechten Maustaste **Verweise**, und klicken Sie dann auf **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="97f5f-148">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>  
  
3.  <span data-ttu-id="97f5f-149">In der **Verweis hinzufügen** (Dialogfeld), klicken Sie auf **.NET**, klicken Sie auf die System.Data.Linq-Assembly, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="97f5f-149">In the **Add Reference** dialog box, click **.NET**, click the System.Data.Linq assembly, and then click **OK**.</span></span>  
  
     <span data-ttu-id="97f5f-150">Dem Projekt wird die Assembly hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="97f5f-150">The assembly is added to the project.</span></span>  
  
## <a name="adding-the-northwind-code-file-to-the-project"></a><span data-ttu-id="97f5f-151">Hinzufügen der Northwind-Codedatei zum Projekt.</span><span class="sxs-lookup"><span data-stu-id="97f5f-151">Adding the Northwind Code File to the Project</span></span>  
 <span data-ttu-id="97f5f-152">Bei diesem Schritt wird davon ausgegangen, dass Sie das SQLMetal-Tool zum Erzeugen einer Codedatei aus der Beispieldatenbank Northwind verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="97f5f-152">This step assumes that you have used the SqlMetal tool to generate a code file from the Northwind sample database.</span></span> <span data-ttu-id="97f5f-153">Weitere Informationen finden Sie im Abschnitt zu Voraussetzungen weiter oben in dieser exemplarischen Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="97f5f-153">For more information, see the Prerequisites section earlier in this walkthrough.</span></span>  
  
#### <a name="to-add-the-northwind-code-file-to-the-project"></a><span data-ttu-id="97f5f-154">So fügen Sie die Northwind-Codedatei dem Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="97f5f-154">To add the northwind code file to the project</span></span>  
  
1.  <span data-ttu-id="97f5f-155">Auf der **Projekt** Menü klicken Sie auf **vorhandenes Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="97f5f-155">On the **Project** menu, click **Add Existing Item**.</span></span>  
  
2.  <span data-ttu-id="97f5f-156">In der **vorhandenes Element hinzufügen** c:\linqtest3\northwind.vb ANS (Dialogfeld), und klicken Sie dann auf **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="97f5f-156">In the **Add Existing Item** dialog box, move to c:\linqtest3\northwind.vb, and then click **Add**.</span></span>  
  
     <span data-ttu-id="97f5f-157">Die Datei northwind.vb wird dem Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="97f5f-157">The northwind.vb file is added to the project.</span></span>  
  
## <a name="creating-a-database-connection"></a><span data-ttu-id="97f5f-158">Erstellen von Datenbankverbindungen</span><span class="sxs-lookup"><span data-stu-id="97f5f-158">Creating a Database Connection</span></span>  
 <span data-ttu-id="97f5f-159">In diesem Schritt definieren Sie die Verbindung zur Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="97f5f-159">In this step, you define the connection to the Northwind sample database.</span></span> <span data-ttu-id="97f5f-160">Diese exemplarische Vorgehensweise verwendet "c:\linqtest3\northwnd.mdf" als Pfad.</span><span class="sxs-lookup"><span data-stu-id="97f5f-160">This walkthrough uses "c:\linqtest3\northwnd.mdf" as the path.</span></span>  
  
#### <a name="to-create-the-database-connection"></a><span data-ttu-id="97f5f-161">So erstellen Sie die Datenbankverbindung</span><span class="sxs-lookup"><span data-stu-id="97f5f-161">To create the database connection</span></span>  
  
1.  <span data-ttu-id="97f5f-162">In **Projektmappen-Explorer**, mit der rechten Maustaste **"Form1.vb"**, und klicken Sie dann auf **Code anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="97f5f-162">In **Solution Explorer**, right-click **Form1.vb**, and then click **View Code**.</span></span>  
  
     <span data-ttu-id="97f5f-163">`Class Form1` erscheint im Code-Editor.</span><span class="sxs-lookup"><span data-stu-id="97f5f-163">`Class Form1` appears in the code editor.</span></span>  
  
2.  <span data-ttu-id="97f5f-164">Geben Sie den folgenden Code in den `Form1`-Code-Block ein.</span><span class="sxs-lookup"><span data-stu-id="97f5f-164">Type the following code into the `Form1` code block:</span></span>  
  
     [!code-vb[DLinqWalk4VB#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk4VB/vb/Form1.vb#1)]  
  
## <a name="setting-up-the-user-interface"></a><span data-ttu-id="97f5f-165">Einrichten der Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="97f5f-165">Setting up the User Interface</span></span>  
 <span data-ttu-id="97f5f-166">In diesem Schritt erstellen Sie eine Benutzeroberfläche, sodass Benutzer durch Ausführen gespeicherter Prozeduren auf die Daten in der Datenbank zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="97f5f-166">In this task you create an interface so that users can execute stored procedures to access data in the database.</span></span> <span data-ttu-id="97f5f-167">In den von Ihnen hier entwickelten Anwendungen können Benutzer nur mithilfe der in der Anwendung eingebetteten gespeicherten Prozeduren auf die Daten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="97f5f-167">In the application that you are developing with this walkthrough, users can access data in the database only by using the stored procedures embedded in the application.</span></span>  
  
#### <a name="to-set-up-the-user-interface"></a><span data-ttu-id="97f5f-168">So richten Sie die Benutzeroberfläche ein</span><span class="sxs-lookup"><span data-stu-id="97f5f-168">To set up the user interface</span></span>  
  
1.  <span data-ttu-id="97f5f-169">Zurück zu den Windows Forms-Designer (**Form1.vb]**).</span><span class="sxs-lookup"><span data-stu-id="97f5f-169">Return to the Windows Forms Designer (**Form1.vb[Design]**).</span></span>  
  
2.  <span data-ttu-id="97f5f-170">Klicken Sie im Menü **Ansicht** auf **Toolbox**.</span><span class="sxs-lookup"><span data-stu-id="97f5f-170">On the **View** menu, click **Toolbox**.</span></span>  
  
     <span data-ttu-id="97f5f-171">Die Toolbox wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="97f5f-171">The toolbox opens.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="97f5f-172">Klicken Sie auf die **Taskleisten** PIN Toolbox geöffnet zu lassen, während Sie die folgenden Schritte in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="97f5f-172">Click the **AutoHide** pushpin to keep the toolbox open while you perform the remaining steps in this section.</span></span>  
  
3.  <span data-ttu-id="97f5f-173">Ziehen Sie zwei Schaltflächen, zwei Textfelder und zwei Bezeichnungen von der Toolbox auf **Form1**.</span><span class="sxs-lookup"><span data-stu-id="97f5f-173">Drag two buttons, two text boxes, and two labels from the toolbox onto **Form1**.</span></span>  
  
     <span data-ttu-id="97f5f-174">Ordnen Sie die Steuerelemente wie in der Abbildung an.</span><span class="sxs-lookup"><span data-stu-id="97f5f-174">Arrange the controls as in the accompanying illustration.</span></span> <span data-ttu-id="97f5f-175">Erweitern Sie **Form1** , damit die Steuerelemente problemlos angepasst.</span><span class="sxs-lookup"><span data-stu-id="97f5f-175">Expand **Form1** so that the controls fit easily.</span></span>  
  
4.  <span data-ttu-id="97f5f-176">Mit der rechten Maustaste **Label1**, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="97f5f-176">Right-click **Label1**, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="97f5f-177">Ändern der **Text** Eigenschaft von **Label1** auf **Enter OrderID:**.</span><span class="sxs-lookup"><span data-stu-id="97f5f-177">Change the **Text** property from **Label1** to **Enter OrderID:**.</span></span>  
  
6.  <span data-ttu-id="97f5f-178">Auf die gleiche Weise für **Label2**, ändern Sie die **Text** Eigenschaft von **Label2** zu **Enter CustomerID:**.</span><span class="sxs-lookup"><span data-stu-id="97f5f-178">In the same way for **Label2**, change the **Text** property from **Label2** to **Enter CustomerID:**.</span></span>  
  
7.  <span data-ttu-id="97f5f-179">Ändern Sie auf die gleiche Weise die **Text** -Eigenschaft für **Button1** auf **Bestelldetails**.</span><span class="sxs-lookup"><span data-stu-id="97f5f-179">In the same way, change the **Text** property for **Button1** to **Order Details**.</span></span>  
  
8.  <span data-ttu-id="97f5f-180">Ändern der **Text** -Eigenschaft für **Button2** auf **Bestellverlauf**.</span><span class="sxs-lookup"><span data-stu-id="97f5f-180">Change the **Text** property for **Button2** to **Order History**.</span></span>  
  
     <span data-ttu-id="97f5f-181">Erweitern Sie die Schaltflächen-Steuerelemente, damit der gesamte Text sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="97f5f-181">Widen the button controls so that all the text is visible.</span></span>  
  
#### <a name="to-handle-button-clicks"></a><span data-ttu-id="97f5f-182">Verarbeitung von Mausklicks auf die Schaltflächen</span><span class="sxs-lookup"><span data-stu-id="97f5f-182">To handle button clicks</span></span>  
  
1.  <span data-ttu-id="97f5f-183">Doppelklicken Sie auf **Bestelldetails** auf **Form1** zum Erstellen der `Button1` -Ereignishandler und das Codeeditor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="97f5f-183">Double-click **Order Details** on **Form1** to create the `Button1` event handler and open the code editor.</span></span>  
  
2.  <span data-ttu-id="97f5f-184">Geben Sie den folgenden Code in den `Button1`-Ereignishandler ein.</span><span class="sxs-lookup"><span data-stu-id="97f5f-184">Type the following code into the `Button1` handler:</span></span>  
  
     [!code-vb[DLinqWalk4VB#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk4VB/vb/Form1.vb#2)]  
  
3.  <span data-ttu-id="97f5f-185">Doppelklicken Sie jetzt auf **Button2** auf Form1 für das Erstellen der `Button2` -Ereignishandler und das Codeeditor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="97f5f-185">Now double-click **Button2** on Form1 to create the `Button2` event handler and open the code editor.</span></span>  
  
4.  <span data-ttu-id="97f5f-186">Geben Sie den folgenden Code in den `Button2`-Ereignishandler ein.</span><span class="sxs-lookup"><span data-stu-id="97f5f-186">Type the following code into the `Button2` handler:</span></span>  
  
     [!code-vb[DLinqWalk4VB#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk4VB/vb/Form1.vb#3)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="97f5f-187">Testen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="97f5f-187">Testing the Application</span></span>  
 <span data-ttu-id="97f5f-188">Nun können Sie die Anwendung testen.</span><span class="sxs-lookup"><span data-stu-id="97f5f-188">Now it is time to test your application.</span></span> <span data-ttu-id="97f5f-189">Beachten Sie, dass die Verbindung zum Datastore auf die Aktionen der beiden gespeicherten Prozeduren beschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="97f5f-189">Note that your contact with the datastore is limited to whatever actions the two stored procedures can take.</span></span> <span data-ttu-id="97f5f-190">Diese Aktionen geben die Produkte zu der von Ihnen eingegebenen OrderID und die Produkthistorie zu der von Ihnen eingegebenen CustomerID zurück.</span><span class="sxs-lookup"><span data-stu-id="97f5f-190">Those actions are to return the products included for any orderID you enter, or to return a history of products ordered for any CustomerID you enter.</span></span>  
  
#### <a name="to-test-the-application"></a><span data-ttu-id="97f5f-191">So testen Sie die Anwendung</span><span class="sxs-lookup"><span data-stu-id="97f5f-191">To test the application</span></span>  
  
1.  <span data-ttu-id="97f5f-192">Drücken Sie die Taste F5, um mit dem Debuggen zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="97f5f-192">Press F5 to start debugging.</span></span>  
  
     <span data-ttu-id="97f5f-193">Form1 wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="97f5f-193">Form1 appears.</span></span>  
  
2.  <span data-ttu-id="97f5f-194">In der **Enter OrderID** geben **10249** , und klicken Sie dann auf **Bestelldetails**.</span><span class="sxs-lookup"><span data-stu-id="97f5f-194">In the **Enter OrderID** box, type **10249** and then click **Order Details**.</span></span>  
  
     <span data-ttu-id="97f5f-195">Ein Meldungsfeld listet die in Bestellung 10249 enthaltenen Produkte auf.</span><span class="sxs-lookup"><span data-stu-id="97f5f-195">A message box lists the products included in order 10249.</span></span>  
  
     <span data-ttu-id="97f5f-196">Klicken Sie auf **OK** um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="97f5f-196">Click **OK** to close the message box.</span></span>  
  
3.  <span data-ttu-id="97f5f-197">In der **Enter CustomerID** geben `ALFKI`, und klicken Sie dann auf **Bestellverlauf**.</span><span class="sxs-lookup"><span data-stu-id="97f5f-197">In the **Enter CustomerID** box, type `ALFKI`, and then click **Order History**.</span></span>  
  
     <span data-ttu-id="97f5f-198">Ein Meldungsfeld mit der Bestellhistorie für Kunde ALFKI wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="97f5f-198">A message box lists the order history for customer ALFKI.</span></span>  
  
     <span data-ttu-id="97f5f-199">Klicken Sie auf **OK** um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="97f5f-199">Click **OK** to close the message box.</span></span>  
  
4.  <span data-ttu-id="97f5f-200">In der **Enter OrderID** geben `123`, und klicken Sie dann auf **Bestelldetails**.</span><span class="sxs-lookup"><span data-stu-id="97f5f-200">In the **Enter OrderID** box, type `123`, and then click **Order Details**.</span></span>  
  
     <span data-ttu-id="97f5f-201">Ein Meldungsfeld zeigt "Keine Ergebnisse" an.</span><span class="sxs-lookup"><span data-stu-id="97f5f-201">A message box displays "No results."</span></span>  
  
     <span data-ttu-id="97f5f-202">Klicken Sie auf **OK** um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="97f5f-202">Click **OK** to close the message box.</span></span>  
  
5.  <span data-ttu-id="97f5f-203">Auf der **Debuggen** Menü klicken Sie auf **Beenden des Debuggens**.</span><span class="sxs-lookup"><span data-stu-id="97f5f-203">On the **Debug** menu, click **Stop debugging**.</span></span>  
  
     <span data-ttu-id="97f5f-204">Die Debugsitzung schließt.</span><span class="sxs-lookup"><span data-stu-id="97f5f-204">The debug session closes.</span></span>  
  
6.  <span data-ttu-id="97f5f-205">Wenn Sie Ihre Versuche abgeschlossen haben, können Sie klicken **Projekt schließen** auf die **Datei** Menü, und speichern Sie das Projekt aus, wenn Sie aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="97f5f-205">If you have finished experimenting, you can click **Close Project** on the **File** menu, and save your project when you are prompted.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="97f5f-206">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="97f5f-206">Next Steps</span></span>  
 <span data-ttu-id="97f5f-207">Sie können dieses Projekt mit einigen Änderungen erweitern.</span><span class="sxs-lookup"><span data-stu-id="97f5f-207">You can enhance this project by making some changes.</span></span> <span data-ttu-id="97f5f-208">Sie können beispielsweise die verfügbaren gespeicherten Prozeduren in einem Listenfeld aufführen, sodass der Benutzer diese auswählen kann.</span><span class="sxs-lookup"><span data-stu-id="97f5f-208">For example, you could list available stored procedures in a list box and have the user select which procedures to execute.</span></span> <span data-ttu-id="97f5f-209">Sie könnten auch die Ausgabe von Berichten in eine Textdatei umleiten.</span><span class="sxs-lookup"><span data-stu-id="97f5f-209">You could also stream the output of the reports to a text file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97f5f-210">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="97f5f-210">See Also</span></span>  
 [<span data-ttu-id="97f5f-211">Lernen durch exemplarische Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="97f5f-211">Learning by Walkthroughs</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)  
 [<span data-ttu-id="97f5f-212">Gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="97f5f-212">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
