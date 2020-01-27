---
title: Anzeigen der Seitenansicht in Windows Forms-apps
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print preview [Windows Forms], displaying
- printing [Windows Forms], print preview
- examples [Windows Forms], print preview
ms.assetid: e394134c-0886-4517-bd8d-edc4a3749eb5
ms.openlocfilehash: ac02339ad86e491cd047dcd4b0c8841374b3bb2e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745573"
---
# <a name="how-to-display-print-preview-in-windows-forms-applications"></a>Gewusst wie: Anzeigen der Seitenansicht in Windows Forms-Anwendungen
Sie können das <xref:System.Windows.Forms.PrintPreviewDialog>-Steuerelement verwenden, um Benutzern das Anzeigen eines Dokuments zu ermöglichen, das häufig vor dem Drucken angezeigt werden soll.  
  
 Zu diesem Zweck müssen Sie eine Instanz der <xref:System.Drawing.Printing.PrintDocument>-Klasse angeben. Dies ist das Dokument, das gedruckt werden soll. Weitere Informationen zum Verwenden der Druckvorschau mit der <xref:System.Drawing.Printing.PrintDocument>-Komponente finden Sie unter Gewusst [wie: Drucken in Windows Forms mithilfe](../advanced/how-to-print-in-windows-forms-using-print-preview.md)der Seitenansicht.  
  
> [!NOTE]
> Um das <xref:System.Windows.Forms.PrintPreviewDialog>-Steuerelement zur Laufzeit zu verwenden, muss auf dem Computer entweder lokal oder über ein Netzwerk ein Drucker installiert sein, da dies dazu führt, dass die <xref:System.Windows.Forms.PrintPreviewDialog> Komponente bestimmt, wie ein Dokument gedruckt wird.  
  
 Das <xref:System.Windows.Forms.PrintPreviewDialog>-Steuerelement verwendet die <xref:System.Drawing.Printing.PrinterSettings>-Klasse. Außerdem verwendet das <xref:System.Windows.Forms.PrintPreviewDialog>-Steuerelement die <xref:System.Drawing.Printing.PageSettings>-Klasse, ebenso wie die <xref:System.Windows.Forms.PrintPreviewDialog>-Komponente. Das in der <xref:System.Windows.Forms.PrintPreviewControl.Document%2A>-Eigenschaft des <xref:System.Windows.Forms.PrintPreviewDialog>-Steuer Elements angegebene Druck Dokument bezieht sich auf Instanzen der Klassen <xref:System.Drawing.Printing.PrinterSettings> und <xref:System.Drawing.Printing.PageSettings>. Diese werden verwendet, um das Dokument im Vorschaufenster zu Rendering.  
  
### <a name="to-view-pages-using-the-printpreviewdialog-control"></a>So zeigen Sie Seiten mit dem PrintPreviewDialog-Steuerelement an  
  
- Verwenden Sie die <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> -Methode, um das Dialogfeld anzuzeigen, und geben Sie das zu verwendende <xref:System.Drawing.Printing.PrintDocument> an.  
  
     Im folgenden Codebeispiel öffnet der <xref:System.Windows.Forms.Control.Click>-Ereignishandler des <xref:System.Windows.Forms.Button>-Steuer Elements eine Instanz des <xref:System.Windows.Forms.PrintPreviewDialog>-Steuer Elements. Das Druck Dokument wird in der <xref:System.Windows.Forms.PrintDialog.Document%2A>-Eigenschaft angegeben. Im folgenden Beispiel wird kein Druck Dokument angegeben.  
  
     Für das Beispiel ist es erforderlich, dass das Formular über ein <xref:System.Windows.Forms.Button>-Steuerelement, eine <xref:System.Drawing.Printing.PrintDocument> Komponente namens `myDocument`und ein <xref:System.Windows.Forms.PrintPreviewDialog>-Steuerelement verfügt.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       ' The print document 'myDocument' used below  
       ' is merely for an example.  
       ' You will have to specify your own print document.  
       PrintPreviewDialog1.Document = myDocument  
       PrintPreviewDialog1.ShowDialog()  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       // The print document 'myDocument' used below  
       // is merely for an example.  
       // You will have to specify your own print document.  
       printPreviewDialog1.Document = myDocument;  
       printPreviewDialog1.ShowDialog();  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // The print document 'myDocument' used below  
          // is merely for an example.  
          // You will have to specify your own print document.  
          printPreviewDialog1->Document = myDocument;  
          printPreviewDialog1->ShowDialog();  
       }  
    ```  
  
     (Visualisierung C#, Visualisierung C++) Fügen Sie den folgenden Code in den Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>Siehe auch

- [PrintDocument-Komponente](printdocument-component-windows-forms.md)
- [PrintPreviewDialog-Steuerelement](printpreviewdialog-control-windows-forms.md)
- [Druckunterstützung in Windows Forms](../advanced/windows-forms-print-support.md)
- [Windows Forms](../index.md)
