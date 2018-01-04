---
title: 'Exemplarische Vorgehensweise: Hosten eines ActiveX-Steuerelements in WPF'
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
- ActiveX controls [WPF interoperability]
- hosting ActiveX controls [WPF]
ms.assetid: 1931d292-0dd1-434f-963c-dcda7638d75a
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6980097c074e10efae7fc6ee77c6c9835c3b1b00
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-hosting-an-activex-control-in-wpf"></a><span data-ttu-id="a0045-102">Exemplarische Vorgehensweise: Hosten eines ActiveX-Steuerelements in WPF</span><span class="sxs-lookup"><span data-stu-id="a0045-102">Walkthrough: Hosting an ActiveX Control in WPF</span></span>
<span data-ttu-id="a0045-103">Um verbesserte Interaktion mit Browsern zu aktivieren, können Sie [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] steuert in Ihrer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-basierten Anwendung.</span><span class="sxs-lookup"><span data-stu-id="a0045-103">To enable improved interaction with browsers, you can use [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] controls in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span> <span data-ttu-id="a0045-104">In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Sie hosten können die [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] als ein Steuerelement auf einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Seite.</span><span class="sxs-lookup"><span data-stu-id="a0045-104">This walkthrough demonstrates how you can host the [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] as a control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page.</span></span>  
  
 <span data-ttu-id="a0045-105">In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="a0045-105">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="a0045-106">Erstellen des Projekts.</span><span class="sxs-lookup"><span data-stu-id="a0045-106">Creating the project.</span></span>  
  
-   <span data-ttu-id="a0045-107">Erstellen das ActiveX-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="a0045-107">Creating the ActiveX control.</span></span>  
  
-   <span data-ttu-id="a0045-108">Hosting von ActiveX-Steuerelement auf einer WPF-Seite.</span><span class="sxs-lookup"><span data-stu-id="a0045-108">Hosting the ActiveX control on a WPF Page.</span></span>  
  
 <span data-ttu-id="a0045-109">Wenn Sie diese exemplarische Vorgehensweise abgeschlossen haben, werden Sie wissen, wie mit [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] steuert in Ihrem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]--basierten Anwendung.</span><span class="sxs-lookup"><span data-stu-id="a0045-109">When you have completed this walkthrough, you will understand how to use [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] controls in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a0045-110">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="a0045-110">Prerequisites</span></span>  
 <span data-ttu-id="a0045-111">Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="a0045-111">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)]<span data-ttu-id="a0045-112">auf dem Computer installiert, auf dem [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] installiert ist.</span><span class="sxs-lookup"><span data-stu-id="a0045-112"> installed on the computer where [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] is installed.</span></span>  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]  
  
## <a name="creating-the-project"></a><span data-ttu-id="a0045-114">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="a0045-114">Creating the Project</span></span>  
  
#### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="a0045-115">So erstellen und richten Sie das Projekt ein</span><span class="sxs-lookup"><span data-stu-id="a0045-115">To create and set up the project</span></span>  
  
1.  <span data-ttu-id="a0045-116">Erstellen Sie ein WPF-Anwendungsprojekt mit dem Namen `HostingAxInWpf`.</span><span class="sxs-lookup"><span data-stu-id="a0045-116">Create a WPF Application project named `HostingAxInWpf`.</span></span>  
  
2.  <span data-ttu-id="a0045-117">Die Projektmappe ein Windows Forms-Steuerelementbibliothek-Projekt hinzu, und nennen Sie das Projekt `WmpAxLib`.</span><span class="sxs-lookup"><span data-stu-id="a0045-117">Add a Windows Forms Control Library project to the solution, and name the project `WmpAxLib`.</span></span>  
  
3.  <span data-ttu-id="a0045-118">Fügen Sie im Projekt WmpAxLib einen Verweis auf die Windows Media Player-Assembly, die wmp.dll genannt wird.</span><span class="sxs-lookup"><span data-stu-id="a0045-118">In the WmpAxLib project, add a reference to the Windows Media Player assembly, which is named wmp.dll.</span></span>  
  
4.  <span data-ttu-id="a0045-119">Öffnen der **Toolbox**.</span><span class="sxs-lookup"><span data-stu-id="a0045-119">Open the **Toolbox**.</span></span>  
  
