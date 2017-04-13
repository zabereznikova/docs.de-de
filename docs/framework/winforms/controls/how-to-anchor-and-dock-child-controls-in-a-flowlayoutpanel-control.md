---
title: "Gewusst wie: Verankern und Andocken von untergeordneten Steuerelementen in einem FlowLayoutPanel-Steuerelement | Microsoft Docs"
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
  - "Untergeordnete Steuerelemente, Verankern und Andocken"
  - "Steuerelemente [Windows Forms], Untergeordnet"
  - "FlowLayoutPanel-Steuerelement [Windows Forms], Untergeordnete Steuerelemente"
  - "Layout [Windows Forms], Untergeordnete Steuerelemente"
ms.assetid: a2bcdfca-9b63-45e6-9c0e-3411015cba98
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Verankern und Andocken von untergeordneten Steuerelementen in einem FlowLayoutPanel-Steuerelement
Das <xref:System.Windows.Forms.FlowLayoutPanel>\-Steuerelement unterstützt die <xref:System.Windows.Forms.Control.Anchor%2A>\- und die <xref:System.Windows.Forms.Control.Dock%2A>\-Eigenschaft in seinen untergeordneten Steuerelementen.  
  
### So verankern Sie untergeordnete Steuerelemente in einem FlowLayoutPanel\-Steuerelement und docken sie an  
  
1.  Erstellen Sie ein <xref:System.Windows.Forms.FlowLayoutPanel>\-Steuerelement auf dem Formular.  
  
2.  Legen Sie die <xref:System.Windows.Forms.Control.Width%2A>\-Eigenschaft des <xref:System.Windows.Forms.FlowLayoutPanel>\-Steuerelements auf 300 fest, und legen Sie seine <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>\-Eigenschaft auf <xref:System.Windows.Forms.FlowDirection> fest.  
  
3.  Erstellen Sie zwei <xref:System.Windows.Forms.Button>\-Steuerelemente, und platzieren Sie diese im <xref:System.Windows.Forms.FlowLayoutPanel>\-Steuerelement.  
  
4.  Legen Sie die <xref:System.Windows.Forms.Control.Width%2A>\-Eigenschaft der ersten Schaltfläche auf 200 fest.  
  
5.  Legen Sie die <xref:System.Windows.Forms.Control.Dock%2A>\-Eigenschaft der zweiten Schaltfläche auf <xref:System.Windows.Forms.DockStyle> fest.  
  
    > [!NOTE]
    >  Für die zweite Schaltfläche wird dieselbe Breite angenommen wie für die erste Schaltfläche.  Die Schaltfläche erstreckt sich nicht über die Breite des <xref:System.Windows.Forms.FlowLayoutPanel>\-Steuerelements.  
  
6.  Legen Sie die <xref:System.Windows.Forms.Control.Dock%2A>\-Eigenschaft der zweiten Schaltfläche auf `None` fest.  Dadurch wird die Schaltfläche auf ihre ursprüngliche Breite zurückgesetzt.  
  
7.  Legen Sie die <xref:System.Windows.Forms.Control.Anchor%2A>\-Eigenschaft der zweiten Schaltfläche auf `Left, Right` fest.  
  
    > [!IMPORTANT]
    >  Für die zweite Schaltfläche wird dieselbe Breite angenommen wie für die erste Schaltfläche.  Die Schaltfläche erstreckt sich nicht über die Breite des <xref:System.Windows.Forms.FlowLayoutPanel>\-Steuerelements.  Die allgemeine Regel zum Verankern und Andocken im <xref:System.Windows.Forms.FlowLayoutPanel>\-Steuerelement lautet wie folgt: Bei vertikalen Flussrichtungen berechnet das <xref:System.Windows.Forms.FlowLayoutPanel>\-Steuerelement die Breite einer impliziten Spalte anhand des breitesten untergeordneten Steuerelements in der Spalte.  Alle anderen Steuerelemente in dieser Spalte mit einer <xref:System.Windows.Forms.Control.Anchor%2A>\- oder einer <xref:System.Windows.Forms.Control.Dock%2A>\-Eigenschaft werden so ausgerichtet oder gestreckt, dass sie diese implizite Spalte ausfüllen.  Bei horizontalen Flussrichtungen ist das Verhalten ähnlich.  Das <xref:System.Windows.Forms.FlowLayoutPanel>\-Steuerelement berechnet die Höhe einer impliziten Zeile anhand des höchsten untergeordneten Steuerelements in der Zeile. Alle angedockten oder verankerten untergeordneten Steuerelemente in dieser Zeile werden dann so ausgerichtet oder vergrößert, dass sie diese implizite Zeile ausfüllen.  
  
## Beispiel  
 Die folgende Abbildung zeigt vier Schaltflächen, die relativ zur blauen Schaltfläche in einem <xref:System.Windows.Forms.FlowLayoutPanel> verankert und angedockt sind.  <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> ist <xref:System.Windows.Forms.FlowDirection>.  
  
 ![FlowLayoutPanel&#45;Verankerung](../../../../docs/framework/winforms/controls/media/net-flpanchorexp.png "NET\_FLPanchorExp")  
  
 Die folgende Abbildung zeigt vier Schaltflächen, die relativ zur blauen Schaltfläche in einem <xref:System.Windows.Forms.FlowLayoutPanel> verankert und angedockt sind.  <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> ist <xref:System.Windows.Forms.FlowDirection>.  
  
 ![FlowLayoutPanel&#45;Verankerung](../../../../docs/framework/winforms/controls/media/vs-flpanchor2.png "VS\_FLPanchor2")  
  
 Das folgende Codebeispiel veranschaulicht verschiedene <xref:System.Windows.Forms.Control.Anchor%2A>\-Eigenschaftswerte für ein <xref:System.Windows.Forms.Button>\-Steuerelement in einem <xref:System.Windows.Forms.FlowLayoutPanel>\-Steuerelement.  
  
 [!code-csharp[System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm/CS/FlpAnchorExampleForm.cs#1)]
 [!code-vb[System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm/VB/FlpAnchorExampleForm.vb#1)]  
  
## Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System", "System.Data", "System.Drawing" und "System.Windows.Forms".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] oder [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] finden Sie unter [Erstellen von der Befehlszeile aus](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) oder [Erstellen über die Befehlszeile mit csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.  Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms\-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Siehe auch  
 <xref:System.Windows.Forms.FlowLayoutPanel>   
 [Übersicht über das FlowLayoutPanel\-Steuerelement](../../../../docs/framework/winforms/controls/flowlayoutpanel-control-overview.md)