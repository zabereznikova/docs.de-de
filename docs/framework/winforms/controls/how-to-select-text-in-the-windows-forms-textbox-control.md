---
title: "Gewusst wie: Programmgesteuertes Ausw&#228;hlen von Text im TextBox-Steuerelement in Windows&#160;Forms | Microsoft Docs"
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
  - "Textfelder, Markieren von Text (programmgesteuert)"
  - "Text, Programmgesteuerte Auswahl in Textfeldern"
  - "TextBox-Steuerelement [Windows Forms], Markieren von Text (programmgesteuert)"
ms.assetid: 8c591546-6a01-45c7-8e03-f78431f903b1
caps.latest.revision: 24
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# Gewusst wie: Programmgesteuertes Ausw&#228;hlen von Text im TextBox-Steuerelement in Windows&#160;Forms
Sie können Text im <xref:System.Windows.Forms.TextBox>\-Steuerelement in Windows Forms programmgesteuert markieren.  Angenommen, Sie erstellen eine Funktion, mit der Text nach einer bestimmten Zeichenfolge durchsucht wird. In diesem Fall kann der Text markiert werden, um dem Leser einen visuellen Hinweis auf die Textposition der gefundenen Zeichenfolge zu geben.  
  
### So markieren Sie Text programmgesteuert  
  
1.  Legen Sie die <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A>\-Eigenschaft auf den Anfang des zu markierenden Textes fest.  
  
     Die <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A>\-Eigenschaft entspricht einer Zahl, die die Position der Einfügemarke innerhalb der Textzeichenfolge angibt, wobei 0 die Position ganz links bezeichnet.  Wenn die <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A>\-Eigenschaft auf einen Wert festgelegt wird, der größer oder gleich der Anzahl der im Textfeld enthaltenen Zeichen ist, wird die Einfügemarke hinter dem letzten Zeichen platziert.  
  
2.  Legen Sie die <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A>\-Eigenschaft auf die Länge des zu markierenden Textes fest.  
  
     Die <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A>\-Eigenschaft ist ein numerischer Wert, der die Breite der Einfügemarke festlegt.  Wird <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> auf einen Wert größer 0 festgelegt, wird die entsprechende Anzahl von Zeichen, beginnend mit der aktuellen Position der Einfügemarke, markiert.  
  
3.  \(Optional\) Greifen Sie mithilfe der <xref:System.Windows.Forms.TextBoxBase.SelectedText%2A>\-Eigenschaft auf den markierten Text zu.  
  
     Der folgende Code markiert den Inhalt eines Textfelds, sobald das <xref:System.Windows.Forms.Control.Enter>\-Ereignis für das Steuerelement ausgelöst wird.  In diesem Beispiel wird überprüft, ob im Textfeld ein Wert für die <xref:System.Windows.Forms.TextBox.Text%2A>\-Eigenschaft angegeben ist, der nicht `null` oder eine leere Zeichenfolge ist.  Wenn das Textfeld den Fokus erhält, wird der vorhandene Text im Textfeld ausgewählt.  Der `TextBox1_Enter`\-Ereignishandler muss an das Steuerelement gebunden werden. Weitere Informationen finden Sie unter [Gewusst wie: Erstellen von Ereignishandlern für Windows Forms zur Laufzeit](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
     Um dieses Beispiel zu testen, drücken Sie die TAB\-TASTE, bis das Textfeld den Fokus erhält.  Sobald Sie in das Textfeld klicken, wird die Textauswahl aufgehoben.  
  
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
  
## Siehe auch  
 <xref:System.Windows.Forms.TextBox>   
 [Übersicht über das TextBox\-Steuerelement](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)   
 [Gewusst wie: Steuern der Einfügemarke in einem TextBox\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)   
 [Gewusst wie: Erstellen eines Kennwort\-Textfelds mit dem TextBox\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)   
 [Gewusst wie: Erstellen eines schreibgeschützten Textfelds](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)   
 [Gewusst wie: Setzen von Anführungszeichen in Zeichenfolgen](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)   
 [Gewusst wie: Anzeigen mehrerer Zeilen im TextBox\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)   
 [TextBox\-Steuerelement](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)