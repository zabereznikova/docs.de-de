---
title: Neuen WPF-Inhalt auf Windows Forms erstellen
titleSuffix: ''
ms.date: 08/18/2018
helpviewer_keywords:
- interoperability [Windows Forms], WPF and Windows Forms
- WPF content [Windows Forms], hosting in Windows Forms
- hosting WPF content in Windows Forms
- ElementHost control
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 2e92d8e8-f0e4-4df7-9f07-2acf35cd798c
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 69a0598b05d1b2bff84b203317d6d5a166ce109d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746388"
---
# <a name="walkthrough-create-new-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="9660e-102">Exemplarische Vorgehensweise: Erstellen eines neuen WPF-Inhalts auf Windows Forms zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="9660e-102">Walkthrough: Create new WPF content on Windows Forms at design time</span></span>

<span data-ttu-id="9660e-103">In diesem Artikel erfahren Sie, wie Sie ein Windows Presentation Foundation-Steuerelement (WPF) für die Verwendung in Ihren Windows Forms basierten Anwendungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="9660e-103">This article shows you how to create a Windows Presentation Foundation (WPF) control for use in your Windows Forms-based applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9660e-104">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="9660e-104">Prerequisites</span></span>

<span data-ttu-id="9660e-105">Für diese exemplarische Vorgehensweise benötigen Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9660e-105">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="9660e-106">Erstellen eines Projekts</span><span class="sxs-lookup"><span data-stu-id="9660e-106">Create the project</span></span>

<span data-ttu-id="9660e-107">Öffnen Sie Visual Studio, und erstellen Sie ein neues Projekt für **Windows Forms-app (.NET Framework)** in Visual Basic oder Visual C# mit dem Namen `HostingWpf`.</span><span class="sxs-lookup"><span data-stu-id="9660e-107">Open Visual Studio and create a new **Windows Forms App (.NET Framework)** project in Visual Basic or Visual C# named `HostingWpf`.</span></span>

> [!NOTE]
> <span data-ttu-id="9660e-108">Beim Hosten von WPF-Inhalt werden nur C#- und Visual Basic-Projekte unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9660e-108">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-a-new-wpf-control"></a><span data-ttu-id="9660e-109">Erstellen eines neuen WPF-Steuer Elements</span><span class="sxs-lookup"><span data-stu-id="9660e-109">Create a new WPF control</span></span>

<span data-ttu-id="9660e-110">Das Erstellen eines neuen WPF-Steuerelements und das Hinzufügen des Steuerelements zum Projekt ist genauso einfach wie das Hinzufügen eines beliebigen anderen Elements zum Projekt.</span><span class="sxs-lookup"><span data-stu-id="9660e-110">Creating a new WPF control and adding it to your project is as easy as adding any other item to your project.</span></span> <span data-ttu-id="9660e-111">Der Windows Forms-Designer funktioniert mit einer bestimmten Art von Steuerelement, das als zusammen *gesetztes Steuer*Element oder *Benutzer Steuer*Element bezeichnet wird</span><span class="sxs-lookup"><span data-stu-id="9660e-111">The Windows Forms Designer works with a particular kind of control named *composite control*, or *user control*.</span></span> <span data-ttu-id="9660e-112">Weitere Informationen zu benutzerdefinierten WPF-Steuerelementen finden Sie unter <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="9660e-112">For more information about WPF user controls, see <xref:System.Windows.Controls.UserControl>.</span></span>

> [!NOTE]
> <span data-ttu-id="9660e-113">Der <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType>-Typ für WPF unterscheidet sich vom Windows Forms-Benutzersteuerelementtyp, der ebenfalls den Namen <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType> hat.</span><span class="sxs-lookup"><span data-stu-id="9660e-113">The <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> type for WPF is distinct from the user control type provided by Windows Forms, which is also named <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="9660e-114">So erstellen Sie ein neues WPF-Steuerelement:</span><span class="sxs-lookup"><span data-stu-id="9660e-114">To create a new WPF control:</span></span>

