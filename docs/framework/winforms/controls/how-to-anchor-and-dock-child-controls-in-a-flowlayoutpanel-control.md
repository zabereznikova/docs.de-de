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
# <a name="how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control"></a><span data-ttu-id="9f173-103">Vorgehensweise: Verankern und Andocken von untergeordneten Steuerelementen in einem FlowLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="9f173-103">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>

<span data-ttu-id="9f173-104">Das <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelement unterstützt die Eigenschaften <xref:System.Windows.Forms.Control.Anchor%2A> und <xref:System.Windows.Forms.Control.Dock%2A> in seinen untergeordneten Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="9f173-104">The <xref:System.Windows.Forms.FlowLayoutPanel> control supports the <xref:System.Windows.Forms.Control.Anchor%2A> and <xref:System.Windows.Forms.Control.Dock%2A> properties in its child controls.</span></span>

### <a name="to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control"></a><span data-ttu-id="9f173-105">So verankern Sie untergeordnete Steuerelemente in einem FlowLayoutPanel-Steuerelement und docken sie an</span><span class="sxs-lookup"><span data-stu-id="9f173-105">To anchor and dock child controls in a FlowLayoutPanel control</span></span>

1. <span data-ttu-id="9f173-106">Erstellen Sie ein <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelement auf dem Formular.</span><span class="sxs-lookup"><span data-stu-id="9f173-106">Create a <xref:System.Windows.Forms.FlowLayoutPanel> control on your form.</span></span>

2. <span data-ttu-id="9f173-107">Legen Sie für das-Steuerelement den Wert <xref:System.Windows.Forms.Control.Width%2A> <xref:System.Windows.Forms.FlowLayoutPanel> **300**fest, und legen <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> Sie dessen auf fest <xref:System.Windows.Forms.FlowDirection.TopDown> .</span><span class="sxs-lookup"><span data-stu-id="9f173-107">Set the <xref:System.Windows.Forms.Control.Width%2A> of the <xref:System.Windows.Forms.FlowLayoutPanel> control to **300**, and set its <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> to <xref:System.Windows.Forms.FlowDirection.TopDown>.</span></span>

3. <span data-ttu-id="9f173-108">Erstellen Sie zwei <xref:System.Windows.Forms.Button>-Steuerelemente, und platzieren Sie diese im <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="9f173-108">Create two <xref:System.Windows.Forms.Button> controls, and place them in the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

4. <span data-ttu-id="9f173-109">Legen <xref:System.Windows.Forms.Control.Width%2A> Sie die der ersten Schaltfläche auf **200**fest.</span><span class="sxs-lookup"><span data-stu-id="9f173-109">Set the <xref:System.Windows.Forms.Control.Width%2A> of the first button to **200**.</span></span>

5. <span data-ttu-id="9f173-110">Legen Sie die <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft der zweiten Schaltfläche auf <xref:System.Windows.Forms.DockStyle.Fill> fest.</span><span class="sxs-lookup"><span data-stu-id="9f173-110">Set the <xref:System.Windows.Forms.Control.Dock%2A> property of the second button to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9f173-111">Für die zweite Schaltfläche wird dieselbe Breite angenommen wie für die erste Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="9f173-111">The second button assumes the same width as the first button.</span></span> <span data-ttu-id="9f173-112">Die Schaltfläche erstreckt sich nicht über die Breite des <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="9f173-112">It does not stretch across the width of the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

6. <span data-ttu-id="9f173-113">Legen Sie die <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft der zweiten Schaltfläche auf `None` fest.</span><span class="sxs-lookup"><span data-stu-id="9f173-113">Set the <xref:System.Windows.Forms.Control.Dock%2A> property of the second button to `None`.</span></span> <span data-ttu-id="9f173-114">Dadurch wird die Schaltfläche auf ihre ursprüngliche Breite zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="9f173-114">This causes the button to assume its original width.</span></span>

