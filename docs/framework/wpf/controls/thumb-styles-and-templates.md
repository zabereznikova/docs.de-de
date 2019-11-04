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
ms.openlocfilehash: c2114a02016db96d898a394b6892b6d3042d81ff
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458235"
---
# <a name="thumb-styles-and-templates"></a><span data-ttu-id="85844-102">Thumb-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="85844-102">Thumb Styles and Templates</span></span>

<span data-ttu-id="85844-103">In diesem Thema werden die Stile und Vorlagen für das <xref:System.Windows.Controls.Primitives.Thumb>-Steuerelement beschrieben.</span><span class="sxs-lookup"><span data-stu-id="85844-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span> <span data-ttu-id="85844-104">Sie können die Standard <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement eine eindeutige Darstellung zu verschaffen.</span><span class="sxs-lookup"><span data-stu-id="85844-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="85844-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="85844-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>

## <a name="thumb-parts"></a><span data-ttu-id="85844-106">Thumb-Teile</span><span class="sxs-lookup"><span data-stu-id="85844-106">Thumb Parts</span></span>

<span data-ttu-id="85844-107">Das <xref:System.Windows.Controls.Primitives.Thumb>-Steuerelement verfügt über keine benannten Teile.</span><span class="sxs-lookup"><span data-stu-id="85844-107">The <xref:System.Windows.Controls.Primitives.Thumb> control does not have any named parts.</span></span>

## <a name="thumb-states"></a><span data-ttu-id="85844-108">Thumb-Zustände</span><span class="sxs-lookup"><span data-stu-id="85844-108">Thumb States</span></span>

<span data-ttu-id="85844-109">In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Controls.Primitives.Thumb>-Steuerelement aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="85844-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span>

|<span data-ttu-id="85844-110">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="85844-110">VisualState Name</span></span>|<span data-ttu-id="85844-111">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="85844-111">VisualStateGroup Name</span></span>|<span data-ttu-id="85844-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="85844-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="85844-113">Normal</span><span class="sxs-lookup"><span data-stu-id="85844-113">Normal</span></span>|<span data-ttu-id="85844-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="85844-114">CommonStates</span></span>|<span data-ttu-id="85844-115">Der Standardzustand</span><span class="sxs-lookup"><span data-stu-id="85844-115">The default state.</span></span>|
|<span data-ttu-id="85844-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="85844-116">MouseOver</span></span>|<span data-ttu-id="85844-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="85844-117">CommonStates</span></span>|<span data-ttu-id="85844-118">Der Mauszeiger befindet sich auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="85844-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="85844-119">Gedrückt</span><span class="sxs-lookup"><span data-stu-id="85844-119">Pressed</span></span>|<span data-ttu-id="85844-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="85844-120">CommonStates</span></span>|<span data-ttu-id="85844-121">Das Steuerelement wird gedrückt.</span><span class="sxs-lookup"><span data-stu-id="85844-121">The control is pressed.</span></span>|
|<span data-ttu-id="85844-122">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="85844-122">Disabled</span></span>|<span data-ttu-id="85844-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="85844-123">CommonStates</span></span>|<span data-ttu-id="85844-124">Das Steuerelement ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="85844-124">The control is disabled.</span></span>|
|<span data-ttu-id="85844-125">Mit Fokus</span><span class="sxs-lookup"><span data-stu-id="85844-125">Focused</span></span>|<span data-ttu-id="85844-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="85844-126">FocusStates</span></span>|<span data-ttu-id="85844-127">Der Fokus liegt auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="85844-127">The control has focus.</span></span>|
|<span data-ttu-id="85844-128">Ohne Fokus</span><span class="sxs-lookup"><span data-stu-id="85844-128">Unfocused</span></span>|<span data-ttu-id="85844-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="85844-129">FocusStates</span></span>|<span data-ttu-id="85844-130">Der Fokus liegt nicht auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="85844-130">The control does not have focus.</span></span>|
|<span data-ttu-id="85844-131">Gültig</span><span class="sxs-lookup"><span data-stu-id="85844-131">Valid</span></span>|<span data-ttu-id="85844-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="85844-132">ValidationStates</span></span>|<span data-ttu-id="85844-133">Das-Steuerelement verwendet die <xref:System.Windows.Controls.Validation>-Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false`.</span><span class="sxs-lookup"><span data-stu-id="85844-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="85844-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="85844-134">InvalidFocused</span></span>|<span data-ttu-id="85844-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="85844-135">ValidationStates</span></span>|<span data-ttu-id="85844-136">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true` hat, dass das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="85844-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="85844-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="85844-137">InvalidUnfocused</span></span>|<span data-ttu-id="85844-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="85844-138">ValidationStates</span></span>|<span data-ttu-id="85844-139">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, wenn das Steuerelement keinen Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="85844-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="thumb-controltemplate-example"></a><span data-ttu-id="85844-140">Thumb ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="85844-140">Thumb ControlTemplate Example</span></span>

<span data-ttu-id="85844-141">Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.ControlTemplate> für das <xref:System.Windows.Controls.Primitives.Thumb>-Steuerelement definiert wird.</span><span class="sxs-lookup"><span data-stu-id="85844-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span>

[!code-xaml[ControlTemplateExamples#Thumb](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#thumb)]

<span data-ttu-id="85844-142">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="85844-142">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="85844-143">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="85844-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="85844-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="85844-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="85844-145">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="85844-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="85844-146">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="85844-146">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="85844-147">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="85844-147">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="85844-148">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="85844-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
