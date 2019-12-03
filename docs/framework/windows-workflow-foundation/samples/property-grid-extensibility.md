---
title: 'Eigenschafts Raster-Erweiterbarkeit: WF-Beispiel'
ms.date: 03/30/2017
ms.assetid: 3530c3a3-756d-4712-9f10-fb2897414d3a
ms.openlocfilehash: 130d8702795bccf0d5f28b5c0940bd7c25be3556
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715606"
---
# <a name="property-grid-extensibility"></a><span data-ttu-id="454b4-102">Erweiterbarkeit von Eigenschaften Rastern</span><span class="sxs-lookup"><span data-stu-id="454b4-102">Property grid extensibility</span></span>

<span data-ttu-id="454b4-103">Entwickler können das Eigenschaftenraster anpassen, das bei Auswahl einer Aktivität im Designer angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="454b4-103">A developer can customize the property grid that is displayed when a given activity is selected within the designer.</span></span> <span data-ttu-id="454b4-104">Auf diese Weise lassen sich die Bearbeitungsmöglichkeiten optimieren.</span><span class="sxs-lookup"><span data-stu-id="454b4-104">This can be done to create a rich editing experience.</span></span> <span data-ttu-id="454b4-105">Dieses Beispiel veranschaulicht die Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="454b4-105">This sample shows how this can be done.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="454b4-106">Veranschaulicht</span><span class="sxs-lookup"><span data-stu-id="454b4-106">Demonstrates</span></span>

