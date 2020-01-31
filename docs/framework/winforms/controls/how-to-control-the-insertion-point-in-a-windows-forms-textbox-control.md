---
title: Steuern der Einfügemarke im TextBox-Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], insertion point
- insertion points [Windows Forms], TextBox controls
- text boxes [Windows Forms], controlling insertion point
ms.assetid: 5bee7d34-5121-429e-ab1f-d8ff67bc74c1
ms.openlocfilehash: fd4803820921f0c922a4ce885f809abee8fd4c6c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742201"
---
# <a name="how-to-control-the-insertion-point-in-a-windows-forms-textbox-control"></a>Gewusst wie: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms
Wenn ein Windows Forms <xref:System.Windows.Forms.TextBox>-Steuerelement den Fokus erhält, wird die Standard Einfügung innerhalb des Textfelds auf der linken Seite von vorhandenem Text angezeigt. Der Benutzer kann die Einfügemarke mit der Tastatur oder der Maus verschieben. Wenn das Textfeld den Fokus verliert und dann wieder erhält, ist die Einfügemarke an der Stelle, an der der Benutzer Sie zuletzt platziert hat.  
  
 In einigen Fällen kann dieses Verhalten dem Benutzer zu einem verwirrend werden. In einer Textverarbeitungsanwendung erwartet der Benutzer möglicherweise, dass neue Zeichen nach vorhandenem Text angezeigt werden. In einer Dateneingabe Anwendung erwartet der Benutzer möglicherweise, dass neue Zeichen einen vorhandenen Eintrag ersetzen. Mit den Eigenschaften <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> und <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> können Sie das Verhalten an ihren Zweck anpassen.  
  
### <a name="to-control-the-insertion-point-in-a-textbox-control"></a>So steuern Sie die Einfügemarke in einem TextBox-Steuerelement  
  
1. Legen Sie für die <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A>-Eigenschaft einen geeigneten Wert fest. NULL platziert die Einfügemarke direkt links vom ersten Zeichen.  
  
2. Optionale Legen Sie die <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A>-Eigenschaft auf die Länge des Texts fest, den Sie auswählen möchten.  
  
     Der folgende Code gibt immer die Einfügemarke auf 0 zurück. Der `TextBox1_Enter` Ereignishandler muss an das-Steuerelement gebunden werden. Weitere Informationen finden Sie unter [Erstellen von Ereignis Handlern in Windows Forms](../creating-event-handlers-in-windows-forms.md).  
  
    ```vb  
    Private Sub TextBox1_Enter(ByVal sender As Object, ByVal e As System.EventArgs) Handles TextBox1.Enter  
       TextBox1.SelectionStart = 0  
       TextBox1.SelectionLength = 0  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_Enter(Object sender, System.EventArgs e) {  
       textBox1.SelectionStart = 0;  
       textBox1.SelectionLength = 0;  
    }  
    ```  
  
    ```cpp  
    private:  
       void textBox1_Enter(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          textBox1->SelectionStart = 0;  
          textBox1->SelectionLength = 0;  
       }  
    ```  
  
## <a name="making-the-insertion-point-visible-by-default"></a>Standardmäßiges sichtbar machen der Einfügemarke  
 Die <xref:System.Windows.Forms.TextBox> Einfügemarke ist standardmäßig nur in einem neuen Format sichtbar, wenn das <xref:System.Windows.Forms.TextBox> Steuerelement in der Aktivier Reihenfolge an erster Stelle steht. Andernfalls wird die Einfügemarke nur angezeigt, wenn Sie die <xref:System.Windows.Forms.TextBox> den Fokus mit der Tastatur oder der Maus versehen.  
  
#### <a name="to-make-the-text-box-insertion-point-visible-by-default-on-a-new-form"></a>So machen Sie die Textfeld-Einfügemarke standardmäßig in einem neuen Formular sichtbar  
  
- Legen Sie die <xref:System.Windows.Forms.Control.TabIndex%2A>-Eigenschaft des <xref:System.Windows.Forms.TextBox>-Steuer Elements auf `0`fest.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.TextBox>
- [Übersicht über das TextBox-Steuerelement](textbox-control-overview-windows-forms.md)
- [Vorgehensweise: Erstellen eines Kennwort-Textfelds mit dem TextBox-Steuerelement in Windows Forms](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Vorgehensweise: Erstellen eines schreibgeschützten Textfelds](how-to-create-a-read-only-text-box-windows-forms.md)
- [Gewusst wie: Setzen von Anführungszeichen in Zeichenfolgen](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Vorgehensweise: Programmgesteuertes Auswählen von Text im TextBox-Steuerelement in Windows Forms](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Vorgehensweise: Anzeigen mehrerer Zeilen im TextBox-Steuerelement in Windows Forms](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [TextBox-Steuerelement](textbox-control-windows-forms.md)
