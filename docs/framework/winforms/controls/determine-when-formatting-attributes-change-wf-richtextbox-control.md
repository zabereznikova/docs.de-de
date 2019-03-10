---
title: 'Vorgehensweise: Bestimmen Sie, wann die Formatierung der Änderung von Formatierungsattributen im RichTextBox-Steuerelement von Windows Forms'
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
ms.openlocfilehash: e463ac0fd77a31e4e11cb440f64ec0d4694af61f
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57722021"
---
# <a name="how-to-determine-when-formatting-attributes-change-in-the-windows-forms-richtextbox-control"></a>Vorgehensweise: Bestimmen Sie, wann die Formatierung der Änderung von Formatierungsattributen im RichTextBox-Steuerelement von Windows Forms
Eine häufige Verwendung des Windows Forms <xref:System.Windows.Forms.RichTextBox> Steuerelement formatieren von Text mit Attributen wie z. B. Schriftartoptionen oder Absätze. Ihre Anwendung möglicherweise Änderungen an Text für die Anzeige von eine Symbolleiste, wie viele Textverarbeitungsprogrammen Formatierung von.  
  
### <a name="to-respond-to-changes-in-formatting-attributes"></a>Reaktion auf Änderungen bei der Formatierung von Attributen  
  
1.  Schreiben Sie Code in die <xref:System.Windows.Forms.RichTextBox.SelectionChanged> Ereignishandler führen Sie eine geeignete Maßnahme, abhängig vom Wert des Attributs. Im folgende Beispiel ändert die Darstellung einer Symbolleisten-Schaltfläche, abhängig vom Wert der <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> Eigenschaft. Die Symbolleisten-Schaltfläche wird nur aktualisiert werden, wenn die Einfügemarke im Steuerelement bewegt wird.  
  
     Im folgenden Beispiel wird ein Formular mit einem <xref:System.Windows.Forms.RichTextBox> Steuerelement und ein <xref:System.Windows.Forms.ToolBar> Steuerelement, das eine Symbolleisten-Schaltfläche enthält. Weitere Informationen über Symbolleisten und Schaltflächen der Symbolleiste finden Sie unter [Vorgehensweise: Hinzufügen von Schaltflächen zu einem ToolBar-Steuerelement](how-to-add-buttons-to-a-toolbar-control.md).  
  
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
- <xref:System.Windows.Forms.RichTextBox.SelectionChanged>
- <xref:System.Windows.Forms.RichTextBox>
- [RichTextBox-Steuerelement](richtextbox-control-windows-forms.md)
- [Windows Forms-Steuerelemente](controls-to-use-on-windows-forms.md)
