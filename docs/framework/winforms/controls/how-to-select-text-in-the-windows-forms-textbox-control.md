---
title: "Gewusst wie: Programmgesteuertes Auswählen von Text im TextBox-Steuerelement in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], selecting text programmatically
- text boxes [Windows Forms], selecting text programmatically
- text [Windows Forms], selecting in text boxes programmatically
ms.assetid: 8c591546-6a01-45c7-8e03-f78431f903b1
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 08ad19f3daca43fb33e845b632ac7d92b00f544c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-select-text-in-the-windows-forms-textbox-control"></a>Gewusst wie: Programmgesteuertes Auswählen von Text im TextBox-Steuerelement in Windows Forms
Sie können Text in Windows Forms programmgesteuert auswählen <xref:System.Windows.Forms.TextBox> Steuerelement. Wenn Sie eine Funktion, mit dem Text für eine bestimmte Zeichenfolge gesucht erstellen, können Sie z. B. den Text den Reader die gefundene Zeichenfolge Position visuell Warnungen auswählen.  
  
### <a name="to-select-text-programmatically"></a>Text programmgesteuert aus  
  
1.  Legen Sie die <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> Eigenschaft auf den Anfang des Texts, die Sie auswählen möchten.  
  
     Die <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> Eigenschaft ist eine Zahl, die Einfügemarke innerhalb der Textzeichenfolge angibt, wobei 0 die linke Position. Wenn die <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> Eigenschaft ist festgelegt auf einen Wert gleich oder größer als die Anzahl der Zeichen in das Textfeld, das die Einfügemarke befindet sich nach dem letzten Zeichen.  
  
2.  Legen Sie die <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> Eigenschaft, um die Länge des Texts, die Sie auswählen möchten.  
  
     Die <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> Eigenschaft ist ein numerischer Wert, der die Breite der Einfügemarke festlegt. Festlegen der <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> auf eine Zahl größer als 0 bewirkt, diese Anzahl von Zeichen dass, die ausgewählt werden, beginnend mit der Einfügemarke.  
  
3.  (Optional) Zugriff auf den markierten Text über den <xref:System.Windows.Forms.TextBoxBase.SelectedText%2A> Eigenschaft.  
  
     Der Code unten wählt den Inhalt von Text Feld, wenn des Steuerelements <xref:System.Windows.Forms.Control.Enter> Ereignis auftritt. In diesem Beispiel wird überprüft, ob es sich bei dem Textfeld einen Wert für ist das <xref:System.Windows.Forms.TextBox.Text%2A> -Eigenschaft, die nicht `null` oder eine leere Zeichenfolge. Wenn das Textfeld den Fokus erhält, wird der aktuelle Text im Textfeld ausgewählt. Die `TextBox1_Enter` Ereignishandler; Weitere Informationen an das Steuerelement gebunden werden muss, finden Sie unter [Vorgehensweise: Erstellen von Ereignishandlern an Zeit für Windows Forms führen](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
     Drücken Sie zum Testen dieses Beispiels die Tab-Taste, bis das Textfeld den Fokus besitzt. Wenn Sie in das Textfeld klicken, wird der Text nicht ausgewählt.  
  
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
 <xref:System.Windows.Forms.TextBox>  
 [Übersicht über das TextBox-Steuerelement](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [Vorgehensweise: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [Vorgehensweise: Erstellen eines Kennwort-Textfelds mit dem TextBox-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [Vorgehensweise: Erstellen eines schreibgeschützten Textfelds](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [Gewusst wie: Setzen von Anführungszeichen in Zeichenfolgen](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [Vorgehensweise: Anzeigen mehrerer Zeilen im TextBox-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [TextBox-Steuerelement](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
