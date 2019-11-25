---
title: 'Exemplarische Vorgehensweise: Zuordnen von Eigenschaften mit dem WindowsFormsHost-Element'
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- WindowsFormsHost element property mapping [WPF]
ms.assetid: 74809167-bf8e-48b7-a2e7-b4ea08bc7d8c
ms.openlocfilehash: 94d175ec58f35b7e807786c221437d05c605c0bc
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73974225"
---
# <a name="walkthrough-mapping-properties-using-the-windowsformshost-element"></a><span data-ttu-id="4290a-102">Exemplarische Vorgehensweise: Zuordnen von Eigenschaften mit dem WindowsFormsHost-Element</span><span class="sxs-lookup"><span data-stu-id="4290a-102">Walkthrough: Mapping Properties Using the WindowsFormsHost Element</span></span>

<span data-ttu-id="4290a-103">In dieser exemplarischen Vorgehensweise wird gezeigt, wie Sie die <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>-Eigenschaft verwenden, um den entsprechenden Eigenschaften eines gehosteten [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuer Elements [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaften zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="4290a-103">This walkthrough shows you how to use the <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> property to map [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>

<span data-ttu-id="4290a-104">In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="4290a-104">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="4290a-105">Erstellen des Projekts.</span><span class="sxs-lookup"><span data-stu-id="4290a-105">Creating the project.</span></span>

- <span data-ttu-id="4290a-106">Definieren des Anwendungslayouts</span><span class="sxs-lookup"><span data-stu-id="4290a-106">Defining the application layout.</span></span>

- <span data-ttu-id="4290a-107">Definieren einer neuen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="4290a-107">Defining a new property mapping.</span></span>

- <span data-ttu-id="4290a-108">Entfernen einer standardmäßigen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="4290a-108">Removing a default property mapping.</span></span>

- <span data-ttu-id="4290a-109">Ersetzen einer standardmäßigen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="4290a-109">Replacing a default property mapping.</span></span>

- <span data-ttu-id="4290a-110">Erweitern einer standardmäßigen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="4290a-110">Extending a default property mapping.</span></span>

<span data-ttu-id="4290a-111">Eine komplette Code Auflistung der Aufgaben in dieser exemplarischen Vorgehensweise finden Sie unter [Mapping Properties using the Windows Form shost Element Sample](https://go.microsoft.com/fwlink/?LinkID=160019).</span><span class="sxs-lookup"><span data-stu-id="4290a-111">For a complete code listing of the tasks illustrated in this walkthrough, see [Mapping Properties Using the WindowsFormsHost Element Sample](https://go.microsoft.com/fwlink/?LinkID=160019).</span></span>

<span data-ttu-id="4290a-112">Wenn Sie fertig sind, können Sie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaften den entsprechenden Eigenschaften eines gehosteten [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuer Elements zuordnen.</span><span class="sxs-lookup"><span data-stu-id="4290a-112">When you are finished, you will be able to map [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4290a-113">Erforderliche Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="4290a-113">Prerequisites</span></span>

<span data-ttu-id="4290a-114">Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="4290a-114">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="4290a-115">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="4290a-115">Visual Studio 2017</span></span>

## <a name="create-and-set-up-the-project"></a><span data-ttu-id="4290a-116">Erstellen und Einrichten des Projekts</span><span class="sxs-lookup"><span data-stu-id="4290a-116">Create and set up the project</span></span>

1. <span data-ttu-id="4290a-117">Erstellen Sie ein **WPF-App** -Projekt mit dem Namen `PropertyMappingWithWfhSample`.</span><span class="sxs-lookup"><span data-stu-id="4290a-117">Create a **WPF App** project named `PropertyMappingWithWfhSample`.</span></span>

2. <span data-ttu-id="4290a-118">Fügen Sie in **Projektmappen-Explorer**einen Verweis auf die WindowsFormsIntegration-Assembly mit dem Namen "WindowsFormsIntegration. dll" hinzu.</span><span class="sxs-lookup"><span data-stu-id="4290a-118">In **Solution Explorer**, add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

3. <span data-ttu-id="4290a-119">Fügen Sie in **Projektmappen-Explorer**Verweise auf die Assemblys "System. Drawing" und "System. Windows. Forms" hinzu.</span><span class="sxs-lookup"><span data-stu-id="4290a-119">In **Solution Explorer**, add references to the System.Drawing and System.Windows.Forms assemblies.</span></span>

## <a name="defining-the-application-layout"></a><span data-ttu-id="4290a-120">Definieren des Anwendungslayouts</span><span class="sxs-lookup"><span data-stu-id="4290a-120">Defining the Application Layout</span></span>

<span data-ttu-id="4290a-121">Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]basierte Anwendung verwendet das <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element, um ein [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-Steuerelement zu hosten.</span><span class="sxs-lookup"><span data-stu-id="4290a-121">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application uses the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element to host a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>

### <a name="to-define-the-application-layout"></a><span data-ttu-id="4290a-122">So definieren sie das Anwendungslayout</span><span class="sxs-lookup"><span data-stu-id="4290a-122">To define the application layout</span></span>

1. <span data-ttu-id="4290a-123">Öffnen Sie Window1. XAML im WPF-Designer.</span><span class="sxs-lookup"><span data-stu-id="4290a-123">Open Window1.xaml in the WPF Designer.</span></span>

2. <span data-ttu-id="4290a-124">Ersetzen Sie den vorhandenen Code durch folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="4290a-124">Replace the existing code with the following code.</span></span>

     [!code-xaml[PropertyMappingWithWfhSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml#1)]

3. <span data-ttu-id="4290a-125">Öffnen Sie Window1.xaml.cs im Code-Editor.</span><span class="sxs-lookup"><span data-stu-id="4290a-125">Open Window1.xaml.cs in the Code Editor.</span></span>

4. <span data-ttu-id="4290a-126">Importieren Sie am Anfang der Datei die folgenden Namespaces.</span><span class="sxs-lookup"><span data-stu-id="4290a-126">At the top of the file, import the following namespaces.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#20](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#20)]
     [!code-vb[PropertyMappingWithWfhSample#20](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#20)]

## <a name="defining-a-new-property-mapping"></a><span data-ttu-id="4290a-127">Definieren einer neuen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="4290a-127">Defining a New Property Mapping</span></span>

<span data-ttu-id="4290a-128">Das <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element stellt mehrere Standardeigenschaften Zuordnungen bereit.</span><span class="sxs-lookup"><span data-stu-id="4290a-128">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element provides several default property mappings.</span></span> <span data-ttu-id="4290a-129">Sie fügen eine neue Eigenschaften Zuordnung hinzu, indem Sie die <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A>-Methode für die <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>des <xref:System.Windows.Forms.Integration.WindowsFormsHost> Elements aufrufen.</span><span class="sxs-lookup"><span data-stu-id="4290a-129">You add a new property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>

### <a name="to-define-a-new-property-mapping"></a><span data-ttu-id="4290a-130">Definieren einer neuen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="4290a-130">To define a new property mapping</span></span>

- <span data-ttu-id="4290a-131">Kopieren Sie den folgenden Code in die Definition für die `Window1`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="4290a-131">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#14](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#14)]
     [!code-vb[PropertyMappingWithWfhSample#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#14)]

     <span data-ttu-id="4290a-132">Mit der `AddClipMapping`-Methode wird eine neue Zuordnung für die <xref:System.Windows.UIElement.Clip%2A>-Eigenschaft hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="4290a-132">The `AddClipMapping` method adds a new mapping for the <xref:System.Windows.UIElement.Clip%2A> property.</span></span>

     <span data-ttu-id="4290a-133">Die `OnClipChange`-Methode übersetzt die <xref:System.Windows.UIElement.Clip%2A>-Eigenschaft in die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.Region%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="4290a-133">The `OnClipChange` method translates the <xref:System.Windows.UIElement.Clip%2A> property to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.Region%2A> property.</span></span>

     <span data-ttu-id="4290a-134">Die `Window1_SizeChanged`-Methode behandelt das <xref:System.Windows.FrameworkElement.SizeChanged> Ereignis des Fensters und passt die Größe des Clippingbereichs an das Anwendungsfenster an.</span><span class="sxs-lookup"><span data-stu-id="4290a-134">The `Window1_SizeChanged` method handles the window's <xref:System.Windows.FrameworkElement.SizeChanged> event and sizes the clipping region to fit the application window.</span></span>

## <a name="removing-a-default-property-mapping"></a><span data-ttu-id="4290a-135">Entfernen einer standardmäßigen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="4290a-135">Removing a Default Property Mapping</span></span>

<span data-ttu-id="4290a-136">Entfernen Sie eine standardmäßige Eigenschaften Zuordnung, indem Sie die <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A>-Methode für die <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>des <xref:System.Windows.Forms.Integration.WindowsFormsHost> Elements aufrufen.</span><span class="sxs-lookup"><span data-stu-id="4290a-136">Remove a default property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>

### <a name="to-remove-a-default-property-mapping"></a><span data-ttu-id="4290a-137">Entfernen einer standardmäßigen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="4290a-137">To remove a default property mapping</span></span>

- <span data-ttu-id="4290a-138">Kopieren Sie den folgenden Code in die Definition für die `Window1`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="4290a-138">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#13](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#13)]
     [!code-vb[PropertyMappingWithWfhSample#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#13)]

     <span data-ttu-id="4290a-139">Die `RemoveCursorMapping`-Methode löscht die Standard Zuordnung für die <xref:System.Windows.FrameworkElement.Cursor%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="4290a-139">The `RemoveCursorMapping` method deletes the default mapping for the <xref:System.Windows.FrameworkElement.Cursor%2A> property.</span></span>

## <a name="replacing-a-default-property-mapping"></a><span data-ttu-id="4290a-140">Ersetzen einer standardmäßigen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="4290a-140">Replacing a Default Property Mapping</span></span>

<span data-ttu-id="4290a-141">Ersetzen Sie eine standardmäßige Eigenschaften Zuordnung, indem Sie die Standard Zuordnung entfernen und die <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A>-Methode für die <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>des <xref:System.Windows.Forms.Integration.WindowsFormsHost> Elements aufrufen.</span><span class="sxs-lookup"><span data-stu-id="4290a-141">Replace a default property mapping by removing the default mapping and calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>

### <a name="to-replace-a-default-property-mapping"></a><span data-ttu-id="4290a-142">So ersetzen Sie eine standardmäßige Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="4290a-142">To replace a default property mapping</span></span>

- <span data-ttu-id="4290a-143">Kopieren Sie den folgenden Code in die Definition für die `Window1`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="4290a-143">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#12](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#12)]
     [!code-vb[PropertyMappingWithWfhSample#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#12)]

     <span data-ttu-id="4290a-144">Die `ReplaceFlowDirectionMapping`-Methode ersetzt die Standard Zuordnung für die <xref:System.Windows.FrameworkElement.FlowDirection%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="4290a-144">The `ReplaceFlowDirectionMapping` method replaces the default mapping for the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property.</span></span>

     <span data-ttu-id="4290a-145">Die `OnFlowDirectionChange`-Methode übersetzt die <xref:System.Windows.FrameworkElement.FlowDirection%2A>-Eigenschaft in die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.RightToLeft%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="4290a-145">The `OnFlowDirectionChange` method translates the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.RightToLeft%2A> property.</span></span>

     <span data-ttu-id="4290a-146">Die `cb_CheckedChanged`-Methode behandelt das <xref:System.Windows.Forms.CheckBox.CheckedChanged>-Ereignis auf dem <xref:System.Windows.Forms.CheckBox>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="4290a-146">The `cb_CheckedChanged` method handles the <xref:System.Windows.Forms.CheckBox.CheckedChanged> event on the <xref:System.Windows.Forms.CheckBox> control.</span></span> <span data-ttu-id="4290a-147">Die <xref:System.Windows.FrameworkElement.FlowDirection%2A>-Eigenschaft wird basierend auf dem Wert der <xref:System.Windows.Forms.CheckBox.CheckState%2A>-Eigenschaft zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="4290a-147">It assigns the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property based on the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property</span></span>

## <a name="extending-a-default-property-mapping"></a><span data-ttu-id="4290a-148">Erweitern einer standardmäßigen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="4290a-148">Extending a Default Property Mapping</span></span>

<span data-ttu-id="4290a-149">Sie können auch eine standardmäßige Eigenschaftenzuordnung verwenden und sie um Ihre eigenen Zuordnung erweitern.</span><span class="sxs-lookup"><span data-stu-id="4290a-149">You can use a default property mapping and also extend it with your own mapping.</span></span>

### <a name="to-extend-a-default-property-mapping"></a><span data-ttu-id="4290a-150">So erweitern Sie eine standardmäßigen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="4290a-150">To extend a default property mapping</span></span>

- <span data-ttu-id="4290a-151">Kopieren Sie den folgenden Code in die Definition für die `Window1`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="4290a-151">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#15](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#15)]
     [!code-vb[PropertyMappingWithWfhSample#15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#15)]

     <span data-ttu-id="4290a-152">Die `ExtendBackgroundMapping`-Methode fügt der vorhandenen <xref:System.Windows.Controls.Control.Background%2A> Eigenschaften Zuordnung einen benutzerdefinierten Eigenschaften Übersetzer hinzu.</span><span class="sxs-lookup"><span data-stu-id="4290a-152">The `ExtendBackgroundMapping` method adds a custom property translator to the existing <xref:System.Windows.Controls.Control.Background%2A> property mapping.</span></span>

     <span data-ttu-id="4290a-153">Die `OnBackgroundChange`-Methode weist ein bestimmtes Bild der <xref:System.Windows.Forms.Control.BackgroundImage%2A>-Eigenschaft des gehosteten Steuer Elements zu.</span><span class="sxs-lookup"><span data-stu-id="4290a-153">The `OnBackgroundChange` method assigns a specific image to the hosted control's <xref:System.Windows.Forms.Control.BackgroundImage%2A> property.</span></span> <span data-ttu-id="4290a-154">Die `OnBackgroundChange`-Methode wird aufgerufen, nachdem die Standardeigenschaften Zuordnung angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="4290a-154">The `OnBackgroundChange` method is called after the default property mapping is applied.</span></span>

## <a name="initializing-your-property-mappings"></a><span data-ttu-id="4290a-155">Initialisieren der Eigenschaftenzuordnungen</span><span class="sxs-lookup"><span data-stu-id="4290a-155">Initializing Your Property Mappings</span></span>

<span data-ttu-id="4290a-156">Richten Sie die Eigenschafts Zuordnungen ein, indem Sie die zuvor beschriebenen Methoden im <xref:System.Windows.FrameworkElement.Loaded>-Ereignishandler aufrufen.</span><span class="sxs-lookup"><span data-stu-id="4290a-156">Set up your property mappings by calling the previously described methods in the <xref:System.Windows.FrameworkElement.Loaded> event handler.</span></span>

### <a name="to-initialize-your-property-mappings"></a><span data-ttu-id="4290a-157">So initialisieren Sie Ihre Eigenschaftenzuordnungen</span><span class="sxs-lookup"><span data-stu-id="4290a-157">To initialize your property mappings</span></span>

1. <span data-ttu-id="4290a-158">Kopieren Sie den folgenden Code in die Definition für die `Window1`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="4290a-158">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#11](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#11)]
     [!code-vb[PropertyMappingWithWfhSample#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#11)]

     <span data-ttu-id="4290a-159">Die `WindowLoaded`-Methode behandelt das <xref:System.Windows.FrameworkElement.Loaded>-Ereignis und führt die folgende Initialisierung aus.</span><span class="sxs-lookup"><span data-stu-id="4290a-159">The `WindowLoaded` method handles the <xref:System.Windows.FrameworkElement.Loaded> event and performs the following initialization.</span></span>

    - <span data-ttu-id="4290a-160">Erstellt eine [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.CheckBox> Steuer Elements.</span><span class="sxs-lookup"><span data-stu-id="4290a-160">Creates a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.CheckBox> control.</span></span>

    - <span data-ttu-id="4290a-161">Sie ruft die Methoden, die Sie zuvor in der exemplarischen Vorgehensweise definiert haben, auf, um die Eigenschaftenzuordnungen einzurichten.</span><span class="sxs-lookup"><span data-stu-id="4290a-161">Calls the methods you defined earlier in the walkthrough to set up the property mappings.</span></span>

    - <span data-ttu-id="4290a-162">Sie weist den zugeordneten Eigenschaften Anfangswerte zu.</span><span class="sxs-lookup"><span data-stu-id="4290a-162">Assigns initial values to the mapped properties.</span></span>

2. <span data-ttu-id="4290a-163">Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4290a-163">Press **F5** to build and run the application.</span></span> <span data-ttu-id="4290a-164">Aktivieren Sie das Kontrollkästchen, um die Auswirkung der <xref:System.Windows.FrameworkElement.FlowDirection%2A> Zuordnung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4290a-164">Click the check box to see the effect of the <xref:System.Windows.FrameworkElement.FlowDirection%2A> mapping.</span></span> <span data-ttu-id="4290a-165">Wenn Sie das Kontrollkästchen klicken, kehrt das Layout seine Links-Rechts-Ausrichtung um.</span><span class="sxs-lookup"><span data-stu-id="4290a-165">When you click the check box, the layout reverses its left-right orientation.</span></span>

## <a name="see-also"></a><span data-ttu-id="4290a-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4290a-166">See also</span></span>

- <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="4290a-167">Eigenschaftenzuordnung von Windows Forms und WPF</span><span class="sxs-lookup"><span data-stu-id="4290a-167">Windows Forms and WPF Property Mapping</span></span>](windows-forms-and-wpf-property-mapping.md)
- [<span data-ttu-id="4290a-168">Entwerfen von XAML-Code in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4290a-168">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="4290a-169">Exemplarische Vorgehensweise: Hosten eines Windows Forms-Steuerelements in WPF</span><span class="sxs-lookup"><span data-stu-id="4290a-169">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
