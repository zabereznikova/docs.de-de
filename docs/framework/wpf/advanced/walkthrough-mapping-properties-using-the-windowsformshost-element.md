---
title: 'Exemplarische Vorgehensweise: Zuordnen von Eigenschaften mit dem WindowsFormsHost-Element'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- WindowsFormsHost element property mapping [WPF]
ms.assetid: 74809167-bf8e-48b7-a2e7-b4ea08bc7d8c
ms.openlocfilehash: 771c0d972420b929ac757ced684de70d2dc7a58d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33549301"
---
# <a name="walkthrough-mapping-properties-using-the-windowsformshost-element"></a><span data-ttu-id="288aa-102">Exemplarische Vorgehensweise: Zuordnen von Eigenschaften mit dem WindowsFormsHost-Element</span><span class="sxs-lookup"><span data-stu-id="288aa-102">Walkthrough: Mapping Properties Using the WindowsFormsHost Element</span></span>
<span data-ttu-id="288aa-103">Diese exemplarische Vorgehensweise veranschaulicht das Verwenden der <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> zuzuordnenden Eigenschaft [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaften den entsprechenden Eigenschaften eines gehosteten [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="288aa-103">This walkthrough shows you how to use the <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> property to map [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>  
  
 <span data-ttu-id="288aa-104">In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="288aa-104">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="288aa-105">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="288aa-105">Creating the project.</span></span>  
  
-   <span data-ttu-id="288aa-106">Definieren des Anwendungslayouts</span><span class="sxs-lookup"><span data-stu-id="288aa-106">Defining the application layout.</span></span>  
  
-   <span data-ttu-id="288aa-107">Definieren einer neuen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="288aa-107">Defining a new property mapping.</span></span>  
  
-   <span data-ttu-id="288aa-108">Entfernen einer standardmäßigen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="288aa-108">Removing a default property mapping.</span></span>  
  
-   <span data-ttu-id="288aa-109">Ersetzen einer standardmäßigen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="288aa-109">Replacing a default property mapping.</span></span>  
  
-   <span data-ttu-id="288aa-110">Erweitern einer standardmäßigen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="288aa-110">Extending a default property mapping.</span></span>  
  
 <span data-ttu-id="288aa-111">Vollständige Codeliste der Aufgaben in dieser exemplarischen Vorgehensweise veranschaulicht, finden Sie unter [Zuordnen von Eigenschaften mit dem WindowsFormsHost-Element-Beispiel](http://go.microsoft.com/fwlink/?LinkID=160019).</span><span class="sxs-lookup"><span data-stu-id="288aa-111">For a complete code listing of the tasks illustrated in this walkthrough, see [Mapping Properties Using the WindowsFormsHost Element Sample](http://go.microsoft.com/fwlink/?LinkID=160019).</span></span>  
  
 <span data-ttu-id="288aa-112">Wenn Sie fertig sind, können Sie zeilenfilterausdruck zuordnen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaften den entsprechenden Eigenschaften eines gehosteten [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="288aa-112">When you are finished, you will be able to map [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="288aa-113">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="288aa-113">Prerequisites</span></span>  
 <span data-ttu-id="288aa-114">Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="288aa-114">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)]<span data-ttu-id="288aa-115">.</span><span class="sxs-lookup"><span data-stu-id="288aa-115">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="288aa-116">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="288aa-116">Creating the Project</span></span>  
  
#### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="288aa-117">So erstellen und richten Sie das Projekt ein</span><span class="sxs-lookup"><span data-stu-id="288aa-117">To create and set up the project</span></span>  
  
1.  <span data-ttu-id="288aa-118">Erstellen Sie ein WPF-Anwendungsprojekt mit dem Namen `PropertyMappingWithWfhSample`.</span><span class="sxs-lookup"><span data-stu-id="288aa-118">Create a WPF Application project named `PropertyMappingWithWfhSample`.</span></span>  
  
2.  <span data-ttu-id="288aa-119">Fügen Sie im Projektmappen-Explorer einen Verweis auf die Assembly mit die Namen WindowsFormsIntegration.dll WindowsFormsIntegration.</span><span class="sxs-lookup"><span data-stu-id="288aa-119">In Solution Explorer, add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>  
  
3.  <span data-ttu-id="288aa-120">Fügen Sie im Projektmappen-Explorer Verweise auf die Assemblys "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="288aa-120">In Solution Explorer, add references to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="defining-the-application-layout"></a><span data-ttu-id="288aa-121">Definieren des Anwendungslayouts</span><span class="sxs-lookup"><span data-stu-id="288aa-121">Defining the Application Layout</span></span>  
 <span data-ttu-id="288aa-122">Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]--basierte Anwendung verwendet die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element Host ein [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="288aa-122">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application uses the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element to host a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>  
  
#### <a name="to-define-the-application-layout"></a><span data-ttu-id="288aa-123">So definieren sie das Anwendungslayout</span><span class="sxs-lookup"><span data-stu-id="288aa-123">To define the application layout</span></span>  
  
1.  <span data-ttu-id="288aa-124">Öffnen Sie Window1.xaml in der [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="288aa-124">Open Window1.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
2.  <span data-ttu-id="288aa-125">Ersetzen Sie den vorhandenen Code durch folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="288aa-125">Replace the existing code with the following code.</span></span>  
  
     [!code-xaml[PropertyMappingWithWfhSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml#1)]  
  
3.  <span data-ttu-id="288aa-126">Öffnen Sie Window1.xaml.cs im Code-Editor.</span><span class="sxs-lookup"><span data-stu-id="288aa-126">Open Window1.xaml.cs in the Code Editor.</span></span>  
  
4.  <span data-ttu-id="288aa-127">Importieren Sie am Anfang der Datei die folgenden Namespaces.</span><span class="sxs-lookup"><span data-stu-id="288aa-127">At the top of the file, import the following namespaces.</span></span>  
  
     [!code-csharp[PropertyMappingWithWfhSample#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#20)]
     [!code-vb[PropertyMappingWithWfhSample#20](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#20)]  
  
## <a name="defining-a-new-property-mapping"></a><span data-ttu-id="288aa-128">Definieren einer neuen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="288aa-128">Defining a New Property Mapping</span></span>  
 <span data-ttu-id="288aa-129">Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element stellt mehrere eigenschaftenzuordnungen bereit.</span><span class="sxs-lookup"><span data-stu-id="288aa-129">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element provides several default property mappings.</span></span> <span data-ttu-id="288aa-130">Sie fügen Sie eine neue eigenschaftenzuordnung durch Aufrufen der <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> Methode für die <xref:System.Windows.Forms.Integration.WindowsFormsHost> des Elements <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span><span class="sxs-lookup"><span data-stu-id="288aa-130">You add a new property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>  
  
#### <a name="to-define-a-new-property-mapping"></a><span data-ttu-id="288aa-131">Definieren einer neuen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="288aa-131">To define a new property mapping</span></span>  
  
-   <span data-ttu-id="288aa-132">Kopieren Sie den folgenden Code in die Definition für die `Window1` Klasse.</span><span class="sxs-lookup"><span data-stu-id="288aa-132">Copy the following code into the definition for the `Window1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithWfhSample#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#14)]
     [!code-vb[PropertyMappingWithWfhSample#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#14)]  
  
     <span data-ttu-id="288aa-133">Die `AddClipMapping` Methode fügt eine neue Zuordnung für die <xref:System.Windows.UIElement.Clip%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="288aa-133">The `AddClipMapping` method adds a new mapping for the <xref:System.Windows.UIElement.Clip%2A> property.</span></span>  
  
     <span data-ttu-id="288aa-134">Die `OnClipChange` -Methode der <xref:System.Windows.UIElement.Clip%2A> Eigenschaft, um die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Control.Region%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="288aa-134">The `OnClipChange` method translates the <xref:System.Windows.UIElement.Clip%2A> property to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.Region%2A> property.</span></span>  
  
     <span data-ttu-id="288aa-135">Die `Window1_SizeChanged` Methode behandelt des Fensters <xref:System.Windows.FrameworkElement.SizeChanged> Ereignis und die Größe des Clippingbereichs entsprechend im Anwendungsfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="288aa-135">The `Window1_SizeChanged` method handles the window's <xref:System.Windows.FrameworkElement.SizeChanged> event and sizes the clipping region to fit the application window.</span></span>  
  
## <a name="removing-a-default-property-mapping"></a><span data-ttu-id="288aa-136">Entfernen einer standardmäßigen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="288aa-136">Removing a Default Property Mapping</span></span>  
 <span data-ttu-id="288aa-137">Entfernen Sie die Zuordnung einer Standard-Eigenschaft durch Aufrufen der <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> Methode für die <xref:System.Windows.Forms.Integration.WindowsFormsHost> des Elements <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span><span class="sxs-lookup"><span data-stu-id="288aa-137">Remove a default property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>  
  
#### <a name="to-remove-a-default-property-mapping"></a><span data-ttu-id="288aa-138">Entfernen einer standardmäßigen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="288aa-138">To remove a default property mapping</span></span>  
  
-   <span data-ttu-id="288aa-139">Kopieren Sie den folgenden Code in die Definition für die `Window1` Klasse.</span><span class="sxs-lookup"><span data-stu-id="288aa-139">Copy the following code into the definition for the `Window1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithWfhSample#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#13)]
     [!code-vb[PropertyMappingWithWfhSample#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#13)]  
  
     <span data-ttu-id="288aa-140">Die `RemoveCursorMapping` -Methode löscht die standardzuordnung für die <xref:System.Windows.FrameworkElement.Cursor%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="288aa-140">The `RemoveCursorMapping` method deletes the default mapping for the <xref:System.Windows.FrameworkElement.Cursor%2A> property.</span></span>  
  
## <a name="replacing-a-default-property-mapping"></a><span data-ttu-id="288aa-141">Ersetzen einer standardmäßigen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="288aa-141">Replacing a Default Property Mapping</span></span>  
 <span data-ttu-id="288aa-142">Ersetzen Sie die Zuordnung einer Standard-Eigenschaft entfernen, indem die standardzuordnung und Aufrufen der <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> Methode für die <xref:System.Windows.Forms.Integration.WindowsFormsHost> des Elements <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span><span class="sxs-lookup"><span data-stu-id="288aa-142">Replace a default property mapping by removing the default mapping and calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>  
  
#### <a name="to-replace-a-default-property-mapping"></a><span data-ttu-id="288aa-143">So ersetzen Sie eine standardmäßige Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="288aa-143">To replace a default property mapping</span></span>  
  
-   <span data-ttu-id="288aa-144">Kopieren Sie den folgenden Code in die Definition für die `Window1` Klasse.</span><span class="sxs-lookup"><span data-stu-id="288aa-144">Copy the following code into the definition for the `Window1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithWfhSample#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#12)]
     [!code-vb[PropertyMappingWithWfhSample#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#12)]  
  
     <span data-ttu-id="288aa-145">Die `ReplaceFlowDirectionMapping` Methode ersetzt die standardzuordnung für die <xref:System.Windows.FrameworkElement.FlowDirection%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="288aa-145">The `ReplaceFlowDirectionMapping` method replaces the default mapping for the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property.</span></span>  
  
     <span data-ttu-id="288aa-146">Die `OnFlowDirectionChange` -Methode der <xref:System.Windows.FrameworkElement.FlowDirection%2A> Eigenschaft, um die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Control.RightToLeft%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="288aa-146">The `OnFlowDirectionChange` method translates the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.RightToLeft%2A> property.</span></span>  
  
     <span data-ttu-id="288aa-147">Die `cb_CheckedChanged` Methode behandelt das <xref:System.Windows.Forms.CheckBox.CheckedChanged> Ereignis auf der <xref:System.Windows.Forms.CheckBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="288aa-147">The `cb_CheckedChanged` method handles the <xref:System.Windows.Forms.CheckBox.CheckedChanged> event on the <xref:System.Windows.Forms.CheckBox> control.</span></span> <span data-ttu-id="288aa-148">Weist die <xref:System.Windows.FrameworkElement.FlowDirection%2A> Eigenschaft basierend auf den Wert der <xref:System.Windows.Forms.CheckBox.CheckState%2A> Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="288aa-148">It assigns the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property based on the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property</span></span>  
  
## <a name="extending-a-default-property-mapping"></a><span data-ttu-id="288aa-149">Erweitern einer standardmäßigen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="288aa-149">Extending a Default Property Mapping</span></span>  
 <span data-ttu-id="288aa-150">Sie können auch eine standardmäßige Eigenschaftenzuordnung verwenden und sie um Ihre eigenen Zuordnung erweitern.</span><span class="sxs-lookup"><span data-stu-id="288aa-150">You can use a default property mapping and also extend it with your own mapping.</span></span>  
  
#### <a name="to-extend-a-default-property-mapping"></a><span data-ttu-id="288aa-151">So erweitern Sie eine standardmäßigen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="288aa-151">To extend a default property mapping</span></span>  
  
-   <span data-ttu-id="288aa-152">Kopieren Sie den folgenden Code in die Definition für die `Window1` Klasse.</span><span class="sxs-lookup"><span data-stu-id="288aa-152">Copy the following code into the definition for the `Window1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithWfhSample#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#15)]
     [!code-vb[PropertyMappingWithWfhSample#15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#15)]  
  
     <span data-ttu-id="288aa-153">Die `ExtendBackgroundMapping` Methode fügt eine benutzerdefinierte Eigenschaftenübersetzer zur vorhandenen <xref:System.Windows.Controls.Control.Background%2A> eigenschaftenzuordnung.</span><span class="sxs-lookup"><span data-stu-id="288aa-153">The `ExtendBackgroundMapping` method adds a custom property translator to the existing <xref:System.Windows.Controls.Control.Background%2A> property mapping.</span></span>  
  
     <span data-ttu-id="288aa-154">Die `OnBackgroundChange` Methode weist ein bestimmtes Abbild des gehosteten Steuerelements <xref:System.Windows.Forms.Control.BackgroundImage%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="288aa-154">The `OnBackgroundChange` method assigns a specific image to the hosted control's <xref:System.Windows.Forms.Control.BackgroundImage%2A> property.</span></span> <span data-ttu-id="288aa-155">Die `OnBackgroundChange` Methode wird aufgerufen, nachdem die standardzuordnung für die Eigenschaft angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="288aa-155">The `OnBackgroundChange` method is called after the default property mapping is applied.</span></span>  
  
## <a name="initializing-your-property-mappings"></a><span data-ttu-id="288aa-156">Initialisieren der Eigenschaftenzuordnungen</span><span class="sxs-lookup"><span data-stu-id="288aa-156">Initializing Your Property Mappings</span></span>  
 <span data-ttu-id="288aa-157">Einrichten von gehen die eigenschaftenzuordnungen durch Aufrufen der zuvor beschriebenen Methoden der <xref:System.Windows.FrameworkElement.Loaded> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="288aa-157">Set up your property mappings by calling the previously described methods in the <xref:System.Windows.FrameworkElement.Loaded> event handler.</span></span>  
  
#### <a name="to-initialize-your-property-mappings"></a><span data-ttu-id="288aa-158">So initialisieren Sie Ihre Eigenschaftenzuordnungen</span><span class="sxs-lookup"><span data-stu-id="288aa-158">To initialize your property mappings</span></span>  
  
1.  <span data-ttu-id="288aa-159">Kopieren Sie den folgenden Code in die Definition für die `Window1` Klasse.</span><span class="sxs-lookup"><span data-stu-id="288aa-159">Copy the following code into the definition for the `Window1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithWfhSample#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#11)]
     [!code-vb[PropertyMappingWithWfhSample#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#11)]  
  
     <span data-ttu-id="288aa-160">Die `WindowLoaded` Methode behandelt das <xref:System.Windows.FrameworkElement.Loaded> Ereignis und führt die folgenden Initialisierung.</span><span class="sxs-lookup"><span data-stu-id="288aa-160">The `WindowLoaded` method handles the <xref:System.Windows.FrameworkElement.Loaded> event and performs the following initialization.</span></span>  
  
    -   <span data-ttu-id="288aa-161">Erstellt eine [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.CheckBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="288aa-161">Creates a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.CheckBox> control.</span></span>  
  
    -   <span data-ttu-id="288aa-162">Sie ruft die Methoden, die Sie zuvor in der exemplarischen Vorgehensweise definiert haben, auf, um die Eigenschaftenzuordnungen einzurichten.</span><span class="sxs-lookup"><span data-stu-id="288aa-162">Calls the methods you defined earlier in the walkthrough to set up the property mappings.</span></span>  
  
    -   <span data-ttu-id="288aa-163">Sie weist den zugeordneten Eigenschaften Anfangswerte zu.</span><span class="sxs-lookup"><span data-stu-id="288aa-163">Assigns initial values to the mapped properties.</span></span>  
  
2.  <span data-ttu-id="288aa-164">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="288aa-164">Press F5 to build and run the application.</span></span> <span data-ttu-id="288aa-165">Klicken Sie auf dieses Kontrollkästchen, damit die Auswirkungen der finden Sie unter der <xref:System.Windows.FrameworkElement.FlowDirection%2A> Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="288aa-165">Click the check box to see the effect of the <xref:System.Windows.FrameworkElement.FlowDirection%2A> mapping.</span></span> <span data-ttu-id="288aa-166">Wenn Sie das Kontrollkästchen klicken, kehrt das Layout seine Links-Rechts-Ausrichtung um.</span><span class="sxs-lookup"><span data-stu-id="288aa-166">When you click the check box, the layout reverses its left-right orientation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="288aa-167">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="288aa-167">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="288aa-168">Eigenschaftenzuordnung von Windows Forms und WPF</span><span class="sxs-lookup"><span data-stu-id="288aa-168">Windows Forms and WPF Property Mapping</span></span>](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)  
 [<span data-ttu-id="288aa-169">WPF-Designer</span><span class="sxs-lookup"><span data-stu-id="288aa-169">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [<span data-ttu-id="288aa-170">Exemplarische Vorgehensweise: Hosten eines Windows Forms-Steuerelements in WPF</span><span class="sxs-lookup"><span data-stu-id="288aa-170">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)
