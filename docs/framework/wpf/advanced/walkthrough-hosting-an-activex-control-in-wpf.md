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
ms.openlocfilehash: 959bc7942eaae91c0a7a72124f6ab1ab92a3553f
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040824"
---
# <a name="walkthrough-hosting-an-activex-control-in-wpf"></a><span data-ttu-id="73c41-102">Exemplarische Vorgehensweise: Hosten eines ActiveX-Steuerelements in WPF</span><span class="sxs-lookup"><span data-stu-id="73c41-102">Walkthrough: Hosting an ActiveX Control in WPF</span></span>
<span data-ttu-id="73c41-103">Um eine verbesserte Interaktion mit Browsern zu ermöglichen, können Sie Microsoft-ActiveX-Steuerelemente in ihrer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]basierten Anwendung verwenden.</span><span class="sxs-lookup"><span data-stu-id="73c41-103">To enable improved interaction with browsers, you can use Microsoft ActiveX controls in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span> <span data-ttu-id="73c41-104">In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Sie die Microsoft Windows-Media Player als Steuerelement auf einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Seite hosten können.</span><span class="sxs-lookup"><span data-stu-id="73c41-104">This walkthrough demonstrates how you can host the Microsoft Windows Media Player as a control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page.</span></span>

 <span data-ttu-id="73c41-105">In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="73c41-105">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="73c41-106">Erstellen des Projekts.</span><span class="sxs-lookup"><span data-stu-id="73c41-106">Creating the project.</span></span>

- <span data-ttu-id="73c41-107">Das ActiveX-Steuerelement wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="73c41-107">Creating the ActiveX control.</span></span>

- <span data-ttu-id="73c41-108">Hosting des ActiveX-Steuer Elements auf einer WPF-Seite.</span><span class="sxs-lookup"><span data-stu-id="73c41-108">Hosting the ActiveX control on a WPF Page.</span></span>

 <span data-ttu-id="73c41-109">Wenn Sie diese exemplarische Vorgehensweise abgeschlossen haben, erfahren Sie, wie Sie Microsoft-ActiveX-Steuerelemente in ihrer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]basierten Anwendung verwenden.</span><span class="sxs-lookup"><span data-stu-id="73c41-109">When you have completed this walkthrough, you will understand how to use Microsoft ActiveX controls in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="73c41-110">Erforderliche Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="73c41-110">Prerequisites</span></span>
 <span data-ttu-id="73c41-111">Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="73c41-111">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="73c41-112">Microsoft Windows Media Player auf dem Computer installiert, auf dem Visual Studio installiert ist.</span><span class="sxs-lookup"><span data-stu-id="73c41-112">Microsoft Windows Media Player installed on the computer where Visual Studio is installed.</span></span>

- <span data-ttu-id="73c41-113">Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="73c41-113">Visual Studio 2010.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="73c41-114">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="73c41-114">Creating the Project</span></span>

### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="73c41-115">So erstellen und richten Sie das Projekt ein</span><span class="sxs-lookup"><span data-stu-id="73c41-115">To create and set up the project</span></span>

1. <span data-ttu-id="73c41-116">Erstellen Sie ein WPF-Anwendungsprojekt mit dem Namen `HostingAxInWpf`.</span><span class="sxs-lookup"><span data-stu-id="73c41-116">Create a WPF Application project named `HostingAxInWpf`.</span></span>

2. <span data-ttu-id="73c41-117">Fügen Sie ein Windows Forms-Steuerelement Bibliothek-Projekt zur Projekt Mappe hinzu, und benennen Sie das Projekt `WmpAxLib`.</span><span class="sxs-lookup"><span data-stu-id="73c41-117">Add a Windows Forms Control Library project to the solution, and name the project `WmpAxLib`.</span></span>

3. <span data-ttu-id="73c41-118">Fügen Sie im wmpxlib-Projekt einen Verweis auf die Windows Media Player-Assembly mit dem Namen "WMP. dll" hinzu.</span><span class="sxs-lookup"><span data-stu-id="73c41-118">In the WmpAxLib project, add a reference to the Windows Media Player assembly, which is named wmp.dll.</span></span>

4. <span data-ttu-id="73c41-119">Öffnen Sie die **Toolbox**.</span><span class="sxs-lookup"><span data-stu-id="73c41-119">Open the **Toolbox**.</span></span>

