---
title: 'Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen in WPF'
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
- hybrid applications [WPF interoperability]
- arranging controls [WPF]
ms.assetid: a1db8049-15c7-45d6-ae3d-36a6735cb848
caps.latest.revision: "31"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 67bfa913627d33238aea92acdd49b6d2ecfef2a2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a><span data-ttu-id="ba492-102">Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen in WPF</span><span class="sxs-lookup"><span data-stu-id="ba492-102">Walkthrough: Arranging Windows Forms Controls in WPF</span></span>
<span data-ttu-id="ba492-103">In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Sie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layoutfunktionen anordnen [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente in einer hybridanwendung.</span><span class="sxs-lookup"><span data-stu-id="ba492-103">This walkthrough shows you how to use [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout features to arrange [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in a hybrid application.</span></span>  
  
 <span data-ttu-id="ba492-104">In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="ba492-104">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="ba492-105">Erstellen des Projekts.</span><span class="sxs-lookup"><span data-stu-id="ba492-105">Creating the project.</span></span>  
  
-   <span data-ttu-id="ba492-106">Verwenden der Standardlayouteinstellungen.</span><span class="sxs-lookup"><span data-stu-id="ba492-106">Using default layout settings.</span></span>  
  
-   <span data-ttu-id="ba492-107">Anpassen der Größe an Inhalt.</span><span class="sxs-lookup"><span data-stu-id="ba492-107">Sizing to content.</span></span>  
  
-   <span data-ttu-id="ba492-108">Verwenden der absoluten Positionierung.</span><span class="sxs-lookup"><span data-stu-id="ba492-108">Using absolute positioning.</span></span>  
  
-   <span data-ttu-id="ba492-109">Explizites Angeben der Größe.</span><span class="sxs-lookup"><span data-stu-id="ba492-109">Specifying size explicitly.</span></span>  
  
-   <span data-ttu-id="ba492-110">Festlegen der Layouteigenschaften.</span><span class="sxs-lookup"><span data-stu-id="ba492-110">Setting layout properties.</span></span>  
  
-   <span data-ttu-id="ba492-111">Grundlegendes zu Einschränkungen der Z-Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="ba492-111">Understanding z-order limitations.</span></span>  
  
-   <span data-ttu-id="ba492-112">Andocken.</span><span class="sxs-lookup"><span data-stu-id="ba492-112">Docking.</span></span>  
  
-   <span data-ttu-id="ba492-113">Einstellen der Sichtbarkeit.</span><span class="sxs-lookup"><span data-stu-id="ba492-113">Setting visibility.</span></span>  
  
-   <span data-ttu-id="ba492-114">Hosten eines Steuerelements, das nicht gestreckt wird.</span><span class="sxs-lookup"><span data-stu-id="ba492-114">Hosting a control that does not stretch.</span></span>  
  
-   <span data-ttu-id="ba492-115">Skalieren.</span><span class="sxs-lookup"><span data-stu-id="ba492-115">Scaling.</span></span>  
  
-   <span data-ttu-id="ba492-116">Drehen.</span><span class="sxs-lookup"><span data-stu-id="ba492-116">Rotating.</span></span>  
  
-   <span data-ttu-id="ba492-117">Einstellen von Abständen und Rändern.</span><span class="sxs-lookup"><span data-stu-id="ba492-117">Setting padding and margins.</span></span>  
  
-   <span data-ttu-id="ba492-118">Verwenden von dynamischen Layoutcontainern.</span><span class="sxs-lookup"><span data-stu-id="ba492-118">Using dynamic layout containers.</span></span>  
  
 <span data-ttu-id="ba492-119">Vollständige Codeliste der Aufgaben in dieser exemplarischen Vorgehensweise veranschaulicht, finden Sie unter [Anordnen von Windows Forms-Steuerelementen im WPF-Beispiel](http://go.microsoft.com/fwlink/?LinkID=159971).</span><span class="sxs-lookup"><span data-stu-id="ba492-119">For a complete code listing of the tasks illustrated in this walkthrough, see [Arranging Windows Forms Controls in WPF Sample](http://go.microsoft.com/fwlink/?LinkID=159971).</span></span>  
  
 <span data-ttu-id="ba492-120">Wenn Sie fertig sind, müssen Sie einen Überblick über [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Layout-Funktionen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-basierten Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="ba492-120">When you are finished, you will have an understanding of [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] layout features in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based applications.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ba492-121">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="ba492-121">Prerequisites</span></span>  
 <span data-ttu-id="ba492-122">Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="ba492-122">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]<span data-ttu-id="ba492-123">.</span><span class="sxs-lookup"><span data-stu-id="ba492-123">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="ba492-124">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="ba492-124">Creating the Project</span></span>  
  
#### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="ba492-125">So erstellen und richten Sie das Projekt ein</span><span class="sxs-lookup"><span data-stu-id="ba492-125">To create and set up the project</span></span>  
  
1.  <span data-ttu-id="ba492-126">Erstellen Sie ein WPF-Anwendungsprojekt mit dem Namen `WpfLayoutHostingWf`.</span><span class="sxs-lookup"><span data-stu-id="ba492-126">Create a WPF Application project named `WpfLayoutHostingWf`.</span></span>  
  
2.  <span data-ttu-id="ba492-127">Fügen Sie im Projektmappen-Explorer Verweise auf die folgenden Assemblys hinzu.</span><span class="sxs-lookup"><span data-stu-id="ba492-127">In Solution Explorer, add references to the following assemblies.</span></span>  
  
    -   <span data-ttu-id="ba492-128">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="ba492-128">WindowsFormsIntegration</span></span>  
  
    -   <span data-ttu-id="ba492-129">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="ba492-129">System.Windows.Forms</span></span>  
  
    -   <span data-ttu-id="ba492-130">System.Drawing</span><span class="sxs-lookup"><span data-stu-id="ba492-130">System.Drawing</span></span>  
  
3.  <span data-ttu-id="ba492-131">Doppelklicken Sie auf „MainWindow.xaml“, um die Datei in der XAML-Ansicht zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ba492-131">Double-click MainWindow.xaml to open it in XAML view.</span></span>  
  
4.  <span data-ttu-id="ba492-132">In der <xref:System.Windows.Window> Element, fügen Sie die folgenden [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Namespacezuordnung.</span><span class="sxs-lookup"><span data-stu-id="ba492-132">In the <xref:System.Windows.Window> element, add the following [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] namespace mapping.</span></span>  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  <span data-ttu-id="ba492-133">In der <xref:System.Windows.Controls.Grid> Elementsatz die <xref:System.Windows.Controls.Grid.ShowGridLines%2A> Eigenschaft `true` fünf Zeilen und drei Spalten definieren.</span><span class="sxs-lookup"><span data-stu-id="ba492-133">In the <xref:System.Windows.Controls.Grid> element set the <xref:System.Windows.Controls.Grid.ShowGridLines%2A> property to `true` and define five rows and three columns.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]  
  
## <a name="using-default-layout-settings"></a><span data-ttu-id="ba492-134">Verwenden der Standardlayouteinstellungen</span><span class="sxs-lookup"><span data-stu-id="ba492-134">Using Default Layout Settings</span></span>  
 <span data-ttu-id="ba492-135">Wird standardmäßig die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element behandelt das Layout für das gehostete [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ba492-135">By default, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element handles the layout for the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>  
  
#### <a name="to-use-default-layout-settings"></a><span data-ttu-id="ba492-136">Verwenden der Standardlayouteinstellungen</span><span class="sxs-lookup"><span data-stu-id="ba492-136">To use default layout settings</span></span>  
  
1.  <span data-ttu-id="ba492-137">Kopieren Sie den folgenden XAML-Code in die <xref:System.Windows.Controls.Grid> Element.</span><span class="sxs-lookup"><span data-stu-id="ba492-137">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]  
  
2.  <span data-ttu-id="ba492-138">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ba492-138">Press F5 to build and run the application.</span></span> <span data-ttu-id="ba492-139">Die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Button?displayProperty=nameWithType> Steuerelement wird in der <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="ba492-139">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Button?displayProperty=nameWithType> control appears in the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="ba492-140">Das gehostete Steuerelement wird basierend auf seinen Inhalt angepasst und der <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element wird angepasst, um das gehostete Steuerelement aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="ba492-140">The hosted control is sized based on its content, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is sized to accommodate the hosted control.</span></span>  
  
## <a name="sizing-to-content"></a><span data-ttu-id="ba492-141">Anpassen der Größe an Inhalt</span><span class="sxs-lookup"><span data-stu-id="ba492-141">Sizing to Content</span></span>  
 <span data-ttu-id="ba492-142">Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Elements sicher, dass das gehostete Steuerelement festgelegt wird, um seinen Inhalt ordnungsgemäß angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ba492-142">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element ensures that the hosted control is sized to display its content properly.</span></span>  
  
#### <a name="to-size-to-content"></a><span data-ttu-id="ba492-143">Anpassen der Größe an Inhalt</span><span class="sxs-lookup"><span data-stu-id="ba492-143">To size to content</span></span>  
  
1.  <span data-ttu-id="ba492-144">Kopieren Sie den folgenden XAML-Code in die <xref:System.Windows.Controls.Grid> Element.</span><span class="sxs-lookup"><span data-stu-id="ba492-144">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]  
  
2.  <span data-ttu-id="ba492-145">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ba492-145">Press F5 to build and run the application.</span></span> <span data-ttu-id="ba492-146">Die zwei neue Schaltflächen-Steuerelemente sind Größe angepasst, um die Textzeichenfolge länger und größere Schriftgröße ordnungsgemäß angezeigt werden und die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Elemente werden geändert, um die gehosteten Steuerelemente angepasst.</span><span class="sxs-lookup"><span data-stu-id="ba492-146">The two new button controls are sized to display the longer text string and larger font size properly, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are resized to accommodate the hosted controls.</span></span>  
  
## <a name="using-absolute-positioning"></a><span data-ttu-id="ba492-147">Verwenden der absoluten Positionierung</span><span class="sxs-lookup"><span data-stu-id="ba492-147">Using Absolute Positioning</span></span>  
 <span data-ttu-id="ba492-148">Sie können absolute Positionierung Platzieren der <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element an einer beliebigen Stelle in der Benutzeroberfläche (UI).</span><span class="sxs-lookup"><span data-stu-id="ba492-148">You can use absolute positioning to place the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element anywhere in the user interface (UI).</span></span>  
  
#### <a name="to-use-absolute-positioning"></a><span data-ttu-id="ba492-149">Verwenden der absoluten Positionierung</span><span class="sxs-lookup"><span data-stu-id="ba492-149">To use absolute positioning</span></span>  
  
1.  <span data-ttu-id="ba492-150">Kopieren Sie den folgenden XAML-Code in die <xref:System.Windows.Controls.Grid> Element.</span><span class="sxs-lookup"><span data-stu-id="ba492-150">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]  
  
2.  <span data-ttu-id="ba492-151">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ba492-151">Press F5 to build and run the application.</span></span> <span data-ttu-id="ba492-152">Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> 20 Pixel vom oberen Rand der Rasterzelle und 20 Pixel vom linken Element befindet.</span><span class="sxs-lookup"><span data-stu-id="ba492-152">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is placed 20 pixels from the top side of the grid cell and 20 pixels from the left.</span></span>  
  
## <a name="specifying-size-explicitly"></a><span data-ttu-id="ba492-153">Explizites Angeben der Größe</span><span class="sxs-lookup"><span data-stu-id="ba492-153">Specifying Size Explicitly</span></span>  
 <span data-ttu-id="ba492-154">Sie können die Größe der angeben der <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element mit der <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="ba492-154">You can specify the size of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element using the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span>  
  
#### <a name="to-specify-size-explicitly"></a><span data-ttu-id="ba492-155">Explizites Angeben der Größe</span><span class="sxs-lookup"><span data-stu-id="ba492-155">To specify size explicitly</span></span>  
  
1.  <span data-ttu-id="ba492-156">Kopieren Sie den folgenden XAML-Code in die <xref:System.Windows.Controls.Grid> Element.</span><span class="sxs-lookup"><span data-stu-id="ba492-156">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]  
  
2.  <span data-ttu-id="ba492-157">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ba492-157">Press F5 to build and run the application.</span></span> <span data-ttu-id="ba492-158">Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element festgelegt, wird er auf eine Größe von 50 Pixel breit und 70 Pixel hoch, die kleiner als die Standardeinstellungen für das Layout.</span><span class="sxs-lookup"><span data-stu-id="ba492-158">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is set to a size of 50 pixels wide by 70 pixels high, which is smaller than the default layout settings.</span></span> <span data-ttu-id="ba492-159">Der Inhalt der [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement wird entsprechend neu angeordnet.</span><span class="sxs-lookup"><span data-stu-id="ba492-159">The content of the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is rearranged accordingly.</span></span>  
  
## <a name="setting-layout-properties"></a><span data-ttu-id="ba492-160">Festlegen der Layouteigenschaften</span><span class="sxs-lookup"><span data-stu-id="ba492-160">Setting Layout Properties</span></span>  
 <span data-ttu-id="ba492-161">Layout-bezogene Eigenschaften immer im gehosteten Steuerelement festgelegt, wird mit den Eigenschaften des der <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element.</span><span class="sxs-lookup"><span data-stu-id="ba492-161">Always set layout-related properties on the hosted control by using the properties of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="ba492-162">Das Festlegen der Layouteigenschaften direkt für das gehostete Steuerelement führt zu unbeabsichtigten Ergebnissen.</span><span class="sxs-lookup"><span data-stu-id="ba492-162">Setting layout properties directly on the hosted control will yield unintended results.</span></span>  
  
 <span data-ttu-id="ba492-163">Festlegen von layoutbezogenen Eigenschaften für das gehostete Steuerelement im [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] hat keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="ba492-163">Setting layout-related properties on the hosted control in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] has no effect.</span></span>  
  