<span data-ttu-id="454b4-107">Erweiterbarkeit des Eigenschaftenrasters im Workflow-Designer.</span><span class="sxs-lookup"><span data-stu-id="454b4-107">Workflow designer property grid extensibility.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="454b4-108">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="454b4-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="454b4-109">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="454b4-109">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="454b4-110">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="454b4-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="454b4-111">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="454b4-111">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\PropertyGridExtensibility`

## <a name="discussion"></a><span data-ttu-id="454b4-112">Diskussion</span><span class="sxs-lookup"><span data-stu-id="454b4-112">Discussion</span></span>

<span data-ttu-id="454b4-113">Zur Erweiterung des Eigenschaftenrasters stehen Entwicklern Optionen zur Verfügung, mit denen sie die Darstellung des Eigenschaftenraster-Editors anpassen oder ein Dialogfeld bereitstellen können, das für eine erweiterte Entwurfsoberfläche angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="454b4-113">To extend the property grid, a developer has options to customize the inline appearance of a property grid editor or provide a dialog that appears for a more advanced editing surface.</span></span> <span data-ttu-id="454b4-114">In diesem Beispiel werden zwei verschiedene Editoren veranschaulicht, ein Inline-Editor und ein Dialog-Editor.</span><span class="sxs-lookup"><span data-stu-id="454b4-114">There are two different editors demonstrated in this sample; an inline editor and a dialog editor.</span></span>

## <a name="inline-editor"></a><span data-ttu-id="454b4-115">Inline-Editor</span><span class="sxs-lookup"><span data-stu-id="454b4-115">Inline editor</span></span>

<span data-ttu-id="454b4-116">Das Beispiel zum Inline-Editor veranschaulicht Folgendes:</span><span class="sxs-lookup"><span data-stu-id="454b4-116">The inline editor sample demonstrates the following:</span></span>

- <span data-ttu-id="454b4-117">Ein von <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor> abgeleiteter Typ wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="454b4-117">Creates a type that derives from <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor>.</span></span>

- <span data-ttu-id="454b4-118">Im Konstruktor wird der <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> Wert mit einer Windows Presentation Foundation (WPF)-Daten Vorlage festgelegt.</span><span class="sxs-lookup"><span data-stu-id="454b4-118">In the constructor, the <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> value is set with a Windows Presentation Foundation (WPF) data template.</span></span> <span data-ttu-id="454b4-119">Diese kann an eine XAML-Vorlage gebunden werden, in diesem Beispiel wird jedoch Code zur Initialisierung der Datenbindung verwendet.</span><span class="sxs-lookup"><span data-stu-id="454b4-119">This can be bound to a XAML template, but in this sample, code is used to initialize data binding.</span></span>

- <span data-ttu-id="454b4-120">Die Datenvorlage weist einen Datenkontext für den <xref:System.Activities.Presentation.PropertyEditing.PropertyValue>-Wert des im Eigenschaftenraster gerenderten Elements auf.</span><span class="sxs-lookup"><span data-stu-id="454b4-120">The data template has a data context of the <xref:System.Activities.Presentation.PropertyEditing.PropertyValue> of the item rendered in the property grid.</span></span> <span data-ttu-id="454b4-121">Beachten Sie beim folgenden Code (aus der Datei "CustomInlineEditor.cs"), dass dieser Kontext dann an die `Value`-Eigenschaft gebunden wird.</span><span class="sxs-lookup"><span data-stu-id="454b4-121">Note in the following code (from CustomInlineEditor.cs) that this context then binds to the `Value` property.</span></span>

    ```csharp
    FrameworkElementFactory stack = new FrameworkElementFactory(typeof(StackPanel));
    FrameworkElementFactory slider = new FrameworkElementFactory(typeof(Slider));
    Binding sliderBinding = new Binding("Value");
    sliderBinding.Mode = BindingMode.TwoWay;
    slider.SetValue(Slider.MinimumProperty, 0.0);
    slider.SetValue(Slider.MaximumProperty, 100.0);
    slider.SetValue(Slider.ValueProperty, sliderBinding);
    stack.AppendChild(slider);
    ```

- <span data-ttu-id="454b4-122">Da die Aktivität und der Designer sich in derselben Assembly befinden, erfolgt die Registrierung der Aktivitätsdesignerattribute im statischen Konstruktor der Aktivität, wie im folgenden Beispiel aus der Datei „SimpleCodeActivity.cs“ gezeigt.</span><span class="sxs-lookup"><span data-stu-id="454b4-122">Because the activity and the designer are in the same assembly, registration of the activity designer attributes are accomplished in the static constructor of the activity itself, as shown in the following example from SimpleCodeActivity.cs.</span></span>

    ```csharp
    static SimpleCodeActivity()
    {
        AttributeTableBuilder builder = new AttributeTableBuilder();
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "RepeatCount", new EditorAttribute(typeof(CustomInlineEditor), typeof(PropertyValueEditor)));
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "FileName", new EditorAttribute(typeof(FilePickerEditor), typeof(DialogPropertyValueEditor)));
        MetadataStore.AddAttributeTable(builder.CreateTable());
    }
    ```

## <a name="dialog-editor"></a><span data-ttu-id="454b4-123">Dialog-Editor</span><span class="sxs-lookup"><span data-stu-id="454b4-123">Dialog editor</span></span>

<span data-ttu-id="454b4-124">Das Beispiel zum Dialog-Editor veranschaulicht Folgendes:</span><span class="sxs-lookup"><span data-stu-id="454b4-124">The dialog editor sample demonstrates the following:</span></span>

1. <span data-ttu-id="454b4-125">Ein von <xref:System.Activities.Presentation.PropertyEditing.DialogPropertyValueEditor> abgeleiteter Typ wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="454b4-125">Creates a type that derives from <xref:System.Activities.Presentation.PropertyEditing.DialogPropertyValueEditor>.</span></span>

2. <span data-ttu-id="454b4-126">Legt den <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> Wert im Konstruktor mit einer WPF-Daten Vorlage fest.</span><span class="sxs-lookup"><span data-stu-id="454b4-126">Sets the <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> value in the constructor with a WPF data template.</span></span> <span data-ttu-id="454b4-127">Diese kann in XAML erstellt werden, in diesem Beispiel wird jedoch Code verwendet.</span><span class="sxs-lookup"><span data-stu-id="454b4-127">This can be created in XAML, but in this sample, this is created in code.</span></span>

3. <span data-ttu-id="454b4-128">Die Datenvorlage weist einen Datenkontext für den <xref:System.Activities.Presentation.PropertyEditing.PropertyValue>-Wert des im Eigenschaftenraster gerenderten Elements auf.</span><span class="sxs-lookup"><span data-stu-id="454b4-128">The data template has a data context of the <xref:System.Activities.Presentation.PropertyEditing.PropertyValue> of the item rendered in the property grid.</span></span> <span data-ttu-id="454b4-129">Im folgenden Code wird dieser dann an die `Value`-Eigenschaft gebunden.</span><span class="sxs-lookup"><span data-stu-id="454b4-129">In the following code, this then binds to the `Value` property.</span></span> <span data-ttu-id="454b4-130">Es muss auch ein <xref:System.Activities.Presentation.PropertyEditing.EditModeSwitchButton>-Element eingebunden werden, um die Schaltfläche bereitzustellen, mit der das Dialogfeld in "FilePickerEditor.cs" ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="454b4-130">It is critical to also include an <xref:System.Activities.Presentation.PropertyEditing.EditModeSwitchButton> to provide the button that raises the dialog in FilePickerEditor.cs.</span></span>

    ```csharp
    this.InlineEditorTemplate = new DataTemplate();

    FrameworkElementFactory stack = new FrameworkElementFactory(typeof(StackPanel));
    stack.SetValue(StackPanel.OrientationProperty, Orientation.Horizontal);
    FrameworkElementFactory label = new FrameworkElementFactory(typeof(Label));
    Binding labelBinding = new Binding("Value");
    label.SetValue(Label.ContentProperty, labelBinding);
    label.SetValue(Label.MaxWidthProperty, 90.0);

    stack.AppendChild(label);

    FrameworkElementFactory editModeSwitch = new FrameworkElementFactory(typeof(EditModeSwitchButton));

    editModeSwitch.SetValue(EditModeSwitchButton.TargetEditModeProperty, PropertyContainerEditMode.Dialog);

    stack.AppendChild(editModeSwitch);

    this.InlineEditorTemplate.VisualTree = stack;
    ```

4. <span data-ttu-id="454b4-131">Überschreibt die <xref:System.Activities.Presentation.PropertyEditing.DialogPropertyValueEditor.ShowDialog%2A>-Methode im Designertyp zur Behandlung der Dialogfeldanzeige.</span><span class="sxs-lookup"><span data-stu-id="454b4-131">Overrides the <xref:System.Activities.Presentation.PropertyEditing.DialogPropertyValueEditor.ShowDialog%2A> method in the designer type to handle the display of the dialog.</span></span> <span data-ttu-id="454b4-132">In diesem Beispiel wird ein einfaches <xref:System.Windows.Forms.FileDialog> gezeigt.</span><span class="sxs-lookup"><span data-stu-id="454b4-132">In this sample, a basic <xref:System.Windows.Forms.FileDialog> is shown.</span></span>

    ```csharp
    public override void ShowDialog(PropertyValue propertyValue, IInputElement commandSource)
    {
        Microsoft.Win32.OpenFileDialog ofd = new Microsoft.Win32.OpenFileDialog();
        if (ofd.ShowDialog() == true)
        {
            propertyValue.Value = ofd.FileName;
        }
    }
    ```

5. <span data-ttu-id="454b4-133">Da die Aktivität und der Designer sich in derselben Assembly befinden, erfolgt die Registrierung der Aktivitätsdesignerattribute im statischen Konstruktor der Aktivität, wie im folgenden Beispiel aus der Datei „SimpleCodeActivity.cs“ gezeigt.</span><span class="sxs-lookup"><span data-stu-id="454b4-133">Because the activity and the designer are in the same assembly, registration of the activity designer attributes are accomplished in the static constructor of the activity itself, as shown in the following example from SimpleCodeActivity.cs.</span></span>

    ```csharp
    static SimpleCodeActivity()
    {
        AttributeTableBuilder builder = new AttributeTableBuilder();
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "RepeatCount", new EditorAttribute(typeof(CustomInlineEditor), typeof(PropertyValueEditor)));
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "FileName", new EditorAttribute(typeof(FilePickerEditor), typeof(DialogPropertyValueEditor)));
        MetadataStore.AddAttributeTable(builder.CreateTable());
    }
    ```

## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="454b4-134">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="454b4-134">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="454b4-135">Erstellen Sie die Projektmappe, und öffnen Sie dann "Workflow1.xaml".</span><span class="sxs-lookup"><span data-stu-id="454b4-135">Build the solution, and then open Workflow1.xaml.</span></span>

2. <span data-ttu-id="454b4-136">Ziehen Sie eine **simplecodeactivity** aus der Toolbox auf den Designer.</span><span class="sxs-lookup"><span data-stu-id="454b4-136">Drag a **SimpleCodeActivity** from the toolbox onto the designer canvas.</span></span>

3. <span data-ttu-id="454b4-137">Klicken Sie auf **simplecodeactivity** , und öffnen Sie dann das Eigenschaften Raster, in dem ein Schieberegler-Steuerelement und ein Dateiauswahl-Steuerelement vorhanden sind</span><span class="sxs-lookup"><span data-stu-id="454b4-137">Click the **SimpleCodeActivity** and then open the property grid where there is a slider control and a file picking control.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="454b4-138">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="454b4-138">The samples may already be installed on your machine.</span></span> <span data-ttu-id="454b4-139">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="454b4-139">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="454b4-140">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="454b4-140">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="454b4-141">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="454b4-141">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\PropertyGridExtensibility`
