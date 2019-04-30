---
title: Erweiterbarkeit des Eigenschaftenrasters - WF-Beispiel
ms.date: 03/30/2017
ms.assetid: 3530c3a3-756d-4712-9f10-fb2897414d3a
ms.openlocfilehash: f1cb64cb10e8d88359e8f94b57602ab127314cff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004873"
---
# <a name="property-grid-extensibility"></a><span data-ttu-id="3b7da-102">Erweiterbarkeit des Eigenschaftenrasters</span><span class="sxs-lookup"><span data-stu-id="3b7da-102">Property grid extensibility</span></span>

<span data-ttu-id="3b7da-103">Entwickler können das Eigenschaftenraster anpassen, das bei Auswahl einer Aktivität im Designer angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="3b7da-103">A developer can customize the property grid that is displayed when a given activity is selected within the designer.</span></span> <span data-ttu-id="3b7da-104">Auf diese Weise lassen sich die Bearbeitungsmöglichkeiten optimieren.</span><span class="sxs-lookup"><span data-stu-id="3b7da-104">This can be done to create a rich editing experience.</span></span> <span data-ttu-id="3b7da-105">Dieses Beispiel veranschaulicht die Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="3b7da-105">This sample shows how this can be done.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="3b7da-106">Veranschaulicht</span><span class="sxs-lookup"><span data-stu-id="3b7da-106">Demonstrates</span></span>

