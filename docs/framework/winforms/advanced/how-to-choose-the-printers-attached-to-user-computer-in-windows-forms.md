---
title: 'Gewusst wie: Wählen Sie die Drucker aus, die an den Computer eines Benutzers angeschlossen sind'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- printing [Windows Forms], choosing printers
- printers [Windows Forms], choosing
ms.assetid: 63c1172b-2931-4ac0-953f-37f629494bbf
ms.openlocfilehash: 2afbccd02ef42a78d5eac1a01841516fca27c92e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182610"
---
# <a name="how-to-choose-the-printers-attached-to-a-users-computer-in-windows-forms"></a>Gewusst wie: Auswählen der einem Benutzercomputer zugewiesenen Drucker in Windows Forms
Häufig möchten Benutzer einen anderen Drucker als den Standarddrucker zum Drucken auswählen. Sie können es Benutzern ermöglichen, mithilfe der <xref:System.Windows.Forms.PrintDialog> -Komponente einen Drucker unter den Druckern auszuwählen, die derzeit installiert sind. Über die Komponente <xref:System.Windows.Forms.PrintDialog> wird das <xref:System.Windows.Forms.DialogResult> der Komponente <xref:System.Windows.Forms.PrintDialog> aufgezeichnet und für die Auswahl des Druckers verwendet.  
  
 In der folgenden Prozedur wird eine Textdatei ausgewählt, die auf dem Standarddrucker gedruckt werden soll. Die <xref:System.Windows.Forms.PrintDialog> -Klasse wird dann instanziiert.  
  
### <a name="to-choose-a-printer-and-then-print-a-file"></a>So wählen Sie einen Drucker aus und drucken eine Datei  
  
1. Wählen Sie den Drucker <xref:System.Windows.Forms.PrintDialog> aus, der mit der Komponente verwendet werden soll.  
  
     Im folgenden Codebeispiel werden zwei Ereignisse behandelt. Im ersten, <xref:System.Windows.Forms.Button> dem Ereignis <xref:System.Windows.Forms.Control.Click> eines <xref:System.Windows.Forms.PrintDialog> Steuerelements, wird die Klasse instanziiert, und <xref:System.Windows.Forms.DialogResult> der vom Benutzer ausgewählte Drucker wird in der Eigenschaft erfasst.  
  
     Im zweiten Ereignis, <xref:System.Drawing.Printing.PrintDocument.PrintPage> dem <xref:System.Drawing.Printing.PrintDocument> Ereignis der Komponente, wird ein Beispieldokument auf dem angegebenen Drucker gedruckt.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles Button1.Click  
       Dim PrintDialog1 As New PrintDialog()  
       PrintDialog1.Document = PrintDocument1  
       Dim result As DialogResult = PrintDialog1.ShowDialog()  
  
       If (result = DialogResult.OK) Then  
         PrintDocument1.Print()  
       End If
  
    End Sub  
  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillRectangle(Brushes.Red, New Rectangle(500, 500, 500, 500))
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       PrintDialog printDialog1 = new PrintDialog();  
       printDialog1.Document = printDocument1;  
       DialogResult result = printDialog1.ShowDialog();  
       if (result == DialogResult.OK)  
       {  
          printDocument1.Print();  
       }  
    }  
  
    private void printDocument1_PrintPage(object sender,
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Red,
         new Rectangle(500, 500, 500, 500));  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          PrintDialog ^ printDialog1 = gcnew PrintDialog();  
          printDialog1->Document = printDocument1;  
          System::Windows::Forms::DialogResult result =
             printDialog1->ShowDialog();  
          if (result == DialogResult::OK)  
          {  
             printDocument1->Print();  
          }  
       }  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Red,  
             Rectangle(500, 500, 500, 500));  
       }  
    ```  
  
     (Visual C- und Visual C++) Platzieren Sie den folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>Weitere Informationen

- [Druckunterstützung in Windows Forms](windows-forms-print-support.md)
