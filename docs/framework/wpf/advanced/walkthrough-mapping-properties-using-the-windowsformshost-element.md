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
ms.openlocfilehash: 4841ce260adfb5d0c0d4b0f359ac9998521d584b
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43529646"
---
# <a name="walkthrough-mapping-properties-using-the-windowsformshost-element"></a><span data-ttu-id="e8747-102">Exemplarische Vorgehensweise: Zuordnen von Eigenschaften mit dem WindowsFormsHost-Element</span><span class="sxs-lookup"><span data-stu-id="e8747-102">Walkthrough: Mapping Properties Using the WindowsFormsHost Element</span></span>

<span data-ttu-id="e8747-103">In dieser exemplarischen Vorgehensweise erfahren Sie, wie Sie mit der <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> zuzuordnenden Eigenschaft [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaften den entsprechenden Eigenschaften eines gehosteten [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="e8747-103">This walkthrough shows you how to use the <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> property to map [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>

<span data-ttu-id="e8747-104">In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="e8747-104">Tasks illustrated in this walkthrough include:</span></span>

-   <span data-ttu-id="e8747-105">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="e8747-105">Creating the project.</span></span>

-   <span data-ttu-id="e8747-106">Definieren des Anwendungslayouts</span><span class="sxs-lookup"><span data-stu-id="e8747-106">Defining the application layout.</span></span>

-   <span data-ttu-id="e8747-107">Definieren einer neuen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="e8747-107">Defining a new property mapping.</span></span>

-   <span data-ttu-id="e8747-108">Entfernen einer standardmäßigen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="e8747-108">Removing a default property mapping.</span></span>

-   <span data-ttu-id="e8747-109">Ersetzen einer standardmäßigen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="e8747-109">Replacing a default property mapping.</span></span>

-   <span data-ttu-id="e8747-110">Erweitern einer standardmäßigen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="e8747-110">Extending a default property mapping.</span></span>

<span data-ttu-id="e8747-111">Eine vollständige codeauflistung der Aufgaben in dieser exemplarischen Vorgehensweise veranschaulicht, finden Sie unter [Zuordnen von Eigenschaften mit dem WindowsFormsHost-Element-Beispiel](https://go.microsoft.com/fwlink/?LinkID=160019).</span><span class="sxs-lookup"><span data-stu-id="e8747-111">For a complete code listing of the tasks illustrated in this walkthrough, see [Mapping Properties Using the WindowsFormsHost Element Sample](https://go.microsoft.com/fwlink/?LinkID=160019).</span></span>

<span data-ttu-id="e8747-112">Wenn Sie fertig sind, Sie werden zum Zuordnen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaften den entsprechenden Eigenschaften eines gehosteten [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="e8747-112">When you are finished, you will be able to map [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e8747-113">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="e8747-113">Prerequisites</span></span>

<span data-ttu-id="e8747-114">Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="e8747-114">You need the following components to complete this walkthrough:</span></span>

-   <span data-ttu-id="e8747-115">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="e8747-115">Visual Studio 2017</span></span>

## <a name="create-and-set-up-the-project"></a><span data-ttu-id="e8747-116">Erstellen und Einrichten des Projekts</span><span class="sxs-lookup"><span data-stu-id="e8747-116">Create and set up the project</span></span>

1.  <span data-ttu-id="e8747-117">Erstellen Sie eine **WPF-App** Projekt mit dem Namen `PropertyMappingWithWfhSample`.</span><span class="sxs-lookup"><span data-stu-id="e8747-117">Create a **WPF App** project named `PropertyMappingWithWfhSample`.</span></span>

2.  <span data-ttu-id="e8747-118">In **Projektmappen-Explorer**, fügen Sie einen Verweis auf die Assembly "WindowsFormsIntegration", mit dem Namen WindowsFormsIntegration.dll.</span><span class="sxs-lookup"><span data-stu-id="e8747-118">In **Solution Explorer**, add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

3.  <span data-ttu-id="e8747-119">In **Projektmappen-Explorer**, fügen Sie Verweise auf die Assemblys "System.Drawing" und "System.Windows.Forms" hinzu.</span><span class="sxs-lookup"><span data-stu-id="e8747-119">In **Solution Explorer**, add references to the System.Drawing and System.Windows.Forms assemblies.</span></span>

## <a name="defining-the-application-layout"></a><span data-ttu-id="e8747-120">Definieren des Anwendungslayouts</span><span class="sxs-lookup"><span data-stu-id="e8747-120">Defining the Application Layout</span></span>

<span data-ttu-id="e8747-121">Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]--basierte Anwendung verwendet die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element Host eine [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="e8747-121">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application uses the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element to host a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>

### <a name="to-define-the-application-layout"></a><span data-ttu-id="e8747-122">So definieren sie das Anwendungslayout</span><span class="sxs-lookup"><span data-stu-id="e8747-122">To define the application layout</span></span>

1.  <span data-ttu-id="e8747-123">Öffnen Sie Window1.xaml in der [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e8747-123">Open Window1.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>

2.  <span data-ttu-id="e8747-124">Ersetzen Sie den vorhandenen Code durch folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="e8747-124">Replace the existing code with the following code.</span></span>

     [!code-xaml[PropertyMappingWithWfhSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml#1)]

3.  <span data-ttu-id="e8747-125">Öffnen Sie Window1.xaml.cs im Code-Editor.</span><span class="sxs-lookup"><span data-stu-id="e8747-125">Open Window1.xaml.cs in the Code Editor.</span></span>

4.  <span data-ttu-id="e8747-126">Importieren Sie am Anfang der Datei die folgenden Namespaces.</span><span class="sxs-lookup"><span data-stu-id="e8747-126">At the top of the file, import the following namespaces.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#20)]
     [!code-vb[PropertyMappingWithWfhSample#20](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#20)]

## <a name="defining-a-new-property-mapping"></a><span data-ttu-id="e8747-127">Definieren einer neuen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="e8747-127">Defining a New Property Mapping</span></span>

<span data-ttu-id="e8747-128">Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element stellt mehrere Standard-eigenschaftenzuordnungen bereit.</span><span class="sxs-lookup"><span data-stu-id="e8747-128">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element provides several default property mappings.</span></span> <span data-ttu-id="e8747-129">Hinzufügen eine neuen eigenschaftenzuordnung durch den Aufruf der <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> Methode für die <xref:System.Windows.Forms.Integration.WindowsFormsHost> des Elements <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span><span class="sxs-lookup"><span data-stu-id="e8747-129">You add a new property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>

### <a name="to-define-a-new-property-mapping"></a><span data-ttu-id="e8747-130">Definieren einer neuen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="e8747-130">To define a new property mapping</span></span>

-   <span data-ttu-id="e8747-131">Kopieren Sie den folgenden Code in die Definition der `Window1` Klasse.</span><span class="sxs-lookup"><span data-stu-id="e8747-131">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#14)]
     [!code-vb[PropertyMappingWithWfhSample#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#14)]

     <span data-ttu-id="e8747-132">Die `AddClipMapping` Methode fügt eine neue Zuordnung für die <xref:System.Windows.UIElement.Clip%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e8747-132">The `AddClipMapping` method adds a new mapping for the <xref:System.Windows.UIElement.Clip%2A> property.</span></span>

     <span data-ttu-id="e8747-133">Die `OnClipChange` -Methode übersetzt die <xref:System.Windows.UIElement.Clip%2A> Eigenschaft, um die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Control.Region%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e8747-133">The `OnClipChange` method translates the <xref:System.Windows.UIElement.Clip%2A> property to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.Region%2A> property.</span></span>

     <span data-ttu-id="e8747-134">Die `Window1_SizeChanged` Methode verarbeitet das <xref:System.Windows.FrameworkElement.SizeChanged> Ereignis und passt die Größe des Clippingbereichs an das Anwendungsfenster angepasst.</span><span class="sxs-lookup"><span data-stu-id="e8747-134">The `Window1_SizeChanged` method handles the window's <xref:System.Windows.FrameworkElement.SizeChanged> event and sizes the clipping region to fit the application window.</span></span>

## <a name="removing-a-default-property-mapping"></a><span data-ttu-id="e8747-135">Entfernen einer standardmäßigen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="e8747-135">Removing a Default Property Mapping</span></span>

<span data-ttu-id="e8747-136">Entfernen eine standardmäßigen eigenschaftenzuordnung durch Aufrufen der <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> Methode für die <xref:System.Windows.Forms.Integration.WindowsFormsHost> des Elements <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span><span class="sxs-lookup"><span data-stu-id="e8747-136">Remove a default property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>

### <a name="to-remove-a-default-property-mapping"></a><span data-ttu-id="e8747-137">Entfernen einer standardmäßigen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="e8747-137">To remove a default property mapping</span></span>

-   <span data-ttu-id="e8747-138">Kopieren Sie den folgenden Code in die Definition der `Window1` Klasse.</span><span class="sxs-lookup"><span data-stu-id="e8747-138">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#13)]
     [!code-vb[PropertyMappingWithWfhSample#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#13)]

     <span data-ttu-id="e8747-139">Die `RemoveCursorMapping` -Methode löscht die standardzuordnung für die <xref:System.Windows.FrameworkElement.Cursor%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e8747-139">The `RemoveCursorMapping` method deletes the default mapping for the <xref:System.Windows.FrameworkElement.Cursor%2A> property.</span></span>

## <a name="replacing-a-default-property-mapping"></a><span data-ttu-id="e8747-140">Ersetzen einer standardmäßigen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="e8747-140">Replacing a Default Property Mapping</span></span>

<span data-ttu-id="e8747-141">Ersetzen eine standardmäßigen eigenschaftenzuordnung durch das Entfernen der standardzuordnung und Aufrufen der <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> Methode für die <xref:System.Windows.Forms.Integration.WindowsFormsHost> des Elements <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span><span class="sxs-lookup"><span data-stu-id="e8747-141">Replace a default property mapping by removing the default mapping and calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>

### <a name="to-replace-a-default-property-mapping"></a><span data-ttu-id="e8747-142">So ersetzen Sie eine standardmäßige Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="e8747-142">To replace a default property mapping</span></span>

-   <span data-ttu-id="e8747-143">Kopieren Sie den folgenden Code in die Definition der `Window1` Klasse.</span><span class="sxs-lookup"><span data-stu-id="e8747-143">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#12)]
     [!code-vb[PropertyMappingWithWfhSample#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#12)]

     <span data-ttu-id="e8747-144">Die `ReplaceFlowDirectionMapping` Methode ersetzt die standardzuordnung für die <xref:System.Windows.FrameworkElement.FlowDirection%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e8747-144">The `ReplaceFlowDirectionMapping` method replaces the default mapping for the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property.</span></span>

     <span data-ttu-id="e8747-145">Die `OnFlowDirectionChange` -Methode übersetzt die <xref:System.Windows.FrameworkElement.FlowDirection%2A> Eigenschaft, um die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Control.RightToLeft%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e8747-145">The `OnFlowDirectionChange` method translates the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.RightToLeft%2A> property.</span></span>

     <span data-ttu-id="e8747-146">Die `cb_CheckedChanged` verarbeitet die <xref:System.Windows.Forms.CheckBox.CheckedChanged> Ereignis auf der <xref:System.Windows.Forms.CheckBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="e8747-146">The `cb_CheckedChanged` method handles the <xref:System.Windows.Forms.CheckBox.CheckedChanged> event on the <xref:System.Windows.Forms.CheckBox> control.</span></span> <span data-ttu-id="e8747-147">Weist die <xref:System.Windows.FrameworkElement.FlowDirection%2A> -Eigenschaft basierend auf den Wert des der <xref:System.Windows.Forms.CheckBox.CheckState%2A> Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="e8747-147">It assigns the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property based on the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property</span></span>

## <a name="extending-a-default-property-mapping"></a><span data-ttu-id="e8747-148">Erweitern einer standardmäßigen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="e8747-148">Extending a Default Property Mapping</span></span>

<span data-ttu-id="e8747-149">Sie können auch eine standardmäßige Eigenschaftenzuordnung verwenden und sie um Ihre eigenen Zuordnung erweitern.</span><span class="sxs-lookup"><span data-stu-id="e8747-149">You can use a default property mapping and also extend it with your own mapping.</span></span>

### <a name="to-extend-a-default-property-mapping"></a><span data-ttu-id="e8747-150">So erweitern Sie eine standardmäßigen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="e8747-150">To extend a default property mapping</span></span>

-   <span data-ttu-id="e8747-151">Kopieren Sie den folgenden Code in die Definition der `Window1` Klasse.</span><span class="sxs-lookup"><span data-stu-id="e8747-151">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#15)]
     [!code-vb[PropertyMappingWithWfhSample#15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#15)]

     <span data-ttu-id="e8747-152">Die `ExtendBackgroundMapping` Methode fügt einen benutzerdefinierten Eigenschaftenübersetzer zur vorhandenen <xref:System.Windows.Controls.Control.Background%2A> eigenschaftenzuordnung.</span><span class="sxs-lookup"><span data-stu-id="e8747-152">The `ExtendBackgroundMapping` method adds a custom property translator to the existing <xref:System.Windows.Controls.Control.Background%2A> property mapping.</span></span>

     <span data-ttu-id="e8747-153">Die `OnBackgroundChange` Methode weist ein bestimmtes Bild des gehosteten Steuerelements <xref:System.Windows.Forms.Control.BackgroundImage%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e8747-153">The `OnBackgroundChange` method assigns a specific image to the hosted control's <xref:System.Windows.Forms.Control.BackgroundImage%2A> property.</span></span> <span data-ttu-id="e8747-154">Die `OnBackgroundChange` Methode wird aufgerufen, nachdem die standardzuordnung angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="e8747-154">The `OnBackgroundChange` method is called after the default property mapping is applied.</span></span>

## <a name="initializing-your-property-mappings"></a><span data-ttu-id="e8747-155">Initialisieren der Eigenschaftenzuordnungen</span><span class="sxs-lookup"><span data-stu-id="e8747-155">Initializing Your Property Mappings</span></span>

<span data-ttu-id="e8747-156">Richten Ihre eigenschaftenzuordnungen durch Aufrufen der oben beschriebenen Methoden in der <xref:System.Windows.FrameworkElement.Loaded> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="e8747-156">Set up your property mappings by calling the previously described methods in the <xref:System.Windows.FrameworkElement.Loaded> event handler.</span></span>

### <a name="to-initialize-your-property-mappings"></a><span data-ttu-id="e8747-157">So initialisieren Sie Ihre Eigenschaftenzuordnungen</span><span class="sxs-lookup"><span data-stu-id="e8747-157">To initialize your property mappings</span></span>

1.  <span data-ttu-id="e8747-158">Kopieren Sie den folgenden Code in die Definition der `Window1` Klasse.</span><span class="sxs-lookup"><span data-stu-id="e8747-158">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#11)]
     [!code-vb[PropertyMappingWithWfhSample#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#11)]

     <span data-ttu-id="e8747-159">Die `WindowLoaded` verarbeitet die <xref:System.Windows.FrameworkElement.Loaded> Ereignis und führt die folgende Initialisierung.</span><span class="sxs-lookup"><span data-stu-id="e8747-159">The `WindowLoaded` method handles the <xref:System.Windows.FrameworkElement.Loaded> event and performs the following initialization.</span></span>

    -   <span data-ttu-id="e8747-160">Erstellt eine [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.CheckBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="e8747-160">Creates a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.CheckBox> control.</span></span>

    -   <span data-ttu-id="e8747-161">Sie ruft die Methoden, die Sie zuvor in der exemplarischen Vorgehensweise definiert haben, auf, um die Eigenschaftenzuordnungen einzurichten.</span><span class="sxs-lookup"><span data-stu-id="e8747-161">Calls the methods you defined earlier in the walkthrough to set up the property mappings.</span></span>

    -   <span data-ttu-id="e8747-162">Sie weist den zugeordneten Eigenschaften Anfangswerte zu.</span><span class="sxs-lookup"><span data-stu-id="e8747-162">Assigns initial values to the mapped properties.</span></span>

2.  <span data-ttu-id="e8747-163">Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e8747-163">Press **F5** to build and run the application.</span></span> <span data-ttu-id="e8747-164">Klicken Sie auf das Kontrollkästchen, um die Wirkung sehen die <xref:System.Windows.FrameworkElement.FlowDirection%2A> Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="e8747-164">Click the check box to see the effect of the <xref:System.Windows.FrameworkElement.FlowDirection%2A> mapping.</span></span> <span data-ttu-id="e8747-165">Wenn Sie das Kontrollkästchen klicken, kehrt das Layout seine Links-Rechts-Ausrichtung um.</span><span class="sxs-lookup"><span data-stu-id="e8747-165">When you click the check box, the layout reverses its left-right orientation.</span></span>

## <a name="see-also"></a><span data-ttu-id="e8747-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8747-166">See Also</span></span>

- <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="e8747-167">Eigenschaftenzuordnung von Windows Forms und WPF</span><span class="sxs-lookup"><span data-stu-id="e8747-167">Windows Forms and WPF Property Mapping</span></span>](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)
- [<span data-ttu-id="e8747-168">Entwerfen von XAML-Code in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e8747-168">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="e8747-169">Exemplarische Vorgehensweise: Hosten eines Windows Forms-Steuerelements in WPF</span><span class="sxs-lookup"><span data-stu-id="e8747-169">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)