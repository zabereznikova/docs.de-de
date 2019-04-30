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
ms.openlocfilehash: 5b759baebb7192c1ee94b4aa925198864ba7a31a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62007161"
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a><span data-ttu-id="12cc0-102">Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen in WPF</span><span class="sxs-lookup"><span data-stu-id="12cc0-102">Walkthrough: Arranging Windows Forms Controls in WPF</span></span>
<span data-ttu-id="12cc0-103">In dieser exemplarischen Vorgehensweise erfahren Sie, wie Sie mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layoutfunktionen anordnen [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente in einer hybridanwendung.</span><span class="sxs-lookup"><span data-stu-id="12cc0-103">This walkthrough shows you how to use [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout features to arrange [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in a hybrid application.</span></span>  
  
 <span data-ttu-id="12cc0-104">In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="12cc0-104">Tasks illustrated in this walkthrough include:</span></span>  
  
- <span data-ttu-id="12cc0-105">Erstellen des Projekts.</span><span class="sxs-lookup"><span data-stu-id="12cc0-105">Creating the project.</span></span>  
  
- <span data-ttu-id="12cc0-106">Verwenden der Standardlayouteinstellungen.</span><span class="sxs-lookup"><span data-stu-id="12cc0-106">Using default layout settings.</span></span>  
  
- <span data-ttu-id="12cc0-107">Anpassen der Größe an Inhalt.</span><span class="sxs-lookup"><span data-stu-id="12cc0-107">Sizing to content.</span></span>  
  
- <span data-ttu-id="12cc0-108">Verwenden der absoluten Positionierung.</span><span class="sxs-lookup"><span data-stu-id="12cc0-108">Using absolute positioning.</span></span>  
  
- <span data-ttu-id="12cc0-109">Explizites Angeben der Größe.</span><span class="sxs-lookup"><span data-stu-id="12cc0-109">Specifying size explicitly.</span></span>  
  
- <span data-ttu-id="12cc0-110">Festlegen der Layouteigenschaften.</span><span class="sxs-lookup"><span data-stu-id="12cc0-110">Setting layout properties.</span></span>  
  
- <span data-ttu-id="12cc0-111">Grundlegendes zu Einschränkungen der Z-Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="12cc0-111">Understanding z-order limitations.</span></span>  
  
- <span data-ttu-id="12cc0-112">Andocken.</span><span class="sxs-lookup"><span data-stu-id="12cc0-112">Docking.</span></span>  
  
- <span data-ttu-id="12cc0-113">Einstellen der Sichtbarkeit.</span><span class="sxs-lookup"><span data-stu-id="12cc0-113">Setting visibility.</span></span>  
  
- <span data-ttu-id="12cc0-114">Hosten eines Steuerelements, das nicht gestreckt wird.</span><span class="sxs-lookup"><span data-stu-id="12cc0-114">Hosting a control that does not stretch.</span></span>  
  
- <span data-ttu-id="12cc0-115">Skalieren.</span><span class="sxs-lookup"><span data-stu-id="12cc0-115">Scaling.</span></span>  
  
- <span data-ttu-id="12cc0-116">Drehen.</span><span class="sxs-lookup"><span data-stu-id="12cc0-116">Rotating.</span></span>  
  
- <span data-ttu-id="12cc0-117">Einstellen von Abständen und Rändern.</span><span class="sxs-lookup"><span data-stu-id="12cc0-117">Setting padding and margins.</span></span>  
  
- <span data-ttu-id="12cc0-118">Verwenden von dynamischen Layoutcontainern.</span><span class="sxs-lookup"><span data-stu-id="12cc0-118">Using dynamic layout containers.</span></span>  
  
 <span data-ttu-id="12cc0-119">Eine vollständige codeauflistung der Aufgaben in dieser exemplarischen Vorgehensweise veranschaulicht, finden Sie unter [Anordnen von Windows Forms-Steuerelementen in WPF-Beispiel](https://go.microsoft.com/fwlink/?LinkID=159971).</span><span class="sxs-lookup"><span data-stu-id="12cc0-119">For a complete code listing of the tasks illustrated in this walkthrough, see [Arranging Windows Forms Controls in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=159971).</span></span>  
  
 <span data-ttu-id="12cc0-120">Wenn Sie fertig sind, haben Sie einen Überblick über [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] -Layoutfunktionen bei [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-basierte Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="12cc0-120">When you are finished, you will have an understanding of [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] layout features in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based applications.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="12cc0-121">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="12cc0-121">Prerequisites</span></span>  

<span data-ttu-id="12cc0-122">Für diese exemplarische Vorgehensweise benötigen Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="12cc0-122">You need Visual Studio to complete this walkthrough.</span></span>
  
## <a name="creating-the-project"></a><span data-ttu-id="12cc0-123">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="12cc0-123">Creating the Project</span></span>  
  
#### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="12cc0-124">So erstellen und richten Sie das Projekt ein</span><span class="sxs-lookup"><span data-stu-id="12cc0-124">To create and set up the project</span></span>  
  
1. <span data-ttu-id="12cc0-125">Erstellen einer WPF-Anwendungsprojekt mit dem Namen `WpfLayoutHostingWf`.</span><span class="sxs-lookup"><span data-stu-id="12cc0-125">Create a WPF Application project named `WpfLayoutHostingWf`.</span></span>  
  
2. <span data-ttu-id="12cc0-126">Fügen Sie im Projektmappen-Explorer Verweise auf die folgenden Assemblys hinzu.</span><span class="sxs-lookup"><span data-stu-id="12cc0-126">In Solution Explorer, add references to the following assemblies.</span></span>  
  
    - <span data-ttu-id="12cc0-127">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="12cc0-127">WindowsFormsIntegration</span></span>  
  
    - <span data-ttu-id="12cc0-128">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="12cc0-128">System.Windows.Forms</span></span>  
  
    - <span data-ttu-id="12cc0-129">System.Drawing</span><span class="sxs-lookup"><span data-stu-id="12cc0-129">System.Drawing</span></span>  
  
3. <span data-ttu-id="12cc0-130">Doppelklicken Sie auf „MainWindow.xaml“, um die Datei in der XAML-Ansicht zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="12cc0-130">Double-click MainWindow.xaml to open it in XAML view.</span></span>  
  
4. <span data-ttu-id="12cc0-131">In der <xref:System.Windows.Window> -Element, fügen Sie die folgenden [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Namespace-Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="12cc0-131">In the <xref:System.Windows.Window> element, add the following [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] namespace mapping.</span></span>  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5. <span data-ttu-id="12cc0-132">In der <xref:System.Windows.Controls.Grid> Elementsatz der <xref:System.Windows.Controls.Grid.ShowGridLines%2A> Eigenschaft `true` und fünf Zeilen und drei Spalten definieren.</span><span class="sxs-lookup"><span data-stu-id="12cc0-132">In the <xref:System.Windows.Controls.Grid> element set the <xref:System.Windows.Controls.Grid.ShowGridLines%2A> property to `true` and define five rows and three columns.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]  
  
## <a name="using-default-layout-settings"></a><span data-ttu-id="12cc0-133">Verwenden der Standardlayouteinstellungen</span><span class="sxs-lookup"><span data-stu-id="12cc0-133">Using Default Layout Settings</span></span>  
 <span data-ttu-id="12cc0-134">In der Standardeinstellung die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element behandelt das Layout für das gehostete [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="12cc0-134">By default, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element handles the layout for the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>  
  
#### <a name="to-use-default-layout-settings"></a><span data-ttu-id="12cc0-135">Verwenden der Standardlayouteinstellungen</span><span class="sxs-lookup"><span data-stu-id="12cc0-135">To use default layout settings</span></span>  
  
1. <span data-ttu-id="12cc0-136">Kopieren Sie den folgenden XAML in die <xref:System.Windows.Controls.Grid> Element.</span><span class="sxs-lookup"><span data-stu-id="12cc0-136">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]  
  
2. <span data-ttu-id="12cc0-137">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="12cc0-137">Press F5 to build and run the application.</span></span> <span data-ttu-id="12cc0-138">Die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Button?displayProperty=nameWithType> Steuerelement angezeigt wird, der <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="12cc0-138">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Button?displayProperty=nameWithType> control appears in the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="12cc0-139">Das gehostete Steuerelement wird basierend auf den Inhalt, Größe und die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element wird angepasst, sodass das gehostete Steuerelement angepasst.</span><span class="sxs-lookup"><span data-stu-id="12cc0-139">The hosted control is sized based on its content, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is sized to accommodate the hosted control.</span></span>  
  
## <a name="sizing-to-content"></a><span data-ttu-id="12cc0-140">Anpassen der Größe an Inhalt</span><span class="sxs-lookup"><span data-stu-id="12cc0-140">Sizing to Content</span></span>  
 <span data-ttu-id="12cc0-141">Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element stellt sicher, dass das gehostete Steuerelement angepasst wird, dass der Inhalt ordnungsgemäß angezeigt.</span><span class="sxs-lookup"><span data-stu-id="12cc0-141">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element ensures that the hosted control is sized to display its content properly.</span></span>  
  
#### <a name="to-size-to-content"></a><span data-ttu-id="12cc0-142">Anpassen der Größe an Inhalt</span><span class="sxs-lookup"><span data-stu-id="12cc0-142">To size to content</span></span>  
  
1. <span data-ttu-id="12cc0-143">Kopieren Sie den folgenden XAML in die <xref:System.Windows.Controls.Grid> Element.</span><span class="sxs-lookup"><span data-stu-id="12cc0-143">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]  
  
2. <span data-ttu-id="12cc0-144">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="12cc0-144">Press F5 to build and run the application.</span></span> <span data-ttu-id="12cc0-145">Die zwei neuen Schaltflächen-Steuerelemente sind die Größe der längeren Textzeichenfolge und einer größeren Schriftgrad ordnungsgemäß angezeigt werden und die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Elemente werden geändert, um die gehosteten Steuerelemente angepasst.</span><span class="sxs-lookup"><span data-stu-id="12cc0-145">The two new button controls are sized to display the longer text string and larger font size properly, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are resized to accommodate the hosted controls.</span></span>  
  
## <a name="using-absolute-positioning"></a><span data-ttu-id="12cc0-146">Verwenden der absoluten Positionierung</span><span class="sxs-lookup"><span data-stu-id="12cc0-146">Using Absolute Positioning</span></span>  
 <span data-ttu-id="12cc0-147">Sie können die absolute Positionierung verwenden, platzieren die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element an einer beliebigen Stelle in der Benutzeroberfläche (UI).</span><span class="sxs-lookup"><span data-stu-id="12cc0-147">You can use absolute positioning to place the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element anywhere in the user interface (UI).</span></span>  
  
#### <a name="to-use-absolute-positioning"></a><span data-ttu-id="12cc0-148">Verwenden der absoluten Positionierung</span><span class="sxs-lookup"><span data-stu-id="12cc0-148">To use absolute positioning</span></span>  
  
1. <span data-ttu-id="12cc0-149">Kopieren Sie den folgenden XAML in die <xref:System.Windows.Controls.Grid> Element.</span><span class="sxs-lookup"><span data-stu-id="12cc0-149">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]  
  
2. <span data-ttu-id="12cc0-150">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="12cc0-150">Press F5 to build and run the application.</span></span> <span data-ttu-id="12cc0-151">Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element wird 20 Pixel vom oberen Rand der Rasterzelle und 20 Pixel vom linken Rand platziert.</span><span class="sxs-lookup"><span data-stu-id="12cc0-151">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is placed 20 pixels from the top side of the grid cell and 20 pixels from the left.</span></span>  
  
## <a name="specifying-size-explicitly"></a><span data-ttu-id="12cc0-152">Explizites Angeben der Größe</span><span class="sxs-lookup"><span data-stu-id="12cc0-152">Specifying Size Explicitly</span></span>  
 <span data-ttu-id="12cc0-153">Sie können angeben, die Größe des der <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element mit dem <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="12cc0-153">You can specify the size of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element using the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span>  
  
#### <a name="to-specify-size-explicitly"></a><span data-ttu-id="12cc0-154">Explizites Angeben der Größe</span><span class="sxs-lookup"><span data-stu-id="12cc0-154">To specify size explicitly</span></span>  
  
1. <span data-ttu-id="12cc0-155">Kopieren Sie den folgenden XAML in die <xref:System.Windows.Controls.Grid> Element.</span><span class="sxs-lookup"><span data-stu-id="12cc0-155">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]  
  
2. <span data-ttu-id="12cc0-156">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="12cc0-156">Press F5 to build and run the application.</span></span> <span data-ttu-id="12cc0-157">Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> auf eine Größe von 50 Pixel breit und 70 Pixel hoch, Element festgelegt ist, ist damit kleiner als die standardlayouteinstellungen.</span><span class="sxs-lookup"><span data-stu-id="12cc0-157">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is set to a size of 50 pixels wide by 70 pixels high, which is smaller than the default layout settings.</span></span> <span data-ttu-id="12cc0-158">Den Inhalt der [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement wird entsprechend neu angeordnet.</span><span class="sxs-lookup"><span data-stu-id="12cc0-158">The content of the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is rearranged accordingly.</span></span>  
  
## <a name="setting-layout-properties"></a><span data-ttu-id="12cc0-159">Festlegen der Layouteigenschaften</span><span class="sxs-lookup"><span data-stu-id="12cc0-159">Setting Layout Properties</span></span>  
 <span data-ttu-id="12cc0-160">Layoutbezogene Eigenschaften immer für das gehostete Steuerelement legen Sie mithilfe der Eigenschaften von den <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element.</span><span class="sxs-lookup"><span data-stu-id="12cc0-160">Always set layout-related properties on the hosted control by using the properties of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="12cc0-161">Das Festlegen der Layouteigenschaften direkt für das gehostete Steuerelement führt zu unbeabsichtigten Ergebnissen.</span><span class="sxs-lookup"><span data-stu-id="12cc0-161">Setting layout properties directly on the hosted control will yield unintended results.</span></span>  
  
 <span data-ttu-id="12cc0-162">Festlegen von layoutbezogenen Eigenschaften für das gehostete Steuerelement in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] hat keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="12cc0-162">Setting layout-related properties on the hosted control in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] has no effect.</span></span>  
  
#### <a name="to-see-the-effects-of-setting-properties-on-the-hosted-control"></a><span data-ttu-id="12cc0-163">Anzeigen der Auswirkungen des Festlegens der Eigenschaften für das gehostete Steuerelement</span><span class="sxs-lookup"><span data-stu-id="12cc0-163">To see the effects of setting properties on the hosted control</span></span>  
  
1. <span data-ttu-id="12cc0-164">Kopieren Sie den folgenden XAML in die <xref:System.Windows.Controls.Grid> Element.</span><span class="sxs-lookup"><span data-stu-id="12cc0-164">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]  
  
