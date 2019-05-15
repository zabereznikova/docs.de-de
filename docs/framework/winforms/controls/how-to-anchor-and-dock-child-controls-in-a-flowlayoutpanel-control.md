---
title: 'Vorgehensweise: Verankern und Andocken von untergeordneten Steuerelementen in einem FlowLayoutPanel-Steuerelement'
ms.date: 03/30/2017
helpviewer_keywords:
- layout [Windows Forms], child controls
- FlowLayoutPanel control [Windows Forms], child controls
- controls [Windows Forms], child
- child controls [Windows Forms], anchoring and docking
ms.assetid: a2bcdfca-9b63-45e6-9c0e-3411015cba98
ms.openlocfilehash: f67733b89d2bde652449e2338362868fdb84bcf3
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592949"
---
# <a name="how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control"></a><span data-ttu-id="d787f-102">Vorgehensweise: Verankern und Andocken von untergeordneten Steuerelementen in einem FlowLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="d787f-102">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>
<span data-ttu-id="d787f-103">Das <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelement unterstützt die Eigenschaften <xref:System.Windows.Forms.Control.Anchor%2A> und <xref:System.Windows.Forms.Control.Dock%2A> in seinen untergeordneten Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="d787f-103">The <xref:System.Windows.Forms.FlowLayoutPanel> control supports the <xref:System.Windows.Forms.Control.Anchor%2A> and <xref:System.Windows.Forms.Control.Dock%2A> properties in its child controls.</span></span>  
  
### <a name="to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control"></a><span data-ttu-id="d787f-104">So verankern Sie untergeordnete Steuerelemente in einem FlowLayoutPanel-Steuerelement und docken sie an</span><span class="sxs-lookup"><span data-stu-id="d787f-104">To anchor and dock child controls in a FlowLayoutPanel control</span></span>  
  
1. <span data-ttu-id="d787f-105">Erstellen Sie ein <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelement auf dem Formular.</span><span class="sxs-lookup"><span data-stu-id="d787f-105">Create a <xref:System.Windows.Forms.FlowLayoutPanel> control on your form.</span></span>  
  
2. <span data-ttu-id="d787f-106">Festlegen der <xref:System.Windows.Forms.Control.Width%2A> von der <xref:System.Windows.Forms.FlowLayoutPanel> die Steuerung an **300**, und legen Sie seine <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> zu <xref:System.Windows.Forms.FlowDirection.TopDown>.</span><span class="sxs-lookup"><span data-stu-id="d787f-106">Set the <xref:System.Windows.Forms.Control.Width%2A> of the <xref:System.Windows.Forms.FlowLayoutPanel> control to **300**, and set its <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> to <xref:System.Windows.Forms.FlowDirection.TopDown>.</span></span>  
  
3. <span data-ttu-id="d787f-107">Erstellen Sie zwei <xref:System.Windows.Forms.Button>-Steuerelemente, und platzieren Sie diese im <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="d787f-107">Create two <xref:System.Windows.Forms.Button> controls, and place them in the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>  
  
4. <span data-ttu-id="d787f-108">Legen Sie die <xref:System.Windows.Forms.Control.Width%2A> der ersten Schaltfläche auf **200**.</span><span class="sxs-lookup"><span data-stu-id="d787f-108">Set the <xref:System.Windows.Forms.Control.Width%2A> of the first button to **200**.</span></span>  
  
5. <span data-ttu-id="d787f-109">Legen Sie die <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft der zweiten Schaltfläche auf <xref:System.Windows.Forms.DockStyle.Fill> fest.</span><span class="sxs-lookup"><span data-stu-id="d787f-109">Set the <xref:System.Windows.Forms.Control.Dock%2A> property of the second button to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d787f-110">Für die zweite Schaltfläche wird dieselbe Breite angenommen wie für die erste Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="d787f-110">The second button assumes the same width as the first button.</span></span> <span data-ttu-id="d787f-111">Die Schaltfläche erstreckt sich nicht über die Breite des <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="d787f-111">It does not stretch across the width of the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>  
  
6. <span data-ttu-id="d787f-112">Legen Sie die <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft der zweiten Schaltfläche auf `None` fest.</span><span class="sxs-lookup"><span data-stu-id="d787f-112">Set the <xref:System.Windows.Forms.Control.Dock%2A> property of the second button to `None`.</span></span> <span data-ttu-id="d787f-113">Dadurch wird die Schaltfläche auf ihre ursprüngliche Breite zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="d787f-113">This causes the button to assume its original width.</span></span>  
  
