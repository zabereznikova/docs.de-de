---
title: 'Exemplarische Vorgehensweise: Anordnen von WPF-Inhalt in Windows Forms zur Entwurfszeit'
ms.date: 08/18/2018
helpviewer_keywords:
- interoperability [Windows Forms], WPF and Windows Forms
- WPF content [Windows Forms], hosting in Windows Forms
- hosting WPF content in Windows Forms
- ElementHost control
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 2e92d8e8-f0e4-4df7-9f07-2acf35cd798c
ms.openlocfilehash: 889e81053d4e2264755468446a4e1681216ae22e
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040374"
---
# <a name="walkthrough-create-new-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="18211-102">Exemplarische Vorgehensweise: Erstellen eines neuen WPF-Inhalts auf Windows Forms zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="18211-102">Walkthrough: Create new WPF content on Windows Forms at design time</span></span>

<span data-ttu-id="18211-103">In diesem Artikel erfahren Sie, wie Sie ein Windows Presentation Foundation-Steuerelement (WPF) für die Verwendung in Ihren Windows Forms basierten Anwendungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="18211-103">This article shows you how to create a Windows Presentation Foundation (WPF) control for use in your Windows Forms-based applications.</span></span>

<span data-ttu-id="18211-104">Im Verlauf dieser exemplarischen Vorgehensweise führen Sie folgende Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="18211-104">In this walkthrough, you perform the following tasks:</span></span>

- <span data-ttu-id="18211-105">Erstellen eines Projekts</span><span class="sxs-lookup"><span data-stu-id="18211-105">Create the project.</span></span>

- <span data-ttu-id="18211-106">Erstellen eines neuen WPF-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="18211-106">Create a new WPF control.</span></span>

- <span data-ttu-id="18211-107">Hinzufügen des neuen WPF-Steuerelements zu einem Windows Form.</span><span class="sxs-lookup"><span data-stu-id="18211-107">Add the new WPF control to a Windows Form.</span></span> <span data-ttu-id="18211-108">Das WPF-Steuerelement wird in einem <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement gehostet.</span><span class="sxs-lookup"><span data-stu-id="18211-108">The WPF control is hosted in an <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="18211-109">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="18211-109">Prerequisites</span></span>

<span data-ttu-id="18211-110">Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="18211-110">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="18211-111">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="18211-111">Visual Studio</span></span>

## <a name="create-the-project"></a><span data-ttu-id="18211-112">Erstellen eines Projekts</span><span class="sxs-lookup"><span data-stu-id="18211-112">Create the project</span></span>

<span data-ttu-id="18211-113">Zunächst muss das Windows Forms-Projekt erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="18211-113">The first step is to create the Windows Forms project.</span></span> <span data-ttu-id="18211-114">Öffnen Sie Visual Studio, und erstellen Sie ein neues Projekt **Windows Forms app (.NET Framework)** in C# Visual Basic `HostingWpf`oder Visual mit dem Namen.</span><span class="sxs-lookup"><span data-stu-id="18211-114">Open Visual Studio and create a new **Windows Forms App (.NET Framework)** project in Visual Basic or Visual C# named `HostingWpf`.</span></span>

> [!NOTE]
> <span data-ttu-id="18211-115">Beim Hosten von WPF-Inhalt werden nur C#- und Visual Basic-Projekte unterstützt.</span><span class="sxs-lookup"><span data-stu-id="18211-115">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-a-new-wpf-control"></a><span data-ttu-id="18211-116">Erstellen eines neuen WPF-Steuer Elements</span><span class="sxs-lookup"><span data-stu-id="18211-116">Create a new WPF control</span></span>

<span data-ttu-id="18211-117">Das Erstellen eines neuen WPF-Steuerelements und das Hinzufügen des Steuerelements zum Projekt ist genauso einfach wie das Hinzufügen eines beliebigen anderen Elements zum Projekt.</span><span class="sxs-lookup"><span data-stu-id="18211-117">Creating a new WPF control and adding it to your project is as easy as adding any other item to your project.</span></span> <span data-ttu-id="18211-118">Der Windows Forms-Designer funktioniert mit einer bestimmten Art von Steuerelement, das als zusammen *gesetztes Steuer*Element oder *Benutzer Steuer*Element bezeichnet wird</span><span class="sxs-lookup"><span data-stu-id="18211-118">The Windows Forms Designer works with a particular kind of control named *composite control*, or *user control*.</span></span> <span data-ttu-id="18211-119">Weitere Informationen zu benutzerdefinierten WPF-Steuerelementen finden Sie unter <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="18211-119">For more information about WPF user controls, see <xref:System.Windows.Controls.UserControl>.</span></span>

> [!NOTE]
> <span data-ttu-id="18211-120">Der <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType>-Typ für WPF unterscheidet sich vom Windows Forms-Benutzersteuerelementtyp, der ebenfalls den Namen <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType> hat.</span><span class="sxs-lookup"><span data-stu-id="18211-120">The <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> type for WPF is distinct from the user control type provided by Windows Forms, which is also named <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="18211-121">So erstellen Sie ein neues WPF-Steuerelement:</span><span class="sxs-lookup"><span data-stu-id="18211-121">To create a new WPF control:</span></span>

