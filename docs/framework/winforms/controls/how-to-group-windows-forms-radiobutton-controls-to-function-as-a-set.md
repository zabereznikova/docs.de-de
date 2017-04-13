---
title: "Gewusst wie: Gruppieren von RadioButton-Steuerelementen in Windows&#160;Forms f&#252;r die Verwendung als Set | Microsoft Docs"
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
  - "Steuerelemente [Windows Forms], Gruppieren"
  - "Optionsfelder, Gruppieren"
  - "RadioButton-Steuerelement [Windows Forms], Gruppieren"
  - "Windows Forms-Steuerelemente, Gruppieren"
ms.assetid: 58f8fe34-50b7-49d8-a2be-c271be3c6b32
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Gruppieren von RadioButton-Steuerelementen in Windows&#160;Forms f&#252;r die Verwendung als Set
<xref:System.Windows.Forms.RadioButton>\-Steuerelemente in Windows Forms sollen dem Benutzer die Auswahl aus zwei oder mehr Einstellungen ermöglichen. Dabei kann einer Prozedur oder einem Objekt jeweils nur eine Einstellung zugewiesen werden.  Bei einer Bestellung lässt sich durch eine <xref:System.Windows.Forms.RadioButton>\-Steuerelementgruppe beispielsweise eine Auswahl von Transportunternehmen darstellen, von denen nur ein Unternehmen ausgewählt werden kann.  Es kann also nur ein <xref:System.Windows.Forms.RadioButton>\-Steuerelement aktiviert werden, selbst wenn alle Elemente derselben Funktionsgruppe angehören.  
  
 Um Optionsfelder zu gruppieren, müssen diese innerhalb eines Containers angelegt werden, z. B. in einem <xref:System.Windows.Forms.Panel>\-Steuerelement, einem <xref:System.Windows.Forms.GroupBox>\-Steuerelement oder einem Formular.  Alle Optionsfelder, die einem Formular direkt hinzugefügt werden, bilden eine Gruppe.  Um separate Gruppen hinzuzufügen, platzieren Sie diese innerhalb von Auswahlbereichen oder Gruppenfeldern.  Weitere Informationen zu Auswahlbereichen und Gruppenfeldern finden Sie unter [Übersicht über das Panel\-Steuerelement](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md) oder [Übersicht über das GroupBox\-Steuerelement](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md).  
  
### So gruppieren Sie RadioButton\-Steuerelemente als Set, das unabhängig von anderen Sets funktioniert  
  
1.  Ziehen Sie ein <xref:System.Windows.Forms.GroupBox>\-Steuerelement oder ein <xref:System.Windows.Forms.Panel>\-Steuerelement von der Registerkarte **Windows Forms** der **Toolbox** in das Formular.  
  
2.  Zeichnen Sie die gewünschten <xref:System.Windows.Forms.RadioButton>\-Steuerelemente im <xref:System.Windows.Forms.GroupBox>\-Steuerelement oder im <xref:System.Windows.Forms.Panel>\-Steuerelement.  
  
## Siehe auch  
 <xref:System.Windows.Forms.RadioButton>   
 [Übersicht über das RadioButton\-Steuerelement](../../../../docs/framework/winforms/controls/radiobutton-control-overview-windows-forms.md)   
 [Übersicht über das Panel\-Steuerelement](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)   
 [Übersicht über das GroupBox\-Steuerelement](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md)   
 [Übersicht über das CheckBox\-Steuerelement](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)   
 [RadioButton\-Steuerelement](../../../../docs/framework/winforms/controls/radiobutton-control-windows-forms.md)