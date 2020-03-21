---
title: Bestimmen, wann sich Formatierungsattribute in RichTextBox Control ändern
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
ms.openlocfilehash: a190c3479b58464763e0eefdd32d14e88a1f05e1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142263"
---
# <a name="how-to-determine-when-formatting-attributes-change-in-the-windows-forms-richtextbox-control"></a>Gewusst wie: Erkennen der Änderung von Formatierungsattributen im RichTextBox-Steuerelement von Windows Forms
Eine häufige Verwendung des <xref:System.Windows.Forms.RichTextBox> Windows Forms-Steuerelements ist das Formatieren von Text mit Attributen wie Schriftartoptionen oder Absatzformatvorlagen. Ihre Anwendung muss möglicherweise alle Änderungen in der Textformatierung nachverfolgen, um eine Symbolleiste anzuzeigen, wie in vielen Textverarbeitungsanwendungen.  
  
### <a name="to-respond-to-changes-in-formatting-attributes"></a>So reagieren Sie auf Änderungen an Formatierungsattributen  
  
1. Schreiben Sie <xref:System.Windows.Forms.RichTextBox.SelectionChanged> Code in den Ereignishandler, um je nach Wert des Attributs eine entsprechende Aktion auszuführen. Im folgenden Beispiel wird die Darstellung einer Symbolleistenschaltfläche <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> abhängig vom Wert der Eigenschaft geändert. Die Symbolleistenschaltfläche wird nur aktualisiert, wenn die Einfügemarke im Steuerelement verschoben wird.  
  
     Im folgenden Beispiel wird <xref:System.Windows.Forms.RichTextBox> ein Formular <xref:System.Windows.Forms.ToolBar> mit einem Steuerelement und einem Steuerelement mit einer Symbolleistenschaltfläche angenommen. Weitere Informationen zu Symbolleisten und Symbolleistenschaltflächen finden Sie unter [Gewusst wie: Hinzufügen von Schaltflächen zu einem ToolBar-Steuerelement](how-to-add-buttons-to-a-toolbar-control.md).  
  
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
- [Windows Forms-Steuerelemente](controls-to-use-on-windows-forms.md)
