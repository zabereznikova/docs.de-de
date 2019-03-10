---
title: 'Vorgehensweise: Andocken von Steuerelementen in Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
ms.openlocfilehash: 4acda9149dd147a823eb42d3962a22b75df93802
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720265"
---
# <a name="how-to-dock-controls-on-windows-forms"></a><span data-ttu-id="ab25f-102">Vorgehensweise: Andocken von Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ab25f-102">How to: Dock Controls on Windows Forms</span></span>
<span data-ttu-id="ab25f-103">Sie können Andocken von Steuerelementen an den Rändern des Formulars oder Sie geben Sie im Container des Steuerelements (ein Formular oder ein Container-Steuerelement).</span><span class="sxs-lookup"><span data-stu-id="ab25f-103">You can dock controls to the edges of your form or have them fill the control's container (either a form or a container control).</span></span> <span data-ttu-id="ab25f-104">Beispielsweise Windows-Explorer angedockt seine <xref:System.Windows.Forms.TreeView> Steuerelement auf der linken Seite des Fensters und die zugehörige <xref:System.Windows.Forms.ListView> Steuerelement auf die rechte Seite des Fensters.</span><span class="sxs-lookup"><span data-stu-id="ab25f-104">For example, Windows Explorer docks its <xref:System.Windows.Forms.TreeView> control to the left side of the window and its <xref:System.Windows.Forms.ListView> control to the right side of the window.</span></span> <span data-ttu-id="ab25f-105">Verwenden der <xref:System.Windows.Forms.Control.Dock%2A> -Eigenschaft für alle sichtbaren Windows Forms-Steuerelemente, um den Andockmodus zu definieren.</span><span class="sxs-lookup"><span data-stu-id="ab25f-105">Use the <xref:System.Windows.Forms.Control.Dock%2A> property for all visible Windows Forms controls to define the docking mode.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ab25f-106">Steuerelemente werden in umgekehrter Z-Reihenfolge angedockt.</span><span class="sxs-lookup"><span data-stu-id="ab25f-106">Controls are docked in reverse z-order.</span></span>  
  
 <span data-ttu-id="ab25f-107">Die <xref:System.Windows.Forms.Control.Dock%2A> -Eigenschaft interagiert mit der <xref:System.Windows.Forms.Control.AutoSize%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="ab25f-107">The <xref:System.Windows.Forms.Control.Dock%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="ab25f-108">Weitere Informationen finden Sie unter [Übersicht über die AutoSize-Eigenschaft](autosize-property-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ab25f-108">For more information, see [AutoSize Property Overview](autosize-property-overview.md).</span></span>  
  
### <a name="to-dock-a-control"></a><span data-ttu-id="ab25f-109">So docken Sie ein Steuerelement an</span><span class="sxs-lookup"><span data-stu-id="ab25f-109">To dock a control</span></span>  
  
1.  <span data-ttu-id="ab25f-110">Wählen Sie das Steuerelement, das Sie andocken möchten.</span><span class="sxs-lookup"><span data-stu-id="ab25f-110">Select the control that you want to dock.</span></span>  
  
2.  <span data-ttu-id="ab25f-111">Klicken Sie im Eigenschaftenfenster auf den Pfeil rechts neben der <xref:System.Windows.Forms.Control.Dock%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="ab25f-111">In the Properties window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span>  
  
     <span data-ttu-id="ab25f-112">Ein Editor wird mit einer Reihe von Feldern, die darstellt, die Kanten und der Mitte des Formulars angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ab25f-112">An editor is displayed that shows a series of boxes representing the edges and the center of the form.</span></span>  
  
3.  <span data-ttu-id="ab25f-113">Klicken Sie auf die Schaltfläche ", die den Rand des Formulars darstellt, in dem das Steuerelement angedockt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ab25f-113">Click the button that represents the edge of the form where you want to dock the control.</span></span> <span data-ttu-id="ab25f-114">Klicken Sie auf das mittlere Feld, um den Inhalt des Steuerelements Formular oder Containersteuerelement zu füllen.</span><span class="sxs-lookup"><span data-stu-id="ab25f-114">To fill the contents of the control's form or container control, click the center box.</span></span> <span data-ttu-id="ab25f-115">Klicken Sie auf **(keine)** zum Andocken zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="ab25f-115">Click **(none)** to disable docking.</span></span>  
  
     <span data-ttu-id="ab25f-116">Das Steuerelement wird automatische größenanpassung die Grenzen der verankerten Kante.</span><span class="sxs-lookup"><span data-stu-id="ab25f-116">The control is automatically resized to fit the boundaries of the docked edge.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ab25f-117">Geerbte Steuerelemente muss `Protected` angedockt werden kann.</span><span class="sxs-lookup"><span data-stu-id="ab25f-117">Inherited controls must be `Protected` to be able to be docked.</span></span> <span data-ttu-id="ab25f-118">Um die Zugriffsebene eines Steuerelements zu ändern, legen Sie dessen **Modifizierer** Eigenschaft im Eigenschaftenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ab25f-118">To change the access level of a control, set its **Modifier** property in the Properties window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab25f-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ab25f-119">See also</span></span>
- [<span data-ttu-id="ab25f-120">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="ab25f-120">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="ab25f-121">Anordnen von Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ab25f-121">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="ab25f-122">Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente</span><span class="sxs-lookup"><span data-stu-id="ab25f-122">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="ab25f-123">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="ab25f-123">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="ab25f-124">Windows Forms-Steuerelemente nach Funktion</span><span class="sxs-lookup"><span data-stu-id="ab25f-124">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
- [<span data-ttu-id="ab25f-125">Vorgehensweise: Verankern und Andocken von untergeordneten Steuerelementen in einem FlowLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ab25f-125">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [<span data-ttu-id="ab25f-126">Vorgehensweise: Verankern und Andocken von untergeordneten Steuerelementen in einem TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ab25f-126">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="ab25f-127">Übersicht über die AutoSize-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="ab25f-127">AutoSize Property Overview</span></span>](autosize-property-overview.md)
- [<span data-ttu-id="ab25f-128">Vorgehensweise: Verankern von Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ab25f-128">How to: Anchor Controls on Windows Forms</span></span>](how-to-anchor-controls-on-windows-forms.md)