#### <a name="to-see-the-effects-of-setting-properties-on-the-hosted-control"></a><span data-ttu-id="ba492-164">Anzeigen der Auswirkungen des Festlegens der Eigenschaften für das gehostete Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ba492-164">To see the effects of setting properties on the hosted control</span></span>  
  
1.  <span data-ttu-id="ba492-165">Kopieren Sie den folgenden XAML-Code in die <xref:System.Windows.Controls.Grid> Element.</span><span class="sxs-lookup"><span data-stu-id="ba492-165">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]  
  
2.  <span data-ttu-id="ba492-166">Doppelklicken Sie in Projektmappen-Explorer „MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="ba492-166">In Solution Explorer, double-click MainWindow.xaml.</span></span> <span data-ttu-id="ba492-167">vb“ oder „MainWindow.Xaml.cs“, um die Datei im Code-Editor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ba492-167">vb or MainWindow.xaml.cs to open it in the Code Editor.</span></span>  
  
3.  <span data-ttu-id="ba492-168">Kopieren Sie den folgenden Code in die `MainWindow` Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="ba492-168">Copy the following code into the `MainWindow` class definition.</span></span>  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]  
  
4.  <span data-ttu-id="ba492-169">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ba492-169">Press F5 to build and run the application.</span></span>  
  
