---
title: 'Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen in WPF'
ms.custom: ''
ms.date: 04/03/2018
ms.prod: .net-framework
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- arranging controls [WPF]
ms.assetid: a1db8049-15c7-45d6-ae3d-36a6735cb848
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4f3129b4128444530b1277299f3f95ce49232421
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2018
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a><span data-ttu-id="5f3bc-102">Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen in WPF</span><span class="sxs-lookup"><span data-stu-id="5f3bc-102">Walkthrough: Arranging Windows Forms Controls in WPF</span></span>
<span data-ttu-id="5f3bc-103">In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Sie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layoutfunktionen anordnen [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente in einer hybridanwendung.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-103">This walkthrough shows you how to use [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout features to arrange [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in a hybrid application.</span></span>  
  
 <span data-ttu-id="5f3bc-104">In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="5f3bc-104">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="5f3bc-105">Erstellen des Projekts.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-105">Creating the project.</span></span>  
  
-   <span data-ttu-id="5f3bc-106">Verwenden der Standardlayouteinstellungen.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-106">Using default layout settings.</span></span>  
  
-   <span data-ttu-id="5f3bc-107">Anpassen der Größe an Inhalt.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-107">Sizing to content.</span></span>  
  
-   <span data-ttu-id="5f3bc-108">Verwenden der absoluten Positionierung.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-108">Using absolute positioning.</span></span>  
  
-   <span data-ttu-id="5f3bc-109">Explizites Angeben der Größe.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-109">Specifying size explicitly.</span></span>  
  
-   <span data-ttu-id="5f3bc-110">Festlegen der Layouteigenschaften.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-110">Setting layout properties.</span></span>  
  
-   <span data-ttu-id="5f3bc-111">Grundlegendes zu Einschränkungen der Z-Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-111">Understanding z-order limitations.</span></span>  
  
-   <span data-ttu-id="5f3bc-112">Andocken.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-112">Docking.</span></span>  
  
-   <span data-ttu-id="5f3bc-113">Einstellen der Sichtbarkeit.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-113">Setting visibility.</span></span>  
  
-   <span data-ttu-id="5f3bc-114">Hosten eines Steuerelements, das nicht gestreckt wird.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-114">Hosting a control that does not stretch.</span></span>  
  
-   <span data-ttu-id="5f3bc-115">Skalieren.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-115">Scaling.</span></span>  
  
-   <span data-ttu-id="5f3bc-116">Drehen.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-116">Rotating.</span></span>  
  
-   <span data-ttu-id="5f3bc-117">Einstellen von Abständen und Rändern.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-117">Setting padding and margins.</span></span>  
  
-   <span data-ttu-id="5f3bc-118">Verwenden von dynamischen Layoutcontainern.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-118">Using dynamic layout containers.</span></span>  
  
 <span data-ttu-id="5f3bc-119">Vollständige Codeliste der Aufgaben in dieser exemplarischen Vorgehensweise veranschaulicht, finden Sie unter [Anordnen von Windows Forms-Steuerelementen im WPF-Beispiel](http://go.microsoft.com/fwlink/?LinkID=159971).</span><span class="sxs-lookup"><span data-stu-id="5f3bc-119">For a complete code listing of the tasks illustrated in this walkthrough, see [Arranging Windows Forms Controls in WPF Sample](http://go.microsoft.com/fwlink/?LinkID=159971).</span></span>  
  
 <span data-ttu-id="5f3bc-120">Wenn Sie fertig sind, müssen Sie einen Überblick über [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Layout-Funktionen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-basierten Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-120">When you are finished, you will have an understanding of [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] layout features in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based applications.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5f3bc-121">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="5f3bc-121">Prerequisites</span></span>  
 <span data-ttu-id="5f3bc-122">Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="5f3bc-122">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]<span data-ttu-id="5f3bc-123">.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-123">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="5f3bc-124">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="5f3bc-124">Creating the Project</span></span>  
  
#### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="5f3bc-125">So erstellen und richten Sie das Projekt ein</span><span class="sxs-lookup"><span data-stu-id="5f3bc-125">To create and set up the project</span></span>  
  
1.  <span data-ttu-id="5f3bc-126">Erstellen Sie ein WPF-Anwendungsprojekt mit dem Namen `WpfLayoutHostingWf`.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-126">Create a WPF Application project named `WpfLayoutHostingWf`.</span></span>  
  
2.  <span data-ttu-id="5f3bc-127">Fügen Sie im Projektmappen-Explorer Verweise auf die folgenden Assemblys hinzu.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-127">In Solution Explorer, add references to the following assemblies.</span></span>  
  
    -   <span data-ttu-id="5f3bc-128">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="5f3bc-128">WindowsFormsIntegration</span></span>  
  
    -   <span data-ttu-id="5f3bc-129">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="5f3bc-129">System.Windows.Forms</span></span>  
  
    -   <span data-ttu-id="5f3bc-130">System.Drawing</span><span class="sxs-lookup"><span data-stu-id="5f3bc-130">System.Drawing</span></span>  
  
3.  <span data-ttu-id="5f3bc-131">Doppelklicken Sie auf „MainWindow.xaml“, um die Datei in der XAML-Ansicht zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-131">Double-click MainWindow.xaml to open it in XAML view.</span></span>  
  
4.  <span data-ttu-id="5f3bc-132">In der <xref:System.Windows.Window> Element, fügen Sie die folgenden [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Namespacezuordnung.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-132">In the <xref:System.Windows.Window> element, add the following [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] namespace mapping.</span></span>  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  <span data-ttu-id="5f3bc-133">In der <xref:System.Windows.Controls.Grid> Elementsatz die <xref:System.Windows.Controls.Grid.ShowGridLines%2A> Eigenschaft `true` fünf Zeilen und drei Spalten definieren.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-133">In the <xref:System.Windows.Controls.Grid> element set the <xref:System.Windows.Controls.Grid.ShowGridLines%2A> property to `true` and define five rows and three columns.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]  
  
## <a name="using-default-layout-settings"></a><span data-ttu-id="5f3bc-134">Verwenden der Standardlayouteinstellungen</span><span class="sxs-lookup"><span data-stu-id="5f3bc-134">Using Default Layout Settings</span></span>  
 <span data-ttu-id="5f3bc-135">Wird standardmäßig die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element behandelt das Layout für das gehostete [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-135">By default, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element handles the layout for the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>  
  
#### <a name="to-use-default-layout-settings"></a><span data-ttu-id="5f3bc-136">Verwenden der Standardlayouteinstellungen</span><span class="sxs-lookup"><span data-stu-id="5f3bc-136">To use default layout settings</span></span>  
  
1.  <span data-ttu-id="5f3bc-137">Kopieren Sie den folgenden XAML-Code in die <xref:System.Windows.Controls.Grid> Element.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-137">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]  
  
2.  <span data-ttu-id="5f3bc-138">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-138">Press F5 to build and run the application.</span></span> <span data-ttu-id="5f3bc-139">Die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Button?displayProperty=nameWithType> Steuerelement wird in der <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-139">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Button?displayProperty=nameWithType> control appears in the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="5f3bc-140">Das gehostete Steuerelement wird basierend auf seinen Inhalt angepasst und der <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element wird angepasst, um das gehostete Steuerelement aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-140">The hosted control is sized based on its content, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is sized to accommodate the hosted control.</span></span>  
  
## <a name="sizing-to-content"></a><span data-ttu-id="5f3bc-141">Anpassen der Größe an Inhalt</span><span class="sxs-lookup"><span data-stu-id="5f3bc-141">Sizing to Content</span></span>  
 <span data-ttu-id="5f3bc-142">Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Elements sicher, dass das gehostete Steuerelement festgelegt wird, um seinen Inhalt ordnungsgemäß angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-142">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element ensures that the hosted control is sized to display its content properly.</span></span>  
  
#### <a name="to-size-to-content"></a><span data-ttu-id="5f3bc-143">Anpassen der Größe an Inhalt</span><span class="sxs-lookup"><span data-stu-id="5f3bc-143">To size to content</span></span>  
  
1.  <span data-ttu-id="5f3bc-144">Kopieren Sie den folgenden XAML-Code in die <xref:System.Windows.Controls.Grid> Element.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-144">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]  
  
2.  <span data-ttu-id="5f3bc-145">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-145">Press F5 to build and run the application.</span></span> <span data-ttu-id="5f3bc-146">Die zwei neue Schaltflächen-Steuerelemente sind Größe angepasst, um die Textzeichenfolge länger und größere Schriftgröße ordnungsgemäß angezeigt werden und die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Elemente werden geändert, um die gehosteten Steuerelemente angepasst.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-146">The two new button controls are sized to display the longer text string and larger font size properly, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are resized to accommodate the hosted controls.</span></span>  
  
## <a name="using-absolute-positioning"></a><span data-ttu-id="5f3bc-147">Verwenden der absoluten Positionierung</span><span class="sxs-lookup"><span data-stu-id="5f3bc-147">Using Absolute Positioning</span></span>  
 <span data-ttu-id="5f3bc-148">Sie können absolute Positionierung Platzieren der <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element an einer beliebigen Stelle in der Benutzeroberfläche (UI).</span><span class="sxs-lookup"><span data-stu-id="5f3bc-148">You can use absolute positioning to place the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element anywhere in the user interface (UI).</span></span>  
  
#### <a name="to-use-absolute-positioning"></a><span data-ttu-id="5f3bc-149">Verwenden der absoluten Positionierung</span><span class="sxs-lookup"><span data-stu-id="5f3bc-149">To use absolute positioning</span></span>  
  
1.  <span data-ttu-id="5f3bc-150">Kopieren Sie den folgenden XAML-Code in die <xref:System.Windows.Controls.Grid> Element.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-150">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]  
  
2.  <span data-ttu-id="5f3bc-151">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-151">Press F5 to build and run the application.</span></span> <span data-ttu-id="5f3bc-152">Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> 20 Pixel vom oberen Rand der Rasterzelle und 20 Pixel vom linken Element befindet.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-152">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is placed 20 pixels from the top side of the grid cell and 20 pixels from the left.</span></span>  
  
## <a name="specifying-size-explicitly"></a><span data-ttu-id="5f3bc-153">Explizites Angeben der Größe</span><span class="sxs-lookup"><span data-stu-id="5f3bc-153">Specifying Size Explicitly</span></span>  
 <span data-ttu-id="5f3bc-154">Sie können die Größe der angeben der <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element mit der <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-154">You can specify the size of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element using the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span>  
  
#### <a name="to-specify-size-explicitly"></a><span data-ttu-id="5f3bc-155">Explizites Angeben der Größe</span><span class="sxs-lookup"><span data-stu-id="5f3bc-155">To specify size explicitly</span></span>  
  
1.  <span data-ttu-id="5f3bc-156">Kopieren Sie den folgenden XAML-Code in die <xref:System.Windows.Controls.Grid> Element.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-156">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]  
  
2.  <span data-ttu-id="5f3bc-157">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-157">Press F5 to build and run the application.</span></span> <span data-ttu-id="5f3bc-158">Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element festgelegt, wird er auf eine Größe von 50 Pixel breit und 70 Pixel hoch, die kleiner als die Standardeinstellungen für das Layout.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-158">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is set to a size of 50 pixels wide by 70 pixels high, which is smaller than the default layout settings.</span></span> <span data-ttu-id="5f3bc-159">Der Inhalt der [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement wird entsprechend neu angeordnet.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-159">The content of the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is rearranged accordingly.</span></span>  
  
## <a name="setting-layout-properties"></a><span data-ttu-id="5f3bc-160">Festlegen der Layouteigenschaften</span><span class="sxs-lookup"><span data-stu-id="5f3bc-160">Setting Layout Properties</span></span>  
 <span data-ttu-id="5f3bc-161">Layout-bezogene Eigenschaften immer im gehosteten Steuerelement festgelegt, wird mit den Eigenschaften des der <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-161">Always set layout-related properties on the hosted control by using the properties of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="5f3bc-162">Das Festlegen der Layouteigenschaften direkt für das gehostete Steuerelement führt zu unbeabsichtigten Ergebnissen.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-162">Setting layout properties directly on the hosted control will yield unintended results.</span></span>  
  
 <span data-ttu-id="5f3bc-163">Festlegen von layoutbezogenen Eigenschaften für das gehostete Steuerelement im [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] hat keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-163">Setting layout-related properties on the hosted control in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] has no effect.</span></span>  
  
#### <a name="to-see-the-effects-of-setting-properties-on-the-hosted-control"></a><span data-ttu-id="5f3bc-164">Anzeigen der Auswirkungen des Festlegens der Eigenschaften für das gehostete Steuerelement</span><span class="sxs-lookup"><span data-stu-id="5f3bc-164">To see the effects of setting properties on the hosted control</span></span>  
  
1.  <span data-ttu-id="5f3bc-165">Kopieren Sie den folgenden XAML-Code in die <xref:System.Windows.Controls.Grid> Element.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-165">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]  
  
2.  <span data-ttu-id="5f3bc-166">Doppelklicken Sie in Projektmappen-Explorer „MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-166">In Solution Explorer, double-click MainWindow.xaml.</span></span> <span data-ttu-id="5f3bc-167">vb“ oder „MainWindow.Xaml.cs“, um die Datei im Code-Editor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-167">vb or MainWindow.xaml.cs to open it in the Code Editor.</span></span>  
  
3.  <span data-ttu-id="5f3bc-168">Kopieren Sie den folgenden Code in die `MainWindow` Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-168">Copy the following code into the `MainWindow` class definition.</span></span>  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]  
  
4.  <span data-ttu-id="5f3bc-169">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-169">Press F5 to build and run the application.</span></span>  
  
5.  <span data-ttu-id="5f3bc-170">Klicken Sie auf die **Click me** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-170">Click the **Click me** button.</span></span> <span data-ttu-id="5f3bc-171">Die `button1_Click` Ereignishandler legt die <xref:System.Windows.Forms.Control.Top%2A> und <xref:System.Windows.Forms.Control.Left%2A> Eigenschaften im gehosteten Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-171">The `button1_Click` event handler sets the <xref:System.Windows.Forms.Control.Top%2A> and <xref:System.Windows.Forms.Control.Left%2A> properties on the hosted control.</span></span> <span data-ttu-id="5f3bc-172">Dies bewirkt, dass das gehostete Steuerelement innerhalb neu angeordnet werden die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-172">This causes the hosted control to be repositioned within the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="5f3bc-173">Der Host behält den gleichen Bildschirmbereich bei, jedoch wird das gehostete Steuerelement abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-173">The host maintains the same screen area, but the hosted control is clipped.</span></span> <span data-ttu-id="5f3bc-174">Das gehostete Steuerelement sollte jedoch immer ausfüllen der <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-174">Instead, the hosted control should always fill the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>  
  
## <a name="understanding-z-order-limitations"></a><span data-ttu-id="5f3bc-175">Grundlegendes zu Einschränkungen der Z-Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="5f3bc-175">Understanding Z-Order Limitations</span></span>  
 <span data-ttu-id="5f3bc-176">Sichtbare <xref:System.Windows.Forms.Integration.WindowsFormsHost> Elemente werden immer auf andere Elemente der WPF-gezeichnet, und sie sind nicht betroffen von Z-Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-176">Visible <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are always drawn on top of other WPF elements, and they are unaffected by z-order.</span></span> <span data-ttu-id="5f3bc-177">Um dieses Verhalten Z-Reihenfolge anzuzeigen, führen Sie folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="5f3bc-177">To see this z-order behavior, do the following:</span></span>

1.  <span data-ttu-id="5f3bc-178">Kopieren Sie den folgenden XAML-Code in die <xref:System.Windows.Controls.Grid> Element.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-178">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]  
 
2.  <span data-ttu-id="5f3bc-179">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-179">Press F5 to build and run the application.</span></span> <span data-ttu-id="5f3bc-180">Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element über das Label-Element gezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-180">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is painted over the label element.</span></span>  


## <a name="docking"></a><span data-ttu-id="5f3bc-181">Andocken</span><span class="sxs-lookup"><span data-stu-id="5f3bc-181">Docking</span></span>  
 <span data-ttu-id="5f3bc-182"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Element unterstützt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] andocken.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-182"><xref:System.Windows.Forms.Integration.WindowsFormsHost> element supports [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] docking.</span></span> <span data-ttu-id="5f3bc-183">Legen Sie die <xref:System.Windows.Controls.DockPanel.Dock%2A> angefügte Eigenschaft, um das gehostete Steuerelement im Andocken ein <xref:System.Windows.Controls.DockPanel> Element.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-183">Set the <xref:System.Windows.Controls.DockPanel.Dock%2A> attached property to dock the hosted control in a <xref:System.Windows.Controls.DockPanel> element.</span></span>  
  
#### <a name="to-dock-a-hosted-control"></a><span data-ttu-id="5f3bc-184">Andocke eines gehosteten Steuerelements</span><span class="sxs-lookup"><span data-stu-id="5f3bc-184">To dock a hosted control</span></span>  
  
1.  <span data-ttu-id="5f3bc-185">Kopieren Sie den folgenden XAML-Code in die <xref:System.Windows.Controls.Grid> Element.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-185">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]  
  
2.  <span data-ttu-id="5f3bc-186">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-186">Press F5 to build and run the application.</span></span> <span data-ttu-id="5f3bc-187">Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element auf der rechten Seite des angedockt ist die <xref:System.Windows.Controls.DockPanel> Element.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-187">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is docked to the right side of the <xref:System.Windows.Controls.DockPanel> element.</span></span>  
  
## <a name="setting-visibility"></a><span data-ttu-id="5f3bc-188">Einstellen der Sichtbarkeit</span><span class="sxs-lookup"><span data-stu-id="5f3bc-188">Setting Visibility</span></span>  
 <span data-ttu-id="5f3bc-189">Sie vornehmen können Ihre [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] unsichtbar zu steuern oder zu reduzieren, indem Sie festlegen der <xref:System.Windows.UIElement.Visibility%2A> Eigenschaft auf die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-189">You can make your [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control invisible or collapse it by setting the <xref:System.Windows.UIElement.Visibility%2A> property on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="5f3bc-190">Wenn ein Steuerelement unsichtbar ist, wird es nicht angezeigt, es belegt jedoch Platz im Layoutbereich.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-190">When a control is invisible, it is not displayed, but it occupies layout space.</span></span> <span data-ttu-id="5f3bc-191">Wenn ein Steuerelement reduziert ist, wird es nicht angezeigt, und es belegt auch keinen Platz im Layoutbereich.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-191">When a control is collapsed, it is not displayed, nor does it occupy layout space.</span></span>  
  
#### <a name="to-set-the-visibility-of-a-hosted-control"></a><span data-ttu-id="5f3bc-192">Festlegen der Sichtbarkeit eines gehosteten Steuerelements</span><span class="sxs-lookup"><span data-stu-id="5f3bc-192">To set the visibility of a hosted control</span></span>  
  
1.  <span data-ttu-id="5f3bc-193">Kopieren Sie den folgenden XAML-Code in die <xref:System.Windows.Controls.Grid> Element.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-193">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]  
  
2.  <span data-ttu-id="5f3bc-194">Kopieren Sie in „MainWindow.xaml.vb“ oder „MainWindow.xaml.cs“ den folgenden Code in die Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-194">In MainWindow.xaml.vb or MainWindow.xaml.cs, copy the following code into the class definition.</span></span>  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]  
  
3.  <span data-ttu-id="5f3bc-195">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-195">Press F5 to build and run the application.</span></span>  
  
4.  <span data-ttu-id="5f3bc-196">Klicken Sie auf die **klicken Sie hier, um unsichtbar zu machen** Schaltfläche stellen die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-196">Click the **Click to make invisible** button to make the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element invisible.</span></span>  
  
5.  <span data-ttu-id="5f3bc-197">Klicken Sie auf die **zum Reduzieren** Schaltfläche Ausblenden der <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element aus dem Layout vollständig.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-197">Click the **Click to collapse** button to hide the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element from the layout entirely.</span></span> <span data-ttu-id="5f3bc-198">Wenn die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement reduziert ist, werden die umgebenden Elemente neu angeordnet, um seine Platz einnehmen.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-198">When the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is collapsed, the surrounding elements are rearranged to occupy its space.</span></span>  
  
## <a name="hosting-a-control-that-does-not-stretch"></a><span data-ttu-id="5f3bc-199">Hosten eines Steuerelements, das nicht gestreckt wird</span><span class="sxs-lookup"><span data-stu-id="5f3bc-199">Hosting a Control That Does Not Stretch</span></span>  
 <span data-ttu-id="5f3bc-200">Einige [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente verfügen über eine feste Größe und können nicht gestreckt werden, um das Layout verfügbaren Platz auszufüllen.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-200">Some [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have a fixed size and do not stretch to fill available space in the layout.</span></span> <span data-ttu-id="5f3bc-201">Z. B. die <xref:System.Windows.Forms.MonthCalendar> Steuerelement ein Monats in einem festen Bereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-201">For example, the <xref:System.Windows.Forms.MonthCalendar> control displays a month in a fixed space.</span></span>  
  
#### <a name="to-host-a-control-that-does-not-stretch"></a><span data-ttu-id="5f3bc-202">Hosten eines Steuerelements, das nicht gestreckt wird</span><span class="sxs-lookup"><span data-stu-id="5f3bc-202">To host a control that does not stretch</span></span>  
  
1.  <span data-ttu-id="5f3bc-203">Kopieren Sie den folgenden XAML-Code in die <xref:System.Windows.Controls.Grid> Element.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-203">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]  
  
2.  <span data-ttu-id="5f3bc-204">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-204">Press F5 to build and run the application.</span></span> <span data-ttu-id="5f3bc-205">Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element wird in der Rasterzeile zentriert, aber es ist nicht gestreckt, um den verfügbaren Platz auszufüllen.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-205">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is centered in the grid row, but it is not stretched to fill the available space.</span></span> <span data-ttu-id="5f3bc-206">Wenn das Fenster groß genug ist, werden möglicherweise zwei oder mehr Monate angezeigt, die von der gehosteten <xref:System.Windows.Forms.MonthCalendar> -Steuerelement, doch diese sind in der Zeile zentriert.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-206">If the window is large enough, you may see two or more months displayed by the hosted <xref:System.Windows.Forms.MonthCalendar> control, but these are centered in the row.</span></span> <span data-ttu-id="5f3bc-207">Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layoutmodul zentriert Elemente, deren Größe geändert werden können nicht um den verfügbaren Platz auszufüllen.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-207">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout engine centers elements that cannot be sized to fill the available space.</span></span>  
  
## <a name="scaling"></a><span data-ttu-id="5f3bc-208">Skalieren</span><span class="sxs-lookup"><span data-stu-id="5f3bc-208">Scaling</span></span>  
 <span data-ttu-id="5f3bc-209">Im Gegensatz zu WPF-Elemente sind die meisten Windows Forms-Steuerelemente nicht kontinuierlich skalierbar.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-209">Unlike WPF elements, most Windows Forms controls are not continuously scalable.</span></span> <span data-ttu-id="5f3bc-210">Um benutzerdefinierte Skalierung bereitzustellen, überschreiben Sie die <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-210">To provide custom scaling, you override the <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> method.</span></span> 
  
#### <a name="to-scale-a-hosted-control-by-using-the-default-behavior"></a><span data-ttu-id="5f3bc-211">Skalieren eines gehosteten Steuerelements mithilfe des Standardverhaltens</span><span class="sxs-lookup"><span data-stu-id="5f3bc-211">To scale a hosted control by using the default behavior</span></span>  
  
1.  <span data-ttu-id="5f3bc-212">Kopieren Sie den folgenden XAML-Code in die <xref:System.Windows.Controls.Grid> Element.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-212">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]  
  
2.  <span data-ttu-id="5f3bc-213">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-213">Press F5 to build and run the application.</span></span> <span data-ttu-id="5f3bc-214">Das gehostete Steuerelement und die umgebenden Elemente werden um den Faktor 0,5 skaliert.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-214">The hosted control and its surrounding elements are scaled by a factor of 0.5.</span></span> <span data-ttu-id="5f3bc-215">Allerdings wird die Schriftart des gehosteten Steuerelements nicht skaliert.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-215">However, the hosted control's font is not scaled.</span></span>

<!-- This could use an example of custom scaling. -->

## <a name="rotating"></a><span data-ttu-id="5f3bc-216">Drehen</span><span class="sxs-lookup"><span data-stu-id="5f3bc-216">Rotating</span></span>  
 <span data-ttu-id="5f3bc-217">Im Gegensatz zu WPF-Elemente unterstützt nicht Drehung Windows Forms-Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-217">Unlike WPF elements, Windows Forms controls do not support rotation.</span></span> <span data-ttu-id="5f3bc-218">Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element wird nicht mit anderen Elementen WPF gedreht, wenn eine Drehtransformation angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-218">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element does not rotate with other WPF elements when a rotation transformation is applied.</span></span> <span data-ttu-id="5f3bc-219">Jeder andere Drehungswert als 180 Grad löst die <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-219">Any rotation value other than 180 degrees raises the <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> event.</span></span>
 
#### <a name="to-see-the-effect-of-rotation-in-a-hybrid-application"></a><span data-ttu-id="5f3bc-220">Anzeigen der Auswirkung der Drehung in einer Hybridanwendung</span><span class="sxs-lookup"><span data-stu-id="5f3bc-220">To see the effect of rotation in a hybrid application</span></span>  
  
1.  <span data-ttu-id="5f3bc-221">Kopieren Sie den folgenden XAML-Code in die <xref:System.Windows.Controls.Grid> Element.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-221">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]  
  
2.  <span data-ttu-id="5f3bc-222">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-222">Press F5 to build and run the application.</span></span> <span data-ttu-id="5f3bc-223">Das gehostete Steuerelement wird nicht gedreht, die umgebenden Elemente werden jedoch um einen Winkel von 180 Grad gedreht.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-223">The hosted control is not rotated, but its surrounding elements are rotated by an angle of 180 degrees.</span></span> <span data-ttu-id="5f3bc-224">Sie müssen möglicherweise die Fenstergröße anpassen, um die Elemente zu sehen.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-224">You may have to resize the window to see the elements.</span></span>  
 

## <a name="setting-padding-and-margins"></a><span data-ttu-id="5f3bc-225">Einstellen von Abständen und Rändern</span><span class="sxs-lookup"><span data-stu-id="5f3bc-225">Setting Padding and Margins</span></span>  
 <span data-ttu-id="5f3bc-226">Auffüllung und Rändern in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layout ähneln Auffüllung und Rändern in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5f3bc-226">Padding and margins in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout are similar to padding and margins in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="5f3bc-227">Legen Sie einfach die <xref:System.Windows.Controls.Control.Padding%2A> und <xref:System.Windows.FrameworkElement.Margin%2A> Eigenschaften auf der <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-227">Simply set the <xref:System.Windows.Controls.Control.Padding%2A> and <xref:System.Windows.FrameworkElement.Margin%2A> properties on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>  
  
#### <a name="to-set-padding-and-margins-for-a-hosted-control"></a><span data-ttu-id="5f3bc-228">Festlegen von Abstand und Rändern für ein gehostetes Steuerelement</span><span class="sxs-lookup"><span data-stu-id="5f3bc-228">To set padding and margins for a hosted control</span></span>  
  
1.  <span data-ttu-id="5f3bc-229">Kopieren Sie den folgenden XAML-Code in die <xref:System.Windows.Controls.Grid> Element.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-229">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]  
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]  
  
2.  <span data-ttu-id="5f3bc-230">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-230">Press F5 to build and run the application.</span></span> <span data-ttu-id="5f3bc-231">Die Ränder und Abstände Einstellungen angewendet, das vom gehosteten [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente auf die gleiche Weise, die sie werden, in angewendet würden [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5f3bc-231">The padding and margin settings are applied to the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in the same way they would be applied in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span>  
  
## <a name="using-dynamic-layout-containers"></a><span data-ttu-id="5f3bc-232">Verwenden von dynamischen Layoutcontainern</span><span class="sxs-lookup"><span data-stu-id="5f3bc-232">Using Dynamic Layout Containers</span></span>  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<span data-ttu-id="5f3bc-233"> stellt zwei dynamische Layoutcontainer <xref:System.Windows.Forms.FlowLayoutPanel> und <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-233"> provides two dynamic layout containers, <xref:System.Windows.Forms.FlowLayoutPanel> and <xref:System.Windows.Forms.TableLayoutPanel>.</span></span> <span data-ttu-id="5f3bc-234">Sie können auch diese Container in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layouts.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-234">You can also use these containers in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layouts.</span></span>  
  
#### <a name="to-use-a-dynamic-layout-container"></a><span data-ttu-id="5f3bc-235">Verwenden von dynamischen Layoutcontainern</span><span class="sxs-lookup"><span data-stu-id="5f3bc-235">To use a dynamic layout container</span></span>  
  
1.  <span data-ttu-id="5f3bc-236">Kopieren Sie den folgenden XAML-Code in die <xref:System.Windows.Controls.Grid> Element.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-236">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]  
  
2.  <span data-ttu-id="5f3bc-237">Kopieren Sie in „MainWindow.xaml.vb“ oder „MainWindow.xaml.cs“ den folgenden Code in die Klassedefinition.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-237">In MainWindow.xaml.vb or MainWindow.xaml.cs copy the following code into the class definition.</span></span>  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]  
  
3.  <span data-ttu-id="5f3bc-238">Fügen Sie einen Aufruf an die `InitializeFlowLayoutPanel` -Methode im Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-238">Add a call to the `InitializeFlowLayoutPanel` method in the constructor.</span></span>  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]  
  
4.  <span data-ttu-id="5f3bc-239">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-239">Press F5 to build and run the application.</span></span> <span data-ttu-id="5f3bc-240">Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element füllt die <xref:System.Windows.Controls.DockPanel>, und <xref:System.Windows.Forms.FlowLayoutPanel> ordnet seine untergeordneten Steuerelemente in der standardmäßigen <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span><span class="sxs-lookup"><span data-stu-id="5f3bc-240">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element fills the <xref:System.Windows.Controls.DockPanel>, and <xref:System.Windows.Forms.FlowLayoutPanel> arranges its child controls in the default <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f3bc-241">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5f3bc-241">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="5f3bc-242">WPF-Designer</span><span class="sxs-lookup"><span data-stu-id="5f3bc-242">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [<span data-ttu-id="5f3bc-243">Überlegungen zum Layout für das WindowsFormsHost-Element</span><span class="sxs-lookup"><span data-stu-id="5f3bc-243">Layout Considerations for the WindowsFormsHost Element</span></span>](../../../../docs/framework/wpf/advanced/layout-considerations-for-the-windowsformshost-element.md)  
 [<span data-ttu-id="5f3bc-244">Anordnen von Windows Forms-Steuerelementen in WPF-Beispiel</span><span class="sxs-lookup"><span data-stu-id="5f3bc-244">Arranging Windows Forms Controls in WPF Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=159971)  
 [<span data-ttu-id="5f3bc-245">Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF</span><span class="sxs-lookup"><span data-stu-id="5f3bc-245">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [<span data-ttu-id="5f3bc-246">Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5f3bc-246">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
