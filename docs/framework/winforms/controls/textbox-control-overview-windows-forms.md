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
ms.openlocfilehash: b15de762b166fb66ff926706e93cbac6d0c6ba9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="textbox-control-overview-windows-forms"></a>Übersicht über das TextBox-Steuerelement (Windows Forms)
Windows Forms-Textfelder dienen, die vom Benutzer Eingabe abzurufen oder um Text anzuzeigen. Die <xref:System.Windows.Forms.TextBox> Steuerelement wird im Allgemeinen für bearbeitbares Textfeld verwendet, obwohl sie auch schreibgeschützt festgelegt werden kann. Textfelder können mehrere Zeilen angezeigt, Zeilenumbruch, um die Größe des Steuerelements und einfache Formatierung hinzufügen. Die <xref:System.Windows.Forms.TextBox> gesteuert Formatvorlage mit einem einzelnen Format für Text im Steuerelement angezeigt oder eingegeben. Um mehrere Arten von formatiertem Text anzuzeigen, verwenden die <xref:System.Windows.Forms.RichTextBox> Steuerelement. Weitere Informationen finden Sie unter [Übersicht über das RichTextBox-Steuerelement](../../../../docs/framework/winforms/controls/richtextbox-control-overview-windows-forms.md).  
  
## <a name="working-with-the-textbox-control"></a>Arbeiten mit dem TextBox-Steuerelement  
 Vom Steuerelement angezeigte Text ist Bestandteil der <xref:System.Windows.Forms.TextBox.Text%2A> Eigenschaft. Standardmäßig können Sie bis zu 2048 Zeichen in einem Textfeld eingeben. Wenn Sie festlegen, die <xref:System.Windows.Forms.TextBox.Multiline%2A> Eigenschaft `true`, Sie können bis zu 32 KB Text eingeben. Die <xref:System.Windows.Forms.TextBox.Text%2A> Eigenschaft kann zur Entwurfszeit im Fenster Eigenschaften zur Laufzeit im Code oder durch die Benutzereingabe zur Laufzeit festgelegt werden. Den aktuellen Inhalt eines Textfelds können zur Laufzeit abgerufen werden, durch Lesen der <xref:System.Windows.Forms.TextBox.Text%2A> Eigenschaft.  
  
 Das folgende Codebeispiel legt Text im Steuerelement zur Laufzeit fest. Die `InitializeMyControl` Prozedur wird nicht automatisch ausgeführt; es muss aufgerufen werden.  
  
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
 <xref:System.Windows.Forms.TextBox>  
 [Vorgehensweise: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [Vorgehensweise: Erstellen eines Kennwort-Textfelds mit dem TextBox-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [Vorgehensweise: Erstellen eines schreibgeschützten Textfelds](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [Gewusst wie: Setzen von Anführungszeichen in Zeichenfolgen](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [Vorgehensweise: Programmgesteuertes Auswählen von Text im TextBox-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [Vorgehensweise: Anzeigen mehrerer Zeilen im TextBox-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [TextBox-Steuerelement](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
