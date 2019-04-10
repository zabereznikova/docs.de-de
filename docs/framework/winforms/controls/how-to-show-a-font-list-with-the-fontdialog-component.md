---
title: 'Vorgehensweise: Anzeigen einer Schriftartenliste mit der FontDialog-Komponente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- fonts [Windows Forms], showing list
- FontDialog component [Windows Forms]
- fonts [Windows Forms], attributes
- Font property [Windows Forms], setting with FontDialog component
- Font dialog box [Windows Forms], displaying
- fonts [Windows Forms], selecting
ms.assetid: 35692c1b-0937-4b7a-9207-1ae6bdc244a0
ms.openlocfilehash: 40679136ea62a437009b308a8b206cf251b46222
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59307312"
---
# <a name="how-to-show-a-font-list-with-the-fontdialog-component"></a>Vorgehensweise: Anzeigen einer Schriftartenliste mit der FontDialog-Komponente
Die [FontDialog](fontdialog-component-windows-forms.md) -Komponente können Benutzer wählen Sie eine Schriftart sowie deren Anzeige ändern, z. B. Größe und Gewicht.  
  
 Im Dialogfeld ausgewählte Schriftart wird zurückgegeben, der <xref:System.Windows.Forms.FontDialog.Font%2A> Eigenschaft. Daher ist die Nutzung der vom Benutzer ausgewählten Schriftart so einfach wie das Lesen einer Eigenschaft.  
  
### <a name="to-select-font-properties-using-the-fontdialog-component"></a>Schriftarteigenschaften, die mit der FontDialog-Komponente auswählen  
  
1. Anzeigen des Dialogfelds mit der <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode.  
  
2. Verwenden der <xref:System.Windows.Forms.DialogResult> Eigenschaft, um zu bestimmen, wie Sie das Dialogfeld geschlossen wurde.  
  
3. Verwenden der <xref:System.Windows.Forms.FontDialog.Font%2A> Eigenschaft, um die gewünschte Schriftart fest.  
  
     Im folgenden Beispiel wird die <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Click> -Ereignishandler öffnet eine <xref:System.Windows.Forms.FontDialog> Komponente. Wenn eine Schriftart ausgewählt und der Benutzer klickt **OK**, <xref:System.Windows.Forms.FontDialog.Font%2A> Eigenschaft eine <xref:System.Windows.Forms.TextBox> Steuerelement, das auf dem Formular für die ausgewählte Schriftart festgelegt ist. Im Beispiel wird vorausgesetzt, das Formular enthält ein <xref:System.Windows.Forms.Button> -Steuerelement, ein <xref:System.Windows.Forms.TextBox> -Steuerelement, und ein <xref:System.Windows.Forms.FontDialog> Komponente.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       If FontDialog1.ShowDialog() = DialogResult.OK Then  
          TextBox1.Font = FontDialog1.Font  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(fontDialog1.ShowDialog() == DialogResult.OK)  
       {  
          textBox1.Font = fontDialog1.Font;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if(fontDialog1->ShowDialog() == DialogResult::OK)  
          {  
             textBox1->Font = fontDialog1->Font;  
          }  
       }  
    ```  
  
     (Visual C#- und [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) fügen Sie folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.FontDialog>
- [FontDialog-Komponente](fontdialog-component-windows-forms.md)
