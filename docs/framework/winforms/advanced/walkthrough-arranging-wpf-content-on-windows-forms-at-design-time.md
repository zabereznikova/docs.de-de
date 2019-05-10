---
title: 'Exemplarische Vorgehensweise: Anordnen von WPF-Inhalt in Windows Forms zur Entwurfszeit'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF user control [Windows Forms], hosting in a layout panel
- WPF content [Windows Forms], arranging at design time
- Windows Forms, arranging WPF content at design time
- WPF content [Windows Forms], hosting in Windows Forms
- Windows Forms, anchoring and docking WPF content
- interoperability [WPF]
ms.assetid: 5efb1c53-1484-43d6-aa8a-f4861b99bb8a
ms.openlocfilehash: a8f690438136450cb12dbcf5e17ddfcca617457e
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211458"
---
# <a name="walkthrough-arrange-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="85251-102">Exemplarische Vorgehensweise: Anordnen von WPF-Inhalt in Windows Forms zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="85251-102">Walkthrough: Arrange WPF content on Windows Forms at design time</span></span>

<span data-ttu-id="85251-103">In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie die Windows Forms-Layoutfunktionen, z. B. Verankern und Ausrichtungslinien, verwendet werden können, um WPF-Steuerelemente (Windows Presentation Foundation) anzuordnen.</span><span class="sxs-lookup"><span data-stu-id="85251-103">This walkthrough shows you how to use the Windows Forms layout features, such as anchoring and snaplines, to arrange Windows Presentation Foundation (WPF) controls.</span></span>

<span data-ttu-id="85251-104">Im Verlauf dieser exemplarischen Vorgehensweise führen Sie die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="85251-104">In this walkthrough, you perform the following tasks:</span></span>

- <span data-ttu-id="85251-105">Erstellen eines Projekts</span><span class="sxs-lookup"><span data-stu-id="85251-105">Create the project.</span></span>

- <span data-ttu-id="85251-106">Erstellen des WPF-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="85251-106">Create the WPF control.</span></span>

- <span data-ttu-id="85251-107">Hosten von WPF-Steuerelementen in einem Layoutbereich</span><span class="sxs-lookup"><span data-stu-id="85251-107">Host WPF controls in a layout panel.</span></span>

- <span data-ttu-id="85251-108">Verwenden von Ausrichtungslinien zum Ausrichten von WPF-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="85251-108">Use snaplines to align WPF controls.</span></span>

- <span data-ttu-id="85251-109">Verankern und Andocken von WPF-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="85251-109">Anchor and dock WPF controls.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="85251-110">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="85251-110">Prerequisites</span></span>

<span data-ttu-id="85251-111">Für diese exemplarische Vorgehensweise benötigen Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="85251-111">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="85251-112">Erstellen eines Projekts</span><span class="sxs-lookup"><span data-stu-id="85251-112">Create the project</span></span>

<span data-ttu-id="85251-113">Öffnen Sie Visual Studio, und erstellen Sie ein neues Windows Forms-Anwendungsprojekt in Visual Basic oder Visual C# mit dem Namen `ArrangeElementHost`.</span><span class="sxs-lookup"><span data-stu-id="85251-113">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `ArrangeElementHost`.</span></span>

> [!NOTE]
> <span data-ttu-id="85251-114">Beim Hosten von WPF-Inhalt werden nur C#- und Visual Basic-Projekte unterstützt.</span><span class="sxs-lookup"><span data-stu-id="85251-114">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control"></a><span data-ttu-id="85251-115">Erstellen des WPF-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="85251-115">Create the WPF control</span></span>

<span data-ttu-id="85251-116">Nachdem Sie dem Projekt ein WPF-Steuerelement hinzugefügt haben, können Sie dieses auf dem Formular anordnen.</span><span class="sxs-lookup"><span data-stu-id="85251-116">After you add a WPF control to the project, you can arrange it on the form.</span></span>

