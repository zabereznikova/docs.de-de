---
title: Verankern von Steuerelementen
ms.date: 03/30/2017
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
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 7c307d8c5b3bc32e15e6de048c434854ef1bbc65
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747182"
---
# <a name="how-to-anchor-controls-on-windows-forms"></a><span data-ttu-id="701c0-102">Gewusst wie: Verankern von Steuerelementen auf Windows Forms</span><span class="sxs-lookup"><span data-stu-id="701c0-102">How to: Anchor controls on Windows Forms</span></span>

<span data-ttu-id="701c0-103">Wenn Sie ein Formular entwerfen, in dem der Benutzer zur Laufzeit die Größe ändern kann, sollten die Steuerelemente auf dem Formular die Größe ändern und die Position ordnungsgemäß ändern.</span><span class="sxs-lookup"><span data-stu-id="701c0-103">If you're designing a form that the user can resize at run time, the controls on your form should resize and reposition properly.</span></span> <span data-ttu-id="701c0-104">Um die Größe der Steuerelemente dynamisch mit dem Formular zu ändern, können Sie die <xref:System.Windows.Forms.Control.Anchor%2A>-Eigenschaft Windows Forms Steuerelementen verwenden.</span><span class="sxs-lookup"><span data-stu-id="701c0-104">To resize controls dynamically with the form, you can use the <xref:System.Windows.Forms.Control.Anchor%2A> property of Windows Forms controls.</span></span> <span data-ttu-id="701c0-105">Die <xref:System.Windows.Forms.Control.Anchor%2A>-Eigenschaft definiert eine Ankerposition für das-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="701c0-105">The <xref:System.Windows.Forms.Control.Anchor%2A> property defines an anchor position for the control.</span></span> <span data-ttu-id="701c0-106">Wenn ein Steuerelement in einem Formular verankert ist und die Größe des Formulars geändert wird, behält das Steuerelement den Abstand zwischen dem Steuerelement und den Anker Positionen.</span><span class="sxs-lookup"><span data-stu-id="701c0-106">When a control is anchored to a form and the form is resized, the control maintains the distance between the control and the anchor positions.</span></span> <span data-ttu-id="701c0-107">Wenn Sie z. b. über ein <xref:System.Windows.Forms.TextBox> Steuerelement verfügen, das am linken, rechten und unteren Rand des Formulars verankert ist, während die Größe des Formulars geändert wird, ändert sich das <xref:System.Windows.Forms.TextBox> Steuerelement horizontal, sodass es die gleiche Entfernung von der rechten und linken Seite des Formulars erhält.</span><span class="sxs-lookup"><span data-stu-id="701c0-107">For example, if you have a <xref:System.Windows.Forms.TextBox> control that is anchored to the left, right, and bottom edges of the form, as the form is resized, the <xref:System.Windows.Forms.TextBox> control resizes horizontally so that it maintains the same distance from the right and left sides of the form.</span></span> <span data-ttu-id="701c0-108">Außerdem positioniert sich das Steuerelement selbst vertikal, sodass seine Position immer die gleiche Entfernung vom unteren Rand des Formulars ist.</span><span class="sxs-lookup"><span data-stu-id="701c0-108">In addition, the control positions itself vertically so that its location is always the same distance from the bottom edge of the form.</span></span> <span data-ttu-id="701c0-109">Wenn ein Steuerelement nicht verankert ist und die Größe des Formulars geändert wird, wird die Position des Steuer Elements relativ zu den Rändern des Formulars geändert.</span><span class="sxs-lookup"><span data-stu-id="701c0-109">If a control is not anchored and the form is resized, the position of the control relative to the edges of the form is changed.</span></span>

<span data-ttu-id="701c0-110">Die <xref:System.Windows.Forms.Control.Anchor%2A>-Eigenschaft interagiert mit der <xref:System.Windows.Forms.Control.AutoSize%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="701c0-110">The <xref:System.Windows.Forms.Control.Anchor%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="701c0-111">Weitere Informationen finden Sie unter [Übersicht über die AutoSize-Eigenschaft](autosize-property-overview.md).</span><span class="sxs-lookup"><span data-stu-id="701c0-111">For more information, see [AutoSize Property Overview](autosize-property-overview.md).</span></span>

## <a name="anchor-a-control-on-a-form"></a><span data-ttu-id="701c0-112">Verankern eines Steuer Elements in einem Formular</span><span class="sxs-lookup"><span data-stu-id="701c0-112">Anchor a control on a form</span></span>

1. <span data-ttu-id="701c0-113">Wählen Sie in Visual Studio das Steuerelement aus, das Sie verankern möchten.</span><span class="sxs-lookup"><span data-stu-id="701c0-113">In Visual Studio, select the control you want to anchor.</span></span>

    > [!NOTE]
    > <span data-ttu-id="701c0-114">Sie können mehrere Steuerelemente gleichzeitig verankern, indem Sie die STRG-Taste drücken, auf jedes Steuerelement klicken, um es auszuwählen, und dann die restlichen Schritte dieses Verfahrens ausführen.</span><span class="sxs-lookup"><span data-stu-id="701c0-114">You can anchor multiple controls simultaneously by pressing the CTRL key, clicking each control to select it, and then following the rest of this procedure.</span></span>