7. <span data-ttu-id="d787f-114">Legen Sie die <xref:System.Windows.Forms.Control.Anchor%2A>-Eigenschaft der zweiten Schaltfläche auf `Left, Right` fest.</span><span class="sxs-lookup"><span data-stu-id="d787f-114">Set the <xref:System.Windows.Forms.Control.Anchor%2A> property of the second button to `Left, Right`.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="d787f-115">Für die zweite Schaltfläche wird dieselbe Breite angenommen wie für die erste Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="d787f-115">The second button assumes the same width as the first button.</span></span> <span data-ttu-id="d787f-116">Die Schaltfläche erstreckt sich nicht über die Breite des <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="d787f-116">It does not stretch across the width of the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span> <span data-ttu-id="d787f-117">Die allgemeine Regel zum Verankern und Andocken im <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelement lautet wie folgt: Bei vertikalen Flussrichtungen berechnet das <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelement die Breite einer impliziten Spalte anhand des breitesten untergeordneten Steuerelements in der Spalte.</span><span class="sxs-lookup"><span data-stu-id="d787f-117">This is the general rule for anchoring and docking in the <xref:System.Windows.Forms.FlowLayoutPanel> control: for vertical flow directions, the <xref:System.Windows.Forms.FlowLayoutPanel> control calculates the width of an implied column from the widest child control in the column.</span></span> <span data-ttu-id="d787f-118">Alle anderen Steuerelemente in dieser Spalte mit einer <xref:System.Windows.Forms.Control.Anchor%2A>- oder einer <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft werden so ausgerichtet oder gestreckt, dass sie diese implizite Spalte ausfüllen.</span><span class="sxs-lookup"><span data-stu-id="d787f-118">All other controls in this column with <xref:System.Windows.Forms.Control.Anchor%2A> or <xref:System.Windows.Forms.Control.Dock%2A> properties are aligned or stretched to fit this implied column.</span></span> <span data-ttu-id="d787f-119">Bei horizontalen Flussrichtungen ist das Verhalten ähnlich.</span><span class="sxs-lookup"><span data-stu-id="d787f-119">The behavior works in a similar way for horizontal flow directions.</span></span> <span data-ttu-id="d787f-120">Das <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelement berechnet die Höhe einer impliziten Zeile anhand des höchsten untergeordneten Steuerelements in der Zeile. Alle angedockten oder verankerten untergeordneten Steuerelemente in dieser Zeile werden dann so ausgerichtet oder vergrößert, dass sie diese implizite Zeile ausfüllen.</span><span class="sxs-lookup"><span data-stu-id="d787f-120">The <xref:System.Windows.Forms.FlowLayoutPanel> control calculates the height of an implied row from the tallest child control in the row, and all docked or anchored child controls in this row are aligned or sized to fit the implied row.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d787f-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d787f-121">Example</span></span>  
 <span data-ttu-id="d787f-122">Die folgende Abbildung zeigt vier Schaltflächen, die relativ zur blauen Schaltfläche in einem <xref:System.Windows.Forms.FlowLayoutPanel> verankert und angedockt sind.</span><span class="sxs-lookup"><span data-stu-id="d787f-122">The following illustration shows four buttons that are anchored and docked relative to the blue button in a <xref:System.Windows.Forms.FlowLayoutPanel>.</span></span> <span data-ttu-id="d787f-123"><xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> ist <xref:System.Windows.Forms.FlowDirection.LeftToRight>.</span><span class="sxs-lookup"><span data-stu-id="d787f-123">The <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> is <xref:System.Windows.Forms.FlowDirection.LeftToRight>.</span></span>  
  
 <span data-ttu-id="d787f-124">![FlowLayoutPanel-Verankerung](./media/net-flpanchorexp.gif "NET_FLPanchorExp")</span><span class="sxs-lookup"><span data-stu-id="d787f-124">![FlowLayoutPanel anchoring](./media/net-flpanchorexp.gif "NET_FLPanchorExp")</span></span>  
  
 <span data-ttu-id="d787f-125">Die folgende Abbildung zeigt vier Schaltflächen, die relativ zur blauen Schaltfläche in einem <xref:System.Windows.Forms.FlowLayoutPanel> verankert und angedockt sind.</span><span class="sxs-lookup"><span data-stu-id="d787f-125">The following illustration shows four buttons that are anchored and docked relative to the blue button in a <xref:System.Windows.Forms.FlowLayoutPanel>.</span></span> <span data-ttu-id="d787f-126"><xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> ist <xref:System.Windows.Forms.FlowDirection.TopDown>.</span><span class="sxs-lookup"><span data-stu-id="d787f-126">The <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> is <xref:System.Windows.Forms.FlowDirection.TopDown>.</span></span>  
  
 <span data-ttu-id="d787f-127">![FlowLayoutPanel-Verankerung](./media/vs-flpanchor2.gif "VS_FLPanchor2")</span><span class="sxs-lookup"><span data-stu-id="d787f-127">![FlowLayoutPanel anchoring](./media/vs-flpanchor2.gif "VS_FLPanchor2")</span></span>  
  
 <span data-ttu-id="d787f-128">Das folgende Codebeispiel veranschaulicht verschiedene <xref:System.Windows.Forms.Control.Anchor%2A>-Eigenschaftswerte für ein <xref:System.Windows.Forms.Button>-Steuerelement in einem <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="d787f-128">The following code example demonstrates various <xref:System.Windows.Forms.Control.Anchor%2A> property values for a <xref:System.Windows.Forms.Button> control in a <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm/CS/FlpAnchorExampleForm.cs#1)]
 [!code-vb[System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm/VB/FlpAnchorExampleForm.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d787f-129">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="d787f-129">Compiling the Code</span></span>  
 <span data-ttu-id="d787f-130">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="d787f-130">This example requires:</span></span>  
  
- <span data-ttu-id="d787f-131">Verweise auf die Assemblys "System", "System.Data", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="d787f-131">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d787f-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d787f-132">See also</span></span>

- <xref:System.Windows.Forms.FlowLayoutPanel>
- [<span data-ttu-id="d787f-133">Übersicht über das FlowLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="d787f-133">FlowLayoutPanel Control Overview</span></span>](flowlayoutpanel-control-overview.md)
