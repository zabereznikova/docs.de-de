---
title: Erstellen einer Vorlage in WPF - .NET Desktop
description: Erfahren Sie, wie Sie eine Steuerelementvorlage in Windows Presentation Foundation und .NET Core erstellen und darauf verweisen.
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
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "81432539"
---
# <a name="create-a-template-for-a-control"></a><span data-ttu-id="0ca95-103">Erstellen einer Vorlage für ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="0ca95-103">Create a template for a control</span></span>

<span data-ttu-id="0ca95-104">Mit Windows Presentation Foundation (WPF) können Sie die visuelle Struktur und das Verhalten eines vorhandenen Steuerelements mit Einer eigenen wiederverwendbaren Vorlage anpassen.</span><span class="sxs-lookup"><span data-stu-id="0ca95-104">With Windows Presentation Foundation (WPF), you can customize an existing control's visual structure and behavior with your own reusable template.</span></span> <span data-ttu-id="0ca95-105">Vorlagen können global auf Ihre Anwendung, Fenster und Seiten oder direkt auf Steuerelemente angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="0ca95-105">Templates can be applied globally to your application, windows and pages, or directly to controls.</span></span> <span data-ttu-id="0ca95-106">Die meisten Szenarien, in denen Sie ein neues Steuerelement erstellen müssen, können stattdessen durch das Erstellen einer neuen Vorlage für ein vorhandenes Steuerelement abgedeckt werden.</span><span class="sxs-lookup"><span data-stu-id="0ca95-106">Most scenarios that require you to create a new control can be covered by instead creating a new template for an existing control.</span></span>

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

<span data-ttu-id="0ca95-107">In diesem Artikel werden Sie das <xref:System.Windows.Controls.ControlTemplate> Erstellen <xref:System.Windows.Controls.Button> eines neuen Steuerelements untersuchen.</span><span class="sxs-lookup"><span data-stu-id="0ca95-107">In this article, you'll explore creating a new <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>

## <a name="when-to-create-a-controltemplate"></a><span data-ttu-id="0ca95-108">Wann sie eine ControlTemplate erstellen</span><span class="sxs-lookup"><span data-stu-id="0ca95-108">When to create a ControlTemplate</span></span>

<span data-ttu-id="0ca95-109">Steuerelemente verfügen über <xref:System.Windows.Controls.Border.Background%2A>viele <xref:System.Windows.Controls.Control.Foreground%2A>Eigenschaften, z. B. , und <xref:System.Windows.Controls.Control.FontFamily%2A>.</span><span class="sxs-lookup"><span data-stu-id="0ca95-109">Controls have many properties, such as <xref:System.Windows.Controls.Border.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>, and <xref:System.Windows.Controls.Control.FontFamily%2A>.</span></span> <span data-ttu-id="0ca95-110">Diese Eigenschaften steuern verschiedene Aspekte der Darstellung des Steuerelements, aber die Änderungen, die Sie durch Festlegen dieser Eigenschaften vornehmen können, sind begrenzt.</span><span class="sxs-lookup"><span data-stu-id="0ca95-110">These properties control different aspects of the control's appearance, but the changes that you can make by setting these properties are limited.</span></span> <span data-ttu-id="0ca95-111">Sie können die <xref:System.Windows.Controls.Control.Foreground%2A> Eigenschaft z. <xref:System.Windows.Controls.Control.FontStyle%2A> B. auf blau <xref:System.Windows.Controls.CheckBox>und auf Kursiv für eine festlegen.</span><span class="sxs-lookup"><span data-stu-id="0ca95-111">For example, you can set the <xref:System.Windows.Controls.Control.Foreground%2A> property to blue and <xref:System.Windows.Controls.Control.FontStyle%2A> to italic on a <xref:System.Windows.Controls.CheckBox>.</span></span> <span data-ttu-id="0ca95-112">Wenn Sie die Darstellung des Steuerelements über das Festlegen der anderen Eigenschaften <xref:System.Windows.Controls.ControlTemplate>des Steuerelements hinaus anpassen möchten, erstellen Sie eine .</span><span class="sxs-lookup"><span data-stu-id="0ca95-112">When you want to customize the control's appearance beyond what setting the other properties on the control can do, you create a <xref:System.Windows.Controls.ControlTemplate>.</span></span>

