---
title: Button-Stile und -Vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], Button
- parts [WPF], Button
- styles [WPF], Button
- Button [WPF], styles and templates
- templates [WPF], Button
- ControlTemplate [WPF], Button
ms.assetid: e223c759-f8c4-4717-acfb-b1e40bdf5f3b
ms.openlocfilehash: ef9f85848ebdda9dc4ae15d0f54847eacd46e24d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283582"
---
# <a name="button-styles-and-templates"></a><span data-ttu-id="98bef-102">Button-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="98bef-102">Button Styles and Templates</span></span>
<span data-ttu-id="98bef-103">In diesem Thema werden die Stile und Vorlagen für das <xref:System.Windows.Controls.Button>-Steuerelement beschrieben.</span><span class="sxs-lookup"><span data-stu-id="98bef-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="98bef-104">Sie können die Standard <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement eine eindeutige Darstellung zu verschaffen.</span><span class="sxs-lookup"><span data-stu-id="98bef-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="98bef-105">Weitere Informationen finden Sie unter [Erstellen einer Vorlage für ein-Steuer](../../../desktop-wpf/themes/how-to-create-apply-template.md)Element.</span><span class="sxs-lookup"><span data-stu-id="98bef-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="button-parts"></a><span data-ttu-id="98bef-106">Schaltflächen Teile</span><span class="sxs-lookup"><span data-stu-id="98bef-106">Button Parts</span></span>  
 <span data-ttu-id="98bef-107">Das <xref:System.Windows.Controls.Button>-Steuerelement verfügt über keine benannten Teile.</span><span class="sxs-lookup"><span data-stu-id="98bef-107">The <xref:System.Windows.Controls.Button> control does not have any named parts.</span></span>  
  
## <a name="button-states"></a><span data-ttu-id="98bef-108">Schaltflächen Zustände</span><span class="sxs-lookup"><span data-stu-id="98bef-108">Button States</span></span>  
 <span data-ttu-id="98bef-109">In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Controls.Button>-Steuerelement aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="98bef-109">The following table lists the visual states for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
|<span data-ttu-id="98bef-110">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="98bef-110">VisualState Name</span></span>|<span data-ttu-id="98bef-111">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="98bef-111">VisualStateGroup Name</span></span>|<span data-ttu-id="98bef-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="98bef-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="98bef-113">Normal</span><span class="sxs-lookup"><span data-stu-id="98bef-113">Normal</span></span>|<span data-ttu-id="98bef-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="98bef-114">CommonStates</span></span>|<span data-ttu-id="98bef-115">Der Standardzustand</span><span class="sxs-lookup"><span data-stu-id="98bef-115">The default state.</span></span>|  
|<span data-ttu-id="98bef-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="98bef-116">MouseOver</span></span>|<span data-ttu-id="98bef-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="98bef-117">CommonStates</span></span>|<span data-ttu-id="98bef-118">Der Mauszeiger ist über dem Steuerelement positioniert.</span><span class="sxs-lookup"><span data-stu-id="98bef-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="98bef-119">Gedrückt</span><span class="sxs-lookup"><span data-stu-id="98bef-119">Pressed</span></span>|<span data-ttu-id="98bef-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="98bef-120">CommonStates</span></span>|<span data-ttu-id="98bef-121">Das Steuerelement wird gedrückt.</span><span class="sxs-lookup"><span data-stu-id="98bef-121">The control is pressed.</span></span>|  
|<span data-ttu-id="98bef-122">Disabled</span><span class="sxs-lookup"><span data-stu-id="98bef-122">Disabled</span></span>|<span data-ttu-id="98bef-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="98bef-123">CommonStates</span></span>|<span data-ttu-id="98bef-124">Das Steuerelement ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="98bef-124">The control is disabled.</span></span>|  
|<span data-ttu-id="98bef-125">Mit Fokus</span><span class="sxs-lookup"><span data-stu-id="98bef-125">Focused</span></span>|<span data-ttu-id="98bef-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="98bef-126">FocusStates</span></span>|<span data-ttu-id="98bef-127">Der Fokus liegt auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="98bef-127">The control has focus.</span></span>|  
|<span data-ttu-id="98bef-128">Ohne Fokus</span><span class="sxs-lookup"><span data-stu-id="98bef-128">Unfocused</span></span>|<span data-ttu-id="98bef-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="98bef-129">FocusStates</span></span>|<span data-ttu-id="98bef-130">Der Fokus liegt nicht auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="98bef-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="98bef-131">Gültig</span><span class="sxs-lookup"><span data-stu-id="98bef-131">Valid</span></span>|<span data-ttu-id="98bef-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="98bef-132">ValidationStates</span></span>|<span data-ttu-id="98bef-133">Das-Steuerelement verwendet die <xref:System.Windows.Controls.Validation>-Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false`.</span><span class="sxs-lookup"><span data-stu-id="98bef-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="98bef-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="98bef-134">InvalidFocused</span></span>|<span data-ttu-id="98bef-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="98bef-135">ValidationStates</span></span>|<span data-ttu-id="98bef-136">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, und das Steuerelement besitzt den Fokus.</span><span class="sxs-lookup"><span data-stu-id="98bef-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="98bef-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="98bef-137">InvalidUnfocused</span></span>|<span data-ttu-id="98bef-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="98bef-138">ValidationStates</span></span>|<span data-ttu-id="98bef-139">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, und das Steuerelement besitzt keinen Fokus.</span><span class="sxs-lookup"><span data-stu-id="98bef-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="button-controltemplate-example"></a><span data-ttu-id="98bef-140">Schaltflächen-ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="98bef-140">Button ControlTemplate Example</span></span>  
 <span data-ttu-id="98bef-141">Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.ControlTemplate> für das <xref:System.Windows.Controls.Button>-Steuerelement definiert wird.</span><span class="sxs-lookup"><span data-stu-id="98bef-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Button](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#button)]  
  
 <span data-ttu-id="98bef-142">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="98bef-142">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="98bef-143">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="98bef-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98bef-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="98bef-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="98bef-145">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="98bef-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="98bef-146">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="98bef-146">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="98bef-147">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="98bef-147">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="98bef-148">Erstellen einer Vorlage für ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="98bef-148">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
