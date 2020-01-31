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
ms.openlocfilehash: 7ff4ff607ab70b55cda1e2c4736ff773d4907a22
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794120"
---
# <a name="walkthrough-mapping-properties-using-the-elementhost-control"></a><span data-ttu-id="fc99f-102">Exemplarische Vorgehensweise: Zuordnen von Eigenschaften mit dem ElementHost-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="fc99f-102">Walkthrough: Mapping Properties Using the ElementHost Control</span></span>

<span data-ttu-id="fc99f-103">In dieser exemplarischen Vorgehensweise wird gezeigt, wie Sie die <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>-Eigenschaft verwenden, um den entsprechenden Eigenschaften eines gehosteten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Elements Windows Forms Eigenschaften zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="fc99f-103">This walkthrough shows you how to use the <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> property to map Windows Forms properties to corresponding properties on a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element.</span></span>

<span data-ttu-id="fc99f-104">In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="fc99f-104">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="fc99f-105">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="fc99f-105">Creating the project.</span></span>

- <span data-ttu-id="fc99f-106">Definieren einer neuen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="fc99f-106">Defining a new property mapping.</span></span>

- <span data-ttu-id="fc99f-107">Entfernen einer standardmäßigen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="fc99f-107">Removing a default property mapping.</span></span>

- <span data-ttu-id="fc99f-108">Erweitern einer standardmäßigen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="fc99f-108">Extending a default property mapping.</span></span>

