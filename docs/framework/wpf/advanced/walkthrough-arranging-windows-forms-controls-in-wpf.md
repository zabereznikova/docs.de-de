---
title: Anordnen von Windows Forms Steuerelementen in WPF
titleSuffix: ''
ms.date: 04/03/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- arranging controls [WPF]
ms.assetid: a1db8049-15c7-45d6-ae3d-36a6735cb848
ms.openlocfilehash: 5e7544dfdbee234bb968c9a7f39814e8749ece15
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735289"
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a><span data-ttu-id="759d9-102">Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen in WPF</span><span class="sxs-lookup"><span data-stu-id="759d9-102">Walkthrough: Arranging Windows Forms Controls in WPF</span></span>

<span data-ttu-id="759d9-103">In dieser exemplarischen Vorgehensweise erfahren Sie, wie Sie mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layoutfeatures [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente in einer Hybrid Anwendung anordnen.</span><span class="sxs-lookup"><span data-stu-id="759d9-103">This walkthrough shows you how to use [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout features to arrange [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in a hybrid application.</span></span>

<span data-ttu-id="759d9-104">In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="759d9-104">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="759d9-105">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="759d9-105">Creating the project.</span></span>
- <span data-ttu-id="759d9-106">Verwenden der Standardlayouteinstellungen.</span><span class="sxs-lookup"><span data-stu-id="759d9-106">Using default layout settings.</span></span>
- <span data-ttu-id="759d9-107">Anpassen der Größe an Inhalt.</span><span class="sxs-lookup"><span data-stu-id="759d9-107">Sizing to content.</span></span>
- <span data-ttu-id="759d9-108">Verwenden der absoluten Positionierung.</span><span class="sxs-lookup"><span data-stu-id="759d9-108">Using absolute positioning.</span></span>
- <span data-ttu-id="759d9-109">Explizites Angeben der Größe.</span><span class="sxs-lookup"><span data-stu-id="759d9-109">Specifying size explicitly.</span></span>
- <span data-ttu-id="759d9-110">Festlegen der Layouteigenschaften.</span><span class="sxs-lookup"><span data-stu-id="759d9-110">Setting layout properties.</span></span>
- <span data-ttu-id="759d9-111">Grundlegendes zu Einschränkungen der Z-Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="759d9-111">Understanding z-order limitations.</span></span>
- <span data-ttu-id="759d9-112">Andocken.</span><span class="sxs-lookup"><span data-stu-id="759d9-112">Docking.</span></span>
- <span data-ttu-id="759d9-113">Einstellen der Sichtbarkeit.</span><span class="sxs-lookup"><span data-stu-id="759d9-113">Setting visibility.</span></span>
- <span data-ttu-id="759d9-114">Hosten eines Steuerelements, das nicht gestreckt wird.</span><span class="sxs-lookup"><span data-stu-id="759d9-114">Hosting a control that does not stretch.</span></span>
- <span data-ttu-id="759d9-115">Scaling.</span><span class="sxs-lookup"><span data-stu-id="759d9-115">Scaling.</span></span>
- <span data-ttu-id="759d9-116">Drehen.</span><span class="sxs-lookup"><span data-stu-id="759d9-116">Rotating.</span></span>
- <span data-ttu-id="759d9-117">Einstellen von Abständen und Rändern.</span><span class="sxs-lookup"><span data-stu-id="759d9-117">Setting padding and margins.</span></span>
- <span data-ttu-id="759d9-118">Verwenden von dynamischen Layoutcontainern.</span><span class="sxs-lookup"><span data-stu-id="759d9-118">Using dynamic layout containers.</span></span>

<span data-ttu-id="759d9-119">Eine umfassende Code Auflistung der Aufgaben in dieser exemplarischen Vorgehensweise finden Sie unter [Anordnen von Windows Forms Steuerelementen in WPF-Beispiel](https://go.microsoft.com/fwlink/?LinkID=159971).</span><span class="sxs-lookup"><span data-stu-id="759d9-119">For a complete code listing of the tasks illustrated in this walkthrough, see [Arranging Windows Forms Controls in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=159971).</span></span>

<span data-ttu-id="759d9-120">Wenn Sie fertig sind, verfügen Sie über die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Layoutfeatures in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-basierten Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="759d9-120">When you are finished, you will have an understanding of [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] layout features in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="759d9-121">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="759d9-121">Prerequisites</span></span>

<span data-ttu-id="759d9-122">Für diese exemplarische Vorgehensweise benötigen Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="759d9-122">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="759d9-123">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="759d9-123">Creating the Project</span></span>

<span data-ttu-id="759d9-124">Führen Sie die folgenden Schritte aus, um das Projekt zu erstellen und einzurichten:</span><span class="sxs-lookup"><span data-stu-id="759d9-124">To create and set up the project, follow these steps:</span></span>

1. <span data-ttu-id="759d9-125">Erstellen Sie ein WPF-Anwendungsprojekt mit dem Namen `WpfLayoutHostingWf`.</span><span class="sxs-lookup"><span data-stu-id="759d9-125">Create a WPF Application project named `WpfLayoutHostingWf`.</span></span>

2. <span data-ttu-id="759d9-126">Fügen Sie in Projektmappen-Explorer Verweise auf die folgenden Assemblys hinzu:</span><span class="sxs-lookup"><span data-stu-id="759d9-126">In Solution Explorer, add references to the following assemblies:</span></span>

    - <span data-ttu-id="759d9-127">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="759d9-127">WindowsFormsIntegration</span></span>
    - <span data-ttu-id="759d9-128">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="759d9-128">System.Windows.Forms</span></span>
    - <span data-ttu-id="759d9-129">System.Drawing</span><span class="sxs-lookup"><span data-stu-id="759d9-129">System.Drawing</span></span>

3. <span data-ttu-id="759d9-130">Doppelklicken Sie auf " *MainWindow. XAML* ", um Sie in der XAML-Ansicht zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="759d9-130">Double-click *MainWindow.xaml* to open it in XAML view.</span></span>

4. <span data-ttu-id="759d9-131">Fügen Sie im <xref:System.Windows.Window>-Element die folgende [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Namespace Zuordnung hinzu.</span><span class="sxs-lookup"><span data-stu-id="759d9-131">In the <xref:System.Windows.Window> element, add the following [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] namespace mapping.</span></span>

    ```xaml
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"
    ```

5. <span data-ttu-id="759d9-132">Legen Sie im <xref:System.Windows.Controls.Grid>-Element die <xref:System.Windows.Controls.Grid.ShowGridLines%2A>-Eigenschaft auf `true` fest, und definieren Sie fünf Zeilen und drei Spalten.</span><span class="sxs-lookup"><span data-stu-id="759d9-132">In the <xref:System.Windows.Controls.Grid> element set the <xref:System.Windows.Controls.Grid.ShowGridLines%2A> property to `true` and define five rows and three columns.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]

## <a name="using-default-layout-settings"></a><span data-ttu-id="759d9-133">Verwenden der Standardlayouteinstellungen</span><span class="sxs-lookup"><span data-stu-id="759d9-133">Using Default Layout Settings</span></span>

<span data-ttu-id="759d9-134">Standardmäßig behandelt das <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element das Layout für das gehostete [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="759d9-134">By default, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element handles the layout for the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>

<span data-ttu-id="759d9-135">Gehen Sie folgendermaßen vor, um Standardlayouteinstellungen zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="759d9-135">To use default layout settings, follow these steps:</span></span>

1. <span data-ttu-id="759d9-136">Kopieren Sie den folgenden XAML-Code in das <xref:System.Windows.Controls.Grid>-Element:</span><span class="sxs-lookup"><span data-stu-id="759d9-136">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]

2. <span data-ttu-id="759d9-137">Drücken Sie <kbd>F5</kbd>, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="759d9-137">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="759d9-138">Das [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Button?displayProperty=nameWithType>-Steuerelement wird im <xref:System.Windows.Controls.Canvas>angezeigt.</span><span class="sxs-lookup"><span data-stu-id="759d9-138">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Button?displayProperty=nameWithType> control appears in the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="759d9-139">Das gehostete Steuerelement wird basierend auf seinem Inhalt angepasst, und das <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element ist für das gehostete Steuerelement angepasst.</span><span class="sxs-lookup"><span data-stu-id="759d9-139">The hosted control is sized based on its content, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is sized to accommodate the hosted control.</span></span>

## <a name="sizing-to-content"></a><span data-ttu-id="759d9-140">Anpassen der Größe an Inhalt</span><span class="sxs-lookup"><span data-stu-id="759d9-140">Sizing to Content</span></span>

<span data-ttu-id="759d9-141">Das <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element stellt sicher, dass das gehostete Steuerelement seine Inhalte ordnungsgemäß anzeigt.</span><span class="sxs-lookup"><span data-stu-id="759d9-141">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element ensures that the hosted control is sized to display its content properly.</span></span>

<span data-ttu-id="759d9-142">Führen Sie die folgenden Schritte aus, um die Größe für den Inhalt zu</span><span class="sxs-lookup"><span data-stu-id="759d9-142">To size to content, follow these steps:</span></span>

1. <span data-ttu-id="759d9-143">Kopieren Sie den folgenden XAML-Code in das <xref:System.Windows.Controls.Grid>-Element:</span><span class="sxs-lookup"><span data-stu-id="759d9-143">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]

2. <span data-ttu-id="759d9-144">Drücken Sie <kbd>F5</kbd>, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="759d9-144">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="759d9-145">Die zwei neuen Schaltflächen-Steuerelemente werden angepasst, um die längere Text Zeichenfolge und eine größere Schriftgröße korrekt anzuzeigen, und die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Elemente werden angepasst, um die gehosteten Steuerelemente anzupassen.</span><span class="sxs-lookup"><span data-stu-id="759d9-145">The two new button controls are sized to display the longer text string and larger font size properly, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are resized to accommodate the hosted controls.</span></span>

## <a name="using-absolute-positioning"></a><span data-ttu-id="759d9-146">Verwenden der absoluten Positionierung</span><span class="sxs-lookup"><span data-stu-id="759d9-146">Using Absolute Positioning</span></span>

<span data-ttu-id="759d9-147">Sie können die absolute Positionierung verwenden, um das <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element an einer beliebigen Stelle in der Benutzeroberfläche (UI) zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="759d9-147">You can use absolute positioning to place the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element anywhere in the user interface (UI).</span></span>

<span data-ttu-id="759d9-148">Führen Sie die folgenden Schritte aus, um die absolute Positionierung zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="759d9-148">To use absolute positioning, follow these steps:</span></span>

1. <span data-ttu-id="759d9-149">Kopieren Sie den folgenden XAML-Code in das <xref:System.Windows.Controls.Grid>-Element:</span><span class="sxs-lookup"><span data-stu-id="759d9-149">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]

2. <span data-ttu-id="759d9-150">Drücken Sie <kbd>F5</kbd>, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="759d9-150">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="759d9-151">Das <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element wird 20 Pixel von der oberen Seite der Raster Zelle und 20 Pixel von Links platziert.</span><span class="sxs-lookup"><span data-stu-id="759d9-151">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is placed 20 pixels from the top side of the grid cell and 20 pixels from the left.</span></span>

## <a name="specifying-size-explicitly"></a><span data-ttu-id="759d9-152">Explizites Angeben der Größe</span><span class="sxs-lookup"><span data-stu-id="759d9-152">Specifying Size Explicitly</span></span>

<span data-ttu-id="759d9-153">Mithilfe der Eigenschaften <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> können Sie die Größe des <xref:System.Windows.Forms.Integration.WindowsFormsHost> Elements angeben.</span><span class="sxs-lookup"><span data-stu-id="759d9-153">You can specify the size of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element using the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span>

<span data-ttu-id="759d9-154">Um die Größe explizit anzugeben, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="759d9-154">To specify size explicitly, follow these steps:</span></span>

1. <span data-ttu-id="759d9-155">Kopieren Sie den folgenden XAML-Code in das <xref:System.Windows.Controls.Grid>-Element:</span><span class="sxs-lookup"><span data-stu-id="759d9-155">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]

2. <span data-ttu-id="759d9-156">Drücken Sie <kbd>F5</kbd>, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="759d9-156">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="759d9-157">Das <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element wird auf eine Größe von 50 Pixel Breite um 70 Pixel hoch festgelegt, die kleiner ist als die Standardlayouteinstellungen.</span><span class="sxs-lookup"><span data-stu-id="759d9-157">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is set to a size of 50 pixels wide by 70 pixels high, which is smaller than the default layout settings.</span></span> <span data-ttu-id="759d9-158">Der Inhalt des [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuer Elements wird entsprechend neu angeordnet.</span><span class="sxs-lookup"><span data-stu-id="759d9-158">The content of the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is rearranged accordingly.</span></span>

## <a name="setting-layout-properties"></a><span data-ttu-id="759d9-159">Festlegen der Layouteigenschaften</span><span class="sxs-lookup"><span data-stu-id="759d9-159">Setting Layout Properties</span></span>

<span data-ttu-id="759d9-160">Legen Sie Layout-bezogene Eigenschaften für das gehostete Steuerelement immer fest, indem Sie die Eigenschaften des <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Elements verwenden.</span><span class="sxs-lookup"><span data-stu-id="759d9-160">Always set layout-related properties on the hosted control by using the properties of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="759d9-161">Das Festlegen der Layouteigenschaften direkt für das gehostete Steuerelement führt zu unbeabsichtigten Ergebnissen.</span><span class="sxs-lookup"><span data-stu-id="759d9-161">Setting layout properties directly on the hosted control will yield unintended results.</span></span>

 <span data-ttu-id="759d9-162">Das Festlegen von layoutbezogenen Eigenschaften für das gehostete Steuerelement in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] hat keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="759d9-162">Setting layout-related properties on the hosted control in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] has no effect.</span></span>

<span data-ttu-id="759d9-163">Führen Sie die folgenden Schritte aus, um die Auswirkungen der Einstellungs Eigenschaften für das gehostete Steuerelement anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="759d9-163">To see the effects of setting properties on the hosted control, follow these steps:</span></span>

1. <span data-ttu-id="759d9-164">Kopieren Sie den folgenden XAML-Code in das <xref:System.Windows.Controls.Grid>-Element:</span><span class="sxs-lookup"><span data-stu-id="759d9-164">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]