7. <span data-ttu-id="9f173-115">Legen Sie die <xref:System.Windows.Forms.Control.Anchor%2A>-Eigenschaft der zweiten Schaltfläche auf `Left, Right` fest.</span><span class="sxs-lookup"><span data-stu-id="9f173-115">Set the <xref:System.Windows.Forms.Control.Anchor%2A> property of the second button to `Left, Right`.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="9f173-116">Für die zweite Schaltfläche wird dieselbe Breite angenommen wie für die erste Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="9f173-116">The second button assumes the same width as the first button.</span></span> <span data-ttu-id="9f173-117">Die Schaltfläche erstreckt sich nicht über die Breite des <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="9f173-117">It does not stretch across the width of the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span> <span data-ttu-id="9f173-118">Die allgemeine Regel zum Verankern und Andocken im <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelement lautet wie folgt: Bei vertikalen Flussrichtungen berechnet das <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelement die Breite einer impliziten Spalte anhand des breitesten untergeordneten Steuerelements in der Spalte.</span><span class="sxs-lookup"><span data-stu-id="9f173-118">This is the general rule for anchoring and docking in the <xref:System.Windows.Forms.FlowLayoutPanel> control: for vertical flow directions, the <xref:System.Windows.Forms.FlowLayoutPanel> control calculates the width of an implied column from the widest child control in the column.</span></span> <span data-ttu-id="9f173-119">Alle anderen Steuerelemente in dieser Spalte mit einer <xref:System.Windows.Forms.Control.Anchor%2A>- oder einer <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft werden so ausgerichtet oder gestreckt, dass sie diese implizite Spalte ausfüllen.</span><span class="sxs-lookup"><span data-stu-id="9f173-119">All other controls in this column with <xref:System.Windows.Forms.Control.Anchor%2A> or <xref:System.Windows.Forms.Control.Dock%2A> properties are aligned or stretched to fit this implied column.</span></span> <span data-ttu-id="9f173-120">Bei horizontalen Flussrichtungen ist das Verhalten ähnlich.</span><span class="sxs-lookup"><span data-stu-id="9f173-120">The behavior works in a similar way for horizontal flow directions.</span></span> <span data-ttu-id="9f173-121">Das <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelement berechnet die Höhe einer impliziten Zeile anhand des höchsten untergeordneten Steuerelements in der Zeile. Alle angedockten oder verankerten untergeordneten Steuerelemente in dieser Zeile werden dann so ausgerichtet oder vergrößert, dass sie diese implizite Zeile ausfüllen.</span><span class="sxs-lookup"><span data-stu-id="9f173-121">The <xref:System.Windows.Forms.FlowLayoutPanel> control calculates the height of an implied row from the tallest child control in the row, and all docked or anchored child controls in this row are aligned or sized to fit the implied row.</span></span>

## <a name="example"></a><span data-ttu-id="9f173-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9f173-122">Example</span></span>

<span data-ttu-id="9f173-123">Die folgende Abbildung zeigt vier Schaltflächen, die relativ zur blauen Schaltfläche in einem <xref:System.Windows.Forms.FlowLayoutPanel> verankert und angedockt sind.</span><span class="sxs-lookup"><span data-stu-id="9f173-123">The following illustration shows four buttons that are anchored and docked relative to the blue button in a <xref:System.Windows.Forms.FlowLayoutPanel>.</span></span> <span data-ttu-id="9f173-124">Der Jointyp (<xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>) lautet <xref:System.Windows.Forms.FlowDirection.LeftToRight>.</span><span class="sxs-lookup"><span data-stu-id="9f173-124">The <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> is <xref:System.Windows.Forms.FlowDirection.LeftToRight>.</span></span>

<span data-ttu-id="9f173-125">![FlowLayoutPanel-Verankerung](./media/net-flpanchorexp.gif "NET_FLPanchorExp")</span><span class="sxs-lookup"><span data-stu-id="9f173-125">![FlowLayoutPanel anchoring](./media/net-flpanchorexp.gif "NET_FLPanchorExp")</span></span>

<span data-ttu-id="9f173-126">Die folgende Abbildung zeigt vier Schaltflächen, die relativ zur blauen Schaltfläche in einem <xref:System.Windows.Forms.FlowLayoutPanel> verankert und angedockt sind.</span><span class="sxs-lookup"><span data-stu-id="9f173-126">The following illustration shows four buttons that are anchored and docked relative to the blue button in a <xref:System.Windows.Forms.FlowLayoutPanel>.</span></span> <span data-ttu-id="9f173-127">Der Jointyp (<xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>) lautet <xref:System.Windows.Forms.FlowDirection.TopDown>.</span><span class="sxs-lookup"><span data-stu-id="9f173-127">The <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> is <xref:System.Windows.Forms.FlowDirection.TopDown>.</span></span>

<span data-ttu-id="9f173-128">![FlowLayoutPanel-Verankerung](./media/vs-flpanchor2.gif "VS_FLPanchor2")</span><span class="sxs-lookup"><span data-stu-id="9f173-128">![FlowLayoutPanel anchoring](./media/vs-flpanchor2.gif "VS_FLPanchor2")</span></span>

<span data-ttu-id="9f173-129">Das folgende Codebeispiel veranschaulicht verschiedene <xref:System.Windows.Forms.Control.Anchor%2A>-Eigenschaftswerte für ein <xref:System.Windows.Forms.Button>-Steuerelement in einem <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="9f173-129">The following code example demonstrates various <xref:System.Windows.Forms.Control.Anchor%2A> property values for a <xref:System.Windows.Forms.Button> control in a <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

[!code-csharp[System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm/CS/FlpAnchorExampleForm.cs#1)]
[!code-vb[System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm/VB/FlpAnchorExampleForm.vb#1)]

## <a name="compiling-the-code"></a><span data-ttu-id="9f173-130">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="9f173-130">Compiling the Code</span></span>

<span data-ttu-id="9f173-131">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="9f173-131">This example requires:</span></span>

- <span data-ttu-id="9f173-132">Verweise auf die Assemblys "System", "System.Data", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="9f173-132">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>

## <a name="see-also"></a><span data-ttu-id="9f173-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9f173-133">See also</span></span>

- <xref:System.Windows.Forms.FlowLayoutPanel>
- [<span data-ttu-id="9f173-134">Übersicht über das FlowLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="9f173-134">FlowLayoutPanel Control Overview</span></span>](flowlayoutpanel-control-overview.md)
