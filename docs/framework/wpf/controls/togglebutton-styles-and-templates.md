---
title: ToggleButton-Stile und -Vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], ToggleButton
- ToggleButton [WPF], styles and templates
- ControlTemplate [WPF], ToggleButton
- styles [WPF], ToggleButton
- templates [WPF], ToggleButton
- parts [WPF], ToggleButton
ms.assetid: 54f23f30-4bcb-4f09-8ce4-376a13a255a1
ms.openlocfilehash: e055dcbd557f9b90eb2fe99ad15a05b6f229fd28
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805914"
---
# <a name="togglebutton-styles-and-templates"></a><span data-ttu-id="095de-102">ToggleButton-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="095de-102">ToggleButton Styles and Templates</span></span>

<span data-ttu-id="095de-103">In diesem Thema werden die <xref:System.Windows.Controls.Primitives.ToggleButton> Stile und Vorlagen für das Steuerelement beschrieben.</span><span class="sxs-lookup"><span data-stu-id="095de-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span> <span data-ttu-id="095de-104">Sie können die <xref:System.Windows.Controls.ControlTemplate> Standardeinstellung ändern, um dem Steuerelement ein eindeutiges Erscheinungsbild zu verleihen.</span><span class="sxs-lookup"><span data-stu-id="095de-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="095de-105">Weitere Informationen finden Sie unter [Erstellen einer Vorlage für ein Steuerelement](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="095de-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>

## <a name="togglebutton-parts"></a><span data-ttu-id="095de-106">ToggleButton-Teile</span><span class="sxs-lookup"><span data-stu-id="095de-106">ToggleButton Parts</span></span>

<span data-ttu-id="095de-107">Das <xref:System.Windows.Controls.Primitives.ToggleButton> Steuerelement enthält keine benannten Teile.</span><span class="sxs-lookup"><span data-stu-id="095de-107">The <xref:System.Windows.Controls.Primitives.ToggleButton> control does not have any named parts.</span></span>

## <a name="togglebutton-states"></a><span data-ttu-id="095de-108">ToggleButton-Zustände</span><span class="sxs-lookup"><span data-stu-id="095de-108">ToggleButton States</span></span>

<span data-ttu-id="095de-109">In der folgenden Tabelle sind <xref:System.Windows.Controls.Primitives.ToggleButton> die visuellen Zustände für das Steuerelement aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="095de-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>

|<span data-ttu-id="095de-110">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="095de-110">VisualState Name</span></span>|<span data-ttu-id="095de-111">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="095de-111">VisualStateGroup Name</span></span>|<span data-ttu-id="095de-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="095de-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="095de-113">Normal</span><span class="sxs-lookup"><span data-stu-id="095de-113">Normal</span></span>|<span data-ttu-id="095de-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="095de-114">CommonStates</span></span>|<span data-ttu-id="095de-115">Der Standardzustand</span><span class="sxs-lookup"><span data-stu-id="095de-115">The default state.</span></span>|
|<span data-ttu-id="095de-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="095de-116">MouseOver</span></span>|<span data-ttu-id="095de-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="095de-117">CommonStates</span></span>|<span data-ttu-id="095de-118">Der Mauszeiger ist über dem Steuerelement positioniert.</span><span class="sxs-lookup"><span data-stu-id="095de-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="095de-119">Gedrückt</span><span class="sxs-lookup"><span data-stu-id="095de-119">Pressed</span></span>|<span data-ttu-id="095de-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="095de-120">CommonStates</span></span>|<span data-ttu-id="095de-121">Das Steuerelement wird gedrückt.</span><span class="sxs-lookup"><span data-stu-id="095de-121">The control is pressed.</span></span>|
|<span data-ttu-id="095de-122">Disabled</span><span class="sxs-lookup"><span data-stu-id="095de-122">Disabled</span></span>|<span data-ttu-id="095de-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="095de-123">CommonStates</span></span>|<span data-ttu-id="095de-124">Das Steuerelement ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="095de-124">The control is disabled.</span></span>|
|<span data-ttu-id="095de-125">Mit Fokus</span><span class="sxs-lookup"><span data-stu-id="095de-125">Focused</span></span>|<span data-ttu-id="095de-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="095de-126">FocusStates</span></span>|<span data-ttu-id="095de-127">Der Fokus liegt auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="095de-127">The control has focus.</span></span>|
|<span data-ttu-id="095de-128">Ohne Fokus</span><span class="sxs-lookup"><span data-stu-id="095de-128">Unfocused</span></span>|<span data-ttu-id="095de-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="095de-129">FocusStates</span></span>|<span data-ttu-id="095de-130">Der Fokus liegt nicht auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="095de-130">The control does not have focus.</span></span>|
|<span data-ttu-id="095de-131">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="095de-131">Checked</span></span>|<span data-ttu-id="095de-132">CheckStates</span><span class="sxs-lookup"><span data-stu-id="095de-132">CheckStates</span></span>|<span data-ttu-id="095de-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> ist `true`</span><span class="sxs-lookup"><span data-stu-id="095de-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|
|<span data-ttu-id="095de-134">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="095de-134">Unchecked</span></span>|<span data-ttu-id="095de-135">CheckStates</span><span class="sxs-lookup"><span data-stu-id="095de-135">CheckStates</span></span>|<span data-ttu-id="095de-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> ist `false`</span><span class="sxs-lookup"><span data-stu-id="095de-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|
|<span data-ttu-id="095de-137">Unbestimmten</span><span class="sxs-lookup"><span data-stu-id="095de-137">Indeterminate</span></span>|<span data-ttu-id="095de-138">CheckStates</span><span class="sxs-lookup"><span data-stu-id="095de-138">CheckStates</span></span>|<span data-ttu-id="095de-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> ist `true`, und <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> ist `null`.</span><span class="sxs-lookup"><span data-stu-id="095de-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|
|<span data-ttu-id="095de-140">Gültig</span><span class="sxs-lookup"><span data-stu-id="095de-140">Valid</span></span>|<span data-ttu-id="095de-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="095de-141">ValidationStates</span></span>|<span data-ttu-id="095de-142">Das Steuerelement <xref:System.Windows.Controls.Validation> verwendet die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Klasse, `false`und die angefügte Eigenschaft ist .</span><span class="sxs-lookup"><span data-stu-id="095de-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="095de-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="095de-143">InvalidFocused</span></span>|<span data-ttu-id="095de-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="095de-144">ValidationStates</span></span>|<span data-ttu-id="095de-145">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte `true` Eigenschaft ist und das Steuerelement hat den Fokus.</span><span class="sxs-lookup"><span data-stu-id="095de-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|
|<span data-ttu-id="095de-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="095de-146">InvalidUnfocused</span></span>|<span data-ttu-id="095de-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="095de-147">ValidationStates</span></span>|<span data-ttu-id="095de-148">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte `true` Eigenschaft ist und das Steuerelement hat keinen Fokus.</span><span class="sxs-lookup"><span data-stu-id="095de-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|

> [!NOTE]
> <span data-ttu-id="095de-149">Wenn der visuelle Status Unbestimmt in der Steuerelementvorlage nicht vorhanden ist, wird der visuelle Status Ungeprüft als visueller Standardstatus verwendet.</span><span class="sxs-lookup"><span data-stu-id="095de-149">If the Indeterminate visual state does not exist in your control template, then the Unchecked visual state will be used as default visual state.</span></span>

## <a name="togglebutton-controltemplate-example"></a><span data-ttu-id="095de-150">ToggleButton ControlTemplate Beispiel</span><span class="sxs-lookup"><span data-stu-id="095de-150">ToggleButton ControlTemplate Example</span></span>

<span data-ttu-id="095de-151">Das folgende Beispiel zeigt, <xref:System.Windows.Controls.ControlTemplate> wie <xref:System.Windows.Controls.Primitives.ToggleButton> sie eine für das Steuerelement definieren.</span><span class="sxs-lookup"><span data-stu-id="095de-151">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>

[!code-xaml[ControlTemplateExamples#ToggleButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#togglebutton)]

<span data-ttu-id="095de-152">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="095de-152">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="095de-153">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="095de-153">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="095de-154">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="095de-154">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="095de-155">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="095de-155">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="095de-156">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="095de-156">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="095de-157">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="095de-157">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="095de-158">Erstellen einer Vorlage für ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="095de-158">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
