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
ms.openlocfilehash: 748ab027fa8206c163578c89b94460665563cbce
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197866"
---
# <a name="walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms"></a><span data-ttu-id="1331c-102">Exemplarische Vorgehensweise: Hosten eines zusammengesetzten 3D-WPF-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1331c-102">Walkthrough: Hosting a 3-D WPF Composite Control in Windows Forms</span></span>

<span data-ttu-id="1331c-103">In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Sie ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zusammengesetztes Steuerelement erstellen und es mithilfe des <xref:System.Windows.Forms.Integration.ElementHost>-Steuer Elements in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelementen und Formularen hosten</span><span class="sxs-lookup"><span data-stu-id="1331c-103">This walkthrough demonstrates how you can create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] composite control and host it in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls and forms by using the <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

<span data-ttu-id="1331c-104">In dieser exemplarischen Vorgehensweise implementieren Sie einen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>, der zwei untergeordnete Steuerelemente enthält.</span><span class="sxs-lookup"><span data-stu-id="1331c-104">In this walkthrough, you will implement a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> that contains two child controls.</span></span> <span data-ttu-id="1331c-105">Die <xref:System.Windows.Controls.UserControl> zeigt einen dreidimensionalen (3D-) Kegel an.</span><span class="sxs-lookup"><span data-stu-id="1331c-105">The <xref:System.Windows.Controls.UserControl> displays a three-dimensional (3-D) cone.</span></span> <span data-ttu-id="1331c-106">Das Rendern von 3D-Objekten ist mit dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wesentlich einfacher als mit [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1331c-106">Rendering 3-D objects is much easier with the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] than with [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="1331c-107">Daher ist es sinnvoll, eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> Klasse zu hosten, um 3D-Grafiken in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1331c-107">Therefore, it makes sense to host a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> class to create 3-D graphics in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span>

<span data-ttu-id="1331c-108">In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="1331c-108">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="1331c-109">Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="1331c-109">Creating the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>

- <span data-ttu-id="1331c-110">Das Windows Forms Host Projekt wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="1331c-110">Creating the Windows Forms host project.</span></span>

- <span data-ttu-id="1331c-111">Hosting des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="1331c-111">Hosting the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1331c-112">Erforderliche Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="1331c-112">Prerequisites</span></span>

<span data-ttu-id="1331c-113">Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="1331c-113">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="1331c-114">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="1331c-114">Visual Studio 2017</span></span>

<a name="To_Create_the_UserControl"></a>
## <a name="create-the-usercontrol"></a><span data-ttu-id="1331c-115">Erstellen des UserControl-Steuer Elements</span><span class="sxs-lookup"><span data-stu-id="1331c-115">Create the UserControl</span></span>

1. <span data-ttu-id="1331c-116">Erstellen Sie ein **WPF-Benutzer Steuer** Element-Bibliotheksprojekt namens `HostingWpfUserControlInWf`.</span><span class="sxs-lookup"><span data-stu-id="1331c-116">Create a **WPF User Control Library** project named `HostingWpfUserControlInWf`.</span></span>

2. <span data-ttu-id="1331c-117">Öffnen Sie UserControl1. XAML im [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1331c-117">Open UserControl1.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>

3. <span data-ttu-id="1331c-118">Ersetzen Sie den generierten Code durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="1331c-118">Replace the generated code with the following code:</span></span>

     [!code-xaml[HostingWpfUserControlInWf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]

     <span data-ttu-id="1331c-119">Dieser Code definiert eine <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType>, die zwei untergeordnete Steuerelemente enthält.</span><span class="sxs-lookup"><span data-stu-id="1331c-119">This code defines a <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> that contains two child controls.</span></span> <span data-ttu-id="1331c-120">Das erste untergeordnete Steuerelement ist ein <xref:System.Windows.Controls.Label?displayProperty=nameWithType> Steuerelement; die zweite ist ein <xref:System.Windows.Controls.Viewport3D> Steuerelement, das einen 3D-Kegel anzeigt.</span><span class="sxs-lookup"><span data-stu-id="1331c-120">The first child control is a <xref:System.Windows.Controls.Label?displayProperty=nameWithType> control; the second is a <xref:System.Windows.Controls.Viewport3D> control that displays a 3-D cone.</span></span>

<a name="To_Create_the_Windows_Forms_Host_Project"></a>
## <a name="create-the-host-project"></a><span data-ttu-id="1331c-121">Erstellen des Host Projekts</span><span class="sxs-lookup"><span data-stu-id="1331c-121">Create the host project</span></span>

1. <span data-ttu-id="1331c-122">Fügen Sie der Projekt Mappe ein **Windows Forms App-Projekt (.NET Framework)** mit dem Namen `WpfUserControlHost` hinzu.</span><span class="sxs-lookup"><span data-stu-id="1331c-122">Add a **Windows Forms App (.NET Framework)** project named `WpfUserControlHost` to the solution.</span></span>

2. <span data-ttu-id="1331c-123">Fügen Sie in **Projektmappen-Explorer**einen Verweis auf die WindowsFormsIntegration-Assembly mit dem Namen "WindowsFormsIntegration. dll" hinzu.</span><span class="sxs-lookup"><span data-stu-id="1331c-123">In **Solution Explorer**, add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

3. <span data-ttu-id="1331c-124">Fügen Sie Verweise auf die folgenden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Assemblys hinzu:</span><span class="sxs-lookup"><span data-stu-id="1331c-124">Add references to the following [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assemblies:</span></span>

    - <span data-ttu-id="1331c-125">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="1331c-125">PresentationCore</span></span>

    - <span data-ttu-id="1331c-126">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="1331c-126">PresentationFramework</span></span>

    - <span data-ttu-id="1331c-127">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="1331c-127">WindowsBase</span></span>

4. <span data-ttu-id="1331c-128">Fügen einen Verweis auf das `HostingWpfUserControlInWf`-Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="1331c-128">Add a reference to the `HostingWpfUserControlInWf` project.</span></span>

5. <span data-ttu-id="1331c-129">Legen Sie in Projektmappen-Explorer das `WpfUserControlHost` Projekt als Startprojekt fest.</span><span class="sxs-lookup"><span data-stu-id="1331c-129">In Solution Explorer, set the `WpfUserControlHost` project to be the startup project.</span></span>

<a name="To_Host_the_Windows_Presentation_Foundation"></a>
## <a name="host-the-usercontrol"></a><span data-ttu-id="1331c-130">Hosten von UserControl</span><span class="sxs-lookup"><span data-stu-id="1331c-130">Host the UserControl</span></span>

1. <span data-ttu-id="1331c-131">Öffnen Sie in der Windows Forms-Designer Form1.</span><span class="sxs-lookup"><span data-stu-id="1331c-131">In the Windows Forms Designer, open Form1.</span></span>

2. <span data-ttu-id="1331c-132">Klicken Sie im Eigenschaftenfenster auf **Ereignisse**, und doppelklicken Sie dann auf das <xref:System.Windows.Forms.Form.Load>-Ereignis, um einen Ereignishandler zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1331c-132">In the Properties window, click **Events**, and then double-click the <xref:System.Windows.Forms.Form.Load> event to create an event handler.</span></span>

     <span data-ttu-id="1331c-133">Der Code-Editor wird mit dem neu generierten `Form1_Load` Ereignishandler geöffnet.</span><span class="sxs-lookup"><span data-stu-id="1331c-133">The Code Editor opens to the newly generated `Form1_Load` event handler.</span></span>

3. <span data-ttu-id="1331c-134">Ersetzen Sie den Code in Form1.cs durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="1331c-134">Replace the code in Form1.cs with the following code.</span></span>

     <span data-ttu-id="1331c-135">Der `Form1_Load`-Ereignishandler erstellt eine Instanz von `UserControl1` und fügt die Auflistung von untergeordneten Steuerelementen des <xref:System.Windows.Forms.Integration.ElementHost>-Steuer Elements hinzu.</span><span class="sxs-lookup"><span data-stu-id="1331c-135">The `Form1_Load` event handler creates an instance of `UserControl1` and adds itto the <xref:System.Windows.Forms.Integration.ElementHost> control's collection of child controls.</span></span> <span data-ttu-id="1331c-136">Das <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement wird der Auflistung von untergeordneten Steuerelementen des Formulars hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1331c-136">The <xref:System.Windows.Forms.Integration.ElementHost> control is added to the form's collection of child controls.</span></span>

     [!code-csharp[HostingWpfUserControlInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]

4. <span data-ttu-id="1331c-137">Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1331c-137">Press **F5** to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="1331c-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1331c-138">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="1331c-139">Entwerfen von XAML-Code in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1331c-139">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="1331c-140">Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1331c-140">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="1331c-141">Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF</span><span class="sxs-lookup"><span data-stu-id="1331c-141">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="1331c-142">Hosting eines zusammengesetzten WPF-Steuer Elements in Windows Forms Beispiel</span><span class="sxs-lookup"><span data-stu-id="1331c-142">Hosting a WPF Composite Control in Windows Forms Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160001)