5.  <span data-ttu-id="ba492-170">Klicken Sie auf die **Click me** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="ba492-170">Click the **Click me** button.</span></span> <span data-ttu-id="ba492-171">Die `button1_Click` Ereignishandler legt die <xref:System.Windows.Forms.Control.Top%2A> und <xref:System.Windows.Forms.Control.Left%2A> Eigenschaften im gehosteten Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ba492-171">The `button1_Click` event handler sets the <xref:System.Windows.Forms.Control.Top%2A> and <xref:System.Windows.Forms.Control.Left%2A> properties on the hosted control.</span></span> <span data-ttu-id="ba492-172">Dies bewirkt, dass das gehostete Steuerelement innerhalb neu angeordnet werden die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element.</span><span class="sxs-lookup"><span data-stu-id="ba492-172">This causes the hosted control to be repositioned within the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="ba492-173">Der Host behält den gleichen Bildschirmbereich bei, jedoch wird das gehostete Steuerelement abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="ba492-173">The host maintains the same screen area, but the hosted control is clipped.</span></span> <span data-ttu-id="ba492-174">Das gehostete Steuerelement sollte jedoch immer ausfüllen der <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element.</span><span class="sxs-lookup"><span data-stu-id="ba492-174">Instead, the hosted control should always fill the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>  
  
