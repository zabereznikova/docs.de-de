---
title: 'Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen in WPF'
ms.date: 04/03/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- arranging controls [WPF]
ms.assetid: a1db8049-15c7-45d6-ae3d-36a6735cb848
ms.openlocfilehash: fa0181e95a03324c4cfa9395ae57439c260d1c23
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972312"
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a><span data-ttu-id="569ac-102">Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen in WPF</span><span class="sxs-lookup"><span data-stu-id="569ac-102">Walkthrough: Arranging Windows Forms Controls in WPF</span></span>

<span data-ttu-id="569ac-103">In dieser exemplarischen Vorgehensweise erfahren Sie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , wie Sie mithilfe [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] von Layoutfunktionen Steuerelemente in einer Hybrid Anwendung anordnen.</span><span class="sxs-lookup"><span data-stu-id="569ac-103">This walkthrough shows you how to use [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout features to arrange [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in a hybrid application.</span></span>

<span data-ttu-id="569ac-104">In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="569ac-104">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="569ac-105">Erstellen des Projekts.</span><span class="sxs-lookup"><span data-stu-id="569ac-105">Creating the project.</span></span>

- <span data-ttu-id="569ac-106">Verwenden der Standardlayouteinstellungen.</span><span class="sxs-lookup"><span data-stu-id="569ac-106">Using default layout settings.</span></span>

- <span data-ttu-id="569ac-107">Anpassen der Größe an Inhalt.</span><span class="sxs-lookup"><span data-stu-id="569ac-107">Sizing to content.</span></span>

- <span data-ttu-id="569ac-108">Verwenden der absoluten Positionierung.</span><span class="sxs-lookup"><span data-stu-id="569ac-108">Using absolute positioning.</span></span>

- <span data-ttu-id="569ac-109">Explizites Angeben der Größe.</span><span class="sxs-lookup"><span data-stu-id="569ac-109">Specifying size explicitly.</span></span>

- <span data-ttu-id="569ac-110">Festlegen der Layouteigenschaften.</span><span class="sxs-lookup"><span data-stu-id="569ac-110">Setting layout properties.</span></span>

- <span data-ttu-id="569ac-111">Grundlegendes zu Einschränkungen der Z-Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="569ac-111">Understanding z-order limitations.</span></span>

- <span data-ttu-id="569ac-112">Andocken.</span><span class="sxs-lookup"><span data-stu-id="569ac-112">Docking.</span></span>

- <span data-ttu-id="569ac-113">Einstellen der Sichtbarkeit.</span><span class="sxs-lookup"><span data-stu-id="569ac-113">Setting visibility.</span></span>

- <span data-ttu-id="569ac-114">Hosten eines Steuerelements, das nicht gestreckt wird.</span><span class="sxs-lookup"><span data-stu-id="569ac-114">Hosting a control that does not stretch.</span></span>

- <span data-ttu-id="569ac-115">Skalieren.</span><span class="sxs-lookup"><span data-stu-id="569ac-115">Scaling.</span></span>

- <span data-ttu-id="569ac-116">Drehen.</span><span class="sxs-lookup"><span data-stu-id="569ac-116">Rotating.</span></span>

- <span data-ttu-id="569ac-117">Einstellen von Abständen und Rändern.</span><span class="sxs-lookup"><span data-stu-id="569ac-117">Setting padding and margins.</span></span>

- <span data-ttu-id="569ac-118">Verwenden von dynamischen Layoutcontainern.</span><span class="sxs-lookup"><span data-stu-id="569ac-118">Using dynamic layout containers.</span></span>

<span data-ttu-id="569ac-119">Eine umfassende Code Auflistung der Aufgaben in dieser exemplarischen Vorgehensweise finden Sie unter [Anordnen von Windows Forms Steuerelementen in WPF-Beispiel](https://go.microsoft.com/fwlink/?LinkID=159971).</span><span class="sxs-lookup"><span data-stu-id="569ac-119">For a complete code listing of the tasks illustrated in this walkthrough, see [Arranging Windows Forms Controls in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=159971).</span></span>

<span data-ttu-id="569ac-120">Wenn Sie fertig sind, verfügen Sie über ein Verständnis der [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Layoutfeatures [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]in-basierten Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="569ac-120">When you are finished, you will have an understanding of [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] layout features in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="569ac-121">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="569ac-121">Prerequisites</span></span>

<span data-ttu-id="569ac-122">Für diese exemplarische Vorgehensweise benötigen Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="569ac-122">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="569ac-123">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="569ac-123">Creating the Project</span></span>

### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="569ac-124">So erstellen und richten Sie das Projekt ein</span><span class="sxs-lookup"><span data-stu-id="569ac-124">To create and set up the project</span></span>

1. <span data-ttu-id="569ac-125">Erstellen Sie ein WPF-Anwendungs `WpfLayoutHostingWf`Projekt mit dem Namen.</span><span class="sxs-lookup"><span data-stu-id="569ac-125">Create a WPF Application project named `WpfLayoutHostingWf`.</span></span>

2. <span data-ttu-id="569ac-126">Fügen Sie im Projektmappen-Explorer Verweise auf die folgenden Assemblys hinzu.</span><span class="sxs-lookup"><span data-stu-id="569ac-126">In Solution Explorer, add references to the following assemblies.</span></span>

    - <span data-ttu-id="569ac-127">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="569ac-127">WindowsFormsIntegration</span></span>

    - <span data-ttu-id="569ac-128">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="569ac-128">System.Windows.Forms</span></span>

    - <span data-ttu-id="569ac-129">System.Drawing</span><span class="sxs-lookup"><span data-stu-id="569ac-129">System.Drawing</span></span>

3. <span data-ttu-id="569ac-130">Doppelklicken Sie auf „MainWindow.xaml“, um die Datei in der XAML-Ansicht zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="569ac-130">Double-click MainWindow.xaml to open it in XAML view.</span></span>

4. <span data-ttu-id="569ac-131">Fügen Sie im- [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ElementdiefolgendeNamespaceZuordnunghinzu.<xref:System.Windows.Window></span><span class="sxs-lookup"><span data-stu-id="569ac-131">In the <xref:System.Windows.Window> element, add the following [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] namespace mapping.</span></span>

    ```xaml
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"
    ```

5. <span data-ttu-id="569ac-132">Legen Sie im- <xref:System.Windows.Controls.Grid.ShowGridLines%2A> `true` Element die-Eigenschaft auf fest, und definieren Sie fünf Zeilen und drei Spalten. <xref:System.Windows.Controls.Grid></span><span class="sxs-lookup"><span data-stu-id="569ac-132">In the <xref:System.Windows.Controls.Grid> element set the <xref:System.Windows.Controls.Grid.ShowGridLines%2A> property to `true` and define five rows and three columns.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]

## <a name="using-default-layout-settings"></a><span data-ttu-id="569ac-133">Verwenden der Standardlayouteinstellungen</span><span class="sxs-lookup"><span data-stu-id="569ac-133">Using Default Layout Settings</span></span>

<span data-ttu-id="569ac-134">Standardmäßig behandelt das <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element das Layout für das gehostete [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] -Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="569ac-134">By default, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element handles the layout for the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>

### <a name="to-use-default-layout-settings"></a><span data-ttu-id="569ac-135">Verwenden der Standardlayouteinstellungen</span><span class="sxs-lookup"><span data-stu-id="569ac-135">To use default layout settings</span></span>

1. <span data-ttu-id="569ac-136">Kopieren Sie den folgenden XAML- <xref:System.Windows.Controls.Grid> Code in das-Element.</span><span class="sxs-lookup"><span data-stu-id="569ac-136">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]

2. <span data-ttu-id="569ac-137">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="569ac-137">Press F5 to build and run the application.</span></span> <span data-ttu-id="569ac-138"><xref:System.Windows.Controls.Canvas>Das [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] -Steuer<xref:System.Windows.Forms.Button?displayProperty=nameWithType> Element wird in der angezeigt.</span><span class="sxs-lookup"><span data-stu-id="569ac-138">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Button?displayProperty=nameWithType> control appears in the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="569ac-139">Das gehostete Steuerelement wird basierend auf seinem Inhalt angepasst, <xref:System.Windows.Forms.Integration.WindowsFormsHost> und das Element wird für das gehostete Steuerelement angepasst.</span><span class="sxs-lookup"><span data-stu-id="569ac-139">The hosted control is sized based on its content, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is sized to accommodate the hosted control.</span></span>

## <a name="sizing-to-content"></a><span data-ttu-id="569ac-140">Anpassen der Größe an Inhalt</span><span class="sxs-lookup"><span data-stu-id="569ac-140">Sizing to Content</span></span>

<span data-ttu-id="569ac-141">Das <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element stellt sicher, dass das gehostete Steuerelement seine Inhalte ordnungsgemäß anzeigt.</span><span class="sxs-lookup"><span data-stu-id="569ac-141">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element ensures that the hosted control is sized to display its content properly.</span></span>

### <a name="to-size-to-content"></a><span data-ttu-id="569ac-142">Anpassen der Größe an Inhalt</span><span class="sxs-lookup"><span data-stu-id="569ac-142">To size to content</span></span>

1. <span data-ttu-id="569ac-143">Kopieren Sie den folgenden XAML- <xref:System.Windows.Controls.Grid> Code in das-Element.</span><span class="sxs-lookup"><span data-stu-id="569ac-143">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]

2. <span data-ttu-id="569ac-144">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="569ac-144">Press F5 to build and run the application.</span></span> <span data-ttu-id="569ac-145">Die zwei neuen Schaltflächen-Steuerelemente werden angepasst, um die längere Text Zeichenfolge und eine größere <xref:System.Windows.Forms.Integration.WindowsFormsHost> Schriftgröße korrekt anzuzeigen, und die Elemente werden angepasst, um die gehosteten Steuerelemente anzupassen.</span><span class="sxs-lookup"><span data-stu-id="569ac-145">The two new button controls are sized to display the longer text string and larger font size properly, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are resized to accommodate the hosted controls.</span></span>

## <a name="using-absolute-positioning"></a><span data-ttu-id="569ac-146">Verwenden der absoluten Positionierung</span><span class="sxs-lookup"><span data-stu-id="569ac-146">Using Absolute Positioning</span></span>

<span data-ttu-id="569ac-147">Sie können die absolute Positionierung verwenden, um <xref:System.Windows.Forms.Integration.WindowsFormsHost> das Element an einer beliebigen Stelle in der Benutzeroberfläche (UI) zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="569ac-147">You can use absolute positioning to place the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element anywhere in the user interface (UI).</span></span>

### <a name="to-use-absolute-positioning"></a><span data-ttu-id="569ac-148">Verwenden der absoluten Positionierung</span><span class="sxs-lookup"><span data-stu-id="569ac-148">To use absolute positioning</span></span>

1. <span data-ttu-id="569ac-149">Kopieren Sie den folgenden XAML- <xref:System.Windows.Controls.Grid> Code in das-Element.</span><span class="sxs-lookup"><span data-stu-id="569ac-149">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]

2. <span data-ttu-id="569ac-150">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="569ac-150">Press F5 to build and run the application.</span></span> <span data-ttu-id="569ac-151">Das <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element wird 20 Pixel von der oberen Seite der Raster Zelle und 20 Pixel von Links platziert.</span><span class="sxs-lookup"><span data-stu-id="569ac-151">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is placed 20 pixels from the top side of the grid cell and 20 pixels from the left.</span></span>

## <a name="specifying-size-explicitly"></a><span data-ttu-id="569ac-152">Explizites Angeben der Größe</span><span class="sxs-lookup"><span data-stu-id="569ac-152">Specifying Size Explicitly</span></span>

<span data-ttu-id="569ac-153">Sie können die Größe des <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Elements mithilfe der <xref:System.Windows.FrameworkElement.Width%2A> -Eigenschaft <xref:System.Windows.FrameworkElement.Height%2A> und der-Eigenschaft angeben.</span><span class="sxs-lookup"><span data-stu-id="569ac-153">You can specify the size of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element using the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span>

### <a name="to-specify-size-explicitly"></a><span data-ttu-id="569ac-154">Explizites Angeben der Größe</span><span class="sxs-lookup"><span data-stu-id="569ac-154">To specify size explicitly</span></span>

1. <span data-ttu-id="569ac-155">Kopieren Sie den folgenden XAML- <xref:System.Windows.Controls.Grid> Code in das-Element.</span><span class="sxs-lookup"><span data-stu-id="569ac-155">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]

