---
title: 'Gewusst wie: Anzeigen von nicht gebundenen Steuerelementen in einem DataRepeater-Steuerelement (Visual Studio)'
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, adding unbound controls
- DataRepeater
- displaying unbound data
ms.assetid: f234fa40-5a13-4209-930e-7c5f81e86e66
ms.openlocfilehash: 698e518a4ed10ed6cf14ccafc6833b1acf8752db
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588105"
---
# <a name="how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio"></a><span data-ttu-id="79296-102">Gewusst wie: Anzeigen von nicht gebundenen Steuerelementen in einem DataRepeater-Steuerelement (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="79296-102">How to: Display Unbound Controls in a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="79296-103">Zusätzlich zur gebundene Steuerelemente möchten Sie möglicherweise andere Steuerelemente zum Hinzufügen einer <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, z. B. eine statische Bezeichnung oder ein Bild, das wiederholt wird, für jedes Element in der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="79296-103">In addition to bound controls, you may want to add other controls to a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, such as a static label or an image that is repeated on each item in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="79296-104">Außerdem benötigen Sie mindestens ein gebundenes Steuerelement auf die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> oder nichts wird zur Laufzeit angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="79296-104">You must also have at least one bound control on the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> or nothing will be displayed at run time.</span></span>  
  
### <a name="to-add-unbound-controls-to-a-datarepeater"></a><span data-ttu-id="79296-105">Hinzufügen von nicht gebundenen Steuerelementen zu einem DataRepeater</span><span class="sxs-lookup"><span data-stu-id="79296-105">To add unbound controls to a DataRepeater</span></span>  
  
1.  <span data-ttu-id="79296-106">Ziehen Sie eine <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement aus der **Visual Basic PowerPacks** Registerkarte der **Toolbox** in einem Formular oder Containersteuerelement.</span><span class="sxs-lookup"><span data-stu-id="79296-106">Drag a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="79296-107">Größe der Größe und Position Ziehpunkte, und positionieren Sie das Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="79296-107">Drag the sizing and position handles to size and position the control.</span></span>  
  
     <span data-ttu-id="79296-108">Sie können auch die Größe und position des Steuerelements durch Ändern der **Größe** und **Position** Eigenschaften im Eigenschaftenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="79296-108">You can also size and position the control by changing the **Size** and **Position** properties in the Properties window.</span></span>  
  
3.  <span data-ttu-id="79296-109">Fügen Sie mindestens ein datengebundenes Steuerelement auf die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="79296-109">Add at least one data-bound control to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="79296-110">Weitere Informationen finden Sie unter [Vorgehensweise: Anzeige von gebundenen Daten in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="79296-110">For more information, see [How to: Display Bound Data in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md).</span></span>  
  
4.  <span data-ttu-id="79296-111">Ziehen Sie ein Steuerelement aus der **Toolbox** in den Elementvorlagenbereich von der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="79296-111">Drag a control from the **Toolbox** onto the item template region of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="79296-112">Beachten Sie, dass das Steuerelement über zwei rechteckige Bereiche verfügt.</span><span class="sxs-lookup"><span data-stu-id="79296-112">Note that the control has two rectangular regions.</span></span> <span data-ttu-id="79296-113">Der innere Bereich ist der *Elementvorlage*; Steuerelemente hinzugefügt wurden, um die Vorlage werden in jedem Element wiederholt die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="79296-113">The inner region is the *item template*; controls added to the template will be repeated in each item in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control at run time.</span></span> <span data-ttu-id="79296-114">Der äußere Bereich ist der *Viewport*, in denen die Elemente angezeigt, da in dieser Region hinzugefügten Steuerelemente zur Laufzeit nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="79296-114">The outer region is the *viewport*, where the items will be displayed; controls that are added to this region will not be displayed at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79296-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="79296-115">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [<span data-ttu-id="79296-116">Einführung in das DataRepeater-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="79296-116">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="79296-117">Problembehandlung beim DataRepeater-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="79296-117">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="79296-118">Gewusst wie: Anzeigen von gebundenen Daten in einem DataRepeater-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="79296-118">How to: Display Bound Data in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="79296-119">Vorgehensweise: erstellen ein Master-/Detailformulars mit zwei DataRepeater-Steuerelementen (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="79296-119">How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)  
 [<span data-ttu-id="79296-120">Gewusst wie: Ändern der Darstellung eines DataRepeater-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="79296-120">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
