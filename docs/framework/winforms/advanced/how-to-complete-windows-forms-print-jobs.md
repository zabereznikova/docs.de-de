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
ms.openlocfilehash: 62f67002bfbaf46e73bae06fdaff26efde865c06
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182600"
---
# <a name="how-to-complete-windows-forms-print-jobs"></a>Gewusst wie: Fertigstellen von Druckaufträgen in Windows Forms
Häufig bieten Textverarbeitungsaufträge und andere Anwendungen, die das Drucken beinhalten, die Möglichkeit, Benutzern eine Meldung anzuzeigen, dass ein Druckauftrag abgeschlossen ist. Sie können diese Funktionalität in Ihren <xref:System.Drawing.Printing.PrintDocument.EndPrint> Windows Forms <xref:System.Drawing.Printing.PrintDocument> bereitstellen, indem Sie das Ereignis der Komponente behandeln.  
  
 Das folgende Verfahren erfordert, dass Sie eine <xref:System.Drawing.Printing.PrintDocument> Windows-basierte Anwendung mit einer Komponente erstellt haben, die die Standardmethode zum Aktivieren des Druckens aus einer Windows-basierten Anwendung darstellt. Weitere Informationen zum Drucken aus <xref:System.Drawing.Printing.PrintDocument> Windows Forms mithilfe der Komponente finden Sie unter [Gewusst wie: Erstellen von Standard-Windows Forms Print Jobs](how-to-create-standard-windows-forms-print-jobs.md).  
  
### <a name="to-complete-a-print-job"></a>So schließen Sie einen Druckauftrag ab  
  
1. Legen <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> Sie die <xref:System.Drawing.Printing.PrintDocument> Eigenschaft der Komponente fest.  
  
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
  
     Im folgenden Codebeispiel wird ein Meldungsfeld angezeigt, das angibt, dass das Dokument den Druckvorgang beendet hat.  
  
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
  
     (Visual C- und Visual C++) Platzieren Sie den folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Drawing.Printing.PrintDocument>
- [Druckunterstützung in Windows Forms](windows-forms-print-support.md)
