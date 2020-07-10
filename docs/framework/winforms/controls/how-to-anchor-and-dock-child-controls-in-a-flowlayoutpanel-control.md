---
title: 'Vorgehensweise: Verankern und Andocken von untergeordneten Steuerelementen in einem FlowLayoutPanel-Steuerelement'
description: Informationen zum programmgesteuerten verankern und Andocken von untergeordneten Steuerelementen in einem Windows Forms FlowLayoutPanel-Steuerelement.
ms.date: 03/30/2017
helpviewer_keywords:
- layout [Windows Forms], child controls
- FlowLayoutPanel control [Windows Forms], child controls
- controls [Windows Forms], child
- child controls [Windows Forms], anchoring and docking
ms.assetid: a2bcdfca-9b63-45e6-9c0e-3411015cba98
ms.openlocfilehash: b4fb3bf6d148a526a75926bd67c1f967286332bf
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174535"
---
# <a name="how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control"></a>Vorgehensweise: Verankern und Andocken von untergeordneten Steuerelementen in einem FlowLayoutPanel-Steuerelement

Das <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelement unterstützt die Eigenschaften <xref:System.Windows.Forms.Control.Anchor%2A> und <xref:System.Windows.Forms.Control.Dock%2A> in seinen untergeordneten Steuerelementen.

### <a name="to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control"></a>So verankern Sie untergeordnete Steuerelemente in einem FlowLayoutPanel-Steuerelement und docken sie an

1. Erstellen Sie ein <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelement auf dem Formular.

2. Legen Sie für das-Steuerelement den Wert <xref:System.Windows.Forms.Control.Width%2A> <xref:System.Windows.Forms.FlowLayoutPanel> **300**fest, und legen <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> Sie dessen auf fest <xref:System.Windows.Forms.FlowDirection.TopDown> .

3. Erstellen Sie zwei <xref:System.Windows.Forms.Button>-Steuerelemente, und platzieren Sie diese im <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelement.

4. Legen <xref:System.Windows.Forms.Control.Width%2A> Sie die der ersten Schaltfläche auf **200**fest.

5. Legen Sie die <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft der zweiten Schaltfläche auf <xref:System.Windows.Forms.DockStyle.Fill> fest.

    > [!NOTE]
    > Für die zweite Schaltfläche wird dieselbe Breite angenommen wie für die erste Schaltfläche. Die Schaltfläche erstreckt sich nicht über die Breite des <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelements.

6. Legen Sie die <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft der zweiten Schaltfläche auf `None` fest. Dadurch wird die Schaltfläche auf ihre ursprüngliche Breite zurückgesetzt.

7. Legen Sie die <xref:System.Windows.Forms.Control.Anchor%2A>-Eigenschaft der zweiten Schaltfläche auf `Left, Right` fest.

    > [!IMPORTANT]
    > Für die zweite Schaltfläche wird dieselbe Breite angenommen wie für die erste Schaltfläche. Die Schaltfläche erstreckt sich nicht über die Breite des <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelements. Die allgemeine Regel zum Verankern und Andocken im <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelement lautet wie folgt: Bei vertikalen Flussrichtungen berechnet das <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelement die Breite einer impliziten Spalte anhand des breitesten untergeordneten Steuerelements in der Spalte. Alle anderen Steuerelemente in dieser Spalte mit einer <xref:System.Windows.Forms.Control.Anchor%2A>- oder einer <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft werden so ausgerichtet oder gestreckt, dass sie diese implizite Spalte ausfüllen. Bei horizontalen Flussrichtungen ist das Verhalten ähnlich. Das <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelement berechnet die Höhe einer impliziten Zeile anhand des höchsten untergeordneten Steuerelements in der Zeile. Alle angedockten oder verankerten untergeordneten Steuerelemente in dieser Zeile werden dann so ausgerichtet oder vergrößert, dass sie diese implizite Zeile ausfüllen.

## <a name="example"></a>Beispiel

Die folgende Abbildung zeigt vier Schaltflächen, die relativ zur blauen Schaltfläche in einem <xref:System.Windows.Forms.FlowLayoutPanel> verankert und angedockt sind. Der Jointyp (<xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>) lautet <xref:System.Windows.Forms.FlowDirection.LeftToRight>.

![FlowLayoutPanel-Verankerung](./media/net-flpanchorexp.gif "NET_FLPanchorExp")

Die folgende Abbildung zeigt vier Schaltflächen, die relativ zur blauen Schaltfläche in einem <xref:System.Windows.Forms.FlowLayoutPanel> verankert und angedockt sind. Der Jointyp (<xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>) lautet <xref:System.Windows.Forms.FlowDirection.TopDown>.

![FlowLayoutPanel-Verankerung](./media/vs-flpanchor2.gif "VS_FLPanchor2")

Das folgende Codebeispiel veranschaulicht verschiedene <xref:System.Windows.Forms.Control.Anchor%2A>-Eigenschaftswerte für ein <xref:System.Windows.Forms.Button>-Steuerelement in einem <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelement.

[!code-csharp[System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm/CS/FlpAnchorExampleForm.cs#1)]
[!code-vb[System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm/VB/FlpAnchorExampleForm.vb#1)]

## <a name="compiling-the-code"></a>Kompilieren des Codes

Für dieses Beispiel benötigen Sie Folgendes:

- Verweise auf die Assemblys "System", "System.Data", "System.Drawing" und "System.Windows.Forms".

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.FlowLayoutPanel>
- [Übersicht über das FlowLayoutPanel-Steuerelement](flowlayoutpanel-control-overview.md)
