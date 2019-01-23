---
title: 'Vorgehensweise: Bestimmen des aktiven untergeordneten MDI-Elements'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Clipboard [Windows Forms], copying data to
- MDI [Windows Forms], child windows
- child forms
- MDI [Windows Forms], activating forms
- MDI [Windows Forms], locating focus
ms.assetid: 33880ec3-0207-4c2b-a616-ff140443cc0f
ms.openlocfilehash: 581fbb839d06aebc6487bb7b4933f0c1e39af3e4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54512553"
---
# <a name="how-to-determine-the-active-mdi-child"></a><span data-ttu-id="1b998-102">Vorgehensweise: Bestimmen des aktiven untergeordneten MDI-Elements</span><span class="sxs-lookup"><span data-stu-id="1b998-102">How to: Determine the Active MDI Child</span></span>
<span data-ttu-id="1b998-103">Gelegentlich möchten Sie einen Befehl, der ausgeführt wird auf dem Steuerelement bereitstellen, auf dem derzeit aktiven untergeordneten Formular den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="1b998-103">On occasion, you will want to provide a command that operates on the control that has focus on the currently active child form.</span></span> <span data-ttu-id="1b998-104">Nehmen wir beispielsweise an, dass Sie den markierten Text aus des untergeordneten Formulars-Textfeld in die Zwischenablage kopieren möchten.</span><span class="sxs-lookup"><span data-stu-id="1b998-104">For example, suppose you want to copy selected text from the child form's text box to the Clipboard.</span></span> <span data-ttu-id="1b998-105">Erstellen Sie eine Prozedur, die ausgewählten Text in die Zwischenablage mithilfe kopiert die <xref:System.Windows.Forms.Control.Click> Ereignis von der Menübefehl zum Kopieren auf die standardmäßige Menü "Bearbeiten".</span><span class="sxs-lookup"><span data-stu-id="1b998-105">You would create a procedure that copies selected text to the Clipboard using the <xref:System.Windows.Forms.Control.Click> event of the Copy menu item on the standard Edit menu.</span></span>  
  
 <span data-ttu-id="1b998-106">Da MDI-Anwendung viele Instanzen der gleichen untergeordneten Formulars verfügen kann, muss die Prozedur wissen, welches Formular verwendet.</span><span class="sxs-lookup"><span data-stu-id="1b998-106">Because an MDI application can have many instances of the same child form, the procedure needs to know which form to use.</span></span> <span data-ttu-id="1b998-107">Um die richtige Form anzugeben, verwenden die <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> -Eigenschaft, wodurch das untergeordnete Formular, das den Fokus besitzt, oder das zuletzt aktiv war.</span><span class="sxs-lookup"><span data-stu-id="1b998-107">To specify the correct form, use the <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> property, which returns the child form that has the focus or that was most recently active.</span></span>  
  
 <span data-ttu-id="1b998-108">Wenn Sie mehrere Steuerelemente in einem Formular haben, müssen Sie auch angeben, welches Steuerelement aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="1b998-108">When you have several controls on a form, you also need to specify which control is active.</span></span> <span data-ttu-id="1b998-109">Wie die <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> -Eigenschaft, die <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> Eigenschaft gibt das Steuerelement mit Fokus auf dem aktiven untergeordneten Formular zurück.</span><span class="sxs-lookup"><span data-stu-id="1b998-109">Like the <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> property, the <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> property returns the control with the focus on the active child form.</span></span> <span data-ttu-id="1b998-110">Das folgende Verfahren veranschaulicht eine Kopierprozedur, die von einem untergeordneten Formularmenü, ein Menü für das MDI-Formular oder eine Symbolleisten-Schaltfläche aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="1b998-110">The procedure below illustrates a copy procedure that can be called from a child form menu, a menu on the MDI form, or a toolbar button.</span></span>  
  