5.  <span data-ttu-id="a0045-120">Mit der rechten Maustaste die **Toolbox**, und klicken Sie dann auf **Elemente auswählen**.</span><span class="sxs-lookup"><span data-stu-id="a0045-120">Right-click in the **Toolbox**, and then click **Choose Items**.</span></span>  
  
6.  <span data-ttu-id="a0045-121">Klicken Sie auf die **COM-Komponenten** Registerkarte die **Windows Media Player** steuern, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a0045-121">Click the **COM Components** tab, select the **Windows Media Player** control, and then click **OK**.</span></span>  
  
     <span data-ttu-id="a0045-122">Windows Media Player-Steuerelement wird hinzugefügt, um die **Toolbox**.</span><span class="sxs-lookup"><span data-stu-id="a0045-122">The Windows Media Player control is added to the **Toolbox**.</span></span>  
  
7.  <span data-ttu-id="a0045-123">Klicken Sie im Projektmappen-Explorer mit der Maustaste die **"UserControl1"** Datei, und klicken Sie dann auf **umbenennen**.</span><span class="sxs-lookup"><span data-stu-id="a0045-123">In Solution Explorer, right-click the **UserControl1** file, and then click **Rename**.</span></span>  
  
8.  <span data-ttu-id="a0045-124">Ändern Sie den Namen in `WmpAxControl.vb` oder `WmpAxControl.cs`, abhängig von der Sprache.</span><span class="sxs-lookup"><span data-stu-id="a0045-124">Change the name to `WmpAxControl.vb` or `WmpAxControl.cs`, depending on the language.</span></span>  
  
9. <span data-ttu-id="a0045-125">Wenn Sie aufgefordert werden, alle Verweise umzubenennen, klicken Sie auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="a0045-125">If you are prompted to rename all references, click **Yes**.</span></span>  
  
## <a name="creating-the-activex-control"></a><span data-ttu-id="a0045-126">Erstellen des ActiveX-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="a0045-126">Creating the ActiveX Control</span></span>  
 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]<span data-ttu-id="a0045-127">generiert automatisch ein <xref:System.Windows.Forms.AxHost> Wrapperklasse für ein [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] steuern, wenn das Steuerelement auf einer Entwurfsoberfläche hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="a0045-127"> automatically generates an <xref:System.Windows.Forms.AxHost> wrapper class for a [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] control when the control is added to a design surface.</span></span> <span data-ttu-id="a0045-128">Die folgende Prozedur erstellt eine verwaltete Assembly mit dem Namen AxInterop.WMPLib.dll.</span><span class="sxs-lookup"><span data-stu-id="a0045-128">The following procedure creates a managed assembly named AxInterop.WMPLib.dll.</span></span>  
  
#### <a name="to-create-the-activex-control"></a><span data-ttu-id="a0045-129">Beim Erstellen des ActiveX-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="a0045-129">To create the ActiveX control</span></span>  
  
1.  <span data-ttu-id="a0045-130">Öffnen Sie WmpAxControl.vb oder WmpAxControl.cs in Windows Forms-Designer an.</span><span class="sxs-lookup"><span data-stu-id="a0045-130">Open WmpAxControl.vb or WmpAxControl.cs in the Windows Forms Designer.</span></span>  
  
2.  <span data-ttu-id="a0045-131">Aus der **Toolbox**, fügen Sie das Windows Media Player-Steuerelement auf die Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="a0045-131">From the **Toolbox**, add the Windows Media Player control to the design surface.</span></span>  
  
3.  <span data-ttu-id="a0045-132">Legen Sie im Fenster Eigenschaften den Wert des Windows Media Player-Steuerelements <xref:System.Windows.Forms.Control.Dock%2A> Eigenschaft <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="a0045-132">In the Properties window, set the value of the Windows Media Player control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
4.  <span data-ttu-id="a0045-133">Die WmpAxLib-Steuerelementbibliothek-Projekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a0045-133">Build the WmpAxLib control library project.</span></span>  
  
## <a name="hosting-the-activex-control-on-a-wpf-page"></a><span data-ttu-id="a0045-134">Hosting von ActiveX-Steuerelement auf einer WPF-Seite</span><span class="sxs-lookup"><span data-stu-id="a0045-134">Hosting the ActiveX Control on a WPF Page</span></span>  
  
#### <a name="to-host-the-activex-control"></a><span data-ttu-id="a0045-135">Zum Hosten des ActiveX-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="a0045-135">To host the ActiveX control</span></span>  
  
