---
title: Erstellen von Standarddruckaufträgen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- printing [Windows Forms]
- printing [Windows Forms], creating print jobs
- printing [Visual Basic], in Windows applications
ms.assetid: 03342b90-9cfe-40b2-838b-b479a13c5dea
ms.openlocfilehash: d9607de7c74132e0d7dce605b16d62c79b7dbccb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182566"
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a>Gewusst wie: Erstellen von standardmäßigen Druckaufträgen in Windows Forms
Die Grundlage für das Drucken <xref:System.Drawing.Printing.PrintDocument> in Windows Forms <xref:System.Drawing.Printing.PrintDocument.PrintPage> ist die Komponente – genauer gesagt das Ereignis. Durch Das Schreiben <xref:System.Drawing.Printing.PrintDocument.PrintPage> von Code für das Ereignis können Sie angeben, was gedruckt und gedruckt werden soll.  
  
### <a name="to-create-a-print-job"></a>So erstellen Sie einen Druckauftrag  
  
1. Fügen <xref:System.Drawing.Printing.PrintDocument> Sie dem Formular eine Komponente hinzu.  
  
2. Erstellen Sie Code zur Behandlung des <xref:System.Drawing.Printing.PrintDocument.PrintPage> -Ereignisses.  
  
     Sie müssen Ihre eigene Drucklogik codieren. Darüber hinaus müssen Sie das zu druckende Material angeben.  
  
     Im folgenden Codebeispiel wird im <xref:System.Drawing.Printing.PrintDocument.PrintPage> Ereignishandler eine Beispielgrafik in Form eines roten Rechtecks erstellt, die als zu druckendes Material fungiert.  
  
    ```vb  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillRectangle(Brushes.Red, New Rectangle(500, 500, 500, 500))  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_PrintPage(object sender,
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Red,
         new Rectangle(500, 500, 500, 500));  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Red,  
             Rectangle(500, 500, 500, 500));  
       }  
    ```  
  
     (Visual C- und Visual C++) Platzieren Sie den folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    ```  
  
    ```cpp  
    printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    ```  
  
     Sie können auch Code für <xref:System.Drawing.Printing.PrintDocument.BeginPrint> <xref:System.Drawing.Printing.PrintDocument.EndPrint> die und Ereignisse schreiben, z. B. eine ganze Zahl, die die Gesamtzahl der zu druckenden Seiten darstellt, die beim Drucken jeder Seite dekrementiert wird.  
  
    > [!NOTE]
    > Sie können <xref:System.Windows.Forms.PrintDialog> dem Formular eine Komponente hinzufügen, um ihren Benutzern eine saubere und effiziente Benutzeroberfläche bereitzustellen. Durch <xref:System.Windows.Forms.PrintDialog.Document%2A> Festlegen der <xref:System.Windows.Forms.PrintDialog> Eigenschaft der Komponente können Sie Eigenschaften festlegen, die sich auf das Druckdokument beziehen, mit dem Sie im Formular arbeiten. Weitere Informationen zur <xref:System.Windows.Forms.PrintDialog> Komponente finden Sie unter [PrintDialog-Komponente](../controls/printdialog-component-windows-forms.md).  
  
     Weitere Informationen zu den Besonderheiten von Windows Forms-Druckaufträgen, z. B. zum programmgesteuerten Erstellen eines Druckauftrags, finden Sie unter <xref:System.Drawing.Printing.PrintPageEventArgs>.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Drawing.Printing.PrintDocument>
- [Druckunterstützung in Windows Forms](windows-forms-print-support.md)
