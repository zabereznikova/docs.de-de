---
title: Anordnen von WPF-Inhalt auf Windows Forms zur Entwurfszeit
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- WPF user control [Windows Forms], hosting in a layout panel
- WPF content [Windows Forms], arranging at design time
- Windows Forms, arranging WPF content at design time
- WPF content [Windows Forms], hosting in Windows Forms
- Windows Forms, anchoring and docking WPF content
- interoperability [WPF]
ms.assetid: 5efb1c53-1484-43d6-aa8a-f4861b99bb8a
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 5a6b12def45052e117fb149555946ea42d6cd3c2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746815"
---
# <a name="walkthrough-arrange-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="0c226-102">Exemplarische Vorgehensweise: Anordnen von WPF-Inhalt auf Windows Forms zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="0c226-102">Walkthrough: Arrange WPF content on Windows Forms at design time</span></span>

<span data-ttu-id="0c226-103">In diesem Artikel erfahren Sie, wie Sie die Windows Forms Layoutfeatures, wie z. b. das verankern und ausrichten, verwenden, um Windows Presentation Foundation (WPF)-Steuerelemente anzuordnen.</span><span class="sxs-lookup"><span data-stu-id="0c226-103">This article shows you how to use the Windows Forms layout features, such as anchoring and snaplines, to arrange Windows Presentation Foundation (WPF) controls.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0c226-104">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="0c226-104">Prerequisites</span></span>

<span data-ttu-id="0c226-105">Für diese exemplarische Vorgehensweise benötigen Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0c226-105">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="0c226-106">Erstellen eines Projekts</span><span class="sxs-lookup"><span data-stu-id="0c226-106">Create the project</span></span>

<span data-ttu-id="0c226-107">Öffnen Sie Visual Studio, und erstellen Sie ein neues Windows Forms-Anwendungsprojekt C# in Visual Basic oder Visual mit dem Namen `ArrangeElementHost`.</span><span class="sxs-lookup"><span data-stu-id="0c226-107">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `ArrangeElementHost`.</span></span>

> [!NOTE]
> <span data-ttu-id="0c226-108">Beim Hosten von WPF-Inhalt werden nur C#- und Visual Basic-Projekte unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0c226-108">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control"></a><span data-ttu-id="0c226-109">Erstellen des WPF-Steuer Elements</span><span class="sxs-lookup"><span data-stu-id="0c226-109">Create the WPF control</span></span>

<span data-ttu-id="0c226-110">Nachdem Sie dem Projekt ein WPF-Steuerelement hinzugefügt haben, können Sie dieses auf dem Formular anordnen.</span><span class="sxs-lookup"><span data-stu-id="0c226-110">After you add a WPF control to the project, you can arrange it on the form.</span></span>

