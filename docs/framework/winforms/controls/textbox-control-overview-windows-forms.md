---
title: "&#220;bersicht &#252;ber das TextBox-Steuerelement (Windows&#160;Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "TextBox"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Textfelder, Hinzufügen"
  - "TextBox-Steuerelement [Windows Forms], Informationen über TextBox-Steuerelemente"
ms.assetid: d1a9c7f5-fa53-480a-a75c-158f8649ea2f
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# &#220;bersicht &#252;ber das TextBox-Steuerelement (Windows&#160;Forms)
Textfelder in Windows Forms werden für Benutzereingaben oder zur Anzeige von Text verwendet.  <xref:System.Windows.Forms.TextBox>\-Steuerelemente werden in der Regel für bearbeitbaren Text verwendet, unterstützen jedoch auch schreibgeschützten Text.  In Textfeldern können mehrere Zeilen angezeigt, Text auf die Größe des Steuerelements umbrochen und grundlegende Formatierungen hinzugefügt werden.  Das <xref:System.Windows.Forms.TextBox>\-Steuerelement enthält eine Formatvorlage mit einem einzelnen Format für Text, der im Steuerelement angezeigt oder eingegeben wird.  Unterschiedlich formatierte Textarten werden mit dem <xref:System.Windows.Forms.RichTextBox>\-Steuerelement angezeigt.  Weitere Informationen finden Sie unter [Übersicht über das RichTextBox\-Steuerelement](../../../../docs/framework/winforms/controls/richtextbox-control-overview-windows-forms.md).  
  
## Arbeiten mit dem TextBox\-Steuerelement  
 Der vom Steuerelement angezeigte Text ist in der <xref:System.Windows.Forms.TextBox.Text%2A>\-Eigenschaft enthalten.  In ein Textfeld können standardmäßig bis zu 2048 Zeichen eingegeben werden.  Wird für die <xref:System.Windows.Forms.TextBox.Multiline%2A>\-Eigenschaft `true` festgelegt, kann das Textfeld bis zu 32 KB Text aufnehmen.  Die <xref:System.Windows.Forms.TextBox.Text%2A>\-Eigenschaft kann zur Entwurfszeit im Eigenschaftenfenster festgelegt oder zur Laufzeit im Code bzw. durch Benutzereingaben definiert werden.  Der aktuelle Inhalt eines Textfeldes kann zur Laufzeit durch Auslesen der <xref:System.Windows.Forms.TextBox.Text%2A>\-Eigenschaft abgerufen werden.  
  
 Im folgenden Codebeispiel wird Text zur Laufzeit im Steuerelement festgelegt.  Die`InitializeMyControl`Prozedur führt nicht automatisch aus. Sie muss aufgerufen werden.  
  
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
  
## Siehe auch  
 <xref:System.Windows.Forms.TextBox>   
 [Gewusst wie: Steuern der Einfügemarke in einem TextBox\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)   
 [Gewusst wie: Erstellen eines Kennwort\-Textfelds mit dem TextBox\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)   
 [Gewusst wie: Erstellen eines schreibgeschützten Textfelds](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)   
 [Gewusst wie: Setzen von Anführungszeichen in Zeichenfolgen](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)   
 [Gewusst wie: Programmgesteuertes Auswählen von Text im TextBox\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)   
 [Gewusst wie: Anzeigen mehrerer Zeilen im TextBox\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)   
 [TextBox\-Steuerelement](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)