### <a name="to-determine-the-active-mdi-child-to-copy-its-text-to-the-clipboard"></a><span data-ttu-id="1b998-111">Bestimmen des aktive untergeordneten MDI-Fensters (um den Text in die Zwischenablage kopieren)</span><span class="sxs-lookup"><span data-stu-id="1b998-111">To determine the active MDI child (to copy its text to the Clipboard)</span></span>  
  
1.  <span data-ttu-id="1b998-112">Kopieren Sie den Text zum aktiven Steuerelement des aktiven untergeordneten Formulars innerhalb einer Methode in die Zwischenablage.</span><span class="sxs-lookup"><span data-stu-id="1b998-112">Within a method, copy the text of the active control of the active child form to the Clipboard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1b998-113">In diesem Beispiel geht davon aus, es ist ein übergeordnetes MDI-Formular (`Form1`), die eine oder mehrere untergeordnete MDI-Fenster mit wurde ein <xref:System.Windows.Forms.RichTextBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="1b998-113">This example assumes there is an MDI parent form (`Form1`) that has one or more MDI child windows containing a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="1b998-114">Weitere Informationen finden Sie unter [Erstellen von übergeordneten MDI-Formularen](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md).</span><span class="sxs-lookup"><span data-stu-id="1b998-114">For more information, see [Creating MDI Parent Forms](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md).</span></span>  
  
    ```vb  
    Public Sub mniCopy_Click(ByVal sender As Object, _  
       ByVal e As System.EventArgs) Handles mniCopy.Click  
  
       ' Determine the active child form.  
       Dim activeChild As Form = Me.ActiveMDIChild  
  
       ' If there is an active child form, find the active control, which  
       ' in this example should be a RichTextBox.  
       If (Not activeChild Is Nothing) Then  
          Dim theBox As RichTextBox = _  
            TryCast(activeChild.ActiveControl, RichTextBox)  
  
          If (Not theBox Is Nothing) Then  
             'Put selected text on Clipboard.  
             Clipboard.SetDataObject(theBox.SelectedText)  
          Else  
             MessageBox.Show("You need to select a RichTextBox.")  
          End If  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    protected void mniCopy_Click (object sender, System.EventArgs e)  
    {  
       // Determine the active child form.  
       Form activeChild = this.ActiveMdiChild;  
  
       // If there is an active child form, find the active control, which  
       // in this example should be a RichTextBox.  
       if (activeChild != null)  
       {    
          try  
          {  
             RichTextBox theBox = (RichTextBox)activeChild.ActiveControl;  
             if (theBox != null)  
             {  
                // Put the selected text on the Clipboard.  
                Clipboard.SetDataObject(theBox.SelectedText);  
  
             }  
          }  
          catch  
          {  
             MessageBox.Show("You need to select a RichTextBox.");  
          }  
       }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1b998-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b998-115">See also</span></span>
- [<span data-ttu-id="1b998-116">MDI-Anwendungen (Multiple Document Interface)</span><span class="sxs-lookup"><span data-stu-id="1b998-116">Multiple-Document Interface (MDI) Applications</span></span>](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="1b998-117">Vorgehensweise: Erstellen von übergeordneten MDI-Formularen</span><span class="sxs-lookup"><span data-stu-id="1b998-117">How to: Create MDI Parent Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="1b998-118">Vorgehensweise: Erstellen von untergeordneten MDI-Formularen</span><span class="sxs-lookup"><span data-stu-id="1b998-118">How to: Create MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="1b998-119">Vorgehensweise: Senden von Daten an das aktive untergeordnete MDI-Element</span><span class="sxs-lookup"><span data-stu-id="1b998-119">How to: Send Data to the Active MDI Child</span></span>](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)
- [<span data-ttu-id="1b998-120">Vorgehensweise: Anordnen von untergeordneten MDI-Formularen</span><span class="sxs-lookup"><span data-stu-id="1b998-120">How to: Arrange MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)
