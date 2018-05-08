---
title: 'Gewusst wie: Drucken von Grafiken in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], printing
- printing [Windows Forms], graphics
ms.assetid: 32b891e6-52ff-4fea-a9ff-2ce5db20a4c6
ms.openlocfilehash: 8281e1e0a3d350c3b81e26bbe59c098536ef064e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-print-graphics-in-windows-forms"></a>Gewusst wie: Drucken von Grafiken in Windows Forms
In vielen Fällen sollten Sie das Drucken von Grafiken in der Windows-basierten Anwendung. Die <xref:System.Drawing.Graphics> -Klasse stellt Methoden zum Zeichnen von Objekten auf einem Gerät, z. B. einem Bildschirm oder Drucker.  
  
### <a name="to-print-graphics"></a>Zum Drucken von Grafiken  
  
1.  Hinzufügen einer <xref:System.Drawing.Printing.PrintDocument> -Komponente in Ihr Formular.  
  
2.  In der <xref:System.Drawing.Printing.PrintDocument.PrintPage> -Ereignishandler der <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> Eigenschaft von der <xref:System.Drawing.Printing.PrintPageEventArgs> Klasse weisen Sie den Drucker, auf welche Art von Grafiken zum Drucken an.  
  
     Das folgende Codebeispiel zeigt einen Ereignishandler verwendet, um eine blaue Ellipse in ein umschließendes Rechteck zu erstellen. Das Rechteck hat die folgenden Speicherort und Dimensionen: beginnend bei 100, 150 mit einer Breite von 250 und eine Höhe von 250.  
  
    ```vb  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillEllipse(Brushes.Blue, New Rectangle(100, 150, 250, 250))  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_PrintPage(object sender,   
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Blue,   
         new Rectangle(100, 150, 250, 250));  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Blue,  
             Rectangle(100, 150, 250, 250));  
       }  
    ```  
  
     (Visual C#- und [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) fügen Sie den folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    ```  
  
    ```cpp  
    this->printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing.Graphics>  
 <xref:System.Drawing.Brush>  
 [Druckunterstützung in Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)
