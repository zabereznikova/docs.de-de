---
title: 'Exemplarische Vorgehensweise: Einbetten von Typinformationen aus Microsoft Office-Assemblys in Visual Studio (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 26b44286-5066-4ad4-8e6a-c24902be347c
ms.openlocfilehash: e5b94c190a77f6877c9a3d37f310aa527083a26a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722776"
---
# <a name="walkthrough-embedding-type-information-from-microsoft-office-assemblies-in-visual-studio-visual-basic"></a><span data-ttu-id="74cdd-102">Exemplarische Vorgehensweise: Einbetten von Typinformationen aus Microsoft Office-Assemblys in Visual Studio (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="74cdd-102">Walkthrough: Embedding Type Information from Microsoft Office Assemblies in Visual Studio (Visual Basic)</span></span>
<span data-ttu-id="74cdd-103">Wenn Sie Typinformationen in eine Anwendung einbetten, die auf COM-Objekte verweist, ist die Verwendung einer primären Interopassembly (PIA) nicht mehr erforderlich.</span><span class="sxs-lookup"><span data-stu-id="74cdd-103">If you embed type information in an application that references COM objects, you can eliminate the need for a primary interop assembly (PIA).</span></span> <span data-ttu-id="74cdd-104">Darüber hinaus wird die Anwendung durch die eingebetteten Typinformationen versionsunabhängig.</span><span class="sxs-lookup"><span data-stu-id="74cdd-104">Additionally, the embedded type information enables you to achieve version independence for your application.</span></span> <span data-ttu-id="74cdd-105">Ihr Programm kann daher für Typen aus unterschiedlichen Versionen einer COM-Bibliothek geschrieben werden; eine versionsspezifische PIA ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="74cdd-105">That is, your program can be written to use types from multiple versions of a COM library without requiring a specific PIA for each version.</span></span> <span data-ttu-id="74cdd-106">Dies ist ein allgemeines Szenario für Anwendungen, die Objekte aus Microsoft Office-Bibliotheken verwenden.</span><span class="sxs-lookup"><span data-stu-id="74cdd-106">This is a common scenario for applications that use objects from Microsoft Office libraries.</span></span> <span data-ttu-id="74cdd-107">Mithilfe von eingebetteten Typinformationen kann ein Build eines Programms verschiedene Versionen von Microsoft Office auf unterschiedlichen Computern verwenden, ohne dass das Programm oder die PIA für jede Version von Microsoft Office erneut bereitgestellt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="74cdd-107">Embedding type information enables the same build of a program to work with different versions of Microsoft Office on different computers without the need to redeploy either the program or the PIA for each version of Microsoft Office.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a><span data-ttu-id="74cdd-108">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="74cdd-108">Prerequisites</span></span>  
 <span data-ttu-id="74cdd-109">Für diese exemplarische Vorgehensweise wird Folgendes vorausgesetzt:</span><span class="sxs-lookup"><span data-stu-id="74cdd-109">This walkthrough requires the following:</span></span>  
  
-   <span data-ttu-id="74cdd-110">Ein Computer, auf dem Visual Studio und Microsoft Excel installiert sind.</span><span class="sxs-lookup"><span data-stu-id="74cdd-110">A computer on which Visual Studio and Microsoft Excel are installed.</span></span>  
  
-   <span data-ttu-id="74cdd-111">Ein zweiter Computer, auf dem .NET Framework 4 oder höher und eine andere Version von Excel installiert sind.</span><span class="sxs-lookup"><span data-stu-id="74cdd-111">A second computer on which the .NET Framework 4 or higher and a different version of Excel are installed.</span></span>  
  
##  <a name="BKMK_createapp"></a> <span data-ttu-id="74cdd-112">So erstellen Sie eine Anwendung, die mit mehreren Versionen von Microsoft Office kompatibel ist</span><span class="sxs-lookup"><span data-stu-id="74cdd-112">To create an application that works with multiple versions of Microsoft Office</span></span>  
  
1.  <span data-ttu-id="74cdd-113">Starten Sie Visual Studio auf einem Computer, auf dem Excel installiert ist.</span><span class="sxs-lookup"><span data-stu-id="74cdd-113">Start Visual Studio on a computer on which Excel is installed.</span></span>  
  
2.  <span data-ttu-id="74cdd-114">Wählen Sie im Menü **Datei** die Optionsfolge **Neu**, **Projekt**aus.</span><span class="sxs-lookup"><span data-stu-id="74cdd-114">On the **File** menu, choose **New**, **Project**.</span></span>  
  
