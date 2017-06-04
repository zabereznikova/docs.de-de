---
title: "&#220;bersicht &#252;ber das Button-Steuerelement (Windows&#160;Forms) | Microsoft Docs"
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
  - "Button"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Button-Steuerelement [Windows Forms], Informationen über das Button-Steuerelement"
  - "Schaltflächen, Informationen über Schaltflächen"
ms.assetid: 255b291b-51a9-4a92-a1a4-2400cd82443f
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# &#220;bersicht &#252;ber das Button-Steuerelement (Windows&#160;Forms)
Der Benutzer hat die Möglichkeit, auf das <xref:System.Windows.Forms.Button>\-Steuerelement in Windows Forms zu klicken, um Aktionen auszuführen.  Beim Klicken entsteht der Eindruck, als würde eine Taste gedrückt und losgelassen werden.  Beim Klicken auf eine Schaltfläche wird der <xref:System.Windows.Forms.Control.Click>\-Ereignishandler aktiviert.  Um eine beliebige Aktion auszuführen, fügen Sie den zugehörigen Code in den <xref:System.Windows.Forms.Control.Click>\-Ereignishandler ein.  
  
 Der auf der Schaltfläche angezeigte Text ist in der <xref:System.Windows.Forms.Control.Text%2A>\-Eigenschaft enthalten.  Wenn der Text zu lang für die Schaltfläche ist, wird er in die nächste Zeile umbrochen.  Es kann jedoch auch vorkommen, dass Text abgeschnitten wird, wenn die Höhe des Steuerelements nicht für den gesamten Text ausreicht.  Weitere Informationen finden Sie unter [Gewusst wie: Festlegen des durch ein Windows Forms\-Steuerelement angezeigten Textes](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md).  Die <xref:System.Windows.Forms.Control.Text%2A>\-Eigenschaft kann eine Zugriffstaste enthalten. Der Benutzer kann somit auf das Steuerelement "klicken", indem er die ALT\-TASTE zusammen mit der Zugriffstaste drückt.  Ausführlichere Informationen finden Sie unter [Gewusst wie: Erstellen von Zugriffstasten für Windows Forms\-Steuerelemente](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).  Die Darstellung des Textes wird durch die <xref:System.Windows.Forms.Control.Font%2A>\-Eigenschaft und <xref:System.Windows.Forms.ButtonBase.TextAlign%2A>\-Eigenschaft gesteuert.  
  
 Das <xref:System.Windows.Forms.Button>\-Steuerelement kann zudem Bilder mit der <xref:System.Windows.Forms.ButtonBase.Image%2A>\-Eigenschaft und <xref:System.Windows.Forms.ButtonBase.ImageList%2A>\-Eigenschaft anzeigen.  Weitere Informationen finden Sie unter [Gewusst wie: Festlegen des durch ein Windows Forms\-Steuerelement angezeigten Bildes](../../../../docs/framework/winforms/controls/how-to-set-the-image-displayed-by-a-windows-forms-control.md).  
  
## Siehe auch  
 <xref:System.Windows.Forms.Button>   
 [Gewusst wie: Reagieren auf das Anklicken von Schaltflächen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)   
 [Methoden zur Auswahl eines Button\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)   
 [Gewusst wie: Definieren einer Windows Forms\-Schaltfläche als "Annehmen"\-Schaltfläche mithilfe des Designers](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-accept-button-using-the-designer.md)   
 [Gewusst wie: Definieren einer Windows Forms\-Schaltfläche als "Abbrechen"\-Schaltfläche mithilfe des Designers](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-cancel-button-using-the-designer.md)   
 [Button\-Steuerelement](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)