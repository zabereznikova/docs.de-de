---
title: "Gewusst wie: Reagieren auf das Klicken auf Kontrollkästchen in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8f15adb84f92c9434d6835e80f08bf1d9bd500ad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a>Gewusst wie: Reagieren auf das Klicken auf Kontrollkästchen in Windows Forms
Wenn ein Benutzer einer Windows Forms klickt <xref:System.Windows.Forms.CheckBox> -Steuerelement, das <xref:System.Windows.Forms.Control.Click> Ereignis tritt auf. Programmieren Sie Ihre Anwendung eine Aktion, die je nach Zustand des Kontrollkästchens auszuführen.  
  
### <a name="to-respond-to-checkbox-clicks"></a>So reagieren Sie auf das Klicken auf Kontrollkästchen  
  
1.  In der <xref:System.Windows.Forms.Control.Click> -Ereignishandler der <xref:System.Windows.Forms.CheckBox.Checked%2A> Eigenschaft zum Bestimmen der Zustand des Steuerelements, und führen alle erforderlichen Aktionen.  
  
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
    >  Wenn der Benutzer versucht, doppelklicken Sie auf die <xref:System.Windows.Forms.CheckBox> -Steuerelement, jedem Mausklick wird separat verarbeitet werden, d. h., die <xref:System.Windows.Forms.CheckBox> Steuerelement unterstützt nicht das Doppelklickereignis.  
  
    > [!NOTE]
    >  Wenn die <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> Eigenschaft ist `true` (Standard), die <xref:System.Windows.Forms.CheckBox> automatisch aktiviert oder deaktiviert werden, wenn darauf geklickt wird. Andernfalls müssen Sie manuell festlegen der <xref:System.Windows.Forms.CheckBox.Checked%2A> Eigenschaft bei der <xref:System.Windows.Forms.Control.Click> Ereignis tritt auf.  
  
     Sie können auch die <xref:System.Windows.Forms.CheckBox> Steuerelement um eine Vorgehensweise zu bestimmen.  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a>Um zu bestimmen, Aktion, wenn Sie das Kontrollkästchen geklickt wird  
  
1.  Eine Case-Anweisung den Wert der Abfragen verwenden die <xref:System.Windows.Forms.CheckBox.CheckState%2A> -Eigenschaft können Sie eine Vorgehensweise zu bestimmen. Wenn die <xref:System.Windows.Forms.CheckBox.ThreeState%2A> -Eigenschaftensatz auf `true`, die <xref:System.Windows.Forms.CheckBox.CheckState%2A> Eigenschaft gelegten drei mögliche Werten, die das zu überprüfende Feld darstellen, Feld deaktiviert wird, oder eine dritte unbestimmten Zustand, in dem Feld angezeigt wird, mit einem abgeblendet Darstellung an, dass die Option ist nicht verfügbar.  
  
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
    >  Wenn die <xref:System.Windows.Forms.CheckBox.ThreeState%2A> -Eigenschaftensatz auf `true`, <xref:System.Windows.Forms.CheckBox.Checked%2A> -Eigenschaft gibt `true` für beide <xref:System.Windows.Forms.CheckState.Checked> und <xref:System.Windows.Forms.CheckState.Indeterminate>.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.CheckBox>  
 [Übersicht über das CheckBox-Steuerelement](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)  
 [Gewusst wie: Festlegen von Optionen mit CheckBox-Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-options-with-windows-forms-checkbox-controls.md)  
 [CheckBox-Steuerelement](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)