2. <span data-ttu-id="759d9-165">Doppelklicken Sie in **Projektmappen-Explorer**auf die Datei *MainWindow. XAML. vb* oder *MainWindow.XAML.cs* , um Sie im Code-Editor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="759d9-165">In **Solution Explorer**, double-click *MainWindow.xaml.vb* or *MainWindow.xaml.cs* to open it in the Code Editor.</span></span>

3. <span data-ttu-id="759d9-166">Kopieren Sie den folgenden Code in die `MainWindow`-Klassendefinition:</span><span class="sxs-lookup"><span data-stu-id="759d9-166">Copy the following code into the `MainWindow` class definition:</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]

4. <span data-ttu-id="759d9-167">Drücken Sie <kbd>F5</kbd>, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="759d9-167">Press <kbd>F5</kbd> to build and run the application.</span></span>

5. <span data-ttu-id="759d9-168">Klicken Sie auf die Schaltfläche **Klicken Sie** .</span><span class="sxs-lookup"><span data-stu-id="759d9-168">Click the **Click me** button.</span></span> <span data-ttu-id="759d9-169">Der `button1_Click`-Ereignishandler legt die Eigenschaften <xref:System.Windows.Forms.Control.Top%2A> und <xref:System.Windows.Forms.Control.Left%2A> für das gehostete Steuerelement fest.</span><span class="sxs-lookup"><span data-stu-id="759d9-169">The `button1_Click` event handler sets the <xref:System.Windows.Forms.Control.Top%2A> and <xref:System.Windows.Forms.Control.Left%2A> properties on the hosted control.</span></span> <span data-ttu-id="759d9-170">Dies bewirkt, dass das gehostete Steuerelement im <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element neu positioniert wird.</span><span class="sxs-lookup"><span data-stu-id="759d9-170">This causes the hosted control to be repositioned within the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="759d9-171">Der Host behält den gleichen Bildschirmbereich bei, jedoch wird das gehostete Steuerelement abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="759d9-171">The host maintains the same screen area, but the hosted control is clipped.</span></span> <span data-ttu-id="759d9-172">Stattdessen sollte das gehostete Steuerelement immer das <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element ausfüllen.</span><span class="sxs-lookup"><span data-stu-id="759d9-172">Instead, the hosted control should always fill the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>

