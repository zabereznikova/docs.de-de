---
title: 'Exemplarische Vorgehensweise: Hosten eines zusammengesetzten 3D-WPF-Steuerelements in Windows Forms'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
- composite controls [WPF], hosting WPF in
ms.assetid: 486369a9-606a-4a3b-b086-a06f2119c7b0
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f2b64cacea48bbc8855cdb9ce451a13d4ad729bd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms"></a><span data-ttu-id="ff698-102">Exemplarische Vorgehensweise: Hosten eines zusammengesetzten 3D-WPF-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ff698-102">Walkthrough: Hosting a 3-D WPF Composite Control in Windows Forms</span></span>
<span data-ttu-id="ff698-103">In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Sie erstellen können eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zusammengesetzten steuern und hostet es im [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] -Steuerelementen und-Formularen mithilfe der <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ff698-103">This walkthrough demonstrates how you can create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] composite control and host it in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls and forms by using the <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>  
  
 <span data-ttu-id="ff698-104">In dieser exemplarischen Vorgehensweise implementieren Sie eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> , zwei untergeordnete Steuerelemente enthält.</span><span class="sxs-lookup"><span data-stu-id="ff698-104">In this walkthrough, you will implement a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> that contains two child controls.</span></span> <span data-ttu-id="ff698-105">Die <xref:System.Windows.Controls.UserControl> zeigt einen dreidimensionalen (3D) Kegel.</span><span class="sxs-lookup"><span data-stu-id="ff698-105">The <xref:System.Windows.Controls.UserControl> displays a three-dimensional (3-D) cone.</span></span> <span data-ttu-id="ff698-106">Rendern von 3D-Objekten ist sehr viel einfacher, mit der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] als mit [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff698-106">Rendering 3-D objects is much easier with the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] than with [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="ff698-107">Aus diesem Grund ist es sinnvoll, Host eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> -Klasse zur Erstellung von 3D-Grafik in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff698-107">Therefore, it makes sense to host a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> class to create 3-D graphics in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span>  
  
 <span data-ttu-id="ff698-108">In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="ff698-108">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="ff698-109">Erstellen der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="ff698-109">Creating the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>  
  
-   <span data-ttu-id="ff698-110">Erstellen das Windows Forms-Host-Projekt.</span><span class="sxs-lookup"><span data-stu-id="ff698-110">Creating the Windows Forms host project.</span></span>  
  
-   <span data-ttu-id="ff698-111">Hosten der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="ff698-111">Hosting the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>  
  
 <span data-ttu-id="ff698-112">Vollständige Codeliste der Aufgaben in dieser exemplarischen Vorgehensweise veranschaulicht, finden Sie unter [Hosten eines 3D zusammengesetzten WPF-Steuerelements in Windows Forms-Beispiel](http://go.microsoft.com/fwlink/?LinkID=160001).</span><span class="sxs-lookup"><span data-stu-id="ff698-112">For a complete code listing of the tasks illustrated in this walkthrough, see [Hosting a 3-D WPF Composite Control in Windows Forms Sample](http://go.microsoft.com/fwlink/?LinkID=160001).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ff698-113">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="ff698-113">Prerequisites</span></span>  
 <span data-ttu-id="ff698-114">Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="ff698-114">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)]  
  
<a name="To_Create_the_UserControl"></a>   
## <a name="creating-the-usercontrol"></a><span data-ttu-id="ff698-116">Erstellen von UserControl</span><span class="sxs-lookup"><span data-stu-id="ff698-116">Creating the UserControl</span></span>  
  
#### <a name="to-create-the-usercontrol"></a><span data-ttu-id="ff698-117">So erstellen Sie UserControl</span><span class="sxs-lookup"><span data-stu-id="ff698-117">To create the UserControl</span></span>  
  
1.  <span data-ttu-id="ff698-118">Erstellen Sie ein WPF-Benutzersteuerelementbibliothek-Projekt mit dem Namen `HostingWpfUserControlInWf`.</span><span class="sxs-lookup"><span data-stu-id="ff698-118">Create a WPF User Control Library project named `HostingWpfUserControlInWf`.</span></span>  
  
