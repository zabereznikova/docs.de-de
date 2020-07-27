---
title: Button-Stile und -Vorlagen
description: Erfahren Sie mehr über Stile und Vorlagen für das Windows Presentation Foundation Button-Steuerelement. Ändern Sie ControlTemplate, um dem Steuerelement eine eindeutige Darstellung zu verschaffen.
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], Button
- parts [WPF], Button
- styles [WPF], Button
- Button [WPF], styles and templates
- templates [WPF], Button
- ControlTemplate [WPF], Button
ms.assetid: e223c759-f8c4-4717-acfb-b1e40bdf5f3b
ms.openlocfilehash: 11509adeef397f26eb040e6e98d0edb333b2515f
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166264"
---
# <a name="button-styles-and-templates"></a><span data-ttu-id="ee2c7-104">Button-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="ee2c7-104">Button Styles and Templates</span></span>
<span data-ttu-id="ee2c7-105">In diesem Thema werden die Stile und Vorlagen für das-Steuerelement beschrieben <xref:System.Windows.Controls.Button> .</span><span class="sxs-lookup"><span data-stu-id="ee2c7-105">This topic describes the styles and templates for the <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="ee2c7-106">Sie können die Standardeinstellung ändern <xref:System.Windows.Controls.ControlTemplate> , um dem Steuerelement eine eindeutige Darstellung zu verschaffen.</span><span class="sxs-lookup"><span data-stu-id="ee2c7-106">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="ee2c7-107">Weitere Informationen finden Sie unter [Erstellen einer Vorlage für ein-Steuer](../../../desktop-wpf/themes/how-to-create-apply-template.md)Element.</span><span class="sxs-lookup"><span data-stu-id="ee2c7-107">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="button-parts"></a><span data-ttu-id="ee2c7-108">Schaltflächen Teile</span><span class="sxs-lookup"><span data-stu-id="ee2c7-108">Button Parts</span></span>  
 <span data-ttu-id="ee2c7-109">Das- <xref:System.Windows.Controls.Button> Steuerelement verfügt über keine benannten Teile.</span><span class="sxs-lookup"><span data-stu-id="ee2c7-109">The <xref:System.Windows.Controls.Button> control does not have any named parts.</span></span>  
  
## <a name="button-states"></a><span data-ttu-id="ee2c7-110">Schaltflächen Zustände</span><span class="sxs-lookup"><span data-stu-id="ee2c7-110">Button States</span></span>  
 <span data-ttu-id="ee2c7-111">In der folgenden Tabelle werden die visuellen Zustände für das-Steuerelement aufgelistet <xref:System.Windows.Controls.Button> .</span><span class="sxs-lookup"><span data-stu-id="ee2c7-111">The following table lists the visual states for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
|<span data-ttu-id="ee2c7-112">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="ee2c7-112">VisualState Name</span></span>|<span data-ttu-id="ee2c7-113">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="ee2c7-113">VisualStateGroup Name</span></span>|<span data-ttu-id="ee2c7-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ee2c7-114">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="ee2c7-115">Normal</span><span class="sxs-lookup"><span data-stu-id="ee2c7-115">Normal</span></span>|<span data-ttu-id="ee2c7-116">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ee2c7-116">CommonStates</span></span>|<span data-ttu-id="ee2c7-117">Der Standardzustand</span><span class="sxs-lookup"><span data-stu-id="ee2c7-117">The default state.</span></span>|  
|<span data-ttu-id="ee2c7-118">MouseOver</span><span class="sxs-lookup"><span data-stu-id="ee2c7-118">MouseOver</span></span>|<span data-ttu-id="ee2c7-119">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ee2c7-119">CommonStates</span></span>|<span data-ttu-id="ee2c7-120">Der Mauszeiger ist über dem Steuerelement positioniert.</span><span class="sxs-lookup"><span data-stu-id="ee2c7-120">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="ee2c7-121">Gedrückt</span><span class="sxs-lookup"><span data-stu-id="ee2c7-121">Pressed</span></span>|<span data-ttu-id="ee2c7-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ee2c7-122">CommonStates</span></span>|<span data-ttu-id="ee2c7-123">Das Steuerelement wird gedrückt.</span><span class="sxs-lookup"><span data-stu-id="ee2c7-123">The control is pressed.</span></span>|  
|<span data-ttu-id="ee2c7-124">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="ee2c7-124">Disabled</span></span>|<span data-ttu-id="ee2c7-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ee2c7-125">CommonStates</span></span>|<span data-ttu-id="ee2c7-126">Das Steuerelement ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="ee2c7-126">The control is disabled.</span></span>|  
|<span data-ttu-id="ee2c7-127">Focused</span><span class="sxs-lookup"><span data-stu-id="ee2c7-127">Focused</span></span>|<span data-ttu-id="ee2c7-128">FocusStates</span><span class="sxs-lookup"><span data-stu-id="ee2c7-128">FocusStates</span></span>|<span data-ttu-id="ee2c7-129">Der Fokus liegt auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ee2c7-129">The control has focus.</span></span>|  
|<span data-ttu-id="ee2c7-130">Ohne Fokus</span><span class="sxs-lookup"><span data-stu-id="ee2c7-130">Unfocused</span></span>|<span data-ttu-id="ee2c7-131">FocusStates</span><span class="sxs-lookup"><span data-stu-id="ee2c7-131">FocusStates</span></span>|<span data-ttu-id="ee2c7-132">Der Fokus liegt nicht auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ee2c7-132">The control does not have focus.</span></span>|  
|<span data-ttu-id="ee2c7-133">Gültig</span><span class="sxs-lookup"><span data-stu-id="ee2c7-133">Valid</span></span>|<span data-ttu-id="ee2c7-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ee2c7-134">ValidationStates</span></span>|<span data-ttu-id="ee2c7-135">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> -Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false` .</span><span class="sxs-lookup"><span data-stu-id="ee2c7-135">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="ee2c7-136">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="ee2c7-136">InvalidFocused</span></span>|<span data-ttu-id="ee2c7-137">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ee2c7-137">ValidationStates</span></span>|<span data-ttu-id="ee2c7-138">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist, `true` und das Steuerelement besitzt den Fokus.</span><span class="sxs-lookup"><span data-stu-id="ee2c7-138">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="ee2c7-139">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="ee2c7-139">InvalidUnfocused</span></span>|<span data-ttu-id="ee2c7-140">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ee2c7-140">ValidationStates</span></span>|<span data-ttu-id="ee2c7-141">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist, `true` und das Steuerelement besitzt keinen Fokus.</span><span class="sxs-lookup"><span data-stu-id="ee2c7-141">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="button-controltemplate-example"></a><span data-ttu-id="ee2c7-142">Schaltflächen-ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="ee2c7-142">Button ControlTemplate Example</span></span>  
 <span data-ttu-id="ee2c7-143">Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.ControlTemplate> für das-Steuerelement definiert wird <xref:System.Windows.Controls.Button> .</span><span class="sxs-lookup"><span data-stu-id="ee2c7-143">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Button](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#button)]  
  
 <span data-ttu-id="ee2c7-144">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="ee2c7-144">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="ee2c7-145">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="ee2c7-145">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee2c7-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ee2c7-146">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="ee2c7-147">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="ee2c7-147">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="ee2c7-148">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="ee2c7-148">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="ee2c7-149">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="ee2c7-149">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="ee2c7-150">Erstellen einer Vorlage für ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ee2c7-150">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
