---
title: "Gewusst wie: Ausrichten eines Steuerelements an den R&#228;ndern eines Formulars zur Entwurfszeit | Microsoft Docs"
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
  - "Benutzerdefinierte Steuerelemente [Windows Forms], Andocken mit dem Designer"
  - "Dock-Eigenschaft, Ausrichten von Steuerelementen (mit dem Designer)"
ms.assetid: 51f08998-5e3b-4330-be58-a4edd0eb60f4
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Ausrichten eines Steuerelements an den R&#228;ndern eines Formulars zur Entwurfszeit
Sie können Steuerelemente an Formularrändern ausrichten, indem Sie die <xref:System.Windows.Forms.Control.Dock%2A>\-Eigenschaft festlegen.  Diese Eigenschaft bestimmt die Position, an der sich das Steuerelement auf dem Formular befindet.  Die <xref:System.Windows.Forms.Control.Dock%2A>\-Eigenschaft kann auf folgende Werte festgelegt werden:  
  
|Einstellung|Auswirkung auf das Steuerelement|  
|-----------------|--------------------------------------|  
|<xref:System.Windows.Forms.DockStyle>|Dockt am unteren Rand des Formulars an.|  
|<xref:System.Windows.Forms.DockStyle>|Füllt sämtlichen verbleibenden Platz im Formular aus.|  
|<xref:System.Windows.Forms.DockStyle>|Dockt am linken Rand des Formulars an.|  
|<xref:System.Windows.Forms.DockStyle>|Dockt nirgendwo an und wird an der mit <xref:System.Windows.Forms.Control.Location%2A> angegebenen Position angezeigt.|  
|<xref:System.Windows.Forms.DockStyle>|Dockt am rechten Rand des Formulars an.|  
|<xref:System.Windows.Forms.DockStyle>|Dockt am oberen Rand des Formulars an.|  
  
 Diese Werte können auch im Code festgelegt werden.  Weitere Informationen finden Sie unter [Gewusst wie: Ausrichten eines Steuerelements an Formularrändern](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So legen Sie zur Entwurfszeit die Dock\-Eigenschaft für das Steuerelement fest  
  
1.  Wählen Sie das Steuerelement im Windows Forms\-Designer aus.  
  
2.  Klicken Sie im **Eigenschaftenfenster** auf das Dropdownfeld neben der <xref:System.Windows.Forms.Control.Dock%2A>\-Eigenschaft.  
  
     Eine grafische Schnittstelle mit sechs möglichen <xref:System.Windows.Forms.Control.Dock%2A>\-Einstellungen wird angezeigt.  
  
3.  Wählen Sie die gewünschte Einstellung aus.  
  
4.  Das Steuerelement dockt nun in der von der Einstellung angegebenen Weise an.  
  
## Siehe auch  
 <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=fullName>   
 [Gewusst wie: Ausrichten eines Steuerelements an Formularrändern](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms.md)   
 [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)   
 [Gewusst wie: Verankern von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-anchor-controls-on-windows-forms.md)   
 [Gewusst wie: Verankern und Andocken von untergeordneten Steuerelementen in einem TableLayoutPanel\-Steuerelement](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)   
 [Gewusst wie: Verankern und Andocken von untergeordneten Steuerelementen in einem FlowLayoutPanel\-Steuerelement](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)   
 [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)   
 [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)   
 [Entwickeln von Windows Forms\-Steuerelementen zur Entwurfszeit](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)