1. <span data-ttu-id="9660e-115">Fügen Sie in **Projektmappen-Explorer**der Projekt Mappe ein neues Projekt für eine **WPF-Benutzer Steuerelement Bibliothek (.NET Framework)** hinzu.</span><span class="sxs-lookup"><span data-stu-id="9660e-115">In **Solution Explorer**, add a new **WPF User Control Library (.NET Framework)** project to the solution.</span></span> <span data-ttu-id="9660e-116">Verwenden Sie den Standardnamen `WpfControlLibrary1` für die Steuerelementbibliothek.</span><span class="sxs-lookup"><span data-stu-id="9660e-116">Use the default name for the control library, `WpfControlLibrary1`.</span></span> <span data-ttu-id="9660e-117">Der Standardname für das Steuerelement lautet `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="9660e-117">The default control name is `UserControl1.xaml`.</span></span>

   <span data-ttu-id="9660e-118">Das Hinzufügen des neuen Steuer Elements hat die folgenden Auswirkungen:</span><span class="sxs-lookup"><span data-stu-id="9660e-118">Adding the new control has the following effects:</span></span>

   - <span data-ttu-id="9660e-119">Die Datei UserControl1.xaml wird hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="9660e-119">File UserControl1.xaml is added.</span></span>

   - <span data-ttu-id="9660e-120">Die Datei UserControl1.XAML.cs (oder UserControl1. XAML. vb) wurde hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="9660e-120">File UserControl1.xaml.cs (or UserControl1.xaml.vb) is added.</span></span> <span data-ttu-id="9660e-121">Diese Datei enthält das Code-Behind-Modell für Ereignishandler und andere Implementierungen.</span><span class="sxs-lookup"><span data-stu-id="9660e-121">This file contains the code-behind for event handlers and other implementation.</span></span>

   - <span data-ttu-id="9660e-122">Es werden Verweise auf die WPF-Assemblys hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="9660e-122">References to WPF assemblies are added.</span></span>

   - <span data-ttu-id="9660e-123">Die Datei UserControl1. XAML wird im WPF-Designer für Visual Studio geöffnet.</span><span class="sxs-lookup"><span data-stu-id="9660e-123">File UserControl1.xaml opens in the WPF Designer for Visual Studio.</span></span>

2. <span data-ttu-id="9660e-124">Stellen Sie in der Entwurfsansicht sicher, dass `UserControl1` ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="9660e-124">In Design view, make sure that `UserControl1` is selected.</span></span>

3. <span data-ttu-id="9660e-125">Legen Sie im Fenster **Eigenschaften** den Wert der Eigenschaften <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> auf **200**fest.</span><span class="sxs-lookup"><span data-stu-id="9660e-125">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="9660e-126">Ziehen Sie aus der **Toolbox**ein <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>-Steuerelement auf die Entwurfs Oberfläche.</span><span class="sxs-lookup"><span data-stu-id="9660e-126">From the **Toolbox**, drag a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control onto the design surface.</span></span>

5. <span data-ttu-id="9660e-127">Legen Sie im Fenster **Eigenschaften** den Wert der <xref:System.Windows.Controls.TextBox.Text%2A>-Eigenschaft auf **gehosteter Inhalt**fest.</span><span class="sxs-lookup"><span data-stu-id="9660e-127">In the **Properties** window, set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="9660e-128">Normalerweise sollten Sie anspruchsvolleren WPF-Inhalt hosten.</span><span class="sxs-lookup"><span data-stu-id="9660e-128">In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="9660e-129"><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>-Steuerelement wird hier nur zur Veranschaulichung verwendet.</span><span class="sxs-lookup"><span data-stu-id="9660e-129">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>

6. <span data-ttu-id="9660e-130">Erstellen Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="9660e-130">Build the project.</span></span>

## <a name="add-a-wpf-control-to-a-windows-form"></a><span data-ttu-id="9660e-131">Hinzufügen eines WPF-Steuer Elements zu einem Windows Form</span><span class="sxs-lookup"><span data-stu-id="9660e-131">Add a WPF control to a Windows Form</span></span>

<span data-ttu-id="9660e-132">Das neue WPF-Steuerelement kann jetzt im Formular verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9660e-132">Your new WPF control is ready for use on the form.</span></span> <span data-ttu-id="9660e-133">Windows Forms verwendet das <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement zum Hosten von WPF-Inhalt.</span><span class="sxs-lookup"><span data-stu-id="9660e-133">Windows Forms uses the <xref:System.Windows.Forms.Integration.ElementHost> control to host WPF content.</span></span>

<span data-ttu-id="9660e-134">So fügen Sie einem Windows Form ein WPF-Steuerelement hinzu:</span><span class="sxs-lookup"><span data-stu-id="9660e-134">To add a WPF control to a Windows Form:</span></span>

1. <span data-ttu-id="9660e-135">Öffnen Sie `Form1` im Windows Forms-Designer.</span><span class="sxs-lookup"><span data-stu-id="9660e-135">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="9660e-136">Suchen Sie in der **Toolbox**die Registerkarte mit der Bezeichnung **wpfusercontrollibrary WPF-Benutzer Steuerelemente**.</span><span class="sxs-lookup"><span data-stu-id="9660e-136">In the **Toolbox**, find the tab labeled **WPFUserControlLibrary WPF User Controls**.</span></span>

3. <span data-ttu-id="9660e-137">Ziehen Sie eine Instanz von `UserControl1` auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="9660e-137">Drag an instance of `UserControl1` onto the form.</span></span>

    - <span data-ttu-id="9660e-138">Ein <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement wird automatisch zum Hosten des WPF-Steuerelements auf dem Formular erstellt.</span><span class="sxs-lookup"><span data-stu-id="9660e-138">An <xref:System.Windows.Forms.Integration.ElementHost> control is created automatically on the form to host the WPF control.</span></span>

    - <span data-ttu-id="9660e-139">Das <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement heißt `elementHost1` und im **Eigenschaften** Fenster sehen Sie, dass seine <xref:System.Windows.Forms.Integration.ElementHost.Child%2A>-Eigenschaft auf **UserControl1**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="9660e-139">The <xref:System.Windows.Forms.Integration.ElementHost> control is named `elementHost1` and in the **Properties** window, you can see its <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl1**.</span></span>

    - <span data-ttu-id="9660e-140">Verweise auf WPF-Assemblys werden dem Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="9660e-140">References to WPF assemblies are added to the project.</span></span>

    - <span data-ttu-id="9660e-141">Das `elementHost1`-Steuerelement verfügt über einen Smarttagbereich, in dem die verfügbaren Hostingoptionen anzeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9660e-141">The `elementHost1` control has a smart tag panel that shows the available hosting options.</span></span>

4. <span data-ttu-id="9660e-142">Wählen Sie im Smarttagbereich **elemelthost Tasks** die Option in übergeordnetem **Container andocken**.</span><span class="sxs-lookup"><span data-stu-id="9660e-142">In the **ElementHost Tasks** smart tag panel, select **Dock in parent container**.</span></span>

5. <span data-ttu-id="9660e-143">Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="9660e-143">Press **F5** to build and run the application.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9660e-144">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="9660e-144">Next steps</span></span>

<span data-ttu-id="9660e-145">Windows Forms und WPF sind unterschiedliche Technologien, wurden aber für eine enge Zusammenarbeit entwickelt.</span><span class="sxs-lookup"><span data-stu-id="9660e-145">Windows Forms and WPF are different technologies, but they are designed to interoperate closely.</span></span> <span data-ttu-id="9660e-146">Um die Darstellung und das Verhalten in Ihren Anwendungen zu Verb leisten, versuchen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="9660e-146">To provide richer appearance and behavior in your applications, try the following:</span></span>

- <span data-ttu-id="9660e-147">Hosten eines Windows Forms-Steuerelements in einer WPF-Seite.</span><span class="sxs-lookup"><span data-stu-id="9660e-147">Host a Windows Forms control in a WPF page.</span></span> <span data-ttu-id="9660e-148">Weitere Informationen finden Sie unter Exemplarische Vorgehensweise [: Hosting eines Windows Forms-Steuer Elements in WPF](../../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="9660e-148">For more information, see [Walkthrough: Hosting a Windows Forms Control in WPF](../../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span></span>

- <span data-ttu-id="9660e-149">Übernehmen von visuellen Windows Forms-Stilen für den WPF-Inhalt.</span><span class="sxs-lookup"><span data-stu-id="9660e-149">Apply Windows Forms visual styles to your WPF content.</span></span> <span data-ttu-id="9660e-150">Weitere Informationen finden Sie unter [Vorgehensweise: Aktivieren von visuellen Stilen in einer Hybridanwendung](../../wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).</span><span class="sxs-lookup"><span data-stu-id="9660e-150">For more information, see [How to: Enable Visual Styles in a Hybrid Application](../../wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).</span></span>

- <span data-ttu-id="9660e-151">Ändern des Stils des WPF-Inhalts.</span><span class="sxs-lookup"><span data-stu-id="9660e-151">Change the style of your WPF content.</span></span> <span data-ttu-id="9660e-152">Weitere Informationen finden Sie unter Exemplarische Vorgehensweise: Formatieren von [WPF-Inhalt](walkthrough-styling-wpf-content.md).</span><span class="sxs-lookup"><span data-stu-id="9660e-152">For more information, see [Walkthrough: Styling WPF Content](walkthrough-styling-wpf-content.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9660e-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9660e-153">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="9660e-154">Migration und Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="9660e-154">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="9660e-155">Verwenden von WPF-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="9660e-155">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="9660e-156">Entwerfen von XAML-Code in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9660e-156">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