2. <span data-ttu-id="12cc0-165">Doppelklicken Sie in Projektmappen-Explorer „MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="12cc0-165">In Solution Explorer, double-click MainWindow.xaml.</span></span> <span data-ttu-id="12cc0-166">vb“ oder „MainWindow.Xaml.cs“, um die Datei im Code-Editor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="12cc0-166">vb or MainWindow.xaml.cs to open it in the Code Editor.</span></span>  
  
3. <span data-ttu-id="12cc0-167">Kopieren Sie den folgenden Code der `MainWindow` Definition der Klasse.</span><span class="sxs-lookup"><span data-stu-id="12cc0-167">Copy the following code into the `MainWindow` class definition.</span></span>  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]

4. <span data-ttu-id="12cc0-168">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="12cc0-168">Press F5 to build and run the application.</span></span>

5. <span data-ttu-id="12cc0-169">Klicken Sie auf die **hier klicken** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="12cc0-169">Click the **Click me** button.</span></span> <span data-ttu-id="12cc0-170">Die `button1_Click` Ereignishandler legt die <xref:System.Windows.Forms.Control.Top%2A> und <xref:System.Windows.Forms.Control.Left%2A> Eigenschaften des gehosteten Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="12cc0-170">The `button1_Click` event handler sets the <xref:System.Windows.Forms.Control.Top%2A> and <xref:System.Windows.Forms.Control.Left%2A> properties on the hosted control.</span></span> <span data-ttu-id="12cc0-171">Dies bewirkt, dass das gehostete Steuerelement in neu positioniert werden die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element.</span><span class="sxs-lookup"><span data-stu-id="12cc0-171">This causes the hosted control to be repositioned within the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="12cc0-172">Der Host behält den gleichen Bildschirmbereich bei, jedoch wird das gehostete Steuerelement abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="12cc0-172">The host maintains the same screen area, but the hosted control is clipped.</span></span> <span data-ttu-id="12cc0-173">Stattdessen sollte das gehostete Steuerelement immer ausfüllen der <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element.</span><span class="sxs-lookup"><span data-stu-id="12cc0-173">Instead, the hosted control should always fill the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>