2.  <span data-ttu-id="ff698-119">Öffnen Sie die Datei UserControl1.xaml in der [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff698-119">Open UserControl1.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
3.  <span data-ttu-id="ff698-120">Ersetzen Sie den generierten Code durch den folgenden Code ein.</span><span class="sxs-lookup"><span data-stu-id="ff698-120">Replace the generated code with the following code.</span></span>  
  
     <span data-ttu-id="ff698-121">Dieser Code definiert eine <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> , zwei untergeordnete Steuerelemente enthält.</span><span class="sxs-lookup"><span data-stu-id="ff698-121">This code defines a <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> that contains two child controls.</span></span> <span data-ttu-id="ff698-122">Das erste untergeordnete Steuerelement ist ein <xref:System.Windows.Controls.Label?displayProperty=nameWithType> Steuerelement; das zweite ist ein <xref:System.Windows.Controls.Viewport3D> Steuerelement, das einen 3D-Kegel anzeigt.</span><span class="sxs-lookup"><span data-stu-id="ff698-122">The first child control is a <xref:System.Windows.Controls.Label?displayProperty=nameWithType> control; the second is a <xref:System.Windows.Controls.Viewport3D> control that displays a 3-D cone.</span></span>  
  
     [!code-xaml[HostingWpfUserControlInWf#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]  
  
<a name="To_Create_the_Windows_Forms_Host_Project"></a>   
## <a name="creating-the-windows-forms-host-project"></a><span data-ttu-id="ff698-123">Erstellen des Windows Forms-Hostprojekts</span><span class="sxs-lookup"><span data-stu-id="ff698-123">Creating the Windows Forms Host Project</span></span>  
  
#### <a name="to-create-the-host-project"></a><span data-ttu-id="ff698-124">So erstellen Sie das Hostprojekt</span><span class="sxs-lookup"><span data-stu-id="ff698-124">To create the host project</span></span>  
  
1.  <span data-ttu-id="ff698-125">Fügen Sie ein Windows-Anwendungsprojekt mit dem Namen `WpfUserControlHost` der Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="ff698-125">Add a Windows application project named `WpfUserControlHost` to the solution.</span></span> <span data-ttu-id="ff698-126">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines neuen WPF-Anwendungsprojekts](http://msdn.microsoft.com/en-us/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span><span class="sxs-lookup"><span data-stu-id="ff698-126">For more information, see [How to: Create a New WPF Application Project](http://msdn.microsoft.com/en-us/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span></span>  
  
2.  <span data-ttu-id="ff698-127">Fügen Sie im Projektmappen-Explorer einen Verweis auf die Assembly mit die Namen WindowsFormsIntegration.dll WindowsFormsIntegration.</span><span class="sxs-lookup"><span data-stu-id="ff698-127">In Solution Explorer, add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>  
  
3.  <span data-ttu-id="ff698-128">Fügen Sie Verweise auf die folgenden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Assemblys:</span><span class="sxs-lookup"><span data-stu-id="ff698-128">Add references to the following [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assemblies:</span></span>  
  
    -   <span data-ttu-id="ff698-129">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="ff698-129">PresentationCore</span></span>  
  
    -   <span data-ttu-id="ff698-130">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="ff698-130">PresentationFramework</span></span>  
  
    -   <span data-ttu-id="ff698-131">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="ff698-131">WindowsBase</span></span>  
  
4.  <span data-ttu-id="ff698-132">Fügen einen Verweis auf das `HostingWpfUserControlInWf`-Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="ff698-132">Add a reference to the `HostingWpfUserControlInWf` project.</span></span>  
  
5.  <span data-ttu-id="ff698-133">Legen Sie im Projektmappen-Explorer die `WpfUserControlHost` Projekt das Startprojekt sein.</span><span class="sxs-lookup"><span data-stu-id="ff698-133">In Solution Explorer, set the `WpfUserControlHost` project to be the startup project.</span></span>  
  
<a name="To_Host_the_Windows_Presentation_Foundation"></a>   
## <a name="hosting-the-windows-presentation-foundation-usercontrol"></a><span data-ttu-id="ff698-134">Hosten von Windows Presentation Foundation UserControl</span><span class="sxs-lookup"><span data-stu-id="ff698-134">Hosting the Windows Presentation Foundation UserControl</span></span>  
  
#### <a name="to-host-the-usercontrol"></a><span data-ttu-id="ff698-135">So hosten Sie UserControl</span><span class="sxs-lookup"><span data-stu-id="ff698-135">To host the UserControl</span></span>  
  
1.  <span data-ttu-id="ff698-136">Öffnen Sie Form1 in der Windows Forms-Designer.</span><span class="sxs-lookup"><span data-stu-id="ff698-136">In the Windows Forms Designer, open Form1.</span></span>  
  
2.  <span data-ttu-id="ff698-137">Klicken Sie im Fenster Eigenschaften auf **Ereignisse**, und doppelklicken Sie dann auf die <xref:System.Windows.Forms.Form.Load> Ereignis, um einen Ereignishandler erstellen.</span><span class="sxs-lookup"><span data-stu-id="ff698-137">In the Properties window, click **Events**, and then double-click the <xref:System.Windows.Forms.Form.Load> event to create an event handler.</span></span>  
  
     <span data-ttu-id="ff698-138">Der Code-Editor wird geöffnet, auf die neu generierten `Form1_Load` -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="ff698-138">The Code Editor opens to the newly generated `Form1_Load` event handler.</span></span>  
  
3.  <span data-ttu-id="ff698-139">Ersetzen Sie den Code in "Form1.cs" durch den folgenden Code ein.</span><span class="sxs-lookup"><span data-stu-id="ff698-139">Replace the code in Form1.cs with the following code.</span></span>  
  
     <span data-ttu-id="ff698-140">Die `Form1_Load` -Ereignishandler erstellt eine Instanz des `UserControl1` und fügt auf der <xref:System.Windows.Forms.Integration.ElementHost> des Steuerelements Auflistung von untergeordneten Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="ff698-140">The `Form1_Load` event handler creates an instance of `UserControl1` and adds itto the <xref:System.Windows.Forms.Integration.ElementHost> control's collection of child controls.</span></span> <span data-ttu-id="ff698-141">Die <xref:System.Windows.Forms.Integration.ElementHost> -Steuerelement Auflistung der untergeordneten Steuerelemente des Formulars hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ff698-141">The <xref:System.Windows.Forms.Integration.ElementHost> control is added to the form's collection of child controls.</span></span>  
  
     [!code-csharp[HostingWpfUserControlInWf#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]  
  
4.  <span data-ttu-id="ff698-142">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ff698-142">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff698-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ff698-143">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="ff698-144">WPF-Designer</span><span class="sxs-lookup"><span data-stu-id="ff698-144">WPF Designer</span></span>](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)  
 [<span data-ttu-id="ff698-145">Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ff698-145">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)  
 [<span data-ttu-id="ff698-146">Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF</span><span class="sxs-lookup"><span data-stu-id="ff698-146">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [<span data-ttu-id="ff698-147">Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms-Beispiel</span><span class="sxs-lookup"><span data-stu-id="ff698-147">Hosting a WPF Composite Control in Windows Forms Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160001)
