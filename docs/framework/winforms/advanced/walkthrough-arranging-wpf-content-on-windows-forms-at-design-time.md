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
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 7858ffd708c78d6397d533f613ccc2ea78d6cbed
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658524"
---
# <a name="walkthrough-arrange-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="ea8ae-102">Exemplarische Vorgehensweise: Anordnen von WPF-Inhalt auf Windows Forms zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="ea8ae-102">Walkthrough: Arrange WPF content on Windows Forms at design time</span></span>

<span data-ttu-id="ea8ae-103">In diesem Artikel erfahren Sie, wie Sie die Windows Forms Layoutfeatures, wie z. b. das verankern und ausrichten, verwenden, um Windows Presentation Foundation (WPF)-Steuerelemente anzuordnen.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-103">This article shows you how to use the Windows Forms layout features, such as anchoring and snaplines, to arrange Windows Presentation Foundation (WPF) controls.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ea8ae-104">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="ea8ae-104">Prerequisites</span></span>

<span data-ttu-id="ea8ae-105">Für diese exemplarische Vorgehensweise benötigen Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-105">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="ea8ae-106">Erstellen eines Projekts</span><span class="sxs-lookup"><span data-stu-id="ea8ae-106">Create the project</span></span>

<span data-ttu-id="ea8ae-107">Öffnen Sie Visual Studio, und erstellen Sie ein neues Windows Forms-Anwendungsprojekt C# in `ArrangeElementHost`Visual Basic oder Visual mit dem Namen.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-107">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `ArrangeElementHost`.</span></span>

> [!NOTE]
> <span data-ttu-id="ea8ae-108">Beim Hosten von WPF-Inhalt werden nur C#- und Visual Basic-Projekte unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-108">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control"></a><span data-ttu-id="ea8ae-109">Erstellen des WPF-Steuer Elements</span><span class="sxs-lookup"><span data-stu-id="ea8ae-109">Create the WPF control</span></span>

<span data-ttu-id="ea8ae-110">Nachdem Sie dem Projekt ein WPF-Steuerelement hinzugefügt haben, können Sie dieses auf dem Formular anordnen.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-110">After you add a WPF control to the project, you can arrange it on the form.</span></span>

1. <span data-ttu-id="ea8ae-111">Fügen Sie dem Projekt ein neues WPF-<xref:System.Windows.Controls.UserControl>-Objekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-111">Add a new WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="ea8ae-112">Verwenden Sie den Standardnamen, `UserControl1.xaml`, für den Steuerelementtyp.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-112">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="ea8ae-113">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen eines neuen WPF-Inhalts auf Windows Forms zur](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)Entwurfszeit.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-113">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="ea8ae-114">Stellen Sie in der Entwurfsansicht sicher, dass `UserControl1` ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-114">In Design view, make sure that `UserControl1` is selected.</span></span>

3. <span data-ttu-id="ea8ae-115">Legen Sie im Fenster **Eigenschaften** den Wert <xref:System.Windows.FrameworkElement.Width%2A> der-Eigenschaft und der- <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaft auf 200 fest.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-115">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="ea8ae-116">Legen Sie den Wert <xref:System.Windows.Controls.Control.Background%2A> der-Eigenschaft auf **Blue**fest.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-116">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to **Blue**.</span></span>

5. <span data-ttu-id="ea8ae-117">Erstellen Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-117">Build the project.</span></span>

## <a name="host-wpf-controls-in-a-layout-panel"></a><span data-ttu-id="ea8ae-118">WPF-Steuerelemente in einem Layoutpanel hosten</span><span class="sxs-lookup"><span data-stu-id="ea8ae-118">Host WPF controls in a layout panel</span></span>

<span data-ttu-id="ea8ae-119">Sie können WPF-Steuerelemente in Layoutbereichen auf die gleiche Weise verwenden wie andere Windows Forms-Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-119">You can use WPF controls in layout panels in the same way you use other Windows Forms controls.</span></span>

1. <span data-ttu-id="ea8ae-120">Öffnen Sie `Form1` im Windows Forms-Designer.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-120">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="ea8ae-121">Ziehen Sieein <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement in der Toolbox auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-121">In the **Toolbox**, drag a <xref:System.Windows.Forms.TableLayoutPanel> control onto the form.</span></span>

3. <span data-ttu-id="ea8ae-122">Wählen Sie <xref:System.Windows.Forms.TableLayoutPanel> im Smarttagbereich des-Steuer Elements **letzte Zeile entfernen**aus.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-122">On the <xref:System.Windows.Forms.TableLayoutPanel> control's smart tag panel, select **Remove Last Row**.</span></span>

4. <span data-ttu-id="ea8ae-123">Ändern Sie die Größe des <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelements, sodass es breiter und höher wird.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-123">Resize the <xref:System.Windows.Forms.TableLayoutPanel> control to a larger width and height.</span></span>

