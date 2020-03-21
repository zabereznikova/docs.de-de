---
title: Festlegen von Optionen mit CheckBox-Steuerelementen
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
ms.openlocfilehash: 00b467836d8e60aeee51a010a6384abf7dd73c56
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141847"
---
# <a name="how-to-set-options-with-windows-forms-checkbox-controls"></a><span data-ttu-id="59275-102">Gewusst wie: Festlegen von Optionen mit CheckBox-Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="59275-102">How to: Set Options with Windows Forms CheckBox Controls</span></span>
<span data-ttu-id="59275-103">Ein Windows <xref:System.Windows.Forms.CheckBox> Forms-Steuerelement wird verwendet, um Benutzern True/False- oder Yes/No-Optionen zu geben.</span><span class="sxs-lookup"><span data-stu-id="59275-103">A Windows Forms <xref:System.Windows.Forms.CheckBox> control is used to give users True/False or Yes/No options.</span></span> <span data-ttu-id="59275-104">Das Steuerelement zeigt ein Häkchen an, wenn es ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="59275-104">The control displays a check mark when it is selected.</span></span>  
  
### <a name="to-set-options-with-checkbox-controls"></a><span data-ttu-id="59275-105">So legen Sie Optionen mit CheckBox-Steuerelementen fest</span><span class="sxs-lookup"><span data-stu-id="59275-105">To set options with CheckBox controls</span></span>  
  
1. <span data-ttu-id="59275-106">Untersuchen Sie den <xref:System.Windows.Forms.CheckBox.Checked%2A> Wert der Eigenschaft, um ihren Status zu bestimmen, und verwenden Sie diesen Wert, um eine Option festzulegen.</span><span class="sxs-lookup"><span data-stu-id="59275-106">Examine the value of the <xref:System.Windows.Forms.CheckBox.Checked%2A> property to determine its state, and use that value to set an option.</span></span>  
  
     <span data-ttu-id="59275-107">Wenn im Codebeispiel unten <xref:System.Windows.Forms.CheckBox> das <xref:System.Windows.Forms.CheckBox.CheckedChanged> Ereignis des Steuerelements ausgelöst <xref:System.Windows.Forms.Control.AllowDrop%2A> wird, `false` wird die Eigenschaft des Formulars auf das Kontrollkästchen festgelegt.</span><span class="sxs-lookup"><span data-stu-id="59275-107">In the code sample below, when the <xref:System.Windows.Forms.CheckBox> control's <xref:System.Windows.Forms.CheckBox.CheckedChanged> event is raised, the form's <xref:System.Windows.Forms.Control.AllowDrop%2A> property is set to `false` if the check box is checked.</span></span> <span data-ttu-id="59275-108">Dies ist nützlich für Situationen, in denen Sie die Benutzerinteraktion einschränken möchten.</span><span class="sxs-lookup"><span data-stu-id="59275-108">This is useful for situations where you want to restrict user interaction.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="59275-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="59275-109">See also</span></span>

- <xref:System.Windows.Forms.CheckBox>
- [<span data-ttu-id="59275-110">Übersicht über das CheckBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="59275-110">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="59275-111">Gewusst wie: Reagieren auf das Klicken auf Kontrollkästchen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="59275-111">How to: Respond to Windows Forms CheckBox Clicks</span></span>](how-to-respond-to-windows-forms-checkbox-clicks.md)
- [<span data-ttu-id="59275-112">CheckBox-Steuerung</span><span class="sxs-lookup"><span data-stu-id="59275-112">CheckBox Control</span></span>](checkbox-control-windows-forms.md)
