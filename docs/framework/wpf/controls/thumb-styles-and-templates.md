---
title: Thumb-Stile und -Vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], Thumb
- styles [WPF], Thumb
- templates [WPF], Thumb
- Thumb [WPF], styles and templates
- ControlTemplate [WPF], Thumb
- parts [WPF], Thumb
ms.assetid: 86a49235-62d9-414e-923e-53126e3f930a
ms.openlocfilehash: 0d0d88e3b527beacfa5f879027e696aa75b18147
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283683"
---
# <a name="thumb-styles-and-templates"></a><span data-ttu-id="5e21a-102">Thumb-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="5e21a-102">Thumb Styles and Templates</span></span>

<span data-ttu-id="5e21a-103">In diesem Thema werden die Stile und Vorlagen für das <xref:System.Windows.Controls.Primitives.Thumb>-Steuerelement beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5e21a-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span> <span data-ttu-id="5e21a-104">Sie können die Standard <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement eine eindeutige Darstellung zu verschaffen.</span><span class="sxs-lookup"><span data-stu-id="5e21a-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="5e21a-105">Weitere Informationen finden Sie unter [Erstellen einer Vorlage für ein-Steuer](../../../desktop-wpf/themes/how-to-create-apply-template.md)Element.</span><span class="sxs-lookup"><span data-stu-id="5e21a-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>

## <a name="thumb-parts"></a><span data-ttu-id="5e21a-106">Thumb-Teile</span><span class="sxs-lookup"><span data-stu-id="5e21a-106">Thumb Parts</span></span>

<span data-ttu-id="5e21a-107">Das <xref:System.Windows.Controls.Primitives.Thumb>-Steuerelement verfügt über keine benannten Teile.</span><span class="sxs-lookup"><span data-stu-id="5e21a-107">The <xref:System.Windows.Controls.Primitives.Thumb> control does not have any named parts.</span></span>

## <a name="thumb-states"></a><span data-ttu-id="5e21a-108">Thumb-Zustände</span><span class="sxs-lookup"><span data-stu-id="5e21a-108">Thumb States</span></span>

<span data-ttu-id="5e21a-109">In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Controls.Primitives.Thumb>-Steuerelement aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="5e21a-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span>

|<span data-ttu-id="5e21a-110">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="5e21a-110">VisualState Name</span></span>|<span data-ttu-id="5e21a-111">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="5e21a-111">VisualStateGroup Name</span></span>|<span data-ttu-id="5e21a-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5e21a-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="5e21a-113">Normal</span><span class="sxs-lookup"><span data-stu-id="5e21a-113">Normal</span></span>|<span data-ttu-id="5e21a-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="5e21a-114">CommonStates</span></span>|<span data-ttu-id="5e21a-115">Der Standardzustand</span><span class="sxs-lookup"><span data-stu-id="5e21a-115">The default state.</span></span>|
|<span data-ttu-id="5e21a-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="5e21a-116">MouseOver</span></span>|<span data-ttu-id="5e21a-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="5e21a-117">CommonStates</span></span>|<span data-ttu-id="5e21a-118">Der Mauszeiger ist über dem Steuerelement positioniert.</span><span class="sxs-lookup"><span data-stu-id="5e21a-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="5e21a-119">Gedrückt</span><span class="sxs-lookup"><span data-stu-id="5e21a-119">Pressed</span></span>|<span data-ttu-id="5e21a-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="5e21a-120">CommonStates</span></span>|<span data-ttu-id="5e21a-121">Das Steuerelement wird gedrückt.</span><span class="sxs-lookup"><span data-stu-id="5e21a-121">The control is pressed.</span></span>|
|<span data-ttu-id="5e21a-122">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="5e21a-122">Disabled</span></span>|<span data-ttu-id="5e21a-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="5e21a-123">CommonStates</span></span>|<span data-ttu-id="5e21a-124">Das Steuerelement ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="5e21a-124">The control is disabled.</span></span>|
|<span data-ttu-id="5e21a-125">Mit Fokus</span><span class="sxs-lookup"><span data-stu-id="5e21a-125">Focused</span></span>|<span data-ttu-id="5e21a-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="5e21a-126">FocusStates</span></span>|<span data-ttu-id="5e21a-127">Der Fokus liegt auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="5e21a-127">The control has focus.</span></span>|
|<span data-ttu-id="5e21a-128">Ohne Fokus</span><span class="sxs-lookup"><span data-stu-id="5e21a-128">Unfocused</span></span>|<span data-ttu-id="5e21a-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="5e21a-129">FocusStates</span></span>|<span data-ttu-id="5e21a-130">Der Fokus liegt nicht auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="5e21a-130">The control does not have focus.</span></span>|
|<span data-ttu-id="5e21a-131">Gültig</span><span class="sxs-lookup"><span data-stu-id="5e21a-131">Valid</span></span>|<span data-ttu-id="5e21a-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5e21a-132">ValidationStates</span></span>|<span data-ttu-id="5e21a-133">Das-Steuerelement verwendet die <xref:System.Windows.Controls.Validation>-Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false`.</span><span class="sxs-lookup"><span data-stu-id="5e21a-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="5e21a-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="5e21a-134">InvalidFocused</span></span>|<span data-ttu-id="5e21a-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5e21a-135">ValidationStates</span></span>|<span data-ttu-id="5e21a-136">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true` hat, dass das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="5e21a-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="5e21a-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="5e21a-137">InvalidUnfocused</span></span>|<span data-ttu-id="5e21a-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5e21a-138">ValidationStates</span></span>|<span data-ttu-id="5e21a-139">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, wenn das Steuerelement keinen Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="5e21a-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="thumb-controltemplate-example"></a><span data-ttu-id="5e21a-140">Thumb ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="5e21a-140">Thumb ControlTemplate Example</span></span>

<span data-ttu-id="5e21a-141">Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.ControlTemplate> für das <xref:System.Windows.Controls.Primitives.Thumb>-Steuerelement definiert wird.</span><span class="sxs-lookup"><span data-stu-id="5e21a-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span>

[!code-xaml[ControlTemplateExamples#Thumb](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#thumb)]

<span data-ttu-id="5e21a-142">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="5e21a-142">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="5e21a-143">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="5e21a-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="5e21a-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e21a-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="5e21a-145">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="5e21a-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="5e21a-146">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="5e21a-146">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="5e21a-147">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="5e21a-147">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="5e21a-148">Erstellen einer Vorlage für ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="5e21a-148">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
