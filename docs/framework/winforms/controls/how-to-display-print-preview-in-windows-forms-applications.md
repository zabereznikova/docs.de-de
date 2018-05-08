---
title: 'Gewusst wie: Anzeigen der Seitenansicht in Windows Forms-Anwendungen'
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
ms.openlocfilehash: 1c1291ea675d823fab3052b0fa365cb2d4c31088
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-display-print-preview-in-windows-forms-applications"></a>Gewusst wie: Anzeigen der Seitenansicht in Windows Forms-Anwendungen
Sie können die <xref:System.Windows.Forms.PrintPreviewDialog> Steuerelement, damit Benutzer ein Dokument anzuzeigen, noch bevor es gedruckt wird.  
  
 Zu diesem Zweck müssen Sie eine Instanz von angeben der <xref:System.Drawing.Printing.PrintDocument> -Klasse; Dies ist das Dokument gedruckt werden. Weitere Informationen zum Verwenden der Seitenansicht mit der <xref:System.Drawing.Printing.PrintDocument> Komponente finden Sie unter [wie: Drucken in Windows Forms mithilfe von Seitenansicht](../../../../docs/framework/winforms/advanced/how-to-print-in-windows-forms-using-print-preview.md).  
  
> [!NOTE]
>  Verwenden der <xref:System.Windows.Forms.PrintPreviewDialog> Steuerelement zur Laufzeit müssen Benutzer einen Drucker, die auf ihrem Computer installiert werden, entweder lokal oder über ein Netzwerk aufweisen, da dies teilweise ist wie die <xref:System.Windows.Forms.PrintPreviewDialog> Komponente bestimmt, wie ein Dokument gedruckt aussehen wird.  
  
 Die <xref:System.Windows.Forms.PrintPreviewDialog> steuern verwendet der <xref:System.Drawing.Printing.PrinterSettings> Klasse. Darüber hinaus die <xref:System.Windows.Forms.PrintPreviewDialog> steuern verwendet der <xref:System.Drawing.Printing.PageSettings> -Klasse, ebenso wie die <xref:System.Windows.Forms.PrintPreviewDialog> -Komponente. Die zu druckenden Dokument im angegebenen der <xref:System.Windows.Forms.PrintPreviewDialog> des Steuerelements <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> Eigenschaft bezieht sich auf Instanzen von sowohl die <xref:System.Drawing.Printing.PrinterSettings> und <xref:System.Drawing.Printing.PageSettings> Klassen und diese dienen zum Rendern des Dokuments im Vorschaufenster.  
  
### <a name="to-view-pages-using-the-printpreviewdialog-control"></a>Zum Anzeigen von Seiten, die über das PrintPreviewDialog-Steuerelement  
  
-   Verwenden Sie die <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> -Methode, um das Dialogfeld anzuzeigen, und geben Sie das zu verwendende <xref:System.Drawing.Printing.PrintDocument> an.  
  
     Im folgenden Codebeispiel die <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Click> Ereignishandler öffnet eine Instanz von der <xref:System.Windows.Forms.PrintPreviewDialog> Steuerelement. Die zu druckenden Dokument wird angegeben, der <xref:System.Windows.Forms.PrintDialog.Document%2A> Eigenschaft. Im folgenden Beispiel wird keine zu druckenden Dokument angegeben.  
  
     Im Beispiel erfordert, dass das Formular verfügt über eine <xref:System.Windows.Forms.Button> -Steuerelement, eine <xref:System.Drawing.Printing.PrintDocument> Komponente, die mit dem Namen `myDocument`, und ein <xref:System.Windows.Forms.PrintPreviewDialog> Steuerelement.  
  
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
  
     (Visual c# [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) fügen Sie den folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [PrintDocument-Komponente](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)  
 [PrintPreviewDialog-Steuerelement](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 [Druckunterstützung in Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)  
 [Windows Forms](../../../../docs/framework/winforms/index.md)
