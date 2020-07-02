---
title: Text im TextBox-Steuerelement auswählen
description: Erfahren Sie, wie Sie Textprogramm gesteuert im TextBox-Steuerelement Windows Forms auswählen. Erfahren Sie außerdem, wie Sie den Reader über die Position der gefundenen Zeichenfolge visuell benachrichtigen.
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
ms.openlocfilehash: b8fdaff76461c4d6766dfc6afaef5e814d982834
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621560"
---
# <a name="how-to-select-text-in-the-windows-forms-textbox-control"></a>Vorgehensweise: Programmgesteuertes Auswählen von Text im TextBox-Steuerelement in Windows Forms
Sie können Textprogramm gesteuert im Windows Forms Steuerelement auswählen <xref:System.Windows.Forms.TextBox> . Wenn Sie z. b. eine Funktion erstellen, mit der Text nach einer bestimmten Zeichenfolge durchsucht wird, können Sie den Text auswählen, um den Reader visuell über die Position der gefundenen Zeichenfolge zu benachrichtigen.  
  
### <a name="to-select-text-programmatically"></a>So wählen Sie Textprogramm gesteuert aus  
  
1. Legen Sie die- <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> Eigenschaft auf den Anfang des Texts fest, den Sie auswählen möchten.  
  
     Die- <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> Eigenschaft ist eine Zahl, die die Einfügemarke in der Text Zeichenfolge angibt, wobei 0 die linke Position ist. Wenn die <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> Eigenschaft auf einen Wert festgelegt ist, der gleich oder größer als die Anzahl der Zeichen im Textfeld ist, wird die Einfügemarke nach dem letzten Zeichen platziert.  
  
2. Legen Sie die- <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> Eigenschaft auf die Länge des Texts fest, den Sie auswählen möchten.  
  
     Die- <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> Eigenschaft ist ein numerischer Wert, der die Breite der Einfügemarke festlegt. Wenn <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> auf eine Zahl größer als 0 festgelegt wird, wird die Anzahl der Zeichen beginnend mit der aktuellen Einfügemarke ausgewählt.  
  
3. Optionale Greifen Sie über die-Eigenschaft auf den ausgewählten Text zu <xref:System.Windows.Forms.TextBoxBase.SelectedText%2A> .  
  
     Der folgende Code wählt den Inhalt eines Textfelds aus, wenn das-Ereignis des-Steuer Elements <xref:System.Windows.Forms.Control.Enter> auftritt. In diesem Beispiel wird überprüft, ob das Textfeld einen Wert für die- <xref:System.Windows.Forms.TextBox.Text%2A> Eigenschaft aufweist, die nicht `null` oder eine leere Zeichenfolge ist. Wenn das Textfeld den Fokus erhält, wird der aktuelle Text im Textfeld ausgewählt. Der `TextBox1_Enter` Ereignishandler muss an das-Steuerelement gebunden werden. Weitere Informationen finden Sie unter Gewusst [wie: Erstellen von Ereignis Handlern zur Laufzeit für Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
     Um dieses Beispiel zu testen, drücken Sie die Tab-Taste, bis das Textfeld den Fokus hat. Wenn Sie in das Textfeld klicken, wird der Text nicht ausgewählt.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.TextBox>
- [Übersicht über das TextBox-Steuerelement](textbox-control-overview-windows-forms.md)
- [Vorgehensweise: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Vorgehensweise: Erstellen eines Kennwort-Textfelds mit dem TextBox-Steuerelement in Windows Forms](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Vorgehensweise: Erstellen eines schreibgeschützten Textfelds](how-to-create-a-read-only-text-box-windows-forms.md)
- [Vorgehensweise: Setzen von Anführungszeichen in Zeichenfolgen](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Vorgehensweise: Anzeigen mehrerer Zeilen im TextBox-Steuerelement in Windows Forms](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [TextBox-Steuerelement](textbox-control-windows-forms.md)
