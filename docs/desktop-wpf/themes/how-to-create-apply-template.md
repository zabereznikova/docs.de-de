---
title: 'Erstellen einer Vorlage in WPF: .NET-Desktop'
description: In diesem Artikel erfahren Sie, wie Sie eine Vorlage für ein Steuerelement in Windows Presentation Foundation und .NET Core erstellen und darauf verweisen.
author: thraka
ms.author: adegeo
ms.date: 11/15/2019
no-loc:
- <Window>
- <ControlTemplate>
- <Ellipse>
- <ContentPresenter>
- <Trigger>
- <Setter>
- <PropertyTrigger>
- <Grid>
- <VisualStateManager.VisualStateGroups>
- <VisualStateGroup>
- <VisualState>
- <Storyboard>
- SizeToContent
- MinWidth
- TargetType
- Title
helpviewer_keywords:
- control contract [WPF]
- controls [WPF], visual structure changes
- ControlTemplate [WPF], customizing for existing controls
- skinning controls [WPF]
- controls [WPF], appearance specified by state
- templates [WPF], custom for existing controls
ms.openlocfilehash: c901864d387b8de976bbfa9a9b3c14a7d5a0b4d8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "81432539"
---
# <a name="create-a-template-for-a-control"></a><span data-ttu-id="e7517-103">Erstellen einer Vorlage für ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="e7517-103">Create a template for a control</span></span>

<span data-ttu-id="e7517-104">Mit Windows Presentation Foundation (WPF) können Sie die visuelle Struktur und das Verhalten eines vorhandenen Steuerelements mit Ihrer eigenen wiederverwendbaren Vorlage anpassen.</span><span class="sxs-lookup"><span data-stu-id="e7517-104">With Windows Presentation Foundation (WPF), you can customize an existing control's visual structure and behavior with your own reusable template.</span></span> <span data-ttu-id="e7517-105">Vorlagen können global auf Anwendungen, Fenster und Seiten oder direkt auf Steuerelemente angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="e7517-105">Templates can be applied globally to your application, windows and pages, or directly to controls.</span></span> <span data-ttu-id="e7517-106">Die meisten Szenarien, in denen Sie ein neues Steuerelement erstellen müssen, können stattdessen durch Erstellen einer neuen Vorlage für ein vorhandenes Steuerelement abgedeckt werden.</span><span class="sxs-lookup"><span data-stu-id="e7517-106">Most scenarios that require you to create a new control can be covered by instead creating a new template for an existing control.</span></span>

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

<span data-ttu-id="e7517-107">In diesem Artikel erfahren Sie, wie Sie eine neue <xref:System.Windows.Controls.ControlTemplate> für das <xref:System.Windows.Controls.Button>-Steuerelement erstellen.</span><span class="sxs-lookup"><span data-stu-id="e7517-107">In this article, you'll explore creating a new <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>

## <a name="when-to-create-a-controltemplate"></a><span data-ttu-id="e7517-108">Wann sollte eine ControlTemplate erstellt werden?</span><span class="sxs-lookup"><span data-stu-id="e7517-108">When to create a ControlTemplate</span></span>

<span data-ttu-id="e7517-109">Steuerelemente verfügen über viele Eigenschaften, etwa über <xref:System.Windows.Controls.Border.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A> und <xref:System.Windows.Controls.Control.FontFamily%2A>.</span><span class="sxs-lookup"><span data-stu-id="e7517-109">Controls have many properties, such as <xref:System.Windows.Controls.Border.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>, and <xref:System.Windows.Controls.Control.FontFamily%2A>.</span></span> <span data-ttu-id="e7517-110">Diese Eigenschaften steuern verschiedene Aspekte der Darstellung des Steuerelements, aber die Änderungen, die Sie vornehmen können, indem Sie diese Eigenschaften festlegen, sind eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="e7517-110">These properties control different aspects of the control's appearance, but the changes that you can make by setting these properties are limited.</span></span> <span data-ttu-id="e7517-111">Beispielsweise können Sie die <xref:System.Windows.Controls.Control.Foreground%2A>-Eigenschaft auf „Blue“ festlegen und <xref:System.Windows.Controls.Control.FontStyle%2A> für ein <xref:System.Windows.Controls.CheckBox>-Element auf kursiv.</span><span class="sxs-lookup"><span data-stu-id="e7517-111">For example, you can set the <xref:System.Windows.Controls.Control.Foreground%2A> property to blue and <xref:System.Windows.Controls.Control.FontStyle%2A> to italic on a <xref:System.Windows.Controls.CheckBox>.</span></span> <span data-ttu-id="e7517-112">Sie erstellen eine <xref:System.Windows.Controls.ControlTemplate>, wenn Sie die Darstellung des Steuerelements über das hinaus ändern möchten, was durch das Festlegen anderer Steuerelementeigenschaften möglich ist.</span><span class="sxs-lookup"><span data-stu-id="e7517-112">When you want to customize the control's appearance beyond what setting the other properties on the control can do, you create a <xref:System.Windows.Controls.ControlTemplate>.</span></span>