5. <span data-ttu-id="ea8ae-124">DoppelklickenSie `UserControl1` in der Toolbox auf, um in der ersten `UserControl1` Zelle des <xref:System.Windows.Forms.TableLayoutPanel> -Steuer Elements eine Instanz von zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-124">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` in the first cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

   <span data-ttu-id="ea8ae-125">Die Instanz von `UserControl1` wird in einem neuen <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement namens `elementHost1` gehostet.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-125">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

6. <span data-ttu-id="ea8ae-126">DoppelklickenSie `UserControl1` in der Toolbox auf, um eine weitere Instanz in der <xref:System.Windows.Forms.TableLayoutPanel> zweiten Zelle des-Steuer Elements zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-126">In the **Toolbox**, double-click `UserControl1` to create another instance in the second cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

7. <span data-ttu-id="ea8ae-127">Wählen Sie `tableLayoutPanel1`im Fenster "Dokument Gliederung" aus.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-127">In the **Document Outline** window, select `tableLayoutPanel1`.</span></span>

8. <span data-ttu-id="ea8ae-128">Legen Sie im Fenster **Eigenschaften** den Wert der <xref:System.Windows.Forms.Control.Padding%2A> -Eigenschaft auf **10, 10, 10, 10**fest.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-128">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Padding%2A> property to **10, 10, 10, 10**.</span></span>

   <span data-ttu-id="ea8ae-129">Die Größe beider <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelemente wird entsprechend dem neuen Layout angepasst.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-129">Both <xref:System.Windows.Forms.Integration.ElementHost> controls are resized to fit into the new layout.</span></span>

## <a name="use-snaplines-to-align-wpf-controls"></a><span data-ttu-id="ea8ae-130">Verwenden von Ausrichtungs Linien zum Ausrichten von WPF-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="ea8ae-130">Use snaplines to align WPF controls</span></span>

<span data-ttu-id="ea8ae-131">Ausrichtungslinien erleichtern die Ausrichtung von Steuerelementen auf einem Formular.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-131">Snaplines enable easy alignment of controls on a form.</span></span> <span data-ttu-id="ea8ae-132">Sie können Ausrichtungslinien auch verwenden, um WPF-Steuerelemente auszurichten.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-132">You can use snaplines to align your WPF controls as well.</span></span> <span data-ttu-id="ea8ae-133">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Anordnen von Steuerelementen auf Windows Forms mithilfe](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)von Richtungslinien.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-133">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>

1. <span data-ttu-id="ea8ae-134">Ziehen Sie aus der **Toolbox**eine Instanz von `UserControl1` auf das Formular, und platzieren Sie Sie in dem Bereich unterhalb <xref:System.Windows.Forms.TableLayoutPanel> des Steuer Elements.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-134">From the **Toolbox**, drag an instance of `UserControl1` onto the form, and place it in the space beneath the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

   <span data-ttu-id="ea8ae-135">Die Instanz von `UserControl1` wird in einem neuen <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement namens `elementHost3` gehostet.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-135">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost3`.</span></span>

2. <span data-ttu-id="ea8ae-136">Richten Sie den linken Rand von `elementHost3` mithilfe der Ausrichtungslinien am linken Rand des <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelements aus.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-136">Using snaplines, align the left edge of `elementHost3` with the left edge of <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

3. <span data-ttu-id="ea8ae-137">Legen Sie die Breite von `elementHost3` mithilfe der Ausrichtungslinien auf dieselbe Breite wie das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement fest.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-137">Using snaplines, size `elementHost3` to the same width as the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

4. <span data-ttu-id="ea8ae-138">Verschieben Sie `elementHost3` in Richtung des <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelements,  steuern, bis zwischen den Steuerelementen eine mittige Ausrichtungslinie angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-138">Move `elementHost3` toward the <xref:System.Windows.Forms.TableLayoutPanel> control until a center snapline appears between the controls.</span></span>

5. <span data-ttu-id="ea8ae-139">Legen Sie im Fenster **Eigenschaften** den Wert der Margin-Eigenschaft auf **20, 20, 20, 20**fest.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-139">In the **Properties** window, set the value of the Margin property to **20, 20, 20, 20**.</span></span>

6. <span data-ttu-id="ea8ae-140">Verschieben Sie `elementHost3` vom <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement weg, bis die mittige Ausrichtungslinie erneut angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-140">Move the `elementHost3` away from the <xref:System.Windows.Forms.TableLayoutPanel> control until the center snapline appears again.</span></span> <span data-ttu-id="ea8ae-141">Die mittige Ausrichtungslinie kennzeichnet jetzt einen Rand von 20.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-141">The center snapline now indicates a margin of 20.</span></span>

7. <span data-ttu-id="ea8ae-142">Nach `elementHost3` rechts verschieben, bis der linke Rand am linken Rand von `elementHost1`ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-142">Move `elementHost3` to the right until its left edge aligns with the left edge of `elementHost1`.</span></span>

