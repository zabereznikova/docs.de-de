---
title: 'Exemplarische Vorgehensweise: Erstellen neuen WPF-Inhalts in Windows Forms zur Entwurfszeit'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interoperability [Windows Forms], WPF and Windows Forms
- WPF content [Windows Forms], hosting in Windows Forms
- hosting WPF content in Windows Forms
- ElementHost control
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 2e92d8e8-f0e4-4df7-9f07-2acf35cd798c
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cc357b8ad1ff450c699878dfffe1fbb6e2440f49
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="b7bef-102">Exemplarische Vorgehensweise: Erstellen neuen WPF-Inhalts in Windows Forms zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="b7bef-102">Walkthrough: Creating New WPF Content on Windows Forms at Design Time</span></span>
<span data-ttu-id="b7bef-103">In diesem Thema wird veranschaulicht, wie Sie ein Windows Presentation Foundation-Steuerelement (WPF) zur Verwendung in Windows Forms-basierten Anwendungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="b7bef-103">This topic shows you how to create a Windows Presentation Foundation (WPF) control for use in your Windows Forms-based applications.</span></span>  
  
 <span data-ttu-id="b7bef-104">Im Verlauf dieser exemplarischen Vorgehensweise führen Sie folgende Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="b7bef-104">In this walkthrough, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="b7bef-105">Erstellen eines Projekts</span><span class="sxs-lookup"><span data-stu-id="b7bef-105">Create the project.</span></span>  
  
-   <span data-ttu-id="b7bef-106">Erstellen eines neuen WPF-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="b7bef-106">Create a new WPF control.</span></span>  
  
-   <span data-ttu-id="b7bef-107">Hinzufügen des neuen WPF-Steuerelements zu einem Windows Form.</span><span class="sxs-lookup"><span data-stu-id="b7bef-107">Add the new WPF control to a Windows Form.</span></span> <span data-ttu-id="b7bef-108">Das WPF-Steuerelement wird in einem <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement gehostet.</span><span class="sxs-lookup"><span data-stu-id="b7bef-108">The WPF control is hosted in an <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b7bef-109">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="b7bef-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="b7bef-110">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="b7bef-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="b7bef-111">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="b7bef-111">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b7bef-112">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="b7bef-112">Prerequisites</span></span>  
 <span data-ttu-id="b7bef-113">Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="b7bef-113">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)]<span data-ttu-id="b7bef-114">.</span><span class="sxs-lookup"><span data-stu-id="b7bef-114">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="b7bef-115">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="b7bef-115">Creating the Project</span></span>  
 <span data-ttu-id="b7bef-116">Zunächst muss das Windows Forms-Projekt erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="b7bef-116">The first step is to create the Windows Forms project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b7bef-117">Beim Hosten von WPF-Inhalt werden nur C#- und Visual Basic-Projekte unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b7bef-117">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="b7bef-118">So erstellen Sie das Projekt</span><span class="sxs-lookup"><span data-stu-id="b7bef-118">To create the project</span></span>  
  
-   <span data-ttu-id="b7bef-119">Erstellen Sie ein neues Windows Forms-Anwendungsprojekt in Visual Basic oder Visual c# mit dem Namen `HostingWpf`.</span><span class="sxs-lookup"><span data-stu-id="b7bef-119">Create a new Windows Forms Application project in Visual Basic or Visual C# named `HostingWpf`.</span></span>  
  
