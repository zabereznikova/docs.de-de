---
title: 'Vorgehensweise: Festlegen von Optionen mit CheckBox-Steuerelementen in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- checked
helpviewer_keywords:
- CheckBox control [Windows Forms], checked state
- check boxes [Windows Forms], using to set options
- CheckBox control [Windows Forms], using to set options
ms.assetid: 2ac70498-7e3e-4e07-8901-ccabaeb5fd3e
ms.openlocfilehash: 881996563acef36a1981ca6236c155b8fc56ef0a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59307309"
---
# <a name="how-to-set-options-with-windows-forms-checkbox-controls"></a><span data-ttu-id="ea025-102">Vorgehensweise: Festlegen von Optionen mit CheckBox-Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ea025-102">How to: Set Options with Windows Forms CheckBox Controls</span></span>
<span data-ttu-id="ea025-103">Ein Windows Forms <xref:System.Windows.Forms.CheckBox> Steuerelement wird verwendet, um Benutzern True/False oder Ja/Nein-Optionen.</span><span class="sxs-lookup"><span data-stu-id="ea025-103">A Windows Forms <xref:System.Windows.Forms.CheckBox> control is used to give users True/False or Yes/No options.</span></span> <span data-ttu-id="ea025-104">Das Steuerelement zeigt ein Häkchen auf, wenn es ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="ea025-104">The control displays a check mark when it is selected.</span></span>  
  
### <a name="to-set-options-with-checkbox-controls"></a><span data-ttu-id="ea025-105">Festlegen von Optionen mit CheckBox-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="ea025-105">To set options with CheckBox controls</span></span>  
  
1. <span data-ttu-id="ea025-106">Überprüfen Sie den Wert, der die <xref:System.Windows.Forms.CheckBox.Checked%2A> Eigenschaft, um seinen Status zu bestimmen, und verwenden diesen Wert, um eine Option festlegen.</span><span class="sxs-lookup"><span data-stu-id="ea025-106">Examine the value of the <xref:System.Windows.Forms.CheckBox.Checked%2A> property to determine its state, and use that value to set an option.</span></span>  
  
     <span data-ttu-id="ea025-107">Im Codebeispiel unten, wenn die <xref:System.Windows.Forms.CheckBox> des Steuerelements <xref:System.Windows.Forms.CheckBox.CheckedChanged> Ereignis wird ausgelöst, des Formulars <xref:System.Windows.Forms.Control.AllowDrop%2A> -Eigenschaftensatz auf `false` Wenn Sie dieses Kontrollkästchen aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="ea025-107">In the code sample below, when the <xref:System.Windows.Forms.CheckBox> control's <xref:System.Windows.Forms.CheckBox.CheckedChanged> event is raised, the form's <xref:System.Windows.Forms.Control.AllowDrop%2A> property is set to `false` if the check box is checked.</span></span> <span data-ttu-id="ea025-108">Dies eignet sich für Situationen, in dem Sie Benutzerinteraktion einschränken möchten.</span><span class="sxs-lookup"><span data-stu-id="ea025-108">This is useful for situations where you want to restrict user interaction.</span></span>  
  
    ```vb  
    Private Sub CheckBox1_CheckedChanged(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles CheckBox1.CheckedChanged  
       ' Determine the CheckState of the check box.  
       If CheckBox1.CheckState = CheckState.Checked Then  
          ' If checked, do not allow items to be dragged onto the form.  
          Me.AllowDrop = False  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_CheckedChanged(object sender, System.EventArgs e)  
    {  
       // Determine the CheckState of the check box.  
       if (checkBox1.CheckState == CheckState.Checked)   
       {  
          // If checked, do not allow items to be dragged onto the form.  
          this.AllowDrop = false;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // Determine the CheckState of the check box.  
          if (checkBox1->CheckState == CheckState::Checked)   
          {  
             // If checked, do not allow items to be dragged onto the form.  
             this->AllowDrop = false;  
          }  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ea025-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ea025-109">See also</span></span>

- <xref:System.Windows.Forms.CheckBox>
- [<span data-ttu-id="ea025-110">Übersicht über das CheckBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ea025-110">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="ea025-111">Vorgehensweise: Reagieren Sie auf Windows Forms das Klicken auf Kontrollkästchen</span><span class="sxs-lookup"><span data-stu-id="ea025-111">How to: Respond to Windows Forms CheckBox Clicks</span></span>](how-to-respond-to-windows-forms-checkbox-clicks.md)
- [<span data-ttu-id="ea025-112">CheckBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ea025-112">CheckBox Control</span></span>](checkbox-control-windows-forms.md)
