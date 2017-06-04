---
title: "Gewusst wie: Festlegen von Optionen mit CheckBox-Steuerelementen in Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "checked"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Kontrollkästchen, Zum Festlegen von Optionen"
  - "CheckBox-Steuerelement [Windows Forms], Aktivierter Zustand"
  - "CheckBox-Steuerelement [Windows Forms], Zum Festlegen von Optionen"
ms.assetid: 2ac70498-7e3e-4e07-8901-ccabaeb5fd3e
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Festlegen von Optionen mit CheckBox-Steuerelementen in Windows Forms
In Windows Forms dienen <xref:System.Windows.Forms.CheckBox>\-Steuerelemente dazu, dem Benutzer die Auswahl zwischen True\/False bzw. Ja\/Nein zu bieten.  Wenn das Steuerelement aktiviert ist, wird ein Häkchen angezeigt.  
  
### So legen Sie Optionen mit CheckBox\-Steuerelementen fest  
  
1.  Stellen Sie den Zustand der <xref:System.Windows.Forms.CheckBox.Checked%2A>\-Eigenschaft fest, indem Sie ihren Wert prüfen. Legen Sie mithilfe dieses Werts eine Option fest.  
  
     Wenn das <xref:System.Windows.Forms.CheckBox.CheckedChanged>\-Ereignis des <xref:System.Windows.Forms.CheckBox>\-Steuerelements ausgelöst wird, wird im folgenden Codebeispiel die <xref:System.Windows.Forms.Control.AllowDrop%2A>\-Eigenschaft des Formulars auf `false` festgelegt, sofern das Kontrollkästchen aktiviert ist.  Dies empfiehlt sich, wenn Sie die Benutzerinteraktion einschränken möchten.  
  
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
  
## Siehe auch  
 <xref:System.Windows.Forms.CheckBox>   
 [Übersicht über das CheckBox\-Steuerelement](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)   
 [Gewusst wie: Reagieren auf das Klicken auf Kontrollkästchen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-checkbox-clicks.md)   
 [CheckBox\-Steuerelement](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)