<span data-ttu-id="0ca95-113">In den meisten Benutzeroberflächen hat eine Schaltfläche die gleiche allgemeine Darstellung: ein Rechteck mit etwas Text.</span><span class="sxs-lookup"><span data-stu-id="0ca95-113">In most user interfaces, a button has the same general appearance: a rectangle with some text.</span></span> <span data-ttu-id="0ca95-114">Wenn Sie eine abgerundete Schaltfläche erstellen möchten, können Sie ein neues Steuerelement erstellen, das von der Schaltfläche erbt oder die Funktionalität der Schaltfläche neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="0ca95-114">If you wanted to create a rounded button, you could create a new control that inherits from the button or recreates the functionality of the button.</span></span> <span data-ttu-id="0ca95-115">Darüber hinaus würde das neue Benutzersteuerelement die kreisförmige Visualisierung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0ca95-115">In addition, the new user control would provide the circular visual.</span></span>

<span data-ttu-id="0ca95-116">Sie können das Erstellen neuer Steuerelemente vermeiden, indem Sie das visuelle Layout eines vorhandenen Steuerelements anpassen.</span><span class="sxs-lookup"><span data-stu-id="0ca95-116">You can avoid creating new controls by customizing the visual layout of an existing control.</span></span> <span data-ttu-id="0ca95-117">Mit einer abgerundeten Schaltfläche <xref:System.Windows.Controls.ControlTemplate> erstellen Sie eine mit dem gewünschten visuellen Layout.</span><span class="sxs-lookup"><span data-stu-id="0ca95-117">With a rounded button, you create a <xref:System.Windows.Controls.ControlTemplate> with the desired visual layout.</span></span>

<span data-ttu-id="0ca95-118">Wenn Sie hingegen ein Steuerelement mit neuen Funktionen, unterschiedlichen Eigenschaften und neuen <xref:System.Windows.Controls.UserControl>Einstellungen benötigen, erstellen Sie eine neue .</span><span class="sxs-lookup"><span data-stu-id="0ca95-118">On the other hand, if you need a control with new functionality, different properties, and new settings, you would create a new <xref:System.Windows.Controls.UserControl>.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0ca95-119">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="0ca95-119">Prerequisites</span></span>

<span data-ttu-id="0ca95-120">Erstellen Sie eine neue WPF-Anwendung, und legen Sie in *MainWindow.xaml* (oder einem anderen Fenster Ihrer Wahl) die folgenden Eigenschaften im \*\* \<Window>-Element\*\* fest:</span><span class="sxs-lookup"><span data-stu-id="0ca95-120">Create a new WPF application and in *MainWindow.xaml* (or another window of your choice) set the following properties on the **\<Window>** element:</span></span>

|     |     |
| --- | --- |
| **[!OP.NO-LOC(Title)]**         | `Template Intro Sample` |
| **[!OP.NO-LOC(SizeToContent)]** | `WidthAndHeight` |
| **[!OP.NO-LOC(MinWidth)]**      | `250` |

<span data-ttu-id="0ca95-121">Legen Sie den Inhalt des \*\* \<Window>-Elements\*\* auf das folgende XAML fest:</span><span class="sxs-lookup"><span data-stu-id="0ca95-121">Set the content of the **\<Window>** element to the following XAML:</span></span>

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

<span data-ttu-id="0ca95-122">Am Ende sollte die *Datei MainWindow.xaml* wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="0ca95-122">In the end, the *MainWindow.xaml* file should look similar to the following:</span></span>

