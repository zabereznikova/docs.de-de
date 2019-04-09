---
title: 'Vorgehensweise: Programmgesteuertes Auswählen von Text im TextBox-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], selecting text programmatically
- text boxes [Windows Forms], selecting text programmatically
- text [Windows Forms], selecting in text boxes programmatically
ms.assetid: 8c591546-6a01-45c7-8e03-f78431f903b1
ms.openlocfilehash: f96ac69f16eefb5bf4a0625ff83e207c289a105b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59111435"
---
# <a name="how-to-select-text-in-the-windows-forms-textbox-control"></a>Vorgehensweise: Programmgesteuertes Auswählen von Text im TextBox-Steuerelement in Windows Forms
Sie können Text programmgesteuert in das Windows Forms auswählen <xref:System.Windows.Forms.TextBox> Steuerelement. Wenn Sie eine Funktion, die Text nach einer bestimmten Zeichenfolge sucht erstellen, können Sie beispielsweise den Text, den Reader, der die gefundene Zeichenfolge Position visuell Warnung auswählen.  
  
### <a name="to-select-text-programmatically"></a>Text programmgesteuert ausgewählt  
  
1.  Legen Sie die <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> Eigenschaft an den Anfang des Texts, die Sie auswählen möchten.  
  
     Die <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> Eigenschaft ist eine Zahl, die die Einfügemarke innerhalb der Zeichenfolge des Texts angibt, wobei 0 die äußerste linke Position. Wenn die <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> -Eigenschaftensatz auf einen Wert gleich oder größer als die Anzahl der Zeichen in das Textfeld, das die Einfügemarke befindet sich hinter dem letzten Zeichen.  
  
2.  Legen Sie die <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> Eigenschaft, um die Länge des Texts, die Sie auswählen möchten.  
  
     Die <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> Eigenschaft ist ein numerischer Wert, der die Breite der Einfügemarke festlegt. Festlegen der <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> auf eine Zahl größer als 0 bewirkt, diese Anzahl von Zeichen dass, die ausgewählt werden, beginnend mit der aktuellen Einfügemarke.  
  
3.  (Optional) Zugriff auf den markierten Text durch die <xref:System.Windows.Forms.TextBoxBase.SelectedText%2A> Eigenschaft.  
  
     Der Code unten wählt den Inhalt mit einem Feld beim des Steuerelements <xref:System.Windows.Forms.Control.Enter> Ereignis auftritt. In diesem Beispiel wird überprüft, ob das Textfeld einen Wert für die <xref:System.Windows.Forms.TextBox.Text%2A> -Eigenschaft, die nicht `null` oder eine leere Zeichenfolge. Wenn das Textfeld den Fokus erhält, ist der aktuelle Text in das Textfeld ausgewählt. Die `TextBox1_Enter` Ereignishandler muss gebunden sein, auf das Steuerelement; Weitere Informationen, wie unter [Vorgehensweise: Erstellen von Ereignishandlern für Windows Forms zur Laufzeit](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
     Zum Testen dieses Beispiels, drücken Sie die Tab-Taste, bis das Textfeld den Fokus besitzt. Wenn Sie in das Textfeld klicken, ist der Text nicht ausgewählt.  
  
    ```vb  
    Private Sub TextBox1_Enter(ByVal sender As Object, ByVal e As System.EventArgs) Handles TextBox1.Enter  
       If (Not String.IsNullOrEmpty(TextBox1.Text)) Then  
          TextBox1.SelectionStart = 0  
          TextBox1.SelectionLength = TextBox1.Text.Length  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_Enter(object sender, System.EventArgs e){  
       if (!String.IsNullOrEmpty(textBox1.Text))  
       {  
          textBox1.SelectionStart = 0;  
          textBox1.SelectionLength = textBox1.Text.Length;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void textBox1_Enter(System::Object ^ sender,  
          System::EventArgs ^ e) {  
       if (!System::String::IsNullOrEmpty(textBox1->Text))  
       {  
          textBox1->SelectionStart = 0;  
          textBox1->SelectionLength = textBox1->Text->Length;  
       }  
    }  
    ```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.TextBox>
- [Übersicht über das TextBox-Steuerelement](textbox-control-overview-windows-forms.md)
- [Vorgehensweise: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Vorgehensweise: Erstellen eines Kennwort-Textfelds mit dem TextBox-Steuerelement in Windows Forms](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Vorgehensweise: Erstellen eines schreibgeschützten Textfelds](how-to-create-a-read-only-text-box-windows-forms.md)
- [Vorgehensweise: Setzen von Anführungszeichen in Zeichenfolgen](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Vorgehensweise: Anzeigen mehrerer Zeilen im TextBox-Steuerelement in Windows Forms](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [TextBox-Steuerelement](textbox-control-windows-forms.md)
