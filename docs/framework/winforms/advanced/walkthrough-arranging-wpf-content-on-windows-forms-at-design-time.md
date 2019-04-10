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
ms.openlocfilehash: 306c042fe432f0c087ceb1b5ff6b5aec0fe0bbc7
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59327307"
---
# <a name="walkthrough-arranging-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="64149-102">Exemplarische Vorgehensweise: Anordnen von WPF-Inhalt in Windows Forms zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="64149-102">Walkthrough: Arranging WPF Content on Windows Forms at Design Time</span></span>
<span data-ttu-id="64149-103">In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie die Windows Forms-Layoutfunktionen, z. B. Verankern und Ausrichtungslinien, verwendet werden können, um WPF-Steuerelemente (Windows Presentation Foundation) anzuordnen.</span><span class="sxs-lookup"><span data-stu-id="64149-103">This walkthrough shows you how to use the Windows Forms layout features, such as anchoring and snaplines, to arrange Windows Presentation Foundation (WPF) controls.</span></span>

 <span data-ttu-id="64149-104">Im Verlauf dieser exemplarischen Vorgehensweise führen Sie die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="64149-104">In this walkthrough, you perform the following tasks:</span></span>

-   <span data-ttu-id="64149-105">Erstellen eines Projekts</span><span class="sxs-lookup"><span data-stu-id="64149-105">Create the project.</span></span>

-   <span data-ttu-id="64149-106">Erstellen des WPF-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="64149-106">Create the WPF control.</span></span>

-   <span data-ttu-id="64149-107">Hosten von WPF-Steuerelementen in einem Layoutbereich</span><span class="sxs-lookup"><span data-stu-id="64149-107">Host WPF controls in a layout panel.</span></span>

-   <span data-ttu-id="64149-108">Verwenden von Ausrichtungslinien zum Ausrichten von WPF-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="64149-108">Use snaplines to align WPF controls.</span></span>

-   <span data-ttu-id="64149-109">Verankern und Andocken von WPF-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="64149-109">Anchor and dock WPF controls.</span></span>

> [!NOTE]
>  <span data-ttu-id="64149-110">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="64149-110">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="64149-111">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="64149-111">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="64149-112">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="64149-112">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="64149-113">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="64149-113">Prerequisites</span></span>  
 <span data-ttu-id="64149-114">Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="64149-114">You need the following components to complete this walkthrough:</span></span>  
  
-   <span data-ttu-id="64149-115">Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="64149-115">Visual Studio 2012.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="64149-116">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="64149-116">Creating the Project</span></span>  
 <span data-ttu-id="64149-117">Zunächst muss das Windows Forms-Projekt erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="64149-117">The first step is to create the Windows Forms project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="64149-118">Beim Hosten von WPF-Inhalt werden nur C#- und Visual Basic-Projekte unterstützt.</span><span class="sxs-lookup"><span data-stu-id="64149-118">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="64149-119">So erstellen Sie das Projekt</span><span class="sxs-lookup"><span data-stu-id="64149-119">To create the project</span></span>  
  
-   <span data-ttu-id="64149-120">Erstellen Sie ein neues Windows Forms-Anwendungsprojekt in Visual Basic oder Visual c# mit dem Namen `ArrangeElementHost`.</span><span class="sxs-lookup"><span data-stu-id="64149-120">Create a new Windows Forms Application project in Visual Basic or Visual C# named `ArrangeElementHost`.</span></span>  
  
## <a name="creating-the-wpf-control"></a><span data-ttu-id="64149-121">Erstellen des WPF-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="64149-121">Creating the WPF Control</span></span>  
 <span data-ttu-id="64149-122">Nachdem Sie dem Projekt ein WPF-Steuerelement hinzugefügt haben, können Sie dieses auf dem Formular anordnen.</span><span class="sxs-lookup"><span data-stu-id="64149-122">After you add a WPF control to the project, you can arrange it on the form.</span></span>  
  
#### <a name="to-create-wpf-controls"></a><span data-ttu-id="64149-123">So erstellen Sie ein WPF-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="64149-123">To create WPF controls</span></span>  
  
