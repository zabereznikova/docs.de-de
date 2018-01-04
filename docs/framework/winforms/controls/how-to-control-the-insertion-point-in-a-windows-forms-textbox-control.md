---
title: "Gewusst wie: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms"
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
- TextBox control [Windows Forms], insertion point
- insertion points [Windows Forms], TextBox controls
- text boxes [Windows Forms], controlling insertion point
ms.assetid: 5bee7d34-5121-429e-ab1f-d8ff67bc74c1
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c8de64ac28fe57e3c448c671859053fad4aae3b6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-control-the-insertion-point-in-a-windows-forms-textbox-control"></a>Gewusst wie: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms
Wenn ein Windows Forms <xref:System.Windows.Forms.TextBox> Steuerelement zunächst den Fokus erhält, ist das Standard-einfügen in das Textfeld auf der linken Seite des vorhandenen Text. Der Benutzer kann die Einfügemarke an der Stelle mit der Tastatur oder die Maus verschieben. Wenn das Textfeld verliert, und klicken Sie dann den Fokus erweitert, wird die Einfügemarke ablegen, wo der Benutzer zuletzt es platziert werden.  
  
 In einigen Fällen kann dieses Verhalten für den Benutzer irritierend sein. In einem Textverarbeitungsprogramm, erwarten die Benutzer neue Zeichen nach einem vorhandenen Text angezeigt werden. In einer Anwendung zur Dateneingabe erwarten die Benutzer neue Zeichen ersetzen alle vorhandenen Eintrag aus. Die <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> und <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> Eigenschaften ermöglichen es Ihnen, die das Verhalten entsprechend Ihren Zweck zu ändern.  
  
### <a name="to-control-the-insertion-point-in-a-textbox-control"></a>Steuern die Einfügemarke in einem Textfeldsteuerelement  
  
1.  Legen Sie für die <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A>-Eigenschaft einen geeigneten Wert fest. 0 (null) wird die Einfügemarke direkt auf der linken Seite des ersten Zeichens platziert.  
  
2.  (Optional) Legen Sie die <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> Eigenschaft, um die Länge des Texts, die Sie auswählen möchten.  
  
     Der folgende Code gibt die Einfügemarke immer auf 0 zurück. Die `TextBox1_Enter` Ereignishandler; Weitere Informationen an das Steuerelement gebunden werden muss, finden Sie unter [Erstellen von Ereignishandlern in Windows Forms](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md).  
  
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
  
## <a name="making-the-insertion-point-visible-by-default"></a>Sichtbarmachen der Einfügemarke an Standardeinstellung  
 Die <xref:System.Windows.Forms.TextBox> Einfügemarke befindet sich standardmäßig in ein neues Formular nur, wenn sichtbar der <xref:System.Windows.Forms.TextBox> Steuerelement steht an erster Stelle in der Aktivierreihenfolge. Andernfalls die Einfügemarke angezeigt wird, nur dann, wenn Sie geben die <xref:System.Windows.Forms.TextBox> den Fokus der Tastatur oder die Maus.  
  
#### <a name="to-make-the-text-box-insertion-point-visible-by-default-on-a-new-form"></a>Um den Text im Feld der Einfügemarke auf eine neue Form standardmäßig sichtbar zu machen  
  
-   Legen Sie die <xref:System.Windows.Forms.TextBox> des Steuerelements <xref:System.Windows.Forms.Control.TabIndex%2A> Eigenschaft `0`.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.TextBox>  
 [Übersicht über das TextBox-Steuerelement](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [Vorgehensweise: Erstellen eines Kennwort-Textfelds mit dem TextBox-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [Vorgehensweise: Erstellen eines schreibgeschützten Textfelds](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [Gewusst wie: Setzen von Anführungszeichen in Zeichenfolgen](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [Vorgehensweise: Programmgesteuertes Auswählen von Text im TextBox-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [Vorgehensweise: Anzeigen mehrerer Zeilen im TextBox-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [TextBox-Steuerelement](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