1. <span data-ttu-id="18211-122">Fügen Sie in **Projektmappen-Explorer**der Projekt Mappe ein neues Projekt für eine **WPF-Benutzer Steuerelement Bibliothek (.NET Framework)** hinzu.</span><span class="sxs-lookup"><span data-stu-id="18211-122">In **Solution Explorer**, add a new **WPF User Control Library (.NET Framework)** project to the solution.</span></span> <span data-ttu-id="18211-123">Verwenden Sie den Standardnamen `WpfControlLibrary1` für die Steuerelementbibliothek.</span><span class="sxs-lookup"><span data-stu-id="18211-123">Use the default name for the control library, `WpfControlLibrary1`.</span></span> <span data-ttu-id="18211-124">Der Standardname für das Steuerelement lautet `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="18211-124">The default control name is `UserControl1.xaml`.</span></span>

     <span data-ttu-id="18211-125">Das Hinzufügen des neuen Steuer Elements hat die folgenden Auswirkungen:</span><span class="sxs-lookup"><span data-stu-id="18211-125">Adding the new control has the following effects:</span></span>

    - <span data-ttu-id="18211-126">Die Datei UserControl1.xaml wird hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="18211-126">File UserControl1.xaml is added.</span></span>

    - <span data-ttu-id="18211-127">Hinzugefügt wird entweder die Datei UserControl1.xaml.cs oder die Datei UserControl1.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="18211-127">Either file UserControl1.xaml.cs or UserControl1.xaml.vb is added.</span></span> <span data-ttu-id="18211-128">Diese Datei enthält das Code-Behind-Modell für Ereignishandler und andere Implementierungen.</span><span class="sxs-lookup"><span data-stu-id="18211-128">This file contains the code-behind for event handlers and other implementation.</span></span>

    - <span data-ttu-id="18211-129">Es werden Verweise auf die WPF-Assemblys hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="18211-129">References to WPF assemblies are added.</span></span>

    - <span data-ttu-id="18211-130">Die Datei UserControl1.xaml wird in [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] geöffnet.</span><span class="sxs-lookup"><span data-stu-id="18211-130">File UserControl1.xaml opens in the [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)].</span></span>

2. <span data-ttu-id="18211-131">Stellen Sie in der Entwurfsansicht sicher, dass `UserControl1` ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="18211-131">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="18211-132">Weitere Informationen finden Sie unter [Vorgehensweise: Auswählen und Verschieben von Elementen auf der](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100))Designoberfläche</span><span class="sxs-lookup"><span data-stu-id="18211-132">For more information, see [How to: Select and Move Elements on the Design Surface](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span></span>

3. <span data-ttu-id="18211-133">Legen Sie im Fenster **Eigenschaften** den Wert <xref:System.Windows.FrameworkElement.Width%2A> der-Eigenschaft und der- <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaft auf 200 fest.</span><span class="sxs-lookup"><span data-stu-id="18211-133">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="18211-134">Ziehen Sie aus der **Toolbox**ein <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> -Steuerelement auf die Entwurfs Oberfläche.</span><span class="sxs-lookup"><span data-stu-id="18211-134">From the **Toolbox**, drag a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control onto the design surface.</span></span>

5. <span data-ttu-id="18211-135">Legen Sie im Fenster **Eigenschaften** den Wert <xref:System.Windows.Controls.TextBox.Text%2A> der-Eigenschaft auf **gehosteter Inhalt**fest.</span><span class="sxs-lookup"><span data-stu-id="18211-135">In the **Properties** window, set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="18211-136">Normalerweise sollten Sie anspruchsvolleren WPF-Inhalt hosten.</span><span class="sxs-lookup"><span data-stu-id="18211-136">In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="18211-137"><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>-Steuerelement wird hier nur zur Veranschaulichung verwendet.</span><span class="sxs-lookup"><span data-stu-id="18211-137">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>

6. <span data-ttu-id="18211-138">Erstellen Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="18211-138">Build the project.</span></span>

## <a name="add-a-wpf-control-to-a-windows-form"></a><span data-ttu-id="18211-139">Hinzufügen eines WPF-Steuer Elements zu einem Windows Form</span><span class="sxs-lookup"><span data-stu-id="18211-139">Add a WPF control to a Windows Form</span></span>

<span data-ttu-id="18211-140">Das neue WPF-Steuerelement kann jetzt im Formular verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="18211-140">Your new WPF control is ready for use on the form.</span></span> <span data-ttu-id="18211-141">Windows Forms verwendet das <xref:System.Windows.Forms.Integration.ElementHost> -Steuerelement zum Hosten von WPF-Inhalt.</span><span class="sxs-lookup"><span data-stu-id="18211-141">Windows Forms uses the <xref:System.Windows.Forms.Integration.ElementHost> control to host WPF content.</span></span>

<span data-ttu-id="18211-142">So fügen Sie einem Windows Form ein WPF-Steuerelement hinzu:</span><span class="sxs-lookup"><span data-stu-id="18211-142">To add a WPF control to a Windows Form:</span></span>

1. <span data-ttu-id="18211-143">Öffnen Sie `Form1` im Windows Forms-Designer.</span><span class="sxs-lookup"><span data-stu-id="18211-143">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="18211-144">Suchen Sie in der **Toolbox**die Registerkarte mit der Bezeichnung **wpfusercontrollibrary WPF-Benutzer Steuerelemente**.</span><span class="sxs-lookup"><span data-stu-id="18211-144">In the **Toolbox**, find the tab labeled **WPFUserControlLibrary WPF User Controls**.</span></span>

3. <span data-ttu-id="18211-145">Ziehen Sie eine Instanz von `UserControl1` auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="18211-145">Drag an instance of `UserControl1` onto the form.</span></span>

    - <span data-ttu-id="18211-146">Ein <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement wird automatisch zum Hosten des WPF-Steuerelements auf dem Formular erstellt.</span><span class="sxs-lookup"><span data-stu-id="18211-146">An <xref:System.Windows.Forms.Integration.ElementHost> control is created automatically on the form to host the WPF control.</span></span>

    - <span data-ttu-id="18211-147">Das <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement hat `elementHost1` den Namen, <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> und im Fenster Eigenschaften wird die-Eigenschaft auf **UserControl1**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="18211-147">The <xref:System.Windows.Forms.Integration.ElementHost> control is named `elementHost1` and in the **Properties** window, you can see its <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl1**.</span></span>

    - <span data-ttu-id="18211-148">Verweise auf WPF-Assemblys werden dem Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="18211-148">References to WPF assemblies are added to the project.</span></span>

    - <span data-ttu-id="18211-149">Das `elementHost1`-Steuerelement verfügt über einen Smarttagbereich, in dem die verfügbaren Hostingoptionen anzeigt werden.</span><span class="sxs-lookup"><span data-stu-id="18211-149">The `elementHost1` control has a smart tag panel that shows the available hosting options.</span></span>

4. <span data-ttu-id="18211-150">Wählen Sie im Smarttagbereich **elemelthost Tasks** die Option in übergeordnetem **Container andocken**.</span><span class="sxs-lookup"><span data-stu-id="18211-150">In the **ElementHost Tasks** smart tag panel, select **Dock in parent container**.</span></span>

5. <span data-ttu-id="18211-151">Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="18211-151">Press **F5** to build and run the application.</span></span>

## <a name="next-steps"></a><span data-ttu-id="18211-152">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="18211-152">Next steps</span></span>

<span data-ttu-id="18211-153">Windows Forms und WPF sind unterschiedliche Technologien, wurden aber für eine enge Zusammenarbeit entwickelt.</span><span class="sxs-lookup"><span data-stu-id="18211-153">Windows Forms and WPF are different technologies, but they are designed to interoperate closely.</span></span> <span data-ttu-id="18211-154">Um die Darstellung und das Verhalten in Ihren Anwendungen zu Verb leisten, versuchen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="18211-154">To provide richer appearance and behavior in your applications, try the following:</span></span>

- <span data-ttu-id="18211-155">Hosten eines Windows Forms-Steuerelements in einer WPF-Seite.</span><span class="sxs-lookup"><span data-stu-id="18211-155">Host a Windows Forms control in a WPF page.</span></span> <span data-ttu-id="18211-156">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Hosting eines Windows Forms-Steuer Elements in](../../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)WPF.</span><span class="sxs-lookup"><span data-stu-id="18211-156">For more information, see [Walkthrough: Hosting a Windows Forms Control in WPF](../../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span></span>

- <span data-ttu-id="18211-157">Übernehmen von visuellen Windows Forms-Stilen für den WPF-Inhalt.</span><span class="sxs-lookup"><span data-stu-id="18211-157">Apply Windows Forms visual styles to your WPF content.</span></span> <span data-ttu-id="18211-158">Weitere Informationen finden Sie unter [Vorgehensweise: Aktivieren von visuellen Stilen in einer Hybrid](../../wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md)Anwendung.</span><span class="sxs-lookup"><span data-stu-id="18211-158">For more information, see [How to: Enable Visual Styles in a Hybrid Application](../../wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).</span></span>

- <span data-ttu-id="18211-159">Ändern des Stils des WPF-Inhalts.</span><span class="sxs-lookup"><span data-stu-id="18211-159">Change the style of your WPF content.</span></span> <span data-ttu-id="18211-160">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Formatieren von WPF-Inhalt](walkthrough-styling-wpf-content.md).</span><span class="sxs-lookup"><span data-stu-id="18211-160">For more information, see [Walkthrough: Styling WPF Content](walkthrough-styling-wpf-content.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="18211-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="18211-161">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="18211-162">Migration und Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="18211-162">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="18211-163">Verwenden von WPF-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="18211-163">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="18211-164">Entwerfen von XAML-Code in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="18211-164">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
