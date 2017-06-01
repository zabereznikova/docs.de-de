---
title: "Gewusst wie: Definieren einer Windows&#160;Forms-Schaltfl&#228;che als &quot;Abbrechen&quot;-Schaltfl&#228;che mithilfe des Designers | Microsoft Docs"
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
ms.assetid: 30e77d9c-d565-4ab5-a84a-62c043af8822
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Definieren einer Windows&#160;Forms-Schaltfl&#228;che als &quot;Abbrechen&quot;-Schaltfl&#228;che mithilfe des Designers
Sie können in beliebigen Windows Forms ein <xref:System.Windows.Forms.Button>\-Steuerelement als "Abbrechen"\-Schaltfläche definieren.  Sobald der Benutzer die ESC\-TASTE drückt, wird auf die "Abbrechen"\-Schaltfläche geklickt. Dies geschieht unabhängig davon, auf welchem anderen Steuerelement im Formular sich der Fokus befindet.  Eine solche Schaltfläche ermöglicht es dem Benutzer normalerweise, eine Operation schnell zu beenden, ohne eine Aktion auszuführen.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So definieren Sie die "Abbrechen"\-Schaltfläche  
  
1.  Wählen Sie das Formular aus, in dem sich die Schaltfläche befindet.  
  
2.  Legen Sie im **Eigenschaftenfenster** die <xref:System.Windows.Forms.Form.CancelButton%2A>\-Eigenschaft des Formulars auf den Namen des <xref:System.Windows.Forms.Button>\-Steuerelements fest.  
  
## Siehe auch  
 <xref:System.Windows.Forms.Form.CancelButton%2A>   
 [Übersicht über das Button\-Steuerelement](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)   
 [Methoden zur Auswahl eines Button\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)   
 [Gewusst wie: Reagieren auf das Anklicken von Schaltflächen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)   
 [Gewusst wie: Definieren einer Windows Forms\-Schaltfläche als "Annehmen"\-Schaltfläche mithilfe des Designers](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-accept-button-using-the-designer.md)   
 [Button\-Steuerelement](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)