## <a name="understanding-z-order-limitations"></a><span data-ttu-id="ba492-175">Grundlegendes zu Einschränkungen der Z-Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="ba492-175">Understanding Z-Order Limitations</span></span>  
 <span data-ttu-id="ba492-176">Standardmäßig sichtbar <xref:System.Windows.Forms.Integration.WindowsFormsHost> Elemente werden immer gezeichnet, zusätzlich zu anderen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Elemente, und Z-Reihenfolge nicht betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="ba492-176">By default, visible <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are always drawn on top of other [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elements, and they are unaffected by z-order.</span></span> <span data-ttu-id="ba492-177">Legen Sie zum Aktivieren der Z-Reihenfolge der <xref:System.Windows.Interop.HwndHost.IsRedirected%2A> Eigenschaft von der <xref:System.Windows.Forms.Integration.WindowsFormsHost> auf "true" und die <xref:System.Windows.Interop.HwndHost.CompositionMode%2A> Eigenschaft <xref:System.Windows.Interop.CompositionMode.Full> oder <xref:System.Windows.Interop.CompositionMode.OutputOnly>.</span><span class="sxs-lookup"><span data-stu-id="ba492-177">To enable z-ordering, set the <xref:System.Windows.Interop.HwndHost.IsRedirected%2A> property of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> to true and the <xref:System.Windows.Interop.HwndHost.CompositionMode%2A> property to <xref:System.Windows.Interop.CompositionMode.Full> or <xref:System.Windows.Interop.CompositionMode.OutputOnly>.</span></span>  
  
#### <a name="to-see-the-default-z-order-behavior"></a><span data-ttu-id="ba492-178">Anzeigen des Standardverhaltens für die Z-Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="ba492-178">To see the default z-order behavior</span></span>  
  
1.  <span data-ttu-id="ba492-179">Kopieren Sie den folgenden XAML-Code in die <xref:System.Windows.Controls.Grid> Element.</span><span class="sxs-lookup"><span data-stu-id="ba492-179">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]  
  
2.  <span data-ttu-id="ba492-180">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ba492-180">Press F5 to build and run the application.</span></span> <span data-ttu-id="ba492-181">Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element über das Label-Element gezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="ba492-181">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is painted over the label element.</span></span>  
  
#### <a name="to-see-the-z-order-behavior-when-isredirected-is-true"></a><span data-ttu-id="ba492-182">Anzeigen des Verhaltens der Z-Reihenfolge, wenn IsRedirected auf true festgelegt ist</span><span class="sxs-lookup"><span data-stu-id="ba492-182">To see the z-order behavior when IsRedirected is true</span></span>  
  
1.  <span data-ttu-id="ba492-183">Ersetzen Sie im vorherigen Beispiel der Z-Reihenfolge durch Folgendes XAML.</span><span class="sxs-lookup"><span data-stu-id="ba492-183">Replace the previous z-order example with the following XAML.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#8b](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml#8b)]  
  
     <span data-ttu-id="ba492-184">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ba492-184">Press F5 to build and run the application.</span></span> <span data-ttu-id="ba492-185">Das Label-Element gezeichnet wird, über die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element.</span><span class="sxs-lookup"><span data-stu-id="ba492-185">The label element is painted over the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>  
  
## <a name="docking"></a><span data-ttu-id="ba492-186">Andocken</span><span class="sxs-lookup"><span data-stu-id="ba492-186">Docking</span></span>  
 <span data-ttu-id="ba492-187"><xref:System.Windows.Forms.Integration.WindowsFormsHost>Element unterstützt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] andocken.</span><span class="sxs-lookup"><span data-stu-id="ba492-187"><xref:System.Windows.Forms.Integration.WindowsFormsHost> element supports [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] docking.</span></span> <span data-ttu-id="ba492-188">Legen Sie die <xref:System.Windows.Controls.DockPanel.Dock%2A> angefügte Eigenschaft, um das gehostete Steuerelement im Andocken ein <xref:System.Windows.Controls.DockPanel> Element.</span><span class="sxs-lookup"><span data-stu-id="ba492-188">Set the <xref:System.Windows.Controls.DockPanel.Dock%2A> attached property to dock the hosted control in a <xref:System.Windows.Controls.DockPanel> element.</span></span>  
  