1. <span data-ttu-id="64149-124">Fügen Sie dem Projekt ein neues WPF-<xref:System.Windows.Controls.UserControl>-Objekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="64149-124">Add a new WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="64149-125">Verwenden Sie den Standardnamen, `UserControl1.xaml`, für den Steuerelementtyp.</span><span class="sxs-lookup"><span data-stu-id="64149-125">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="64149-126">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen von neuen WPF-Inhalts in Windows Forms zur Entwurfszeit](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="64149-126">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2. <span data-ttu-id="64149-127">Stellen Sie in der Entwurfsansicht sicher, dass `UserControl1` ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="64149-127">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="64149-128">Weitere Informationen finden Sie unter [Vorgehensweise: Wählen Sie aus, und verschieben Sie Elemente auf der Entwurfsoberfläche](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="64149-128">For more information, see [How to: Select and Move Elements on the Design Surface](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span></span>  
  
3. <span data-ttu-id="64149-129">In der **Eigenschaften** legen den Wert des der <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften `200`.</span><span class="sxs-lookup"><span data-stu-id="64149-129">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>  
  
4. <span data-ttu-id="64149-130">Legen Sie den Wert der <xref:System.Windows.Controls.Control.Background%2A>-Eigenschaft auf `Blue` fest.</span><span class="sxs-lookup"><span data-stu-id="64149-130">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to `Blue`.</span></span>  
  
5. <span data-ttu-id="64149-131">Erstellen Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="64149-131">Build the project.</span></span>  
  
## <a name="hosting-wpf-controls-in-a-layout-panel"></a><span data-ttu-id="64149-132">Hosten von WPF-Steuerelementen in einem Layoutbereich</span><span class="sxs-lookup"><span data-stu-id="64149-132">Hosting WPF Controls in a Layout Panel</span></span>  
 <span data-ttu-id="64149-133">Sie können WPF-Steuerelemente in Layoutbereichen auf die gleiche Weise verwenden wie andere Windows Forms-Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="64149-133">You can use WPF controls in layout panels in the same way you use other Windows Forms controls.</span></span>  
  
#### <a name="to-host-wpf-controls-in-a-layout-panel"></a><span data-ttu-id="64149-134">So hosten Sie WPF-Steuerelemente in einem Layoutbereich</span><span class="sxs-lookup"><span data-stu-id="64149-134">To host WPF controls in a layout panel</span></span>  
  
1. <span data-ttu-id="64149-135">Öffnen Sie `Form1` im Windows Forms-Designer.</span><span class="sxs-lookup"><span data-stu-id="64149-135">Open `Form1` in the Windows Forms Designer.</span></span>  
  
2. <span data-ttu-id="64149-136">In der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="64149-136">In the **Toolbox**, drag a <xref:System.Windows.Forms.TableLayoutPanel> control onto the form.</span></span>  
  
3. <span data-ttu-id="64149-137">Auf der <xref:System.Windows.Forms.TableLayoutPanel> des Steuerelements im Smarttagbereich auf **letzte Zeile entfernen**.</span><span class="sxs-lookup"><span data-stu-id="64149-137">On the <xref:System.Windows.Forms.TableLayoutPanel> control's smart tag panel, select **Remove Last Row**.</span></span>  
  
4. <span data-ttu-id="64149-138">Ändern Sie die Größe des <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelements, sodass es breiter und höher wird.</span><span class="sxs-lookup"><span data-stu-id="64149-138">Resize the <xref:System.Windows.Forms.TableLayoutPanel> control to a larger width and height.</span></span>  
  
5. <span data-ttu-id="64149-139">In der **Toolbox**, doppelklicken Sie auf `UserControl1` zum Erstellen einer Instanz von `UserControl1` in der ersten Zelle der <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="64149-139">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` in the first cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
     <span data-ttu-id="64149-140">Die Instanz von `UserControl1` wird in einem neuen <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement namens `elementHost1` gehostet.</span><span class="sxs-lookup"><span data-stu-id="64149-140">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
6. <span data-ttu-id="64149-141">In der **Toolbox**, doppelklicken Sie auf `UserControl1` zum Erstellen von einer anderen Instanz in der zweiten Zelle die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="64149-141">In the **Toolbox**, double-click `UserControl1` to create another instance in the second cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
7. <span data-ttu-id="64149-142">In der **Dokumentgliederung** wählen Sie im Fenster `tableLayoutPanel1`.</span><span class="sxs-lookup"><span data-stu-id="64149-142">In the **Document Outline** window, select `tableLayoutPanel1`.</span></span> <span data-ttu-id="64149-143">Weitere Informationen finden Sie unter [Dokumentgliederung (Fenster)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/46xf4h0w(v=vs.100)#using-the-document-outline-window-for-silverlight-and-wpf).</span><span class="sxs-lookup"><span data-stu-id="64149-143">For more information, see [Document Outline Window](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/46xf4h0w(v=vs.100)#using-the-document-outline-window-for-silverlight-and-wpf).</span></span>  
  
8. <span data-ttu-id="64149-144">In der **Eigenschaften** legen den Wert des der <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaft `10, 10, 10, 10`.</span><span class="sxs-lookup"><span data-stu-id="64149-144">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Padding%2A> property to `10, 10, 10, 10`.</span></span>  
  
     <span data-ttu-id="64149-145">Die Größe beider <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelemente wird entsprechend dem neuen Layout angepasst.</span><span class="sxs-lookup"><span data-stu-id="64149-145">Both <xref:System.Windows.Forms.Integration.ElementHost> controls are resized to fit into the new layout.</span></span>  
  
## <a name="using-snaplines-to-align-wpf-controls"></a><span data-ttu-id="64149-146">Verwenden von Ausrichtungslinien zum Ausrichten von WPF-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="64149-146">Using Snaplines to Align WPF Controls</span></span>  
 <span data-ttu-id="64149-147">Ausrichtungslinien erleichtern die Ausrichtung von Steuerelementen auf einem Formular.</span><span class="sxs-lookup"><span data-stu-id="64149-147">Snaplines enable easy alignment of controls on a form.</span></span> <span data-ttu-id="64149-148">Sie können Ausrichtungslinien auch verwenden, um WPF-Steuerelemente auszurichten.</span><span class="sxs-lookup"><span data-stu-id="64149-148">You can use snaplines to align your WPF controls as well.</span></span> <span data-ttu-id="64149-149">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span><span class="sxs-lookup"><span data-stu-id="64149-149">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>  
  
#### <a name="to-use-snaplines-to-align-wpf-controls"></a><span data-ttu-id="64149-150">So verwenden Sie Ausrichtungslinien zum Ausrichten von WPF-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="64149-150">To use snaplines to align WPF controls</span></span>  
  
1. <span data-ttu-id="64149-151">Aus der **Toolbox**, ziehen Sie eine Instanz des `UserControl1` auf das Formular, und fügen Sie ihn in den Bereich unterhalb der <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="64149-151">From the **Toolbox**, drag an instance of `UserControl1` onto the form and place it in the space beneath the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
     <span data-ttu-id="64149-152">Die Instanz von `UserControl1` wird in einem neuen <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement namens `elementHost3` gehostet.</span><span class="sxs-lookup"><span data-stu-id="64149-152">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost3`.</span></span>  
  
2. <span data-ttu-id="64149-153">Richten Sie den linken Rand von `elementHost3` mithilfe der Ausrichtungslinien am linken Rand des <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelements aus.</span><span class="sxs-lookup"><span data-stu-id="64149-153">Using snaplines, align the left edge of `elementHost3` with the left edge of <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
3. <span data-ttu-id="64149-154">Legen Sie die Breite von `elementHost3` mithilfe der Ausrichtungslinien auf dieselbe Breite wie das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement fest.</span><span class="sxs-lookup"><span data-stu-id="64149-154">Using snaplines, size `elementHost3` to the same width as the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
4. <span data-ttu-id="64149-155">Verschieben Sie `elementHost3` in Richtung des <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelements,  steuern, bis zwischen den Steuerelementen eine mittige Ausrichtungslinie angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="64149-155">Move `elementHost3` toward the <xref:System.Windows.Forms.TableLayoutPanel> control until a center snapline appears between the controls.</span></span>  
  
5. <span data-ttu-id="64149-156">In der **Eigenschaften** legen den Wert der Margin-Eigenschaft auf `20, 20, 20, 20`.</span><span class="sxs-lookup"><span data-stu-id="64149-156">In the **Properties** window, set the value of the Margin property to `20, 20, 20, 20`.</span></span>  
  
6. <span data-ttu-id="64149-157">Verschieben Sie `elementHost3` vom <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement weg, bis die mittige Ausrichtungslinie erneut angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="64149-157">Move the `elementHost3` away from the <xref:System.Windows.Forms.TableLayoutPanel> control until the center snapline appears again.</span></span> <span data-ttu-id="64149-158">Die mittige Ausrichtungslinie kennzeichnet jetzt einen Rand von 20.</span><span class="sxs-lookup"><span data-stu-id="64149-158">The center snapline now indicates a margin of 20.</span></span>  
  
7. <span data-ttu-id="64149-159">Verschieben Sie `elementHost3` nach rechts, bis dessen linker Rand am linken Rand von `elementHost1` ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="64149-159">Move `elementHost3` to the right, until its left edge aligns with the left edge of `elementHost1`.</span></span>  
  
8. <span data-ttu-id="64149-160">Ändern Sie die Breite von `elementHost3` bis dessen rechter Rand am rechten Rand von `elementHost2` ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="64149-160">Change the width of `elementHost3` until its right edge aligns with the right edge of `elementHost2`.</span></span>  
  
## <a name="anchoring-and-docking-wpf-controls"></a><span data-ttu-id="64149-161">Verankern und Andocken von WPF-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="64149-161">Anchoring and Docking WPF Controls</span></span>  
 <span data-ttu-id="64149-162">Ein auf einem Formular gehostetes WPF-Steuerelement hat dasselbe Verankerungs- und Andockverhalten auf wie andere Windows Forms-Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="64149-162">A WPF control hosted on a form has the same anchoring and docking behavior as other Windows Forms controls.</span></span>  
  
#### <a name="to-anchor-and-dock-wpf-controls"></a><span data-ttu-id="64149-163">So verankern Sie WPF-Steuerelemente und docken diese an</span><span class="sxs-lookup"><span data-stu-id="64149-163">To anchor and dock WPF controls</span></span>  
  
1. <span data-ttu-id="64149-164">Klicken Sie auf `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="64149-164">Select `elementHost1`.</span></span>  
  
2. <span data-ttu-id="64149-165">In der **Eigenschaften** legen die <xref:System.Windows.Forms.Control.Anchor%2A> Eigenschaft **Top, Bottom, Left, Right**.</span><span class="sxs-lookup"><span data-stu-id="64149-165">In the **Properties** window, set the <xref:System.Windows.Forms.Control.Anchor%2A> property to **Top, Bottom, Left, Right**.</span></span>  
  
3. <span data-ttu-id="64149-166">Vergrößern Sie das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="64149-166">Resize the <xref:System.Windows.Forms.TableLayoutPanel> control to a larger size.</span></span>  
  
     <span data-ttu-id="64149-167">Die Größe des `elementHost1`-Steuerelements wird geändert, sodass es die Zelle ausfüllt.</span><span class="sxs-lookup"><span data-stu-id="64149-167">The `elementHost1` control resizes to fill the cell.</span></span>  
  
4. <span data-ttu-id="64149-168">Klicken Sie auf `elementHost2`.</span><span class="sxs-lookup"><span data-stu-id="64149-168">Select `elementHost2`.</span></span>  
  
5. <span data-ttu-id="64149-169">In der **Eigenschaften** legen den Wert des der <xref:System.Windows.Forms.Control.Dock%2A> Eigenschaft <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="64149-169">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
     <span data-ttu-id="64149-170">Die Größe des `elementHost2`-Steuerelements wird geändert, sodass es die Zelle ausfüllt.</span><span class="sxs-lookup"><span data-stu-id="64149-170">The `elementHost2` control resizes to fill the cell.</span></span>  
  
6. <span data-ttu-id="64149-171">Wählen Sie das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="64149-171">Select the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
7. <span data-ttu-id="64149-172">Legen Sie den Wert von dessen <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft auf <xref:System.Windows.Forms.DockStyle.Top> fest.</span><span class="sxs-lookup"><span data-stu-id="64149-172">Set the value of its <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Top>.</span></span>  
  
8. <span data-ttu-id="64149-173">Klicken Sie auf `elementHost3`.</span><span class="sxs-lookup"><span data-stu-id="64149-173">Select `elementHost3`.</span></span>  
  
9. <span data-ttu-id="64149-174">Legen Sie den Wert von dessen <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft auf <xref:System.Windows.Forms.DockStyle.Fill> fest.</span><span class="sxs-lookup"><span data-stu-id="64149-174">Set the value of its <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
     <span data-ttu-id="64149-175">Die Größe des `elementHost3`-Steuerelements wird so geändert, dass es den verbleibenden Platz auf dem Formular ausfüllt.</span><span class="sxs-lookup"><span data-stu-id="64149-175">The `elementHost3` control resizes to fill the remaining space on the form.</span></span>  
  
10. <span data-ttu-id="64149-176">Ändern Sie die Größe des Formulars.</span><span class="sxs-lookup"><span data-stu-id="64149-176">Resize the form.</span></span>  
  
     <span data-ttu-id="64149-177">Die Größen aller drei <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelemente werden entsprechend angepasst.</span><span class="sxs-lookup"><span data-stu-id="64149-177">All three <xref:System.Windows.Forms.Integration.ElementHost> controls resize appropriately.</span></span>  
  
     <span data-ttu-id="64149-178">Weitere Informationen finden Sie unter [Vorgehensweise: Verankern und Andocken von untergeordneten Steuerelementen in einem TableLayoutPanel-Steuerelement](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md).</span><span class="sxs-lookup"><span data-stu-id="64149-178">For more information, see [How to: Anchor and Dock Child Controls in a TableLayoutPanel Control](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64149-179">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="64149-179">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="64149-180">Vorgehensweise: Verankern und Andocken von untergeordneten Steuerelementen in einem TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="64149-180">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="64149-181">Vorgehensweise: Ausrichten eines Steuerelements an den Rändern eines Formulars zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="64149-181">How to: Align a Control to the Edges of Forms at Design Time</span></span>](../controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)
- [<span data-ttu-id="64149-182">Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien</span><span class="sxs-lookup"><span data-stu-id="64149-182">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="64149-183">Migration und Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="64149-183">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="64149-184">Verwenden von WPF-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="64149-184">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="64149-185">Entwerfen von XAML-Code in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="64149-185">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
