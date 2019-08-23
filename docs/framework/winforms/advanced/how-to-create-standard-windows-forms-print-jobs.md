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
ms.openlocfilehash: 44673e6b26f088e71813aaac26c4b9a03429597a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938241"
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a>Vorgehensweise: Erstellen von standardmäßigen Druckaufträgen in Windows Forms
Die Grundlage für das Drucken in Windows Forms ist <xref:System.Drawing.Printing.PrintDocument> die Komponente – genauer gesagt das <xref:System.Drawing.Printing.PrintDocument.PrintPage> Ereignis. Wenn Sie Code schreiben, um <xref:System.Drawing.Printing.PrintDocument.PrintPage> das Ereignis zu behandeln, können Sie angeben, was gedruckt und gedruckt werden soll.  
  
### <a name="to-create-a-print-job"></a>So erstellen Sie einen Druckauftrag  
  
1. Fügen Sie <xref:System.Drawing.Printing.PrintDocument> dem Formular eine Komponente hinzu.  
  
2. Erstellen Sie Code zur Behandlung des <xref:System.Drawing.Printing.PrintDocument.PrintPage> -Ereignisses.  
  
     Sie müssen ihre eigene Druck Logik programmieren. Außerdem müssen Sie das Material angeben, das gedruckt werden soll.  
  
     Im folgenden Codebeispiel wird eine Beispiel Grafik in der Form eines roten Rechtecks im-Ereignishandler <xref:System.Drawing.Printing.PrintDocument.PrintPage> erstellt, der als Material zum Drucken fungiert.  
  
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
  
     (Visualisierung C# und Visualisierung C++) Fügen Sie den folgenden Code in den Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.  
  
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
  
     Möglicherweise möchten Sie auch Code für das- <xref:System.Drawing.Printing.PrintDocument.BeginPrint> Ereignis <xref:System.Drawing.Printing.PrintDocument.EndPrint> und das-Ereignis schreiben, z. b. eine ganze Zahl, die die Gesamtzahl der zu druckenden Seiten darstellt, die bei jeder Seite gedruckt wird.  
  
    > [!NOTE]
    > Sie können dem Formular <xref:System.Windows.Forms.PrintDialog> eine Komponente hinzufügen, um Benutzern eine saubere und effiziente Benutzeroberfläche zur Verfügung zu stellen. Durch Festlegen <xref:System.Windows.Forms.PrintDialog.Document%2A> der-Eigenschaft <xref:System.Windows.Forms.PrintDialog> der-Komponente können Sie Eigenschaften festlegen, die sich auf das Druck Dokument beziehen, mit dem Sie in Ihrem Formular arbeiten. Weitere Informationen <xref:System.Windows.Forms.PrintDialog> zur-Komponente finden Sie unter [PrintDialog-Komponente](../controls/printdialog-component-windows-forms.md).  
  
     Weitere Informationen zu den Besonderheiten Windows Forms Druckaufträgen, einschließlich der programmgesteuerten Erstellung eines Druckauftrags, finden <xref:System.Drawing.Printing.PrintPageEventArgs>Sie unter.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Drawing.Printing.PrintDocument>
- [Druckunterstützung in Windows Forms](windows-forms-print-support.md)