#### <a name="to-dock-a-hosted-control"></a><span data-ttu-id="ba492-189">Andocke eines gehosteten Steuerelements</span><span class="sxs-lookup"><span data-stu-id="ba492-189">To dock a hosted control</span></span>  
  
1.  <span data-ttu-id="ba492-190">Kopieren Sie den folgenden XAML-Code in die <xref:System.Windows.Controls.Grid> Element.</span><span class="sxs-lookup"><span data-stu-id="ba492-190">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]  
  
2.  <span data-ttu-id="ba492-191">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ba492-191">Press F5 to build and run the application.</span></span> <span data-ttu-id="ba492-192">Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element auf der rechten Seite des angedockt ist die <xref:System.Windows.Controls.DockPanel> Element.</span><span class="sxs-lookup"><span data-stu-id="ba492-192">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is docked to the right side of the <xref:System.Windows.Controls.DockPanel> element.</span></span>  
  
## <a name="setting-visibility"></a><span data-ttu-id="ba492-193">Einstellen der Sichtbarkeit</span><span class="sxs-lookup"><span data-stu-id="ba492-193">Setting Visibility</span></span>  
 <span data-ttu-id="ba492-194">Sie vornehmen können Ihre [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] unsichtbar zu steuern oder zu reduzieren, indem Sie festlegen der <xref:System.Windows.UIElement.Visibility%2A> Eigenschaft auf die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element.</span><span class="sxs-lookup"><span data-stu-id="ba492-194">You can make your [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control invisible or collapse it by setting the <xref:System.Windows.UIElement.Visibility%2A> property on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="ba492-195">Wenn ein Steuerelement unsichtbar ist, wird es nicht angezeigt, es belegt jedoch Platz im Layoutbereich.</span><span class="sxs-lookup"><span data-stu-id="ba492-195">When a control is invisible, it is not displayed, but it occupies layout space.</span></span> <span data-ttu-id="ba492-196">Wenn ein Steuerelement reduziert ist, wird es nicht angezeigt, und es belegt auch keinen Platz im Layoutbereich.</span><span class="sxs-lookup"><span data-stu-id="ba492-196">When a control is collapsed, it is not displayed, nor does it occupy layout space.</span></span>  
  
#### <a name="to-set-the-visibility-of-a-hosted-control"></a><span data-ttu-id="ba492-197">Festlegen der Sichtbarkeit eines gehosteten Steuerelements</span><span class="sxs-lookup"><span data-stu-id="ba492-197">To set the visibility of a hosted control</span></span>  
  
1.  <span data-ttu-id="ba492-198">Kopieren Sie den folgenden XAML-Code in die <xref:System.Windows.Controls.Grid> Element.</span><span class="sxs-lookup"><span data-stu-id="ba492-198">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]  
  
2.  <span data-ttu-id="ba492-199">Kopieren Sie in „MainWindow.xaml.vb“ oder „MainWindow.xaml.cs“ den folgenden Code in die Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="ba492-199">In MainWindow.xaml.vb or MainWindow.xaml.cs, copy the following code into the class definition.</span></span>  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]  
  
3.  <span data-ttu-id="ba492-200">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ba492-200">Press F5 to build and run the application.</span></span>  
  
4.  <span data-ttu-id="ba492-201">Klicken Sie auf die **klicken Sie hier, um unsichtbar zu machen** Schaltfläche stellen die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="ba492-201">Click the **Click to make invisible** button to make the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element invisible.</span></span>  
  
5.  <span data-ttu-id="ba492-202">Klicken Sie auf die **zum Reduzieren** Schaltfläche Ausblenden der <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element aus dem Layout vollständig.</span><span class="sxs-lookup"><span data-stu-id="ba492-202">Click the **Click to collapse** button to hide the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element from the layout entirely.</span></span> <span data-ttu-id="ba492-203">Wenn die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement reduziert ist, werden die umgebenden Elemente neu angeordnet, um seine Platz einnehmen.</span><span class="sxs-lookup"><span data-stu-id="ba492-203">When the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is collapsed, the surrounding elements are rearranged to occupy its space.</span></span>  
  