## <a name="creating-a-new-wpf-control"></a><span data-ttu-id="b7bef-120">Erstellen eines neuen WPF-Steuerelements </span><span class="sxs-lookup"><span data-stu-id="b7bef-120">Creating a New WPF Control</span></span>  
 <span data-ttu-id="b7bef-121">Das Erstellen eines neuen WPF-Steuerelements und das Hinzufügen des Steuerelements zum Projekt ist genauso einfach wie das Hinzufügen eines beliebigen anderen Elements zum Projekt.</span><span class="sxs-lookup"><span data-stu-id="b7bef-121">Creating a new WPF control and adding it to your project is as easy as adding any other item to your project.</span></span> <span data-ttu-id="b7bef-122">Windows Forms-Designer funktioniert mit einer bestimmten Art von Steuerelement namens *zusammengesetztes Steuerelement*, oder *Benutzersteuerelement*.</span><span class="sxs-lookup"><span data-stu-id="b7bef-122">The Windows Forms Designer works with a particular kind of control named *composite control*, or *user control*.</span></span> <span data-ttu-id="b7bef-123">Weitere Informationen zu benutzerdefinierten WPF-Steuerelementen finden Sie unter <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="b7bef-123">For more information about WPF user controls, see <xref:System.Windows.Controls.UserControl>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b7bef-124">Der <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType>-Typ für WPF unterscheidet sich vom Windows Forms-Benutzersteuerelementtyp, der ebenfalls den Namen <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType> hat.
</span><span class="sxs-lookup"><span data-stu-id="b7bef-124">The <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> type for WPF is distinct from the user control type provided by Windows Forms, which is also named <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>.</span></span>  
  
#### <a name="to-create-a-new-wpf-control"></a><span data-ttu-id="b7bef-125">So erstellen Sie ein neues WPF-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="b7bef-125">To create a new WPF control</span></span>  
  