## <a name="understanding-z-order-limitations"></a><span data-ttu-id="759d9-173">Grundlegendes zu Einschränkungen der Z-Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="759d9-173">Understanding Z-Order Limitations</span></span>

<span data-ttu-id="759d9-174">Sichtbare <xref:System.Windows.Forms.Integration.WindowsFormsHost> Elemente werden immer auf anderen WPF-Elementen gezeichnet, und Sie sind nicht von der z-Reihenfolge betroffen.</span><span class="sxs-lookup"><span data-stu-id="759d9-174">Visible <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are always drawn on top of other WPF elements, and they are unaffected by z-order.</span></span> <span data-ttu-id="759d9-175">Gehen Sie folgendermaßen vor, um dieses z-Reihen folgen Verhalten anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="759d9-175">To see this z-order behavior, do the following:</span></span>

1. <span data-ttu-id="759d9-176">Kopieren Sie den folgenden XAML-Code in das <xref:System.Windows.Controls.Grid>-Element:</span><span class="sxs-lookup"><span data-stu-id="759d9-176">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]

2. <span data-ttu-id="759d9-177">Drücken Sie <kbd>F5</kbd>, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="759d9-177">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="759d9-178">Das <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element wird über das Label-Element gezeichnet.</span><span class="sxs-lookup"><span data-stu-id="759d9-178">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is painted over the label element.</span></span>

