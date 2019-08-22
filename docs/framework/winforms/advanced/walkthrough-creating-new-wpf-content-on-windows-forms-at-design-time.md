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
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: e3fb6e42270cc0a530646b656470ec99fcfc7f1f
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666245"
---
# <a name="walkthrough-create-new-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="a61bf-102">Exemplarische Vorgehensweise: Erstellen eines neuen WPF-Inhalts auf Windows Forms zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="a61bf-102">Walkthrough: Create new WPF content on Windows Forms at design time</span></span>

<span data-ttu-id="a61bf-103">In diesem Artikel erfahren Sie, wie Sie ein Windows Presentation Foundation-Steuerelement (WPF) für die Verwendung in Ihren Windows Forms basierten Anwendungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="a61bf-103">This article shows you how to create a Windows Presentation Foundation (WPF) control for use in your Windows Forms-based applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a61bf-104">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="a61bf-104">Prerequisites</span></span>

<span data-ttu-id="a61bf-105">Für diese exemplarische Vorgehensweise benötigen Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a61bf-105">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="a61bf-106">Erstellen eines Projekts</span><span class="sxs-lookup"><span data-stu-id="a61bf-106">Create the project</span></span>

<span data-ttu-id="a61bf-107">Zunächst muss das Windows Forms-Projekt erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="a61bf-107">The first step is to create the Windows Forms project.</span></span> <span data-ttu-id="a61bf-108">Öffnen Sie Visual Studio, und erstellen Sie ein neues Projekt **Windows Forms app (.NET Framework)** in C# Visual Basic `HostingWpf`oder Visual mit dem Namen.</span><span class="sxs-lookup"><span data-stu-id="a61bf-108">Open Visual Studio and create a new **Windows Forms App (.NET Framework)** project in Visual Basic or Visual C# named `HostingWpf`.</span></span>

> [!NOTE]
> <span data-ttu-id="a61bf-109">Beim Hosten von WPF-Inhalt werden nur C#- und Visual Basic-Projekte unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a61bf-109">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-a-new-wpf-control"></a><span data-ttu-id="a61bf-110">Erstellen eines neuen WPF-Steuer Elements</span><span class="sxs-lookup"><span data-stu-id="a61bf-110">Create a new WPF control</span></span>

<span data-ttu-id="a61bf-111">Das Erstellen eines neuen WPF-Steuerelements und das Hinzufügen des Steuerelements zum Projekt ist genauso einfach wie das Hinzufügen eines beliebigen anderen Elements zum Projekt.</span><span class="sxs-lookup"><span data-stu-id="a61bf-111">Creating a new WPF control and adding it to your project is as easy as adding any other item to your project.</span></span> <span data-ttu-id="a61bf-112">Der Windows Forms-Designer funktioniert mit einer bestimmten Art von Steuerelement, das als zusammen *gesetztes Steuer*Element oder *Benutzer Steuer*Element bezeichnet wird</span><span class="sxs-lookup"><span data-stu-id="a61bf-112">The Windows Forms Designer works with a particular kind of control named *composite control*, or *user control*.</span></span> <span data-ttu-id="a61bf-113">Weitere Informationen zu benutzerdefinierten WPF-Steuerelementen finden Sie unter <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="a61bf-113">For more information about WPF user controls, see <xref:System.Windows.Controls.UserControl>.</span></span>

> [!NOTE]
> <span data-ttu-id="a61bf-114">Der <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType>-Typ für WPF unterscheidet sich vom Windows Forms-Benutzersteuerelementtyp, der ebenfalls den Namen <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType> hat.</span><span class="sxs-lookup"><span data-stu-id="a61bf-114">The <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> type for WPF is distinct from the user control type provided by Windows Forms, which is also named <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="a61bf-115">So erstellen Sie ein neues WPF-Steuerelement:</span><span class="sxs-lookup"><span data-stu-id="a61bf-115">To create a new WPF control:</span></span>