3.  <span data-ttu-id="74cdd-115">Überprüfen Sie, ob im Dialogfeld **Neues Projekt** im Bereich **Projekttypen** der Eintrag **Windows** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="74cdd-115">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="74cdd-116">Wählen Sie im Bereich **Vorlagen** die Option **Konsolenanwendung** aus.</span><span class="sxs-lookup"><span data-stu-id="74cdd-116">Select **Console Application** in the **Templates** pane.</span></span> <span data-ttu-id="74cdd-117">Geben Sie im Feld **Name** `CreateExcelWorkbook` ein, und wählen Sie dann die Schaltfläche **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="74cdd-117">In the **Name** box, enter `CreateExcelWorkbook`, and then choose the **OK** button.</span></span> <span data-ttu-id="74cdd-118">Das neue Projekt wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="74cdd-118">The new project is created.</span></span>  
  
4.  <span data-ttu-id="74cdd-119">Öffnen Sie das Kontextmenü für das CreateExcelWorkbook-Projekt, und wählen Sie dann **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="74cdd-119">Open the shortcut menu for the CreateExcelWorkbook project and then choose **Properties**.</span></span> <span data-ttu-id="74cdd-120">Wählen Sie die **Verweise** Registerkarte. Wählen Sie die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="74cdd-120">Choose the **References** tab. Choose the **Add** button.</span></span>  
  
5.  <span data-ttu-id="74cdd-121">Wählen Sie auf der Registerkarte **.NET** die aktuellste Version von `Microsoft.Office.Interop.Excel` aus.</span><span class="sxs-lookup"><span data-stu-id="74cdd-121">On the **.NET** tab, choose the most recent version of `Microsoft.Office.Interop.Excel`.</span></span> <span data-ttu-id="74cdd-122">Beispiel: **Microsoft.Office.Interop.Excel 14.0.0.0**.</span><span class="sxs-lookup"><span data-stu-id="74cdd-122">For example, **Microsoft.Office.Interop.Excel 14.0.0.0**.</span></span> <span data-ttu-id="74cdd-123">Klicken Sie auf die Schaltfläche **OK** .</span><span class="sxs-lookup"><span data-stu-id="74cdd-123">Choose the **OK** button.</span></span>  
  
6.  <span data-ttu-id="74cdd-124">Wählen Sie in der Liste der Verweise für das **CreateExcelWorkbook**-Projekt den Verweis für `Microsoft.Office.Interop.Excel` aus, den Sie im vorherigen Schritt hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="74cdd-124">In the list of references for the **CreateExcelWorkbook** project, select the reference for `Microsoft.Office.Interop.Excel` that you added in the previous step.</span></span> <span data-ttu-id="74cdd-125">Vergewissern Sie sich, dass die `Embed Interop Types`-Eigenschaft im Fester **Eigenschaften** auf `True` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="74cdd-125">In the **Properties** window, make sure that the `Embed Interop Types` property is set to `True`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="74cdd-126">Die in dieser exemplarischen Vorgehensweise erstellte Anwendung kann aufgrund der eingebetteten Interop-Typinformationen mit verschiedenen Versionen von Microsoft Office ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="74cdd-126">The application created in this walkthrough runs with different versions of Microsoft Office because of the embedded interop type information.</span></span> <span data-ttu-id="74cdd-127">Wenn die `Embed Interop Types`-Eigenschaft auf `False` festgelegt ist, müssen Sie eine PIA für jede Version von Microsoft Office einschließen, mit der die Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="74cdd-127">If the `Embed Interop Types` property is set to `False`, you must include a PIA for each version of Microsoft Office that the application will run with.</span></span>  
  
7.  <span data-ttu-id="74cdd-128">Öffnen Sie die Datei "Module1.vb".</span><span class="sxs-lookup"><span data-stu-id="74cdd-128">Open the Module1.vb file.</span></span> <span data-ttu-id="74cdd-129">Ersetzen Sie den Code in der Datei durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="74cdd-129">Replace the code in the file with the following code:</span></span>  
  
    ```vb  
    Imports Excel = Microsoft.Office.Interop.Excel  
  
    Module Module1  
  
        Sub Main()  
            Dim values = {4, 6, 18, 2, 1, 76, 0, 3, 11}  
  
            CreateWorkbook(values, "C:\SampleFolder\SampleWorkbook.xls")  
        End Sub  
  
        Sub CreateWorkbook(ByVal values As Integer(), ByVal filePath As String)  
            Dim excelApp As Excel.Application = Nothing  
            Dim wkbk As Excel.Workbook  
            Dim sheet As Excel.Worksheet  
  
            Try  
                ' Start Excel and create a workbook and worksheet.  
                excelApp = New Excel.Application  
                wkbk = excelApp.Workbooks.Add()  
                sheet = CType(wkbk.Sheets.Add(), Excel.Worksheet)  
                sheet.Name = "Sample Worksheet"  
  
                ' Write a column of values.  
                ' In the For loop, both the row index and array index start at 1.  
                ' Therefore the value of 4 at array index 0 is not included.  
                For i = 1 To values.Length - 1  
                    sheet.Cells(i, 1) = values(i)  
                Next  
  
                ' Suppress any alerts and save the file. Create the directory   
                ' if it does not exist. Overwrite the file if it exists.  
                excelApp.DisplayAlerts = False  
                Dim folderPath = My.Computer.FileSystem.GetParentPath(filePath)  
                If Not My.Computer.FileSystem.DirectoryExists(folderPath) Then  
                    My.Computer.FileSystem.CreateDirectory(folderPath)  
                End If  
                wkbk.SaveAs(filePath)  
        Catch  
  
            Finally  
                sheet = Nothing  
                wkbk = Nothing  
  
                ' Close Excel.  
                excelApp.Quit()  
                excelApp = Nothing  
            End Try  
  
        End Sub  
    End Module  
    ```  
  
