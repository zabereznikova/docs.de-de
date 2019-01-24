---
title: Übersicht über das TextBox-Steuerelement (Windows Forms)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- TextBox
helpviewer_keywords:
- TextBox control [Windows Forms], about TextBox controls
- text boxes [Windows Forms], adding
ms.assetid: d1a9c7f5-fa53-480a-a75c-158f8649ea2f
ms.openlocfilehash: ed4a40c172e527c6210bc31ab2575ebc08ead1bd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54671238"
---
# <a name="textbox-control-overview-windows-forms"></a>Übersicht über das TextBox-Steuerelement (Windows Forms)
Windows Forms-Textfelder werden Eingaben von den Benutzer erhalten oder zum Anzeigen von Text verwendet. Die <xref:System.Windows.Forms.TextBox> Steuerelement wird im Allgemeinen für bearbeitbaren Text verwendet, obwohl sie auch schreibgeschützt festgelegt werden kann. Textfelder können mehrere Zeilen angezeigt, Umbrechen von Text auf die Größe des Steuerelements und fügen die einfache Formatierung. Die <xref:System.Windows.Forms.TextBox> -Steuerelement stellt einen einzelnen Formatstil für Text angezeigt oder in das Steuerelement eingegeben. Um mehrere Arten von formatiertem Text anzuzeigen, verwenden die <xref:System.Windows.Forms.RichTextBox> Steuerelement. Weitere Informationen finden Sie unter [Übersicht über das RichTextBox-Steuerelement](../../../../docs/framework/winforms/controls/richtextbox-control-overview-windows-forms.md).  
  
## <a name="working-with-the-textbox-control"></a>Arbeiten mit dem TextBox-Steuerelement  
 Vom Steuerelement angezeigte Text ist Bestandteil der <xref:System.Windows.Forms.TextBox.Text%2A> Eigenschaft. Standardmäßig können Sie bis zu 2048 Zeichen in einem Textfeld eingeben. Setzen Sie die <xref:System.Windows.Forms.TextBox.Multiline%2A> Eigenschaft `true`, können Sie bis zu 32 KB Text eingeben. Die <xref:System.Windows.Forms.TextBox.Text%2A> Eigenschaft kann zur Entwurfszeit im Fenster Eigenschaften zur Laufzeit im Code oder durch die Benutzereingabe zur Laufzeit festgelegt werden. Den aktuellen Inhalt eines Textfelds können zur Laufzeit abgerufen werden, durch Lesen der <xref:System.Windows.Forms.TextBox.Text%2A> Eigenschaft.  
  
 Das folgende Codebeispiel legt Text im Steuerelement zur Laufzeit fest. Die `InitializeMyControl` -Prozedur wird nicht automatisch ausgeführt; muss aufgerufen werden.  
  
```vb  
Private Sub InitializeMyControl()  
   ' Put some text into the control first.  
   TextBox1.Text = "This is a TextBox control."  
End Sub  
```  
  
```csharp  
private void InitializeMyControl() {  
   // Put some text into the control first.  
   textBox1.Text = "This is a TextBox control.";  
}  
```  
  
```cpp  
private:  
   void InitializeMyControl()  
   {  
      // Put some text into the control first.  
      textBox1->Text = "This is a TextBox control.";  
   }  
```  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.TextBox>
- [Vorgehensweise: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Vorgehensweise: Erstellen Sie ein Kennwort-Textfeld mit dem TextBox-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Vorgehensweise: Erstellen eines schreibgeschützten Textfelds](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)
- [Vorgehensweise: Setzen von Anführungszeichen in Zeichenfolgen](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Vorgehensweise: Wählen Sie Text im TextBox-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Vorgehensweise: Zeigen Sie mehrerer Zeilen in der TextBox-Steuerelement in Windows Forms an](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [TextBox-Steuerelement](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
