---
title: 'Vorgehensweise: Vollständige Windows Forms-Druckaufträge'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print jobs [Windows Forms], completing in Windows Forms
- printing [Windows Forms], print jobs
ms.assetid: 23ec74f7-34c5-4710-82a0-ee2914518548
ms.openlocfilehash: 1ae20e4fdc3a4fc3de8c462c355bcc700eddf22e
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711732"
---
# <a name="how-to-complete-windows-forms-print-jobs"></a>Vorgehensweise: Vollständige Windows Forms-Druckaufträge
In vielen Fällen bieten textverarbeitungs- und andere Anwendungen, bei denen Drucken die Möglichkeit, Benutzern eine Meldung angezeigt, dass ein Auftrag abgeschlossen ist. Sie können diese Funktionalität in Windows Forms bereitstellen, durch Behandeln der <xref:System.Drawing.Printing.PrintDocument.EndPrint> Ereignis die <xref:System.Drawing.Printing.PrintDocument> Komponente.  
  
 Das folgende Verfahren ist erforderlich, nach der Erstellung eine Windows-basierten Anwendung mit einem <xref:System.Drawing.Printing.PrintDocument> -Komponente auf, ist die Standardmethode zum Drucken aus einer Windows-basierten Anwendung aktivieren. Weitere Informationen zum Drucken von Windows Forms mithilfe der <xref:System.Drawing.Printing.PrintDocument> Komponente finden Sie unter [Vorgehensweise: Erstellen von standardmäßigen Windows Forms-Druckaufträge](how-to-create-standard-windows-forms-print-jobs.md).  
  
### <a name="to-complete-a-print-job"></a>Einen Auftrag abgeschlossen  
  
1.  Legen Sie die <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> Eigenschaft der <xref:System.Drawing.Printing.PrintDocument> Komponente.  
  
    ```vb  
    PrintDocument1.DocumentName = "MyTextFile"  
    ```  
  
    ```csharp  
    printDocument1.DocumentName = "MyTextFile";  
    ```  
  
    ```cpp  
    printDocument1->DocumentName = "MyTextFile";  
    ```  
  
2.  Erstellen Sie Code zur Behandlung des <xref:System.Drawing.Printing.PrintDocument.EndPrint> -Ereignisses.  
  
     Im folgenden Codebeispiel wird ein Meldungsfeld angezeigt, der angibt, dass das Dokument gedruckt wurde.  
  
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
  
     (Visual C#- und [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) fügen Sie folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.  
  
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
