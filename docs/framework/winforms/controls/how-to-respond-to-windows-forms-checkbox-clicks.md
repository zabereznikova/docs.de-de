---
title: Reagieren auf CheckBox-Klicks
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
ms.openlocfilehash: ba2afb52939a6274978ce725dac19b5622419b99
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735660"
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a>Gewusst wie: Reagieren auf das Klicken auf Kontrollkästchen in Windows Forms
Wenn ein Benutzer auf eine Windows Forms <xref:System.Windows.Forms.CheckBox>-Steuerelement klickt, tritt das <xref:System.Windows.Forms.Control.Click>-Ereignis auf. Sie können Ihre Anwendung so programmieren, dass je nach Zustand des Kontrollkästchens Aktionen ausgeführt werden.  
  
### <a name="to-respond-to-checkbox-clicks"></a>So reagieren Sie auf CheckBox-Klicks  
  
1. Verwenden Sie im <xref:System.Windows.Forms.Control.Click>-Ereignishandler die <xref:System.Windows.Forms.CheckBox.Checked%2A>-Eigenschaft, um den Zustand des Steuer Elements zu bestimmen und alle notwendigen Aktionen auszuführen.  
  
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
    > Wenn der Benutzer versucht, auf das <xref:System.Windows.Forms.CheckBox>-Steuerelement zu doppelklicken, wird jeder Klick separat verarbeitet. Das <xref:System.Windows.Forms.CheckBox> Steuerelement unterstützt das Doppelklick Ereignis also nicht.  
  
    > [!NOTE]
    > Wenn die <xref:System.Windows.Forms.CheckBox.AutoCheck%2A>-Eigenschaft `true` (Standardeinstellung) ist, wird die <xref:System.Windows.Forms.CheckBox> automatisch ausgewählt oder gelöscht, wenn darauf geklickt wird. Andernfalls müssen Sie die <xref:System.Windows.Forms.CheckBox.Checked%2A>-Eigenschaft manuell festlegen, wenn das <xref:System.Windows.Forms.Control.Click> Ereignis auftritt.  
  
     Sie können auch das <xref:System.Windows.Forms.CheckBox>-Steuerelement verwenden, um eine Vorgehensweise zu bestimmen.  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a>So bestimmen Sie eine Vorgehensweise, wenn auf ein Kontrollkästchen geklickt wird  
  
1. Verwenden Sie eine Case-Anweisung, um den Wert der <xref:System.Windows.Forms.CheckBox.CheckState%2A>-Eigenschaft abzufragen, um eine Vorgehensweise zu bestimmen. Wenn die <xref:System.Windows.Forms.CheckBox.ThreeState%2A>-Eigenschaft auf `true`festgelegt ist, gibt die <xref:System.Windows.Forms.CheckBox.CheckState%2A>-Eigenschaft möglicherweise drei mögliche Werte zurück, die das Kontrollkästchen darstellen, das Kontrollkästchen deaktiviert ist, oder einen dritten unbestimmten Zustand, in dem das Feld mit einer Abbild Darstellung angezeigt wird, um anzugeben, dass die Option nicht verfügbar ist.  
  
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
    > Wenn die <xref:System.Windows.Forms.CheckBox.ThreeState%2A>-Eigenschaft auf `true`festgelegt ist, gibt die <xref:System.Windows.Forms.CheckBox.Checked%2A>-Eigenschaft `true` für <xref:System.Windows.Forms.CheckState.Checked> und <xref:System.Windows.Forms.CheckState.Indeterminate>zurück.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.CheckBox>
- [Übersicht über das CheckBox-Steuerelement](checkbox-control-overview-windows-forms.md)
- [Gewusst wie: Festlegen von Optionen mit CheckBox-Steuerelementen in Windows Forms](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [CheckBox-Steuerelement](checkbox-control-windows-forms.md)