1. <span data-ttu-id="a61bf-116">Fügen Sie in **Projektmappen-Explorer**der Projekt Mappe ein neues Projekt für eine **WPF-Benutzer Steuerelement Bibliothek (.NET Framework)** hinzu.</span><span class="sxs-lookup"><span data-stu-id="a61bf-116">In **Solution Explorer**, add a new **WPF User Control Library (.NET Framework)** project to the solution.</span></span> <span data-ttu-id="a61bf-117">Verwenden Sie den Standardnamen `WpfControlLibrary1` für die Steuerelementbibliothek.</span><span class="sxs-lookup"><span data-stu-id="a61bf-117">Use the default name for the control library, `WpfControlLibrary1`.</span></span> <span data-ttu-id="a61bf-118">Der Standardname für das Steuerelement lautet `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="a61bf-118">The default control name is `UserControl1.xaml`.</span></span>

   <span data-ttu-id="a61bf-119">Das Hinzufügen des neuen Steuer Elements hat die folgenden Auswirkungen:</span><span class="sxs-lookup"><span data-stu-id="a61bf-119">Adding the new control has the following effects:</span></span>

   - <span data-ttu-id="a61bf-120">Die Datei UserControl1.xaml wird hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a61bf-120">File UserControl1.xaml is added.</span></span>

   - <span data-ttu-id="a61bf-121">Die Datei UserControl1.XAML.cs (oder UserControl1. XAML. vb) wurde hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a61bf-121">File UserControl1.xaml.cs (or UserControl1.xaml.vb) is added.</span></span> <span data-ttu-id="a61bf-122">Diese Datei enthält das Code-Behind-Modell für Ereignishandler und andere Implementierungen.</span><span class="sxs-lookup"><span data-stu-id="a61bf-122">This file contains the code-behind for event handlers and other implementation.</span></span>

   - <span data-ttu-id="a61bf-123">Es werden Verweise auf die WPF-Assemblys hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a61bf-123">References to WPF assemblies are added.</span></span>

   - <span data-ttu-id="a61bf-124">Die Datei UserControl1. XAML wird im WPF-Designer für Visual Studio geöffnet.</span><span class="sxs-lookup"><span data-stu-id="a61bf-124">File UserControl1.xaml opens in the WPF Designer for Visual Studio.</span></span>

2. <span data-ttu-id="a61bf-125">Stellen Sie in der Entwurfsansicht sicher, dass `UserControl1` ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="a61bf-125">In Design view, make sure that `UserControl1` is selected.</span></span>

3. <span data-ttu-id="a61bf-126">Legen Sie im Fenster **Eigenschaften** den Wert <xref:System.Windows.FrameworkElement.Width%2A> der-Eigenschaft und der- <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaft auf 200 fest.</span><span class="sxs-lookup"><span data-stu-id="a61bf-126">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="a61bf-127">Ziehen Sie aus der **Toolbox**ein <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> -Steuerelement auf die Entwurfs Oberfläche.</span><span class="sxs-lookup"><span data-stu-id="a61bf-127">From the **Toolbox**, drag a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control onto the design surface.</span></span>

5. <span data-ttu-id="a61bf-128">Legen Sie im Fenster **Eigenschaften** den Wert <xref:System.Windows.Controls.TextBox.Text%2A> der-Eigenschaft auf **gehosteter Inhalt**fest.</span><span class="sxs-lookup"><span data-stu-id="a61bf-128">In the **Properties** window, set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a61bf-129">Normalerweise sollten Sie anspruchsvolleren WPF-Inhalt hosten.</span><span class="sxs-lookup"><span data-stu-id="a61bf-129">In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="a61bf-130"><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>-Steuerelement wird hier nur zur Veranschaulichung verwendet.</span><span class="sxs-lookup"><span data-stu-id="a61bf-130">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>

6. <span data-ttu-id="a61bf-131">Erstellen Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="a61bf-131">Build the project.</span></span>

## <a name="add-a-wpf-control-to-a-windows-form"></a><span data-ttu-id="a61bf-132">Hinzufügen eines WPF-Steuer Elements zu einem Windows Form</span><span class="sxs-lookup"><span data-stu-id="a61bf-132">Add a WPF control to a Windows Form</span></span>

<span data-ttu-id="a61bf-133">Das neue WPF-Steuerelement kann jetzt im Formular verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a61bf-133">Your new WPF control is ready for use on the form.</span></span> <span data-ttu-id="a61bf-134">Windows Forms verwendet das <xref:System.Windows.Forms.Integration.ElementHost> -Steuerelement zum Hosten von WPF-Inhalt.</span><span class="sxs-lookup"><span data-stu-id="a61bf-134">Windows Forms uses the <xref:System.Windows.Forms.Integration.ElementHost> control to host WPF content.</span></span>

<span data-ttu-id="a61bf-135">So fügen Sie einem Windows Form ein WPF-Steuerelement hinzu:</span><span class="sxs-lookup"><span data-stu-id="a61bf-135">To add a WPF control to a Windows Form:</span></span>

1. <span data-ttu-id="a61bf-136">Öffnen Sie `Form1` im Windows Forms-Designer.</span><span class="sxs-lookup"><span data-stu-id="a61bf-136">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="a61bf-137">Suchen Sie in der **Toolbox**die Registerkarte mit der Bezeichnung **wpfusercontrollibrary WPF-Benutzer Steuerelemente**.</span><span class="sxs-lookup"><span data-stu-id="a61bf-137">In the **Toolbox**, find the tab labeled **WPFUserControlLibrary WPF User Controls**.</span></span>

3. <span data-ttu-id="a61bf-138">Ziehen Sie eine Instanz von `UserControl1` auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="a61bf-138">Drag an instance of `UserControl1` onto the form.</span></span>

    - <span data-ttu-id="a61bf-139">Ein <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement wird automatisch zum Hosten des WPF-Steuerelements auf dem Formular erstellt.</span><span class="sxs-lookup"><span data-stu-id="a61bf-139">An <xref:System.Windows.Forms.Integration.ElementHost> control is created automatically on the form to host the WPF control.</span></span>

    - <span data-ttu-id="a61bf-140">Das <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement hat `elementHost1` den Namen, <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> und im Fenster Eigenschaften wird die-Eigenschaft auf **UserControl1**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a61bf-140">The <xref:System.Windows.Forms.Integration.ElementHost> control is named `elementHost1` and in the **Properties** window, you can see its <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl1**.</span></span>

    - <span data-ttu-id="a61bf-141">Verweise auf WPF-Assemblys werden dem Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a61bf-141">References to WPF assemblies are added to the project.</span></span>

    - <span data-ttu-id="a61bf-142">Das `elementHost1`-Steuerelement verfügt über einen Smarttagbereich, in dem die verfügbaren Hostingoptionen anzeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a61bf-142">The `elementHost1` control has a smart tag panel that shows the available hosting options.</span></span>

4. <span data-ttu-id="a61bf-143">Wählen Sie im Smarttagbereich **elemelthost Tasks** die Option in übergeordnetem **Container andocken**.</span><span class="sxs-lookup"><span data-stu-id="a61bf-143">In the **ElementHost Tasks** smart tag panel, select **Dock in parent container**.</span></span>

5. <span data-ttu-id="a61bf-144">Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a61bf-144">Press **F5** to build and run the application.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a61bf-145">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="a61bf-145">Next steps</span></span>

<span data-ttu-id="a61bf-146">Windows Forms und WPF sind unterschiedliche Technologien, wurden aber für eine enge Zusammenarbeit entwickelt.</span><span class="sxs-lookup"><span data-stu-id="a61bf-146">Windows Forms and WPF are different technologies, but they are designed to interoperate closely.</span></span> <span data-ttu-id="a61bf-147">Um die Darstellung und das Verhalten in Ihren Anwendungen zu Verb leisten, versuchen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="a61bf-147">To provide richer appearance and behavior in your applications, try the following:</span></span>

- <span data-ttu-id="a61bf-148">Hosten eines Windows Forms-Steuerelements in einer WPF-Seite.</span><span class="sxs-lookup"><span data-stu-id="a61bf-148">Host a Windows Forms control in a WPF page.</span></span> <span data-ttu-id="a61bf-149">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Hosting eines Windows Forms-Steuer Elements in](../../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)WPF.</span><span class="sxs-lookup"><span data-stu-id="a61bf-149">For more information, see [Walkthrough: Hosting a Windows Forms Control in WPF](../../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span></span>

- <span data-ttu-id="a61bf-150">Übernehmen von visuellen Windows Forms-Stilen für den WPF-Inhalt.</span><span class="sxs-lookup"><span data-stu-id="a61bf-150">Apply Windows Forms visual styles to your WPF content.</span></span> <span data-ttu-id="a61bf-151">Weitere Informationen finden Sie unter [Vorgehensweise: Aktivieren von visuellen Stilen in einer Hybrid](../../wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md)Anwendung.</span><span class="sxs-lookup"><span data-stu-id="a61bf-151">For more information, see [How to: Enable Visual Styles in a Hybrid Application](../../wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).</span></span>

- <span data-ttu-id="a61bf-152">Ändern des Stils des WPF-Inhalts.</span><span class="sxs-lookup"><span data-stu-id="a61bf-152">Change the style of your WPF content.</span></span> <span data-ttu-id="a61bf-153">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Formatieren von WPF-Inhalt](walkthrough-styling-wpf-content.md).</span><span class="sxs-lookup"><span data-stu-id="a61bf-153">For more information, see [Walkthrough: Styling WPF Content](walkthrough-styling-wpf-content.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a61bf-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a61bf-154">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="a61bf-155">Migration und Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="a61bf-155">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="a61bf-156">Verwenden von WPF-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="a61bf-156">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="a61bf-157">Entwerfen von XAML-Code in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a61bf-157">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