## <a name="understanding-z-order-limitations"></a><span data-ttu-id="12cc0-174">Grundlegendes zu Einschränkungen der Z-Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="12cc0-174">Understanding Z-Order Limitations</span></span>
 <span data-ttu-id="12cc0-175">Sichtbare <xref:System.Windows.Forms.Integration.WindowsFormsHost> Elemente werden immer über anderen WPF-Elemente gezeichnet werden soll, und sie die Z-Reihenfolge betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="12cc0-175">Visible <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are always drawn on top of other WPF elements, and they are unaffected by z-order.</span></span> <span data-ttu-id="12cc0-176">Um dieses Verhalten für die Z-Reihenfolge anzuzeigen, führen Sie folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="12cc0-176">To see this z-order behavior, do the following:</span></span>

1. <span data-ttu-id="12cc0-177">Kopieren Sie den folgenden XAML in die <xref:System.Windows.Controls.Grid> Element.</span><span class="sxs-lookup"><span data-stu-id="12cc0-177">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]

2. <span data-ttu-id="12cc0-178">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="12cc0-178">Press F5 to build and run the application.</span></span> <span data-ttu-id="12cc0-179">Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element über das Label-Element gezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="12cc0-179">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is painted over the label element.</span></span>

## <a name="docking"></a><span data-ttu-id="12cc0-180">Andocken</span><span class="sxs-lookup"><span data-stu-id="12cc0-180">Docking</span></span>
 <span data-ttu-id="12cc0-181"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Element unterstützt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] andocken.</span><span class="sxs-lookup"><span data-stu-id="12cc0-181"><xref:System.Windows.Forms.Integration.WindowsFormsHost> element supports [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] docking.</span></span> <span data-ttu-id="12cc0-182">Legen Sie die <xref:System.Windows.Controls.DockPanel.Dock%2A> angefügte Eigenschaft, um das gehostete Steuerelement in Andocken eine <xref:System.Windows.Controls.DockPanel> Element.</span><span class="sxs-lookup"><span data-stu-id="12cc0-182">Set the <xref:System.Windows.Controls.DockPanel.Dock%2A> attached property to dock the hosted control in a <xref:System.Windows.Controls.DockPanel> element.</span></span>

