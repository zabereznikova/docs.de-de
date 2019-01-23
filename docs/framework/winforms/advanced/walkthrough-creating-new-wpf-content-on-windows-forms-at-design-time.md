---
title: 'Exemplarische Vorgehensweise: Erstellen von neuen WPF-Inhalts in Windows Forms zur Entwurfszeit'
ms.date: 08/18/2018
helpviewer_keywords:
- interoperability [Windows Forms], WPF and Windows Forms
- WPF content [Windows Forms], hosting in Windows Forms
- hosting WPF content in Windows Forms
- ElementHost control
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 2e92d8e8-f0e4-4df7-9f07-2acf35cd798c
ms.openlocfilehash: 9414eb8edc839b109aafa0c98fa3ed74a34a7d62
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54500498"
---
# <a name="walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="41033-102">Exemplarische Vorgehensweise: Erstellen von neuen WPF-Inhalts in Windows Forms zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="41033-102">Walkthrough: Creating New WPF Content on Windows Forms at Design Time</span></span>

<span data-ttu-id="41033-103">In diesem Thema wird veranschaulicht, wie Sie ein Windows Presentation Foundation-Steuerelement (WPF) zur Verwendung in Windows Forms-basierten Anwendungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="41033-103">This topic shows you how to create a Windows Presentation Foundation (WPF) control for use in your Windows Forms-based applications.</span></span>

<span data-ttu-id="41033-104">Im Verlauf dieser exemplarischen Vorgehensweise führen Sie folgende Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="41033-104">In this walkthrough, you perform the following tasks:</span></span>

- <span data-ttu-id="41033-105">Erstellen eines Projekts</span><span class="sxs-lookup"><span data-stu-id="41033-105">Create the project.</span></span>

- <span data-ttu-id="41033-106">Erstellen eines neuen WPF-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="41033-106">Create a new WPF control.</span></span>

- <span data-ttu-id="41033-107">Hinzufügen des neuen WPF-Steuerelements zu einem Windows Form.</span><span class="sxs-lookup"><span data-stu-id="41033-107">Add the new WPF control to a Windows Form.</span></span> <span data-ttu-id="41033-108">Das WPF-Steuerelement wird in einem <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement gehostet.</span><span class="sxs-lookup"><span data-stu-id="41033-108">The WPF control is hosted in an <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="41033-109">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="41033-109">Prerequisites</span></span>

<span data-ttu-id="41033-110">Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="41033-110">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="41033-111">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="41033-111">Visual Studio 2017</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="41033-112">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="41033-112">Creating the Project</span></span>

