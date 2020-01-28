---
title: Vollständige Druckaufträge
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print jobs [Windows Forms], completing in Windows Forms
- printing [Windows Forms], print jobs
ms.assetid: 23ec74f7-34c5-4710-82a0-ee2914518548
ms.openlocfilehash: b8ef4fa05b2107247181e82b72389f9503507135
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746490"
---
# <a name="how-to-complete-windows-forms-print-jobs"></a>Gewusst wie: Fertigstellen von Druckaufträgen in Windows Forms
Häufig bieten Word-Prozessoren und andere Anwendungen, die das Drucken einschließen, die Möglichkeit, Benutzern eine Meldung anzuzeigen, dass ein Druckauftrag vollständig ist. Sie können diese Funktionalität in Ihrem Windows Forms bereitstellen, indem Sie das <xref:System.Drawing.Printing.PrintDocument.EndPrint>-Ereignis der <xref:System.Drawing.Printing.PrintDocument> Komponente behandeln.  
  
 Das folgende Verfahren erfordert, dass Sie eine Windows-basierte Anwendung mit einer <xref:System.Drawing.Printing.PrintDocument>-Komponente erstellt haben. Dies ist die Standardmethode zum Aktivieren des Drucks aus einer Windows-basierten Anwendung. Weitere Informationen zum Drucken aus Windows Forms mithilfe der <xref:System.Drawing.Printing.PrintDocument> Komponente finden Sie unter Gewusst [wie: Erstellen von Standard-Windows Forms Druckaufträgen](how-to-create-standard-windows-forms-print-jobs.md).  
  
### <a name="to-complete-a-print-job"></a>So vervollständigen Sie einen Druckauftrag  
  
1. Legen Sie die <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A>-Eigenschaft der <xref:System.Drawing.Printing.PrintDocument> Komponente fest.  
  
    ```vb  
    PrintDocument1.DocumentName = "MyTextFile"  
    ```  
  
    ```csharp  
    printDocument1.DocumentName = "MyTextFile";  
    ```  
  
    ```cpp  
    printDocument1->DocumentName = "MyTextFile";  
    ```  
  
2. Erstellen Sie Code zur Behandlung des <xref:System.Drawing.Printing.PrintDocument.EndPrint> -Ereignisses.  
  
     Im folgenden Codebeispiel wird ein Meldungs Feld angezeigt, das angibt, dass das Dokument den Druckvorgang abgeschlossen hat.  
  
    ```vb  
    Private Sub PrintDocument1_EndPrint(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintEventArgs) Handles PrintDocument1.EndPrint  
       MessageBox.Show(PrintDocument1.DocumentName + " has finished printing.")  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_EndPrint(object sender,   
    System.Drawing.Printing.PrintEventArgs e)  
    {  
       MessageBox.Show(printDocument1.DocumentName +   
          " has finished printing.");  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_EndPrint(System::Object ^ sender,  
          System::Drawing::Printing::PrintEventArgs ^ e)  
       {  
          MessageBox::Show(String::Concat(printDocument1->DocumentName,  
             " has finished printing."));  
       }  
    ```  
  
     (Visualisierung C# und Visualisierung C++) Fügen Sie den folgenden Code in den Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.printDocument1.EndPrint += new  
       System.Drawing.Printing.PrintEventHandler  
       (this.printDocument1_EndPrint);  
    ```  
  
    ```cpp  
    this->printDocument1->EndPrint += gcnew  
       System::Drawing::Printing::PrintEventHandler  
       (this, &Form1::printDocument1_EndPrint);  
    ```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Drawing.Printing.PrintDocument>
- [Druckunterstützung in Windows Forms](windows-forms-print-support.md)