#### <a name="to-dock-a-hosted-control"></a><span data-ttu-id="12cc0-183">Andocke eines gehosteten Steuerelements</span><span class="sxs-lookup"><span data-stu-id="12cc0-183">To dock a hosted control</span></span>

1. <span data-ttu-id="12cc0-184">Kopieren Sie den folgenden XAML in die <xref:System.Windows.Controls.Grid> Element.</span><span class="sxs-lookup"><span data-stu-id="12cc0-184">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#9](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]

2. <span data-ttu-id="12cc0-185">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="12cc0-185">Press F5 to build and run the application.</span></span> <span data-ttu-id="12cc0-186">Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element rechts angedockt ist die <xref:System.Windows.Controls.DockPanel> Element.</span><span class="sxs-lookup"><span data-stu-id="12cc0-186">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is docked to the right side of the <xref:System.Windows.Controls.DockPanel> element.</span></span>

## <a name="setting-visibility"></a><span data-ttu-id="12cc0-187">Einstellen der Sichtbarkeit</span><span class="sxs-lookup"><span data-stu-id="12cc0-187">Setting Visibility</span></span>
 <span data-ttu-id="12cc0-188">Möglich Ihre [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] -Steuerelement ausblenden oder reduzieren, indem Sie die Einstellung der <xref:System.Windows.UIElement.Visibility%2A> Eigenschaft für die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element.</span><span class="sxs-lookup"><span data-stu-id="12cc0-188">You can make your [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control invisible or collapse it by setting the <xref:System.Windows.UIElement.Visibility%2A> property on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="12cc0-189">Wenn ein Steuerelement unsichtbar ist, wird es nicht angezeigt, es belegt jedoch Platz im Layoutbereich.</span><span class="sxs-lookup"><span data-stu-id="12cc0-189">When a control is invisible, it is not displayed, but it occupies layout space.</span></span> <span data-ttu-id="12cc0-190">Wenn ein Steuerelement reduziert ist, wird es nicht angezeigt, und es belegt auch keinen Platz im Layoutbereich.</span><span class="sxs-lookup"><span data-stu-id="12cc0-190">When a control is collapsed, it is not displayed, nor does it occupy layout space.</span></span>

#### <a name="to-set-the-visibility-of-a-hosted-control"></a><span data-ttu-id="12cc0-191">Festlegen der Sichtbarkeit eines gehosteten Steuerelements</span><span class="sxs-lookup"><span data-stu-id="12cc0-191">To set the visibility of a hosted control</span></span>

1. <span data-ttu-id="12cc0-192">Kopieren Sie den folgenden XAML in die <xref:System.Windows.Controls.Grid> Element.</span><span class="sxs-lookup"><span data-stu-id="12cc0-192">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#10](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]

2. <span data-ttu-id="12cc0-193">Kopieren Sie in „MainWindow.xaml.vb“ oder „MainWindow.xaml.cs“ den folgenden Code in die Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="12cc0-193">In MainWindow.xaml.vb or MainWindow.xaml.cs, copy the following code into the class definition.</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]