## <a name="hosting-a-control-that-does-not-stretch"></a><span data-ttu-id="ba492-204">Hosten eines Steuerelements, das nicht gestreckt wird</span><span class="sxs-lookup"><span data-stu-id="ba492-204">Hosting a Control That Does Not Stretch</span></span>  
 <span data-ttu-id="ba492-205">Einige [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente verfügen über eine feste Größe und können nicht gestreckt werden, um das Layout verfügbaren Platz auszufüllen.</span><span class="sxs-lookup"><span data-stu-id="ba492-205">Some [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have a fixed size and do not stretch to fill available space in the layout.</span></span> <span data-ttu-id="ba492-206">Z. B. die <xref:System.Windows.Forms.MonthCalendar> Steuerelement ein Monats in einem festen Bereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ba492-206">For example, the <xref:System.Windows.Forms.MonthCalendar> control displays a month in a fixed space.</span></span>  
  
#### <a name="to-host-a-control-that-does-not-stretch"></a><span data-ttu-id="ba492-207">Hosten eines Steuerelements, das nicht gestreckt wird</span><span class="sxs-lookup"><span data-stu-id="ba492-207">To host a control that does not stretch</span></span>  
  
1.  <span data-ttu-id="ba492-208">Kopieren Sie den folgenden XAML-Code in die <xref:System.Windows.Controls.Grid> Element.</span><span class="sxs-lookup"><span data-stu-id="ba492-208">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]  
  
2.  <span data-ttu-id="ba492-209">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ba492-209">Press F5 to build and run the application.</span></span> <span data-ttu-id="ba492-210">Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element wird in der Rasterzeile zentriert, aber es ist nicht gestreckt, um den verfügbaren Platz auszufüllen.</span><span class="sxs-lookup"><span data-stu-id="ba492-210">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is centered in the grid row, but it is not stretched to fill the available space.</span></span> <span data-ttu-id="ba492-211">Wenn das Fenster groß genug ist, werden möglicherweise zwei oder mehr Monate angezeigt, die von der gehosteten <xref:System.Windows.Forms.MonthCalendar> -Steuerelement, doch diese sind in der Zeile zentriert.</span><span class="sxs-lookup"><span data-stu-id="ba492-211">If the window is large enough, you may see two or more months displayed by the hosted <xref:System.Windows.Forms.MonthCalendar> control, but these are centered in the row.</span></span> <span data-ttu-id="ba492-212">Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layoutmodul zentriert Elemente, deren Größe geändert werden können nicht um den verfügbaren Platz auszufüllen.</span><span class="sxs-lookup"><span data-stu-id="ba492-212">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout engine centers elements that cannot be sized to fill the available space.</span></span>  
  
## <a name="scaling"></a><span data-ttu-id="ba492-213">Skalieren</span><span class="sxs-lookup"><span data-stu-id="ba492-213">Scaling</span></span>  
 <span data-ttu-id="ba492-214">Im Gegensatz zu [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Elemente, die meisten [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente können nicht fortlaufend.</span><span class="sxs-lookup"><span data-stu-id="ba492-214">Unlike [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elements, most [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls are not continuously scalable.</span></span> <span data-ttu-id="ba492-215">Wird standardmäßig die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element skaliert sein gehostetes Steuerelement, wenn möglich.</span><span class="sxs-lookup"><span data-stu-id="ba492-215">By default, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element scales its hosted control when possible.</span></span>  <span data-ttu-id="ba492-216">Um vollwertige Skalierung zu aktivieren, legen die <xref:System.Windows.Interop.HwndHost.IsRedirected%2A> Eigenschaft von der <xref:System.Windows.Forms.Integration.WindowsFormsHost> auf "true" und der <xref:System.Windows.Interop.HwndHost.CompositionMode%2A> Eigenschaft <xref:System.Windows.Interop.CompositionMode.Full> oder <xref:System.Windows.Interop.CompositionMode.OutputOnly>.</span><span class="sxs-lookup"><span data-stu-id="ba492-216">To enable full-fledged scaling, set the <xref:System.Windows.Interop.HwndHost.IsRedirected%2A> property of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> to true and the <xref:System.Windows.Interop.HwndHost.CompositionMode%2A> property to <xref:System.Windows.Interop.CompositionMode.Full> or <xref:System.Windows.Interop.CompositionMode.OutputOnly>.</span></span>  
  
#### <a name="to-scale-a-hosted-control-by-using-the-default-behavior"></a><span data-ttu-id="ba492-217">Skalieren eines gehosteten Steuerelements mithilfe des Standardverhaltens</span><span class="sxs-lookup"><span data-stu-id="ba492-217">To scale a hosted control by using the default behavior</span></span>  
  
1.  <span data-ttu-id="ba492-218">Kopieren Sie den folgenden XAML-Code in die <xref:System.Windows.Controls.Grid> Element.</span><span class="sxs-lookup"><span data-stu-id="ba492-218">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]  
  
2.  <span data-ttu-id="ba492-219">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ba492-219">Press F5 to build and run the application.</span></span> <span data-ttu-id="ba492-220">Das gehostete Steuerelement und die umgebenden Elemente werden um den Faktor 0,5 skaliert.</span><span class="sxs-lookup"><span data-stu-id="ba492-220">The hosted control and its surrounding elements are scaled by a factor of 0.5.</span></span> <span data-ttu-id="ba492-221">Allerdings wird die Schriftart des gehosteten Steuerelements nicht skaliert.</span><span class="sxs-lookup"><span data-stu-id="ba492-221">However, the hosted control's font is not scaled.</span></span>  
  
#### <a name="to-scale-a-hosted-control-by-setting-isredirected-to-true"></a><span data-ttu-id="ba492-222">Skalieren eines gehosteten Steuerelements durch Festlegen von IsRedirected auf True</span><span class="sxs-lookup"><span data-stu-id="ba492-222">To scale a hosted control by setting IsRedirected to true</span></span>  
  
1.  <span data-ttu-id="ba492-223">Ersetzen Sie das vorherige Beispiel für die Skalierung durch das folgende XAML.</span><span class="sxs-lookup"><span data-stu-id="ba492-223">Replace the previous scaling example with the following XAML.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#12b](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml#12b)]  
  
2.  <span data-ttu-id="ba492-224">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ba492-224">Press F5 to build and run the application.</span></span> <span data-ttu-id="ba492-225">Das gehostete Steuerelement, die umgebenden Elemente und die Schriftart des gehosteten Steuerelements werden durch den Faktor 0,5 skaliert.</span><span class="sxs-lookup"><span data-stu-id="ba492-225">The hosted control, its surrounding elements, and the hosted control's font are scaled by a factor of 0.5.</span></span>  
  
## <a name="rotating"></a><span data-ttu-id="ba492-226">Drehen</span><span class="sxs-lookup"><span data-stu-id="ba492-226">Rotating</span></span>  
 <span data-ttu-id="ba492-227">Im Gegensatz zu [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Elemente [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente unterstützen nicht die Drehung.</span><span class="sxs-lookup"><span data-stu-id="ba492-227">Unlike [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elements, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls do not support rotation.</span></span> <span data-ttu-id="ba492-228">Wird standardmäßig die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element dreht sich nicht mit anderen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Elemente angezeigt, wenn eine Drehtransformation angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="ba492-228">By default, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element does not rotate with other [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elements when a rotation transformation is applied.</span></span> <span data-ttu-id="ba492-229">Jeder andere Drehungswert als 180 Grad löst die <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="ba492-229">Any rotation value other than 180 degrees raises the <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> event.</span></span>  <span data-ttu-id="ba492-230">Legen Sie zum Aktivieren, um einen beliebigen Winkel drehen der <xref:System.Windows.Interop.HwndHost.IsRedirected%2A> Eigenschaft von der <xref:System.Windows.Forms.Integration.WindowsFormsHost> auf "true" und die <xref:System.Windows.Interop.HwndHost.CompositionMode%2A> Eigenschaft <xref:System.Windows.Interop.CompositionMode.Full> oder <xref:System.Windows.Interop.CompositionMode.OutputOnly>.</span><span class="sxs-lookup"><span data-stu-id="ba492-230">To enable rotating to any angle, set the <xref:System.Windows.Interop.HwndHost.IsRedirected%2A> property of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> to true and the <xref:System.Windows.Interop.HwndHost.CompositionMode%2A> property to <xref:System.Windows.Interop.CompositionMode.Full> or <xref:System.Windows.Interop.CompositionMode.OutputOnly>.</span></span>  
  
#### <a name="to-see-the-effect-of-rotation-in-a-hybrid-application"></a><span data-ttu-id="ba492-231">Anzeigen der Auswirkung der Drehung in einer Hybridanwendung</span><span class="sxs-lookup"><span data-stu-id="ba492-231">To see the effect of rotation in a hybrid application</span></span>  
  
1.  <span data-ttu-id="ba492-232">Kopieren Sie den folgenden XAML-Code in die <xref:System.Windows.Controls.Grid> Element.</span><span class="sxs-lookup"><span data-stu-id="ba492-232">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]  
  
2.  <span data-ttu-id="ba492-233">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ba492-233">Press F5 to build and run the application.</span></span> <span data-ttu-id="ba492-234">Das gehostete Steuerelement wird nicht gedreht, die umgebenden Elemente werden jedoch um einen Winkel von 180 Grad gedreht.</span><span class="sxs-lookup"><span data-stu-id="ba492-234">The hosted control is not rotated, but its surrounding elements are rotated by an angle of 180 degrees.</span></span> <span data-ttu-id="ba492-235">Sie müssen möglicherweise die Fenstergröße anpassen, um die Elemente zu sehen.</span><span class="sxs-lookup"><span data-stu-id="ba492-235">You may have to resize the window to see the elements.</span></span>  
  
#### <a name="to-see-the-effect-of-rotation-in-a-hybrid-application-when-isredirected-is-true"></a><span data-ttu-id="ba492-236">Anzeigen der Auswirkung der Drehung in einer Hybridanwendung, wenn IsRedirected auf true festgelegt ist</span><span class="sxs-lookup"><span data-stu-id="ba492-236">To see the effect of rotation in a hybrid application when IsRedirected is true</span></span>  
  
1.  <span data-ttu-id="ba492-237">Ersetzen das vorherige Beispiel für die Drehung durch das folgende XAML.</span><span class="sxs-lookup"><span data-stu-id="ba492-237">Replace the previous rotation example with the following XAML.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#13b](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml#13b)]  
  
2.  <span data-ttu-id="ba492-238">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ba492-238">Press F5 to build and run the application.</span></span> <span data-ttu-id="ba492-239">Das gehostete Steuerelement wird gedreht.</span><span class="sxs-lookup"><span data-stu-id="ba492-239">The hosted control is rotated.</span></span>  <span data-ttu-id="ba492-240">Beachten Sie, dass die <xref:System.Windows.Media.RotateTransform.Angle%2A> Eigenschaft kann auf einen beliebigen Wert festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="ba492-240">Note that the <xref:System.Windows.Media.RotateTransform.Angle%2A> property can be set to any value.</span></span> <span data-ttu-id="ba492-241">Sie müssen möglicherweise die Fenstergröße anpassen, um die Elemente zu sehen.</span><span class="sxs-lookup"><span data-stu-id="ba492-241">You may have to resize the window to see the elements.</span></span>  
  
## <a name="setting-padding-and-margins"></a><span data-ttu-id="ba492-242">Einstellen von Abständen und Rändern</span><span class="sxs-lookup"><span data-stu-id="ba492-242">Setting Padding and Margins</span></span>  
 <span data-ttu-id="ba492-243">Auffüllung und Rändern in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layout ähneln Auffüllung und Rändern in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ba492-243">Padding and margins in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout are similar to padding and margins in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="ba492-244">Legen Sie einfach die <xref:System.Windows.Controls.Control.Padding%2A> und <xref:System.Windows.FrameworkElement.Margin%2A> Eigenschaften auf der <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element.</span><span class="sxs-lookup"><span data-stu-id="ba492-244">Simply set the <xref:System.Windows.Controls.Control.Padding%2A> and <xref:System.Windows.FrameworkElement.Margin%2A> properties on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>  
  
#### <a name="to-set-padding-and-margins-for-a-hosted-control"></a><span data-ttu-id="ba492-245">Festlegen von Abstand und Rändern für ein gehostetes Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ba492-245">To set padding and margins for a hosted control</span></span>  
  
1.  <span data-ttu-id="ba492-246">Kopieren Sie den folgenden XAML-Code in die <xref:System.Windows.Controls.Grid> Element.</span><span class="sxs-lookup"><span data-stu-id="ba492-246">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]  
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]  
  
2.  <span data-ttu-id="ba492-247">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ba492-247">Press F5 to build and run the application.</span></span> <span data-ttu-id="ba492-248">Die Ränder und Abstände Einstellungen angewendet, das vom gehosteten [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente auf die gleiche Weise, die sie werden, in angewendet würden [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ba492-248">The padding and margin settings are applied to the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in the same way they would be applied in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span>  
  
## <a name="using-dynamic-layout-containers"></a><span data-ttu-id="ba492-249">Verwenden von dynamischen Layoutcontainern</span><span class="sxs-lookup"><span data-stu-id="ba492-249">Using Dynamic Layout Containers</span></span>  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<span data-ttu-id="ba492-250">stellt zwei dynamische Layoutcontainer <xref:System.Windows.Forms.FlowLayoutPanel> und <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="ba492-250"> provides two dynamic layout containers, <xref:System.Windows.Forms.FlowLayoutPanel> and <xref:System.Windows.Forms.TableLayoutPanel>.</span></span> <span data-ttu-id="ba492-251">Sie können auch diese Container in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layouts.</span><span class="sxs-lookup"><span data-stu-id="ba492-251">You can also use these containers in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layouts.</span></span>  
  
#### <a name="to-use-a-dynamic-layout-container"></a><span data-ttu-id="ba492-252">Verwenden von dynamischen Layoutcontainern</span><span class="sxs-lookup"><span data-stu-id="ba492-252">To use a dynamic layout container</span></span>  
  
1.  <span data-ttu-id="ba492-253">Kopieren Sie den folgenden XAML-Code in die <xref:System.Windows.Controls.Grid> Element.</span><span class="sxs-lookup"><span data-stu-id="ba492-253">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]  
  
2.  <span data-ttu-id="ba492-254">Kopieren Sie in „MainWindow.xaml.vb“ oder „MainWindow.xaml.cs“ den folgenden Code in die Klassedefinition.</span><span class="sxs-lookup"><span data-stu-id="ba492-254">In MainWindow.xaml.vb or MainWindow.xaml.cs copy the following code into the class definition.</span></span>  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]  
  
3.  <span data-ttu-id="ba492-255">Fügen Sie einen Aufruf an die `InitializeFlowLayoutPanel` -Methode im Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="ba492-255">Add a call to the `InitializeFlowLayoutPanel` method in the constructor.</span></span>  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]  
  
4.  <span data-ttu-id="ba492-256">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ba492-256">Press F5 to build and run the application.</span></span> <span data-ttu-id="ba492-257">Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element füllt die <xref:System.Windows.Controls.DockPanel>, und <xref:System.Windows.Forms.FlowLayoutPanel> ordnet seine untergeordneten Steuerelemente in der standardmäßigen <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span><span class="sxs-lookup"><span data-stu-id="ba492-257">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element fills the <xref:System.Windows.Controls.DockPanel>, and <xref:System.Windows.Forms.FlowLayoutPanel> arranges its child controls in the default <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba492-258">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba492-258">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="ba492-259">WPF-Designer</span><span class="sxs-lookup"><span data-stu-id="ba492-259">WPF Designer</span></span>](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)  
 [<span data-ttu-id="ba492-260">Überlegungen zum Layout für das WindowsFormsHost-Element</span><span class="sxs-lookup"><span data-stu-id="ba492-260">Layout Considerations for the WindowsFormsHost Element</span></span>](../../../../docs/framework/wpf/advanced/layout-considerations-for-the-windowsformshost-element.md)  
 [<span data-ttu-id="ba492-261">Anordnen von Windows Forms-Steuerelementen in WPF-Beispiel</span><span class="sxs-lookup"><span data-stu-id="ba492-261">Arranging Windows Forms Controls in WPF Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=159971)  
 [<span data-ttu-id="ba492-262">Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF</span><span class="sxs-lookup"><span data-stu-id="ba492-262">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [<span data-ttu-id="ba492-263">Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ba492-263">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
