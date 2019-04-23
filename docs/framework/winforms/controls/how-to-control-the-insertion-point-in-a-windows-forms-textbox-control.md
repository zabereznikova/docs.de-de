---
title: 'Vorgehensweise: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms'
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
ms.openlocfilehash: 43fdb023f19aa988dfef3dcd68443d6f59808472
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59341321"
---
# <a name="how-to-control-the-insertion-point-in-a-windows-forms-textbox-control"></a>Vorgehensweise: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms
Wenn ein Windows Forms <xref:System.Windows.Forms.TextBox> Steuerelement zunächst den Fokus erhält, wird das standardmäßige einfügen in das Textfeld auf der linken Seite des vorhandenen Text. Der Benutzer kann die Einfügemarke die Tastatur oder Maus verschieben. Wenn das Textfeld eingeschränkt, und klicken Sie dann wieder den Fokus erhält, wird die Einfügemarke ablegen, wo der Benutzer zuletzt es platziert werden.  
  
 In einigen Fällen kann dieses Verhalten für den Benutzer verwirrend sein. In einem Textverarbeitungsprogramm, erwarten die Benutzer neue Zeichen nach der vorhandenen Text angezeigt werden. In eine Anwendung zur Dateneingabe erwarten die Benutzer neue Zeichen bestehende Einträge zu ersetzen. Die <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> und <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> Eigenschaften können Sie das Verhalten entsprechend Ihren Zweck zu ändern.  
  
### <a name="to-control-the-insertion-point-in-a-textbox-control"></a>Zum Steuern der Einfügemarke in einem TextBox-Steuerelement  
  
1. Legen Sie für die <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A>-Eigenschaft einen geeigneten Wert fest. 0 (null) platziert die Einfügemarke direkt auf der linken Seite des ersten Zeichens.  
  
2. (Optional) Legen Sie die <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> Eigenschaft, um die Länge des Texts, die Sie auswählen möchten.  
  
     Der folgende Code gibt die Einfügemarke immer 0 zurück. Die `TextBox1_Enter` Ereignishandler muss gebunden sein, auf das Steuerelement; Weitere Informationen, wie unter [Erstellen von Ereignishandlern in Windows Forms](../creating-event-handlers-in-windows-forms.md).  
  
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
  
## <a name="making-the-insertion-point-visible-by-default"></a>Sichtbarmachen wird standardmäßig der Einfügemarke ein.  
 Die <xref:System.Windows.Forms.TextBox> Einfügemarke ist standardmäßig sichtbar in einer neuen Form nur, wenn die <xref:System.Windows.Forms.TextBox> Steuerelement wird in der Reihenfolge an erster Stelle. Andernfalls die Einfügemarke angezeigt wird, nur, wenn Sie geben die <xref:System.Windows.Forms.TextBox> der Fokus mit der Tastatur oder Maus.  
  
#### <a name="to-make-the-text-box-insertion-point-visible-by-default-on-a-new-form"></a>Um den Text die Einfügemarke auf eine neue Form standardmäßig sichtbar zu machen  
  
-   Legen Sie die <xref:System.Windows.Forms.TextBox> des Steuerelements <xref:System.Windows.Forms.Control.TabIndex%2A> Eigenschaft `0`.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.TextBox>
- [Übersicht über das TextBox-Steuerelement](textbox-control-overview-windows-forms.md)
- [Vorgehensweise: Erstellen Sie ein Kennwort-Textfeld mit dem TextBox-Steuerelement in Windows Forms](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Vorgehensweise: Erstellen eines schreibgeschützten Textfelds](how-to-create-a-read-only-text-box-windows-forms.md)
- [Vorgehensweise: Setzen von Anführungszeichen in Zeichenfolgen](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Vorgehensweise: Wählen Sie Text im TextBox-Steuerelement von Windows Forms](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Vorgehensweise: Zeigen Sie mehrerer Zeilen in der TextBox-Steuerelement in Windows Forms an](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [TextBox-Steuerelement](textbox-control-windows-forms.md)