3. <span data-ttu-id="12cc0-194">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="12cc0-194">Press F5 to build and run the application.</span></span>

4. <span data-ttu-id="12cc0-195">Klicken Sie auf die **zum Ausblenden klicken** Schaltfläche, um die stellen die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="12cc0-195">Click the **Click to make invisible** button to make the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element invisible.</span></span>

5. <span data-ttu-id="12cc0-196">Klicken Sie auf die **zum Reduzieren klicken** Schaltfläche zum Ausblenden der <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element aus dem Layout vollständig.</span><span class="sxs-lookup"><span data-stu-id="12cc0-196">Click the **Click to collapse** button to hide the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element from the layout entirely.</span></span> <span data-ttu-id="12cc0-197">Wenn die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement reduziert ist, werden die umgebenden Elemente neu angeordnet, um dessen Bereich einzunehmen.</span><span class="sxs-lookup"><span data-stu-id="12cc0-197">When the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is collapsed, the surrounding elements are rearranged to occupy its space.</span></span>

## <a name="hosting-a-control-that-does-not-stretch"></a><span data-ttu-id="12cc0-198">Hosten eines Steuerelements, das nicht gestreckt wird</span><span class="sxs-lookup"><span data-stu-id="12cc0-198">Hosting a Control That Does Not Stretch</span></span>
 <span data-ttu-id="12cc0-199">Einige [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente haben eine feste Größe und können nicht gestreckt werden, um den verfügbaren Platz im Layout auszufüllen.</span><span class="sxs-lookup"><span data-stu-id="12cc0-199">Some [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have a fixed size and do not stretch to fill available space in the layout.</span></span> <span data-ttu-id="12cc0-200">Z. B. die <xref:System.Windows.Forms.MonthCalendar> Steuerelement zeigt einen Monat in einem festen Bereich.</span><span class="sxs-lookup"><span data-stu-id="12cc0-200">For example, the <xref:System.Windows.Forms.MonthCalendar> control displays a month in a fixed space.</span></span>

#### <a name="to-host-a-control-that-does-not-stretch"></a><span data-ttu-id="12cc0-201">Hosten eines Steuerelements, das nicht gestreckt wird</span><span class="sxs-lookup"><span data-stu-id="12cc0-201">To host a control that does not stretch</span></span>

1. <span data-ttu-id="12cc0-202">Kopieren Sie den folgenden XAML in die <xref:System.Windows.Controls.Grid> Element.</span><span class="sxs-lookup"><span data-stu-id="12cc0-202">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]

2. <span data-ttu-id="12cc0-203">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="12cc0-203">Press F5 to build and run the application.</span></span> <span data-ttu-id="12cc0-204">Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element wird in der Rasterzeile zentriert, aber es ist nicht gestreckt, um den verfügbaren Platz auszufüllen.</span><span class="sxs-lookup"><span data-stu-id="12cc0-204">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is centered in the grid row, but it is not stretched to fill the available space.</span></span> <span data-ttu-id="12cc0-205">Wenn das Fenster groß genug ist, wird möglicherweise angezeigt mindestens zwei Monate angezeigt, indem das gehostete <xref:System.Windows.Forms.MonthCalendar> -Steuerelement, aber diese sind in der Zeile zentriert.</span><span class="sxs-lookup"><span data-stu-id="12cc0-205">If the window is large enough, you may see two or more months displayed by the hosted <xref:System.Windows.Forms.MonthCalendar> control, but these are centered in the row.</span></span> <span data-ttu-id="12cc0-206">Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layout-Engine zentriert Elemente, deren Größe geändert werden können nicht um den verfügbaren Platz auszufüllen.</span><span class="sxs-lookup"><span data-stu-id="12cc0-206">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout engine centers elements that cannot be sized to fill the available space.</span></span>

## <a name="scaling"></a><span data-ttu-id="12cc0-207">Skalieren</span><span class="sxs-lookup"><span data-stu-id="12cc0-207">Scaling</span></span>
 <span data-ttu-id="12cc0-208">Im Gegensatz zu WPF-Elemente sind die meisten Windows Forms-Steuerelemente nicht kontinuierlich skalierbar.</span><span class="sxs-lookup"><span data-stu-id="12cc0-208">Unlike WPF elements, most Windows Forms controls are not continuously scalable.</span></span> <span data-ttu-id="12cc0-209">Um benutzerdefinierte Skalierung zu ermöglichen, Sie überschreiben die <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="12cc0-209">To provide custom scaling, you override the <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> method.</span></span>

#### <a name="to-scale-a-hosted-control-by-using-the-default-behavior"></a><span data-ttu-id="12cc0-210">Skalieren eines gehosteten Steuerelements mithilfe des Standardverhaltens</span><span class="sxs-lookup"><span data-stu-id="12cc0-210">To scale a hosted control by using the default behavior</span></span>

1. <span data-ttu-id="12cc0-211">Kopieren Sie den folgenden XAML in die <xref:System.Windows.Controls.Grid> Element.</span><span class="sxs-lookup"><span data-stu-id="12cc0-211">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]

