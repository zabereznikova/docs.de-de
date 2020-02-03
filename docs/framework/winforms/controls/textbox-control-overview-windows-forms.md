---
title: Übersicht über das TextBox-Steuerelement
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
ms.openlocfilehash: 06ab460d720d17331881b5ba653263160eaf3cb3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742807"
---
# <a name="textbox-control-overview-windows-forms"></a>Übersicht über das TextBox-Steuerelement (Windows Forms)
Windows Forms Textfelder werden verwendet, um Eingaben vom Benutzer zu erhalten oder Text anzuzeigen. Das <xref:System.Windows.Forms.TextBox> Steuerelement wird im Allgemeinen für bearbeitbaren Text verwendet, obwohl es auch als schreibgeschützt festgelegt werden kann. Textfelder können mehrere Zeilen anzeigen, Text in die Größe des Steuer Elements umschließen und grundlegende Formatierung hinzufügen. Das <xref:System.Windows.Forms.TextBox>-Steuerelement stellt einen einzelnen Formatierungs Stil für Text bereit, der im Steuerelement angezeigt oder eingegeben wird. Verwenden Sie das <xref:System.Windows.Forms.RichTextBox>-Steuerelement, um mehrere formatierte Text Typen anzuzeigen. Weitere Informationen finden Sie unter [Übersicht über das RichTextBox-Steuer](richtextbox-control-overview-windows-forms.md)Element.  
  
## <a name="working-with-the-textbox-control"></a>Arbeiten mit dem TextBox-Steuerelement  
 Der vom Steuerelement angezeigte Text ist in der <xref:System.Windows.Forms.TextBox.Text%2A>-Eigenschaft enthalten. Standardmäßig können Sie bis zu 2048 Zeichen in einem Textfeld eingeben. Wenn Sie die <xref:System.Windows.Forms.TextBox.Multiline%2A>-Eigenschaft auf `true`festlegen, können Sie bis zu 32 KB Text eingeben. Die <xref:System.Windows.Forms.TextBox.Text%2A>-Eigenschaft kann zur Entwurfszeit mit dem Eigenschaften Fenster, zur Laufzeit im Code oder durch Benutzereingaben zur Laufzeit festgelegt werden. Der aktuelle Inhalt eines Textfelds kann zur Laufzeit abgerufen werden, indem die <xref:System.Windows.Forms.TextBox.Text%2A>-Eigenschaft gelesen wird.  
  
 Im folgenden Codebeispiel wird der Text im-Steuerelement zur Laufzeit festgelegt. Die `InitializeMyControl` Prozedur wird nicht automatisch ausgeführt. Es muss aufgerufen werden.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.TextBox>
- [Vorgehensweise: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Vorgehensweise: Erstellen eines Kennwort-Textfelds mit dem TextBox-Steuerelement in Windows Forms](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Vorgehensweise: Erstellen eines schreibgeschützten Textfelds](how-to-create-a-read-only-text-box-windows-forms.md)
- [Gewusst wie: Setzen von Anführungszeichen in Zeichenfolgen](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Vorgehensweise: Programmgesteuertes Auswählen von Text im TextBox-Steuerelement in Windows Forms](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Vorgehensweise: Anzeigen mehrerer Zeilen im TextBox-Steuerelement in Windows Forms](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [TextBox-Steuerelement](textbox-control-windows-forms.md)