2. <span data-ttu-id="701c0-115">Klicken Sie im **Eigenschaften** Fenster auf den Pfeil rechts neben der <xref:System.Windows.Forms.Control.Anchor%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="701c0-115">In the **Properties** window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Anchor%2A> property.</span></span>

     <span data-ttu-id="701c0-116">Es wird ein Editor angezeigt, der eine Kreuz Darstellung anzeigt.</span><span class="sxs-lookup"><span data-stu-id="701c0-116">An editor is displayed that shows a cross.</span></span>

3. <span data-ttu-id="701c0-117">Um einen Anker festzulegen, klicken Sie auf den oberen, linken, rechten oder unteren Abschnitt des Kreuz-.</span><span class="sxs-lookup"><span data-stu-id="701c0-117">To set an anchor, click the top, left, right, or bottom section of the cross.</span></span>

     <span data-ttu-id="701c0-118">Steuerelemente werden standardmäßig oben und Links verankert.</span><span class="sxs-lookup"><span data-stu-id="701c0-118">Controls are anchored to the top and left by default.</span></span>

4. <span data-ttu-id="701c0-119">Um eine Seite des verankerten Steuer Elements zu löschen, klicken Sie auf den Arm des Kreuz-.</span><span class="sxs-lookup"><span data-stu-id="701c0-119">To clear a side of the control that has been anchored, click that arm of the cross.</span></span>

5. <span data-ttu-id="701c0-120">Um den Eigenschaften-Editor für <xref:System.Windows.Forms.Control.Anchor%2A> zu schließen, klicken Sie erneut auf den Eigenschaften Namen <xref:System.Windows.Forms.Control.Anchor%2A>.</span><span class="sxs-lookup"><span data-stu-id="701c0-120">To close the <xref:System.Windows.Forms.Control.Anchor%2A> property editor, click the <xref:System.Windows.Forms.Control.Anchor%2A> property name again.</span></span>

<span data-ttu-id="701c0-121">Wenn das Formular zur Laufzeit angezeigt wird, wird die Größe des Steuer Elements so geändert, dass es in der gleichen Entfernung vom Rand des Formulars positioniert bleibt.</span><span class="sxs-lookup"><span data-stu-id="701c0-121">When your form is displayed at run time, the control resizes to remain positioned at the same distance from the edge of the form.</span></span> <span data-ttu-id="701c0-122">Der Abstand vom verankerten Rand bleibt immer identisch mit dem Abstand, der definiert wird, wenn das Steuerelement im Windows Forms-Designer positioniert ist.</span><span class="sxs-lookup"><span data-stu-id="701c0-122">The distance from the anchored edge always remains the same as the distance defined when the control is positioned in the Windows Forms Designer.</span></span>

> [!NOTE]
> <span data-ttu-id="701c0-123">Bestimmte Steuerelemente, wie z. b. das <xref:System.Windows.Forms.ComboBox>-Steuerelement, haben eine Begrenzung der Höhe.</span><span class="sxs-lookup"><span data-stu-id="701c0-123">Certain controls, such as the <xref:System.Windows.Forms.ComboBox> control, have a limit to their height.</span></span> <span data-ttu-id="701c0-124">Wenn das Steuerelement am unteren Rand des Formulars oder Containers verankert wird, kann das Steuerelement das Höhen Limit nicht überschreiten.</span><span class="sxs-lookup"><span data-stu-id="701c0-124">Anchoring the control to the bottom of its form or container cannot force the control to exceed its height limit.</span></span>

<span data-ttu-id="701c0-125">Geerbte Steuerelemente müssen `Protected` werden, um verankert werden zu können.</span><span class="sxs-lookup"><span data-stu-id="701c0-125">Inherited controls must be `Protected` to be able to be anchored.</span></span> <span data-ttu-id="701c0-126">Um die Zugriffsebene eines Steuer Elements zu ändern, legen Sie dessen `Modifiers`-Eigenschaft im **Eigenschaften** Fenster fest.</span><span class="sxs-lookup"><span data-stu-id="701c0-126">To change the access level of a control, set its `Modifiers` property in the **Properties** window.</span></span>

## <a name="see-also"></a><span data-ttu-id="701c0-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="701c0-127">See also</span></span>

- [<span data-ttu-id="701c0-128">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="701c0-128">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="701c0-129">Übersicht über die AutoSize-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="701c0-129">AutoSize Property Overview</span></span>](autosize-property-overview.md)
- [<span data-ttu-id="701c0-130">Gewusst wie: Andocken von Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="701c0-130">How to: Dock Controls on Windows Forms</span></span>](how-to-dock-controls-on-windows-forms.md)
- [<span data-ttu-id="701c0-131">Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="701c0-131">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="701c0-132">Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="701c0-132">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="701c0-133">Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen mithilfe von Abständen, Rändern und der AutoSize-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="701c0-133">Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property</span></span>](windows-forms-controls-padding-autosize.md)