2. <span data-ttu-id="12cc0-212">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="12cc0-212">Press F5 to build and run the application.</span></span> <span data-ttu-id="12cc0-213">Das gehostete Steuerelement und die umgebenden Elemente werden um den Faktor 0,5 skaliert.</span><span class="sxs-lookup"><span data-stu-id="12cc0-213">The hosted control and its surrounding elements are scaled by a factor of 0.5.</span></span> <span data-ttu-id="12cc0-214">Allerdings wird die Schriftart des gehosteten Steuerelements nicht skaliert.</span><span class="sxs-lookup"><span data-stu-id="12cc0-214">However, the hosted control's font is not scaled.</span></span>

<!-- This could use an example of custom scaling. -->

## <a name="rotating"></a><span data-ttu-id="12cc0-215">Drehen</span><span class="sxs-lookup"><span data-stu-id="12cc0-215">Rotating</span></span>
 <span data-ttu-id="12cc0-216">Im Gegensatz zu WPF-Elemente unterstützen Windows Forms-Steuerelemente keine Drehung.</span><span class="sxs-lookup"><span data-stu-id="12cc0-216">Unlike WPF elements, Windows Forms controls do not support rotation.</span></span> <span data-ttu-id="12cc0-217">Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element wird nicht mit anderen WPF-Elementen gedreht, wenn eine Drehtransformation angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="12cc0-217">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element does not rotate with other WPF elements when a rotation transformation is applied.</span></span> <span data-ttu-id="12cc0-218">Jeder andere Drehungswert als 180 Grad löst die <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="12cc0-218">Any rotation value other than 180 degrees raises the <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> event.</span></span>