<span data-ttu-id="fc99f-109">Eine komplette Code Auflistung der Aufgaben, die in dieser exemplarischen Vorgehensweise veranschaulicht werden, finden [Sie unter Mapping Properties using the ElementHost Control Sample](https://go.microsoft.com/fwlink/?LinkID=160018).</span><span class="sxs-lookup"><span data-stu-id="fc99f-109">For a complete code listing of the tasks illustrated in this walkthrough, see [Mapping Properties Using the ElementHost Control Sample](https://go.microsoft.com/fwlink/?LinkID=160018).</span></span>

<span data-ttu-id="fc99f-110">Wenn Sie fertig sind, können Sie Windows Forms Eigenschaften den entsprechenden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaften für ein gehosteter Element zuordnen.</span><span class="sxs-lookup"><span data-stu-id="fc99f-110">When you are finished, you will be able to map Windows Forms properties to corresponding [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties on a hosted element.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fc99f-111">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="fc99f-111">Prerequisites</span></span>

<span data-ttu-id="fc99f-112">Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="fc99f-112">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="fc99f-113">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="fc99f-113">Visual Studio 2017</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="fc99f-114">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="fc99f-114">Creating the Project</span></span>

### <a name="to-create-the-project"></a><span data-ttu-id="fc99f-115">So erstellen Sie das Projekt</span><span class="sxs-lookup"><span data-stu-id="fc99f-115">To create the project</span></span>

1. <span data-ttu-id="fc99f-116">Erstellen Sie ein **Windows Forms App** -Projekt mit dem Namen `PropertyMappingWithElementHost`.</span><span class="sxs-lookup"><span data-stu-id="fc99f-116">Create a **Windows Forms App** project named `PropertyMappingWithElementHost`.</span></span>

2. <span data-ttu-id="fc99f-117">Fügen Sie in **Projektmappen-Explorer**Verweise auf die folgenden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Assemblys hinzu.</span><span class="sxs-lookup"><span data-stu-id="fc99f-117">In **Solution Explorer**, add references to the following [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assemblies.</span></span>

    - <span data-ttu-id="fc99f-118">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="fc99f-118">PresentationCore</span></span>

    - <span data-ttu-id="fc99f-119">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="fc99f-119">PresentationFramework</span></span>

    - <span data-ttu-id="fc99f-120">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="fc99f-120">WindowsBase</span></span>

    - <span data-ttu-id="fc99f-121">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="fc99f-121">WindowsFormsIntegration</span></span>

3. <span data-ttu-id="fc99f-122">Kopieren Sie den folgenden Code an den Anfang der Codedatei `Form1`.</span><span class="sxs-lookup"><span data-stu-id="fc99f-122">Copy the following code into the top of the `Form1` code file.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#10](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#10)]
     [!code-vb[PropertyMappingWithElementHost#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#10)]

4. <span data-ttu-id="fc99f-123">Öffnen Sie `Form1` im Windows Forms-Designer.</span><span class="sxs-lookup"><span data-stu-id="fc99f-123">Open `Form1` in the Windows Forms Designer.</span></span> <span data-ttu-id="fc99f-124">Doppelklicken Sie auf das Formular, um einen Ereignishandler für das <xref:System.Windows.Forms.Form.Load>-Ereignis hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="fc99f-124">Double-click the form to add an event handler for the <xref:System.Windows.Forms.Form.Load> event.</span></span>

5. <span data-ttu-id="fc99f-125">Kehren Sie zum Windows Forms-Designer zurück, und fügen Sie einen Ereignishandler für das <xref:System.Windows.Forms.Control.Resize>-Ereignis des Formulars hinzu.</span><span class="sxs-lookup"><span data-stu-id="fc99f-125">Return to the Windows Forms Designer and add an event handler for the form's <xref:System.Windows.Forms.Control.Resize> event.</span></span> <span data-ttu-id="fc99f-126">Weitere Informationen finden Sie unter Gewusst [wie: Erstellen von Ereignis Handlern mithilfe des Designers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="fc99f-126">For more information, see [How to: Create Event Handlers Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)).</span></span>

6. <span data-ttu-id="fc99f-127">Deklarieren Sie ein <xref:System.Windows.Forms.Integration.ElementHost> Feld in der `Form1`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="fc99f-127">Declare an <xref:System.Windows.Forms.Integration.ElementHost> field in the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#16](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#16)]
     [!code-vb[PropertyMappingWithElementHost#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#16)]

## <a name="defining-new-property-mappings"></a><span data-ttu-id="fc99f-128">Definieren neuer Eigenschaften Zuordnungen</span><span class="sxs-lookup"><span data-stu-id="fc99f-128">Defining New Property Mappings</span></span>

<span data-ttu-id="fc99f-129">Das <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement stellt mehrere Standardeigenschaften Zuordnungen bereit.</span><span class="sxs-lookup"><span data-stu-id="fc99f-129">The <xref:System.Windows.Forms.Integration.ElementHost> control provides several default property mappings.</span></span> <span data-ttu-id="fc99f-130">Sie fügen eine neue Eigenschaften Zuordnung hinzu, indem Sie die <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A>-Methode für die <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>des <xref:System.Windows.Forms.Integration.ElementHost> Steuer Elements aufrufen.</span><span class="sxs-lookup"><span data-stu-id="fc99f-130">You add a new property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control's <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span></span>

### <a name="to-define-new-property-mappings"></a><span data-ttu-id="fc99f-131">So definieren Sie neue Eigenschaften Zuordnungen</span><span class="sxs-lookup"><span data-stu-id="fc99f-131">To define new property mappings</span></span>

1. <span data-ttu-id="fc99f-132">Kopieren Sie den folgenden Code in die Definition für die `Form1`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="fc99f-132">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#12](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#12)]
     [!code-vb[PropertyMappingWithElementHost#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#12)]

     <span data-ttu-id="fc99f-133">Mit der `AddMarginMapping`-Methode wird eine neue Zuordnung für die <xref:System.Windows.Forms.Control.Margin%2A>-Eigenschaft hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="fc99f-133">The `AddMarginMapping` method adds a new mapping for the <xref:System.Windows.Forms.Control.Margin%2A> property.</span></span>

     <span data-ttu-id="fc99f-134">Die `OnMarginChange`-Methode übersetzt die <xref:System.Windows.Forms.Control.Margin%2A>-Eigenschaft in die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="fc99f-134">The `OnMarginChange` method translates the <xref:System.Windows.Forms.Control.Margin%2A> property to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> property.</span></span>

2. <span data-ttu-id="fc99f-135">Kopieren Sie den folgenden Code in die Definition für die `Form1`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="fc99f-135">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#14](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#14)]
     [!code-vb[PropertyMappingWithElementHost#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#14)]

     <span data-ttu-id="fc99f-136">Mit der `AddRegionMapping`-Methode wird eine neue Zuordnung für die <xref:System.Windows.Forms.Control.Region%2A>-Eigenschaft hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="fc99f-136">The `AddRegionMapping` method adds a new mapping for the <xref:System.Windows.Forms.Control.Region%2A> property.</span></span>

     <span data-ttu-id="fc99f-137">Die `OnRegionChange`-Methode übersetzt die <xref:System.Windows.Forms.Control.Region%2A>-Eigenschaft in die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="fc99f-137">The `OnRegionChange` method translates the <xref:System.Windows.Forms.Control.Region%2A> property to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> property.</span></span>

     <span data-ttu-id="fc99f-138">Die `Form1_Resize`-Methode behandelt das <xref:System.Windows.Forms.Control.Resize>-Ereignis des Formulars und passt die Größe des Clippingbereichs an das gehostete Element an.</span><span class="sxs-lookup"><span data-stu-id="fc99f-138">The `Form1_Resize` method handles the form's <xref:System.Windows.Forms.Control.Resize> event and sizes the clipping region to fit the hosted element.</span></span>

## <a name="removing-a-default-property-mapping"></a><span data-ttu-id="fc99f-139">Entfernen einer standardmäßigen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="fc99f-139">Removing a Default Property Mapping</span></span>

<span data-ttu-id="fc99f-140">Entfernen Sie eine standardmäßige Eigenschaften Zuordnung, indem Sie die <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A>-Methode für die <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>des <xref:System.Windows.Forms.Integration.ElementHost> Steuer Elements aufrufen.</span><span class="sxs-lookup"><span data-stu-id="fc99f-140">Remove a default property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control's <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span></span>

### <a name="to-remove-a-default-property-mapping"></a><span data-ttu-id="fc99f-141">Entfernen einer standardmäßigen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="fc99f-141">To remove a default property mapping</span></span>

- <span data-ttu-id="fc99f-142">Kopieren Sie den folgenden Code in die Definition für die `Form1`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="fc99f-142">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#13](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#13)]
     [!code-vb[PropertyMappingWithElementHost#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#13)]

     <span data-ttu-id="fc99f-143">Die `RemoveCursorMapping`-Methode löscht die Standard Zuordnung für die <xref:System.Windows.Forms.Control.Cursor%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="fc99f-143">The `RemoveCursorMapping` method deletes the default mapping for the <xref:System.Windows.Forms.Control.Cursor%2A> property.</span></span>

## <a name="extending-a-default-property-mapping"></a><span data-ttu-id="fc99f-144">Erweitern einer standardmäßigen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="fc99f-144">Extending a Default Property Mapping</span></span>

<span data-ttu-id="fc99f-145">Sie können auch eine standardmäßige Eigenschaftenzuordnung verwenden und sie um Ihre eigenen Zuordnung erweitern.</span><span class="sxs-lookup"><span data-stu-id="fc99f-145">You can use a default property mapping and also extend it with your own mapping.</span></span>

### <a name="to-extend-a-default-property-mapping"></a><span data-ttu-id="fc99f-146">So erweitern Sie eine standardmäßigen Eigenschaftenzuordnung</span><span class="sxs-lookup"><span data-stu-id="fc99f-146">To extend a default property mapping</span></span>

- <span data-ttu-id="fc99f-147">Kopieren Sie den folgenden Code in die Definition für die `Form1`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="fc99f-147">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#15](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#15)]
     [!code-vb[PropertyMappingWithElementHost#15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#15)]

     <span data-ttu-id="fc99f-148">Die `ExtendBackColorMapping`-Methode fügt der vorhandenen <xref:System.Windows.Forms.Control.BackColor%2A> Eigenschaften Zuordnung einen benutzerdefinierten Eigenschaften Übersetzer hinzu.</span><span class="sxs-lookup"><span data-stu-id="fc99f-148">The `ExtendBackColorMapping` method adds a custom property translator to the existing <xref:System.Windows.Forms.Control.BackColor%2A> property mapping.</span></span>

     <span data-ttu-id="fc99f-149">Die `OnBackColorChange`-Methode weist ein bestimmtes Bild der <xref:System.Windows.Controls.Control.Background%2A>-Eigenschaft des gehosteten Steuer Elements zu.</span><span class="sxs-lookup"><span data-stu-id="fc99f-149">The `OnBackColorChange` method assigns a specific image to the hosted control's <xref:System.Windows.Controls.Control.Background%2A> property.</span></span> <span data-ttu-id="fc99f-150">Die `OnBackColorChange`-Methode wird aufgerufen, nachdem die Standardeigenschaften Zuordnung angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="fc99f-150">The `OnBackColorChange` method is called after the default property mapping is applied.</span></span>

## <a name="initialize-your-property-mappings"></a><span data-ttu-id="fc99f-151">Eigenschafts Zuordnungen initialisieren</span><span class="sxs-lookup"><span data-stu-id="fc99f-151">Initialize your property mappings</span></span>

1. <span data-ttu-id="fc99f-152">Kopieren Sie den folgenden Code in die Definition für die `Form1`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="fc99f-152">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#11](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#11)]
     [!code-vb[PropertyMappingWithElementHost#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#11)]

     <span data-ttu-id="fc99f-153">Die `Form1_Load`-Methode behandelt das <xref:System.Windows.Forms.Form.Load>-Ereignis und führt die folgende Initialisierung aus.</span><span class="sxs-lookup"><span data-stu-id="fc99f-153">The `Form1_Load` method handles the <xref:System.Windows.Forms.Form.Load> event and performs the following initialization.</span></span>

    - <span data-ttu-id="fc99f-154">Erstellt eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button>-Elements.</span><span class="sxs-lookup"><span data-stu-id="fc99f-154">Creates a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> element.</span></span>

    - <span data-ttu-id="fc99f-155">Sie ruft die Methoden, die Sie zuvor in der exemplarischen Vorgehensweise definiert haben, auf, um die Eigenschaftenzuordnungen einzurichten.</span><span class="sxs-lookup"><span data-stu-id="fc99f-155">Calls the methods you defined earlier in the walkthrough to set up the property mappings.</span></span>

    - <span data-ttu-id="fc99f-156">Sie weist den zugeordneten Eigenschaften Anfangswerte zu.</span><span class="sxs-lookup"><span data-stu-id="fc99f-156">Assigns initial values to the mapped properties.</span></span>

2. <span data-ttu-id="fc99f-157">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="fc99f-157">Press F5 to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="fc99f-158">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc99f-158">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="fc99f-159">Eigenschaftenzuordnung von Windows Forms und WPF</span><span class="sxs-lookup"><span data-stu-id="fc99f-159">Windows Forms and WPF Property Mapping</span></span>](windows-forms-and-wpf-property-mapping.md)
- [<span data-ttu-id="fc99f-160">Entwerfen von XAML-Code in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fc99f-160">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="fc99f-161">Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fc99f-161">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