8.  <span data-ttu-id="74cdd-130">Speichern Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="74cdd-130">Save the project.</span></span>  
  
9. <span data-ttu-id="74cdd-131">Drücken Sie STRG+F5, um das Projekt zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="74cdd-131">Press CTRL+F5 to build and run the project.</span></span> <span data-ttu-id="74cdd-132">Stellen Sie sicher, dass eine Excel-Arbeitsmappe an dem im Beispielcode angegebenen Speicherort erstellt wurde: C:\SampleFolder\SampleWorkbook.xls.</span><span class="sxs-lookup"><span data-stu-id="74cdd-132">Verify that an Excel workbook has been created at the location specified in the example code: C:\SampleFolder\SampleWorkbook.xls.</span></span>  
  
##  <a name="BKMK_publishapp"></a> <span data-ttu-id="74cdd-133">So veröffentlichen Sie die Anwendung auf einem Computer, auf dem eine andere Version von Microsoft Office installiert ist</span><span class="sxs-lookup"><span data-stu-id="74cdd-133">To publish the application to a computer on which a different version of Microsoft Office is installed</span></span>  
  
1.  <span data-ttu-id="74cdd-134">Öffnen Sie das Projekt, das Sie in dieser exemplarischen Vorgehensweise erstellt haben, in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="74cdd-134">Open the project created by this walkthrough in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="74cdd-135">Wählen Sie im Menü **Erstellen** die Option **CreateExcelWorkbook veröffentlichen** aus.</span><span class="sxs-lookup"><span data-stu-id="74cdd-135">On the **Build** menu, choose **Publish CreateExcelWorkbook**.</span></span> <span data-ttu-id="74cdd-136">Führen Sie die Schritte des Webpublishing-Assistenten aus, um eine installierbare Version der Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="74cdd-136">Follow the steps of the Publish Wizard to create an installable version of the application.</span></span> <span data-ttu-id="74cdd-137">Weitere Informationen finden Sie unter [Veröffentlichungs-Assistent (Office-Entwicklung in Visual Studio)](/visualstudio/vsto/publish-wizard-office-development-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="74cdd-137">For more information, see [Publish Wizard (Office Development in Visual Studio)](/visualstudio/vsto/publish-wizard-office-development-in-visual-studio).</span></span>  
  
3.  <span data-ttu-id="74cdd-138">Installieren Sie die Anwendung auf einem Computer, auf dem .NET Framework 4 oder höher und eine andere Version von Excel installiert sind.</span><span class="sxs-lookup"><span data-stu-id="74cdd-138">Install the application on a computer on which the .NET Framework 4 or higher and a different version of Excel are installed.</span></span>  
  
4.  <span data-ttu-id="74cdd-139">Führen Sie das installierte Programm aus, sobald die Installation abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="74cdd-139">When the installation is finished, run the installed program.</span></span>  
  
5.  <span data-ttu-id="74cdd-140">Stellen Sie sicher, dass eine Excel-Arbeitsmappe an dem im Code angegebenen Speicherort erstellt wurde: C:\SampleFolder\SampleWorkbook.xls.</span><span class="sxs-lookup"><span data-stu-id="74cdd-140">Verify that an Excel workbook has been created at the location specified in the sample code: C:\SampleFolder\SampleWorkbook.xls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74cdd-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74cdd-141">See also</span></span>

- [<span data-ttu-id="74cdd-142">Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys in Visual Studio (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="74cdd-142">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-vs.md)
- [<span data-ttu-id="74cdd-143">/link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="74cdd-143">/link (Visual Basic)</span></span>](../../../../visual-basic/reference/command-line-compiler/link.md)