2. <span data-ttu-id="569ac-156">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="569ac-156">Press F5 to build and run the application.</span></span> <span data-ttu-id="569ac-157">Das <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element wird auf eine Größe von 50 Pixel Breite um 70 Pixel hoch festgelegt, die kleiner ist als die Standardlayouteinstellungen.</span><span class="sxs-lookup"><span data-stu-id="569ac-157">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is set to a size of 50 pixels wide by 70 pixels high, which is smaller than the default layout settings.</span></span> <span data-ttu-id="569ac-158">Der Inhalt des [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuer Elements wird entsprechend neu angeordnet.</span><span class="sxs-lookup"><span data-stu-id="569ac-158">The content of the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is rearranged accordingly.</span></span>

## <a name="setting-layout-properties"></a><span data-ttu-id="569ac-159">Festlegen der Layouteigenschaften</span><span class="sxs-lookup"><span data-stu-id="569ac-159">Setting Layout Properties</span></span>

<span data-ttu-id="569ac-160">Legen Sie Layout-bezogene Eigenschaften für das gehostete Steuer <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element immer mithilfe der Eigenschaften des-Elements fest.</span><span class="sxs-lookup"><span data-stu-id="569ac-160">Always set layout-related properties on the hosted control by using the properties of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="569ac-161">Das Festlegen der Layouteigenschaften direkt für das gehostete Steuerelement führt zu unbeabsichtigten Ergebnissen.</span><span class="sxs-lookup"><span data-stu-id="569ac-161">Setting layout properties directly on the hosted control will yield unintended results.</span></span>

 <span data-ttu-id="569ac-162">Das Festlegen von layoutbezogenen Eigenschaften für das gehostete Steuerelement in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] hat keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="569ac-162">Setting layout-related properties on the hosted control in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] has no effect.</span></span>

