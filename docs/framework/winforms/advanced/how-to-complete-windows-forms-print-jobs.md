---
title: "Gewusst wie: Fertigstellen von Druckaufträgen in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print jobs [Windows Forms], completing in Windows Forms
- printing [Windows Forms], print jobs
ms.assetid: 23ec74f7-34c5-4710-82a0-ee2914518548
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9decba052589bfcc3ecd7b2861dad51e9c51378a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-complete-windows-forms-print-jobs"></a>Gewusst wie: Fertigstellen von Druckaufträgen in Windows Forms
In vielen Fällen bietet textverarbeitungs- und anderen Anwendungen, die Druck betreffen die Möglichkeit, Benutzern eine Meldung anzuzeigen, dass ein Auftrag abgeschlossen ist. Sie können diese Funktionalität in Windows Forms bereitstellen, durch Behandeln der <xref:System.Drawing.Printing.PrintDocument.EndPrint> -Ereignis für die <xref:System.Drawing.Printing.PrintDocument> Komponente.  
  
 Das folgende Verfahren erfordert, dass es sich bei der Erstellung einer Windows-basierten Anwendung mit einem <xref:System.Drawing.Printing.PrintDocument> -Komponente darauf, also die Standardmethode zum Drucken aus einer Windows-basierten Anwendung aktivieren. Weitere Informationen zum Drucken von Windows Forms mithilfe der <xref:System.Drawing.Printing.PrintDocument> Komponente finden Sie unter [Vorgehensweise: Standard Windows Forms-Druckaufträge erstellen](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md).  
  
### <a name="to-complete-a-print-job"></a>Zum Abschließen eines Druckauftrags  
  
1.  Legen Sie die <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> Eigenschaft von der <xref:System.Drawing.Printing.PrintDocument> Komponente.  
  
    ```vb  
    PrintDocument1.DocumentName = "MyTextFile"  
    ```  
  
    ```csharp  
    printDocument1.DocumentName = "MyTextFile";  
    ```  
  
    ```cpp  
    printDocument1->DocumentName = "MyTextFile";  
    ```  
  
2.  Erstellen Sie Code zur Behandlung des <xref:System.Drawing.Printing.PrintDocument.EndPrint>-Ereignisses.  
  
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
  
     ([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] und [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Fügen Sie den folgenden Code in den Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.  
  
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
 <xref:System.Drawing.Printing.PrintDocument>  
 [Druckunterstützung in Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)