## <a name="docking"></a><span data-ttu-id="759d9-179">Docking</span><span class="sxs-lookup"><span data-stu-id="759d9-179">Docking</span></span>

<span data-ttu-id="759d9-180"><xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element unterstützt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] andocken.</span><span class="sxs-lookup"><span data-stu-id="759d9-180"><xref:System.Windows.Forms.Integration.WindowsFormsHost> element supports [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] docking.</span></span> <span data-ttu-id="759d9-181">Legen Sie die <xref:System.Windows.Controls.DockPanel.Dock%2A> angefügte-Eigenschaft fest, um das gehostete-Steuerelement in einem <xref:System.Windows.Controls.DockPanel>-Element</span><span class="sxs-lookup"><span data-stu-id="759d9-181">Set the <xref:System.Windows.Controls.DockPanel.Dock%2A> attached property to dock the hosted control in a <xref:System.Windows.Controls.DockPanel> element.</span></span>

<span data-ttu-id="759d9-182">Führen Sie die folgenden Schritte aus, um ein gehostetes Steuerelement zu</span><span class="sxs-lookup"><span data-stu-id="759d9-182">To dock a hosted control, follow these steps:</span></span>

1. <span data-ttu-id="759d9-183">Kopieren Sie den folgenden XAML-Code in das <xref:System.Windows.Controls.Grid>-Element:</span><span class="sxs-lookup"><span data-stu-id="759d9-183">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#9](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]

