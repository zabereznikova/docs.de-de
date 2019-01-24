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
# <a name="walkthrough-embedding-type-information-from-microsoft-office-assemblies-in-visual-studio-visual-basic"></a>Exemplarische Vorgehensweise: Einbetten von Typinformationen aus Microsoft Office-Assemblys in Visual Studio (Visual Basic)
Wenn Sie Typinformationen in eine Anwendung einbetten, die auf COM-Objekte verweist, ist die Verwendung einer primären Interopassembly (PIA) nicht mehr erforderlich. Darüber hinaus wird die Anwendung durch die eingebetteten Typinformationen versionsunabhängig. Ihr Programm kann daher für Typen aus unterschiedlichen Versionen einer COM-Bibliothek geschrieben werden; eine versionsspezifische PIA ist nicht erforderlich. Dies ist ein allgemeines Szenario für Anwendungen, die Objekte aus Microsoft Office-Bibliotheken verwenden. Mithilfe von eingebetteten Typinformationen kann ein Build eines Programms verschiedene Versionen von Microsoft Office auf unterschiedlichen Computern verwenden, ohne dass das Programm oder die PIA für jede Version von Microsoft Office erneut bereitgestellt werden müssen.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Vorraussetzungen  
 Für diese exemplarische Vorgehensweise wird Folgendes vorausgesetzt:  
  
-   Ein Computer, auf dem Visual Studio und Microsoft Excel installiert sind.  
  
-   Ein zweiter Computer, auf dem .NET Framework 4 oder höher und eine andere Version von Excel installiert sind.  
  
##  <a name="BKMK_createapp"></a> So erstellen Sie eine Anwendung, die mit mehreren Versionen von Microsoft Office kompatibel ist  
  
1.  Starten Sie Visual Studio auf einem Computer, auf dem Excel installiert ist.  
  
2.  Wählen Sie im Menü **Datei** die Optionsfolge **Neu**, **Projekt**aus.  
  
3.  Überprüfen Sie, ob im Dialogfeld **Neues Projekt** im Bereich **Projekttypen** der Eintrag **Windows** ausgewählt ist. Wählen Sie im Bereich **Vorlagen** die Option **Konsolenanwendung** aus. Geben Sie im Feld **Name** `CreateExcelWorkbook` ein, und wählen Sie dann die Schaltfläche **OK** aus. Das neue Projekt wird erstellt.  
  
4.  Öffnen Sie das Kontextmenü für das CreateExcelWorkbook-Projekt, und wählen Sie dann **Eigenschaften**. Wählen Sie die **Verweise** Registerkarte. Wählen Sie die Schaltfläche **Hinzufügen** aus.  
  
5.  Wählen Sie auf der Registerkarte **.NET** die aktuellste Version von `Microsoft.Office.Interop.Excel` aus. Beispiel: **Microsoft.Office.Interop.Excel 14.0.0.0**. Klicken Sie auf die Schaltfläche **OK** .  
  
6.  Wählen Sie in der Liste der Verweise für das **CreateExcelWorkbook**-Projekt den Verweis für `Microsoft.Office.Interop.Excel` aus, den Sie im vorherigen Schritt hinzugefügt haben. Vergewissern Sie sich, dass die `Embed Interop Types`-Eigenschaft im Fester **Eigenschaften** auf `True` festgelegt ist.  
  
    > [!NOTE]
    >  Die in dieser exemplarischen Vorgehensweise erstellte Anwendung kann aufgrund der eingebetteten Interop-Typinformationen mit verschiedenen Versionen von Microsoft Office ausgeführt werden. Wenn die `Embed Interop Types`-Eigenschaft auf `False` festgelegt ist, müssen Sie eine PIA für jede Version von Microsoft Office einschließen, mit der die Anwendung ausgeführt wird.  
  
7.  Öffnen Sie die Datei "Module1.vb". Ersetzen Sie den Code in der Datei durch den folgenden Code:  
  
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
  
8.  Speichern Sie das Projekt.  
  
9. Drücken Sie STRG+F5, um das Projekt zu erstellen und auszuführen. Stellen Sie sicher, dass eine Excel-Arbeitsmappe an dem im Beispielcode angegebenen Speicherort erstellt wurde: C:\SampleFolder\SampleWorkbook.xls.  
  
##  <a name="BKMK_publishapp"></a> So veröffentlichen Sie die Anwendung auf einem Computer, auf dem eine andere Version von Microsoft Office installiert ist  
  
1.  Öffnen Sie das Projekt, das Sie in dieser exemplarischen Vorgehensweise erstellt haben, in Visual Studio.  
  
2.  Wählen Sie im Menü **Erstellen** die Option **CreateExcelWorkbook veröffentlichen** aus. Führen Sie die Schritte des Webpublishing-Assistenten aus, um eine installierbare Version der Anwendung zu erstellen. Weitere Informationen finden Sie unter [Veröffentlichungs-Assistent (Office-Entwicklung in Visual Studio)](/visualstudio/vsto/publish-wizard-office-development-in-visual-studio).  
  
3.  Installieren Sie die Anwendung auf einem Computer, auf dem .NET Framework 4 oder höher und eine andere Version von Excel installiert sind.  
  
4.  Führen Sie das installierte Programm aus, sobald die Installation abgeschlossen ist.  
  
5.  Stellen Sie sicher, dass eine Excel-Arbeitsmappe an dem im Code angegebenen Speicherort erstellt wurde: C:\SampleFolder\SampleWorkbook.xls.  
  
## <a name="see-also"></a>Siehe auch

- [Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys in Visual Studio (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-vs.md)
- [/link (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/link.md)
