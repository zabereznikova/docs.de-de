---
title: Slider-Stile und -Vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], Slider
- states [WPF], Slider
- Slider [WPF], styles and templates
- styles [WPF], Slider
- templates [WPF], Slider
- ControlTemplate [WPF], Slider
ms.assetid: d89aa97b-075a-4752-9c41-9679df65c491
ms.openlocfilehash: f533142d5ba202bd4aaf628487eaaa2a18a535d0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283389"
---
# <a name="slider-styles-and-templates"></a><span data-ttu-id="2ba29-102">Slider-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="2ba29-102">Slider Styles and Templates</span></span>
<span data-ttu-id="2ba29-103">In diesem Thema werden die Stile und Vorlagen für das <xref:System.Windows.Controls.Slider>-Steuerelement beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2ba29-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Slider> control.</span></span> <span data-ttu-id="2ba29-104">Sie können die Standard <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement eine eindeutige Darstellung zu verschaffen.</span><span class="sxs-lookup"><span data-stu-id="2ba29-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="2ba29-105">Weitere Informationen finden Sie unter [Erstellen einer Vorlage für ein-Steuer](../../../desktop-wpf/themes/how-to-create-apply-template.md)Element.</span><span class="sxs-lookup"><span data-stu-id="2ba29-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="slider-parts"></a><span data-ttu-id="2ba29-106">Schieberegler-Teile</span><span class="sxs-lookup"><span data-stu-id="2ba29-106">Slider Parts</span></span>  
 <span data-ttu-id="2ba29-107">In der folgenden Tabelle sind die benannten Teile für das <xref:System.Windows.Controls.Slider>-Steuerelement aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="2ba29-107">The following table lists the named parts for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
|<span data-ttu-id="2ba29-108">Segment</span><span class="sxs-lookup"><span data-stu-id="2ba29-108">Part</span></span>|<span data-ttu-id="2ba29-109">Typ</span><span class="sxs-lookup"><span data-stu-id="2ba29-109">Type</span></span>|<span data-ttu-id="2ba29-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2ba29-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="2ba29-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="2ba29-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="2ba29-112">Der Container für das Element, das die Position des <xref:System.Windows.Controls.Slider>angibt.</span><span class="sxs-lookup"><span data-stu-id="2ba29-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Slider>.</span></span>|  
|<span data-ttu-id="2ba29-113">PART_SelectionRange</span><span class="sxs-lookup"><span data-stu-id="2ba29-113">PART_SelectionRange</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="2ba29-114">Das Element, das einen Auswahlbereich entlang der <xref:System.Windows.Controls.Slider>anzeigt.</span><span class="sxs-lookup"><span data-stu-id="2ba29-114">The element that displays a selection range along the <xref:System.Windows.Controls.Slider>.</span></span>  <span data-ttu-id="2ba29-115">Der Auswahlbereich ist nur sichtbar, wenn die <xref:System.Windows.Controls.Slider.IsSelectionRangeEnabled%2A>-Eigenschaft `true`ist.</span><span class="sxs-lookup"><span data-stu-id="2ba29-115">The selection range is visible only if the <xref:System.Windows.Controls.Slider.IsSelectionRangeEnabled%2A> property is `true`.</span></span>|  
  
## <a name="slider-states"></a><span data-ttu-id="2ba29-116">Schieberegler-Zustände</span><span class="sxs-lookup"><span data-stu-id="2ba29-116">Slider States</span></span>  
 <span data-ttu-id="2ba29-117">In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Controls.Slider>-Steuerelement aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="2ba29-117">The following table lists the visual states for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
