---
title: 'Vorgehensweise: Erstellen von standardmäßigen Druckaufträgen in Windows Forms'
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
ms.openlocfilehash: 816da93218e20f73f16c14769ed1a549dd3d8eb3
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59335406"
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a>Vorgehensweise: Erstellen von standardmäßigen Druckaufträgen in Windows Forms
Die Grundlage für das Drucken in Windows Forms ist die <xref:System.Drawing.Printing.PrintDocument> Komponente – genauer gesagt die <xref:System.Drawing.Printing.PrintDocument.PrintPage> Ereignis. Durch das Schreiben von Code zum Behandeln der <xref:System.Drawing.Printing.PrintDocument.PrintPage> Ereignis können Sie angeben, was gedruckt und wie es gedruckt.  
  
### <a name="to-create-a-print-job"></a>Um einen Druckauftrag zu erstellen.  
  
1. Hinzufügen einer <xref:System.Drawing.Printing.PrintDocument> Ihrem Formular.  
  
2. Erstellen Sie Code zur Behandlung des <xref:System.Drawing.Printing.PrintDocument.PrintPage> -Ereignisses.  
  
     Sie müssen Ihre eigene Logik zum Drucken zu codieren. Darüber hinaus müssen Sie sich an das Material, das gedruckt werden.  
  
     Im folgenden Codebeispiel wird eine Beispielgrafik in der Form eines roten Rechtecks in erstellt die <xref:System.Drawing.Printing.PrintDocument.PrintPage> Ereignishandler als Material zu druckenden fungieren.  
  
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
  
     (Visual C#- und [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) fügen Sie folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.  
  
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
  
     Sie sollten auch zum Schreiben von Code für die <xref:System.Drawing.Printing.PrintDocument.BeginPrint> und <xref:System.Drawing.Printing.PrintDocument.EndPrint> Ereignisse, die durch eine ganze Zahl, der die Gesamtzahl der Seiten darstellt, drucken, die abgezogen wird bei jeder gedruckten Seite.  
  
    > [!NOTE]
    >  Sie können Hinzufügen einer <xref:System.Windows.Forms.PrintDialog> Ihrem Formular eine saubere und effizienten Benutzeroberfläche (UI) für Ihre Benutzer bereitstellen. Festlegen der <xref:System.Windows.Forms.PrintDialog.Document%2A> Eigenschaft der <xref:System.Windows.Forms.PrintDialog> Komponente ermöglicht, die Sie zum Festlegen von Eigenschaften, die im Zusammenhang mit dem Drucken dokumentieren Sie arbeiten mit in Ihrem Formular. Weitere Informationen zu den <xref:System.Windows.Forms.PrintDialog> Komponente finden Sie unter [PrintDialog-Komponente](../controls/printdialog-component-windows-forms.md).  
  
     Weitere Informationen zu den Besonderheiten von Windows Forms Druckaufträge, wie Sie einen Druckauftrag programmgesteuert erstellen finden Sie unter <xref:System.Drawing.Printing.PrintPageEventArgs>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Drawing.Printing.PrintDocument>
- [Druckunterstützung in Windows Forms](windows-forms-print-support.md)
