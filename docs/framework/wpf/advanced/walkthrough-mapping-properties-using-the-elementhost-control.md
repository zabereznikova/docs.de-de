---
title: 'Exemplarische Vorgehensweise: Zuordnen von Eigenschaften mit dem ElementHost-Steuerelement'
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- ElementHost control [WPF], mapping properties
ms.assetid: bccd6e0d-2272-4924-9107-ff8ed58b88aa
ms.openlocfilehash: 360f19e558f97e1807b329ad18e429fa893bbf86
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59300917"
---
# <a name="walkthrough-mapping-properties-using-the-elementhost-control"></a><span data-ttu-id="7d438-102">Exemplarische Vorgehensweise: Zuordnen von Eigenschaften mit dem ElementHost-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="7d438-102">Walkthrough: Mapping Properties Using the ElementHost Control</span></span>

<span data-ttu-id="7d438-103">In dieser exemplarischen Vorgehensweise erfahren Sie, wie Sie mit der <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> zuzuordnenden Eigenschaft [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Eigenschaften den entsprechenden Eigenschaften eines gehosteten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Element.</span><span class="sxs-lookup"><span data-stu-id="7d438-103">This walkthrough shows you how to use the <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> property to map [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element.</span></span>

<span data-ttu-id="7d438-104">In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="7d438-104">Tasks illustrated in this walkthrough include:</span></span>

-   <span data-ttu-id="7d438-105">Erstellen des Projekts.</span><span class="sxs-lookup"><span data-stu-id="7d438-105">Creating the project.</span></span>

-   <span data-ttu-id="7d438-106">Definieren einer neuen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="7d438-106">Defining a new property mapping.</span></span>

-   <span data-ttu-id="7d438-107">Entfernen einer standardmäßigen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="7d438-107">Removing a default property mapping.</span></span>

-   <span data-ttu-id="7d438-108">Erweitern einer standardmäßigen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="7d438-108">Extending a default property mapping.</span></span>

<span data-ttu-id="7d438-109">Eine vollständige codeauflistung der Aufgaben in dieser exemplarischen Vorgehensweise veranschaulicht, finden Sie unter [Zuordnen von Eigenschaften mit dem ElementHost-Steuerelement-Beispiel](https://go.microsoft.com/fwlink/?LinkID=160018).</span><span class="sxs-lookup"><span data-stu-id="7d438-109">For a complete code listing of the tasks illustrated in this walkthrough, see [Mapping Properties Using the ElementHost Control Sample](https://go.microsoft.com/fwlink/?LinkID=160018).</span></span>

<span data-ttu-id="7d438-110">Wenn Sie fertig sind, Sie werden zum Zuordnen [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Eigenschaften entsprechenden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaften eines gehosteten Elements.</span><span class="sxs-lookup"><span data-stu-id="7d438-110">When you are finished, you will be able to map [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] properties to corresponding [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties on a hosted element.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7d438-111">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="7d438-111">Prerequisites</span></span>

<span data-ttu-id="7d438-112">Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="7d438-112">You need the following components to complete this walkthrough:</span></span>

-   <span data-ttu-id="7d438-113">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="7d438-113">Visual Studio 2017</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="7d438-114">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="7d438-114">Creating the Project</span></span>

### <a name="to-create-the-project"></a><span data-ttu-id="7d438-115">So erstellen Sie das Projekt</span><span class="sxs-lookup"><span data-stu-id="7d438-115">To create the project</span></span>

1. <span data-ttu-id="7d438-116">Erstellen Sie eine **Windows Forms-App** Projekt mit dem Namen `PropertyMappingWithElementHost`.</span><span class="sxs-lookup"><span data-stu-id="7d438-116">Create a **Windows Forms App** project named `PropertyMappingWithElementHost`.</span></span>

2. <span data-ttu-id="7d438-117">In **Projektmappen-Explorer**, fügen Sie Verweise auf die folgenden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Assemblys.</span><span class="sxs-lookup"><span data-stu-id="7d438-117">In **Solution Explorer**, add references to the following [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assemblies.</span></span>

    -   <span data-ttu-id="7d438-118">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="7d438-118">PresentationCore</span></span>

    -   <span data-ttu-id="7d438-119">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="7d438-119">PresentationFramework</span></span>

    -   <span data-ttu-id="7d438-120">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="7d438-120">WindowsBase</span></span>

    -   <span data-ttu-id="7d438-121">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="7d438-121">WindowsFormsIntegration</span></span>

3. <span data-ttu-id="7d438-122">Kopieren Sie den folgenden Code oben in der `Form1` Codedatei.</span><span class="sxs-lookup"><span data-stu-id="7d438-122">Copy the following code into the top of the `Form1` code file.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#10](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#10)]
     [!code-vb[PropertyMappingWithElementHost#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#10)]

4. <span data-ttu-id="7d438-123">Öffnen Sie `Form1` im Windows Forms-Designer.</span><span class="sxs-lookup"><span data-stu-id="7d438-123">Open `Form1` in the Windows Forms Designer.</span></span> <span data-ttu-id="7d438-124">Doppelklicken Sie auf das Formular, um das Hinzufügen eines ereignishandlers für das <xref:System.Windows.Forms.Form.Load> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="7d438-124">Double-click the form to add an event handler for the <xref:System.Windows.Forms.Form.Load> event.</span></span>

5. <span data-ttu-id="7d438-125">Zurück zu den Windows Forms-Designer, und fügen Sie einen Ereignishandler für des Formulars des <xref:System.Windows.Forms.Control.Resize> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="7d438-125">Return to the Windows Forms Designer and add an event handler for the form's <xref:System.Windows.Forms.Control.Resize> event.</span></span> <span data-ttu-id="7d438-126">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von Ereignishandlern mithilfe des Designers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="7d438-126">For more information, see [How to: Create Event Handlers Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)).</span></span>

6. <span data-ttu-id="7d438-127">Deklarieren Sie eine <xref:System.Windows.Forms.Integration.ElementHost> -Feld in der `Form1` Klasse.</span><span class="sxs-lookup"><span data-stu-id="7d438-127">Declare an <xref:System.Windows.Forms.Integration.ElementHost> field in the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#16](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#16)]
     [!code-vb[PropertyMappingWithElementHost#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#16)]

## <a name="defining-new-property-mappings"></a><span data-ttu-id="7d438-128">Definieren neue Eigenschaftenzuordnungen</span><span class="sxs-lookup"><span data-stu-id="7d438-128">Defining New Property Mappings</span></span>

<span data-ttu-id="7d438-129">Die <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement bietet mehrere Standard-eigenschaftenzuordnungen.</span><span class="sxs-lookup"><span data-stu-id="7d438-129">The <xref:System.Windows.Forms.Integration.ElementHost> control provides several default property mappings.</span></span> <span data-ttu-id="7d438-130">Hinzufügen eine neuen eigenschaftenzuordnung durch den Aufruf der <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> Methode für die <xref:System.Windows.Forms.Integration.ElementHost> des Steuerelements <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span><span class="sxs-lookup"><span data-stu-id="7d438-130">You add a new property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control's <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span></span>

### <a name="to-define-new-property-mappings"></a><span data-ttu-id="7d438-131">Definieren Sie neue eigenschaftenzuordnungen</span><span class="sxs-lookup"><span data-stu-id="7d438-131">To define new property mappings</span></span>

1. <span data-ttu-id="7d438-132">Kopieren Sie den folgenden Code in die Definition der `Form1` Klasse.</span><span class="sxs-lookup"><span data-stu-id="7d438-132">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#12](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#12)]
     [!code-vb[PropertyMappingWithElementHost#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#12)]

     <span data-ttu-id="7d438-133">Die `AddMarginMapping` Methode fügt eine neue Zuordnung für die <xref:System.Windows.Forms.Control.Margin%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="7d438-133">The `AddMarginMapping` method adds a new mapping for the <xref:System.Windows.Forms.Control.Margin%2A> property.</span></span>

     <span data-ttu-id="7d438-134">Die `OnMarginChange` -Methode übersetzt die <xref:System.Windows.Forms.Control.Margin%2A> Eigenschaft, um die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="7d438-134">The `OnMarginChange` method translates the <xref:System.Windows.Forms.Control.Margin%2A> property to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> property.</span></span>

2. <span data-ttu-id="7d438-135">Kopieren Sie den folgenden Code in die Definition der `Form1` Klasse.</span><span class="sxs-lookup"><span data-stu-id="7d438-135">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#14](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#14)]
     [!code-vb[PropertyMappingWithElementHost#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#14)]

     <span data-ttu-id="7d438-136">Die `AddRegionMapping` Methode fügt eine neue Zuordnung für die <xref:System.Windows.Forms.Control.Region%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="7d438-136">The `AddRegionMapping` method adds a new mapping for the <xref:System.Windows.Forms.Control.Region%2A> property.</span></span>

     <span data-ttu-id="7d438-137">Die `OnRegionChange` -Methode übersetzt die <xref:System.Windows.Forms.Control.Region%2A> Eigenschaft, um die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="7d438-137">The `OnRegionChange` method translates the <xref:System.Windows.Forms.Control.Region%2A> property to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> property.</span></span>

     <span data-ttu-id="7d438-138">Die `Form1_Resize` Methode verarbeitet des Formulars <xref:System.Windows.Forms.Control.Resize> Ereignis und passt die Größe des Clippingbereichs an das gehostete Element passt.</span><span class="sxs-lookup"><span data-stu-id="7d438-138">The `Form1_Resize` method handles the form's <xref:System.Windows.Forms.Control.Resize> event and sizes the clipping region to fit the hosted element.</span></span>

## <a name="removing-a-default-property-mapping"></a><span data-ttu-id="7d438-139">Entfernen einer standardmäßigen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="7d438-139">Removing a Default Property Mapping</span></span>

<span data-ttu-id="7d438-140">Entfernen eine standardmäßigen eigenschaftenzuordnung durch Aufrufen der <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> Methode für die <xref:System.Windows.Forms.Integration.ElementHost> des Steuerelements <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span><span class="sxs-lookup"><span data-stu-id="7d438-140">Remove a default property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control's <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span></span>

### <a name="to-remove-a-default-property-mapping"></a><span data-ttu-id="7d438-141">Entfernen einer standardmäßigen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="7d438-141">To remove a default property mapping</span></span>

-   <span data-ttu-id="7d438-142">Kopieren Sie den folgenden Code in die Definition der `Form1` Klasse.</span><span class="sxs-lookup"><span data-stu-id="7d438-142">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#13](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#13)]
     [!code-vb[PropertyMappingWithElementHost#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#13)]

     <span data-ttu-id="7d438-143">Die `RemoveCursorMapping` -Methode löscht die standardzuordnung für die <xref:System.Windows.Forms.Control.Cursor%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="7d438-143">The `RemoveCursorMapping` method deletes the default mapping for the <xref:System.Windows.Forms.Control.Cursor%2A> property.</span></span>

## <a name="extending-a-default-property-mapping"></a><span data-ttu-id="7d438-144">Erweitern einer standardmäßigen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="7d438-144">Extending a Default Property Mapping</span></span>

<span data-ttu-id="7d438-145">Sie können auch eine standardmäßige Eigenschaftenzuordnung verwenden und sie um Ihre eigenen Zuordnung erweitern.</span><span class="sxs-lookup"><span data-stu-id="7d438-145">You can use a default property mapping and also extend it with your own mapping.</span></span>

### <a name="to-extend-a-default-property-mapping"></a><span data-ttu-id="7d438-146">So erweitern Sie eine standardmäßigen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="7d438-146">To extend a default property mapping</span></span>

-   <span data-ttu-id="7d438-147">Kopieren Sie den folgenden Code in die Definition der `Form1` Klasse.</span><span class="sxs-lookup"><span data-stu-id="7d438-147">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#15](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#15)]
     [!code-vb[PropertyMappingWithElementHost#15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#15)]

     <span data-ttu-id="7d438-148">Die `ExtendBackColorMapping` Methode fügt einen benutzerdefinierten Eigenschaftenübersetzer zur vorhandenen <xref:System.Windows.Forms.Control.BackColor%2A> eigenschaftenzuordnung.</span><span class="sxs-lookup"><span data-stu-id="7d438-148">The `ExtendBackColorMapping` method adds a custom property translator to the existing <xref:System.Windows.Forms.Control.BackColor%2A> property mapping.</span></span>

     <span data-ttu-id="7d438-149">Die `OnBackColorChange` Methode weist ein bestimmtes Bild des gehosteten Steuerelements <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="7d438-149">The `OnBackColorChange` method assigns a specific image to the hosted control's <xref:System.Windows.Controls.Control.Background%2A> property.</span></span> <span data-ttu-id="7d438-150">Die `OnBackColorChange` Methode wird aufgerufen, nachdem die standardzuordnung angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="7d438-150">The `OnBackColorChange` method is called after the default property mapping is applied.</span></span>

## <a name="initialize-your-property-mappings"></a><span data-ttu-id="7d438-151">Initialisieren Sie Ihre eigenschaftenzuordnungen</span><span class="sxs-lookup"><span data-stu-id="7d438-151">Initialize your property mappings</span></span>

1. <span data-ttu-id="7d438-152">Kopieren Sie den folgenden Code in die Definition der `Form1` Klasse.</span><span class="sxs-lookup"><span data-stu-id="7d438-152">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#11](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#11)]
     [!code-vb[PropertyMappingWithElementHost#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#11)]

     <span data-ttu-id="7d438-153">Die `Form1_Load` verarbeitet die <xref:System.Windows.Forms.Form.Load> Ereignis und führt die folgende Initialisierung.</span><span class="sxs-lookup"><span data-stu-id="7d438-153">The `Form1_Load` method handles the <xref:System.Windows.Forms.Form.Load> event and performs the following initialization.</span></span>

    -   <span data-ttu-id="7d438-154">Erstellt eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> Element.</span><span class="sxs-lookup"><span data-stu-id="7d438-154">Creates a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> element.</span></span>

    -   <span data-ttu-id="7d438-155">Sie ruft die Methoden, die Sie zuvor in der exemplarischen Vorgehensweise definiert haben, auf, um die Eigenschaftenzuordnungen einzurichten.</span><span class="sxs-lookup"><span data-stu-id="7d438-155">Calls the methods you defined earlier in the walkthrough to set up the property mappings.</span></span>

    -   <span data-ttu-id="7d438-156">Sie weist den zugeordneten Eigenschaften Anfangswerte zu.</span><span class="sxs-lookup"><span data-stu-id="7d438-156">Assigns initial values to the mapped properties.</span></span>

2. <span data-ttu-id="7d438-157">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7d438-157">Press F5 to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="7d438-158">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7d438-158">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="7d438-159">Eigenschaftenzuordnung von Windows Forms und WPF</span><span class="sxs-lookup"><span data-stu-id="7d438-159">Windows Forms and WPF Property Mapping</span></span>](windows-forms-and-wpf-property-mapping.md)
- [<span data-ttu-id="7d438-160">Entwerfen von XAML-Code in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7d438-160">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="7d438-161">Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7d438-161">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)