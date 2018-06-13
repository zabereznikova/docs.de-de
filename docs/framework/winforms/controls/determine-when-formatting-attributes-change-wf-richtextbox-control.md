---
title: 'Gewusst wie: Erkennen der Änderung von Formatierungsattributen im RichTextBox-Steuerelement von Windows Forms'
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
ms.openlocfilehash: 789a0a25c65185b101ef427ff62871fa490c7f1d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525213"
---
# <a name="how-to-determine-when-formatting-attributes-change-in-the-windows-forms-richtextbox-control"></a>Gewusst wie: Erkennen der Änderung von Formatierungsattributen im RichTextBox-Steuerelement von Windows Forms
Eine häufige Verwendung von Windows Forms <xref:System.Windows.Forms.RichTextBox> Steuerelement formatieren von Text mit Attributen wie Schriftartoptionen oder Absatzformatvorlagen. Ihre Anwendung möglicherweise Änderungen an textformatierung für die Anzeige von eine Symbolleiste, wie viele Textverarbeitungsprogrammen des.  
  
### <a name="to-respond-to-changes-in-formatting-attributes"></a>So reagieren Sie auf Änderungen bei der Formatierung von Attributen  
  
1.  Schreiben von Code in der <xref:System.Windows.Forms.RichTextBox.SelectionChanged> -Ereignishandler hinzu, führen Sie eine geeignete Maßnahme, abhängig vom Wert des Attributs. Im folgende Beispiel ändert die Darstellung von einer Symbolleisten-Schaltfläche, abhängig vom Wert der <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> Eigenschaft. Der Symbolleisten-Schaltfläche wird nur aktualisiert werden, wenn die Einfügemarke im Steuerelement bewegt wird.  
  
     Im folgenden Beispiel wird ein Formular mit einem <xref:System.Windows.Forms.RichTextBox> Steuerelement und ein <xref:System.Windows.Forms.ToolBar> Steuerelement, das eine Symbolleisten-Schaltfläche enthält. Weitere Informationen über Symbolleisten und Schaltflächen der Symbolleiste finden Sie unter [wie: Hinzufügen von Schaltflächen zu einem ToolBar-Steuerelement](../../../../docs/framework/winforms/controls/how-to-add-buttons-to-a-toolbar-control.md).  
  
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
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.RichTextBox.SelectionChanged>  
 <xref:System.Windows.Forms.RichTextBox>  
 [RichTextBox-Steuerelement](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