<span data-ttu-id="e7517-113">In den meisten Benutzeroberflächen weis eine Schaltfläche dieselbe allgemeine Darstellung auf: ein Rechteck mit Text.</span><span class="sxs-lookup"><span data-stu-id="e7517-113">In most user interfaces, a button has the same general appearance: a rectangle with some text.</span></span> <span data-ttu-id="e7517-114">Wenn Sie eine abgerundete Schaltfläche erstellen möchten, können Sie ein neues Steuerelement erstellen, das von der Schaltfläche erbt oder die Funktionalität der Schaltfläche neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="e7517-114">If you wanted to create a rounded button, you could create a new control that inherits from the button or recreates the functionality of the button.</span></span> <span data-ttu-id="e7517-115">Außerdem würde das neue Benutzersteuerelement das abgerundete visuelle Element bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e7517-115">In addition, the new user control would provide the circular visual.</span></span>

<span data-ttu-id="e7517-116">Sie können vermeiden, neue Steuerelemente zu erstellen, indem Sie das visuelle Layout eines vorhandenen Steuerelements anpassen.</span><span class="sxs-lookup"><span data-stu-id="e7517-116">You can avoid creating new controls by customizing the visual layout of an existing control.</span></span> <span data-ttu-id="e7517-117">Mit einer abgerundeten Schaltfläche erstellen Sie eine <xref:System.Windows.Controls.ControlTemplate> mit dem gewünschten visuellen Layout.</span><span class="sxs-lookup"><span data-stu-id="e7517-117">With a rounded button, you create a <xref:System.Windows.Controls.ControlTemplate> with the desired visual layout.</span></span>

<span data-ttu-id="e7517-118">Wenn Sie jedoch ein Steuerelement mit neuen Funktionen, anderen Eigenschaften und neuen Einstellungen benötigen, erstellen Sie ein neues <xref:System.Windows.Controls.UserControl>-Element.</span><span class="sxs-lookup"><span data-stu-id="e7517-118">On the other hand, if you need a control with new functionality, different properties, and new settings, you would create a new <xref:System.Windows.Controls.UserControl>.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e7517-119">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="e7517-119">Prerequisites</span></span>

<span data-ttu-id="e7517-120">Erstellen Sie eine neue WPF-Anwendung, und legen Sie in *MainWindow.xaml* (oder in einem anderen Fenster Ihrer Wahl) die folgenden Eigenschaften für das **\<Window>** -Element fest:</span><span class="sxs-lookup"><span data-stu-id="e7517-120">Create a new WPF application and in *MainWindow.xaml* (or another window of your choice) set the following properties on the **\<Window>** element:</span></span>

|     |     |
| --- | --- |
| **[!OP.NO-LOC(Title)]**         | `Template Intro Sample` |
| **[!OP.NO-LOC(SizeToContent)]** | `WidthAndHeight` |
| **[!OP.NO-LOC(MinWidth)]**      | `250` |

<span data-ttu-id="e7517-121">Legen Sie den Inhalt der **\<Window>** -Elements auf den folgenden XAML-Code fest:</span><span class="sxs-lookup"><span data-stu-id="e7517-121">Set the content of the **\<Window>** element to the following XAML:</span></span>

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

<span data-ttu-id="e7517-122">Schließlich sollte die Datei *MainWindow.xaml* ähnlich wie im Folgenden aussehen:</span><span class="sxs-lookup"><span data-stu-id="e7517-122">In the end, the *MainWindow.xaml* file should look similar to the following:</span></span>

