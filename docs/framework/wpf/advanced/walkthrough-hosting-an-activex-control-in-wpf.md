---
title: 'Exemplarische Vorgehensweise: Hosten eines ActiveX-Steuerelements in WPF'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ActiveX controls [WPF interoperability]
- hosting ActiveX controls [WPF]
ms.assetid: 1931d292-0dd1-434f-963c-dcda7638d75a
ms.openlocfilehash: c27449da5ee0351e472eaba7d930a774979db65f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59311499"
---
# <a name="walkthrough-hosting-an-activex-control-in-wpf"></a><span data-ttu-id="18ebf-102">Exemplarische Vorgehensweise: Hosten eines ActiveX-Steuerelements in WPF</span><span class="sxs-lookup"><span data-stu-id="18ebf-102">Walkthrough: Hosting an ActiveX Control in WPF</span></span>
<span data-ttu-id="18ebf-103">Um verbesserte Interaktion mit Browsern zu aktivieren, können Sie [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] -Steuerelemente in Ihre [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-basierten Anwendung.</span><span class="sxs-lookup"><span data-stu-id="18ebf-103">To enable improved interaction with browsers, you can use [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] controls in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span> <span data-ttu-id="18ebf-104">In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Sie hosten können die [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] als ein Steuerelement auf einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Seite.</span><span class="sxs-lookup"><span data-stu-id="18ebf-104">This walkthrough demonstrates how you can host the [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] as a control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page.</span></span>

 <span data-ttu-id="18ebf-105">In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="18ebf-105">Tasks illustrated in this walkthrough include:</span></span>

-   <span data-ttu-id="18ebf-106">Erstellen des Projekts.</span><span class="sxs-lookup"><span data-stu-id="18ebf-106">Creating the project.</span></span>

-   <span data-ttu-id="18ebf-107">Erstellen das ActiveX-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="18ebf-107">Creating the ActiveX control.</span></span>

-   <span data-ttu-id="18ebf-108">Hosten das ActiveX-Steuerelement auf einer WPF-Seite.</span><span class="sxs-lookup"><span data-stu-id="18ebf-108">Hosting the ActiveX control on a WPF Page.</span></span>

 <span data-ttu-id="18ebf-109">Wenn Sie diese exemplarische Vorgehensweise abgeschlossen haben, wissen Sie, wie mit [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] -Steuerelemente in Ihre [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-basierenden Anwendung.</span><span class="sxs-lookup"><span data-stu-id="18ebf-109">When you have completed this walkthrough, you will understand how to use [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] controls in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="18ebf-110">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="18ebf-110">Prerequisites</span></span>
 <span data-ttu-id="18ebf-111">Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="18ebf-111">You need the following components to complete this walkthrough:</span></span>

-   [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] <span data-ttu-id="18ebf-112">installiert auf dem Computer, auf dem Visual Studio installiert ist.</span><span class="sxs-lookup"><span data-stu-id="18ebf-112">installed on the computer where Visual Studio is installed.</span></span>

-   <span data-ttu-id="18ebf-113">Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="18ebf-113">Visual Studio 2010.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="18ebf-114">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="18ebf-114">Creating the Project</span></span>

#### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="18ebf-115">So erstellen und richten Sie das Projekt ein</span><span class="sxs-lookup"><span data-stu-id="18ebf-115">To create and set up the project</span></span>

1. <span data-ttu-id="18ebf-116">Erstellen einer WPF-Anwendungsprojekt mit dem Namen `HostingAxInWpf`.</span><span class="sxs-lookup"><span data-stu-id="18ebf-116">Create a WPF Application project named `HostingAxInWpf`.</span></span>

2. <span data-ttu-id="18ebf-117">Hinzufügen ein Windows Forms-Steuerelementbibliothek-Projekts zur Projektmappe, und nennen Sie das Projekt `WmpAxLib`.</span><span class="sxs-lookup"><span data-stu-id="18ebf-117">Add a Windows Forms Control Library project to the solution, and name the project `WmpAxLib`.</span></span>

3. <span data-ttu-id="18ebf-118">Fügen Sie einen Verweis auf die Windows Media Player-Assembly, mit die Namen wmp.dll WmpAxLib im Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="18ebf-118">In the WmpAxLib project, add a reference to the Windows Media Player assembly, which is named wmp.dll.</span></span>

4. <span data-ttu-id="18ebf-119">Öffnen der **Toolbox**.</span><span class="sxs-lookup"><span data-stu-id="18ebf-119">Open the **Toolbox**.</span></span>

5. <span data-ttu-id="18ebf-120">Mit der rechten Maustaste den **Toolbox**, und klicken Sie dann auf **Elemente auswählen**.</span><span class="sxs-lookup"><span data-stu-id="18ebf-120">Right-click in the **Toolbox**, and then click **Choose Items**.</span></span>

6. <span data-ttu-id="18ebf-121">Klicken Sie auf die **COM-Komponenten** Registerkarte die **Windows Media Player** steuern, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="18ebf-121">Click the **COM Components** tab, select the **Windows Media Player** control, and then click **OK**.</span></span>

     <span data-ttu-id="18ebf-122">Das Windows Media Player-Steuerelement wird hinzugefügt, um die **Toolbox**.</span><span class="sxs-lookup"><span data-stu-id="18ebf-122">The Windows Media Player control is added to the **Toolbox**.</span></span>

7. <span data-ttu-id="18ebf-123">Klicken Sie im Projektmappen-Explorer mit der Maustaste der **"UserControl1"** Datei, und klicken Sie dann auf **umbenennen**.</span><span class="sxs-lookup"><span data-stu-id="18ebf-123">In Solution Explorer, right-click the **UserControl1** file, and then click **Rename**.</span></span>

8. <span data-ttu-id="18ebf-124">Ändern Sie den Namen in `WmpAxControl.vb` oder `WmpAxControl.cs`, je nach Sprache.</span><span class="sxs-lookup"><span data-stu-id="18ebf-124">Change the name to `WmpAxControl.vb` or `WmpAxControl.cs`, depending on the language.</span></span>

9. <span data-ttu-id="18ebf-125">Wenn Sie aufgefordert werden, alle Verweise umzubenennen, klicken Sie auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="18ebf-125">If you are prompted to rename all references, click **Yes**.</span></span>

## <a name="creating-the-activex-control"></a><span data-ttu-id="18ebf-126">Erstellen das ActiveX-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="18ebf-126">Creating the ActiveX Control</span></span>
 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] <span data-ttu-id="18ebf-127">generiert automatisch ein <xref:System.Windows.Forms.AxHost> Wrapperklasse für ein [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] steuern, wenn das Steuerelement, einer Entwurfsoberfläche hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="18ebf-127">automatically generates an <xref:System.Windows.Forms.AxHost> wrapper class for a [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] control when the control is added to a design surface.</span></span> <span data-ttu-id="18ebf-128">Die folgende Prozedur erstellt eine verwaltete Assembly mit dem Namen AxInterop.WMPLib.dll.</span><span class="sxs-lookup"><span data-stu-id="18ebf-128">The following procedure creates a managed assembly named AxInterop.WMPLib.dll.</span></span>

#### <a name="to-create-the-activex-control"></a><span data-ttu-id="18ebf-129">Beim Erstellen des ActiveX-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="18ebf-129">To create the ActiveX control</span></span>

1. <span data-ttu-id="18ebf-130">Öffnen Sie WmpAxControl.vb oder WmpAxControl.cs im Windows Forms-Designer an.</span><span class="sxs-lookup"><span data-stu-id="18ebf-130">Open WmpAxControl.vb or WmpAxControl.cs in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="18ebf-131">Von der **Toolbox**, fügen Sie das Windows Media Player-Steuerelement, auf die Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="18ebf-131">From the **Toolbox**, add the Windows Media Player control to the design surface.</span></span>

3. <span data-ttu-id="18ebf-132">Legen Sie im Eigenschaftenfenster den Wert des Windows Media Player-Steuerelements <xref:System.Windows.Forms.Control.Dock%2A> Eigenschaft <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="18ebf-132">In the Properties window, set the value of the Windows Media Player control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

4. <span data-ttu-id="18ebf-133">Erstellen Sie das WmpAxLib Steuerelementbibliothek-Projekt.</span><span class="sxs-lookup"><span data-stu-id="18ebf-133">Build the WmpAxLib control library project.</span></span>

## <a name="hosting-the-activex-control-on-a-wpf-page"></a><span data-ttu-id="18ebf-134">Hosten das ActiveX-Steuerelement auf einer WPF-Seite</span><span class="sxs-lookup"><span data-stu-id="18ebf-134">Hosting the ActiveX Control on a WPF Page</span></span>

#### <a name="to-host-the-activex-control"></a><span data-ttu-id="18ebf-135">Zum Hosten des ActiveX-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="18ebf-135">To host the ActiveX control</span></span>

1. <span data-ttu-id="18ebf-136">Fügen Sie in HostingAxInWpf-Projekt einen Verweis auf die generierte [!INCLUDE[TLA2#tla_actx](../../../../includes/tla2sharptla-actx-md.md)] Interop-Assembly.</span><span class="sxs-lookup"><span data-stu-id="18ebf-136">In the HostingAxInWpf project, add a reference to the generated [!INCLUDE[TLA2#tla_actx](../../../../includes/tla2sharptla-actx-md.md)] interoperability assembly.</span></span>

     <span data-ttu-id="18ebf-137">Diese Assembly ist mit dem Namen AxInterop.WMPLib.dll und wurde dem Debugordner des Projekts WmpAxLib hinzugefügt, wenn Sie das Windows Media Player-Steuerelement importiert.</span><span class="sxs-lookup"><span data-stu-id="18ebf-137">This assembly is named AxInterop.WMPLib.dll and was added to the Debug folder of the WmpAxLib project when you imported the Windows Media Player control.</span></span>

2. <span data-ttu-id="18ebf-138">Fügen Sie einen Verweis auf die Assembly "WindowsFormsIntegration", mit die Namen WindowsFormsIntegration.dll hinzu.</span><span class="sxs-lookup"><span data-stu-id="18ebf-138">Add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

3. <span data-ttu-id="18ebf-139">Hinzufügen eines Verweises auf die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] -Assembly, die mit dem Namen "System.Windows.Forms.dll".</span><span class="sxs-lookup"><span data-stu-id="18ebf-139">Add a reference to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] assembly, which is named System.Windows.Forms.dll.</span></span>

4. <span data-ttu-id="18ebf-140">Öffnen Sie "MainWindow.xaml" im WPF-Designer.</span><span class="sxs-lookup"><span data-stu-id="18ebf-140">Open MainWindow.xaml in the WPF Designer.</span></span>

5. <span data-ttu-id="18ebf-141">Name der <xref:System.Windows.Controls.Grid> Element `grid1`.</span><span class="sxs-lookup"><span data-stu-id="18ebf-141">Name the <xref:System.Windows.Controls.Grid> element `grid1`.</span></span>

     [!code-xaml[HostingAxInWpf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml#1)]

6. <span data-ttu-id="18ebf-142">Wählen Sie in der Entwurfsansicht oder XAML-Ansicht der <xref:System.Windows.Window> Element.</span><span class="sxs-lookup"><span data-stu-id="18ebf-142">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>

7. <span data-ttu-id="18ebf-143">Klicken Sie im Eigenschaftenfenster auf die **Ereignisse** Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="18ebf-143">In the Properties window, click the **Events** tab.</span></span>

8. <span data-ttu-id="18ebf-144">Doppelklicken Sie auf die <xref:System.Windows.FrameworkElement.Loaded> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="18ebf-144">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

9. <span data-ttu-id="18ebf-145">Fügen Sie den folgenden Code zum Behandeln der <xref:System.Windows.FrameworkElement.Loaded> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="18ebf-145">Insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

     <span data-ttu-id="18ebf-146">Dieser Code erstellt eine Instanz der <xref:System.Windows.Forms.Integration.WindowsFormsHost> steuern und fügt eine Instanz des der `AxWindowsMediaPlayer` Steuerelement als untergeordnetes Element.</span><span class="sxs-lookup"><span data-stu-id="18ebf-146">This code creates an instance of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control and adds an instance of the `AxWindowsMediaPlayer` control as its child.</span></span>

     [!code-csharp[HostingAxInWpf#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml.cs#11)]
     [!code-vb[HostingAxInWpf#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingAxInWpf/VisualBasic/HostingAxInWpf/window1.xaml.vb#11)]  
  
10. <span data-ttu-id="18ebf-147">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="18ebf-147">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18ebf-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="18ebf-148">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="18ebf-149">Entwerfen von XAML-Code in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="18ebf-149">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="18ebf-150">Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF</span><span class="sxs-lookup"><span data-stu-id="18ebf-150">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="18ebf-151">Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="18ebf-151">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
