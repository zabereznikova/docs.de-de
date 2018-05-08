---
title: 'Gewusst wie: Verankern und Andocken von untergeordneten Steuerelementen in einem FlowLayoutPanel-Steuerelement'
ms.date: 03/30/2017
helpviewer_keywords:
- layout [Windows Forms], child controls
- FlowLayoutPanel control [Windows Forms], child controls
- controls [Windows Forms], child
- child controls [Windows Forms], anchoring and docking
ms.assetid: a2bcdfca-9b63-45e6-9c0e-3411015cba98
ms.openlocfilehash: 2c8cb2d89ffaedde59d54edf6cae1f8c47548680
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control"></a>Gewusst wie: Verankern und Andocken von untergeordneten Steuerelementen in einem FlowLayoutPanel-Steuerelement
Das <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelement unterstützt die <xref:System.Windows.Forms.Control.Anchor%2A>- und die <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft in seinen untergeordneten Steuerelementen.  
  
### <a name="to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control"></a>So verankern Sie untergeordnete Steuerelemente in einem FlowLayoutPanel-Steuerelement und docken sie an  
  
1.  Erstellen Sie ein <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelement auf dem Formular.  
  
2.  Festlegen der <xref:System.Windows.Forms.Control.Width%2A> von der <xref:System.Windows.Forms.FlowLayoutPanel> die Steuerung an **300**, und legen Sie seine <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> auf <xref:System.Windows.Forms.FlowDirection.TopDown>.  
  
3.  Erstellen Sie zwei <xref:System.Windows.Forms.Button>-Steuerelemente, und platzieren Sie diese im <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelement.  
  
4.  Legen Sie die <xref:System.Windows.Forms.Control.Width%2A> der ersten Schaltfläche auf **200**.  
  
5.  Legen Sie die <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft der zweiten Schaltfläche auf <xref:System.Windows.Forms.DockStyle.Fill> fest.  
  
    > [!NOTE]
    >  Für die zweite Schaltfläche wird dieselbe Breite angenommen wie für die erste Schaltfläche. Die Schaltfläche erstreckt sich nicht über die Breite des <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelements.  
  
6.  Legen Sie die <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft der zweiten Schaltfläche auf `None` fest. Dadurch wird die Schaltfläche auf ihre ursprüngliche Breite zurückgesetzt.  
  
7.  Legen Sie die <xref:System.Windows.Forms.Control.Anchor%2A>-Eigenschaft der zweiten Schaltfläche auf `Left, Right` fest.  
  
    > [!IMPORTANT]
    >  Für die zweite Schaltfläche wird dieselbe Breite angenommen wie für die erste Schaltfläche. Die Schaltfläche erstreckt sich nicht über die Breite des <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelements. Die allgemeine Regel zum Verankern und Andocken im <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelement lautet wie folgt: Bei vertikalen Flussrichtungen berechnet das <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelement die Breite einer impliziten Spalte anhand des breitesten untergeordneten Steuerelements in der Spalte. Alle anderen Steuerelemente in dieser Spalte mit einer <xref:System.Windows.Forms.Control.Anchor%2A>- oder einer <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft werden so ausgerichtet oder gestreckt, dass sie diese implizite Spalte ausfüllen. Bei horizontalen Flussrichtungen ist das Verhalten ähnlich. Das <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelement berechnet die Höhe einer impliziten Zeile anhand des höchsten untergeordneten Steuerelements in der Zeile. Alle angedockten oder verankerten untergeordneten Steuerelemente in dieser Zeile werden dann so ausgerichtet oder vergrößert, dass sie diese implizite Zeile ausfüllen.  
  
## <a name="example"></a>Beispiel  
 Die folgende Abbildung zeigt vier Schaltflächen, die relativ zur blauen Schaltfläche in einem <xref:System.Windows.Forms.FlowLayoutPanel> verankert und angedockt sind. <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> ist <xref:System.Windows.Forms.FlowDirection.LeftToRight>.  
  
 ![FlowLayoutPanel-Verankerung](../../../../docs/framework/winforms/controls/media/net-flpanchorexp.gif "NET_FLPanchorExp")  
  
 Die folgende Abbildung zeigt vier Schaltflächen, die relativ zur blauen Schaltfläche in einem <xref:System.Windows.Forms.FlowLayoutPanel> verankert und angedockt sind. <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> ist <xref:System.Windows.Forms.FlowDirection.TopDown>.  
  
 ![FlowLayoutPanel-Verankerung](../../../../docs/framework/winforms/controls/media/vs-flpanchor2.gif "VS_FLPanchor2")  
  
 Das folgende Codebeispiel veranschaulicht verschiedene <xref:System.Windows.Forms.Control.Anchor%2A>-Eigenschaftswerte für ein <xref:System.Windows.Forms.Button>-Steuerelement in einem <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelement.  
  
 [!code-csharp[System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm/CS/FlpAnchorExampleForm.cs#1)]
 [!code-vb[System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm/VB/FlpAnchorExampleForm.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System", "System.Data", "System.Drawing" und "System.Windows.Forms".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.  Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 [Übersicht über das FlowLayoutPanel-Steuerelement](../../../../docs/framework/winforms/controls/flowlayoutpanel-control-overview.md)
