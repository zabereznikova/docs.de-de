---
title: "&#220;bersicht &#252;ber das CheckBox-Steuerelement (Windows&#160;Forms) | Microsoft Docs"
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
  - "CheckBox"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Gebundene Steuerelemente, Kontrollkästchen"
  - "Kontrollkästchen, Informationen über Kontrollkästchen"
  - "CheckBox-Steuerelement [Windows Forms], Informationen über das CheckBox-Steuerelement"
  - "Datenbindung, CheckBox-Steuerelement"
  - "Datengebundene Steuerelemente, Kontrollkästchen"
ms.assetid: 085a4e0b-9046-473f-b141-d0edddfb2ebb
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# &#220;bersicht &#252;ber das CheckBox-Steuerelement (Windows&#160;Forms)
Das <xref:System.Windows.Forms.CheckBox>\-Steuerelement in Windows Forms gibt an, ob eine bestimmte Bedingung erfüllt wird oder nicht.  Es wird im Allgemeinen verwendet, um dem Benutzer eine eindeutige Auswahl \(Yes\/No bzw. True\/False\) zu ermöglichen.  Sie können Kontrollkästchen\-Steuerelemente gruppieren, um mehrere Optionen anzuzeigen, aus denen der Benutzer eine oder mehrere auswählen kann.  
  
 Das Kontrollkästchen\-Steuerelement ist insofern mit dem Optionsfeld\-Steuerelement vergleichbar, als dass beide Steuerelemente für eine Benutzerauswahl stehen.  Der Unterschied besteht darin, dass jeweils nur ein Optionsfeld aus einer Gruppe aktiviert werden kann.  Beim Kontrollkästchen\-Steuerelement können dagegen beliebig viele Kontrollkästchen aktiviert werden.  
  
 Ein Kontrollkästchen kann durch einfache Datenbindung mit Elementen in einer Datenbank verbunden werden.  Mehrere Kontrollkästchen können mithilfe des <xref:System.Windows.Forms.GroupBox>\-Steuerelements gruppiert werden.  Dieses Steuerelement ist für die visuelle Darstellung und für die Gestaltung von Benutzeroberflächen hilfreich, da gruppierte Steuerelemente im Formular\-Designer zusammen bewegt werden können.  Weitere Informationen finden Sie unter [Datenbindung in Web Forms](../../../../docs/framework/winforms/windows-forms-data-binding.md) und [GroupBox\-Steuerelement](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md).  
  
 Das <xref:System.Windows.Forms.CheckBox>\-Steuerelement verfügt über zwei wichtige Eigenschaften, nämlich <xref:System.Windows.Forms.CheckBox.Checked%2A> und <xref:System.Windows.Forms.CheckBox.CheckState%2A>.  Die <xref:System.Windows.Forms.CheckBox.Checked%2A>\-Eigenschaft gibt `true` oder `false` zurück.  Die <xref:System.Windows.Forms.CheckBox.CheckState%2A>\-Eigenschaft gibt <xref:System.Windows.Forms.CheckState> oder <xref:System.Windows.Forms.CheckState> zurück. Wenn die <xref:System.Windows.Forms.CheckBox.ThreeState%2A>\-Eigenschaft auf `true` festgelegt ist, kann <xref:System.Windows.Forms.CheckBox.CheckState%2A> auch <xref:System.Windows.Forms.CheckState> zurückgeben.  Im unbestimmten Zustand wird das Kontrollkästchen abgeblendet angezeigt, was darauf hinweist, dass die Option nicht verfügbar ist.  
  
## Siehe auch  
 <xref:System.Windows.Forms.CheckBox>   
 [Gewusst wie: Festlegen von Optionen mit CheckBox\-Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-options-with-windows-forms-checkbox-controls.md)   
 [Gewusst wie: Reagieren auf das Klicken auf Kontrollkästchen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-checkbox-clicks.md)   
 [CheckBox\-Steuerelement](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)