1. <span data-ttu-id="85251-117">Fügen Sie dem Projekt ein neues WPF-<xref:System.Windows.Controls.UserControl>-Objekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="85251-117">Add a new WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="85251-118">Verwenden Sie den Standardnamen, `UserControl1.xaml`, für den Steuerelementtyp.</span><span class="sxs-lookup"><span data-stu-id="85251-118">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="85251-119">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen von neuen WPF-Inhalts in Windows Forms zur Entwurfszeit](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="85251-119">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="85251-120">Stellen Sie in der Entwurfsansicht sicher, dass `UserControl1` ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="85251-120">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="85251-121">Weitere Informationen finden Sie unter [Vorgehensweise: Wählen Sie aus, und verschieben Sie Elemente auf der Entwurfsoberfläche](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="85251-121">For more information, see [How to: Select and Move Elements on the Design Surface](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span></span>

3. <span data-ttu-id="85251-122">In der **Eigenschaften** legen den Wert des der <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften `200`.</span><span class="sxs-lookup"><span data-stu-id="85251-122">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>

4. <span data-ttu-id="85251-123">Legen Sie den Wert der <xref:System.Windows.Controls.Control.Background%2A>-Eigenschaft auf `Blue` fest.</span><span class="sxs-lookup"><span data-stu-id="85251-123">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to `Blue`.</span></span>

5. <span data-ttu-id="85251-124">Erstellen Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="85251-124">Build the project.</span></span>

## <a name="hosting-wpf-controls-in-a-layout-panel"></a><span data-ttu-id="85251-125">Hosten von WPF-Steuerelementen in einem Layoutbereich</span><span class="sxs-lookup"><span data-stu-id="85251-125">Hosting WPF Controls in a Layout Panel</span></span>
 <span data-ttu-id="85251-126">Sie können WPF-Steuerelemente in Layoutbereichen auf die gleiche Weise verwenden wie andere Windows Forms-Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="85251-126">You can use WPF controls in layout panels in the same way you use other Windows Forms controls.</span></span>

#### <a name="to-host-wpf-controls-in-a-layout-panel"></a><span data-ttu-id="85251-127">So hosten Sie WPF-Steuerelemente in einem Layoutbereich</span><span class="sxs-lookup"><span data-stu-id="85251-127">To host WPF controls in a layout panel</span></span>

1. <span data-ttu-id="85251-128">Öffnen Sie `Form1` im Windows Forms-Designer.</span><span class="sxs-lookup"><span data-stu-id="85251-128">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="85251-129">In der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="85251-129">In the **Toolbox**, drag a <xref:System.Windows.Forms.TableLayoutPanel> control onto the form.</span></span>

3. <span data-ttu-id="85251-130">Auf der <xref:System.Windows.Forms.TableLayoutPanel> des Steuerelements im Smarttagbereich auf **letzte Zeile entfernen**.</span><span class="sxs-lookup"><span data-stu-id="85251-130">On the <xref:System.Windows.Forms.TableLayoutPanel> control's smart tag panel, select **Remove Last Row**.</span></span>

4. <span data-ttu-id="85251-131">Ändern Sie die Größe des <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelements, sodass es breiter und höher wird.</span><span class="sxs-lookup"><span data-stu-id="85251-131">Resize the <xref:System.Windows.Forms.TableLayoutPanel> control to a larger width and height.</span></span>

5. <span data-ttu-id="85251-132">In der **Toolbox**, doppelklicken Sie auf `UserControl1` zum Erstellen einer Instanz von `UserControl1` in der ersten Zelle der <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="85251-132">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` in the first cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

     <span data-ttu-id="85251-133">Die Instanz von `UserControl1` wird in einem neuen <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement namens `elementHost1` gehostet.</span><span class="sxs-lookup"><span data-stu-id="85251-133">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

6. <span data-ttu-id="85251-134">In der **Toolbox**, doppelklicken Sie auf `UserControl1` zum Erstellen von einer anderen Instanz in der zweiten Zelle die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="85251-134">In the **Toolbox**, double-click `UserControl1` to create another instance in the second cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

7. <span data-ttu-id="85251-135">In der **Dokumentgliederung** wählen Sie im Fenster `tableLayoutPanel1`.</span><span class="sxs-lookup"><span data-stu-id="85251-135">In the **Document Outline** window, select `tableLayoutPanel1`.</span></span> <span data-ttu-id="85251-136">Weitere Informationen finden Sie unter [Dokumentgliederung (Fenster)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/46xf4h0w(v=vs.100)#using-the-document-outline-window-for-silverlight-and-wpf).</span><span class="sxs-lookup"><span data-stu-id="85251-136">For more information, see [Document Outline Window](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/46xf4h0w(v=vs.100)#using-the-document-outline-window-for-silverlight-and-wpf).</span></span>

8. <span data-ttu-id="85251-137">In der **Eigenschaften** legen den Wert des der <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaft `10, 10, 10, 10`.</span><span class="sxs-lookup"><span data-stu-id="85251-137">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Padding%2A> property to `10, 10, 10, 10`.</span></span>

     <span data-ttu-id="85251-138">Die Größe beider <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelemente wird entsprechend dem neuen Layout angepasst.</span><span class="sxs-lookup"><span data-stu-id="85251-138">Both <xref:System.Windows.Forms.Integration.ElementHost> controls are resized to fit into the new layout.</span></span>

## <a name="using-snaplines-to-align-wpf-controls"></a><span data-ttu-id="85251-139">Verwenden von Ausrichtungslinien zum Ausrichten von WPF-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="85251-139">Using Snaplines to Align WPF Controls</span></span>
 <span data-ttu-id="85251-140">Ausrichtungslinien erleichtern die Ausrichtung von Steuerelementen auf einem Formular.</span><span class="sxs-lookup"><span data-stu-id="85251-140">Snaplines enable easy alignment of controls on a form.</span></span> <span data-ttu-id="85251-141">Sie können Ausrichtungslinien auch verwenden, um WPF-Steuerelemente auszurichten.</span><span class="sxs-lookup"><span data-stu-id="85251-141">You can use snaplines to align your WPF controls as well.</span></span> <span data-ttu-id="85251-142">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span><span class="sxs-lookup"><span data-stu-id="85251-142">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>

#### <a name="to-use-snaplines-to-align-wpf-controls"></a><span data-ttu-id="85251-143">So verwenden Sie Ausrichtungslinien zum Ausrichten von WPF-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="85251-143">To use snaplines to align WPF controls</span></span>

1. <span data-ttu-id="85251-144">Aus der **Toolbox**, ziehen Sie eine Instanz des `UserControl1` auf das Formular, und fügen Sie ihn in den Bereich unterhalb der <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="85251-144">From the **Toolbox**, drag an instance of `UserControl1` onto the form and place it in the space beneath the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

     <span data-ttu-id="85251-145">Die Instanz von `UserControl1` wird in einem neuen <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement namens `elementHost3` gehostet.</span><span class="sxs-lookup"><span data-stu-id="85251-145">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost3`.</span></span>

2. <span data-ttu-id="85251-146">Richten Sie den linken Rand von `elementHost3` mithilfe der Ausrichtungslinien am linken Rand des <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelements aus.</span><span class="sxs-lookup"><span data-stu-id="85251-146">Using snaplines, align the left edge of `elementHost3` with the left edge of <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

3. <span data-ttu-id="85251-147">Legen Sie die Breite von `elementHost3` mithilfe der Ausrichtungslinien auf dieselbe Breite wie das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement fest.</span><span class="sxs-lookup"><span data-stu-id="85251-147">Using snaplines, size `elementHost3` to the same width as the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

4. <span data-ttu-id="85251-148">Verschieben Sie `elementHost3` in Richtung des <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelements,  steuern, bis zwischen den Steuerelementen eine mittige Ausrichtungslinie angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="85251-148">Move `elementHost3` toward the <xref:System.Windows.Forms.TableLayoutPanel> control until a center snapline appears between the controls.</span></span>

5. <span data-ttu-id="85251-149">In der **Eigenschaften** legen den Wert der Margin-Eigenschaft auf `20, 20, 20, 20`.</span><span class="sxs-lookup"><span data-stu-id="85251-149">In the **Properties** window, set the value of the Margin property to `20, 20, 20, 20`.</span></span>

6. <span data-ttu-id="85251-150">Verschieben Sie `elementHost3` vom <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement weg, bis die mittige Ausrichtungslinie erneut angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="85251-150">Move the `elementHost3` away from the <xref:System.Windows.Forms.TableLayoutPanel> control until the center snapline appears again.</span></span> <span data-ttu-id="85251-151">Die mittige Ausrichtungslinie kennzeichnet jetzt einen Rand von 20.</span><span class="sxs-lookup"><span data-stu-id="85251-151">The center snapline now indicates a margin of 20.</span></span>

7. <span data-ttu-id="85251-152">Verschieben Sie `elementHost3` nach rechts, bis dessen linker Rand am linken Rand von `elementHost1` ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="85251-152">Move `elementHost3` to the right, until its left edge aligns with the left edge of `elementHost1`.</span></span>

8. <span data-ttu-id="85251-153">Ändern Sie die Breite von `elementHost3` bis dessen rechter Rand am rechten Rand von `elementHost2` ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="85251-153">Change the width of `elementHost3` until its right edge aligns with the right edge of `elementHost2`.</span></span>

## <a name="anchoring-and-docking-wpf-controls"></a><span data-ttu-id="85251-154">Verankern und Andocken von WPF-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="85251-154">Anchoring and Docking WPF Controls</span></span>
 <span data-ttu-id="85251-155">Ein auf einem Formular gehostetes WPF-Steuerelement hat dasselbe Verankerungs- und Andockverhalten auf wie andere Windows Forms-Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="85251-155">A WPF control hosted on a form has the same anchoring and docking behavior as other Windows Forms controls.</span></span>

#### <a name="to-anchor-and-dock-wpf-controls"></a><span data-ttu-id="85251-156">So verankern Sie WPF-Steuerelemente und docken diese an</span><span class="sxs-lookup"><span data-stu-id="85251-156">To anchor and dock WPF controls</span></span>

1. <span data-ttu-id="85251-157">Klicken Sie auf `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="85251-157">Select `elementHost1`.</span></span>

2. <span data-ttu-id="85251-158">In der **Eigenschaften** legen die <xref:System.Windows.Forms.Control.Anchor%2A> Eigenschaft **Top, Bottom, Left, Right**.</span><span class="sxs-lookup"><span data-stu-id="85251-158">In the **Properties** window, set the <xref:System.Windows.Forms.Control.Anchor%2A> property to **Top, Bottom, Left, Right**.</span></span>

3. <span data-ttu-id="85251-159">Vergrößern Sie das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="85251-159">Resize the <xref:System.Windows.Forms.TableLayoutPanel> control to a larger size.</span></span>

     <span data-ttu-id="85251-160">Die Größe des `elementHost1`-Steuerelements wird geändert, sodass es die Zelle ausfüllt.</span><span class="sxs-lookup"><span data-stu-id="85251-160">The `elementHost1` control resizes to fill the cell.</span></span>

4. <span data-ttu-id="85251-161">Klicken Sie auf `elementHost2`.</span><span class="sxs-lookup"><span data-stu-id="85251-161">Select `elementHost2`.</span></span>

5. <span data-ttu-id="85251-162">In der **Eigenschaften** legen den Wert des der <xref:System.Windows.Forms.Control.Dock%2A> Eigenschaft <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="85251-162">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

     <span data-ttu-id="85251-163">Die Größe des `elementHost2`-Steuerelements wird geändert, sodass es die Zelle ausfüllt.</span><span class="sxs-lookup"><span data-stu-id="85251-163">The `elementHost2` control resizes to fill the cell.</span></span>

6. <span data-ttu-id="85251-164">Wählen Sie das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="85251-164">Select the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

7. <span data-ttu-id="85251-165">Legen Sie den Wert von dessen <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft auf <xref:System.Windows.Forms.DockStyle.Top> fest.</span><span class="sxs-lookup"><span data-stu-id="85251-165">Set the value of its <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Top>.</span></span>

8. <span data-ttu-id="85251-166">Klicken Sie auf `elementHost3`.</span><span class="sxs-lookup"><span data-stu-id="85251-166">Select `elementHost3`.</span></span>

9. <span data-ttu-id="85251-167">Legen Sie den Wert von dessen <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft auf <xref:System.Windows.Forms.DockStyle.Fill> fest.</span><span class="sxs-lookup"><span data-stu-id="85251-167">Set the value of its <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

     <span data-ttu-id="85251-168">Die Größe des `elementHost3`-Steuerelements wird so geändert, dass es den verbleibenden Platz auf dem Formular ausfüllt.</span><span class="sxs-lookup"><span data-stu-id="85251-168">The `elementHost3` control resizes to fill the remaining space on the form.</span></span>

10. <span data-ttu-id="85251-169">Ändern Sie die Größe des Formulars.</span><span class="sxs-lookup"><span data-stu-id="85251-169">Resize the form.</span></span>

     <span data-ttu-id="85251-170">Die Größen aller drei <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelemente werden entsprechend angepasst.</span><span class="sxs-lookup"><span data-stu-id="85251-170">All three <xref:System.Windows.Forms.Integration.ElementHost> controls resize appropriately.</span></span>

     <span data-ttu-id="85251-171">Weitere Informationen finden Sie unter [Vorgehensweise: Verankern und Andocken von untergeordneten Steuerelementen in einem TableLayoutPanel-Steuerelement](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md).</span><span class="sxs-lookup"><span data-stu-id="85251-171">For more information, see [How to: Anchor and Dock Child Controls in a TableLayoutPanel Control](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="85251-172">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="85251-172">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="85251-173">Vorgehensweise: Verankern und Andocken von untergeordneten Steuerelementen in einem TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="85251-173">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="85251-174">Vorgehensweise: Ausrichten eines Steuerelements an den Rändern eines Formulars zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="85251-174">How to: Align a Control to the Edges of Forms at Design Time</span></span>](../controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)
- [<span data-ttu-id="85251-175">Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien</span><span class="sxs-lookup"><span data-stu-id="85251-175">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="85251-176">Migration und Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="85251-176">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="85251-177">Verwenden von WPF-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="85251-177">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="85251-178">Entwerfen von XAML-Code in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="85251-178">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