1. <span data-ttu-id="0c226-111">Fügen Sie dem Projekt ein neues WPF-<xref:System.Windows.Controls.UserControl>-Objekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="0c226-111">Add a new WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="0c226-112">Verwenden Sie den Standardnamen, `UserControl1.xaml`, für den Steuerelementtyp.</span><span class="sxs-lookup"><span data-stu-id="0c226-112">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="0c226-113">Weitere Informationen finden Sie unter Exemplarische Vorgehensweise [: Erstellen eines neuen WPF-Inhalts auf Windows Forms zur Entwurfszeit](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="0c226-113">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="0c226-114">Stellen Sie in der Entwurfsansicht sicher, dass `UserControl1` ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="0c226-114">In Design view, make sure that `UserControl1` is selected.</span></span>

3. <span data-ttu-id="0c226-115">Legen Sie im Fenster **Eigenschaften** den Wert der Eigenschaften <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> auf **200**fest.</span><span class="sxs-lookup"><span data-stu-id="0c226-115">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="0c226-116">Legen Sie den Wert der <xref:System.Windows.Controls.Control.Background%2A>-Eigenschaft auf **Blue**fest.</span><span class="sxs-lookup"><span data-stu-id="0c226-116">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to **Blue**.</span></span>

5. <span data-ttu-id="0c226-117">Erstellen Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="0c226-117">Build the project.</span></span>

## <a name="host-wpf-controls-in-a-layout-panel"></a><span data-ttu-id="0c226-118">WPF-Steuerelemente in einem Layoutpanel hosten</span><span class="sxs-lookup"><span data-stu-id="0c226-118">Host WPF controls in a layout panel</span></span>

<span data-ttu-id="0c226-119">Sie können WPF-Steuerelemente in Layoutbereichen auf die gleiche Weise verwenden wie andere Windows Forms-Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="0c226-119">You can use WPF controls in layout panels in the same way you use other Windows Forms controls.</span></span>

1. <span data-ttu-id="0c226-120">Öffnen Sie `Form1` im Windows Forms-Designer.</span><span class="sxs-lookup"><span data-stu-id="0c226-120">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="0c226-121">Ziehen Sie ein <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement in der **Toolbox**auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="0c226-121">In the **Toolbox**, drag a <xref:System.Windows.Forms.TableLayoutPanel> control onto the form.</span></span>

3. <span data-ttu-id="0c226-122">Wählen Sie im Smarttagbereich des <xref:System.Windows.Forms.TableLayoutPanel> Steuer Elements **letzte Zeile entfernen**aus.</span><span class="sxs-lookup"><span data-stu-id="0c226-122">On the <xref:System.Windows.Forms.TableLayoutPanel> control's smart tag panel, select **Remove Last Row**.</span></span>

4. <span data-ttu-id="0c226-123">Ändern Sie die Größe des <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelements, sodass es breiter und höher wird.</span><span class="sxs-lookup"><span data-stu-id="0c226-123">Resize the <xref:System.Windows.Forms.TableLayoutPanel> control to a larger width and height.</span></span>

5. <span data-ttu-id="0c226-124">Doppelklicken Sie in der **Toolbox**auf `UserControl1`, um in der ersten Zelle des <xref:System.Windows.Forms.TableLayoutPanel>-Steuer Elements eine Instanz von `UserControl1` zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0c226-124">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` in the first cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

   <span data-ttu-id="0c226-125">Die Instanz von `UserControl1` wird in einem neuen <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement namens `elementHost1` gehostet.</span><span class="sxs-lookup"><span data-stu-id="0c226-125">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

6. <span data-ttu-id="0c226-126">Doppelklicken Sie in der **Toolbox**auf `UserControl1`, um eine weitere Instanz in der zweiten Zelle des <xref:System.Windows.Forms.TableLayoutPanel> Steuer Elements zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0c226-126">In the **Toolbox**, double-click `UserControl1` to create another instance in the second cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

7. <span data-ttu-id="0c226-127">Wählen Sie im Fenster **Dokument** Gliederung die Option `tableLayoutPanel1`aus.</span><span class="sxs-lookup"><span data-stu-id="0c226-127">In the **Document Outline** window, select `tableLayoutPanel1`.</span></span>

8. <span data-ttu-id="0c226-128">Legen Sie im Fenster **Eigenschaften** den Wert der <xref:System.Windows.Forms.Control.Padding%2A>-Eigenschaft auf **10, 10, 10, 10**fest.</span><span class="sxs-lookup"><span data-stu-id="0c226-128">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Padding%2A> property to **10, 10, 10, 10**.</span></span>

   <span data-ttu-id="0c226-129">Die Größe beider <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelemente wird entsprechend dem neuen Layout angepasst.</span><span class="sxs-lookup"><span data-stu-id="0c226-129">Both <xref:System.Windows.Forms.Integration.ElementHost> controls are resized to fit into the new layout.</span></span>

## <a name="use-snaplines-to-align-wpf-controls"></a><span data-ttu-id="0c226-130">Verwenden von Ausrichtungs Linien zum Ausrichten von WPF-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="0c226-130">Use snaplines to align WPF controls</span></span>

<span data-ttu-id="0c226-131">Ausrichtungslinien erleichtern die Ausrichtung von Steuerelementen auf einem Formular.</span><span class="sxs-lookup"><span data-stu-id="0c226-131">Snaplines enable easy alignment of controls on a form.</span></span> <span data-ttu-id="0c226-132">Sie können Ausrichtungslinien auch verwenden, um WPF-Steuerelemente auszurichten.</span><span class="sxs-lookup"><span data-stu-id="0c226-132">You can use snaplines to align your WPF controls as well.</span></span> <span data-ttu-id="0c226-133">Weitere Informationen finden Sie unter Exemplarische Vorgehensweise [: Anordnen von Steuerelementen auf Windows Forms mithilfe](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)von Ausrichtungs Linien.</span><span class="sxs-lookup"><span data-stu-id="0c226-133">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>

1. <span data-ttu-id="0c226-134">Ziehen Sie aus der **Toolbox**eine Instanz von `UserControl1` auf das Formular, und platzieren Sie Sie in dem Bereich unterhalb des <xref:System.Windows.Forms.TableLayoutPanel> Steuer Elements.</span><span class="sxs-lookup"><span data-stu-id="0c226-134">From the **Toolbox**, drag an instance of `UserControl1` onto the form, and place it in the space beneath the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

   <span data-ttu-id="0c226-135">Die Instanz von `UserControl1` wird in einem neuen <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement namens `elementHost3` gehostet.</span><span class="sxs-lookup"><span data-stu-id="0c226-135">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost3`.</span></span>

2. <span data-ttu-id="0c226-136">Richten Sie den linken Rand von `elementHost3` mithilfe der Ausrichtungslinien am linken Rand des <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelements aus.</span><span class="sxs-lookup"><span data-stu-id="0c226-136">Using snaplines, align the left edge of `elementHost3` with the left edge of <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

3. <span data-ttu-id="0c226-137">Legen Sie die Breite von `elementHost3` mithilfe der Ausrichtungslinien auf dieselbe Breite wie das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement fest.</span><span class="sxs-lookup"><span data-stu-id="0c226-137">Using snaplines, size `elementHost3` to the same width as the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

4. <span data-ttu-id="0c226-138">Verschieben Sie `elementHost3` in Richtung des <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelements,  steuern, bis zwischen den Steuerelementen eine mittige Ausrichtungslinie angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0c226-138">Move `elementHost3` toward the <xref:System.Windows.Forms.TableLayoutPanel> control until a center snapline appears between the controls.</span></span>

5. <span data-ttu-id="0c226-139">Legen Sie im Fenster **Eigenschaften** den Wert der Margin-Eigenschaft auf **20, 20, 20, 20**fest.</span><span class="sxs-lookup"><span data-stu-id="0c226-139">In the **Properties** window, set the value of the Margin property to **20, 20, 20, 20**.</span></span>

6. <span data-ttu-id="0c226-140">Verschieben Sie `elementHost3` vom <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement weg, bis die mittige Ausrichtungslinie erneut angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0c226-140">Move the `elementHost3` away from the <xref:System.Windows.Forms.TableLayoutPanel> control until the center snapline appears again.</span></span> <span data-ttu-id="0c226-141">Die mittige Ausrichtungslinie kennzeichnet jetzt einen Rand von 20.</span><span class="sxs-lookup"><span data-stu-id="0c226-141">The center snapline now indicates a margin of 20.</span></span>

7. <span data-ttu-id="0c226-142">Verschieben Sie `elementHost3` nach rechts, bis der linke Rand am linken Rand des `elementHost1`ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="0c226-142">Move `elementHost3` to the right until its left edge aligns with the left edge of `elementHost1`.</span></span>

8. <span data-ttu-id="0c226-143">Ändern Sie die Breite von `elementHost3` bis dessen rechter Rand am rechten Rand von `elementHost2` ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="0c226-143">Change the width of `elementHost3` until its right edge aligns with the right edge of `elementHost2`.</span></span>

## <a name="anchor-and-dock-wpf-controls"></a><span data-ttu-id="0c226-144">WPF-Steuerelemente verankern und Andocken</span><span class="sxs-lookup"><span data-stu-id="0c226-144">Anchor and dock WPF controls</span></span>

<span data-ttu-id="0c226-145">Ein auf einem Formular gehostetes WPF-Steuerelement hat dasselbe Verankerungs- und Andockverhalten auf wie andere Windows Forms-Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="0c226-145">A WPF control hosted on a form has the same anchoring and docking behavior as other Windows Forms controls.</span></span>

1. <span data-ttu-id="0c226-146">Klicken Sie auf `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="0c226-146">Select `elementHost1`.</span></span>

2. <span data-ttu-id="0c226-147">Legen Sie im Fenster **Eigenschaften** die <xref:System.Windows.Forms.Control.Anchor%2A>-Eigenschaft auf **oben, unten, Links und rechts**fest.</span><span class="sxs-lookup"><span data-stu-id="0c226-147">In the **Properties** window, set the <xref:System.Windows.Forms.Control.Anchor%2A> property to **Top, Bottom, Left, Right**.</span></span>

3. <span data-ttu-id="0c226-148">Vergrößern Sie das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0c226-148">Resize the <xref:System.Windows.Forms.TableLayoutPanel> control to a larger size.</span></span>

   <span data-ttu-id="0c226-149">Die Größe des `elementHost1`-Steuerelements wird geändert, sodass es die Zelle ausfüllt.</span><span class="sxs-lookup"><span data-stu-id="0c226-149">The `elementHost1` control resizes to fill the cell.</span></span>

4. <span data-ttu-id="0c226-150">Klicken Sie auf `elementHost2`.</span><span class="sxs-lookup"><span data-stu-id="0c226-150">Select `elementHost2`.</span></span>

5. <span data-ttu-id="0c226-151">Legen Sie im Fenster **Eigenschaften** den Wert der <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft auf <xref:System.Windows.Forms.DockStyle.Fill>fest.</span><span class="sxs-lookup"><span data-stu-id="0c226-151">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

   <span data-ttu-id="0c226-152">Die Größe des `elementHost2`-Steuerelements wird geändert, sodass es die Zelle ausfüllt.</span><span class="sxs-lookup"><span data-stu-id="0c226-152">The `elementHost2` control resizes to fill the cell.</span></span>

6. <span data-ttu-id="0c226-153">Wählen Sie das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0c226-153">Select the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

7. <span data-ttu-id="0c226-154">Legen Sie den Wert von dessen <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft auf <xref:System.Windows.Forms.DockStyle.Top> fest.</span><span class="sxs-lookup"><span data-stu-id="0c226-154">Set the value of its <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Top>.</span></span>

8. <span data-ttu-id="0c226-155">Klicken Sie auf `elementHost3`.</span><span class="sxs-lookup"><span data-stu-id="0c226-155">Select `elementHost3`.</span></span>

9. <span data-ttu-id="0c226-156">Legen Sie den Wert von dessen <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft auf <xref:System.Windows.Forms.DockStyle.Fill> fest.</span><span class="sxs-lookup"><span data-stu-id="0c226-156">Set the value of its <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

   <span data-ttu-id="0c226-157">Die Größe des `elementHost3`-Steuerelements wird so geändert, dass es den verbleibenden Platz auf dem Formular ausfüllt.</span><span class="sxs-lookup"><span data-stu-id="0c226-157">The `elementHost3` control resizes to fill the remaining space on the form.</span></span>

10. <span data-ttu-id="0c226-158">Ändern Sie die Größe des Formulars.</span><span class="sxs-lookup"><span data-stu-id="0c226-158">Resize the form.</span></span>

    <span data-ttu-id="0c226-159">Die Größen aller drei <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelemente werden entsprechend angepasst.</span><span class="sxs-lookup"><span data-stu-id="0c226-159">All three <xref:System.Windows.Forms.Integration.ElementHost> controls resize appropriately.</span></span>

    <span data-ttu-id="0c226-160">Weitere Informationen finden Sie unter Gewusst [wie: verankern und Andocken von untergeordneten Steuerelementen in einem TableLayoutPanel-Steuer](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)Element.</span><span class="sxs-lookup"><span data-stu-id="0c226-160">For more information, see [How to: Anchor and Dock Child Controls in a TableLayoutPanel Control](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0c226-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0c226-161">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="0c226-162">Gewusst wie: Verankern und Andocken von untergeordneten Steuerelementen in einem TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="0c226-162">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="0c226-163">Gewusst wie: Ausrichten eines Steuerelements an den Rändern eines Formulars zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="0c226-163">How to: Align a Control to the Edges of Forms at Design Time</span></span>](../controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)
- [<span data-ttu-id="0c226-164">Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien</span><span class="sxs-lookup"><span data-stu-id="0c226-164">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="0c226-165">Migration und Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="0c226-165">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="0c226-166">Verwenden von WPF-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="0c226-166">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="0c226-167">Entwerfen von XAML-Code in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0c226-167">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