### <a name="to-see-the-effects-of-setting-properties-on-the-hosted-control"></a><span data-ttu-id="569ac-163">Anzeigen der Auswirkungen des Festlegens der Eigenschaften für das gehostete Steuerelement</span><span class="sxs-lookup"><span data-stu-id="569ac-163">To see the effects of setting properties on the hosted control</span></span>

1. <span data-ttu-id="569ac-164">Kopieren Sie den folgenden XAML- <xref:System.Windows.Controls.Grid> Code in das-Element.</span><span class="sxs-lookup"><span data-stu-id="569ac-164">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]

2. <span data-ttu-id="569ac-165">Doppelklicken Sie in Projektmappen-Explorer „MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="569ac-165">In Solution Explorer, double-click MainWindow.xaml.</span></span> <span data-ttu-id="569ac-166">vb“ oder „MainWindow.Xaml.cs“, um die Datei im Code-Editor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="569ac-166">vb or MainWindow.xaml.cs to open it in the Code Editor.</span></span>

3. <span data-ttu-id="569ac-167">Kopieren Sie den folgenden Code in `MainWindow` die Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="569ac-167">Copy the following code into the `MainWindow` class definition.</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]

4. <span data-ttu-id="569ac-168">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="569ac-168">Press F5 to build and run the application.</span></span>