[!code-xaml[InitialWhole](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#InitialWhole)]

<span data-ttu-id="0ca95-123">Wenn Sie die Anwendung ausführen, sieht sie wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="0ca95-123">If you run the application, it looks like the following:</span></span>

![WPF-Fenster mit zwei unformatierten Schaltflächen](media/create-apply-template/unstyled-button.png)

## <a name="create-a-controltemplate"></a><span data-ttu-id="0ca95-125">Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="0ca95-125">Create a ControlTemplate</span></span>

<span data-ttu-id="0ca95-126">Die häufigste Möglichkeit zum <xref:System.Windows.Controls.ControlTemplate> Deklarieren einer `Resources` ist als Ressource im Abschnitt in einer XAML-Datei.</span><span class="sxs-lookup"><span data-stu-id="0ca95-126">The most common way to declare a <xref:System.Windows.Controls.ControlTemplate> is as a resource in the `Resources` section in a XAML file.</span></span> <span data-ttu-id="0ca95-127">Da Vorlagen Ressourcen sind, befolgen sie dieselben Bereichsregeln, die für alle Ressourcen gelten.</span><span class="sxs-lookup"><span data-stu-id="0ca95-127">Because templates are resources, they obey the same scoping rules that apply to all resources.</span></span> <span data-ttu-id="0ca95-128">Einfach ausgedrückt, wo Sie eine Vorlage deklarieren wirkt, wo die Vorlage angewendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="0ca95-128">Put simply, where you declare a template affects where the template can be applied.</span></span> <span data-ttu-id="0ca95-129">Wenn Sie beispielsweise die Vorlage im Stammelement Der XAML-Datei der Anwendungsdefinition deklarieren, kann die Vorlage überall in der Anwendung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0ca95-129">For example, if you declare the template in the root element of your application definition XAML file, the template can be used anywhere in your application.</span></span> <span data-ttu-id="0ca95-130">Wenn Sie die Vorlage in einem Fenster definieren, können nur die Steuerelemente in diesem Fenster die Vorlage verwenden.</span><span class="sxs-lookup"><span data-stu-id="0ca95-130">If you define the template in a window, only the controls in that window can use the template.</span></span>

<span data-ttu-id="0ca95-131">Fügen Sie zunächst `Window.Resources` ein Element zu Ihrer *MainWindow.xaml-Datei* hinzu:</span><span class="sxs-lookup"><span data-stu-id="0ca95-131">To start with, add a `Window.Resources` element to your *MainWindow.xaml* file:</span></span>

[!code-xaml[WindowResStart](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window2.xaml#WindowResStart)]

<span data-ttu-id="0ca95-132">Erstellen Sie eine neue \*\* \<ControlTemplate->\*\* mit den folgenden Eigenschaftensatz:</span><span class="sxs-lookup"><span data-stu-id="0ca95-132">Create a new **\<ControlTemplate>** with the following properties set:</span></span>

|     |     |
| --- | --- |
| <span data-ttu-id="0ca95-133">**x:Key**</span><span class="sxs-lookup"><span data-stu-id="0ca95-133">**x:Key**</span></span>         | `roundbutton` |
| **TargetType**    | `Button` |

<span data-ttu-id="0ca95-134">Diese Steuerelementvorlage ist einfach:</span><span class="sxs-lookup"><span data-stu-id="0ca95-134">This control template will be simple:</span></span>

- <span data-ttu-id="0ca95-135">ein Stammelement für das Steuerelement, ein<xref:System.Windows.Controls.Grid></span><span class="sxs-lookup"><span data-stu-id="0ca95-135">a root element for the control, a <xref:System.Windows.Controls.Grid></span></span>
- <span data-ttu-id="0ca95-136">a, <xref:System.Windows.Shapes.Ellipse> um das abgerundete Erscheinungsbild der Schaltfläche zu zeichnen</span><span class="sxs-lookup"><span data-stu-id="0ca95-136">an <xref:System.Windows.Shapes.Ellipse> to draw the rounded appearance of the button</span></span>
- <span data-ttu-id="0ca95-137">a <xref:System.Windows.Controls.ContentPresenter> zum Anzeigen des benutzerdefinierten Schaltflächeninhalts</span><span class="sxs-lookup"><span data-stu-id="0ca95-137">a <xref:System.Windows.Controls.ContentPresenter> to display the user-specified button content</span></span>

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#ControlTemplate)]

### <a name="templatebinding"></a><span data-ttu-id="0ca95-138">TemplateBinding</span><span class="sxs-lookup"><span data-stu-id="0ca95-138">TemplateBinding</span></span>

<span data-ttu-id="0ca95-139">Wenn Sie einen <xref:System.Windows.Controls.ControlTemplate>neuen erstellen, können Sie die öffentlichen Eigenschaften weiterhin verwenden, um die Darstellung des Steuerelements zu ändern.</span><span class="sxs-lookup"><span data-stu-id="0ca95-139">When you create a new <xref:System.Windows.Controls.ControlTemplate>, you still might want to use the public properties to change the control's appearance.</span></span> <span data-ttu-id="0ca95-140">Die [TemplateBinding-Markuperweiterung](../../framework/wpf/advanced/templatebinding-markup-extension.md) bindet eine Eigenschaft eines <xref:System.Windows.Controls.ControlTemplate> Elements, das sich im Element befindet, an eine öffentliche Eigenschaft, die durch das Steuerelement definiert wird.</span><span class="sxs-lookup"><span data-stu-id="0ca95-140">The [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) markup extension binds a property of an element that is in the <xref:System.Windows.Controls.ControlTemplate> to a public property that is defined by the control.</span></span> <span data-ttu-id="0ca95-141">Wenn Sie eine [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md)verwenden, aktivieren Sie Eigenschaften für das Steuerelement, um als Parameter für die Vorlage zu fungieren.</span><span class="sxs-lookup"><span data-stu-id="0ca95-141">When you use a [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md), you enable properties on the control to act as parameters to the template.</span></span> <span data-ttu-id="0ca95-142">D.h., beim Festlegen einer Steuerelementeigenschaft wird dieser Wert an das Element mit [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) übergeben.</span><span class="sxs-lookup"><span data-stu-id="0ca95-142">That is, when a property on a control is set, that value is passed on to the element that has the [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) on it.</span></span>

### <a name="ellipse"></a><span data-ttu-id="0ca95-143">Ellipse</span><span class="sxs-lookup"><span data-stu-id="0ca95-143">Ellipse</span></span>

<span data-ttu-id="0ca95-144">Beachten **:::no-loc text="Fill":::** Sie, **:::no-loc text="Stroke":::** dass die und die Eigenschaften des \*\* \<Ellipse->-Elements\*\* an die Eigenschaften des Steuerelements <xref:System.Windows.Controls.Control.Foreground> und <xref:System.Windows.Controls.Control.Background> der Eigenschaften gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="0ca95-144">Notice that the **:::no-loc text="Fill":::** and **:::no-loc text="Stroke":::** properties of the **\<Ellipse>** element are bound to the control's <xref:System.Windows.Controls.Control.Foreground> and <xref:System.Windows.Controls.Control.Background> properties.</span></span>

### <a name="contentpresenter"></a><span data-ttu-id="0ca95-145">ContentPresenter</span><span class="sxs-lookup"><span data-stu-id="0ca95-145">ContentPresenter</span></span>

<span data-ttu-id="0ca95-146">Ein [ \<ContentPresenter->-Element](xref:System.Windows.Controls.ContentPresenter) wird ebenfalls zur Vorlage hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0ca95-146">A [\<ContentPresenter>](xref:System.Windows.Controls.ContentPresenter) element is also added to the template.</span></span> <span data-ttu-id="0ca95-147">Da diese Vorlage für eine Schaltfläche entworfen wurde, sollten <xref:System.Windows.Controls.ContentControl>Sie berücksichtigen, dass die Schaltfläche von erbt.</span><span class="sxs-lookup"><span data-stu-id="0ca95-147">Because this template is designed for a button, take into consideration that the button inherits from <xref:System.Windows.Controls.ContentControl>.</span></span> <span data-ttu-id="0ca95-148">Die Schaltfläche zeigt den Inhalt des Elements an.</span><span class="sxs-lookup"><span data-stu-id="0ca95-148">The button presents the content of the element.</span></span> <span data-ttu-id="0ca95-149">Sie können alles innerhalb der Schaltfläche festlegen, z. B. Nur-Text oder sogar ein anderes Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0ca95-149">You can set anything inside of the button, such as plain text or even another control.</span></span> <span data-ttu-id="0ca95-150">Beide der folgenden Schaltflächen sind gültig:</span><span class="sxs-lookup"><span data-stu-id="0ca95-150">Both of the following are valid buttons:</span></span>

```xaml
<Button>My Text</Button>

<!-- and -->

<Button>
    <CheckBox>Checkbox in a button</CheckBox>
</Button>
```

<span data-ttu-id="0ca95-151">In beiden vorherigen Beispielen werden der Text und das Kontrollkästchen als [Button.Content-Eigenschaft](xref:System.Windows.Controls.ContentControl.Content) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="0ca95-151">In both of the previous examples, the text and the checkbox are set as the [Button.Content](xref:System.Windows.Controls.ContentControl.Content) property.</span></span> <span data-ttu-id="0ca95-152">Was auch immer als Inhalt festgelegt wird, kann über einen \*\* \<ContentPresenter>\*\* dargestellt werden, was die Vorlage tut.</span><span class="sxs-lookup"><span data-stu-id="0ca95-152">Whatever is set as the content can be presented through a **\<ContentPresenter>**, which is what the template does.</span></span>

<span data-ttu-id="0ca95-153">Wenn <xref:System.Windows.Controls.ControlTemplate> der auf <xref:System.Windows.Controls.ContentControl> einen Typ angewendet `Button`wird, z. B. ein , <xref:System.Windows.Controls.ContentPresenter> wird in der Elementstruktur gesucht.</span><span class="sxs-lookup"><span data-stu-id="0ca95-153">If the <xref:System.Windows.Controls.ControlTemplate> is applied to a <xref:System.Windows.Controls.ContentControl> type, such as a `Button`, a <xref:System.Windows.Controls.ContentPresenter> is searched for in the element tree.</span></span> <span data-ttu-id="0ca95-154">Wenn `ContentPresenter` der gefunden wird, bindet die Vorlage <xref:System.Windows.Controls.ContentControl.Content> automatisch `ContentPresenter`die Eigenschaft des Steuerelements an die .</span><span class="sxs-lookup"><span data-stu-id="0ca95-154">If the `ContentPresenter` is found, the template automatically binds the control's <xref:System.Windows.Controls.ContentControl.Content> property to the `ContentPresenter`.</span></span>

## <a name="use-the-template"></a><span data-ttu-id="0ca95-155">Verwenden der Vorlage</span><span class="sxs-lookup"><span data-stu-id="0ca95-155">Use the template</span></span>

<span data-ttu-id="0ca95-156">Suchen Sie die Schaltflächen, die am Anfang dieses Artikels deklariert wurden.</span><span class="sxs-lookup"><span data-stu-id="0ca95-156">Find the buttons that were declared at the start of this article.</span></span>

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

<span data-ttu-id="0ca95-157">Legen Sie die <xref:System.Windows.Controls.Control.Template> Eigenschaft der `roundbutton` zweiten Schaltfläche auf die Ressource fest:</span><span class="sxs-lookup"><span data-stu-id="0ca95-157">Set the second button's <xref:System.Windows.Controls.Control.Template> property to the `roundbutton` resource:</span></span>

[!code-xaml[StyledButton](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButton)]

<span data-ttu-id="0ca95-158">Wenn Sie das Projekt ausführen und sich das Ergebnis ansehen, sehen Sie, dass die Schaltfläche einen abgerundeten Hintergrund hat.</span><span class="sxs-lookup"><span data-stu-id="0ca95-158">If you run the project and look at the result, you'll see that the button has a rounded background.</span></span>

![WPF-Fenster mit einer ovalen Vorlagetaste](media/create-apply-template/styled-button.png)

<span data-ttu-id="0ca95-160">Sie haben vielleicht bemerkt, dass die Schaltfläche kein Kreis ist, sondern verzerrt ist.</span><span class="sxs-lookup"><span data-stu-id="0ca95-160">You may have noticed that the button isn't a circle but is skewed.</span></span> <span data-ttu-id="0ca95-161">Aufgrund der Funktionsweise des \*\* \<Ellipse->-Elements\*\* wird es immer erweitert, um den verfügbaren Platz zu füllen.</span><span class="sxs-lookup"><span data-stu-id="0ca95-161">Because of the way the **\<Ellipse>** element works, it always expands to fill the available space.</span></span> <span data-ttu-id="0ca95-162">Machen Sie den Kreis gleichmäßig, **:::no-loc text="width":::** **:::no-loc text="height":::** indem Sie die Schaltfläche und die Eigenschaften auf denselben Wert ändern:</span><span class="sxs-lookup"><span data-stu-id="0ca95-162">Make the circle uniform by changing the button's  **:::no-loc text="width":::** and **:::no-loc text="height":::** properties to the same value:</span></span>

[!code-xaml[StyledButtonSize](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButtonSize)]

![WPF-Fenster mit einer Vorlagen-Rundschaltfläche](media/create-apply-template/styled-uniform-button.png)

## <a name="add-a-trigger"></a><span data-ttu-id="0ca95-164">Hinzufügen eines Triggers</span><span class="sxs-lookup"><span data-stu-id="0ca95-164">Add a Trigger</span></span>

<span data-ttu-id="0ca95-165">Auch wenn eine Schaltfläche mit einer angewendeten Vorlage anders aussieht, verhält sie sich genauso wie jede andere Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="0ca95-165">Even though a button with a template applied looks different, it behaves the same as any other button.</span></span> <span data-ttu-id="0ca95-166">Wenn Sie die Taste <xref:System.Windows.Controls.Primitives.ButtonBase.Click> drücken, wird das Ereignis ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="0ca95-166">If you press the button, the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event fires.</span></span> <span data-ttu-id="0ca95-167">Sie haben jedoch möglicherweise bemerkt, dass sich die Visuellen der Schaltfläche nicht ändern, wenn Sie die Maus über die Schaltfläche bewegen.</span><span class="sxs-lookup"><span data-stu-id="0ca95-167">However, you may have noticed that when you move your mouse over the button, the button's visuals don't change.</span></span> <span data-ttu-id="0ca95-168">Diese visuellen Interaktionen werden alle durch die Vorlage definiert.</span><span class="sxs-lookup"><span data-stu-id="0ca95-168">These visual interactions are all defined by the template.</span></span>

<span data-ttu-id="0ca95-169">Mit den dynamischen Ereignis- und Eigenschaftssystemen, die WPF bereitstellt, können Sie eine bestimmte Eigenschaft für einen Wert ansehen und die Vorlage dann entsprechend umgestalten.</span><span class="sxs-lookup"><span data-stu-id="0ca95-169">With the dynamic event and property systems that WPF provides, you can watch a specific property for a value and then restyle the template when appropriate.</span></span> <span data-ttu-id="0ca95-170">In diesem Beispiel sehen Sie sich <xref:System.Windows.UIElement.IsMouseOver> die Eigenschaft der Schaltfläche an.</span><span class="sxs-lookup"><span data-stu-id="0ca95-170">In this example, you'll watch the button's <xref:System.Windows.UIElement.IsMouseOver> property.</span></span> <span data-ttu-id="0ca95-171">Wenn die Maus über dem Steuerelement ist, stilisieren Sie die \*\* \<Ellipse->\*\* mit einer neuen Farbe.</span><span class="sxs-lookup"><span data-stu-id="0ca95-171">When the mouse is over the control, style the **\<Ellipse>** with a new color.</span></span> <span data-ttu-id="0ca95-172">Dieser Triggertyp wird als *PropertyTrigger*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="0ca95-172">This type of trigger is known as a *PropertyTrigger*.</span></span>

<span data-ttu-id="0ca95-173">Damit dies funktioniert, müssen Sie dem \*\* \<Ellipse->\*\* einen Namen hinzufügen, auf den Sie verweisen können.</span><span class="sxs-lookup"><span data-stu-id="0ca95-173">For this to work, you'll need to add a name to the **\<Ellipse>** that you can reference.</span></span> <span data-ttu-id="0ca95-174">Geben Sie ihm den Namen **backgroundElement**.</span><span class="sxs-lookup"><span data-stu-id="0ca95-174">Give it the name of **backgroundElement**.</span></span>

[!code-xaml[EllipseName](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml#EllipseName)]

<span data-ttu-id="0ca95-175">Fügen Sie als <xref:System.Windows.Trigger> Nächstes der [ControlTemplate.Triggers-Auflistung](xref:System.Windows.Controls.ControlTemplate.Triggers) eine neue hinzu.</span><span class="sxs-lookup"><span data-stu-id="0ca95-175">Next, add a new <xref:System.Windows.Trigger> to the [ControlTemplate.Triggers](xref:System.Windows.Controls.ControlTemplate.Triggers) collection.</span></span> <span data-ttu-id="0ca95-176">Der Trigger beobachtet `IsMouseOver` das Ereignis `true`für den Wert .</span><span class="sxs-lookup"><span data-stu-id="0ca95-176">The trigger will watch the `IsMouseOver` event for the value `true`.</span></span>

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml?name=ControlTemplate&highlight=6-10)]

<span data-ttu-id="0ca95-177">Fügen Sie als Nächstes eine \*\* \<Setter->\*\* zum \*\* \<Trigger->\*\* hinzu, die die **Fill-Eigenschaft** der \*\* \<Ellipse->\*\* in eine neue Farbe ändert.</span><span class="sxs-lookup"><span data-stu-id="0ca95-177">Next, add a **\<Setter>** to the **\<Trigger>** that changes the **Fill** property of the **\<Ellipse>** to a new color.</span></span>

[!code-xaml[MouseOver](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#MouseOver)]

<span data-ttu-id="0ca95-178">Führen Sie das Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="0ca95-178">Run the project.</span></span> <span data-ttu-id="0ca95-179">Beachten Sie, dass sich beim Bewegen der Maus über die Schaltfläche die Farbe der \*\* \<Ellipse->\*\* ändert.</span><span class="sxs-lookup"><span data-stu-id="0ca95-179">Notice that when you move the mouse over the button, the color of the **\<Ellipse>** changes.</span></span>

![Maus bewegt sich über die WPF-Taste, um die Füllfarbe zu ändern](media/create-apply-template/mouse-move-over-button.gif)

## <a name="use-a-visualstate"></a><span data-ttu-id="0ca95-181">Verwenden eines VisualState</span><span class="sxs-lookup"><span data-stu-id="0ca95-181">Use a VisualState</span></span>

<span data-ttu-id="0ca95-182">Visuelle Zustände werden durch ein Steuerelement definiert und ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="0ca95-182">Visual states are defined and triggered by a control.</span></span> <span data-ttu-id="0ca95-183">Wenn die Maus beispielsweise über das Steuerelement bewegt `CommonStates.MouseOver` wird, wird der Zustand ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="0ca95-183">For example, when the mouse is moved on top of the control, the `CommonStates.MouseOver` state is triggered.</span></span> <span data-ttu-id="0ca95-184">Sie können Eigenschaftenänderungen basierend auf dem aktuellen Status des Steuerelements animieren.</span><span class="sxs-lookup"><span data-stu-id="0ca95-184">You can animate property changes based on the current state of the control.</span></span> <span data-ttu-id="0ca95-185">Im vorherigen Abschnitt wurde `IsMouseOver` ein `true` \*\* \<PropertyTrigger->\*\* verwendet, um `AliceBlue` den Vordergrund der Schaltfläche in den Zeitpunkt zu ändern, zu dem die Eigenschaft war.</span><span class="sxs-lookup"><span data-stu-id="0ca95-185">In the previous section, a **\<PropertyTrigger>** was used to change the foreground of the button to `AliceBlue` when the `IsMouseOver` property was `true`.</span></span> <span data-ttu-id="0ca95-186">Erstellen Sie stattdessen einen visuellen Zustand, der die Änderung dieser Farbe animiert und einen reibungslosen Übergang bietet.</span><span class="sxs-lookup"><span data-stu-id="0ca95-186">Instead, create a visual state that animates the change of this color, providing a smooth transition.</span></span> <span data-ttu-id="0ca95-187">Weitere Informationen zu *VisualStates*finden Sie [unter Stile und Vorlagen in WPF](../fundamentals/styles-templates-overview.md#visual-states).</span><span class="sxs-lookup"><span data-stu-id="0ca95-187">For more information about *VisualStates*, see [Styles and templates in WPF](../fundamentals/styles-templates-overview.md#visual-states).</span></span>

<span data-ttu-id="0ca95-188">Um \*\* \<propertyTrigger>\*\* in einen animierten visuellen Zustand zu konvertieren, entfernen Sie zuerst das \*\* \<ControlTemplate.Triggers>-Element\*\* aus Ihrer Vorlage.</span><span class="sxs-lookup"><span data-stu-id="0ca95-188">To convert the **\<PropertyTrigger>** to an animated visual state, First, remove the **\<ControlTemplate.Triggers>** element from your template.</span></span>

[!code-xaml[CleanTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#CleanTemplate)]

<span data-ttu-id="0ca95-189">Fügen Sie anschließend im \*\* \<Stammverzeichnis "Grid>"\*\* der Steuerelementvorlage das \*\* \<VisualStateManager.VisualStateGroups->-Element\*\* mit einem \*\* \<VisualStateGroup->\*\* für `CommonStates`hinzu.</span><span class="sxs-lookup"><span data-stu-id="0ca95-189">Next, in the **\<Grid>** root of the control template, add the **\<VisualStateManager.VisualStateGroups>** element with a **\<VisualStateGroup>** for `CommonStates`.</span></span> <span data-ttu-id="0ca95-190">Definieren Sie `Normal` zwei `MouseOver`Zustände und .</span><span class="sxs-lookup"><span data-stu-id="0ca95-190">Define two states, `Normal` and `MouseOver`.</span></span>

[!code-xaml[VisualState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#VisualState)]

<span data-ttu-id="0ca95-191">Alle Animationen, die in einem \*\* \<VisualState->\*\* definiert sind, werden angewendet, wenn dieser Status ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="0ca95-191">Any animations defined in a **\<VisualState>** are applied when that state is triggered.</span></span> <span data-ttu-id="0ca95-192">Erstellen Sie Animationen für jeden Status.</span><span class="sxs-lookup"><span data-stu-id="0ca95-192">Create animations for each state.</span></span> <span data-ttu-id="0ca95-193">Animationen werden in einem \*\* \<Storyboard->-Element\*\* abgelegt.</span><span class="sxs-lookup"><span data-stu-id="0ca95-193">Animations are put inside of a **\<Storyboard>** element.</span></span> <span data-ttu-id="0ca95-194">Weitere Informationen zu Storyboards finden Sie unter [Storyboards Übersicht](../../framework/wpf/graphics-multimedia/storyboards-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0ca95-194">For more information about storyboards, see [Storyboards Overview](../../framework/wpf/graphics-multimedia/storyboards-overview.md).</span></span>

- <span data-ttu-id="0ca95-195">Normal</span><span class="sxs-lookup"><span data-stu-id="0ca95-195">Normal</span></span>

  <span data-ttu-id="0ca95-196">Dieser Zustand animiert die Ellipsenfüllung und stellt `Background` sie in der Farbe des Steuerelements wieder her.</span><span class="sxs-lookup"><span data-stu-id="0ca95-196">This state animates the ellipse fill, restoring it to the control's `Background` color.</span></span>

  [!code-xaml[NormalState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#NormalState)]

- <span data-ttu-id="0ca95-197">MouseOver</span><span class="sxs-lookup"><span data-stu-id="0ca95-197">MouseOver</span></span>

  <span data-ttu-id="0ca95-198">Dieser Zustand animiert `Background` die Ellipsenfarbe `Yellow`zu einer neuen Farbe: .</span><span class="sxs-lookup"><span data-stu-id="0ca95-198">This state animates the ellipse `Background` color to a new color: `Yellow`.</span></span>

  [!code-xaml[MouseOverState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#MouseOverState)]

<span data-ttu-id="0ca95-199">Die \*\* \<ControlTemplate->\*\* sollten nun wie folgt aussehen.</span><span class="sxs-lookup"><span data-stu-id="0ca95-199">The **\<ControlTemplate>** should now look like the following.</span></span>

[!code-xaml[FinalTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window7.xaml#FinalTemplate)]

<span data-ttu-id="0ca95-200">Führen Sie das Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="0ca95-200">Run the project.</span></span> <span data-ttu-id="0ca95-201">Beachten Sie, dass beim Bewegen der Maus über die Schaltfläche die Farbe der \*\* \<Ellipse->\*\* animiert wird.</span><span class="sxs-lookup"><span data-stu-id="0ca95-201">Notice that when you move the mouse over the button, the color of the **\<Ellipse>** animates.</span></span>

![Maus bewegt sich über die WPF-Taste, um die Füllfarbe zu ändern](media/create-apply-template/mouse-move-over-button-visualstate.gif)

## <a name="next-steps"></a><span data-ttu-id="0ca95-203">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="0ca95-203">Next steps</span></span>

- [<span data-ttu-id="0ca95-204">Erstellen eines Stils für ein Steuerelement in WPF</span><span class="sxs-lookup"><span data-stu-id="0ca95-204">Create a style for a control in WPF</span></span>](../fundamentals/styles-templates-create-apply-style.md)
- [<span data-ttu-id="0ca95-205">Stile und Vorlagen in WPF</span><span class="sxs-lookup"><span data-stu-id="0ca95-205">Styles and templates in WPF</span></span>](../fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="0ca95-206">Überblick über XAML-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="0ca95-206">Overview of XAML Resources</span></span>](../fundamentals/xaml-resources-define.md)
