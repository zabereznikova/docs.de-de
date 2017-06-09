---
title: "Gewusst wie: Erkennen der &#196;nderung von Formatierungsattributen im RichTextBox-Steuerelement von Windows&#160;Forms | Microsoft Docs"
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
  - "Beispiele [Windows Forms], Textfelder"
  - "RichTextBox-Steuerelement [Windows Forms], Feststellen von Schriftartänderungen"
  - "SelBold-Eigenschaft"
  - "SelChange-Ereignis"
  - "Textfelder, Feststellen von Schriftartänderungen"
ms.assetid: bdfed015-f77a-41e5-b38f-f8629b2fa166
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Erkennen der &#196;nderung von Formatierungsattributen im RichTextBox-Steuerelement von Windows&#160;Forms
Häufig wird das <xref:System.Windows.Forms.RichTextBox>\-Steuerelement von Windows Forms zum Formatieren von Text mit Attributen wie Schriftartoptionen oder Absatzformatvorlagen verwendet.  Die Anwendung muss möglicherweise alle Änderungen an der Textformatierung verfolgen, um eine Symbolleiste anzeigen zu können. Dies gilt z. B. für viele Textverarbeitungsanwendungen.  
  
### So bestimmen Sie die Reaktionen auf Änderungen an den Formatierungsattributen  
  
1.  Schreiben Sie Code im <xref:System.Windows.Forms.RichTextBox.SelectionChanged>\-Ereignishandler, um je nach Wert des Attributs einen entsprechenden Vorgang auszuführen.  Im folgenden Beispiel wird die Darstellung einer Symbolleisten\-Schaltfläche entsprechend dem Wert der <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A>\-Eigenschaft geändert.  Die Symbolleisten\-Schaltfläche wird erst aktualisiert, wenn die Einfügemarke im Steuerelement verschoben wird.  
  
     Im folgenden Beispiel wird von einem Formular ausgegangen, das ein <xref:System.Windows.Forms.RichTextBox>\-Steuerelement und ein <xref:System.Windows.Forms.ToolBar>\-Steuerelement mit einer Symbolleisten\-Schaltfläche enthält.  Weitere Informationen über Symbolleisten und Symbolleisten\-Schaltflächen finden Sie unter [Gewusst wie: Hinzufügen von Schaltflächen zu einem ToolBar\-Steuerelement](../../../../docs/framework/winforms/controls/how-to-add-buttons-to-a-toolbar-control.md).  
  
    ```vb  
    ' The following code assumes the existence of a toolbar control  
    ' with at least one toolbar button.  
    Private Sub RichTextBox1_SelectionChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles RichTextBox1.SelectionChanged  
       If RichTextBox1.SelectionBullet = True Then  
          ' Bullet button on toolbar should appear pressed  
          ToolBarButton1.Pushed = True  
       Else  
           ' Bullet button on toolbar should appear unpressed  
           ToolBarButton1.Pushed = False  
       End If  
    End Sub  
  
    ```  
  
    ```csharp  
    // The following code assumes the existence of a toolbar control  
    // with at least one toolbar button.  
    private void richTextBox1_SelectionChanged(object sender,  
    System.EventArgs e)  
    {  
       if (richTextBox1.SelectionBullet == true)   
       {  
          // Bullet button on toolbar should appear pressed  
          toolBarButton1.Pushed = true;  
       }  
       else   
       {  
          // Bullet button on toolbar should appear unpressed  
          toolBarButton1.Pushed = false;  
       }  
    }  
  
    ```  
  
    ```cpp  
    // The following code assumes the existence of a toolbar control  
    // with at least one toolbar button.  
    private:  
       System::Void richTextBox1_SelectionChanged(  
          System::Object ^  sender, System::EventArgs ^  e)  
       {  
          if (richTextBox1->SelectionBullet == true)  
          {  
             // Bullet button on toolbar should appear pressed  
             toolBarButton1->Pushed = true;  
          }  
          else  
          {  
             // Bullet button on toolbar should appear unpressed  
             toolBarButton1->Pushed = false;  
          }  
       }  
    ```  
  
## Siehe auch  
 <xref:System.Windows.Forms.RichTextBox.SelectionChanged>   
 <xref:System.Windows.Forms.RichTextBox>   
 [RichTextBox\-Steuerelement](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)   
 [Steuerelemente für Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)