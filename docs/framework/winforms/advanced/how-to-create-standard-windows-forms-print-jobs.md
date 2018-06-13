---
title: 'Gewusst wie: Erstellen von standardmäßigen Druckaufträgen in Windows Forms'
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
ms.openlocfilehash: b580268a6af3f56f240a1c511c3d473a4a5ddc15
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33522332"
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a>Gewusst wie: Erstellen von standardmäßigen Druckaufträgen in Windows Forms
Die Grundlage für das Drucken in Windows Forms ist die <xref:System.Drawing.Printing.PrintDocument> Komponente – genauer gesagt, die <xref:System.Drawing.Printing.PrintDocument.PrintPage> Ereignis. Durch das Schreiben von Code zum Behandeln der <xref:System.Drawing.Printing.PrintDocument.PrintPage> -Ereignis können Sie angeben, was gedruckt und wie es gedruckt.  
  
### <a name="to-create-a-print-job"></a>So erstellen einen Druckauftrag  
  
1.  Hinzufügen einer <xref:System.Drawing.Printing.PrintDocument> -Komponente in Ihr Formular.  
  
2.  Erstellen Sie Code zur Behandlung des <xref:System.Drawing.Printing.PrintDocument.PrintPage>-Ereignisses.  
  
     Sie müssen Ihre eigene Logik zum Drucken zu codieren. Darüber hinaus müssen Sie das Material zu druckende angegeben.  
  
     Im folgenden Codebeispiel wird eine Beispielgrafik in der Form eines roten Rechtecks erstellt, der <xref:System.Drawing.Printing.PrintDocument.PrintPage> Ereignishandler fungieren als Material, das gedruckt werden soll.  
  
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
  
     (Visual C#- und [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) fügen Sie den folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.  
  
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
  
     Sie sollten auch zum Schreiben von Code für die <xref:System.Drawing.Printing.PrintDocument.BeginPrint> und <xref:System.Drawing.Printing.PrintDocument.EndPrint> Ereignisse, die eine ganze Zahl, die die Gesamtanzahl der Seiten darstellt, drucken, das jede Seite gedruckt wird wieder um eins erniedrigt ist.  
  
    > [!NOTE]
    >  Sie können Hinzufügen einer <xref:System.Windows.Forms.PrintDialog> -Komponente zum Formular an eine übersichtliche und effiziente Benutzeroberfläche (UI) für Ihre Benutzer bereitzustellen. Festlegen der <xref:System.Windows.Forms.PrintDialog.Document%2A> Eigenschaft von der <xref:System.Windows.Forms.PrintDialog> Komponente ermöglicht, die Sie zum Festlegen von Eigenschaften, die im Zusammenhang mit dem Druckserver dokumentieren Sie arbeiten mit auf dem Formular. Weitere Informationen zu den <xref:System.Windows.Forms.PrintDialog> Komponente finden Sie unter [PrintDialog-Komponente](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md).  
  
     Weitere Informationen zu den Besonderheiten von Windows Forms-Druckaufträge, einschließlich der Erstellung ein Druckauftrags programmgesteuert erstellen, finden Sie unter <xref:System.Drawing.Printing.PrintPageEventArgs>.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing.Printing.PrintDocument>  
 [Druckunterstützung in Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)