|<span data-ttu-id="2ba29-118">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="2ba29-118">VisualState Name</span></span>|<span data-ttu-id="2ba29-119">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="2ba29-119">VisualStateGroup Name</span></span>|<span data-ttu-id="2ba29-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2ba29-120">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="2ba29-121">Normal</span><span class="sxs-lookup"><span data-stu-id="2ba29-121">Normal</span></span>|<span data-ttu-id="2ba29-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="2ba29-122">CommonStates</span></span>|<span data-ttu-id="2ba29-123">Der Standardzustand</span><span class="sxs-lookup"><span data-stu-id="2ba29-123">The default state.</span></span>|  
|<span data-ttu-id="2ba29-124">MouseOver</span><span class="sxs-lookup"><span data-stu-id="2ba29-124">MouseOver</span></span>|<span data-ttu-id="2ba29-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="2ba29-125">CommonStates</span></span>|<span data-ttu-id="2ba29-126">Der Mauszeiger ist über dem Steuerelement positioniert.</span><span class="sxs-lookup"><span data-stu-id="2ba29-126">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="2ba29-127">Disabled</span><span class="sxs-lookup"><span data-stu-id="2ba29-127">Disabled</span></span>|<span data-ttu-id="2ba29-128">CommonStates</span><span class="sxs-lookup"><span data-stu-id="2ba29-128">CommonStates</span></span>|<span data-ttu-id="2ba29-129">Das Steuerelement ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="2ba29-129">The control is disabled.</span></span>|  
|<span data-ttu-id="2ba29-130">Mit Fokus</span><span class="sxs-lookup"><span data-stu-id="2ba29-130">Focused</span></span>|<span data-ttu-id="2ba29-131">FocusStates</span><span class="sxs-lookup"><span data-stu-id="2ba29-131">FocusStates</span></span>|<span data-ttu-id="2ba29-132">Der Fokus liegt auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="2ba29-132">The control has focus.</span></span>|  
|<span data-ttu-id="2ba29-133">Ohne Fokus</span><span class="sxs-lookup"><span data-stu-id="2ba29-133">Unfocused</span></span>|<span data-ttu-id="2ba29-134">FocusStates</span><span class="sxs-lookup"><span data-stu-id="2ba29-134">FocusStates</span></span>|<span data-ttu-id="2ba29-135">Der Fokus liegt nicht auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="2ba29-135">The control does not have focus.</span></span>|  
|<span data-ttu-id="2ba29-136">Gültig</span><span class="sxs-lookup"><span data-stu-id="2ba29-136">Valid</span></span>|<span data-ttu-id="2ba29-137">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="2ba29-137">ValidationStates</span></span>|<span data-ttu-id="2ba29-138">Das-Steuerelement verwendet die <xref:System.Windows.Controls.Validation>-Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false`.</span><span class="sxs-lookup"><span data-stu-id="2ba29-138">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="2ba29-139">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="2ba29-139">InvalidFocused</span></span>|<span data-ttu-id="2ba29-140">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="2ba29-140">ValidationStates</span></span>|<span data-ttu-id="2ba29-141">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true` hat, dass das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="2ba29-141">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="2ba29-142">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="2ba29-142">InvalidUnfocused</span></span>|<span data-ttu-id="2ba29-143">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="2ba29-143">ValidationStates</span></span>|<span data-ttu-id="2ba29-144">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, wenn das Steuerelement keinen Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="2ba29-144">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="slider-controltemplate-example"></a><span data-ttu-id="2ba29-145">Beispiel für Schieberegler-ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="2ba29-145">Slider ControlTemplate Example</span></span>  
 <span data-ttu-id="2ba29-146">Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.ControlTemplate> für das <xref:System.Windows.Controls.Slider>-Steuerelement definiert wird.</span><span class="sxs-lookup"><span data-stu-id="2ba29-146">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Slider](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#slider)]  
  
 <span data-ttu-id="2ba29-147">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="2ba29-147">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="2ba29-148">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="2ba29-148">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ba29-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ba29-149">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="2ba29-150">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="2ba29-150">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="2ba29-151">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="2ba29-151">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="2ba29-152">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="2ba29-152">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="2ba29-153">Erstellen einer Vorlage für ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="2ba29-153">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