<span data-ttu-id="3b7da-107">Erweiterbarkeit des Eigenschaftenrasters im Workflow-Designer.</span><span class="sxs-lookup"><span data-stu-id="3b7da-107">Workflow designer property grid extensibility.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3b7da-108">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="3b7da-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="3b7da-109">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="3b7da-109">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="3b7da-110">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="3b7da-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3b7da-111">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="3b7da-111">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\PropertyGridExtensibility`

## <a name="discussion"></a><span data-ttu-id="3b7da-112">Diskussion</span><span class="sxs-lookup"><span data-stu-id="3b7da-112">Discussion</span></span>

<span data-ttu-id="3b7da-113">Zur Erweiterung des Eigenschaftenrasters stehen Entwicklern Optionen zur Verfügung, mit denen sie die Darstellung des Eigenschaftenraster-Editors anpassen oder ein Dialogfeld bereitstellen können, das für eine erweiterte Entwurfsoberfläche angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="3b7da-113">To extend the property grid, a developer has options to customize the inline appearance of a property grid editor or provide a dialog that appears for a more advanced editing surface.</span></span> <span data-ttu-id="3b7da-114">In diesem Beispiel werden zwei verschiedene Editoren veranschaulicht, ein Inline-Editor und ein Dialog-Editor.</span><span class="sxs-lookup"><span data-stu-id="3b7da-114">There are two different editors demonstrated in this sample; an inline editor and a dialog editor.</span></span>

## <a name="inline-editor"></a><span data-ttu-id="3b7da-115">Inline-editor</span><span class="sxs-lookup"><span data-stu-id="3b7da-115">Inline editor</span></span>

<span data-ttu-id="3b7da-116">Das Beispiel zum Inline-Editor veranschaulicht Folgendes:</span><span class="sxs-lookup"><span data-stu-id="3b7da-116">The inline editor sample demonstrates the following:</span></span>

- <span data-ttu-id="3b7da-117">Ein von <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor> abgeleiteter Typ wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="3b7da-117">Creates a type that derives from <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor>.</span></span>

- <span data-ttu-id="3b7da-118">Im Konstruktor der <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> Wert mit einer Datenvorlage Windows Presentation Foundation (WPF) festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="3b7da-118">In the constructor, the <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> value is set with a Windows Presentation Foundation (WPF) data template.</span></span> <span data-ttu-id="3b7da-119">Diese kann an eine XAML-Vorlage gebunden werden, in diesem Beispiel wird jedoch Code zur Initialisierung der Datenbindung verwendet.</span><span class="sxs-lookup"><span data-stu-id="3b7da-119">This can be bound to a XAML template, but in this sample, code is used to initialize data binding.</span></span>

- <span data-ttu-id="3b7da-120">Die Datenvorlage weist einen Datenkontext für den <xref:System.Activities.Presentation.PropertyEditing.PropertyValue>-Wert des im Eigenschaftenraster gerenderten Elements auf.</span><span class="sxs-lookup"><span data-stu-id="3b7da-120">The data template has a data context of the <xref:System.Activities.Presentation.PropertyEditing.PropertyValue> of the item rendered in the property grid.</span></span> <span data-ttu-id="3b7da-121">Beachten Sie beim folgenden Code (aus der Datei "CustomInlineEditor.cs"), dass dieser Kontext dann an die `Value`-Eigenschaft gebunden wird.</span><span class="sxs-lookup"><span data-stu-id="3b7da-121">Note in the following code (from CustomInlineEditor.cs) that this context then binds to the `Value` property.</span></span>

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

- <span data-ttu-id="3b7da-122">Da die Aktivität und der Designer sich in derselben Assembly befinden, erfolgt die Registrierung der Aktivitätsdesignerattribute im statischen Konstruktor der Aktivität, wie im folgenden Beispiel aus der Datei „SimpleCodeActivity.cs“ gezeigt.</span><span class="sxs-lookup"><span data-stu-id="3b7da-122">Because the activity and the designer are in the same assembly, registration of the activity designer attributes are accomplished in the static constructor of the activity itself, as shown in the following example from SimpleCodeActivity.cs.</span></span>

    ```csharp
    static SimpleCodeActivity()
    {
        AttributeTableBuilder builder = new AttributeTableBuilder();
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "RepeatCount", new EditorAttribute(typeof(CustomInlineEditor), typeof(PropertyValueEditor)));
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "FileName", new EditorAttribute(typeof(FilePickerEditor), typeof(DialogPropertyValueEditor)));
        MetadataStore.AddAttributeTable(builder.CreateTable());
    }
    ```

## <a name="dialog-editor"></a><span data-ttu-id="3b7da-123">Dialog-Editor</span><span class="sxs-lookup"><span data-stu-id="3b7da-123">Dialog editor</span></span>

<span data-ttu-id="3b7da-124">Das Beispiel zum Dialog-Editor veranschaulicht Folgendes:</span><span class="sxs-lookup"><span data-stu-id="3b7da-124">The dialog editor sample demonstrates the following:</span></span>

1. <span data-ttu-id="3b7da-125">Ein von <xref:System.Activities.Presentation.PropertyEditing.DialogPropertyValueEditor> abgeleiteter Typ wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="3b7da-125">Creates a type that derives from <xref:System.Activities.Presentation.PropertyEditing.DialogPropertyValueEditor>.</span></span>

2. <span data-ttu-id="3b7da-126">Der <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A>-Wert im Konstruktor wird mit einer [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)]-Datenvorlage festgelegt.</span><span class="sxs-lookup"><span data-stu-id="3b7da-126">Sets the <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> value in the constructor with a [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] data template.</span></span> <span data-ttu-id="3b7da-127">Diese kann in XAML erstellt werden, in diesem Beispiel wird jedoch Code verwendet.</span><span class="sxs-lookup"><span data-stu-id="3b7da-127">This can be created in XAML, but in this sample, this is created in code.</span></span>

3. <span data-ttu-id="3b7da-128">Die Datenvorlage weist einen Datenkontext für den <xref:System.Activities.Presentation.PropertyEditing.PropertyValue>-Wert des im Eigenschaftenraster gerenderten Elements auf.</span><span class="sxs-lookup"><span data-stu-id="3b7da-128">The data template has a data context of the <xref:System.Activities.Presentation.PropertyEditing.PropertyValue> of the item rendered in the property grid.</span></span> <span data-ttu-id="3b7da-129">Im folgenden Code wird dieser dann an die `Value`-Eigenschaft gebunden.</span><span class="sxs-lookup"><span data-stu-id="3b7da-129">In the following code, this then binds to the `Value` property.</span></span> <span data-ttu-id="3b7da-130">Es muss auch ein <xref:System.Activities.Presentation.PropertyEditing.EditModeSwitchButton>-Element eingebunden werden, um die Schaltfläche bereitzustellen, mit der das Dialogfeld in "FilePickerEditor.cs" ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="3b7da-130">It is critical to also include an <xref:System.Activities.Presentation.PropertyEditing.EditModeSwitchButton> to provide the button that raises the dialog in FilePickerEditor.cs.</span></span>

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

4. <span data-ttu-id="3b7da-131">Überschreibt die <xref:System.Activities.Presentation.PropertyEditing.DialogPropertyValueEditor.ShowDialog%2A>-Methode im Designertyp zur Behandlung der Dialogfeldanzeige.</span><span class="sxs-lookup"><span data-stu-id="3b7da-131">Overrides the <xref:System.Activities.Presentation.PropertyEditing.DialogPropertyValueEditor.ShowDialog%2A> method in the designer type to handle the display of the dialog.</span></span> <span data-ttu-id="3b7da-132">In diesem Beispiel wird ein einfaches <xref:System.Windows.Forms.FileDialog> gezeigt.</span><span class="sxs-lookup"><span data-stu-id="3b7da-132">In this sample, a basic <xref:System.Windows.Forms.FileDialog> is shown.</span></span>

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

5. <span data-ttu-id="3b7da-133">Da die Aktivität und der Designer sich in derselben Assembly befinden, erfolgt die Registrierung der Aktivitätsdesignerattribute im statischen Konstruktor der Aktivität, wie im folgenden Beispiel aus der Datei „SimpleCodeActivity.cs“ gezeigt.</span><span class="sxs-lookup"><span data-stu-id="3b7da-133">Because the activity and the designer are in the same assembly, registration of the activity designer attributes are accomplished in the static constructor of the activity itself, as shown in the following example from SimpleCodeActivity.cs.</span></span>

    ```csharp
    static SimpleCodeActivity()
    {
        AttributeTableBuilder builder = new AttributeTableBuilder();
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "RepeatCount", new EditorAttribute(typeof(CustomInlineEditor), typeof(PropertyValueEditor)));
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "FileName", new EditorAttribute(typeof(FilePickerEditor), typeof(DialogPropertyValueEditor)));
        MetadataStore.AddAttributeTable(builder.CreateTable());
    }
    ```

## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="3b7da-134">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="3b7da-134">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="3b7da-135">Erstellen Sie die Projektmappe, und öffnen Sie dann "Workflow1.xaml".</span><span class="sxs-lookup"><span data-stu-id="3b7da-135">Build the solution, and then open Workflow1.xaml.</span></span>

2. <span data-ttu-id="3b7da-136">Ziehen Sie eine **SimpleCodeActivity** aus der Toolbox auf den designerzeichnungsbereich.</span><span class="sxs-lookup"><span data-stu-id="3b7da-136">Drag a **SimpleCodeActivity** from the toolbox onto the designer canvas.</span></span>

3. <span data-ttu-id="3b7da-137">Klicken Sie auf die **SimpleCodeActivity** und öffnen Sie dann das Eigenschaftenraster, ein Schieberegler-Steuerelement und ein Dateiauswahl-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="3b7da-137">Click the **SimpleCodeActivity** and then open the property grid where there is a slider control and a file picking control.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3b7da-138">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="3b7da-138">The samples may already be installed on your machine.</span></span> <span data-ttu-id="3b7da-139">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="3b7da-139">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="3b7da-140">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="3b7da-140">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3b7da-141">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="3b7da-141">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\PropertyGridExtensibility`