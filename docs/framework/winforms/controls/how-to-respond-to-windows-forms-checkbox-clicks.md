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
ms.openlocfilehash: 6ff20c443519446d3804b325924cb3c5cbedea97
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141925"
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a>Gewusst wie: Reagieren auf das Klicken auf Kontrollkästchen in Windows Forms
Wenn ein Benutzer auf <xref:System.Windows.Forms.CheckBox> ein Windows <xref:System.Windows.Forms.Control.Click> Forms-Steuerelement klickt, tritt das Ereignis auf. Sie können Ihre Anwendung so programmieren, dass sie je nach Status des Kontrollkästchens eine Aktion ausführt.  
  
### <a name="to-respond-to-checkbox-clicks"></a>Um auf CheckBox-Klicks zu reagieren  
  
1. Verwenden <xref:System.Windows.Forms.Control.Click> Sie im Ereignishandler die <xref:System.Windows.Forms.CheckBox.Checked%2A> Eigenschaft, um den Status des Steuerelements zu bestimmen, und führen Sie alle erforderlichen Aktionen aus.  
  
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
    > Wenn der Benutzer versucht, <xref:System.Windows.Forms.CheckBox> auf das Steuerelement zu doppelklicken, wird jeder Klick separat verarbeitet. D. h., das <xref:System.Windows.Forms.CheckBox> Steuerelement unterstützt das Doppelklickereignis nicht.  
  
    > [!NOTE]
    > Wenn <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> die `true` Eigenschaft (Standardeinstellung) ist, wird die <xref:System.Windows.Forms.CheckBox> automatisch ausgewählt oder gelöscht, wenn darauf geklickt wird. Andernfalls müssen Sie die <xref:System.Windows.Forms.CheckBox.Checked%2A> Eigenschaft manuell <xref:System.Windows.Forms.Control.Click> festlegen, wenn das Ereignis eintritt.  
  
     Sie können das <xref:System.Windows.Forms.CheckBox> Steuerelement auch verwenden, um eine Vorgehensweise zu bestimmen.  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a>So ermitteln Sie eine Vorgehensweise, wenn auf ein Kontrollkästchen geklickt wird  
  
1. Verwenden Sie eine Fallanweisung, <xref:System.Windows.Forms.CheckBox.CheckState%2A> um den Wert der Eigenschaft abzufragen, um eine Vorgehensweise zu bestimmen. Wenn <xref:System.Windows.Forms.CheckBox.ThreeState%2A> die Eigenschaft `true`auf <xref:System.Windows.Forms.CheckBox.CheckState%2A> festgelegt ist, gibt die Eigenschaft möglicherweise drei mögliche Werte zurück, die das Kontrollkästchen darstellen, das Kontrollkästchen deaktiviert ist oder ein dritter unbestimmter Zustand, in dem das Kontrollkästchen mit einem abgeblendeten Erscheinungsbild angezeigt wird, um anzuzeigen, dass die Option nicht verfügbar ist.  
  
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
    > Wenn <xref:System.Windows.Forms.CheckBox.ThreeState%2A> die Eigenschaft `true`auf <xref:System.Windows.Forms.CheckBox.Checked%2A> festgelegt `true` ist, <xref:System.Windows.Forms.CheckState.Checked> <xref:System.Windows.Forms.CheckState.Indeterminate>gibt die Eigenschaft für beide und zurück.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.CheckBox>
- [Übersicht über das CheckBox-Steuerelement](checkbox-control-overview-windows-forms.md)
- [Gewusst wie: Festlegen von Optionen mit CheckBox-Steuerelementen in Windows Forms](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [CheckBox-Steuerung](checkbox-control-windows-forms.md)