5. <span data-ttu-id="569ac-169">Klicken Sie auf die Schaltfläche **Klicken Sie** .</span><span class="sxs-lookup"><span data-stu-id="569ac-169">Click the **Click me** button.</span></span> <span data-ttu-id="569ac-170">Der `button1_Click` -Ereignishandler legt <xref:System.Windows.Forms.Control.Top%2A> die <xref:System.Windows.Forms.Control.Left%2A> Eigenschaften und für das gehostete Steuerelement fest.</span><span class="sxs-lookup"><span data-stu-id="569ac-170">The `button1_Click` event handler sets the <xref:System.Windows.Forms.Control.Top%2A> and <xref:System.Windows.Forms.Control.Left%2A> properties on the hosted control.</span></span> <span data-ttu-id="569ac-171">Dies bewirkt, dass das gehostete Steuer <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element im-Element neu positioniert wird.</span><span class="sxs-lookup"><span data-stu-id="569ac-171">This causes the hosted control to be repositioned within the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="569ac-172">Der Host behält den gleichen Bildschirmbereich bei, jedoch wird das gehostete Steuerelement abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="569ac-172">The host maintains the same screen area, but the hosted control is clipped.</span></span> <span data-ttu-id="569ac-173">Stattdessen sollte das gehostete Steuerelement immer das <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element ausfüllen.</span><span class="sxs-lookup"><span data-stu-id="569ac-173">Instead, the hosted control should always fill the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>

## <a name="understanding-z-order-limitations"></a><span data-ttu-id="569ac-174">Grundlegendes zu Einschränkungen der Z-Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="569ac-174">Understanding Z-Order Limitations</span></span>

<span data-ttu-id="569ac-175">Sichtbare <xref:System.Windows.Forms.Integration.WindowsFormsHost> Elemente werden immer auf anderen WPF-Elementen gezeichnet, und Sie sind nicht von der z-Reihenfolge betroffen.</span><span class="sxs-lookup"><span data-stu-id="569ac-175">Visible <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are always drawn on top of other WPF elements, and they are unaffected by z-order.</span></span> <span data-ttu-id="569ac-176">Gehen Sie folgendermaßen vor, um dieses z-Reihen folgen Verhalten anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="569ac-176">To see this z-order behavior, do the following:</span></span>

1. <span data-ttu-id="569ac-177">Kopieren Sie den folgenden XAML- <xref:System.Windows.Controls.Grid> Code in das-Element.</span><span class="sxs-lookup"><span data-stu-id="569ac-177">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]