1.  <span data-ttu-id="a0045-136">Fügen Sie im HostingAxInWpf-Projekt einen Verweis auf die generierten [!INCLUDE[TLA2#tla_actx](../../../../includes/tla2sharptla-actx-md.md)] Interop-Assembly.</span><span class="sxs-lookup"><span data-stu-id="a0045-136">In the HostingAxInWpf project, add a reference to the generated [!INCLUDE[TLA2#tla_actx](../../../../includes/tla2sharptla-actx-md.md)] interoperability assembly.</span></span>  
  
     <span data-ttu-id="a0045-137">Diese Assembly ist mit dem Namen AxInterop.WMPLib.dll und wurde der Debugordner des Projekts WmpAxLib hinzugefügt, wenn Sie das Windows Media Player-Steuerelement importiert.</span><span class="sxs-lookup"><span data-stu-id="a0045-137">This assembly is named AxInterop.WMPLib.dll and was added to the Debug folder of the WmpAxLib project when you imported the Windows Media Player control.</span></span>  
  
2.  <span data-ttu-id="a0045-138">Fügen Sie einen Verweis auf die WindowsFormsIntegration-Assembly mit die Namen WindowsFormsIntegration.dll hinzu.</span><span class="sxs-lookup"><span data-stu-id="a0045-138">Add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>  
  
3.  <span data-ttu-id="a0045-139">Hinzufügen eines Verweises auf die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Assembly, die System.Windows.Forms.dll genannt wird.</span><span class="sxs-lookup"><span data-stu-id="a0045-139">Add a reference to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] assembly, which is named System.Windows.Forms.dll.</span></span>  
  
4.  <span data-ttu-id="a0045-140">Öffnen Sie "MainWindow.xaml" im WPF-Designer.</span><span class="sxs-lookup"><span data-stu-id="a0045-140">Open MainWindow.xaml in the WPF Designer.</span></span>  
  
5.  <span data-ttu-id="a0045-141">Name der <xref:System.Windows.Controls.Grid> Element `grid1`.</span><span class="sxs-lookup"><span data-stu-id="a0045-141">Name the <xref:System.Windows.Controls.Grid> element `grid1`.</span></span>  
  
     [!code-xaml[HostingAxInWpf#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml#1)]  
  
6.  <span data-ttu-id="a0045-142">Wählen Sie in der Entwurfsansicht oder der XAML-Ansicht, die <xref:System.Windows.Window> Element.</span><span class="sxs-lookup"><span data-stu-id="a0045-142">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>  
  
7.  <span data-ttu-id="a0045-143">Klicken Sie im Eigenschaftenfenster auf die **Ereignisse** Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="a0045-143">In the Properties window, click the **Events** tab.</span></span>  
  
8.  <span data-ttu-id="a0045-144">Doppelklicken Sie auf die <xref:System.Windows.FrameworkElement.Loaded> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="a0045-144">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>  
  
9. <span data-ttu-id="a0045-145">Fügen Sie folgenden Code zum Behandeln der <xref:System.Windows.FrameworkElement.Loaded> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="a0045-145">Insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>  
  
     <span data-ttu-id="a0045-146">Dieser Code erstellt eine Instanz von der <xref:System.Windows.Forms.Integration.WindowsFormsHost> steuern und fügt Sie eine Instanz von der `AxWindowsMediaPlayer` Steuerelement als untergeordnetes Element.</span><span class="sxs-lookup"><span data-stu-id="a0045-146">This code creates an instance of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control and adds an instance of the `AxWindowsMediaPlayer` control as its child.</span></span>  
  
     [!code-csharp[HostingAxInWpf#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml.cs#11)]
     [!code-vb[HostingAxInWpf#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingAxInWpf/VisualBasic/HostingAxInWpf/window1.xaml.vb#11)]  
  
10. <span data-ttu-id="a0045-147">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a0045-147">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0045-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0045-148">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="a0045-149">WPF-Designer</span><span class="sxs-lookup"><span data-stu-id="a0045-149">WPF Designer</span></span>](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)  
 [<span data-ttu-id="a0045-150">Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF</span><span class="sxs-lookup"><span data-stu-id="a0045-150">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [<span data-ttu-id="a0045-151">Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a0045-151">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