[!code-xaml[InitialWhole](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#InitialWhole)]

<span data-ttu-id="e7517-123">Wenn Sie die Anwendung ausführen, sieht dies wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="e7517-123">If you run the application, it looks like the following:</span></span>

![WPF-Fenster mit zwei Schaltflächen ohne Stilangabe](media/create-apply-template/unstyled-button.png)

## <a name="create-a-controltemplate"></a><span data-ttu-id="e7517-125">Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="e7517-125">Create a ControlTemplate</span></span>

<span data-ttu-id="e7517-126">Eine <xref:System.Windows.Controls.ControlTemplate> wird üblicherweise deklariert, indem sie im Abschnitt `Resources` einer XAML-Datei als Ressource deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="e7517-126">The most common way to declare a <xref:System.Windows.Controls.ControlTemplate> is as a resource in the `Resources` section in a XAML file.</span></span> <span data-ttu-id="e7517-127">Da es sich bei Vorlagen um Ressourcen handelt, unterliegen sie denselben Gültigkeitsbereichsregeln, die für alle Ressourcen gelten.</span><span class="sxs-lookup"><span data-stu-id="e7517-127">Because templates are resources, they obey the same scoping rules that apply to all resources.</span></span> <span data-ttu-id="e7517-128">Einfach ausgedrückt: Wo Sie eine Vorlage deklarieren, wirkt sich darauf aus, wo die Vorlage angewendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="e7517-128">Put simply, where you declare a template affects where the template can be applied.</span></span> <span data-ttu-id="e7517-129">Wenn Sie die Vorlage beispielsweise im Stammelement der XAML-Anwendungsdefinitionsdatei deklarieren, kann die Vorlage überall in Ihrer Anwendung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e7517-129">For example, if you declare the template in the root element of your application definition XAML file, the template can be used anywhere in your application.</span></span> <span data-ttu-id="e7517-130">Wenn Sie die Vorlage in einem Fenster definieren, können nur die Steuerelemente in diesem Fenster die Vorlage verwenden.</span><span class="sxs-lookup"><span data-stu-id="e7517-130">If you define the template in a window, only the controls in that window can use the template.</span></span>

<span data-ttu-id="e7517-131">Fügen Sie zunächst der Datei *MainWindow.xaml* ein `Window.Resources`-Element hinzu:</span><span class="sxs-lookup"><span data-stu-id="e7517-131">To start with, add a `Window.Resources` element to your *MainWindow.xaml* file:</span></span>

[!code-xaml[WindowResStart](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window2.xaml#WindowResStart)]

<span data-ttu-id="e7517-132">Erstellen Sie eine neue **\<ControlTemplate** mit den folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="e7517-132">Create a new **\<ControlTemplate>** with the following properties set:</span></span>

|     |     |
| --- | --- |
| <span data-ttu-id="e7517-133">**x:Key**</span><span class="sxs-lookup"><span data-stu-id="e7517-133">**x:Key**</span></span>         | `roundbutton` |
| **TargetType**    | `Button` |

<span data-ttu-id="e7517-134">Diese Steuerelementvorlage ist einfach:</span><span class="sxs-lookup"><span data-stu-id="e7517-134">This control template will be simple:</span></span>

- <span data-ttu-id="e7517-135">ein Stammelement für das-Steuerelement, ein <xref:System.Windows.Controls.Grid></span><span class="sxs-lookup"><span data-stu-id="e7517-135">a root element for the control, a <xref:System.Windows.Controls.Grid></span></span>
- <span data-ttu-id="e7517-136">ein <xref:System.Windows.Shapes.Ellipse>-Element, um das abgerundete Aussehen der Schaltfläche zu zeichnen</span><span class="sxs-lookup"><span data-stu-id="e7517-136">an <xref:System.Windows.Shapes.Ellipse> to draw the rounded appearance of the button</span></span>
- <span data-ttu-id="e7517-137">ein <xref:System.Windows.Controls.ContentPresenter>-Element, um den benutzerdefinierten Schaltflächeninhalt anzuzeigen</span><span class="sxs-lookup"><span data-stu-id="e7517-137">a <xref:System.Windows.Controls.ContentPresenter> to display the user-specified button content</span></span>

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#ControlTemplate)]

### <a name="templatebinding"></a><span data-ttu-id="e7517-138">TemplateBinding</span><span class="sxs-lookup"><span data-stu-id="e7517-138">TemplateBinding</span></span>

<span data-ttu-id="e7517-139">Beim Erstellen einer neuen <xref:System.Windows.Controls.ControlTemplate> können Sie weiterhin die öffentlichen Eigenschaften verwenden, um die Darstellung der Steuerelemente anzupassen.</span><span class="sxs-lookup"><span data-stu-id="e7517-139">When you create a new <xref:System.Windows.Controls.ControlTemplate>, you still might want to use the public properties to change the control's appearance.</span></span> <span data-ttu-id="e7517-140">Die [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md)-Markuperweiterung bindet eine Eigenschaft eines in der <xref:System.Windows.Controls.ControlTemplate> enthaltenen Elements an eine vom Steuerelement definierte öffentliche Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e7517-140">The [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) markup extension binds a property of an element that is in the <xref:System.Windows.Controls.ControlTemplate> to a public property that is defined by the control.</span></span> <span data-ttu-id="e7517-141">Bei Verwendung einer [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) können Steuerelementeigenschaften als Parameter der Vorlage fungieren.</span><span class="sxs-lookup"><span data-stu-id="e7517-141">When you use a [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md), you enable properties on the control to act as parameters to the template.</span></span> <span data-ttu-id="e7517-142">D.h., beim Festlegen einer Steuerelementeigenschaft wird dieser Wert an das Element mit [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) übergeben.</span><span class="sxs-lookup"><span data-stu-id="e7517-142">That is, when a property on a control is set, that value is passed on to the element that has the [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) on it.</span></span>

### <a name="ellipse"></a><span data-ttu-id="e7517-143">Ellipse</span><span class="sxs-lookup"><span data-stu-id="e7517-143">Ellipse</span></span>

<span data-ttu-id="e7517-144">Beachten Sie, dass die Eigenschaften **:::no-loc text="Fill":::** und **:::no-loc text="Stroke":::** des Elements **\<Ellipse>** an die Eigenschaften <xref:System.Windows.Controls.Control.Foreground> und <xref:System.Windows.Controls.Control.Background> des Steuerelements gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="e7517-144">Notice that the **:::no-loc text="Fill":::** and **:::no-loc text="Stroke":::** properties of the **\<Ellipse>** element are bound to the control's <xref:System.Windows.Controls.Control.Foreground> and <xref:System.Windows.Controls.Control.Background> properties.</span></span>

### <a name="contentpresenter"></a><span data-ttu-id="e7517-145">ContentPresenter</span><span class="sxs-lookup"><span data-stu-id="e7517-145">ContentPresenter</span></span>

<span data-ttu-id="e7517-146">Der Vorlage wird auch ein [\<ContentPresenter>](xref:System.Windows.Controls.ContentPresenter)-Element hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e7517-146">A [\<ContentPresenter>](xref:System.Windows.Controls.ContentPresenter) element is also added to the template.</span></span> <span data-ttu-id="e7517-147">Da diese Vorlage für eine Schaltfläche konzipiert ist, müssen Sie berücksichtigen, dass die Schaltfläche von <xref:System.Windows.Controls.ContentControl> erbt.</span><span class="sxs-lookup"><span data-stu-id="e7517-147">Because this template is designed for a button, take into consideration that the button inherits from <xref:System.Windows.Controls.ContentControl>.</span></span> <span data-ttu-id="e7517-148">Die Schaltfläche stellt den Inhalt des Elements dar.</span><span class="sxs-lookup"><span data-stu-id="e7517-148">The button presents the content of the element.</span></span> <span data-ttu-id="e7517-149">Sie können beliebige Elemente innerhalb der Schaltfläche festlegen, z. B. Nur-Text oder sogar ein anderes Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="e7517-149">You can set anything inside of the button, such as plain text or even another control.</span></span> <span data-ttu-id="e7517-150">Beide folgenden Schaltflächen sind gültig:</span><span class="sxs-lookup"><span data-stu-id="e7517-150">Both of the following are valid buttons:</span></span>

```xaml
<Button>My Text</Button>

<!-- and -->

<Button>
    <CheckBox>Checkbox in a button</CheckBox>
</Button>
```

<span data-ttu-id="e7517-151">In den beiden vorherigen Beispielen werden der Text und das Kontrollkästchen als [Button.Content](xref:System.Windows.Controls.ContentControl.Content)-Eigenschaft festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e7517-151">In both of the previous examples, the text and the checkbox are set as the [Button.Content](xref:System.Windows.Controls.ContentControl.Content) property.</span></span> <span data-ttu-id="e7517-152">Was auch immer als Inhalt festgelegt wird, kann durch einen **\<ContentPresenter>** dargestellt werden, was die Vorlage auch leistet.</span><span class="sxs-lookup"><span data-stu-id="e7517-152">Whatever is set as the content can be presented through a **\<ContentPresenter>**, which is what the template does.</span></span>

<span data-ttu-id="e7517-153">Wenn die <xref:System.Windows.Controls.ControlTemplate> auf einen <xref:System.Windows.Controls.ContentControl>-Typ angewendet wird, z. B. auf ein `Button`-Element, wird nach einem <xref:System.Windows.Controls.ContentPresenter>-Element in der-Elementstruktur gesucht.</span><span class="sxs-lookup"><span data-stu-id="e7517-153">If the <xref:System.Windows.Controls.ControlTemplate> is applied to a <xref:System.Windows.Controls.ContentControl> type, such as a `Button`, a <xref:System.Windows.Controls.ContentPresenter> is searched for in the element tree.</span></span> <span data-ttu-id="e7517-154">Wenn der `ContentPresenter` gefunden wird, bindet die Vorlage automatisch die <xref:System.Windows.Controls.ContentControl.Content>-Eigenschaft des Steuerelements an den `ContentPresenter`.</span><span class="sxs-lookup"><span data-stu-id="e7517-154">If the `ContentPresenter` is found, the template automatically binds the control's <xref:System.Windows.Controls.ContentControl.Content> property to the `ContentPresenter`.</span></span>

## <a name="use-the-template"></a><span data-ttu-id="e7517-155">Verwenden der Vorlage</span><span class="sxs-lookup"><span data-stu-id="e7517-155">Use the template</span></span>

<span data-ttu-id="e7517-156">Suchen Sie die Schaltflächen, die zu Beginn dieses Artikels deklariert wurden.</span><span class="sxs-lookup"><span data-stu-id="e7517-156">Find the buttons that were declared at the start of this article.</span></span>

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

<span data-ttu-id="e7517-157">Legen Sie die <xref:System.Windows.Controls.Control.Template>-Eigenschaft der zweiten Schaltfläche auf die `roundbutton`-Ressource fest:</span><span class="sxs-lookup"><span data-stu-id="e7517-157">Set the second button's <xref:System.Windows.Controls.Control.Template> property to the `roundbutton` resource:</span></span>

[!code-xaml[StyledButton](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButton)]

<span data-ttu-id="e7517-158">Wenn Sie das Projekt ausführen und das Ergebnis untersuchen, sehen Sie, dass die Schaltfläche einen abgerundeten Hintergrund aufweist.</span><span class="sxs-lookup"><span data-stu-id="e7517-158">If you run the project and look at the result, you'll see that the button has a rounded background.</span></span>

![WPF-Fenster mit einer ovalen Vorlagenschaltfläche](media/create-apply-template/styled-button.png)

<span data-ttu-id="e7517-160">Vielleicht haben Sie bemerkt, dass die Schaltfläche kein Kreis ist, sondern verzerrt ist.</span><span class="sxs-lookup"><span data-stu-id="e7517-160">You may have noticed that the button isn't a circle but is skewed.</span></span> <span data-ttu-id="e7517-161">Aufgrund der Art und Weise, wie das **\<Ellipse>** -Element funktioniert, wird sie immer erweitert, um den verfügbaren Platz auszufüllen.</span><span class="sxs-lookup"><span data-stu-id="e7517-161">Because of the way the **\<Ellipse>** element works, it always expands to fill the available space.</span></span> <span data-ttu-id="e7517-162">Vereinheitlichen Sie den Kreis, indem Sie die Eigenschaften der Schaltfläche **:::no-loc text="width":::** und **:::no-loc text="height":::** in den gleichen Wert ändern:</span><span class="sxs-lookup"><span data-stu-id="e7517-162">Make the circle uniform by changing the button's  **:::no-loc text="width":::** and **:::no-loc text="height":::** properties to the same value:</span></span>

[!code-xaml[StyledButtonSize](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButtonSize)]

![WPF-Fenster mit einer runden Vorlagenschaltfläche](media/create-apply-template/styled-uniform-button.png)

## <a name="add-a-trigger"></a><span data-ttu-id="e7517-164">Hinzufügen eines Triggers</span><span class="sxs-lookup"><span data-stu-id="e7517-164">Add a Trigger</span></span>

<span data-ttu-id="e7517-165">Obwohl eine Schaltfläche mit einer angewendeten Vorlage anders aussieht, verhält sie sich wie jede andere Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="e7517-165">Even though a button with a template applied looks different, it behaves the same as any other button.</span></span> <span data-ttu-id="e7517-166">Wenn Sie auf die Schaltfläche klicken, wird das <xref:System.Windows.Controls.Primitives.ButtonBase.Click>-Ereignis ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="e7517-166">If you press the button, the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event fires.</span></span> <span data-ttu-id="e7517-167">Möglicherweise haben Sie jedoch bemerkt, dass die visuellen Elemente der Schaltfläche nicht geändert werden, wenn Sie den Mauszeiger über die Schaltfläche bewegen.</span><span class="sxs-lookup"><span data-stu-id="e7517-167">However, you may have noticed that when you move your mouse over the button, the button's visuals don't change.</span></span> <span data-ttu-id="e7517-168">Diese visuellen Interaktionen werden alle durch die Vorlage definiert.</span><span class="sxs-lookup"><span data-stu-id="e7517-168">These visual interactions are all defined by the template.</span></span>

<span data-ttu-id="e7517-169">Durch die dynamischen Ereignis- und Eigenschaftensysteme, die von WPF bereitgestellt werden, können Sie eine bestimmte Eigenschaft für einen Wert beobachten und die Vorlage ggf. neu formatieren.</span><span class="sxs-lookup"><span data-stu-id="e7517-169">With the dynamic event and property systems that WPF provides, you can watch a specific property for a value and then restyle the template when appropriate.</span></span> <span data-ttu-id="e7517-170">In diesem Beispiel beobachten Sie die <xref:System.Windows.UIElement.IsMouseOver>-Eigenschaft der Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="e7517-170">In this example, you'll watch the button's <xref:System.Windows.UIElement.IsMouseOver> property.</span></span> <span data-ttu-id="e7517-171">Wenn sich der Mauszeiger über dem Steuerelement befindet, formatieren Sie die **\<Ellipse>** mit einer neuen Farbe.</span><span class="sxs-lookup"><span data-stu-id="e7517-171">When the mouse is over the control, style the **\<Ellipse>** with a new color.</span></span> <span data-ttu-id="e7517-172">Dieser Triggertyp wird als *PropertyTrigger* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="e7517-172">This type of trigger is known as a *PropertyTrigger*.</span></span>

<span data-ttu-id="e7517-173">Damit dies funktioniert, müssen Sie **\<Ellipse>** einen Namen hinzufügen, auf den Sie verweisen können.</span><span class="sxs-lookup"><span data-stu-id="e7517-173">For this to work, you'll need to add a name to the **\<Ellipse>** that you can reference.</span></span> <span data-ttu-id="e7517-174">Vergeben Sie den Namen **backgroundElement**.</span><span class="sxs-lookup"><span data-stu-id="e7517-174">Give it the name of **backgroundElement**.</span></span>

[!code-xaml[EllipseName](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml#EllipseName)]

<span data-ttu-id="e7517-175">Fügen Sie als nun der [ControlTemplate.Triggers](xref:System.Windows.Controls.ControlTemplate.Triggers)-Sammlung einen neuen <xref:System.Windows.Trigger> hinzu.</span><span class="sxs-lookup"><span data-stu-id="e7517-175">Next, add a new <xref:System.Windows.Trigger> to the [ControlTemplate.Triggers](xref:System.Windows.Controls.ControlTemplate.Triggers) collection.</span></span> <span data-ttu-id="e7517-176">Der Trigger überwacht das `IsMouseOver`-Ereignis für den Wert `true`.</span><span class="sxs-lookup"><span data-stu-id="e7517-176">The trigger will watch the `IsMouseOver` event for the value `true`.</span></span>

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml?name=ControlTemplate&highlight=6-10)]

<span data-ttu-id="e7517-177">Fügen Sie dem **\<Trigger>** nun einen **\<Setter>** hinzu, der die **Fill**-Eigenschaft von **\<Ellipse>** in eine neue Farbe ändert.</span><span class="sxs-lookup"><span data-stu-id="e7517-177">Next, add a **\<Setter>** to the **\<Trigger>** that changes the **Fill** property of the **\<Ellipse>** to a new color.</span></span>

[!code-xaml[MouseOver](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#MouseOver)]

<span data-ttu-id="e7517-178">Führen Sie das Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="e7517-178">Run the project.</span></span> <span data-ttu-id="e7517-179">Beachten Sie, dass beim Bewegen der Maus über die Schaltfläche sich die Farbe der **\<Ellipse>** ändert.</span><span class="sxs-lookup"><span data-stu-id="e7517-179">Notice that when you move the mouse over the button, the color of the **\<Ellipse>** changes.</span></span>

![Mausbewegung über die WPF-Schaltfläche, um die Füllfarbe zu ändern](media/create-apply-template/mouse-move-over-button.gif)

## <a name="use-a-visualstate"></a><span data-ttu-id="e7517-181">Verwenden eines VisualState</span><span class="sxs-lookup"><span data-stu-id="e7517-181">Use a VisualState</span></span>

<span data-ttu-id="e7517-182">Visuelle Zustände werden von einem-Steuerelement definiert und ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="e7517-182">Visual states are defined and triggered by a control.</span></span> <span data-ttu-id="e7517-183">Wenn die Maus z. B. über das Steuerelement bewegt wird, wird der `CommonStates.MouseOver`-Zustand ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="e7517-183">For example, when the mouse is moved on top of the control, the `CommonStates.MouseOver` state is triggered.</span></span> <span data-ttu-id="e7517-184">Sie können Eigenschaftsänderungen auf der Grundlage des aktuellen Zustands des Steuerelements animieren.</span><span class="sxs-lookup"><span data-stu-id="e7517-184">You can animate property changes based on the current state of the control.</span></span> <span data-ttu-id="e7517-185">Im vorherigen Abschnitt wurde ein **\<PropertyTrigger>** verwendet, um den Vordergrund der Schaltfläche in `AliceBlue` zu ändern, wenn die `IsMouseOver`-Eigenschaft `true` war.</span><span class="sxs-lookup"><span data-stu-id="e7517-185">In the previous section, a **\<PropertyTrigger>** was used to change the foreground of the button to `AliceBlue` when the `IsMouseOver` property was `true`.</span></span> <span data-ttu-id="e7517-186">Erstellen Sie stattdessen einen visuellen Zustand, der die Änderung dieser Farbe animiert und für einen fließenden Übergang sorgt.</span><span class="sxs-lookup"><span data-stu-id="e7517-186">Instead, create a visual state that animates the change of this color, providing a smooth transition.</span></span> <span data-ttu-id="e7517-187">Weitere Informationen zu *VisualStates* finden Sie unter [Stile und Vorlagen in WPF](../fundamentals/styles-templates-overview.md#visual-states).</span><span class="sxs-lookup"><span data-stu-id="e7517-187">For more information about *VisualStates*, see [Styles and templates in WPF](../fundamentals/styles-templates-overview.md#visual-states).</span></span>

<span data-ttu-id="e7517-188">Wenn Sie den **\<PropertyTrigger>** in einen animierten visuellen Zustand konvertieren möchten, entfernen Sie zunächst das **\<ControlTemplate.Triggers>** -Element aus der Vorlage.</span><span class="sxs-lookup"><span data-stu-id="e7517-188">To convert the **\<PropertyTrigger>** to an animated visual state, First, remove the **\<ControlTemplate.Triggers>** element from your template.</span></span>

[!code-xaml[CleanTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#CleanTemplate)]

<span data-ttu-id="e7517-189">Fügen Sie dann im **\<Grid>** -Stamm der Steuerelementvorlage das **\<VisualStateManager.VisualStateGroups>** -Element mit einer **\<VisualStateGroup>** für `CommonStates` hinzu.</span><span class="sxs-lookup"><span data-stu-id="e7517-189">Next, in the **\<Grid>** root of the control template, add the **\<VisualStateManager.VisualStateGroups>** element with a **\<VisualStateGroup>** for `CommonStates`.</span></span> <span data-ttu-id="e7517-190">Definieren Sie zwei Zustände, `Normal` und `MouseOver`.</span><span class="sxs-lookup"><span data-stu-id="e7517-190">Define two states, `Normal` and `MouseOver`.</span></span>

[!code-xaml[VisualState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#VisualState)]

<span data-ttu-id="e7517-191">Alle in einem **\<VisualState>** definierten Animationen werden angewendet, wenn dieser Zustand ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="e7517-191">Any animations defined in a **\<VisualState>** are applied when that state is triggered.</span></span> <span data-ttu-id="e7517-192">Erstellen Sie Animationen für jeden Zustand.</span><span class="sxs-lookup"><span data-stu-id="e7517-192">Create animations for each state.</span></span> <span data-ttu-id="e7517-193">Animationen werden in einem **\<Storyboard>** -Element abgelegt.</span><span class="sxs-lookup"><span data-stu-id="e7517-193">Animations are put inside of a **\<Storyboard>** element.</span></span> <span data-ttu-id="e7517-194">Weitere Informationen zu Storyboards finden Sie unter [Übersicht über Storyboards](../../framework/wpf/graphics-multimedia/storyboards-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e7517-194">For more information about storyboards, see [Storyboards Overview](../../framework/wpf/graphics-multimedia/storyboards-overview.md).</span></span>

- <span data-ttu-id="e7517-195">Normal</span><span class="sxs-lookup"><span data-stu-id="e7517-195">Normal</span></span>

  <span data-ttu-id="e7517-196">Dieser Zustand animiert die Ellipsenfüllung und stellt sie in der Farbe `Background` des Steuerelements wieder her.</span><span class="sxs-lookup"><span data-stu-id="e7517-196">This state animates the ellipse fill, restoring it to the control's `Background` color.</span></span>

  [!code-xaml[NormalState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#NormalState)]

- <span data-ttu-id="e7517-197">MouseOver</span><span class="sxs-lookup"><span data-stu-id="e7517-197">MouseOver</span></span>

  <span data-ttu-id="e7517-198">Dieser Zustand animiert die Farbe `Background` der Ellipse in eine neue Farbe: `Yellow`.</span><span class="sxs-lookup"><span data-stu-id="e7517-198">This state animates the ellipse `Background` color to a new color: `Yellow`.</span></span>

  [!code-xaml[MouseOverState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#MouseOverState)]

<span data-ttu-id="e7517-199">Die **\<ControlTemplate>** sollte nun wie folgt aussehen.</span><span class="sxs-lookup"><span data-stu-id="e7517-199">The **\<ControlTemplate>** should now look like the following.</span></span>

[!code-xaml[FinalTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window7.xaml#FinalTemplate)]

<span data-ttu-id="e7517-200">Führen Sie das Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="e7517-200">Run the project.</span></span> <span data-ttu-id="e7517-201">Beachten Sie, dass beim Bewegen der Maus über die Schaltfläche sich die Farbe der **\<Ellipse>** animiert wird.</span><span class="sxs-lookup"><span data-stu-id="e7517-201">Notice that when you move the mouse over the button, the color of the **\<Ellipse>** animates.</span></span>

![Mausbewegung über die WPF-Schaltfläche, um die Füllfarbe zu ändern](media/create-apply-template/mouse-move-over-button-visualstate.gif)

## <a name="next-steps"></a><span data-ttu-id="e7517-203">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="e7517-203">Next steps</span></span>

- [<span data-ttu-id="e7517-204">Erstellen eines Stils für ein Steuerelement in WPF</span><span class="sxs-lookup"><span data-stu-id="e7517-204">Create a style for a control in WPF</span></span>](../fundamentals/styles-templates-create-apply-style.md)
- [<span data-ttu-id="e7517-205">Stile und Vorlagen in WPF</span><span class="sxs-lookup"><span data-stu-id="e7517-205">Styles and templates in WPF</span></span>](../fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="e7517-206">Überblick über XAML-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="e7517-206">Overview of XAML Resources</span></span>](../fundamentals/xaml-resources-define.md)