#### <a name="to-see-the-effect-of-rotation-in-a-hybrid-application"></a><span data-ttu-id="12cc0-219">Anzeigen der Auswirkung der Drehung in einer Hybridanwendung</span><span class="sxs-lookup"><span data-stu-id="12cc0-219">To see the effect of rotation in a hybrid application</span></span>

1. <span data-ttu-id="12cc0-220">Kopieren Sie den folgenden XAML in die <xref:System.Windows.Controls.Grid> Element.</span><span class="sxs-lookup"><span data-stu-id="12cc0-220">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]

2. <span data-ttu-id="12cc0-221">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="12cc0-221">Press F5 to build and run the application.</span></span> <span data-ttu-id="12cc0-222">Das gehostete Steuerelement wird nicht gedreht, die umgebenden Elemente werden jedoch um einen Winkel von 180 Grad gedreht.</span><span class="sxs-lookup"><span data-stu-id="12cc0-222">The hosted control is not rotated, but its surrounding elements are rotated by an angle of 180 degrees.</span></span> <span data-ttu-id="12cc0-223">Sie müssen möglicherweise die Fenstergröße anpassen, um die Elemente zu sehen.</span><span class="sxs-lookup"><span data-stu-id="12cc0-223">You may have to resize the window to see the elements.</span></span>

## <a name="setting-padding-and-margins"></a><span data-ttu-id="12cc0-224">Einstellen von Abständen und Rändern</span><span class="sxs-lookup"><span data-stu-id="12cc0-224">Setting Padding and Margins</span></span>
 <span data-ttu-id="12cc0-225">Abstand und Ränder im [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Layout ähneln den Abständen und Rändern in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12cc0-225">Padding and margins in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout are similar to padding and margins in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="12cc0-226">Legen Sie einfach die <xref:System.Windows.Controls.Control.Padding%2A> und <xref:System.Windows.FrameworkElement.Margin%2A> Eigenschaften für die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element.</span><span class="sxs-lookup"><span data-stu-id="12cc0-226">Simply set the <xref:System.Windows.Controls.Control.Padding%2A> and <xref:System.Windows.FrameworkElement.Margin%2A> properties on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>

#### <a name="to-set-padding-and-margins-for-a-hosted-control"></a><span data-ttu-id="12cc0-227">Festlegen von Abstand und Rändern für ein gehostetes Steuerelement</span><span class="sxs-lookup"><span data-stu-id="12cc0-227">To set padding and margins for a hosted control</span></span>

1. <span data-ttu-id="12cc0-228">Kopieren Sie den folgenden XAML in die <xref:System.Windows.Controls.Grid> Element.</span><span class="sxs-lookup"><span data-stu-id="12cc0-228">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]

