---
title: 'Exemplarische Vorgehensweise: Einbetten von Typinformationen aus Microsoft Office-Assemblys in Visual Studio (C#)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 3320e866-01f1-4b7f-8932-049a7b2d2a9b
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 45ec4521da08a9a1f4bdc3b433d3f8d765960526
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-embedding-type-information-from-microsoft-office-assemblies-in-visual-studio-c"></a>Exemplarische Vorgehensweise: Einbetten von Typinformationen aus Microsoft Office-Assemblys in Visual Studio (C#)
Wenn Sie Typinformationen in eine Anwendung einbetten, die auf COM-Objekte verweist, ist die Verwendung einer primären Interopassembly (PIA) nicht mehr erforderlich. Darüber hinaus wird die Anwendung durch die eingebetteten Typinformationen versionsunabhängig. Ihr Programm kann daher für Typen aus unterschiedlichen Versionen einer COM-Bibliothek geschrieben werden; eine versionsspezifische PIA ist nicht erforderlich. Dies ist ein allgemeines Szenario für Anwendungen, die Objekte aus Microsoft Office-Bibliotheken verwenden. Mithilfe von eingebetteten Typinformationen kann ein Build eines Programms verschiedene Versionen von Microsoft Office auf unterschiedlichen Computern verwenden, ohne dass das Programm oder die PIA für jede Version von Microsoft Office erneut bereitgestellt werden müssen.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Für diese exemplarische Vorgehensweise wird Folgendes vorausgesetzt:  
  
-   Ein Computer, auf dem Visual Studio und Microsoft Excel installiert sind.  
  
-   Ein zweiter Computer, auf dem .NET Framework 4 oder höher und eine andere Version von Excel installiert sind.  
  
##  <a name="BKMK_createapp"></a> So erstellen Sie eine Anwendung, die mit mehreren Versionen von Microsoft Office kompatibel ist  
  
1.  Starten Sie Visual Studio auf einem Computer, auf dem Excel installiert ist.  
  
2.  Wählen Sie im Menü **Datei** die Optionsfolge **Neu**, **Projekt**aus.  
  
3.  Überprüfen Sie, ob im Dialogfeld **Neues Projekt** im Bereich **Projekttypen** der Eintrag **Windows** ausgewählt ist. Wählen Sie im Bereich **Vorlagen** die Option **Konsolenanwendung** aus. Geben Sie im Feld **Name** `CreateExcelWorkbook` ein, und wählen Sie dann die Schaltfläche **OK** aus. Das neue Projekt wird erstellt.  
  
4.  Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für den Ordner **Verweise**, und wählen Sie dann **Verweis hinzufügen** aus.  
  
5.  Wählen Sie auf der Registerkarte **.NET** die aktuellste Version von `Microsoft.Office.Interop.Excel` aus. Beispiel: **Microsoft.Office.Interop.Excel 14.0.0.0**. Klicken Sie auf die Schaltfläche **OK** .  
  
6.  Wählen Sie in der Liste der Verweise für das **CreateExcelWorkbook**-Projekt den Verweis für `Microsoft.Office.Interop.Excel` aus, den Sie im vorherigen Schritt hinzugefügt haben. Vergewissern Sie sich, dass die `Embed Interop Types`-Eigenschaft im Fester **Eigenschaften** auf `True` festgelegt ist.  
  
    > [!NOTE]
    >  Die in dieser exemplarischen Vorgehensweise erstellte Anwendung kann aufgrund der eingebetteten Interop-Typinformationen mit verschiedenen Versionen von Microsoft Office ausgeführt werden. Wenn die `Embed Interop Types`-Eigenschaft auf `False` festgelegt ist, müssen Sie eine PIA für jede Version von Microsoft Office einschließen, mit der die Anwendung ausgeführt wird.  
  
7.  Öffnen Sie die Datei **Program.cs**. Ersetzen Sie den Code in der Datei durch den folgenden Code:  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using System.IO;  
    using Excel = Microsoft.Office.Interop.Excel;  
  
    namespace CreateExcelWorkbook  
    {  
        class Program  
        {  
            static void Main(string[] args)  
            {  
                int[] values = {4, 6, 18, 2, 1, 76, 0, 3, 11};  
  
                CreateWorkbook(values, @"C:\SampleFolder\SampleWorkbook.xls");  
            }  
  
            static void CreateWorkbook(int[] values, string filePath)  
            {  
                Excel.Application excelApp = null;  
                Excel.Workbook wkbk;  
                Excel.Worksheet sheet;  
  
                try  
                {  
                        // Start Excel and create a workbook and worksheet.  
                        excelApp = new Excel.Application();  
                        wkbk = excelApp.Workbooks.Add();  
                        sheet = wkbk.Sheets.Add() as Excel.Worksheet;  
                        sheet.Name = "Sample Worksheet";  
  
                        // Write a column of values.  
                        // In the For loop, both the row index and array index start at 1.  
                        // Therefore the value of 4 at array index 0 is not included.  
                        for (int i = 1; i < values.Length; i++)  
                        {  
                            sheet.Cells[i, 1] = values[i];  
                        }  
  
                        // Suppress any alerts and save the file. Create the directory   
                        // if it does not exist. Overwrite the file if it exists.  
                        excelApp.DisplayAlerts = false;  
                        string folderPath = Path.GetDirectoryName(filePath);  
                        if (!Directory.Exists(folderPath))  
                        {  
                            Directory.CreateDirectory(folderPath);  
                        }  
                        wkbk.SaveAs(filePath);  
                }  
                catch  
                {  
                }  
                finally  
                {  
                    sheet = null;  
                    wkbk = null;  
  
                    // Close Excel.  
                    excelApp.Quit();  
                    excelApp = null;  
                }  
            }  
        }  
    }  
    ```  
  
8.  Speichern Sie das Projekt.  
  
9. Drücken Sie STRG+F5, um das Projekt zu erstellen und auszuführen. Überprüfen Sie, ob eine Excel-Arbeitsmappe an dem Speicherort erstellt wurde, der im Beispielcode angegebenen ist: C:\SampleFolder\SampleWorkbook.xls.  
  
##  <a name="BKMK_publishapp"></a> So veröffentlichen Sie die Anwendung auf einem Computer, auf dem eine andere Version von Microsoft Office installiert ist  
  
1.  Öffnen Sie das Projekt, das Sie in dieser exemplarischen Vorgehensweise erstellt haben, in Visual Studio.  
  
2.  Wählen Sie im Menü **Erstellen** die Option **CreateExcelWorkbook veröffentlichen** aus. Führen Sie die Schritte des Webpublishing-Assistenten aus, um eine installierbare Version der Anwendung zu erstellen. Weitere Informationen finden Sie unter [Veröffentlichungs-Assistent (Office-Entwicklung in Visual Studio)](https://msdn.microsoft.com/library/bb625071).  
  
3.  Installieren Sie die Anwendung auf einem Computer, auf dem .NET Framework 4 oder höher und eine andere Version von Excel installiert sind.  
  
4.  Führen Sie das installierte Programm aus, sobald die Installation abgeschlossen ist.  
  
5.  Überprüfen Sie, ob eine Excel-Arbeitsmappe an dem Speicherort erstellt wurde, der im Beispielcode angegebenen ist: C:\SampleFolder\SampleWorkbook.xls.  
  
## <a name="see-also"></a>Siehe auch  
 [Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys in Visual Studio (c#)](../../../../csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md)  
 [-link (C#-Compileroptionen)](../../../../csharp/language-reference/compiler-options/link-compiler-option.md)
