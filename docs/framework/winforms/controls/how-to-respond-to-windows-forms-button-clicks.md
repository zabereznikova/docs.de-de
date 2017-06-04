---
title: "Gewusst wie: Reagieren auf das Anklicken von Schaltfl&#228;chen in Windows Forms | Microsoft Docs"
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
  - "Button-Steuerelement [Windows Forms], Klickreaktion"
  - "Schaltflächen, Reagieren auf Click-Ereignisse"
  - "Click-Ereignis, Button-Steuerelement"
  - "Click-Ereignis, Reagieren auf"
  - "Doppelklicken"
  - "Ereignisse [Windows Forms], Click-Ereignisse"
  - "Beispiele [Windows Forms], Steuerelemente"
  - "MouseDown-Ereignis"
ms.assetid: 7a4951bd-369c-4662-b246-28ad83eda484
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Reagieren auf das Anklicken von Schaltfl&#228;chen in Windows Forms
Die Hauptfunktion des <xref:System.Windows.Forms.Button>\-Steuerelements in Windows Forms besteht darin, Code auszuführen, sobald auf die Schaltfläche geklickt wird.  
  
 Durch Klicken auf ein <xref:System.Windows.Forms.Button>\-Steuerelement werden zudem eine Reihe weiterer Ereignisse wie <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown> und <xref:System.Windows.Forms.Control.MouseUp> generiert.  Wenn Sie beabsichtigen, Ereignishandler für diese verwandten Ereignisse anzuhängen, müssen Sie sicherstellen, dass deren Aktionen nicht miteinander in Konflikt stehen.  Beispiel: Durch Klicken auf die Schaltfläche werden Informationen gelöscht, die der Benutzer in ein Textfeld eingegeben hat. In diesem Fall sollte – wenn der Mauszeiger über die Schaltfläche bewegt wird – keine QuickInfo angezeigt werden, da das Feld keine Informationen mehr enthält.  
  
 Wenn der Benutzer auf das <xref:System.Windows.Forms.Button>\-Steuerelement doppelklickt, wird jedes Klicken einzeln verarbeitet, das Doppelklickereignis wird also vom Steuerelement nicht unterstützt.  
  
### So reagieren Sie auf das Klicken auf eine Schaltfläche  
  
-   Schreiben Sie im`Click` <xref:System.EventHandler> der Schaltfläche den auszuführenden Code.  `Button1_Click` muss an das Steuerelement gebunden sein.  Weitere Informationen hierzu finden Sie unter [Gewusst wie: Erstellen von Ereignishandlern für Windows Forms zur Laufzeit](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       MessageBox.Show("Button1 was clicked")  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       MessageBox.Show("button1 was clicked");  
    }  
    ```  
  
    ```cpp#  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          MessageBox::Show("button1 was clicked");  
       }  
    ```  
  
## Siehe auch  
 [Übersicht über das Button\-Steuerelement](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)   
 [Methoden zur Auswahl eines Button\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)   
 [Button\-Steuerelement](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)