---
title: 'Vorgehensweise: Festlegen von Optionen mit CheckBox-Steuerelementen für Windows Forms'
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
ms.openlocfilehash: 3eb68d76d936f13e78d13629455c6ac7fb537b40
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57714787"
---
# <a name="how-to-set-options-with-windows-forms-checkbox-controls"></a>Vorgehensweise: Festlegen von Optionen mit CheckBox-Steuerelementen für Windows Forms
Ein Windows Forms <xref:System.Windows.Forms.CheckBox> Steuerelement wird verwendet, um Benutzern True/False oder Ja/Nein-Optionen. Das Steuerelement zeigt ein Häkchen auf, wenn es ausgewählt wird.  
  
### <a name="to-set-options-with-checkbox-controls"></a>Festlegen von Optionen mit CheckBox-Steuerelementen  
  
1.  Überprüfen Sie den Wert, der die <xref:System.Windows.Forms.CheckBox.Checked%2A> Eigenschaft, um seinen Status zu bestimmen, und verwenden diesen Wert, um eine Option festlegen.  
  
     Im Codebeispiel unten, wenn die <xref:System.Windows.Forms.CheckBox> des Steuerelements <xref:System.Windows.Forms.CheckBox.CheckedChanged> Ereignis wird ausgelöst, des Formulars <xref:System.Windows.Forms.Control.AllowDrop%2A> -Eigenschaftensatz auf `false` Wenn Sie dieses Kontrollkästchen aktiviert ist. Dies eignet sich für Situationen, in dem Sie Benutzerinteraktion einschränken möchten.  
  
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
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.CheckBox>
- [Übersicht über das CheckBox-Steuerelement](checkbox-control-overview-windows-forms.md)
- [Vorgehensweise: Reagieren Sie auf Windows Forms das Klicken auf Kontrollkästchen](how-to-respond-to-windows-forms-checkbox-clicks.md)
- [CheckBox-Steuerelement](checkbox-control-windows-forms.md)
