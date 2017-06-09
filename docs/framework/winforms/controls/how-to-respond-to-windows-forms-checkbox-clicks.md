---
title: "Gewusst wie: Reagieren auf das Klicken auf Kontrollk&#228;stchen in Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Kontrollkästchen, Reagieren auf Ereignisse"
  - "CheckBox-Steuerelement [Windows Forms], Click-Ereignisse"
  - "Click-Ereignis, CheckBox-Steuerelement"
  - "Doppelklicken"
  - "Ereignisse [Windows Forms], Click-Ereignisse"
ms.assetid: c39f901e-8899-43b6-aa31-939cbf7089fb
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Reagieren auf das Klicken auf Kontrollk&#228;stchen in Windows Forms
Sobald ein Benutzer auf das <xref:System.Windows.Forms.CheckBox>\-Steuerelement in Windows Forms klickt, wird das <xref:System.Windows.Forms.Control.Click>\-Ereignis ausgelöst.  Sie können Ihre Anwendung so programmieren, dass abhängig vom Zustand des Kontrollkästchens eine bestimmte Aktion ausgeführt wird.  
  
### So reagieren Sie auf das Klicken auf Kontrollkästchen  
  
1.  Stellen Sie im <xref:System.Windows.Forms.Control.Click>\-Ereignishandler anhand der <xref:System.Windows.Forms.CheckBox.Checked%2A>\-Eigenschaft den Zustand des Steuerelements fest, und führen Sie alle erforderlichen Aktionen aus.  
  
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
    >  Wenn der Benutzer auf das <xref:System.Windows.Forms.CheckBox>\-Steuerelement doppelklickt, wird jedes Klicken einzeln verarbeitet, das Doppelklickereignis wird also vom <xref:System.Windows.Forms.CheckBox>\-Steuerelement nicht unterstützt.  
  
    > [!NOTE]
    >  Wenn der Wert der <xref:System.Windows.Forms.CheckBox.AutoCheck%2A>\-Eigenschaft `true` lautet \(der Standardwert\), wird das <xref:System.Windows.Forms.CheckBox>\-Steuerelement durch Klicken automatisch aktiviert bzw. deaktiviert.  Andernfalls muss der Wert der <xref:System.Windows.Forms.CheckBox.Checked%2A>\-Eigenschaft bei Auftreten des <xref:System.Windows.Forms.Control.Click>\-Ereignisses manuell festgelegt werden.  
  
     Darüber hinaus können Sie mit dem <xref:System.Windows.Forms.CheckBox>\-Steuerelement eine Aktion ausführen.  
  
### So legen Sie fest, welche Aktion beim Klicken auf ein Kontrollkästchen ausgeführt wird  
  
1.  Fragen Sie den Wert der <xref:System.Windows.Forms.CheckBox.CheckState%2A>\-Eigenschaft mit einer Case\-Anweisung ab, um die Aktion zu bestimmen.  Wenn die <xref:System.Windows.Forms.CheckBox.ThreeState%2A>\-Eigenschaft auf `true` festgelegt ist, kann die <xref:System.Windows.Forms.CheckBox.CheckState%2A>\-Eigenschaft einen der folgenden drei Zustandswerte zurückgeben: Das Kästchen ist aktiviert, das Kästchen ist deaktiviert, oder es liegt ein dritter unbestimmter Zustand vor, bei dem das Kontrollkästchen abgeblendet und die Option somit nicht verfügbar ist.  
  
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
    >  Wenn die <xref:System.Windows.Forms.CheckBox.ThreeState%2A>\-Eigenschaft auf `true` festgelegt ist, gibt die <xref:System.Windows.Forms.CheckBox.Checked%2A>\-Eigenschaft für <xref:System.Windows.Forms.CheckState> und <xref:System.Windows.Forms.CheckState> den Wert `true` zurück.  
  
## Siehe auch  
 <xref:System.Windows.Forms.CheckBox>   
 [Übersicht über das CheckBox\-Steuerelement](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)   
 [Gewusst wie: Festlegen von Optionen mit CheckBox\-Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-options-with-windows-forms-checkbox-controls.md)   
 [CheckBox\-Steuerelement](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)