1.  <span data-ttu-id="b7bef-126">In **Projektmappen-Explorer**, fügen Sie einen neuen **WPF-Benutzersteuerelementbibliothek** Projekt der Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="b7bef-126">In **Solution Explorer**, add a new **WPF User Control Library** project to the solution.</span></span> <span data-ttu-id="b7bef-127">Verwenden Sie den Standardnamen `WpfControlLibrary1` für die Steuerelementbibliothek.</span><span class="sxs-lookup"><span data-stu-id="b7bef-127">Use the default name for the control library, `WpfControlLibrary1`.</span></span> <span data-ttu-id="b7bef-128">Der Standardname für das Steuerelement lautet `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="b7bef-128">The default control name is `UserControl1.xaml`.</span></span>  
  
     <span data-ttu-id="b7bef-129">Das Hinzufügen des neuen Steuerelements hat folgende Auswirkungen:</span><span class="sxs-lookup"><span data-stu-id="b7bef-129">Adding the new control has the following effects.</span></span>  
  
    -   <span data-ttu-id="b7bef-130">Die Datei UserControl1.xaml wird hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b7bef-130">File UserControl1.xaml is added.</span></span>  
  
    -   <span data-ttu-id="b7bef-131">Hinzugefügt wird entweder die Datei UserControl1.xaml.cs oder die Datei UserControl1.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="b7bef-131">Either file UserControl1.xaml.cs or UserControl1.xaml.vb is added.</span></span> <span data-ttu-id="b7bef-132">Diese Datei enthält das Code-Behind-Modell für Ereignishandler und andere Implementierungen.</span><span class="sxs-lookup"><span data-stu-id="b7bef-132">This file contains the code-behind for event handlers and other implementation.</span></span>  
  
    -   <span data-ttu-id="b7bef-133">Es werden Verweise auf die WPF-Assemblys hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b7bef-133">References to WPF assemblies are added.</span></span>  
  
    -   <span data-ttu-id="b7bef-134">Die Datei UserControl1.xaml wird in [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] geöffnet.</span><span class="sxs-lookup"><span data-stu-id="b7bef-134">File UserControl1.xaml opens in the [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="b7bef-135">Stellen Sie in der Entwurfsansicht sicher, dass `UserControl1` ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="b7bef-135">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="b7bef-136">Weitere Informationen finden Sie unter [Vorgehensweise: auswählen und Verschieben von Elementen auf der Entwurfsoberfläche](http://msdn.microsoft.com/library/54cb70b6-b35b-46e4-a0cc-65189399c474).</span><span class="sxs-lookup"><span data-stu-id="b7bef-136">For more information, see [How to: Select and Move Elements on the Design Surface](http://msdn.microsoft.com/library/54cb70b6-b35b-46e4-a0cc-65189399c474).</span></span>  
  
3.  <span data-ttu-id="b7bef-137">In der **Eigenschaften** Fenster, legen Sie den Wert von der <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften `200`.</span><span class="sxs-lookup"><span data-stu-id="b7bef-137">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>  
  
4.  <span data-ttu-id="b7bef-138">Aus der **Toolbox**, ziehen Sie eine <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> -Steuerelement auf der Entwurfsoberfläche angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b7bef-138">From the **Toolbox**, drag a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control onto the design surface.</span></span>  
  
5.  <span data-ttu-id="b7bef-139">In der **Eigenschaften** Fenster, legen Sie den Wert von der <xref:System.Windows.Controls.TextBox.Text%2A> Eigenschaft **gehosteten Inhalt**.</span><span class="sxs-lookup"><span data-stu-id="b7bef-139">In the **Properties** window, set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b7bef-140">Normalerweise sollten Sie anspruchsvolleren WPF-Inhalt hosten.</span><span class="sxs-lookup"><span data-stu-id="b7bef-140">In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="b7bef-141"><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>-Steuerelement wird hier nur zur Veranschaulichung verwendet. </span><span class="sxs-lookup"><span data-stu-id="b7bef-141">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>  
  
6.  <span data-ttu-id="b7bef-142">Erstellen Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="b7bef-142">Build the project.</span></span>  
  
## <a name="adding-a-wpf-control-to-a-windows-form"></a><span data-ttu-id="b7bef-143">Hinzufügen eines neuen WPF-Steuerelements zu einem Windows Form</span><span class="sxs-lookup"><span data-stu-id="b7bef-143">Adding a WPF Control to a Windows Form</span></span>  
 <span data-ttu-id="b7bef-144">Das neue WPF-Steuerelement kann jetzt im Formular verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b7bef-144">Your new WPF control is ready for use on the form.</span></span> <span data-ttu-id="b7bef-145">Windows Forms verwendet das <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement zum Hosten des WPF-Inhalts.</span><span class="sxs-lookup"><span data-stu-id="b7bef-145">Windows Forms uses the <xref:System.Windows.Forms.Integration.ElementHost> control to host WPF content</span></span>  
  
#### <a name="to-add-a-wpf-control-to-a-windows-form"></a><span data-ttu-id="b7bef-146">So fügen Sie einem Windows Form ein WPF-Steuerelement hinzu</span><span class="sxs-lookup"><span data-stu-id="b7bef-146">To add a WPF control to a Windows Form</span></span>  
  
1.  <span data-ttu-id="b7bef-147">Öffnen Sie `Form1` im Windows Forms-Designer.</span><span class="sxs-lookup"><span data-stu-id="b7bef-147">Open `Form1` in the Windows Forms Designer.</span></span>  
  
2.  <span data-ttu-id="b7bef-148">In der **Toolbox**, suchen Sie die Registerkarte mit der Bezeichnung **WPFUserControlLibrary WPF-Benutzersteuerelemente**.</span><span class="sxs-lookup"><span data-stu-id="b7bef-148">In the **Toolbox**, find the tab labeled **WPFUserControlLibrary WPF User Controls**.</span></span>  
  
3.  <span data-ttu-id="b7bef-149">Ziehen Sie eine Instanz von `UserControl1` auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="b7bef-149">Drag an instance of `UserControl1` onto the form.</span></span>  
  
    -   <span data-ttu-id="b7bef-150">Ein <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement wird automatisch zum Hosten des WPF-Steuerelements auf dem Formular erstellt.</span><span class="sxs-lookup"><span data-stu-id="b7bef-150">An <xref:System.Windows.Forms.Integration.ElementHost> control is created automatically on the form to host the WPF control.</span></span>  
  
    -   <span data-ttu-id="b7bef-151">Die <xref:System.Windows.Forms.Integration.ElementHost> -Steuerelement heißt `elementHost1` und klicken Sie in der **Eigenschaften** Fenster sehen Sie seine <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> -Eigenschaftensatz auf **"UserControl1"**.</span><span class="sxs-lookup"><span data-stu-id="b7bef-151">The <xref:System.Windows.Forms.Integration.ElementHost> control is named `elementHost1` and in the **Properties** window, you can see its <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl1**.</span></span>  
  
    -   <span data-ttu-id="b7bef-152">Verweise auf WPF-Assemblys werden dem Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b7bef-152">References to WPF assemblies are added to the project.</span></span>  
  
    -   <span data-ttu-id="b7bef-153">Das `elementHost1`-Steuerelement verfügt über einen Smarttagbereich, in dem die verfügbaren Hostingoptionen anzeigt werden. </span><span class="sxs-lookup"><span data-stu-id="b7bef-153">The `elementHost1` control has a smart tag panel that shows the available hosting options.</span></span>  
  
4.  <span data-ttu-id="b7bef-154">In der **ElementHost-Aufgaben** wählen Sie im Smarttagbereich **in übergeordnetem Container Andocken**.</span><span class="sxs-lookup"><span data-stu-id="b7bef-154">In the **ElementHost Tasks** smart tag panel, select **Dock in parent container**.</span></span>  
  
5.  <span data-ttu-id="b7bef-155">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b7bef-155">Press F5 to build and run the application.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="b7bef-156">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="b7bef-156">Next Steps</span></span>  
 <span data-ttu-id="b7bef-157">Windows Forms und WPF sind unterschiedliche Technologien, wurden aber für eine enge Zusammenarbeit entwickelt.</span><span class="sxs-lookup"><span data-stu-id="b7bef-157">Windows Forms and WPF are different technologies, but they are designed to interoperate closely.</span></span> <span data-ttu-id="b7bef-158">Um die Darstellung und das Verhalten in Ihren Anwendungen zu optimieren, versuchen Sie Folgendes: </span><span class="sxs-lookup"><span data-stu-id="b7bef-158">To provide richer appearance and behavior in your applications, try the following.</span></span>  
  
-   <span data-ttu-id="b7bef-159">Hosten eines Windows Forms-Steuerelements in einer WPF-Seite.</span><span class="sxs-lookup"><span data-stu-id="b7bef-159">Host a Windows Forms control in a WPF page.</span></span> <span data-ttu-id="b7bef-160">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Hosten eines Windows Forms-Steuerelements in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="b7bef-160">For more information, see [Walkthrough: Hosting a Windows Forms Control in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span></span>  
  
-   <span data-ttu-id="b7bef-161">Übernehmen von visuellen Windows Forms-Stilen für den WPF-Inhalt.</span><span class="sxs-lookup"><span data-stu-id="b7bef-161">Apply Windows Forms visual styles to your WPF content.</span></span> <span data-ttu-id="b7bef-162">Weitere Informationen finden Sie unter [Vorgehensweise: Aktivieren von visuellen Stilen in einer Hybridanwendung](../../../../docs/framework/wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).</span><span class="sxs-lookup"><span data-stu-id="b7bef-162">For more information, see [How to: Enable Visual Styles in a Hybrid Application](../../../../docs/framework/wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).</span></span>  
  
-   <span data-ttu-id="b7bef-163">Ändern des Stils des WPF-Inhalts.</span><span class="sxs-lookup"><span data-stu-id="b7bef-163">Change the style of your WPF content.</span></span> <span data-ttu-id="b7bef-164">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Formatieren von WPF-Inhalt](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md).</span><span class="sxs-lookup"><span data-stu-id="b7bef-164">For more information, see [Walkthrough: Styling WPF Content](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7bef-165">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b7bef-165">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="b7bef-166">Migration und Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="b7bef-166">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [<span data-ttu-id="b7bef-167">Verwenden von WPF-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="b7bef-167">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [<span data-ttu-id="b7bef-168">WPF-Designer</span><span class="sxs-lookup"><span data-stu-id="b7bef-168">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)