2. <span data-ttu-id="759d9-184">Drücken Sie <kbd>F5</kbd>, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="759d9-184">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="759d9-185">Das <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element wird an der rechten Seite des <xref:System.Windows.Controls.DockPanel> Elements angedockt.</span><span class="sxs-lookup"><span data-stu-id="759d9-185">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is docked to the right side of the <xref:System.Windows.Controls.DockPanel> element.</span></span>

## <a name="setting-visibility"></a><span data-ttu-id="759d9-186">Einstellen der Sichtbarkeit</span><span class="sxs-lookup"><span data-stu-id="759d9-186">Setting Visibility</span></span>

<span data-ttu-id="759d9-187">Sie können das [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-Steuerelement unsichtbar machen oder reduzieren, indem Sie die <xref:System.Windows.UIElement.Visibility%2A>-Eigenschaft für das <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element festlegen.</span><span class="sxs-lookup"><span data-stu-id="759d9-187">You can make your [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control invisible or collapse it by setting the <xref:System.Windows.UIElement.Visibility%2A> property on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="759d9-188">Wenn ein Steuerelement unsichtbar ist, wird es nicht angezeigt, es belegt jedoch Platz im Layoutbereich.</span><span class="sxs-lookup"><span data-stu-id="759d9-188">When a control is invisible, it is not displayed, but it occupies layout space.</span></span> <span data-ttu-id="759d9-189">Wenn ein Steuerelement reduziert ist, wird es nicht angezeigt, und es belegt auch keinen Platz im Layoutbereich.</span><span class="sxs-lookup"><span data-stu-id="759d9-189">When a control is collapsed, it is not displayed, nor does it occupy layout space.</span></span>

<span data-ttu-id="759d9-190">Führen Sie die folgenden Schritte aus, um die Sichtbarkeit eines gehosteten Steuer Elements festzulegen:</span><span class="sxs-lookup"><span data-stu-id="759d9-190">To set the visibility of a hosted control, follow these steps:</span></span>

1. <span data-ttu-id="759d9-191">Kopieren Sie den folgenden XAML-Code in das <xref:System.Windows.Controls.Grid>-Element:</span><span class="sxs-lookup"><span data-stu-id="759d9-191">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#10](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]

2. <span data-ttu-id="759d9-192">Kopieren Sie in *MainWindow. XAML. vb* oder *MainWindow.XAML.cs*den folgenden Code in die Klassendefinition:</span><span class="sxs-lookup"><span data-stu-id="759d9-192">In *MainWindow.xaml.vb* or *MainWindow.xaml.cs*, copy the following code into the class definition:</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]

3. <span data-ttu-id="759d9-193">Drücken Sie <kbd>F5</kbd>, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="759d9-193">Press <kbd>F5</kbd> to build and run the application.</span></span>

4. <span data-ttu-id="759d9-194">Klicken Sie auf die Schaltfläche **zum sichtbar machen** , um das <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element unsichtbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="759d9-194">Click the **Click to make invisible** button to make the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element invisible.</span></span>

5. <span data-ttu-id="759d9-195">Klicken Sie auf die Schaltfläche **zum reduzieren klicken** , um das <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element aus dem Layout vollständig auszublenden.</span><span class="sxs-lookup"><span data-stu-id="759d9-195">Click the **Click to collapse** button to hide the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element from the layout entirely.</span></span> <span data-ttu-id="759d9-196">Wenn das [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-Steuerelement reduziert ist, werden die umgebenden Elemente neu angeordnet, um ihren Platz zu belegen.</span><span class="sxs-lookup"><span data-stu-id="759d9-196">When the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is collapsed, the surrounding elements are rearranged to occupy its space.</span></span>

## <a name="hosting-a-control-that-does-not-stretch"></a><span data-ttu-id="759d9-197">Hosten eines Steuerelements, das nicht gestreckt wird</span><span class="sxs-lookup"><span data-stu-id="759d9-197">Hosting a Control That Does Not Stretch</span></span>

<span data-ttu-id="759d9-198">Einige [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente haben eine Festgröße und werden nicht gestreckt, um den verfügbaren Platz im Layout auszufüllen.</span><span class="sxs-lookup"><span data-stu-id="759d9-198">Some [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have a fixed size and do not stretch to fill available space in the layout.</span></span> <span data-ttu-id="759d9-199">Das <xref:System.Windows.Forms.MonthCalendar>-Steuerelement zeigt z. b. einen Monat in einem fester Bereich an.</span><span class="sxs-lookup"><span data-stu-id="759d9-199">For example, the <xref:System.Windows.Forms.MonthCalendar> control displays a month in a fixed space.</span></span>

<span data-ttu-id="759d9-200">Zum Hosten eines Steuer Elements, das nicht gestreckt wird, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="759d9-200">To host a control that does not stretch, follow these steps:</span></span>

1. <span data-ttu-id="759d9-201">Kopieren Sie den folgenden XAML-Code in das <xref:System.Windows.Controls.Grid>-Element:</span><span class="sxs-lookup"><span data-stu-id="759d9-201">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]

2. <span data-ttu-id="759d9-202">Drücken Sie <kbd>F5</kbd>, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="759d9-202">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="759d9-203">Das <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element wird in der Raster Zeile zentriert, aber nicht gestreckt, um den verfügbaren Platz auszufüllen.</span><span class="sxs-lookup"><span data-stu-id="759d9-203">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is centered in the grid row, but it is not stretched to fill the available space.</span></span> <span data-ttu-id="759d9-204">Wenn das Fenster groß genug ist, werden möglicherweise zwei oder mehr Monate vom gehosteten <xref:System.Windows.Forms.MonthCalendar> Steuerelement angezeigt, diese werden jedoch in der Zeile zentriert.</span><span class="sxs-lookup"><span data-stu-id="759d9-204">If the window is large enough, you may see two or more months displayed by the hosted <xref:System.Windows.Forms.MonthCalendar> control, but these are centered in the row.</span></span> <span data-ttu-id="759d9-205">Das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layoutmodul zentriert Elemente, deren Größen nicht so groß sind, dass der verfügbare Platz ausgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="759d9-205">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout engine centers elements that cannot be sized to fill the available space.</span></span>

## <a name="scaling"></a><span data-ttu-id="759d9-206">Skalieren</span><span class="sxs-lookup"><span data-stu-id="759d9-206">Scaling</span></span>

<span data-ttu-id="759d9-207">Anders als WPF-Elemente sind die meisten Windows Forms-Steuerelemente nicht kontinuierlich skalierbar.</span><span class="sxs-lookup"><span data-stu-id="759d9-207">Unlike WPF elements, most Windows Forms controls are not continuously scalable.</span></span> <span data-ttu-id="759d9-208">Zum Bereitstellen einer benutzerdefinierten Skalierung überschreiben Sie die <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType>-Methode.</span><span class="sxs-lookup"><span data-stu-id="759d9-208">To provide custom scaling, you override the <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="759d9-209">Führen Sie die folgenden Schritte aus, um ein gehostetes Steuerelement mithilfe des Standard Verhaltens zu skalieren:</span><span class="sxs-lookup"><span data-stu-id="759d9-209">To scale a hosted control by using the default behavior, follow these steps:</span></span>

1. <span data-ttu-id="759d9-210">Kopieren Sie den folgenden XAML-Code in das <xref:System.Windows.Controls.Grid>-Element:</span><span class="sxs-lookup"><span data-stu-id="759d9-210">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]

2. <span data-ttu-id="759d9-211">Drücken Sie <kbd>F5</kbd>, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="759d9-211">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="759d9-212">Das gehostete Steuerelement und die umgebenden Elemente werden um den Faktor 0,5 skaliert.</span><span class="sxs-lookup"><span data-stu-id="759d9-212">The hosted control and its surrounding elements are scaled by a factor of 0.5.</span></span> <span data-ttu-id="759d9-213">Allerdings wird die Schriftart des gehosteten Steuerelements nicht skaliert.</span><span class="sxs-lookup"><span data-stu-id="759d9-213">However, the hosted control's font is not scaled.</span></span>

<!-- This could use an example of custom scaling. -->

## <a name="rotating"></a><span data-ttu-id="759d9-214">Drehen</span><span class="sxs-lookup"><span data-stu-id="759d9-214">Rotating</span></span>

<span data-ttu-id="759d9-215">Anders als WPF-Elemente unterstützen Windows Forms Steuerelemente keine Rotation.</span><span class="sxs-lookup"><span data-stu-id="759d9-215">Unlike WPF elements, Windows Forms controls do not support rotation.</span></span> <span data-ttu-id="759d9-216">Das <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element wird nicht mit anderen WPF-Elementen gedreht, wenn eine Rotations Transformation angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="759d9-216">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element does not rotate with other WPF elements when a rotation transformation is applied.</span></span> <span data-ttu-id="759d9-217">Bei einem anderen Rotations Wert als 180 Grad wird das <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError>-Ereignis ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="759d9-217">Any rotation value other than 180 degrees raises the <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> event.</span></span>

<span data-ttu-id="759d9-218">Führen Sie die folgenden Schritte aus, um die Auswirkung der Drehung in einer Hybrid Anwendung anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="759d9-218">To see the effect of rotation in a hybrid application, follow these steps:</span></span>

1. <span data-ttu-id="759d9-219">Kopieren Sie den folgenden XAML-Code in das <xref:System.Windows.Controls.Grid>-Element:</span><span class="sxs-lookup"><span data-stu-id="759d9-219">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]

2. <span data-ttu-id="759d9-220">Drücken Sie <kbd>F5</kbd>, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="759d9-220">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="759d9-221">Das gehostete Steuerelement wird nicht gedreht, die umgebenden Elemente werden jedoch um einen Winkel von 180 Grad gedreht.</span><span class="sxs-lookup"><span data-stu-id="759d9-221">The hosted control is not rotated, but its surrounding elements are rotated by an angle of 180 degrees.</span></span> <span data-ttu-id="759d9-222">Sie müssen möglicherweise die Fenstergröße anpassen, um die Elemente zu sehen.</span><span class="sxs-lookup"><span data-stu-id="759d9-222">You may have to resize the window to see the elements.</span></span>

## <a name="setting-padding-and-margins"></a><span data-ttu-id="759d9-223">Einstellen von Abständen und Rändern</span><span class="sxs-lookup"><span data-stu-id="759d9-223">Setting Padding and Margins</span></span>

<span data-ttu-id="759d9-224">Abstand und Ränder in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layout ähneln der Auffüll-und Seitenränder in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="759d9-224">Padding and margins in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout are similar to padding and margins in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="759d9-225">Legen Sie einfach die Eigenschaften <xref:System.Windows.Controls.Control.Padding%2A> und <xref:System.Windows.FrameworkElement.Margin%2A> für das <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element fest.</span><span class="sxs-lookup"><span data-stu-id="759d9-225">Simply set the <xref:System.Windows.Controls.Control.Padding%2A> and <xref:System.Windows.FrameworkElement.Margin%2A> properties on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>

<span data-ttu-id="759d9-226">Gehen Sie folgendermaßen vor, um Auffüll-und Seitenränder für ein gehosteter Steuerelement festzulegen:</span><span class="sxs-lookup"><span data-stu-id="759d9-226">To set padding and margins for a hosted control, follow these steps:</span></span>

1. <span data-ttu-id="759d9-227">Kopieren Sie den folgenden XAML-Code in das <xref:System.Windows.Controls.Grid>-Element:</span><span class="sxs-lookup"><span data-stu-id="759d9-227">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]