8. <span data-ttu-id="ea8ae-143">Ändern Sie die Breite von `elementHost3` bis dessen rechter Rand am rechten Rand von `elementHost2` ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-143">Change the width of `elementHost3` until its right edge aligns with the right edge of `elementHost2`.</span></span>

## <a name="anchor-and-dock-wpf-controls"></a><span data-ttu-id="ea8ae-144">WPF-Steuerelemente verankern und Andocken</span><span class="sxs-lookup"><span data-stu-id="ea8ae-144">Anchor and dock WPF controls</span></span>

<span data-ttu-id="ea8ae-145">Ein auf einem Formular gehostetes WPF-Steuerelement hat dasselbe Verankerungs- und Andockverhalten auf wie andere Windows Forms-Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-145">A WPF control hosted on a form has the same anchoring and docking behavior as other Windows Forms controls.</span></span>

1. <span data-ttu-id="ea8ae-146">Klicken Sie auf `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-146">Select `elementHost1`.</span></span>

2. <span data-ttu-id="ea8ae-147">Legen Sie im Fenster **Eigenschaften** die <xref:System.Windows.Forms.Control.Anchor%2A> -Eigenschaft auf **oben, unten, Links und rechts**fest.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-147">In the **Properties** window, set the <xref:System.Windows.Forms.Control.Anchor%2A> property to **Top, Bottom, Left, Right**.</span></span>

3. <span data-ttu-id="ea8ae-148">Vergrößern Sie das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-148">Resize the <xref:System.Windows.Forms.TableLayoutPanel> control to a larger size.</span></span>

   <span data-ttu-id="ea8ae-149">Die Größe des `elementHost1`-Steuerelements wird geändert, sodass es die Zelle ausfüllt.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-149">The `elementHost1` control resizes to fill the cell.</span></span>

4. <span data-ttu-id="ea8ae-150">Klicken Sie auf `elementHost2`.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-150">Select `elementHost2`.</span></span>

5. <span data-ttu-id="ea8ae-151">Legen Sie im Fenster **Eigenschaften** den Wert <xref:System.Windows.Forms.Control.Dock%2A> der-Eigenschaft auf <xref:System.Windows.Forms.DockStyle.Fill>fest.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-151">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

   <span data-ttu-id="ea8ae-152">Die Größe des `elementHost2`-Steuerelements wird geändert, sodass es die Zelle ausfüllt.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-152">The `elementHost2` control resizes to fill the cell.</span></span>

6. <span data-ttu-id="ea8ae-153">Wählen Sie das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-153">Select the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

7. <span data-ttu-id="ea8ae-154">Legen Sie den Wert von dessen <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft auf <xref:System.Windows.Forms.DockStyle.Top> fest.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-154">Set the value of its <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Top>.</span></span>

8. <span data-ttu-id="ea8ae-155">Klicken Sie auf `elementHost3`.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-155">Select `elementHost3`.</span></span>

9. <span data-ttu-id="ea8ae-156">Legen Sie den Wert von dessen <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft auf <xref:System.Windows.Forms.DockStyle.Fill> fest.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-156">Set the value of its <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

   <span data-ttu-id="ea8ae-157">Die Größe des `elementHost3`-Steuerelements wird so geändert, dass es den verbleibenden Platz auf dem Formular ausfüllt.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-157">The `elementHost3` control resizes to fill the remaining space on the form.</span></span>

10. <span data-ttu-id="ea8ae-158">Ändern Sie die Größe des Formulars.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-158">Resize the form.</span></span>

    <span data-ttu-id="ea8ae-159">Die Größen aller drei <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelemente werden entsprechend angepasst.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-159">All three <xref:System.Windows.Forms.Integration.ElementHost> controls resize appropriately.</span></span>

    <span data-ttu-id="ea8ae-160">Weitere Informationen finden Sie unter [Vorgehensweise: Verankern und Andocken von untergeordneten Steuerelementen in einem TableLayoutPanel-Steuer](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)Element</span><span class="sxs-lookup"><span data-stu-id="ea8ae-160">For more information, see [How to: Anchor and Dock Child Controls in a TableLayoutPanel Control](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ea8ae-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ea8ae-161">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="ea8ae-162">Vorgehensweise: Verankern und Andocken untergeordneter Steuerelemente in einem TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ea8ae-162">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="ea8ae-163">Vorgehensweise: Ausrichten eines Steuer Elements an den Kanten von Formularen zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="ea8ae-163">How to: Align a Control to the Edges of Forms at Design Time</span></span>](../controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)
- [<span data-ttu-id="ea8ae-164">Exemplarische Vorgehensweise: Anordnen von Steuerelementen auf Windows Forms mithilfe von Richtungslinien</span><span class="sxs-lookup"><span data-stu-id="ea8ae-164">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="ea8ae-165">Migration und Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="ea8ae-165">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="ea8ae-166">Verwenden von WPF-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="ea8ae-166">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="ea8ae-167">Entwerfen von XAML-Code in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ea8ae-167">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
