---
title: "Gewusst wie: Steuern der Einf&#252;gemarke in einem TextBox-Steuerelement in Windows&#160;Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Einfügepunkte, TextBox-Steuerelemente"
  - "Textfelder, Steuern des Einfügepunkts"
  - "TextBox-Steuerelement [Windows Forms], Einfügepunkt"
ms.assetid: 5bee7d34-5121-429e-ab1f-d8ff67bc74c1
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Gewusst wie: Steuern der Einf&#252;gemarke in einem TextBox-Steuerelement in Windows&#160;Forms
Wenn ein <xref:System.Windows.Forms.TextBox>\-Steuerelement in Windows Forms den Fokus zuerst erhält, werden Einfügungen im Textfeld standardmäßig links neben bereits vorhandenem Text vorgenommen.  Die Einfügemarke kann vom Benutzer mithilfe der Tastatur oder der Maus verschoben werden.  Wenn das Textfeld den Fokus verliert und anschließend wieder erhält, befindet sich die Einfügemarke an der Stelle, an der sie zuletzt vom Benutzer positioniert wurde.  
  
 Gelegentlich wirkt dieses Verhalten irritierend auf Benutzer.  In einem Textverarbeitungsprogramm würde der Benutzer z. B. erwarten, dass neue Zeichen hinter bereits vorhandenem Text eingefügt werden.  In einem Datenerfassungsprogramm könnte der Benutzer wiederum davon ausgehen, dass bestehende Einträge durch neue Zeichen ersetzt werden.  Mithilfe der <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A>\-Eigenschaft und der <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A>\-Eigenschaft können Sie das Verhalten Ihren Anforderungen entsprechend anpassen.  
  
### So steuern Sie die Einfügemarke in einem TextBox\-Steuerelement  
  
1.  Legen Sie für die <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A>\-Eigenschaft einen geeigneten Wert fest.  Durch den Wert 0 wird die Einfügemarke links vom ersten Zeichen positioniert.  
  
2.  \(Optional\) Legen Sie die <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A>\-Eigenschaft auf die Länge des zu markierenden Textes fest.  
  
     Durch den folgenden Code wird die Einfügemarke stets auf 0 \(null\) zurückgesetzt.  Der `TextBox1_Enter`\-Ereignishandler muss an das Steuerelement gebunden werden. Weitere Informationen finden Sie unter [Erstellen von Ereignishandlern in Windows Forms](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md).  
  
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
  
## Standardmäßiges Anzeigen der Einfügemarke  
 Die <xref:System.Windows.Forms.TextBox>\-Einfügemarke ist in einem neuen Formular standardmäßig nur dann sichtbar, wenn sich das <xref:System.Windows.Forms.TextBox>\-Steuerelement in der Aktivierreihenfolge an erster Stelle befindet.  Andernfalls wird die Einfügemarke nur angezeigt, wenn <xref:System.Windows.Forms.TextBox> entweder über die Tastatur oder die Maus den Fokus erhält.  
  
#### So wird die Einfügemarke des Textfelds standardmäßig in einem neuen Formular angezeigt  
  
-   Legen Sie die <xref:System.Windows.Forms.Control.TabIndex%2A>\-Eigenschaft des <xref:System.Windows.Forms.TextBox>\-Steuerelements auf `0` fest.  
  
## Siehe auch  
 <xref:System.Windows.Forms.TextBox>   
 [Übersicht über das TextBox\-Steuerelement](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)   
 [Gewusst wie: Erstellen eines Kennwort\-Textfelds mit dem TextBox\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)   
 [Gewusst wie: Erstellen eines schreibgeschützten Textfelds](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)   
 [Gewusst wie: Setzen von Anführungszeichen in Zeichenfolgen](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)   
 [Gewusst wie: Programmgesteuertes Auswählen von Text im TextBox\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)   
 [Gewusst wie: Anzeigen mehrerer Zeilen im TextBox\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)   
 [TextBox\-Steuerelement](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)