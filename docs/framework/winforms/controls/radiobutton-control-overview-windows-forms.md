---
title: "&#220;bersicht &#252;ber das RadioButton-Steuerelement (Windows&#160;Forms) | Microsoft Docs"
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
  - "RadioButton"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Optionsfelder, Informationen über Optionsfelder"
  - "Optionsfelder, Feststellen des Zustands"
  - "RadioButton-Steuerelement [Windows Forms], Informationen über das RadioButton-Steuerelement"
  - "RadioButton-Steuerelement [Windows Forms], Feststellen des Zustands"
ms.assetid: cd11f0c2-d098-4022-adf9-1455bc166a13
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# &#220;bersicht &#252;ber das RadioButton-Steuerelement (Windows&#160;Forms)
<xref:System.Windows.Forms.RadioButton>\-Steuerelemente in Windows Forms bieten dem Benutzer zwei oder mehr Optionen, die sich gegenseitig ausschließen.  Obwohl Optionsfelder und Kontrollkästchen eine relativ ähnliche Funktionsweise besitzen, weisen Sie doch einen wichtigen Unterschied auf: Sobald der Benutzer ein Optionsfeld aktiviert, können in derselben Gruppe keine zusätzlichen Optionsfelder aktiviert werden.  Bei Kontrollkästchen können im Gegensatz dazu beliebig viele aktiviert werden.  Eine Optionsfeldgruppe stellt dem Benutzer eine Reihe von Optionen zur Verfügung, von denen jeweils nur eine aktiviert werden kann.  
  
## Verwenden des Steuerelements  
 Beim Klicken auf ein <xref:System.Windows.Forms.RadioButton>\-Steuerelement wird dessen <xref:System.Windows.Forms.RadioButton.Checked%2A>\-Eigenschaft auf `true` festgelegt, und der <xref:System.Windows.Forms.Control.Click>\-Ereignishandler wird aufgerufen.  Sobald sich der Wert der <xref:System.Windows.Forms.RadioButton.Checked%2A>\-Eigenschaft ändert, wird das <xref:System.Windows.Forms.RadioButton.CheckedChanged>\-Ereignis ausgelöst.  Wenn für die <xref:System.Windows.Forms.RadioButton.AutoCheck%2A>\-Eigenschaft `true` festgelegt ist \(der Standardwert\) und das Optionsfeld aktiviert wird, werden alle übrigen Optionsfelder in der Gruppe automatisch deaktiviert.  Für diese Eigenschaft wird in der Regel nur `false` festgelegt, wenn eine Validierung mittels Code durchgeführt wird, um sicherzustellen, dass das aktivierte Optionsfeld eine zulässige Option darstellt.  Der Text innerhalb des Steuerelements wird mithilfe der <xref:System.Windows.Forms.Control.Text%2A>\-Eigenschaft festgelegt, die zusätzlich Tastenkombinationen für Zugriffstasten enthalten kann.  Über eine Zugriffstaste kann der Benutzer auf das Steuerelement "klicken", indem er die ALT\-TASTE zusammen mit der Tastenkombination drückt.  Weitere Informationen finden Sie unter [Gewusst wie: Erstellen von Zugriffstasten für Windows Forms\-Steuerelemente](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md) und [Gewusst wie: Festlegen des durch ein Windows Forms\-Steuerelement angezeigten Textes](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md).  
  
 Wenn die <xref:System.Windows.Forms.RadioButton.Appearance%2A>\-Eigenschaft auf <xref:System.Windows.Forms.Appearance> festgelegt ist, kann das <xref:System.Windows.Forms.RadioButton>\-Steuerelement wie eine Befehlsschaltfläche angezeigt werden, die, wenn sie ausgewählt wird, gedrückt aussieht.  Optionsfelder können mithilfe der <xref:System.Windows.Forms.ButtonBase.Image%2A>\-Eigenschaft und <xref:System.Windows.Forms.ButtonBase.ImageList%2A>\-Eigenschaft auch Bilder anzeigen.  Weitere Informationen finden Sie unter [Gewusst wie: Festlegen des durch ein Windows Forms\-Steuerelement angezeigten Bildes](../../../../docs/framework/winforms/controls/how-to-set-the-image-displayed-by-a-windows-forms-control.md).  
  
## Siehe auch  
 <xref:System.Windows.Forms.RadioButton>   
 [Übersicht über das Panel\-Steuerelement](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)   
 [Übersicht über das GroupBox\-Steuerelement](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md)   
 [Übersicht über das CheckBox\-Steuerelement](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)   
 [Gewusst wie: Erstellen von Zugriffstasten für Windows Forms\-Steuerelemente](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)   
 [Gewusst wie: Festlegen des durch ein Windows Forms\-Steuerelement angezeigten Textes](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)   
 [Gewusst wie: Gruppieren von RadioButton\-Steuerelementen in Windows Forms für die Verwendung als Set](../../../../docs/framework/winforms/controls/how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md)   
 [RadioButton\-Steuerelement](../../../../docs/framework/winforms/controls/radiobutton-control-windows-forms.md)