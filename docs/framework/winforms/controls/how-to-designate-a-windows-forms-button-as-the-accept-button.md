---
title: "Gewusst wie: Definieren einer Windows&#160;Forms-Schaltfl&#228;che als &quot;Annehmen&quot;-Schaltfl&#228;che | Microsoft Docs"
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
  - "Annehmen (Schaltfläche in Windows Forms)"
  - "Button-Steuerelement [Windows Forms], Definieren als Standard"
  - "Schaltflächen, Standard in Windows Forms"
  - "Windows Forms-Steuerelemente, Standardschaltfläche in einem Formular"
ms.assetid: 22cc9da6-b913-4e04-9554-dee443ac5c3a
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Definieren einer Windows&#160;Forms-Schaltfl&#228;che als &quot;Annehmen&quot;-Schaltfl&#228;che
Sie können in allen Windows Forms ein <xref:System.Windows.Forms.Button>\-Steuerelement als "Annehmen"\-Schaltfläche, die auch als Standardschaltfläche bezeichnet wird, definieren.  Sobald der Benutzer die EINGABETASTE drückt, wird auf die Standardschaltfläche geklickt. Dies geschieht unabhängig davon, welches Steuerelement im Formular den Fokus besitzt.  
  
> [!NOTE]
>  Dies gilt nicht, wenn es sich bei dem Steuerelement mit dem Fokus um eine weitere Schaltfläche handelt – in diesem Fall wird auf diese Schaltfläche geklickt – oder ein mehrzeiliges Textfeld bzw. ein benutzerdefiniertes Steuerelement, das die EINGABETASTE auffängt.  
  
### So definieren Sie die "Annehmen"\-Schaltfläche  
  
1.  Legen Sie das entsprechende <xref:System.Windows.Forms.Button>\-Steuerelement als <xref:System.Windows.Forms.Form.AcceptButton%2A>\-Eigenschaft des Formulars fest.  
  
    ```vb  
    Private Sub SetDefault(ByVal myDefaultBtn As Button)  
      Me.AcceptButton = myDefaultBtn   
    End Sub  
    ```  
  
    ```csharp  
    private void SetDefault(Button myDefaultBtn)  
    {  
       this.AcceptButton = myDefaultBtn;  
    }  
    ```  
  
    ```cpp  
    private:  
       void SetDefault(Button ^ myDefaultBtn)  
       {  
          this->AcceptButton = myDefaultBtn;  
       }  
    ```  
  
## Siehe auch  
 <xref:System.Windows.Forms.Form.AcceptButton%2A>   
 [Übersicht über das Button\-Steuerelement](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)   
 [Methoden zur Auswahl eines Button\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)   
 [Gewusst wie: Reagieren auf das Anklicken von Schaltflächen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)   
 [Gewusst wie: Definieren einer Windows Forms\-Schaltfläche als "Abbrechen"\-Schaltfläche](../../../../docs/framework/winforms/controls/how-to-designate-a-windows-forms-button-as-the-cancel-button.md)   
 [Button\-Steuerelement](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)