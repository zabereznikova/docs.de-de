---
title: "Gewusst wie: Definieren einer Windows&#160;Forms-Schaltfl&#228;che als &quot;Abbrechen&quot;-Schaltfl&#228;che | Microsoft Docs"
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
  - "Button-Steuerelement [Windows Forms], Definieren als Schaltfläche zum Abbrechen"
  - "Schaltflächen, Abbrechen (Schaltflächen)"
ms.assetid: 252f0834-e54b-44d9-96f7-ee5f50e94f2c
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Definieren einer Windows&#160;Forms-Schaltfl&#228;che als &quot;Abbrechen&quot;-Schaltfl&#228;che
Sie können in beliebigen Windows Forms ein <xref:System.Windows.Forms.Button>\-Steuerelement als "Abbrechen"\-Schaltfläche definieren.  Sobald der Benutzer die ESC\-TASTE drückt, wird auf die "Abbrechen"\-Schaltfläche geklickt. Dies geschieht unabhängig davon, auf welchem anderen Steuerelement im Formular sich der Fokus befindet.  Eine solche Schaltfläche ermöglicht es dem Benutzer normalerweise, eine Operation schnell zu beenden, ohne eine Aktion auszuführen.  
  
### So definieren Sie die "Abbrechen"\-Schaltfläche  
  
1.  Legen Sie das entsprechende <xref:System.Windows.Forms.Button>\-Steuerelement als <xref:System.Windows.Forms.Form.CancelButton%2A>\-Eigenschaft des Formulars fest.  
  
    ```vb  
    Private Sub SetCancelButton(ByVal myCancelBtn As Button)  
       Me.CancelButton = myCancelBtn  
    End Sub  
    ```  
  
    ```csharp  
    private void SetCancelButton(Button myCancelBtn)  
    {  
       this.CancelButton = myCancelBtn;  
    }  
    ```  
  
    ```cpp  
    private:  
       void SetCancelButton(Button ^ myCancelBtn)  
       {  
          this->CancelButton = myCancelBtn;  
       }  
    ```  
  
## Siehe auch  
 <xref:System.Windows.Forms.Form.CancelButton%2A>   
 [Übersicht über das Button\-Steuerelement](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)   
 [Methoden zur Auswahl eines Button\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)   
 [Gewusst wie: Reagieren auf das Anklicken von Schaltflächen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)   
 [Gewusst wie: Definieren einer Windows Forms\-Schaltfläche als "Annehmen"\-Schaltfläche](../../../../docs/framework/winforms/controls/how-to-designate-a-windows-forms-button-as-the-accept-button.md)   
 [Button\-Steuerelement](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)