---
title: 'Exemplarische Vorgehensweise: Zuordnen von Eigenschaften mit dem ElementHost-Steuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- ElementHost control [WPF], mapping properties
ms.assetid: bccd6e0d-2272-4924-9107-ff8ed58b88aa
ms.openlocfilehash: b5af1f45a0d01761358e83c890544ec1a11836e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33549190"
---
# <a name="walkthrough-mapping-properties-using-the-elementhost-control"></a><span data-ttu-id="94789-102">Exemplarische Vorgehensweise: Zuordnen von Eigenschaften mit dem ElementHost-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="94789-102">Walkthrough: Mapping Properties Using the ElementHost Control</span></span>
<span data-ttu-id="94789-103">Diese exemplarische Vorgehensweise veranschaulicht das Verwenden der <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> zuzuordnenden Eigenschaft [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Eigenschaften den entsprechenden Eigenschaften eines gehosteten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Element.</span><span class="sxs-lookup"><span data-stu-id="94789-103">This walkthrough shows you how to use the <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> property to map [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element.</span></span>  
  
 <span data-ttu-id="94789-104">In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="94789-104">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="94789-105">Erstellen des Projekts.</span><span class="sxs-lookup"><span data-stu-id="94789-105">Creating the project.</span></span>  
  
-   <span data-ttu-id="94789-106">Definieren einer neuen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="94789-106">Defining a new property mapping.</span></span>  
  
-   <span data-ttu-id="94789-107">Entfernen einer standardmäßigen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="94789-107">Removing a default property mapping.</span></span>  
  
-   <span data-ttu-id="94789-108">Erweitern einer standardmäßigen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="94789-108">Extending a default property mapping.</span></span>  
  
 <span data-ttu-id="94789-109">Vollständige Codeliste der Aufgaben in dieser exemplarischen Vorgehensweise veranschaulicht, finden Sie unter [Zuordnungseigenschaften, die mithilfe der ElementHost-Steuerelement-Beispiel](http://go.microsoft.com/fwlink/?LinkID=160018).</span><span class="sxs-lookup"><span data-stu-id="94789-109">For a complete code listing of the tasks illustrated in this walkthrough, see [Mapping Properties Using the ElementHost Control Sample](http://go.microsoft.com/fwlink/?LinkID=160018).</span></span>  
  
 <span data-ttu-id="94789-110">Wenn Sie fertig sind, können Sie zeilenfilterausdruck zuordnen [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Eigenschaften entsprechenden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaften in einem gehosteten Element.</span><span class="sxs-lookup"><span data-stu-id="94789-110">When you are finished, you will be able to map [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] properties to corresponding [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties on a hosted element.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="94789-111">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="94789-111">Prerequisites</span></span>  
 <span data-ttu-id="94789-112">Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="94789-112">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)]<span data-ttu-id="94789-113">.</span><span class="sxs-lookup"><span data-stu-id="94789-113">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="94789-114">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="94789-114">Creating the Project</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="94789-115">So erstellen Sie das Projekt</span><span class="sxs-lookup"><span data-stu-id="94789-115">To create the project</span></span>  
  
1.  <span data-ttu-id="94789-116">Erstellen einer [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] -Anwendungsprojekt mit dem Namen `PropertyMappingWithElementHost`.</span><span class="sxs-lookup"><span data-stu-id="94789-116">Create a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] application project named `PropertyMappingWithElementHost`.</span></span> <span data-ttu-id="94789-117">Weitere Informationen finden Sie unter [How to: Create a Windows Application Project (Vorgehensweise: Erstellen eines neuen Windows Forms-Anwendungsprojekts)](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span><span class="sxs-lookup"><span data-stu-id="94789-117">For more information, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
2.  <span data-ttu-id="94789-118">Fügen Sie im Projektmappen-Explorer Verweise auf die folgenden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Assemblys.</span><span class="sxs-lookup"><span data-stu-id="94789-118">In Solution Explorer, add references to the following [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assemblies.</span></span>  
  
    -   <span data-ttu-id="94789-119">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="94789-119">PresentationCore</span></span>  
  
    -   <span data-ttu-id="94789-120">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="94789-120">PresentationFramework</span></span>  
  
    -   <span data-ttu-id="94789-121">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="94789-121">WindowsBase</span></span>  
  
    -   <span data-ttu-id="94789-122">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="94789-122">WindowsFormsIntegration</span></span>  
  
3.  <span data-ttu-id="94789-123">Kopieren Sie den folgenden Code in den oberen Rand der `Form1` -Codedatei.</span><span class="sxs-lookup"><span data-stu-id="94789-123">Copy the following code into the top of the `Form1` code file.</span></span>  
  
     [!code-csharp[PropertyMappingWithElementHost#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#10)]
     [!code-vb[PropertyMappingWithElementHost#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#10)]  
  
4.  <span data-ttu-id="94789-124">Öffnen Sie `Form1` im Windows Forms-Designer.</span><span class="sxs-lookup"><span data-stu-id="94789-124">Open `Form1` in the Windows Forms Designer.</span></span> <span data-ttu-id="94789-125">Doppelklicken Sie auf das Formular zum Hinzufügen eines ereignishandlers für das <xref:System.Windows.Forms.Form.Load> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="94789-125">Double-click the form to add an event handler for the <xref:System.Windows.Forms.Form.Load> event.</span></span>  
  
5.  <span data-ttu-id="94789-126">Kehren Sie zum Windows Forms-Designer zurück, und fügen Sie einen Ereignishandler für des Formulars <xref:System.Windows.Forms.Control.Resize> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="94789-126">Return to the Windows Forms Designer and add an event handler for the form's <xref:System.Windows.Forms.Control.Resize> event.</span></span> <span data-ttu-id="94789-127">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen Sie Ereignis-Handler mithilfe des Designers](http://msdn.microsoft.com/library/8461e9b8-14e8-406f-936e-3726732b23d2).</span><span class="sxs-lookup"><span data-stu-id="94789-127">For more information, see [How to: Create Event Handlers Using the Designer](http://msdn.microsoft.com/library/8461e9b8-14e8-406f-936e-3726732b23d2).</span></span>  
  
6.  <span data-ttu-id="94789-128">Deklarieren Sie eine <xref:System.Windows.Forms.Integration.ElementHost> -Feld in der `Form1` Klasse.</span><span class="sxs-lookup"><span data-stu-id="94789-128">Declare an <xref:System.Windows.Forms.Integration.ElementHost> field in the `Form1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithElementHost#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#16)]
     [!code-vb[PropertyMappingWithElementHost#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#16)]  
  
## <a name="defining-new-property-mappings"></a><span data-ttu-id="94789-129">Definieren neue Eigenschaftenzuordnungen</span><span class="sxs-lookup"><span data-stu-id="94789-129">Defining New Property Mappings</span></span>  
 <span data-ttu-id="94789-130">Die <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement stellt mehrere eigenschaftenzuordnungen.</span><span class="sxs-lookup"><span data-stu-id="94789-130">The <xref:System.Windows.Forms.Integration.ElementHost> control provides several default property mappings.</span></span> <span data-ttu-id="94789-131">Sie fügen Sie eine neue eigenschaftenzuordnung durch Aufrufen der <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> Methode für die <xref:System.Windows.Forms.Integration.ElementHost> des Steuerelements <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span><span class="sxs-lookup"><span data-stu-id="94789-131">You add a new property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control's <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span></span>  
  
#### <a name="to-define-new-property-mappings"></a><span data-ttu-id="94789-132">Um neue eigenschaftenzuordnungen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="94789-132">To define new property mappings</span></span>  
  
1.  <span data-ttu-id="94789-133">Kopieren Sie den folgenden Code in die Definition für die `Form1` Klasse.</span><span class="sxs-lookup"><span data-stu-id="94789-133">Copy the following code into the definition for the `Form1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithElementHost#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#12)]
     [!code-vb[PropertyMappingWithElementHost#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#12)]  
  
     <span data-ttu-id="94789-134">Die `AddMarginMapping` Methode fügt eine neue Zuordnung für die <xref:System.Windows.Forms.Control.Margin%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="94789-134">The `AddMarginMapping` method adds a new mapping for the <xref:System.Windows.Forms.Control.Margin%2A> property.</span></span>  
  
     <span data-ttu-id="94789-135">Die `OnMarginChange` -Methode der <xref:System.Windows.Forms.Control.Margin%2A> Eigenschaft, um die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="94789-135">The `OnMarginChange` method translates the <xref:System.Windows.Forms.Control.Margin%2A> property to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> property.</span></span>  
  
2.  <span data-ttu-id="94789-136">Kopieren Sie den folgenden Code in die Definition für die `Form1` Klasse.</span><span class="sxs-lookup"><span data-stu-id="94789-136">Copy the following code into the definition for the `Form1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithElementHost#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#14)]
     [!code-vb[PropertyMappingWithElementHost#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#14)]  
  
     <span data-ttu-id="94789-137">Die `AddRegionMapping` Methode fügt eine neue Zuordnung für die <xref:System.Windows.Forms.Control.Region%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="94789-137">The `AddRegionMapping` method adds a new mapping for the <xref:System.Windows.Forms.Control.Region%2A> property.</span></span>  
  
     <span data-ttu-id="94789-138">Die `OnRegionChange` -Methode der <xref:System.Windows.Forms.Control.Region%2A> Eigenschaft, um die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="94789-138">The `OnRegionChange` method translates the <xref:System.Windows.Forms.Control.Region%2A> property to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> property.</span></span>  
  
     <span data-ttu-id="94789-139">Die `Form1_Resize` Methode behandelt des Formulars <xref:System.Windows.Forms.Control.Resize> Ereignis und die Größe des Clippingbereichs das gehostete Element passt.</span><span class="sxs-lookup"><span data-stu-id="94789-139">The `Form1_Resize` method handles the form's <xref:System.Windows.Forms.Control.Resize> event and sizes the clipping region to fit the hosted element.</span></span>  
  
## <a name="removing-a-default-property-mapping"></a><span data-ttu-id="94789-140">Entfernen einer standardmäßigen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="94789-140">Removing a Default Property Mapping</span></span>  
 <span data-ttu-id="94789-141">Entfernen Sie die Zuordnung einer Standard-Eigenschaft durch Aufrufen der <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> Methode für die <xref:System.Windows.Forms.Integration.ElementHost> des Steuerelements <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span><span class="sxs-lookup"><span data-stu-id="94789-141">Remove a default property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control's <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span></span>  
  
#### <a name="to-remove-a-default-property-mapping"></a><span data-ttu-id="94789-142">Entfernen einer standardmäßigen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="94789-142">To remove a default property mapping</span></span>  
  
-   <span data-ttu-id="94789-143">Kopieren Sie den folgenden Code in die Definition für die `Form1` Klasse.</span><span class="sxs-lookup"><span data-stu-id="94789-143">Copy the following code into the definition for the `Form1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithElementHost#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#13)]
     [!code-vb[PropertyMappingWithElementHost#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#13)]  
  
     <span data-ttu-id="94789-144">Die `RemoveCursorMapping` -Methode löscht die standardzuordnung für die <xref:System.Windows.Forms.Control.Cursor%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="94789-144">The `RemoveCursorMapping` method deletes the default mapping for the <xref:System.Windows.Forms.Control.Cursor%2A> property.</span></span>  
  
## <a name="extending-a-default-property-mapping"></a><span data-ttu-id="94789-145">Erweitern einer standardmäßigen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="94789-145">Extending a Default Property Mapping</span></span>  
 <span data-ttu-id="94789-146">Sie können auch eine standardmäßige Eigenschaftenzuordnung verwenden und sie um Ihre eigenen Zuordnung erweitern.</span><span class="sxs-lookup"><span data-stu-id="94789-146">You can use a default property mapping and also extend it with your own mapping.</span></span>  
  
#### <a name="to-extend-a-default-property-mapping"></a><span data-ttu-id="94789-147">So erweitern Sie eine standardmäßigen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="94789-147">To extend a default property mapping</span></span>  
  
-   <span data-ttu-id="94789-148">Kopieren Sie den folgenden Code in die Definition für die `Form1` Klasse.</span><span class="sxs-lookup"><span data-stu-id="94789-148">Copy the following code into the definition for the `Form1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithElementHost#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#15)]
     [!code-vb[PropertyMappingWithElementHost#15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#15)]  
  
     <span data-ttu-id="94789-149">Die `ExtendBackColorMapping` Methode fügt eine benutzerdefinierte Eigenschaftenübersetzer zur vorhandenen <xref:System.Windows.Forms.Control.BackColor%2A> eigenschaftenzuordnung.</span><span class="sxs-lookup"><span data-stu-id="94789-149">The `ExtendBackColorMapping` method adds a custom property translator to the existing <xref:System.Windows.Forms.Control.BackColor%2A> property mapping.</span></span>  
  
     <span data-ttu-id="94789-150">Die `OnBackColorChange` Methode weist ein bestimmtes Abbild des gehosteten Steuerelements <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="94789-150">The `OnBackColorChange` method assigns a specific image to the hosted control's <xref:System.Windows.Controls.Control.Background%2A> property.</span></span> <span data-ttu-id="94789-151">Die `OnBackColorChange` Methode wird aufgerufen, nachdem die standardzuordnung für die Eigenschaft angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="94789-151">The `OnBackColorChange` method is called after the default property mapping is applied.</span></span>  
  
## <a name="initializing-your-property-mappings"></a><span data-ttu-id="94789-152">Initialisieren der Eigenschaftenzuordnungen</span><span class="sxs-lookup"><span data-stu-id="94789-152">Initializing Your Property Mappings</span></span>  
  
#### <a name="to-initialize-your-property-mappings"></a><span data-ttu-id="94789-153">So initialisieren Sie Ihre Eigenschaftenzuordnungen</span><span class="sxs-lookup"><span data-stu-id="94789-153">To initialize your property mappings</span></span>  
  
1.  <span data-ttu-id="94789-154">Kopieren Sie den folgenden Code in die Definition für die `Form1` Klasse.</span><span class="sxs-lookup"><span data-stu-id="94789-154">Copy the following code into the definition for the `Form1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithElementHost#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#11)]
     [!code-vb[PropertyMappingWithElementHost#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#11)]  
  
     <span data-ttu-id="94789-155">Die `Form1_Load` Methode behandelt das <xref:System.Windows.Forms.Form.Load> Ereignis und führt die folgenden Initialisierung.</span><span class="sxs-lookup"><span data-stu-id="94789-155">The `Form1_Load` method handles the <xref:System.Windows.Forms.Form.Load> event and performs the following initialization.</span></span>  
  
    -   <span data-ttu-id="94789-156">Erstellt eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> Element.</span><span class="sxs-lookup"><span data-stu-id="94789-156">Creates a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> element.</span></span>  
  
    -   <span data-ttu-id="94789-157">Sie ruft die Methoden, die Sie zuvor in der exemplarischen Vorgehensweise definiert haben, auf, um die Eigenschaftenzuordnungen einzurichten.</span><span class="sxs-lookup"><span data-stu-id="94789-157">Calls the methods you defined earlier in the walkthrough to set up the property mappings.</span></span>  
  
    -   <span data-ttu-id="94789-158">Sie weist den zugeordneten Eigenschaften Anfangswerte zu.</span><span class="sxs-lookup"><span data-stu-id="94789-158">Assigns initial values to the mapped properties.</span></span>  
  
2.  <span data-ttu-id="94789-159">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="94789-159">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94789-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94789-160">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="94789-161">Eigenschaftenzuordnung von Windows Forms und WPF</span><span class="sxs-lookup"><span data-stu-id="94789-161">Windows Forms and WPF Property Mapping</span></span>](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)  
 [<span data-ttu-id="94789-162">WPF-Designer</span><span class="sxs-lookup"><span data-stu-id="94789-162">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [<span data-ttu-id="94789-163">Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="94789-163">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
