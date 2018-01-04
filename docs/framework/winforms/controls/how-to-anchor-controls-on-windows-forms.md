---
title: "Gewusst wie: Verankern von Steuerelementen in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Anchor property [Windows Forms], enabling resizable forms
- Windows Forms controls, screen resolutions
- resizing forms [Windows Forms]
- Windows Forms controls, size
- screen resolution and control display
- controls [Windows Forms], anchoring
- forms [Windows Forms], resizing
- Windows Forms, resizing
- controls [Windows Forms], positioning
ms.assetid: 59ea914f-fbd3-427a-80fe-decd02f7ae6d
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7fcc672dea63bc74980b4829129f530de9cc72ec
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-anchor-controls-on-windows-forms"></a><span data-ttu-id="5c544-102">Gewusst wie: Verankern von Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5c544-102">How to: Anchor Controls on Windows Forms</span></span>
<span data-ttu-id="5c544-103">Wenn Sie ein Formular entwerfen, die der Benutzer zur Laufzeit ändern kann, sollten die Steuerelemente im Formular Größe und ordnungsgemäß neu zu positionieren.</span><span class="sxs-lookup"><span data-stu-id="5c544-103">If you are designing a form that the user can resize at run time, the controls on your form should resize and reposition properly.</span></span> <span data-ttu-id="5c544-104">Zum Ändern der Größe von Steuerelementen dynamisch mit dem Formular können Sie die <xref:System.Windows.Forms.Control.Anchor%2A> Eigenschaft von Windows Forms-Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="5c544-104">To resize controls dynamically with the form, you can use the <xref:System.Windows.Forms.Control.Anchor%2A> property of Windows Forms controls.</span></span> <span data-ttu-id="5c544-105">Die <xref:System.Windows.Forms.Control.Anchor%2A> -Eigenschaft definiert ein Ankerposition für das Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="5c544-105">The <xref:System.Windows.Forms.Control.Anchor%2A> property defines an anchor position for the control.</span></span> <span data-ttu-id="5c544-106">Wenn ein Steuerelement einem Formular verankert ist und der Größe des Formulars, behält das Steuerelement den Abstand zwischen dem Steuerelement und dem Anker Positionen an.</span><span class="sxs-lookup"><span data-stu-id="5c544-106">When a control is anchored to a form and the form is resized, the control maintains the distance between the control and the anchor positions.</span></span> <span data-ttu-id="5c544-107">Angenommen, Sie haben eine <xref:System.Windows.Forms.TextBox> Steuerelement, das den linken, rechten und unteren Rand des Formulars verbunden ist wie die Größe des Formulars die <xref:System.Windows.Forms.TextBox> ändert die Größe horizontal steuern, sodass er die gleiche Distanz vom die rechten und linken Rand des Formulars verwaltet.</span><span class="sxs-lookup"><span data-stu-id="5c544-107">For example, if you have a <xref:System.Windows.Forms.TextBox> control that is anchored to the left, right, and bottom edges of the form, as the form is resized, the <xref:System.Windows.Forms.TextBox> control resizes horizontally so that it maintains the same distance from the right and left sides of the form.</span></span> <span data-ttu-id="5c544-108">Darüber hinaus wird das Steuerelement vertikal positioniert, sodass am Speicherort stets die gleiche Distanz vom unteren Rand des Formulars.</span><span class="sxs-lookup"><span data-stu-id="5c544-108">In addition, the control positions itself vertically so that its location is always the same distance from the bottom edge of the form.</span></span> <span data-ttu-id="5c544-109">Wenn ein Steuerelement verankert ist, und der Größe des Formulars, wird die Position des Steuerelements relativ zu den Rändern des Formulars geändert.</span><span class="sxs-lookup"><span data-stu-id="5c544-109">If a control is not anchored and the form is resized, the position of the control relative to the edges of the form is changed.</span></span>  
  
 <span data-ttu-id="5c544-110">Die <xref:System.Windows.Forms.Control.Anchor%2A> -Eigenschaft interagiert mit den <xref:System.Windows.Forms.Control.AutoSize%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="5c544-110">The <xref:System.Windows.Forms.Control.Anchor%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="5c544-111">Weitere Informationen finden Sie unter [Übersicht über die AutoSize-Eigenschaft](../../../../docs/framework/winforms/controls/autosize-property-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5c544-111">For more information, see [AutoSize Property Overview](../../../../docs/framework/winforms/controls/autosize-property-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5c544-112">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="5c544-112">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="5c544-113">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="5c544-113">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="5c544-114">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="5c544-114">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-anchor-a-control-on-a-form"></a><span data-ttu-id="5c544-115">Um ein Steuerelement in einem Formular zu verankern.</span><span class="sxs-lookup"><span data-stu-id="5c544-115">To anchor a control on a form</span></span>  
  
1.  <span data-ttu-id="5c544-116">Wählen Sie das Steuerelement, verankert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5c544-116">Select the control you want to anchor.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5c544-117">Sie können mehrere Steuerelemente, die gleichzeitig durch Drücken der STRG-Taste auf jedes Steuerelement, um ihn auszuwählen und dann folgen den Rest dieses Verfahrens verankern.</span><span class="sxs-lookup"><span data-stu-id="5c544-117">You can anchor multiple controls simultaneously by pressing the CTRL key, clicking each control to select it, and then following the rest of this procedure.</span></span>  
  
2.  <span data-ttu-id="5c544-118">In der **Eigenschaften** Fenster, klicken Sie auf den Pfeil rechts neben der <xref:System.Windows.Forms.Control.Anchor%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="5c544-118">In the **Properties** window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Anchor%2A> property.</span></span>  
  
     <span data-ttu-id="5c544-119">Ein Editor wird angezeigt, in der ein Kreuz angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5c544-119">An editor is displayed that shows a cross.</span></span>  
  
3.  <span data-ttu-id="5c544-120">Um einen Anker festzulegen, klicken Sie auf die oben, links, rechts oder unten im Abschnitt die kreuzfilterrichtung.</span><span class="sxs-lookup"><span data-stu-id="5c544-120">To set an anchor, click the top, left, right, or bottom section of the cross.</span></span>  
  
     <span data-ttu-id="5c544-121">Steuerelemente sind oben verankert und wird standardmäßig links.</span><span class="sxs-lookup"><span data-stu-id="5c544-121">Controls are anchored to the top and left by default.</span></span>  
  
4.  <span data-ttu-id="5c544-122">Um eine Seite des Steuerelements zu löschen, die verankert wurde, klicken Sie auf diese Arm für die kreuzfilterrichtung.</span><span class="sxs-lookup"><span data-stu-id="5c544-122">To clear a side of the control that has been anchored, click that arm of the cross.</span></span>  
  
5.  <span data-ttu-id="5c544-123">Schließen der <xref:System.Windows.Forms.Control.Anchor%2A> Eigenschaften-Editor, klicken Sie auf die <xref:System.Windows.Forms.Control.Anchor%2A> Eigenschaftsname erneut aus.</span><span class="sxs-lookup"><span data-stu-id="5c544-123">To close the <xref:System.Windows.Forms.Control.Anchor%2A> property editor, click the <xref:System.Windows.Forms.Control.Anchor%2A> property name again.</span></span>  
  
 <span data-ttu-id="5c544-124">Wenn das Formular zur Laufzeit angezeigt wird, wird das Steuerelement an die gleiche Distanz vom Rand des Formulars positioniert bleiben.</span><span class="sxs-lookup"><span data-stu-id="5c544-124">When your form is displayed at run time, the control resizes to remain positioned at the same distance from the edge of the form.</span></span> <span data-ttu-id="5c544-125">Der Abstand zwischen dem verankerten bleibt dasselbe immer, wie der Abstand definiert, wenn das Steuerelement in Windows Forms-Designer positioniert ist.</span><span class="sxs-lookup"><span data-stu-id="5c544-125">The distance from the anchored edge always remains the same as the distance defined when the control is positioned in the Windows Forms Designer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5c544-126">Bestimmte Steuerelemente, z. B. die <xref:System.Windows.Forms.ComboBox> steuern, besteht ein Limit, der Höhe.</span><span class="sxs-lookup"><span data-stu-id="5c544-126">Certain controls, such as the <xref:System.Windows.Forms.ComboBox> control, have a limit to their height.</span></span> <span data-ttu-id="5c544-127">Verankern das Steuerelement an das Ende seiner Formular oder Containersteuerelement kann nicht das Steuerelement seine Höhe überschreiten erzwingen.</span><span class="sxs-lookup"><span data-stu-id="5c544-127">Anchoring the control to the bottom of its form or container cannot force the control to exceed its height limit.</span></span>  
  
 <span data-ttu-id="5c544-128">Geerbte Steuerelemente muss `Protected` verankert werden können.</span><span class="sxs-lookup"><span data-stu-id="5c544-128">Inherited controls must be `Protected` to be able to be anchored.</span></span> <span data-ttu-id="5c544-129">Um die Zugriffsebene eines Steuerelements zu ändern, legen Sie dessen `Modifiers` Eigenschaft in der **Eigenschaften** Fenster.</span><span class="sxs-lookup"><span data-stu-id="5c544-129">To change the access level of a control, set its `Modifiers` property in the **Properties** window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c544-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5c544-130">See Also</span></span>  
 [<span data-ttu-id="5c544-131">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="5c544-131">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="5c544-132">Anordnen von Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5c544-132">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="5c544-133">Übersicht über die AutoSize-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5c544-133">AutoSize Property Overview</span></span>](../../../../docs/framework/winforms/controls/autosize-property-overview.md)  
 [<span data-ttu-id="5c544-134">Gewusst wie: Andocken von Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5c544-134">How to: Dock Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md)  
 [<span data-ttu-id="5c544-135">Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="5c544-135">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [<span data-ttu-id="5c544-136">Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="5c544-136">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [<span data-ttu-id="5c544-137">Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen mithilfe von Abständen, Rändern und der AutoSize-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5c544-137">Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)
