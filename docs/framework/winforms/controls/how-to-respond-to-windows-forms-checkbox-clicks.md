---
title: 'Vorgehensweise: Reagieren auf das Klicken auf Kontrollkästchen in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Click event [Windows Forms], CheckBox control
- CheckBox control [Windows Forms], Click events
- events [Windows Forms], Click events
- double-clicks
- check boxes [Windows Forms], responding to events
ms.assetid: c39f901e-8899-43b6-aa31-939cbf7089fb
ms.openlocfilehash: 7ff6b2aad9ef0775547af57f11af28839e69637c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69914981"
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a>Vorgehensweise: Reagieren auf das Klicken auf Kontrollkästchen in Windows Forms
Wenn ein Benutzer auf ein Windows Forms <xref:System.Windows.Forms.CheckBox> -Steuerelement <xref:System.Windows.Forms.Control.Click> klickt, tritt das-Ereignis auf. Sie können Ihre Anwendung so programmieren, dass je nach Zustand des Kontrollkästchens Aktionen ausgeführt werden.  
  
### <a name="to-respond-to-checkbox-clicks"></a>So reagieren Sie auf CheckBox-Klicks  
  
1. Verwenden Sie im- <xref:System.Windows.Forms.CheckBox.Checked%2A> Ereignishandlerdie-Eigenschaft,umdenZustanddesSteuerElementszubestimmenundallenotwendigenAktionenauszuführen.<xref:System.Windows.Forms.Control.Click>  
  
    ```vb  
    Private Sub CheckBox1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles CheckBox1.Click  
       ' The CheckBox control's Text property is changed each time the   
       ' control is clicked, indicating a checked or unchecked state.  
       If CheckBox1.Checked = True Then  
          CheckBox1.Text = "Checked"  
       Else  
          CheckBox1.Text = "Unchecked"  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_Click(object sender, System.EventArgs e)  
    {  
       // The CheckBox control's Text property is changed each time the   
       // control is clicked, indicating a checked or unchecked state.  
       if (checkBox1.Checked)  
       {  
          checkBox1.Text = "Checked";  
       }  
       else  
       {  
          checkBox1.Text = "Unchecked";  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if (checkBox1->Checked)  
          {  
             checkBox1->Text = "Checked";  
          }  
          else  
          {  
             checkBox1->Text = "Unchecked";  
          }  
       }  
    ```  
  
    > [!NOTE]
    > Wenn der Benutzer versucht, auf das <xref:System.Windows.Forms.CheckBox> Steuerelement zu doppelklicken, wird jeder Klick separat verarbeitet, d. h. <xref:System.Windows.Forms.CheckBox> , das Steuerelement unterstützt das Doppelklick Ereignis nicht.  
  
    > [!NOTE]
    > Wenn die <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> -Eigenschaft `true` ist (Standardeinstellung), <xref:System.Windows.Forms.CheckBox> wird automatisch ausgewählt oder gelöscht, wenn darauf geklickt wird. Andernfalls müssen Sie die <xref:System.Windows.Forms.CheckBox.Checked%2A> -Eigenschaft manuell festlegen, wenn das <xref:System.Windows.Forms.Control.Click> -Ereignis auftritt.  
  
     Sie können auch das <xref:System.Windows.Forms.CheckBox> -Steuerelement verwenden, um eine Vorgehensweise zu bestimmen.  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a>So bestimmen Sie eine Vorgehensweise, wenn auf ein Kontrollkästchen geklickt wird  
  
1. Verwenden Sie eine Case-Anweisung, um den Wert <xref:System.Windows.Forms.CheckBox.CheckState%2A> der-Eigenschaft abzufragen, um eine Vorgehensweise zu bestimmen. Wenn die <xref:System.Windows.Forms.CheckBox.ThreeState%2A> -Eigenschaft auf `true`festgelegt ist <xref:System.Windows.Forms.CheckBox.CheckState%2A> , gibt die-Eigenschaft möglicherweise drei mögliche Werte zurück, die das Kontrollkästchen darstellen, das Kontrollkästchen deaktiviert ist, oder einen dritten unbestimmten Zustand, in dem das Feld mit abgeblendet angezeigt wird. Darstellung, um anzugeben, dass die Option nicht verfügbar ist.  
  
    ```vb  
    Private Sub CheckBox1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles CheckBox1.Click  
       Select Case CheckBox1.CheckState  
          Case CheckState.Checked  
             ' Code for checked state.  
          Case CheckState.Unchecked  
             ' Code for unchecked state.  
          Case CheckState.Indeterminate  
             ' Code for indeterminate state.  
       End Select   
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_Click(object sender, System.EventArgs e)  
    {  
       switch(checkBox1.CheckState)  
       {  
          case CheckState.Checked:  
             // Code for checked state.  
             break;  
          case CheckState.Unchecked:  
             // Code for unchecked state.  
             break;  
          case CheckState.Indeterminate:  
             // Code for indeterminate state.  
             break;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          switch(checkBox1->CheckState) {  
             case CheckState::Checked:  
                // Code for checked state.  
                break;  
             case CheckState::Unchecked:  
                // Code for unchecked state.  
                break;  
             case CheckState::Indeterminate:  
                // Code for indeterminate state.  
                break;  
          }  
       }  
    ```  
  
    > [!NOTE]
    > Wenn die <xref:System.Windows.Forms.CheckBox.ThreeState%2A> -Eigenschaft auf `true`festgelegt ist <xref:System.Windows.Forms.CheckBox.Checked%2A> , gibt die- <xref:System.Windows.Forms.CheckState.Checked> Eigenschaft <xref:System.Windows.Forms.CheckState.Indeterminate>sowohl für als auch für zurück `true` .  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.CheckBox>
- [Übersicht über das CheckBox-Steuerelement](checkbox-control-overview-windows-forms.md)
- [Vorgehensweise: Festlegen von Optionen mit CheckBox-Steuerelementen Windows Forms](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [CheckBox-Steuerelement](checkbox-control-windows-forms.md)
