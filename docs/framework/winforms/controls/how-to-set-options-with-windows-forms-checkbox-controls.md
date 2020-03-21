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
# <a name="how-to-set-options-with-windows-forms-checkbox-controls"></a>Gewusst wie: Festlegen von Optionen mit CheckBox-Steuerelementen in Windows Forms
Ein Windows <xref:System.Windows.Forms.CheckBox> Forms-Steuerelement wird verwendet, um Benutzern True/False- oder Yes/No-Optionen zu geben. Das Steuerelement zeigt ein Häkchen an, wenn es ausgewählt ist.  
  
### <a name="to-set-options-with-checkbox-controls"></a>So legen Sie Optionen mit CheckBox-Steuerelementen fest  
  
1. Untersuchen Sie den <xref:System.Windows.Forms.CheckBox.Checked%2A> Wert der Eigenschaft, um ihren Status zu bestimmen, und verwenden Sie diesen Wert, um eine Option festzulegen.  
  
     Wenn im Codebeispiel unten <xref:System.Windows.Forms.CheckBox> das <xref:System.Windows.Forms.CheckBox.CheckedChanged> Ereignis des Steuerelements ausgelöst <xref:System.Windows.Forms.Control.AllowDrop%2A> wird, `false` wird die Eigenschaft des Formulars auf das Kontrollkästchen festgelegt. Dies ist nützlich für Situationen, in denen Sie die Benutzerinteraktion einschränken möchten.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.CheckBox>
- [Übersicht über das CheckBox-Steuerelement](checkbox-control-overview-windows-forms.md)
- [Gewusst wie: Reagieren auf das Klicken auf Kontrollkästchen in Windows Forms](how-to-respond-to-windows-forms-checkbox-clicks.md)
- [CheckBox-Steuerung](checkbox-control-windows-forms.md)