2. <span data-ttu-id="759d9-228">Drücken Sie <kbd>F5</kbd>, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="759d9-228">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="759d9-229">Die Auffüll-und Rand Einstellungen werden auf die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente auf die gleiche Weise wie auf [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]angewendet.</span><span class="sxs-lookup"><span data-stu-id="759d9-229">The padding and margin settings are applied to the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in the same way they would be applied in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span>

## <a name="using-dynamic-layout-containers"></a><span data-ttu-id="759d9-230">Verwenden von dynamischen Layoutcontainern</span><span class="sxs-lookup"><span data-stu-id="759d9-230">Using Dynamic Layout Containers</span></span>

[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <span data-ttu-id="759d9-231">stellt zwei dynamische Layoutcontainer bereit, <xref:System.Windows.Forms.FlowLayoutPanel> und <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="759d9-231">provides two dynamic layout containers, <xref:System.Windows.Forms.FlowLayoutPanel> and <xref:System.Windows.Forms.TableLayoutPanel>.</span></span> <span data-ttu-id="759d9-232">Diese Container können auch in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layouts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="759d9-232">You can also use these containers in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layouts.</span></span>

<span data-ttu-id="759d9-233">Führen Sie die folgenden Schritte aus, um einen dynamischen Layoutcontainer zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="759d9-233">To use a dynamic layout container, follow these steps:</span></span>

1. <span data-ttu-id="759d9-234">Kopieren Sie den folgenden XAML-Code in das <xref:System.Windows.Controls.Grid>-Element:</span><span class="sxs-lookup"><span data-stu-id="759d9-234">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#16](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]

2. <span data-ttu-id="759d9-235">Kopieren Sie in *MainWindow. XAML. vb* oder *MainWindow.XAML.cs*den folgenden Code in die Klassendefinition:</span><span class="sxs-lookup"><span data-stu-id="759d9-235">In *MainWindow.xaml.vb* or *MainWindow.xaml.cs*, copy the following code into the class definition:</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]

