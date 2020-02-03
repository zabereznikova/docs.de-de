---
title: Bestimmen, wann Formatierungs Attribute im RichTextBox-Steuerelement geändert werden
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], text boxes
- RichTextBox control [Windows Forms], determining font changes
- text boxes [Windows Forms], determining font changes
- SelChange event
ms.assetid: bdfed015-f77a-41e5-b38f-f8629b2fa166
ms.openlocfilehash: f9b2a1028f79059ec7d4d6bf3683100455bb5dea
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746036"
---
# <a name="how-to-determine-when-formatting-attributes-change-in-the-windows-forms-richtextbox-control"></a>Gewusst wie: Erkennen der Änderung von Formatierungsattributen im RichTextBox-Steuerelement von Windows Forms
Die Windows Forms <xref:System.Windows.Forms.RichTextBox>-Steuerelement wird häufig verwendet, um Text mit Attributen wie z. b. Schriftart Optionen oder Absatzformaten zu formatieren. Die Anwendung muss möglicherweise Änderungen an der Textformatierung für den Zweck der Anzeige einer Symbolleiste nachverfolgen, wie in vielen Textverarbeitungsanwendungen.  
  
### <a name="to-respond-to-changes-in-formatting-attributes"></a>So reagieren Sie auf Änderungen in Formatierungs Attributen  
  
1. Schreiben Sie Code in den <xref:System.Windows.Forms.RichTextBox.SelectionChanged>-Ereignishandler, um abhängig vom Wert des Attributs eine geeignete Aktion auszuführen. Im folgenden Beispiel wird die Darstellung einer Symbolleisten Schaltfläche abhängig vom Wert der <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A>-Eigenschaft geändert. Die Symbolleisten-Schaltfläche wird nur aktualisiert, wenn die Einfügemarke im Steuerelement verschoben wird.  
  
     Im folgenden Beispiel wird ein Formular mit einem <xref:System.Windows.Forms.RichTextBox>-Steuerelement und ein <xref:System.Windows.Forms.ToolBar>-Steuerelement angenommen, das eine Symbolleisten-Schaltfläche enthält Weitere Informationen zu Symbolleisten und Symbolleisten-Schaltflächen finden Sie unter Gewusst [wie: Hinzufügen von Schaltflächen zu einem Toolbar-Steuer](how-to-add-buttons-to-a-toolbar-control.md)Element.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.RichTextBox.SelectionChanged>
- <xref:System.Windows.Forms.RichTextBox>
- [RichTextBox-Steuerelement](richtextbox-control-windows-forms.md)
- [Steuerelemente für Windows Forms](controls-to-use-on-windows-forms.md)