5. <span data-ttu-id="73c41-120">Klicken Sie mit der rechten Maustaste in die **Toolbox**, und klicken Sie dann auf **Elemente auswählen**.</span><span class="sxs-lookup"><span data-stu-id="73c41-120">Right-click in the **Toolbox**, and then click **Choose Items**.</span></span>

6. <span data-ttu-id="73c41-121">Klicken Sie auf die Registerkarte **com-Komponenten** , wählen Sie das **Fenster Windows Media Player** aus, und klicken Sie dann auf **OK**</span><span class="sxs-lookup"><span data-stu-id="73c41-121">Click the **COM Components** tab, select the **Windows Media Player** control, and then click **OK**.</span></span>

     <span data-ttu-id="73c41-122">Das Windows Media Player-Steuerelement wird der **Toolbox**hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="73c41-122">The Windows Media Player control is added to the **Toolbox**.</span></span>

7. <span data-ttu-id="73c41-123">Klicken Sie in Projektmappen-Explorer mit der rechten Maustaste auf die Datei **UserControl1** , und klicken Sie dann auf **Umbenennen**.</span><span class="sxs-lookup"><span data-stu-id="73c41-123">In Solution Explorer, right-click the **UserControl1** file, and then click **Rename**.</span></span>

8. <span data-ttu-id="73c41-124">Ändern Sie den Namen abhängig von der Sprache in `WmpAxControl.vb` oder `WmpAxControl.cs`.</span><span class="sxs-lookup"><span data-stu-id="73c41-124">Change the name to `WmpAxControl.vb` or `WmpAxControl.cs`, depending on the language.</span></span>

9. <span data-ttu-id="73c41-125">Wenn Sie aufgefordert werden, alle Verweise umzubenennen, klicken Sie auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="73c41-125">If you are prompted to rename all references, click **Yes**.</span></span>

## <a name="creating-the-activex-control"></a><span data-ttu-id="73c41-126">Erstellen des ActiveX-Steuer Elements</span><span class="sxs-lookup"><span data-stu-id="73c41-126">Creating the ActiveX Control</span></span>
<span data-ttu-id="73c41-127">Visual Studio generiert automatisch eine <xref:System.Windows.Forms.AxHost> Wrapper Klasse für ein Microsoft ActiveX-Steuerelement, wenn das Steuerelement einer Entwurfs Oberfläche hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="73c41-127">Visual Studio automatically generates an <xref:System.Windows.Forms.AxHost> wrapper class for a Microsoft ActiveX control when the control is added to a design surface.</span></span> <span data-ttu-id="73c41-128">Mit der folgenden Prozedur wird eine verwaltete Assembly mit dem Namen "AxInterop. WMPLib. dll" erstellt.</span><span class="sxs-lookup"><span data-stu-id="73c41-128">The following procedure creates a managed assembly named AxInterop.WMPLib.dll.</span></span>

### <a name="to-create-the-activex-control"></a><span data-ttu-id="73c41-129">So erstellen Sie das ActiveX-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="73c41-129">To create the ActiveX control</span></span>

1. <span data-ttu-id="73c41-130">Öffnen Sie wmpxcontrol. vb oder WmpAxControl.cs im Windows Forms-Designer.</span><span class="sxs-lookup"><span data-stu-id="73c41-130">Open WmpAxControl.vb or WmpAxControl.cs in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="73c41-131">Fügen Sie der Entwurfs Oberfläche aus der **Toolbox**das Windows Media Player-Steuerelement hinzu.</span><span class="sxs-lookup"><span data-stu-id="73c41-131">From the **Toolbox**, add the Windows Media Player control to the design surface.</span></span>

3. <span data-ttu-id="73c41-132">Legen Sie in der Eigenschaftenfenster den Wert der Eigenschaft <xref:System.Windows.Forms.Control.Dock%2A> des Windows Media Player-Steuer Elements auf <xref:System.Windows.Forms.DockStyle.Fill>fest.</span><span class="sxs-lookup"><span data-stu-id="73c41-132">In the Properties window, set the value of the Windows Media Player control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

4. <span data-ttu-id="73c41-133">Erstellen Sie das wmpxlib-Steuerelement Bibliothek-Projekt.</span><span class="sxs-lookup"><span data-stu-id="73c41-133">Build the WmpAxLib control library project.</span></span>

