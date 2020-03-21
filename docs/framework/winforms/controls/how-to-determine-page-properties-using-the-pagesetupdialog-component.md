---
title: 'Gewusst wie: Bestimmen von Seiteneigenschaften mit der PageSetupDialog-Komponente'
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
ms.openlocfilehash: 8a015c199193dfd9c43bec53cc93cbf9dc201413
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142042"
---
# <a name="how-to-determine-page-properties-using-the-pagesetupdialog-component"></a>Gewusst wie: Bestimmen von Seiteneigenschaften mit der PageSetupDialog-Komponente
Mithilfe der [PageSetupDialog](pagesetupdialog-component-windows-forms.md) -Komponente können Benutzer das Layout, die Papiergröße und weitere Optionen für das Seitenlayout festlegen.  
  
 Sie müssen dazu eine Instanz der <xref:System.Drawing.Printing.PrintDocument> -Klasse angeben. Dabei handelt es sich um das Dokument, das gedruckt werden soll. Darüber hinaus benötigen Benutzer einen lokal oder über ein Netzwerk auf dem Computer installierten Drucker, da die <xref:System.Windows.Forms.PageSetupDialog> -Komponente darauf aufbauend die Formatierungsoptionen bestimmt, die dem Benutzer angezeigt werden.  
  
 Ein wichtiger Aspekt an der Arbeit mit der <xref:System.Windows.Forms.PageSetupDialog> -Komponente ist ihre Interaktionsweise mit der <xref:System.Drawing.Printing.PageSettings> -Klasse. Die <xref:System.Drawing.Printing.PageSettings> -Klasse wird verwendet, um die Einstellungen anzugeben, die die Druckweise einer Seite beeinflussen, z.B. die Ausrichtung, die Seitengröße und die Ränder. Jede dieser Einstellungen wird als Eigenschaft der <xref:System.Drawing.Printing.PageSettings> -Klasse dargestellt. Die <xref:System.Windows.Forms.PageSetupDialog> -Klasse ändert diese Eigenschaftswerte für eine bestimmte Instanz der <xref:System.Drawing.Printing.PageSettings> -Klasse, die mit dem Dokument verknüpft ist (als eine <xref:System.Drawing.Printing.PrintDocument.DefaultPageSettings%2A> -Eigenschaft dargestellt).  
  
### <a name="to-set-page-properties-using-the-pagesetupdialog-component"></a>So bestimmen Sie die Seiteneigenschaften mit der PageSetupDialog-Komponente  
  
1. Verwenden Sie die <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> -Methode, um das Dialogfeld anzuzeigen, und geben Sie das zu verwendende <xref:System.Drawing.Printing.PrintDocument> an.  
  
     Im folgenden Beispiel öffnet der <xref:System.Windows.Forms.Button> -Ereignishandler des <xref:System.Windows.Forms.Control.Click> -Steuerelements eine Instanz der <xref:System.Windows.Forms.PageSetupDialog> -Komponente. Ein vorhandenes Dokument wird in der <xref:System.Windows.Forms.PageSetupDialog.Document%2A> -Eigenschaft angegeben, und seine <xref:System.Drawing.Printing.PageSettings.Color%2A?displayProperty=nameWithType> -Eigenschaft wird auf `false`festgelegt.  
  
     Im Beispiel wird davon <xref:System.Windows.Forms.Button> ausgegangen, <xref:System.Drawing.Printing.PrintDocument> dass `myDocument`das <xref:System.Windows.Forms.PageSetupDialog> Formular über ein Steuerelement, eine Komponente mit dem Namen und eine Komponente verfügt.  
  
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
  
     (Visual C- und Visual C++) Platzieren Sie den folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.PageSetupDialog>
- [Gewusst wie: Erstellen von standardmäßigen Druckaufträgen in Windows Forms](../advanced/how-to-create-standard-windows-forms-print-jobs.md)
- [PageSetupDialog-Komponente](pagesetupdialog-component-windows-forms.md)
