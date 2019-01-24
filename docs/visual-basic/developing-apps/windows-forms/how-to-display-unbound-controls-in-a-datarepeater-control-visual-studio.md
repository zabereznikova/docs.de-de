---
title: 'Vorgehensweise: Zeigen Sie nicht gebundener Steuerelemente in einem DataRepeater-Steuerelement (Visual Studio an)'
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, adding unbound controls
- DataRepeater
- displaying unbound data
ms.assetid: f234fa40-5a13-4209-930e-7c5f81e86e66
ms.openlocfilehash: a20e1ba83d1963bc3d4c135817767ee02fcbdeda
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730788"
---
# <a name="how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio"></a><span data-ttu-id="fc59b-102">Vorgehensweise: Zeigen Sie nicht gebundener Steuerelemente in einem DataRepeater-Steuerelement (Visual Studio an)</span><span class="sxs-lookup"><span data-stu-id="fc59b-102">How to: Display Unbound Controls in a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="fc59b-103">Zusätzlich zu den gebundenen Steuerelementen, Sie möchten andere Steuerelemente zum Hinzufügen einer <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, z. B. eine statische Bezeichnung oder ein Bild, das wiederholt wird, für jedes Element in der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="fc59b-103">In addition to bound controls, you may want to add other controls to a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, such as a static label or an image that is repeated on each item in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fc59b-104">Außerdem benötigen Sie mindestens ein gebundenes Steuerelement auf der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> oder "nothing" wird zur Laufzeit angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fc59b-104">You must also have at least one bound control on the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> or nothing will be displayed at run time.</span></span>  
  
### <a name="to-add-unbound-controls-to-a-datarepeater"></a><span data-ttu-id="fc59b-105">Hinzufügen von nicht gebundenen Steuerelementen zum DataRepeater</span><span class="sxs-lookup"><span data-stu-id="fc59b-105">To add unbound controls to a DataRepeater</span></span>  
  
1.  <span data-ttu-id="fc59b-106">Ziehen Sie eine <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement aus der **Visual Basic PowerPacks** Registerkarte die **Toolbox** in ein Formular oder Containersteuerelement.</span><span class="sxs-lookup"><span data-stu-id="fc59b-106">Drag a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="fc59b-107">Ziehen Sie die Größe und Position Handles auf Größe, und platzieren Sie das Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="fc59b-107">Drag the sizing and position handles to size and position the control.</span></span>  
  
     <span data-ttu-id="fc59b-108">Sie können auch die Größe und position des Steuerelements durch Ändern der **Größe** und **Position** Eigenschaften im Eigenschaftenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fc59b-108">You can also size and position the control by changing the **Size** and **Position** properties in the Properties window.</span></span>  
  
3.  <span data-ttu-id="fc59b-109">Fügen Sie mindestens ein vom datengebundenen Steuerelement, das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="fc59b-109">Add at least one data-bound control to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="fc59b-110">Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen von gebundenen Daten in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="fc59b-110">For more information, see [How to: Display Bound Data in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md).</span></span>  
  
4.  <span data-ttu-id="fc59b-111">Ziehen Sie ein Steuerelement aus der **Toolbox** in den Elementvorlagenbereich von der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="fc59b-111">Drag a control from the **Toolbox** onto the item template region of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="fc59b-112">Beachten Sie, dass das Steuerelement über zwei rechteckige Bereiche verfügt.</span><span class="sxs-lookup"><span data-stu-id="fc59b-112">Note that the control has two rectangular regions.</span></span> <span data-ttu-id="fc59b-113">Der innere Bereich ist die *Elementvorlage*; Steuerelemente hinzugefügt werden, auf die Vorlage werden in jedem Element im wiederholt die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="fc59b-113">The inner region is the *item template*; controls added to the template will be repeated in each item in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control at run time.</span></span> <span data-ttu-id="fc59b-114">Die äußere Region ist die *Viewport*, in denen die Elemente angezeigt, Steuerelemente, die in dieser Region hinzugefügt haben, werden nicht zur Laufzeit angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fc59b-114">The outer region is the *viewport*, where the items will be displayed; controls that are added to this region will not be displayed at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc59b-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc59b-115">See also</span></span>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>
- [<span data-ttu-id="fc59b-116">Einführung in das DataRepeater-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="fc59b-116">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="fc59b-117">Problembehandlung beim DataRepeater-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="fc59b-117">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="fc59b-118">Vorgehensweise: Anzeigen von gebundenen Daten in einem DataRepeater-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="fc59b-118">How to: Display Bound Data in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="fc59b-119">Vorgehensweise: Erstellen Sie eine Master-/Detailformulars mit zwei DataRepeater-Steuerelementen (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="fc59b-119">How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)
- [<span data-ttu-id="fc59b-120">Vorgehensweise: Ändern der Darstellung eines DataRepeater-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="fc59b-120">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
