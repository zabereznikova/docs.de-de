---
title: 'Gewusst wie: Drucken von Grafiken'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], printing
- printing [Windows Forms], graphics
ms.assetid: 32b891e6-52ff-4fea-a9ff-2ce5db20a4c6
ms.openlocfilehash: 15f3a507839430ce058302e7f5abd317ef84626f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182535"
---
# <a name="how-to-print-graphics-in-windows-forms"></a>Gewusst wie: Drucken von Grafiken in Windows Forms
Häufig sollten Sie Grafiken in Ihrer Windows-basierten Anwendung drucken. Die <xref:System.Drawing.Graphics> Klasse stellt Methoden zum Zeichnen von Objekten auf einem Gerät bereit, z. B. auf einem Bildschirm oder Drucker.  
  
### <a name="to-print-graphics"></a>So drucken Sie Grafiken  
  
1. Fügen <xref:System.Drawing.Printing.PrintDocument> Sie dem Formular eine Komponente hinzu.  
  
2. Verwenden <xref:System.Drawing.Printing.PrintDocument.PrintPage> Sie im Ereignishandler <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> die <xref:System.Drawing.Printing.PrintPageEventArgs> Eigenschaft der Klasse, um den Drucker anzuweisen, welche Art von Grafiken gedruckt werden sollen.  
  
     Das folgende Codebeispiel zeigt einen Ereignishandler, der zum Erstellen einer blauen Ellipse innerhalb eines angrenzenden Rechtecks verwendet wird. Das Rechteck hat die folgende Position und Abmessungen: beginnend bei 100, 150 mit einer Breite von 250 und einer Höhe von 250.  
  
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
  
     (Visual C- und Visual C++) Platzieren Sie den folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Brush>
- [Druckunterstützung in Windows Forms](windows-forms-print-support.md)