2. <span data-ttu-id="569ac-178">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="569ac-178">Press F5 to build and run the application.</span></span> <span data-ttu-id="569ac-179">Das <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element wird über das Label-Element gezeichnet.</span><span class="sxs-lookup"><span data-stu-id="569ac-179">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is painted over the label element.</span></span>

## <a name="docking"></a><span data-ttu-id="569ac-180">Andocken</span><span class="sxs-lookup"><span data-stu-id="569ac-180">Docking</span></span>

<span data-ttu-id="569ac-181"><xref:System.Windows.Forms.Integration.WindowsFormsHost>Das- [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Element unterstützt Docking.</span><span class="sxs-lookup"><span data-stu-id="569ac-181"><xref:System.Windows.Forms.Integration.WindowsFormsHost> element supports [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] docking.</span></span> <span data-ttu-id="569ac-182">Legen Sie <xref:System.Windows.Controls.DockPanel.Dock%2A> die angefügte-Eigenschaft fest, um das <xref:System.Windows.Controls.DockPanel> gehostete Steuerelement in einem-Element</span><span class="sxs-lookup"><span data-stu-id="569ac-182">Set the <xref:System.Windows.Controls.DockPanel.Dock%2A> attached property to dock the hosted control in a <xref:System.Windows.Controls.DockPanel> element.</span></span>

### <a name="to-dock-a-hosted-control"></a><span data-ttu-id="569ac-183">Andocke eines gehosteten Steuerelements</span><span class="sxs-lookup"><span data-stu-id="569ac-183">To dock a hosted control</span></span>

1. <span data-ttu-id="569ac-184">Kopieren Sie den folgenden XAML- <xref:System.Windows.Controls.Grid> Code in das-Element.</span><span class="sxs-lookup"><span data-stu-id="569ac-184">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#9](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]

2. <span data-ttu-id="569ac-185">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="569ac-185">Press F5 to build and run the application.</span></span> <span data-ttu-id="569ac-186">Das <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element wird an der rechten Seite <xref:System.Windows.Controls.DockPanel> des Elements angedockt.</span><span class="sxs-lookup"><span data-stu-id="569ac-186">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is docked to the right side of the <xref:System.Windows.Controls.DockPanel> element.</span></span>

## <a name="setting-visibility"></a><span data-ttu-id="569ac-187">Einstellen der Sichtbarkeit</span><span class="sxs-lookup"><span data-stu-id="569ac-187">Setting Visibility</span></span>

<span data-ttu-id="569ac-188">Sie können das [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement unsichtbar machen oder reduzieren, indem Sie <xref:System.Windows.UIElement.Visibility%2A> die-Eigenschaft <xref:System.Windows.Forms.Integration.WindowsFormsHost> für das-Element festlegen.</span><span class="sxs-lookup"><span data-stu-id="569ac-188">You can make your [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control invisible or collapse it by setting the <xref:System.Windows.UIElement.Visibility%2A> property on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="569ac-189">Wenn ein Steuerelement unsichtbar ist, wird es nicht angezeigt, es belegt jedoch Platz im Layoutbereich.</span><span class="sxs-lookup"><span data-stu-id="569ac-189">When a control is invisible, it is not displayed, but it occupies layout space.</span></span> <span data-ttu-id="569ac-190">Wenn ein Steuerelement reduziert ist, wird es nicht angezeigt, und es belegt auch keinen Platz im Layoutbereich.</span><span class="sxs-lookup"><span data-stu-id="569ac-190">When a control is collapsed, it is not displayed, nor does it occupy layout space.</span></span>

### <a name="to-set-the-visibility-of-a-hosted-control"></a><span data-ttu-id="569ac-191">Festlegen der Sichtbarkeit eines gehosteten Steuerelements</span><span class="sxs-lookup"><span data-stu-id="569ac-191">To set the visibility of a hosted control</span></span>

1. <span data-ttu-id="569ac-192">Kopieren Sie den folgenden XAML- <xref:System.Windows.Controls.Grid> Code in das-Element.</span><span class="sxs-lookup"><span data-stu-id="569ac-192">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#10](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]

2. <span data-ttu-id="569ac-193">Kopieren Sie in „MainWindow.xaml.vb“ oder „MainWindow.xaml.cs“ den folgenden Code in die Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="569ac-193">In MainWindow.xaml.vb or MainWindow.xaml.cs, copy the following code into the class definition.</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]

3. <span data-ttu-id="569ac-194">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="569ac-194">Press F5 to build and run the application.</span></span>

4. <span data-ttu-id="569ac-195">Klicken Sie auf die Schaltfläche **zum unsichtbar machen** , <xref:System.Windows.Forms.Integration.WindowsFormsHost> um das Element unsichtbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="569ac-195">Click the **Click to make invisible** button to make the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element invisible.</span></span>

5. <span data-ttu-id="569ac-196">Klicken Sie auf die Schaltfläche **zum** reduzieren klicken <xref:System.Windows.Forms.Integration.WindowsFormsHost> , um das Element aus dem Layout vollständig auszublenden.</span><span class="sxs-lookup"><span data-stu-id="569ac-196">Click the **Click to collapse** button to hide the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element from the layout entirely.</span></span> <span data-ttu-id="569ac-197">Wenn das [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] -Steuerelement reduziert ist, werden die umgebenden Elemente neu angeordnet, um ihren Platz zu belegen.</span><span class="sxs-lookup"><span data-stu-id="569ac-197">When the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is collapsed, the surrounding elements are rearranged to occupy its space.</span></span>

## <a name="hosting-a-control-that-does-not-stretch"></a><span data-ttu-id="569ac-198">Hosten eines Steuerelements, das nicht gestreckt wird</span><span class="sxs-lookup"><span data-stu-id="569ac-198">Hosting a Control That Does Not Stretch</span></span>

<span data-ttu-id="569ac-199">Einige [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente verfügen über eine Größe mit fester Größe und werden nicht gestreckt, um den verfügbaren Platz im Layout auszufüllen.</span><span class="sxs-lookup"><span data-stu-id="569ac-199">Some [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have a fixed size and do not stretch to fill available space in the layout.</span></span> <span data-ttu-id="569ac-200">Das <xref:System.Windows.Forms.MonthCalendar> -Steuerelement zeigt z. b. einen Monat in einem fester Bereich an.</span><span class="sxs-lookup"><span data-stu-id="569ac-200">For example, the <xref:System.Windows.Forms.MonthCalendar> control displays a month in a fixed space.</span></span>

### <a name="to-host-a-control-that-does-not-stretch"></a><span data-ttu-id="569ac-201">Hosten eines Steuerelements, das nicht gestreckt wird</span><span class="sxs-lookup"><span data-stu-id="569ac-201">To host a control that does not stretch</span></span>

1. <span data-ttu-id="569ac-202">Kopieren Sie den folgenden XAML- <xref:System.Windows.Controls.Grid> Code in das-Element.</span><span class="sxs-lookup"><span data-stu-id="569ac-202">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]

2. <span data-ttu-id="569ac-203">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="569ac-203">Press F5 to build and run the application.</span></span> <span data-ttu-id="569ac-204">Das <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element wird in der Raster Zeile zentriert, aber nicht gestreckt, um den verfügbaren Platz auszufüllen.</span><span class="sxs-lookup"><span data-stu-id="569ac-204">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is centered in the grid row, but it is not stretched to fill the available space.</span></span> <span data-ttu-id="569ac-205">Wenn das Fenster groß genug ist, werden möglicherweise zwei oder mehr Monate vom gehosteten <xref:System.Windows.Forms.MonthCalendar> Steuerelement angezeigt, diese werden jedoch in der Zeile zentriert.</span><span class="sxs-lookup"><span data-stu-id="569ac-205">If the window is large enough, you may see two or more months displayed by the hosted <xref:System.Windows.Forms.MonthCalendar> control, but these are centered in the row.</span></span> <span data-ttu-id="569ac-206">Das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layoutmodul zentriert Elemente, für die keine Größenanpassung möglich ist, um den verfügbaren Platz auszufüllen.</span><span class="sxs-lookup"><span data-stu-id="569ac-206">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout engine centers elements that cannot be sized to fill the available space.</span></span>

## <a name="scaling"></a><span data-ttu-id="569ac-207">Skalieren</span><span class="sxs-lookup"><span data-stu-id="569ac-207">Scaling</span></span>

<span data-ttu-id="569ac-208">Anders als WPF-Elemente sind die meisten Windows Forms-Steuerelemente nicht kontinuierlich skalierbar.</span><span class="sxs-lookup"><span data-stu-id="569ac-208">Unlike WPF elements, most Windows Forms controls are not continuously scalable.</span></span> <span data-ttu-id="569ac-209">Zum Bereitstellen einer benutzerdefinierten Skalierung <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> überschreiben Sie die-Methode.</span><span class="sxs-lookup"><span data-stu-id="569ac-209">To provide custom scaling, you override the <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> method.</span></span>

### <a name="to-scale-a-hosted-control-by-using-the-default-behavior"></a><span data-ttu-id="569ac-210">Skalieren eines gehosteten Steuerelements mithilfe des Standardverhaltens</span><span class="sxs-lookup"><span data-stu-id="569ac-210">To scale a hosted control by using the default behavior</span></span>

1. <span data-ttu-id="569ac-211">Kopieren Sie den folgenden XAML- <xref:System.Windows.Controls.Grid> Code in das-Element.</span><span class="sxs-lookup"><span data-stu-id="569ac-211">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]

2. <span data-ttu-id="569ac-212">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="569ac-212">Press F5 to build and run the application.</span></span> <span data-ttu-id="569ac-213">Das gehostete Steuerelement und die umgebenden Elemente werden um den Faktor 0,5 skaliert.</span><span class="sxs-lookup"><span data-stu-id="569ac-213">The hosted control and its surrounding elements are scaled by a factor of 0.5.</span></span> <span data-ttu-id="569ac-214">Allerdings wird die Schriftart des gehosteten Steuerelements nicht skaliert.</span><span class="sxs-lookup"><span data-stu-id="569ac-214">However, the hosted control's font is not scaled.</span></span>

<!-- This could use an example of custom scaling. -->

## <a name="rotating"></a><span data-ttu-id="569ac-215">Drehen</span><span class="sxs-lookup"><span data-stu-id="569ac-215">Rotating</span></span>

<span data-ttu-id="569ac-216">Anders als WPF-Elemente unterstützen Windows Forms Steuerelemente keine Rotation.</span><span class="sxs-lookup"><span data-stu-id="569ac-216">Unlike WPF elements, Windows Forms controls do not support rotation.</span></span> <span data-ttu-id="569ac-217">Das <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element wird nicht mit anderen WPF-Elementen gedreht, wenn eine Rotations Transformation angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="569ac-217">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element does not rotate with other WPF elements when a rotation transformation is applied.</span></span> <span data-ttu-id="569ac-218">Ein beliebiger Rotations Wert außer 180 Grad löst <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> das-Ereignis aus.</span><span class="sxs-lookup"><span data-stu-id="569ac-218">Any rotation value other than 180 degrees raises the <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> event.</span></span>

### <a name="to-see-the-effect-of-rotation-in-a-hybrid-application"></a><span data-ttu-id="569ac-219">Anzeigen der Auswirkung der Drehung in einer Hybridanwendung</span><span class="sxs-lookup"><span data-stu-id="569ac-219">To see the effect of rotation in a hybrid application</span></span>

1. <span data-ttu-id="569ac-220">Kopieren Sie den folgenden XAML- <xref:System.Windows.Controls.Grid> Code in das-Element.</span><span class="sxs-lookup"><span data-stu-id="569ac-220">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]

2. <span data-ttu-id="569ac-221">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="569ac-221">Press F5 to build and run the application.</span></span> <span data-ttu-id="569ac-222">Das gehostete Steuerelement wird nicht gedreht, die umgebenden Elemente werden jedoch um einen Winkel von 180 Grad gedreht.</span><span class="sxs-lookup"><span data-stu-id="569ac-222">The hosted control is not rotated, but its surrounding elements are rotated by an angle of 180 degrees.</span></span> <span data-ttu-id="569ac-223">Sie müssen möglicherweise die Fenstergröße anpassen, um die Elemente zu sehen.</span><span class="sxs-lookup"><span data-stu-id="569ac-223">You may have to resize the window to see the elements.</span></span>

## <a name="setting-padding-and-margins"></a><span data-ttu-id="569ac-224">Einstellen von Abständen und Rändern</span><span class="sxs-lookup"><span data-stu-id="569ac-224">Setting Padding and Margins</span></span>

<span data-ttu-id="569ac-225">Auffüll-und Rand [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Ränder im Layout ähneln den Auffüll-und [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]Seitenrändern in.</span><span class="sxs-lookup"><span data-stu-id="569ac-225">Padding and margins in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout are similar to padding and margins in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="569ac-226">Legen Sie einfach <xref:System.Windows.Controls.Control.Padding%2A> die <xref:System.Windows.FrameworkElement.Margin%2A> Eigenschaften und für <xref:System.Windows.Forms.Integration.WindowsFormsHost> das Element fest.</span><span class="sxs-lookup"><span data-stu-id="569ac-226">Simply set the <xref:System.Windows.Controls.Control.Padding%2A> and <xref:System.Windows.FrameworkElement.Margin%2A> properties on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>

### <a name="to-set-padding-and-margins-for-a-hosted-control"></a><span data-ttu-id="569ac-227">Festlegen von Abstand und Rändern für ein gehostetes Steuerelement</span><span class="sxs-lookup"><span data-stu-id="569ac-227">To set padding and margins for a hosted control</span></span>

1. <span data-ttu-id="569ac-228">Kopieren Sie den folgenden XAML- <xref:System.Windows.Controls.Grid> Code in das-Element.</span><span class="sxs-lookup"><span data-stu-id="569ac-228">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]

2. <span data-ttu-id="569ac-229">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="569ac-229">Press F5 to build and run the application.</span></span> <span data-ttu-id="569ac-230">Die Auffüll-und Rand Einstellungen werden auf dieselbe Weise [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] auf die gehosteten Steuerelemente angewendet wie in. [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]</span><span class="sxs-lookup"><span data-stu-id="569ac-230">The padding and margin settings are applied to the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in the same way they would be applied in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span>

## <a name="using-dynamic-layout-containers"></a><span data-ttu-id="569ac-231">Verwenden von dynamischen Layoutcontainern</span><span class="sxs-lookup"><span data-stu-id="569ac-231">Using Dynamic Layout Containers</span></span>

[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<span data-ttu-id="569ac-232">stellt zwei dynamische Layoutcontainer <xref:System.Windows.Forms.FlowLayoutPanel> ( <xref:System.Windows.Forms.TableLayoutPanel>und) bereit.</span><span class="sxs-lookup"><span data-stu-id="569ac-232">provides two dynamic layout containers, <xref:System.Windows.Forms.FlowLayoutPanel> and <xref:System.Windows.Forms.TableLayoutPanel>.</span></span> <span data-ttu-id="569ac-233">Diese Container können auch in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layouts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="569ac-233">You can also use these containers in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layouts.</span></span>

### <a name="to-use-a-dynamic-layout-container"></a><span data-ttu-id="569ac-234">Verwenden von dynamischen Layoutcontainern</span><span class="sxs-lookup"><span data-stu-id="569ac-234">To use a dynamic layout container</span></span>

1. <span data-ttu-id="569ac-235">Kopieren Sie den folgenden XAML- <xref:System.Windows.Controls.Grid> Code in das-Element.</span><span class="sxs-lookup"><span data-stu-id="569ac-235">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#16](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]

2. <span data-ttu-id="569ac-236">Kopieren Sie in „MainWindow.xaml.vb“ oder „MainWindow.xaml.cs“ den folgenden Code in die Klassedefinition.</span><span class="sxs-lookup"><span data-stu-id="569ac-236">In MainWindow.xaml.vb or MainWindow.xaml.cs copy the following code into the class definition.</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]

3. <span data-ttu-id="569ac-237">Fügen Sie einen Aufruf der `InitializeFlowLayoutPanel` -Methode im Konstruktor hinzu.</span><span class="sxs-lookup"><span data-stu-id="569ac-237">Add a call to the `InitializeFlowLayoutPanel` method in the constructor.</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]

