---
title: 'Exemplarische Vorgehensweise: Hosten eines zusammengesetzten 3D-WPF-Steuerelements in Windows Forms'
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
- composite controls [WPF], hosting WPF in
ms.assetid: 486369a9-606a-4a3b-b086-a06f2119c7b0
ms.openlocfilehash: d32b98fce3cf5e4fe82745c3d0ba8992ee75339e
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2019
ms.locfileid: "56746204"
---
# <a name="walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms"></a><span data-ttu-id="12cfd-102">Exemplarische Vorgehensweise: Hosten eines zusammengesetzten 3D-WPF-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="12cfd-102">Walkthrough: Hosting a 3-D WPF Composite Control in Windows Forms</span></span>

<span data-ttu-id="12cfd-103">In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie kann eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zusammengesetzten steuern und hosten Sie es in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] -Steuerelementen und-Formularen mithilfe der <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="12cfd-103">This walkthrough demonstrates how you can create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] composite control and host it in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls and forms by using the <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

<span data-ttu-id="12cfd-104">In dieser exemplarischen Vorgehensweise implementieren Sie eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> , das zwei untergeordnete Steuerelemente enthält.</span><span class="sxs-lookup"><span data-stu-id="12cfd-104">In this walkthrough, you will implement a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> that contains two child controls.</span></span> <span data-ttu-id="12cfd-105">Die <xref:System.Windows.Controls.UserControl> zeigt einen Kegel der dreidimensionalen (3D).</span><span class="sxs-lookup"><span data-stu-id="12cfd-105">The <xref:System.Windows.Controls.UserControl> displays a three-dimensional (3-D) cone.</span></span> <span data-ttu-id="12cfd-106">3D-Objekte zu rendern ist viel einfacher, mit der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] als mit [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12cfd-106">Rendering 3-D objects is much easier with the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] than with [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="12cfd-107">Aus diesem Grund ist es sinnvoll, auf Host eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> -Klasse zur Erstellung von 3D-Grafiken in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12cfd-107">Therefore, it makes sense to host a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> class to create 3-D graphics in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span>

<span data-ttu-id="12cfd-108">In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="12cfd-108">Tasks illustrated in this walkthrough include:</span></span>

-   <span data-ttu-id="12cfd-109">Erstellen der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="12cfd-109">Creating the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>

-   <span data-ttu-id="12cfd-110">Erstellen die Windows Forms-Hostprojekts.</span><span class="sxs-lookup"><span data-stu-id="12cfd-110">Creating the Windows Forms host project.</span></span>

-   <span data-ttu-id="12cfd-111">Hosten der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="12cfd-111">Hosting the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="12cfd-112">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="12cfd-112">Prerequisites</span></span>

<span data-ttu-id="12cfd-113">Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="12cfd-113">You need the following components to complete this walkthrough:</span></span>

-   <span data-ttu-id="12cfd-114">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="12cfd-114">Visual Studio 2017</span></span>

<a name="To_Create_the_UserControl"></a>
## <a name="create-the-usercontrol"></a><span data-ttu-id="12cfd-115">Erstellen Sie das UserControl-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="12cfd-115">Create the UserControl</span></span>

1.  <span data-ttu-id="12cfd-116">Erstellen Sie eine **WPF-Benutzersteuerelementbibliothek** Projekt mit dem Namen `HostingWpfUserControlInWf`.</span><span class="sxs-lookup"><span data-stu-id="12cfd-116">Create a **WPF User Control Library** project named `HostingWpfUserControlInWf`.</span></span>

2.  <span data-ttu-id="12cfd-117">Öffnen Sie die Datei UserControl1.xaml im der [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12cfd-117">Open UserControl1.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>

3.  <span data-ttu-id="12cfd-118">Ersetzen Sie den generierten Code durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="12cfd-118">Replace the generated code with the following code:</span></span>

     [!code-xaml[HostingWpfUserControlInWf#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]

     <span data-ttu-id="12cfd-119">Dieser Code definiert eine <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> , das zwei untergeordnete Steuerelemente enthält.</span><span class="sxs-lookup"><span data-stu-id="12cfd-119">This code defines a <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> that contains two child controls.</span></span> <span data-ttu-id="12cfd-120">Das erste untergeordnete Steuerelement ist ein <xref:System.Windows.Controls.Label?displayProperty=nameWithType> Steuerelement, das zweite ist ein <xref:System.Windows.Controls.Viewport3D> Steuerelement, das einen 3D-Kegel anzeigt.</span><span class="sxs-lookup"><span data-stu-id="12cfd-120">The first child control is a <xref:System.Windows.Controls.Label?displayProperty=nameWithType> control; the second is a <xref:System.Windows.Controls.Viewport3D> control that displays a 3-D cone.</span></span>

<a name="To_Create_the_Windows_Forms_Host_Project"></a>
## <a name="create-the-host-project"></a><span data-ttu-id="12cfd-121">Erstellen des Hostprojekts</span><span class="sxs-lookup"><span data-stu-id="12cfd-121">Create the host project</span></span>

1.  <span data-ttu-id="12cfd-122">Hinzufügen einer **WPF-App ((.NET Framework)** Projekt mit dem Namen `WpfUserControlHost` der Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="12cfd-122">Add a **WPF App (.NET Framework)** project named `WpfUserControlHost` to the solution.</span></span> <span data-ttu-id="12cfd-123">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span><span class="sxs-lookup"><span data-stu-id="12cfd-123">For more information, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

2.  <span data-ttu-id="12cfd-124">In **Projektmappen-Explorer**, fügen Sie einen Verweis auf die Assembly "WindowsFormsIntegration", mit dem Namen WindowsFormsIntegration.dll.</span><span class="sxs-lookup"><span data-stu-id="12cfd-124">In **Solution Explorer**, add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

3.  <span data-ttu-id="12cfd-125">Fügen Sie Verweise auf die folgenden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Assemblys:</span><span class="sxs-lookup"><span data-stu-id="12cfd-125">Add references to the following [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assemblies:</span></span>

    -   <span data-ttu-id="12cfd-126">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="12cfd-126">PresentationCore</span></span>

    -   <span data-ttu-id="12cfd-127">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="12cfd-127">PresentationFramework</span></span>

    -   <span data-ttu-id="12cfd-128">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="12cfd-128">WindowsBase</span></span>

4.  <span data-ttu-id="12cfd-129">Fügen einen Verweis auf das `HostingWpfUserControlInWf`-Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="12cfd-129">Add a reference to the `HostingWpfUserControlInWf` project.</span></span>

5.  <span data-ttu-id="12cfd-130">Legen Sie im Projektmappen-Explorer die `WpfUserControlHost` Projekt das Startprojekt sein.</span><span class="sxs-lookup"><span data-stu-id="12cfd-130">In Solution Explorer, set the `WpfUserControlHost` project to be the startup project.</span></span>

<a name="To_Host_the_Windows_Presentation_Foundation"></a>
## <a name="host-the-usercontrol"></a><span data-ttu-id="12cfd-131">Hosten Sie das UserControl-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="12cfd-131">Host the UserControl</span></span>

1.  <span data-ttu-id="12cfd-132">Öffnen Sie Form1 im Windows Forms-Designer.</span><span class="sxs-lookup"><span data-stu-id="12cfd-132">In the Windows Forms Designer, open Form1.</span></span>

2.  <span data-ttu-id="12cfd-133">Klicken Sie im Fenster Eigenschaften auf **Ereignisse**, und doppelklicken Sie dann auf die <xref:System.Windows.Forms.Form.Load> Ereignis, um einen Ereignishandler erstellen.</span><span class="sxs-lookup"><span data-stu-id="12cfd-133">In the Properties window, click **Events**, and then double-click the <xref:System.Windows.Forms.Form.Load> event to create an event handler.</span></span>

     <span data-ttu-id="12cfd-134">Der Code-Editor wird geöffnet, mit dem neu generierten `Form1_Load` -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="12cfd-134">The Code Editor opens to the newly generated `Form1_Load` event handler.</span></span>

3.  <span data-ttu-id="12cfd-135">Ersetzen Sie den Code in "Form1.cs" durch den folgenden Code ein.</span><span class="sxs-lookup"><span data-stu-id="12cfd-135">Replace the code in Form1.cs with the following code.</span></span>

     <span data-ttu-id="12cfd-136">Die `Form1_Load` -Ereignishandler erstellt eine Instanz des `UserControl1` und fügt hinzu, auf die <xref:System.Windows.Forms.Integration.ElementHost> des Steuerelements Auflistung von untergeordneten Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="12cfd-136">The `Form1_Load` event handler creates an instance of `UserControl1` and adds itto the <xref:System.Windows.Forms.Integration.ElementHost> control's collection of child controls.</span></span> <span data-ttu-id="12cfd-137">Die <xref:System.Windows.Forms.Integration.ElementHost> -Steuerelement des Formulars die Auflistung der untergeordneten Steuerelemente hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="12cfd-137">The <xref:System.Windows.Forms.Integration.ElementHost> control is added to the form's collection of child controls.</span></span>

     [!code-csharp[HostingWpfUserControlInWf#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]

4.  <span data-ttu-id="12cfd-138">Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="12cfd-138">Press **F5** to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="12cfd-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12cfd-139">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="12cfd-140">Entwerfen von XAML-Code in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="12cfd-140">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="12cfd-141">Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="12cfd-141">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="12cfd-142">Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF</span><span class="sxs-lookup"><span data-stu-id="12cfd-142">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="12cfd-143">Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms-Beispiel</span><span class="sxs-lookup"><span data-stu-id="12cfd-143">Hosting a WPF Composite Control in Windows Forms Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160001)