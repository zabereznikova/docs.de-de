---
title: 'Vorgehensweise: Bestimmen von Seiteneigenschaften mit der PageSetupDialog-Komponente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- page properties
- page setup
- PageSetupDialog component
ms.assetid: 6dae05bc-c0fd-4357-bb93-841a1631d98f
ms.openlocfilehash: 7c65eb54bb95b9a20cd1e43f0d491af47985f2e0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59329205"
---
# <a name="how-to-determine-page-properties-using-the-pagesetupdialog-component"></a>Vorgehensweise: Bestimmen von Seiteneigenschaften mit der PageSetupDialog-Komponente
Mithilfe der [PageSetupDialog](pagesetupdialog-component-windows-forms.md) -Komponente können Benutzer das Layout, die Papiergröße und weitere Optionen für das Seitenlayout festlegen.  
  
 Sie müssen dazu eine Instanz der <xref:System.Drawing.Printing.PrintDocument> -Klasse angeben. Dabei handelt es sich um das Dokument, das gedruckt werden soll. Darüber hinaus benötigen Benutzer einen lokal oder über ein Netzwerk auf dem Computer installierten Drucker, da die <xref:System.Windows.Forms.PageSetupDialog> -Komponente darauf aufbauend die Formatierungsoptionen bestimmt, die dem Benutzer angezeigt werden.  
  
 Ein wichtiger Aspekt an der Arbeit mit der <xref:System.Windows.Forms.PageSetupDialog> -Komponente ist ihre Interaktionsweise mit der <xref:System.Drawing.Printing.PageSettings> -Klasse. Die <xref:System.Drawing.Printing.PageSettings> -Klasse wird verwendet, um die Einstellungen anzugeben, die die Druckweise einer Seite beeinflussen, z.B. die Ausrichtung, die Seitengröße und die Ränder. Jede dieser Einstellungen wird als Eigenschaft der <xref:System.Drawing.Printing.PageSettings> -Klasse dargestellt. Die <xref:System.Windows.Forms.PageSetupDialog> -Klasse ändert diese Eigenschaftswerte für eine bestimmte Instanz der <xref:System.Drawing.Printing.PageSettings> -Klasse, die mit dem Dokument verknüpft ist (als eine <xref:System.Drawing.Printing.PrintDocument.DefaultPageSettings%2A> -Eigenschaft dargestellt).  
  
### <a name="to-set-page-properties-using-the-pagesetupdialog-component"></a>So bestimmen Sie die Seiteneigenschaften mit der PageSetupDialog-Komponente  
  
1. Verwenden Sie die <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> -Methode, um das Dialogfeld anzuzeigen, und geben Sie das zu verwendende <xref:System.Drawing.Printing.PrintDocument> an.  
  
     Im folgenden Beispiel öffnet der <xref:System.Windows.Forms.Button> -Ereignishandler des <xref:System.Windows.Forms.Control.Click> -Steuerelements eine Instanz der <xref:System.Windows.Forms.PageSetupDialog> -Komponente. Ein vorhandenes Dokument wird in der <xref:System.Windows.Forms.PageSetupDialog.Document%2A> -Eigenschaft angegeben, und seine <xref:System.Drawing.Printing.PageSettings.Color%2A?displayProperty=nameWithType> -Eigenschaft wird auf `false`festgelegt.  
  
     Im Beispiel wird vorausgesetzt, das Formular enthält ein <xref:System.Windows.Forms.Button> -Steuerelement, ein <xref:System.Drawing.Printing.PrintDocument> Komponente, die mit dem Namen `myDocument`, und ein <xref:System.Windows.Forms.PageSetupDialog> Komponente.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles Button1.Click  
       ' The print document 'myDocument' used below  
       ' is merely for an example.  
       'You will have to specify your own print document.  
       PageSetupDialog1.Document = myDocument  
       ' Sets the print document's color setting to false,  
       ' so that the page will not be printed in color.  
       PageSetupDialog1.Document.DefaultPageSettings.Color = False  
       PageSetupDialog1.ShowDialog()  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       // The print document 'myDocument' used below  
       // is merely for an example.  
       // You will have to specify your own print document.  
       pageSetupDialog1.Document = myDocument;  
       // Sets the print document's color setting to false,  
       // so that the page will not be printed in color.  
       pageSetupDialog1.Document.DefaultPageSettings.Color = false;  
       pageSetupDialog1.ShowDialog();  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void button1_Click(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          // The print document 'myDocument' used below  
          // is merely for an example.  
          // You will have to specify your own print document.  
          pageSetupDialog1->Document = myDocument;  
          // Sets the print document's color setting to false,  
          // so that the page will not be printed in color.  
          pageSetupDialog1->Document->DefaultPageSettings->Color = false;  
          pageSetupDialog1->ShowDialog();  
       }  
    ```  
  
     (Visual C#- und [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) fügen Sie folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew   
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.PageSetupDialog>
- [Vorgehensweise: Erstellen von Druckaufträgen in Standard-Windows Forms](../advanced/how-to-create-standard-windows-forms-print-jobs.md)
- [PageSetupDialog-Komponente](pagesetupdialog-component-windows-forms.md)
