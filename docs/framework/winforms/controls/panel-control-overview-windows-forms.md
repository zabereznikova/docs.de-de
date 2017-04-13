---
title: "&#220;bersicht &#252;ber das Panel-Steuerelement (Windows&#160;Forms) | Microsoft Docs"
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
  - "Panel"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Gruppieren von Steuerelementen, Panel-Steuerelement"
  - "Panel-Steuerelement [Windows Forms], Informationen über das Panel-Steuerelement"
ms.assetid: b6b83636-2c39-4dad-89d6-f0fa41049a74
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# &#220;bersicht &#252;ber das Panel-Steuerelement (Windows&#160;Forms)
<xref:System.Windows.Forms.Panel>\-Steuerelemente in Windows Forms werden dazu verwendet, andere Steuerelemente zu identifizierbaren Gruppen zusammenzufassen.  Normalerweise werden Auswahlbereiche verwendet, um ein Formular nach Funktionsbereichen zu unterteilen.  Angenommen, in einem Bestellformular sind Zustelloptionen, beispielsweise der zu verwendende Overnight\-Zustelldienst, definiert.  Wenn alle Optionen in einem Auswahlbereich zusammengefasst sind, erhält der Benutzer eine logische visuelle Orientierungshilfe.  Zur Entwurfszeit lassen sich alle Steuerelemente leicht verschieben. Beim Verschieben des <xref:System.Windows.Forms.Panel>\-Steuerelements werden auch alle darin enthaltenen Steuerelemente verschoben.  Der Zugriff auf die in einem Auswahlbereich gruppierten Steuerelemente erfolgt über seine <xref:System.Windows.Forms.Control.Controls%2A>\-Eigenschaft.  Diese Eigenschaft gibt eine Auflistung von <xref:System.Windows.Forms.Control>\-Instanzen zurück. Ein auf diese Weise abgerufenes Steuerelement muss daher normalerweise in seinen spezifischen Typ umgewandelt werden.  
  
## Panel im Vergleich zu GroupBox  
 Das <xref:System.Windows.Forms.Panel>\-Steuerelement ist grundsätzlich mit dem <xref:System.Windows.Forms.GroupBox>\-Steuerelement vergleichbar. Allerdings kann nur das <xref:System.Windows.Forms.Panel>\-Steuerelement mit Bildlaufleisten und nur das <xref:System.Windows.Forms.GroupBox>\-Steuerelement mit einer Beschriftung versehen werden.  
  
## Haupteigenschaften  
 Um Schiebeleisten anzuzeigen, legen Sie für die <xref:System.Windows.Forms.ScrollableControl.AutoScroll%2A>\-Eigenschaft `true` fest.  Sie können die Darstellung des Auswahlbereichs auch anpassen, indem Sie die Eigenschaften <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A> und <xref:System.Windows.Forms.Panel.BorderStyle%2A> festlegen.  Weitere Informationen über die Eigenschaften <xref:System.Windows.Forms.Control.BackColor%2A> und <xref:System.Windows.Forms.Control.BackgroundImage%2A> finden Sie unter [Gewusst wie: Festlegen des Hintergrunds eines Bereichs](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel.md).  Durch die <xref:System.Windows.Forms.Panel.BorderStyle%2A>\-Eigenschaft wird festgelegt, ob der Auswahlbereich von einer einfachen Linie \(<xref:System.Windows.Forms.BorderStyle>\) oder einer schattierten Linie \(<xref:System.Windows.Forms.BorderStyle>\) umgeben ist oder überhaupt keine sichtbare Rahmenlinie \(<xref:System.Windows.Forms.BorderStyle>\) aufweist.  
  
## Siehe auch  
 <xref:System.Windows.Forms.Panel>   
 [GroupBox\-Steuerelement](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md)   
 [Gewusst wie: Gruppieren von Steuerelementen mit dem Windows Forms\-Bereichssteuerelement im Designer](../../../../docs/framework/winforms/controls/group-controls-with-wf-panel-control-using-the-designer.md)   
 [Gewusst wie: Festlegen des Hintergrunds eines Windows Forms\-Bereichs mithilfe des Designers](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel-using-the-designer.md)