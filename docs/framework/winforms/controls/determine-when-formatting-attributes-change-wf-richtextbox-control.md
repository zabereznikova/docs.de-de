---
title: 'Vorgehensweise: Erkennen der Änderung von Formatierungsattributen im RichTextBox-Steuerelement von Windows Forms'
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
ms.openlocfilehash: a90affde9de36f1c83d5b7c21b40580cdf53402e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61972288"
---
# <a name="how-to-determine-when-formatting-attributes-change-in-the-windows-forms-richtextbox-control"></a><span data-ttu-id="c1430-102">Vorgehensweise: Erkennen der Änderung von Formatierungsattributen im RichTextBox-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c1430-102">How to: Determine When Formatting Attributes Change in the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="c1430-103">Eine häufige Verwendung des Windows Forms <xref:System.Windows.Forms.RichTextBox> Steuerelement formatieren von Text mit Attributen wie z. B. Schriftartoptionen oder Absätze.</span><span class="sxs-lookup"><span data-stu-id="c1430-103">A common use of the Windows Forms <xref:System.Windows.Forms.RichTextBox> control is formatting text with attributes such as font options or paragraph styles.</span></span> <span data-ttu-id="c1430-104">Ihre Anwendung möglicherweise Änderungen an Text für die Anzeige von eine Symbolleiste, wie viele Textverarbeitungsprogrammen Formatierung von.</span><span class="sxs-lookup"><span data-stu-id="c1430-104">Your application may need to keep track of any changes in text formatting for the purpose of displaying a toolbar, as in many word-processing applications.</span></span>  
  
### <a name="to-respond-to-changes-in-formatting-attributes"></a><span data-ttu-id="c1430-105">Reaktion auf Änderungen bei der Formatierung von Attributen</span><span class="sxs-lookup"><span data-stu-id="c1430-105">To respond to changes in formatting attributes</span></span>  
  
1. <span data-ttu-id="c1430-106">Schreiben Sie Code in die <xref:System.Windows.Forms.RichTextBox.SelectionChanged> Ereignishandler führen Sie eine geeignete Maßnahme, abhängig vom Wert des Attributs.</span><span class="sxs-lookup"><span data-stu-id="c1430-106">Write code in the <xref:System.Windows.Forms.RichTextBox.SelectionChanged> event handler to perform an appropriate action depending on the value of the attribute.</span></span> <span data-ttu-id="c1430-107">Im folgende Beispiel ändert die Darstellung einer Symbolleisten-Schaltfläche, abhängig vom Wert der <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="c1430-107">The following example changes the appearance of a toolbar button depending on the value of the <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> property.</span></span> <span data-ttu-id="c1430-108">Die Symbolleisten-Schaltfläche wird nur aktualisiert werden, wenn die Einfügemarke im Steuerelement bewegt wird.</span><span class="sxs-lookup"><span data-stu-id="c1430-108">The toolbar button will only be updated when the insertion point is moved in the control.</span></span>  
  
     <span data-ttu-id="c1430-109">Im folgenden Beispiel wird ein Formular mit einem <xref:System.Windows.Forms.RichTextBox> Steuerelement und ein <xref:System.Windows.Forms.ToolBar> Steuerelement, das eine Symbolleisten-Schaltfläche enthält.</span><span class="sxs-lookup"><span data-stu-id="c1430-109">The example below assumes a form with a <xref:System.Windows.Forms.RichTextBox> control and a <xref:System.Windows.Forms.ToolBar> control that contains a toolbar button.</span></span> <span data-ttu-id="c1430-110">Weitere Informationen über Symbolleisten und Schaltflächen der Symbolleiste finden Sie unter [Vorgehensweise: Hinzufügen von Schaltflächen zu einem ToolBar-Steuerelement](how-to-add-buttons-to-a-toolbar-control.md).</span><span class="sxs-lookup"><span data-stu-id="c1430-110">For more information about toolbars and toolbar buttons, see [How to: Add Buttons to a ToolBar Control](how-to-add-buttons-to-a-toolbar-control.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c1430-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1430-111">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox.SelectionChanged>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="c1430-112">RichTextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="c1430-112">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="c1430-113">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="c1430-113">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