4. <span data-ttu-id="569ac-238">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="569ac-238">Press F5 to build and run the application.</span></span> <span data-ttu-id="569ac-239">Das <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element füllt <xref:System.Windows.Controls.DockPanel>das- <xref:System.Windows.Forms.FlowLayoutPanel> Element und ordnet seine untergeordneten Steuer <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>Elemente in der Standardeinstellung an.</span><span class="sxs-lookup"><span data-stu-id="569ac-239">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element fills the <xref:System.Windows.Controls.DockPanel>, and <xref:System.Windows.Forms.FlowLayoutPanel> arranges its child controls in the default <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="569ac-240">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="569ac-240">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="569ac-241">Entwerfen von XAML-Code in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="569ac-241">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="569ac-242">Überlegungen zum Layout für das WindowsFormsHost-Element</span><span class="sxs-lookup"><span data-stu-id="569ac-242">Layout Considerations for the WindowsFormsHost Element</span></span>](layout-considerations-for-the-windowsformshost-element.md)
- [<span data-ttu-id="569ac-243">Anordnen von Windows Forms Steuerelementen in WPF-Beispiel</span><span class="sxs-lookup"><span data-stu-id="569ac-243">Arranging Windows Forms Controls in WPF Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159971)
- [<span data-ttu-id="569ac-244">Exemplarische Vorgehensweise: Hosting eines Windows Forms zusammengesetzten Steuer Elements in WPF</span><span class="sxs-lookup"><span data-stu-id="569ac-244">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="569ac-245">Exemplarische Vorgehensweise: Hosting eines zusammengesetzten WPF-Steuer Elements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="569ac-245">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