<span data-ttu-id="41033-113">Zunächst muss das Windows Forms-Projekt erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="41033-113">The first step is to create the Windows Forms project.</span></span> <span data-ttu-id="41033-114">Öffnen Sie Visual Studio, und erstellen Sie ein neues **Windows Forms-App ((.NET Framework)** Projekt in Visual Basic oder Visual c# mit dem Namen `HostingWpf`.</span><span class="sxs-lookup"><span data-stu-id="41033-114">Open Visual Studio and create a new **Windows Forms App (.NET Framework)** project in Visual Basic or Visual C# named `HostingWpf`.</span></span>

> [!NOTE]
> <span data-ttu-id="41033-115">Beim Hosten von WPF-Inhalt werden nur C#- und Visual Basic-Projekte unterstützt.</span><span class="sxs-lookup"><span data-stu-id="41033-115">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="creating-a-new-wpf-control"></a><span data-ttu-id="41033-116">Erstellen eines neuen WPF-Steuerelements </span><span class="sxs-lookup"><span data-stu-id="41033-116">Creating a New WPF Control</span></span>

<span data-ttu-id="41033-117">Das Erstellen eines neuen WPF-Steuerelements und das Hinzufügen des Steuerelements zum Projekt ist genauso einfach wie das Hinzufügen eines beliebigen anderen Elements zum Projekt.</span><span class="sxs-lookup"><span data-stu-id="41033-117">Creating a new WPF control and adding it to your project is as easy as adding any other item to your project.</span></span> <span data-ttu-id="41033-118">Der Windows Forms-Designer arbeitet mit einer bestimmten Art von Steuerelement mit dem Namen *zusammengesetztes Steuerelement*, oder *Benutzersteuerelement*.</span><span class="sxs-lookup"><span data-stu-id="41033-118">The Windows Forms Designer works with a particular kind of control named *composite control*, or *user control*.</span></span> <span data-ttu-id="41033-119">Weitere Informationen zu benutzerdefinierten WPF-Steuerelementen finden Sie unter <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="41033-119">For more information about WPF user controls, see <xref:System.Windows.Controls.UserControl>.</span></span>

> [!NOTE]
> <span data-ttu-id="41033-120">Der <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType>-Typ für WPF unterscheidet sich vom Windows Forms-Benutzersteuerelementtyp, der ebenfalls den Namen <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType> hat.</span><span class="sxs-lookup"><span data-stu-id="41033-120">The <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> type for WPF is distinct from the user control type provided by Windows Forms, which is also named <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>.</span></span>

### <a name="to-create-a-new-wpf-control"></a><span data-ttu-id="41033-121">So erstellen Sie ein neues WPF-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="41033-121">To create a new WPF control</span></span>

1. <span data-ttu-id="41033-122">In **Projektmappen-Explorer**, fügen Sie einen neuen **WPF-Benutzersteuerelementbibliothek ((.NET Framework)** Projekt der Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="41033-122">In **Solution Explorer**, add a new **WPF User Control Library (.NET Framework)** project to the solution.</span></span> <span data-ttu-id="41033-123">Verwenden Sie den Standardnamen `WpfControlLibrary1` für die Steuerelementbibliothek.</span><span class="sxs-lookup"><span data-stu-id="41033-123">Use the default name for the control library, `WpfControlLibrary1`.</span></span> <span data-ttu-id="41033-124">Der Standardname für das Steuerelement lautet `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="41033-124">The default control name is `UserControl1.xaml`.</span></span>

     <span data-ttu-id="41033-125">Hinzufügen des neuen Steuerelements hat folgende Auswirkungen:</span><span class="sxs-lookup"><span data-stu-id="41033-125">Adding the new control has the following effects:</span></span>

    - <span data-ttu-id="41033-126">Die Datei UserControl1.xaml wird hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="41033-126">File UserControl1.xaml is added.</span></span>

    - <span data-ttu-id="41033-127">Hinzugefügt wird entweder die Datei UserControl1.xaml.cs oder die Datei UserControl1.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="41033-127">Either file UserControl1.xaml.cs or UserControl1.xaml.vb is added.</span></span> <span data-ttu-id="41033-128">Diese Datei enthält das Code-Behind-Modell für Ereignishandler und andere Implementierungen.</span><span class="sxs-lookup"><span data-stu-id="41033-128">This file contains the code-behind for event handlers and other implementation.</span></span>

    - <span data-ttu-id="41033-129">Es werden Verweise auf die WPF-Assemblys hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="41033-129">References to WPF assemblies are added.</span></span>

    - <span data-ttu-id="41033-130">Die Datei UserControl1.xaml wird in [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] geöffnet.</span><span class="sxs-lookup"><span data-stu-id="41033-130">File UserControl1.xaml opens in the [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)].</span></span>

2. <span data-ttu-id="41033-131">Stellen Sie in der Entwurfsansicht sicher, dass `UserControl1` ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="41033-131">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="41033-132">Weitere Informationen finden Sie unter [Vorgehensweise: Wählen Sie aus, und verschieben Sie Elemente auf der Entwurfsoberfläche](https://msdn.microsoft.com/library/54cb70b6-b35b-46e4-a0cc-65189399c474).</span><span class="sxs-lookup"><span data-stu-id="41033-132">For more information, see [How to: Select and Move Elements on the Design Surface](https://msdn.microsoft.com/library/54cb70b6-b35b-46e4-a0cc-65189399c474).</span></span>

3. <span data-ttu-id="41033-133">In der **Eigenschaften** legen den Wert des der <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften **200**.</span><span class="sxs-lookup"><span data-stu-id="41033-133">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="41033-134">Von der **Toolbox**, ziehen Sie eine <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> Steuerelement auf die Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="41033-134">From the **Toolbox**, drag a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control onto the design surface.</span></span>

5. <span data-ttu-id="41033-135">In der **Eigenschaften** legen den Wert des der <xref:System.Windows.Controls.TextBox.Text%2A> Eigenschaft **gehosteten Inhalt**.</span><span class="sxs-lookup"><span data-stu-id="41033-135">In the **Properties** window, set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="41033-136">Normalerweise sollten Sie anspruchsvolleren WPF-Inhalt hosten.</span><span class="sxs-lookup"><span data-stu-id="41033-136">In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="41033-137"><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>-Steuerelement wird hier nur zur Veranschaulichung verwendet. </span><span class="sxs-lookup"><span data-stu-id="41033-137">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>

6. <span data-ttu-id="41033-138">Erstellen Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="41033-138">Build the project.</span></span>

## <a name="adding-a-wpf-control-to-a-windows-form"></a><span data-ttu-id="41033-139">Hinzufügen eines neuen WPF-Steuerelements zu einem Windows Form</span><span class="sxs-lookup"><span data-stu-id="41033-139">Adding a WPF Control to a Windows Form</span></span>

<span data-ttu-id="41033-140">Das neue WPF-Steuerelement kann jetzt im Formular verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="41033-140">Your new WPF control is ready for use on the form.</span></span> <span data-ttu-id="41033-141">Windows Forms verwendet die <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement zum Hosten von WPF-Inhalt.</span><span class="sxs-lookup"><span data-stu-id="41033-141">Windows Forms uses the <xref:System.Windows.Forms.Integration.ElementHost> control to host WPF content.</span></span>

### <a name="to-add-a-wpf-control-to-a-windows-form"></a><span data-ttu-id="41033-142">So fügen Sie einem Windows Form ein WPF-Steuerelement hinzu</span><span class="sxs-lookup"><span data-stu-id="41033-142">To add a WPF control to a Windows Form</span></span>

1. <span data-ttu-id="41033-143">Öffnen Sie `Form1` im Windows Forms-Designer.</span><span class="sxs-lookup"><span data-stu-id="41033-143">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="41033-144">In der **Toolbox**, suchen Sie die Registerkarte mit der Bezeichnung **WPFUserControlLibrary WPF-Benutzersteuerelemente**.</span><span class="sxs-lookup"><span data-stu-id="41033-144">In the **Toolbox**, find the tab labeled **WPFUserControlLibrary WPF User Controls**.</span></span>

3. <span data-ttu-id="41033-145">Ziehen Sie eine Instanz von `UserControl1` auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="41033-145">Drag an instance of `UserControl1` onto the form.</span></span>

    - <span data-ttu-id="41033-146">Ein <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement wird automatisch zum Hosten des WPF-Steuerelements auf dem Formular erstellt.</span><span class="sxs-lookup"><span data-stu-id="41033-146">An <xref:System.Windows.Forms.Integration.ElementHost> control is created automatically on the form to host the WPF control.</span></span>

    - <span data-ttu-id="41033-147">Die <xref:System.Windows.Forms.Integration.ElementHost> -Steuerelement heißt `elementHost1` und klicken Sie in der **Eigenschaften** Fenster können Sie sehen die <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> -Eigenschaftensatz auf **"UserControl1"**.</span><span class="sxs-lookup"><span data-stu-id="41033-147">The <xref:System.Windows.Forms.Integration.ElementHost> control is named `elementHost1` and in the **Properties** window, you can see its <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl1**.</span></span>

    - <span data-ttu-id="41033-148">Verweise auf WPF-Assemblys werden dem Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="41033-148">References to WPF assemblies are added to the project.</span></span>

    - <span data-ttu-id="41033-149">Das `elementHost1`-Steuerelement verfügt über einen Smarttagbereich, in dem die verfügbaren Hostingoptionen anzeigt werden.</span><span class="sxs-lookup"><span data-stu-id="41033-149">The `elementHost1` control has a smart tag panel that shows the available hosting options.</span></span>

4. <span data-ttu-id="41033-150">In der **ElementHost-Aufgaben** wählen Sie im Smarttagbereich **in übergeordnetem Container Andocken**.</span><span class="sxs-lookup"><span data-stu-id="41033-150">In the **ElementHost Tasks** smart tag panel, select **Dock in parent container**.</span></span>

5. <span data-ttu-id="41033-151">Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="41033-151">Press **F5** to build and run the application.</span></span>

## <a name="next-steps"></a><span data-ttu-id="41033-152">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="41033-152">Next Steps</span></span>

<span data-ttu-id="41033-153">Windows Forms und WPF sind unterschiedliche Technologien, wurden aber für eine enge Zusammenarbeit entwickelt.</span><span class="sxs-lookup"><span data-stu-id="41033-153">Windows Forms and WPF are different technologies, but they are designed to interoperate closely.</span></span> <span data-ttu-id="41033-154">Um umfangreichere Darstellung und Verhalten in Ihren Anwendungen bereitzustellen, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="41033-154">To provide richer appearance and behavior in your applications, try the following:</span></span>

- <span data-ttu-id="41033-155">Hosten eines Windows Forms-Steuerelements in einer WPF-Seite.</span><span class="sxs-lookup"><span data-stu-id="41033-155">Host a Windows Forms control in a WPF page.</span></span> <span data-ttu-id="41033-156">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Hosten ein Windows Forms-Steuerelements in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="41033-156">For more information, see [Walkthrough: Hosting a Windows Forms Control in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span></span>

- <span data-ttu-id="41033-157">Übernehmen von visuellen Windows Forms-Stilen für den WPF-Inhalt.</span><span class="sxs-lookup"><span data-stu-id="41033-157">Apply Windows Forms visual styles to your WPF content.</span></span> <span data-ttu-id="41033-158">Weitere Informationen finden Sie unter [Vorgehensweise: Aktivieren von visuellen Stilen in einer Hybridanwendung](../../../../docs/framework/wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).</span><span class="sxs-lookup"><span data-stu-id="41033-158">For more information, see [How to: Enable Visual Styles in a Hybrid Application](../../../../docs/framework/wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).</span></span>

- <span data-ttu-id="41033-159">Ändern des Stils des WPF-Inhalts.</span><span class="sxs-lookup"><span data-stu-id="41033-159">Change the style of your WPF content.</span></span> <span data-ttu-id="41033-160">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Formatieren von WPF-Inhalt](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md).</span><span class="sxs-lookup"><span data-stu-id="41033-160">For more information, see [Walkthrough: Styling WPF Content](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="41033-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41033-161">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="41033-162">Migration und Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="41033-162">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="41033-163">Verwenden von WPF-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="41033-163">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)
- [<span data-ttu-id="41033-164">Entwerfen von XAML-Code in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="41033-164">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
