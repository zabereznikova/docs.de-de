---
title: 'Gewusst wie: Ausrichten eines Steuerelements an den Rändern eines Formulars zur Entwurfszeit'
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], docking using designer
- Dock property [Windows Forms], aligning controls (using designer)
ms.assetid: 51f08998-5e3b-4330-be58-a4edd0eb60f4
ms.openlocfilehash: 5b36879413442ff99da034fcbee6bf6388affa6d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33528712"
---
# <a name="how-to-align-a-control-to-the-edges-of-forms-at-design-time"></a><span data-ttu-id="4a5f5-102">Gewusst wie: Ausrichten eines Steuerelements an den Rändern eines Formulars zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="4a5f5-102">How to: Align a Control to the Edges of Forms at Design Time</span></span>
<span data-ttu-id="4a5f5-103">Sie können das Steuerelement durch Festlegen der Formularrand ausrichten machen die <xref:System.Windows.Forms.Control.Dock%2A>.</span><span class="sxs-lookup"><span data-stu-id="4a5f5-103">You can make your control align to the edge of your forms by setting the <xref:System.Windows.Forms.Control.Dock%2A>.</span></span> <span data-ttu-id="4a5f5-104">Diese Eigenschaft legt fest, wo auf dem Formular das Steuerelement sich befindet.</span><span class="sxs-lookup"><span data-stu-id="4a5f5-104">This property designates where your control resides in the form.</span></span> <span data-ttu-id="4a5f5-105">Die <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft kann auf einen der folgenden Werte festgelegt werden:</span><span class="sxs-lookup"><span data-stu-id="4a5f5-105">The <xref:System.Windows.Forms.Control.Dock%2A> property can be set to the following values:</span></span>  
  
|<span data-ttu-id="4a5f5-106">Einstellung</span><span class="sxs-lookup"><span data-stu-id="4a5f5-106">Setting</span></span>|<span data-ttu-id="4a5f5-107">Auswirkung auf das Steuerelement</span><span class="sxs-lookup"><span data-stu-id="4a5f5-107">Effect on your control</span></span>|  
|-------------|----------------------------|  
|<xref:System.Windows.Forms.DockStyle.Bottom>|<span data-ttu-id="4a5f5-108">Wird im unteren Bereich des Formulars angedockt.</span><span class="sxs-lookup"><span data-stu-id="4a5f5-108">Docks to the bottom of the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Fill>|<span data-ttu-id="4a5f5-109">Füllt den gesamten verbleibenden Platz im Formular aus.</span><span class="sxs-lookup"><span data-stu-id="4a5f5-109">Fills all remaining space in the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Left>|<span data-ttu-id="4a5f5-110">Wird an der linken Seite des Formulars angedockt.</span><span class="sxs-lookup"><span data-stu-id="4a5f5-110">Docks to the left side of the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.None>|<span data-ttu-id="4a5f5-111">Wird nicht angedockt, die überall und wird an der Position gemäß seiner <xref:System.Windows.Forms.Control.Location%2A>.</span><span class="sxs-lookup"><span data-stu-id="4a5f5-111">Does not dock anywhere, and it appears at the location specified by its <xref:System.Windows.Forms.Control.Location%2A>.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Right>|<span data-ttu-id="4a5f5-112">Wird an der rechten Seite des Formulars angedockt.</span><span class="sxs-lookup"><span data-stu-id="4a5f5-112">Docks to the right side of the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Top>|<span data-ttu-id="4a5f5-113">Wird im oberen Bereich des Formulars angedockt.</span><span class="sxs-lookup"><span data-stu-id="4a5f5-113">Docks to the top of the form.</span></span>|  
  
 <span data-ttu-id="4a5f5-114">Diese Werte können auch im Code festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="4a5f5-114">These values can also be set in code.</span></span> <span data-ttu-id="4a5f5-115">Weitere Informationen finden Sie unter [wie: Ausrichten eines Steuerelements an den Kanten Formularen](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms.md).</span><span class="sxs-lookup"><span data-stu-id="4a5f5-115">For more information, see [How to: Align a Control to the Edges of Forms](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4a5f5-116">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="4a5f5-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="4a5f5-117">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="4a5f5-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="4a5f5-118">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="4a5f5-118">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-set-the-dock-property-for-your-control-at-design-time"></a><span data-ttu-id="4a5f5-119">Um die Dock-Eigenschaft für das Steuerelement zur Entwurfszeit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4a5f5-119">To set the Dock property for your control at design time</span></span>  
  
1.  <span data-ttu-id="4a5f5-120">Wählen Sie das Steuerelement in Windows Forms-Designer.</span><span class="sxs-lookup"><span data-stu-id="4a5f5-120">In the Windows Forms Designer, select your control.</span></span>  
  
2.  <span data-ttu-id="4a5f5-121">In der **Eigenschaften** Fenster, klicken Sie auf das Dropdown-Feld neben dem <xref:System.Windows.Forms.Control.Dock%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="4a5f5-121">In the **Properties** window, click the drop-down box next to the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span>  
  
     <span data-ttu-id="4a5f5-122">Eine grafische Benutzeroberfläche, die sechs mögliche darstellt <xref:System.Windows.Forms.Control.Dock%2A> Einstellungen wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4a5f5-122">A graphical interface representing the six possible <xref:System.Windows.Forms.Control.Dock%2A> settings is displayed.</span></span>  
  
3.  <span data-ttu-id="4a5f5-123">Wählen Sie die gewünschte Einstellung aus.</span><span class="sxs-lookup"><span data-stu-id="4a5f5-123">Choose the appropriate setting.</span></span>  
  
4.  <span data-ttu-id="4a5f5-124">Das Steuerelement wird jetzt von der Einstellung angegebene Weise angedockt.</span><span class="sxs-lookup"><span data-stu-id="4a5f5-124">Your control will now dock in the manner specified by the setting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a5f5-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4a5f5-125">See Also</span></span>  
 <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="4a5f5-126">Gewusst wie: Ausrichten eines Steuerelements an Formularrändern</span><span class="sxs-lookup"><span data-stu-id="4a5f5-126">How to: Align a Control to the Edges of Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms.md)  
 [<span data-ttu-id="4a5f5-127">Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien</span><span class="sxs-lookup"><span data-stu-id="4a5f5-127">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [<span data-ttu-id="4a5f5-128">Gewusst wie: Verankern von Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4a5f5-128">How to: Anchor Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-controls-on-windows-forms.md)  
 [<span data-ttu-id="4a5f5-129">Gewusst wie: Verankern und Andocken von untergeordneten Steuerelementen in einem TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="4a5f5-129">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [<span data-ttu-id="4a5f5-130">Gewusst wie: Verankern und Andocken von untergeordneten Steuerelementen in einem FlowLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="4a5f5-130">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)  
 [<span data-ttu-id="4a5f5-131">Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="4a5f5-131">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [<span data-ttu-id="4a5f5-132">Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="4a5f5-132">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [<span data-ttu-id="4a5f5-133">Entwickeln von Windows Forms-Steuerelementen zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="4a5f5-133">Developing Windows Forms Controls at Design Time</span></span>](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)
