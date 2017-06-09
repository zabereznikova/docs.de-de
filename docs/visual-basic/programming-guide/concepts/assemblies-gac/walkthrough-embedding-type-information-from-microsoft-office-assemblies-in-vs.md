---
title: 'Exemplarische Vorgehensweise: Einbetten von Typinformationen aus Microsoft Office-Assemblys in Visual Studio (Visual Basic) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 26b44286-5066-4ad4-8e6a-c24902be347c
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 4347ba0e740419b53a1aa662c43933dead107e9c
ms.contentlocale: de-de
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-embedding-type-information-from-microsoft-office-assemblies-in-visual-studio-visual-basic"></a>Exemplarische Vorgehensweise: Einbetten von Typinformationen aus Microsoft Office-Assemblys in Visual Studio (Visual Basic)
Wenn Sie Typinformationen in eine Anwendung einbetten, die auf COM-Objekte verweist, ist die Verwendung einer primären Interopassembly (PIA) nicht mehr erforderlich. Darüber hinaus wird die Anwendung durch die eingebetteten Typinformationen versionsunabhängig. Ihr Programm kann daher für Typen aus unterschiedlichen Versionen einer COM-Bibliothek geschrieben werden; eine versionsspezifische PIA ist nicht erforderlich. Dies ist ein allgemeines Szenario für Anwendungen, die Objekte aus Microsoft Office-Bibliotheken verwenden. Mithilfe von eingebetteten Typinformationen kann ein Build eines Programms verschiedene Versionen von Microsoft Office auf unterschiedlichen Computern verwenden, ohne dass das Programm oder die PIA für jede Version von Microsoft Office erneut bereitgestellt werden müssen.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Für diese exemplarische Vorgehensweise wird Folgendes vorausgesetzt:  
  
-   Ein Computer, auf dem Visual Studio und Microsoft Excel installiert sind.  
  
-   Ein zweiter Computer, auf dem .NET Framework 4 oder höher und eine andere Version von Excel installiert sind.  
  
##  <a name="BKMK_createapp"></a>Zum Erstellen einer Anwendung, die mit mehreren Versionen von Microsoft Office  
  
1.  Starten Sie Visual Studio auf einem Computer, auf dem Excel installiert ist.  
  
2.  Wählen Sie im Menü **Datei** die Optionsfolge **Neu**, **Projekt**aus.  
  
3.  In der **neues Projekt** im Feld der **Projekttypen** Bereich, stellen Sie sicher, dass **Windows** ausgewählt ist. Wählen Sie **Konsolenanwendung** in der **Vorlagen** Bereich. In der **Namen** geben `CreateExcelWorkbook`, und wählen Sie dann die **OK** Schaltfläche. Das neue Projekt wird erstellt.  
  
4.  Öffnen Sie das Kontextmenü für das CreateExcelWorkbook-Projekt, und wählen Sie dann **Eigenschaften**. Wählen Sie die **Verweise** Registerkarte. Wählen Sie die Schaltfläche **Hinzufügen** aus.  
  
5.  Auf der **.NET** Registerkarte, und wählen Sie die neueste Version von `Microsoft.Office.Interop.Excel`. Beispielsweise **Microsoft.Office.Interop.Excel 14.0.0.0.**. Klicken Sie auf die Schaltfläche **OK** .  
  
6.  In der Liste der Verweise für die **CreateExcelWorkbook** Projekt, wählen Sie den Verweis für `Microsoft.Office.Interop.Excel` , die Sie im vorherigen Schritt hinzugefügt. In der **Eigenschaften** Fenster, stellen Sie sicher, dass die `Embed Interop Types` -Eigenschaft auf festgelegt ist `True`.  
  
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
  
9. Drücken Sie STRG+F5, um das Projekt zu erstellen und auszuführen. Überprüfen Sie, ob eine Excel-Arbeitsmappe an dem Speicherort erstellt wurde, der im Beispielcode angegebenen ist: C:\SampleFolder\SampleWorkbook.xls.  
  
##  <a name="BKMK_publishapp"></a>Veröffentlichen die Anwendung auf einem Computer, auf dem eine andere Version von Microsoft Office installiert ist  
  
1.  Öffnen Sie das Projekt in dieser exemplarischen Vorgehensweise in Visual Studio erstellt haben.  
  
2.  Auf der **erstellen** Menü wählen **CreateExcelWorkbook veröffentlichen**. Führen Sie die Schritte des Webpublishing-Assistenten aus, um eine installierbare Version der Anwendung zu erstellen. Weitere Informationen finden Sie unter [Webpublishing-Assistent (Office-Entwicklung in Visual Studio)](https://msdn.microsoft.com/library/bb625071).  
  
3.  Installieren Sie die Anwendung auf einem Computer, auf dem .NET Framework 4 oder höher und eine andere Version von Excel installiert sind.  
  
4.  Führen Sie das installierte Programm aus, sobald die Installation abgeschlossen ist.  
  
5.  Überprüfen Sie, ob eine Excel-Arbeitsmappe an dem Speicherort erstellt wurde, der im Beispielcode angegebenen ist: C:\SampleFolder\SampleWorkbook.xls.  
  
## <a name="see-also"></a>Siehe auch  
 [Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys in Visual Studio (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-vs.md)   
 [/ Link (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/link.md)

