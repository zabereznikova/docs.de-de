---
title: "Gewusst wie: Andocken von Steuerelementen in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fc7227ee46f127070b44771a56a89b82bd0930ca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-dock-controls-on-windows-forms"></a><span data-ttu-id="baa5b-102">Gewusst wie: Andocken von Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="baa5b-102">How to: Dock Controls on Windows Forms</span></span>
<span data-ttu-id="baa5b-103">Sie können Steuerelemente an den Rändern des Formulars angedockt oder Steuerelementcontainers (ein Formular oder Containersteuerelement) ausfüllen.</span><span class="sxs-lookup"><span data-stu-id="baa5b-103">You can dock controls to the edges of your form or have them fill the control's container (either a form or a container control).</span></span> <span data-ttu-id="baa5b-104">Z. B. Windows-Explorer dockt an seine <xref:System.Windows.Forms.TreeView> Steuerelement auf der linken Seite des Fensters und die zugehörige <xref:System.Windows.Forms.ListView> Steuerelement auf die rechte Seite des Fensters.</span><span class="sxs-lookup"><span data-stu-id="baa5b-104">For example, Windows Explorer docks its <xref:System.Windows.Forms.TreeView> control to the left side of the window and its <xref:System.Windows.Forms.ListView> control to the right side of the window.</span></span> <span data-ttu-id="baa5b-105">Verwenden der <xref:System.Windows.Forms.Control.Dock%2A> -Eigenschaft für alle sichtbaren Windows Forms-Steuerelemente den Andockmodus definieren.</span><span class="sxs-lookup"><span data-stu-id="baa5b-105">Use the <xref:System.Windows.Forms.Control.Dock%2A> property for all visible Windows Forms controls to define the docking mode.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="baa5b-106">Steuerelemente werden in umgekehrter Z-Reihenfolge angedockt.</span><span class="sxs-lookup"><span data-stu-id="baa5b-106">Controls are docked in reverse z-order.</span></span>  
  
 <span data-ttu-id="baa5b-107">Die <xref:System.Windows.Forms.Control.Dock%2A> -Eigenschaft interagiert mit den <xref:System.Windows.Forms.Control.AutoSize%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="baa5b-107">The <xref:System.Windows.Forms.Control.Dock%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="baa5b-108">Weitere Informationen finden Sie unter [Übersicht über die AutoSize-Eigenschaft](../../../../docs/framework/winforms/controls/autosize-property-overview.md).</span><span class="sxs-lookup"><span data-stu-id="baa5b-108">For more information, see [AutoSize Property Overview](../../../../docs/framework/winforms/controls/autosize-property-overview.md).</span></span>  
  
### <a name="to-dock-a-control"></a><span data-ttu-id="baa5b-109">So docken Sie ein Steuerelement an</span><span class="sxs-lookup"><span data-stu-id="baa5b-109">To dock a control</span></span>  
  
1.  <span data-ttu-id="baa5b-110">Wählen Sie das Steuerelement, das Sie andocken möchten.</span><span class="sxs-lookup"><span data-stu-id="baa5b-110">Select the control that you want to dock.</span></span>  
  
2.  <span data-ttu-id="baa5b-111">Klicken Sie im Fenster Eigenschaften auf den Pfeil rechts neben der <xref:System.Windows.Forms.Control.Dock%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="baa5b-111">In the Properties window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span>  
  
     <span data-ttu-id="baa5b-112">Ein Editor wird angezeigt, die eine Reihe von Feldern, die die Kanten und der Mitte des Formulars darstellt.</span><span class="sxs-lookup"><span data-stu-id="baa5b-112">An editor is displayed that shows a series of boxes representing the edges and the center of the form.</span></span>  
  
3.  <span data-ttu-id="baa5b-113">Klicken Sie auf die Schaltfläche ", die den Rand des Formulars darstellt, in dem das Steuerelement angedockt werden soll.</span><span class="sxs-lookup"><span data-stu-id="baa5b-113">Click the button that represents the edge of the form where you want to dock the control.</span></span> <span data-ttu-id="baa5b-114">Klicken Sie auf das mittlere Feld, um den Inhalt des Steuerelements Formular oder Containersteuerelement zu füllen.</span><span class="sxs-lookup"><span data-stu-id="baa5b-114">To fill the contents of the control's form or container control, click the center box.</span></span> <span data-ttu-id="baa5b-115">Klicken Sie auf **(keine)** zum Andocken zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="baa5b-115">Click **(none)** to disable docking.</span></span>  
  
     <span data-ttu-id="baa5b-116">Das Steuerelement wird automatisch die Grenzen des angedockten Rands entsprechend angepasst.</span><span class="sxs-lookup"><span data-stu-id="baa5b-116">The control is automatically resized to fit the boundaries of the docked edge.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="baa5b-117">Geerbte Steuerelemente muss `Protected` angedockt werden können.</span><span class="sxs-lookup"><span data-stu-id="baa5b-117">Inherited controls must be `Protected` to be able to be docked.</span></span> <span data-ttu-id="baa5b-118">Um die Zugriffsebene eines Steuerelements zu ändern, legen Sie dessen **Modifizierer** Eigenschaft im Eigenschaftenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="baa5b-118">To change the access level of a control, set its **Modifier** property in the Properties window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baa5b-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="baa5b-119">See Also</span></span>  
 [<span data-ttu-id="baa5b-120">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="baa5b-120">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="baa5b-121">Anordnen von Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="baa5b-121">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="baa5b-122">Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente</span><span class="sxs-lookup"><span data-stu-id="baa5b-122">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="baa5b-123">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="baa5b-123">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="baa5b-124">Windows Forms-Steuerelemente nach Funktion</span><span class="sxs-lookup"><span data-stu-id="baa5b-124">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)  
 [<span data-ttu-id="baa5b-125">Gewusst wie: Verankern und Andocken von untergeordneten Steuerelementen in einem FlowLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="baa5b-125">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)  
 [<span data-ttu-id="baa5b-126">Gewusst wie: Verankern und Andocken von untergeordneten Steuerelementen in einem TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="baa5b-126">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [<span data-ttu-id="baa5b-127">Übersicht über die AutoSize-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="baa5b-127">AutoSize Property Overview</span></span>](../../../../docs/framework/winforms/controls/autosize-property-overview.md)  
 [<span data-ttu-id="baa5b-128">Gewusst wie: Verankern von Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="baa5b-128">How to: Anchor Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-controls-on-windows-forms.md)
