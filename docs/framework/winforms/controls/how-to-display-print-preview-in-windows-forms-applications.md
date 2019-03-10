---
title: 'Vorgehensweise: Anzeigen der Seitenansicht in Windows Forms-Anwendungen'
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
ms.openlocfilehash: 13510086edb13ff54f5551296c1b64c51873f649
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57715359"
---
# <a name="how-to-display-print-preview-in-windows-forms-applications"></a>Vorgehensweise: Anzeigen der Seitenansicht in Windows Forms-Anwendungen
Sie können die <xref:System.Windows.Forms.PrintPreviewDialog> Steuerelement, damit Benutzer ein Dokument anzuzeigen, noch bevor es gedruckt werden.  
  
 Zu diesem Zweck müssen Sie eine Instanz von angeben der <xref:System.Drawing.Printing.PrintDocument> Klasse; Dies ist das Dokument gedruckt werden sollen. Weitere Informationen zur Verwendung der Seitenansicht, mit der <xref:System.Drawing.Printing.PrintDocument> Komponente finden Sie unter [Vorgehensweise: In Windows Forms unter Verwendung der Seitenansicht drucken](../advanced/how-to-print-in-windows-forms-using-print-preview.md).  
  
> [!NOTE]
>  Verwenden der <xref:System.Windows.Forms.PrintPreviewDialog> Steuerelement zur Laufzeit benötigen Benutzer einen Drucker auf dem Computer installiert werden, entweder lokal oder über ein Netzwerk, da es sich teilweise handelt wie die <xref:System.Windows.Forms.PrintPreviewDialog> Anwendungskomponente bestimmt, wie ein Dokument gedruckt aussehen wird.  
  
 Die <xref:System.Windows.Forms.PrintPreviewDialog> -Steuerelement verwendet die <xref:System.Drawing.Printing.PrinterSettings> Klasse. Darüber hinaus die <xref:System.Windows.Forms.PrintPreviewDialog> -Steuerelement verwendet die <xref:System.Drawing.Printing.PageSettings> -Klasse, wie die <xref:System.Windows.Forms.PrintPreviewDialog> Komponente. Des zu druckenden Dokuments angegeben wird, der <xref:System.Windows.Forms.PrintPreviewDialog> des Steuerelements <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> Eigenschaft bezieht sich auf Instanzen von sowohl die <xref:System.Drawing.Printing.PrinterSettings> und <xref:System.Drawing.Printing.PageSettings> Klassen und diese werden verwendet, um das Dokument in einem Vorschaufenster zu rendern.  
  
### <a name="to-view-pages-using-the-printpreviewdialog-control"></a>Zum Anzeigen von Seiten, die über das PrintPreviewDialog-Steuerelement  
  
-   Verwenden Sie die <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> -Methode, um das Dialogfeld anzuzeigen, und geben Sie das zu verwendende <xref:System.Drawing.Printing.PrintDocument> an.  
  
     Das folgende Codebeispiel zeigt die <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Click> Ereignishandler öffnet eine Instanz von der <xref:System.Windows.Forms.PrintPreviewDialog> Steuerelement. Der zu druckenden Dokuments wird angegeben, der <xref:System.Windows.Forms.PrintDialog.Document%2A> Eigenschaft. Im folgenden Beispiel wird keine zu druckenden Dokuments angegeben.  
  
     Das Beispiel erfordert, dass das Formular enthält ein <xref:System.Windows.Forms.Button> -Steuerelement, ein <xref:System.Drawing.Printing.PrintDocument> Komponente, die mit dem Namen `myDocument`, und ein <xref:System.Windows.Forms.PrintPreviewDialog> Steuerelement.  
  
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
  
     (Visual c# [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) fügen Sie folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.  
  
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
