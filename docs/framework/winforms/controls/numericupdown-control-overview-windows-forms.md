---
title: "&#220;bersicht &#252;ber das NumericUpDown-Steuerelement (Windows&#160;Forms) | Microsoft Docs"
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
  - "NumericUpDown"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Numerisches Drehfeld-Steuerelement, Windows Forms"
  - "NumericUpDown-Steuerelement [Windows Forms], Informationen über das NumericUpDown-Steuerelement"
  - "Drehfeld-Steuerelement, Windows Forms"
ms.assetid: cff3cf30-4d46-4381-87df-37bfe83c71c5
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# &#220;bersicht &#252;ber das NumericUpDown-Steuerelement (Windows&#160;Forms)
Das <xref:System.Windows.Forms.NumericUpDown>\-Steuerelement sieht wie eine Kombination aus einem Textfeld und einem Paar Pfeilen aus, auf die der Benutzer klicken kann, um einen Wert anzupassen.  Das Steuerelement zeigt einen einzelnen numerischen Wert aus einer Liste mit festen numerischen Werten an und legt ihn fest.  Die Zahl kann durch Klicken auf den Nach\-oben\- bzw. Nach\-unten\-Pfeil oder durch Drücken der NACH\-OBEN\- bzw. NACH\-UNTEN\-TASTE und Eingabe einer Zahl in das Textfeld des Steuerelements vergrößert oder verkleinert werden.  Durch Drücken der NACH\-OBEN\-TASTE wird die Zahl in Richtung Maximalwert geändert; durch Drücken der NACH\-UNTEN\-TASTE wird die Zahl in Richtung Minimum geändert.  
  
 Aufgrund der vielseitigen Funktionalität bietet sich dieses Steuerelement beispielsweise zur Erstellung eines Lautstärkereglers für die Musikwiedergabe an.  Das <xref:System.Windows.Forms.NumericUpDown>\-Steuerelement wird in vielen Anwendungen der Windows\-Systemsteuerung verwendet.  
  
## Wichtige Eigenschaften und Methoden  
 Die im Textfeld des Steuerelements angezeigten Zahlen können diverse Formate aufweisen, z. B. das hexadezimale Format.  Weitere Informationen finden Sie unter [Gewusst wie: Festlegen des Formats für das NumericUpDown\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-format-for-the-windows-forms-numericupdown-control.md).  Die wichtigsten Eigenschaften des Steuerelements sind <xref:System.Windows.Forms.NumericUpDown.Value%2A>, <xref:System.Windows.Forms.NumericUpDown.Maximum%2A> \(Standardwert 100\), <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> \(Standardwert 0\) und <xref:System.Windows.Forms.NumericUpDown.Increment%2A> \(Standardwert 1\).  Die <xref:System.Windows.Forms.NumericUpDown.Value%2A>\-Eigenschaft legt die aktuelle Zahl fest, die im Steuerelement ausgewählt ist.  Die <xref:System.Windows.Forms.NumericUpDown.Increment%2A>\-Eigenschaft legt fest, in welchem Maße die Zahl angepasst wird, wenn der Benutzer auf den Nach\-oben\- bzw. Nach\-unten\-Pfeil klickt.  Wenn der Fokus nicht mehr auf dem Steuerelement liegt, wird die Eingabe anhand des minimalen und maximalen numerischen Werts überprüft.  Sie können die Geschwindigkeit, mit der das Steuerelement die Zahlen durchläuft, wenn der Benutzer den Nach\-oben\- bzw. Nach\-unten\-Pfeil dauerhaft drückt, mithilfe der <xref:System.Windows.Forms.NumericUpDown.Accelerations%2A>\-Eigenschaft erhöhen.  Die wichtigsten Methoden des Steuerelements sind <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> und <xref:System.Windows.Forms.NumericUpDown.DownButton%2A>.  
  
## Siehe auch  
 <xref:System.Windows.Forms.NumericUpDown>   
 [NumericUpDown\-Steuerelement](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md)   
 [Gewusst wie: Festlegen des Formats für das NumericUpDown\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-format-for-the-windows-forms-numericupdown-control.md)   
 [TextBox\-Steuerelement](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)