2. <span data-ttu-id="12cc0-229">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="12cc0-229">Press F5 to build and run the application.</span></span> <span data-ttu-id="12cc0-230">Die Einstellungen für Ränder und Abstände werden angewendet, an das gehostete [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente auf die gleiche Weise, die sie in angewendet werden sollen [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12cc0-230">The padding and margin settings are applied to the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in the same way they would be applied in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span>

## <a name="using-dynamic-layout-containers"></a><span data-ttu-id="12cc0-231">Verwenden von dynamischen Layoutcontainern</span><span class="sxs-lookup"><span data-stu-id="12cc0-231">Using Dynamic Layout Containers</span></span>
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <span data-ttu-id="12cc0-232">stellt zwei dynamische Layoutcontainer, <xref:System.Windows.Forms.FlowLayoutPanel> und <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="12cc0-232">provides two dynamic layout containers, <xref:System.Windows.Forms.FlowLayoutPanel> and <xref:System.Windows.Forms.TableLayoutPanel>.</span></span> <span data-ttu-id="12cc0-233">Sie können auch dieser Container in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layouts.</span><span class="sxs-lookup"><span data-stu-id="12cc0-233">You can also use these containers in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layouts.</span></span>

#### <a name="to-use-a-dynamic-layout-container"></a><span data-ttu-id="12cc0-234">Verwenden von dynamischen Layoutcontainern</span><span class="sxs-lookup"><span data-stu-id="12cc0-234">To use a dynamic layout container</span></span>

1. <span data-ttu-id="12cc0-235">Kopieren Sie den folgenden XAML in die <xref:System.Windows.Controls.Grid> Element.</span><span class="sxs-lookup"><span data-stu-id="12cc0-235">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#16](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]

2. <span data-ttu-id="12cc0-236">Kopieren Sie in „MainWindow.xaml.vb“ oder „MainWindow.xaml.cs“ den folgenden Code in die Klassedefinition.</span><span class="sxs-lookup"><span data-stu-id="12cc0-236">In MainWindow.xaml.vb or MainWindow.xaml.cs copy the following code into the class definition.</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]

3. <span data-ttu-id="12cc0-237">Fügen Sie einen Aufruf der `InitializeFlowLayoutPanel` -Methode im Konstruktor hinzu.</span><span class="sxs-lookup"><span data-stu-id="12cc0-237">Add a call to the `InitializeFlowLayoutPanel` method in the constructor.</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]  
  
4. <span data-ttu-id="12cc0-238">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="12cc0-238">Press F5 to build and run the application.</span></span> <span data-ttu-id="12cc0-239">Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element füllt die <xref:System.Windows.Controls.DockPanel>, und <xref:System.Windows.Forms.FlowLayoutPanel> ordnet seine untergeordneten Steuerelemente in der standardmäßigen <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span><span class="sxs-lookup"><span data-stu-id="12cc0-239">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element fills the <xref:System.Windows.Controls.DockPanel>, and <xref:System.Windows.Forms.FlowLayoutPanel> arranges its child controls in the default <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12cc0-240">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12cc0-240">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="12cc0-241">Entwerfen von XAML-Code in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="12cc0-241">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="12cc0-242">Überlegungen zum Layout für das WindowsFormsHost-Element</span><span class="sxs-lookup"><span data-stu-id="12cc0-242">Layout Considerations for the WindowsFormsHost Element</span></span>](layout-considerations-for-the-windowsformshost-element.md)
- [<span data-ttu-id="12cc0-243">Anordnen von Windows Forms-Steuerelementen in WPF-Beispiel</span><span class="sxs-lookup"><span data-stu-id="12cc0-243">Arranging Windows Forms Controls in WPF Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159971)
- [<span data-ttu-id="12cc0-244">Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF</span><span class="sxs-lookup"><span data-stu-id="12cc0-244">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="12cc0-245">Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="12cc0-245">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