3. <span data-ttu-id="759d9-236">Fügen Sie im Konstruktor einen aufzurufenden `InitializeFlowLayoutPanel`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="759d9-236">Add a call to the `InitializeFlowLayoutPanel` method in the constructor:</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]

4. <span data-ttu-id="759d9-237">Drücken Sie <kbd>F5</kbd>, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="759d9-237">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="759d9-238">Das <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element füllt die <xref:System.Windows.Controls.DockPanel>, und <xref:System.Windows.Forms.FlowLayoutPanel> ordnet die untergeordneten Steuerelemente im Standard <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>an.</span><span class="sxs-lookup"><span data-stu-id="759d9-238">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element fills the <xref:System.Windows.Controls.DockPanel>, and <xref:System.Windows.Forms.FlowLayoutPanel> arranges its child controls in the default <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="759d9-239">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="759d9-239">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="759d9-240">Entwerfen von XAML-Code in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="759d9-240">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="759d9-241">Überlegungen zum Layout für das WindowsFormsHost-Element</span><span class="sxs-lookup"><span data-stu-id="759d9-241">Layout Considerations for the WindowsFormsHost Element</span></span>](layout-considerations-for-the-windowsformshost-element.md)
- [<span data-ttu-id="759d9-242">Anordnen von Windows Forms Steuerelementen in WPF-Beispiel</span><span class="sxs-lookup"><span data-stu-id="759d9-242">Arranging Windows Forms Controls in WPF Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159971)
- [<span data-ttu-id="759d9-243">Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF</span><span class="sxs-lookup"><span data-stu-id="759d9-243">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="759d9-244">Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="759d9-244">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