## <a name="hosting-the-activex-control-on-a-wpf-page"></a><span data-ttu-id="73c41-134">Hosting des ActiveX-Steuer Elements auf einer WPF-Seite</span><span class="sxs-lookup"><span data-stu-id="73c41-134">Hosting the ActiveX Control on a WPF Page</span></span>

### <a name="to-host-the-activex-control"></a><span data-ttu-id="73c41-135">Zum Hosten des ActiveX-Steuer Elements</span><span class="sxs-lookup"><span data-stu-id="73c41-135">To host the ActiveX control</span></span>

1. <span data-ttu-id="73c41-136">Fügen Sie im Projekt "hustingaxinwpf" einen Verweis auf die generierte ActiveX-Interoperabilitäts-Assembly hinzu.</span><span class="sxs-lookup"><span data-stu-id="73c41-136">In the HostingAxInWpf project, add a reference to the generated ActiveX interoperability assembly.</span></span>

     <span data-ttu-id="73c41-137">Diese Assembly heißt "AxInterop. WMPLib. dll" und wurde beim Importieren des Windows Media Player-Steuer Elements zum Ordner "Debug" des Projekts "wmpxlib" hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="73c41-137">This assembly is named AxInterop.WMPLib.dll and was added to the Debug folder of the WmpAxLib project when you imported the Windows Media Player control.</span></span>

2. <span data-ttu-id="73c41-138">Fügen Sie einen Verweis auf die WindowsFormsIntegration-Assembly mit dem Namen "WindowsFormsIntegration. dll" hinzu.</span><span class="sxs-lookup"><span data-stu-id="73c41-138">Add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

3. <span data-ttu-id="73c41-139">Fügen Sie einen Verweis auf die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Assembly mit dem Namen "System. Windows. Forms. dll" hinzu.</span><span class="sxs-lookup"><span data-stu-id="73c41-139">Add a reference to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] assembly, which is named System.Windows.Forms.dll.</span></span>

4. <span data-ttu-id="73c41-140">Öffnen Sie die Datei "MainWindow. XAML" im WPF-Designer.</span><span class="sxs-lookup"><span data-stu-id="73c41-140">Open MainWindow.xaml in the WPF Designer.</span></span>

5. <span data-ttu-id="73c41-141">Benennen Sie das <xref:System.Windows.Controls.Grid> Element `grid1`.</span><span class="sxs-lookup"><span data-stu-id="73c41-141">Name the <xref:System.Windows.Controls.Grid> element `grid1`.</span></span>

     [!code-xaml[HostingAxInWpf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml#1)]

6. <span data-ttu-id="73c41-142">Wählen Sie in Designansicht-oder XAML-Ansicht das <xref:System.Windows.Window> Element aus.</span><span class="sxs-lookup"><span data-stu-id="73c41-142">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>

7. <span data-ttu-id="73c41-143">Klicken Sie im Eigenschaftenfenster auf die Registerkarte **Ereignisse** .</span><span class="sxs-lookup"><span data-stu-id="73c41-143">In the Properties window, click the **Events** tab.</span></span>

8. <span data-ttu-id="73c41-144">Doppelklicken Sie auf das <xref:System.Windows.FrameworkElement.Loaded> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="73c41-144">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

9. <span data-ttu-id="73c41-145">Fügen Sie den folgenden Code ein, um das <xref:System.Windows.FrameworkElement.Loaded>-Ereignis zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="73c41-145">Insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

     <span data-ttu-id="73c41-146">Mit diesem Code wird eine Instanz des <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Steuer Elements erstellt und eine Instanz des `AxWindowsMediaPlayer` Steuer Elements als untergeordnetes Element hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="73c41-146">This code creates an instance of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control and adds an instance of the `AxWindowsMediaPlayer` control as its child.</span></span>

     [!code-csharp[HostingAxInWpf#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml.cs#11)]
     [!code-vb[HostingAxInWpf#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingAxInWpf/VisualBasic/HostingAxInWpf/window1.xaml.vb#11)]  
  
10. <span data-ttu-id="73c41-147">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="73c41-147">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73c41-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="73c41-148">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="73c41-149">Entwerfen von XAML-Code in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="73c41-149">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="73c41-150">Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF</span><span class="sxs-lookup"><span data-stu-id="73c41-150">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="73c41-151">Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="73c41-151">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
