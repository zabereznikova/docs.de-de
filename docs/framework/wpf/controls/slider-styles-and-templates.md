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
ms.openlocfilehash: 385a69ad2bd17ae4c51437245915109aad446bdf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61970975"
---
# <a name="slider-styles-and-templates"></a><span data-ttu-id="0bdf6-102">Slider-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="0bdf6-102">Slider Styles and Templates</span></span>
<span data-ttu-id="0bdf6-103">In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.Slider> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0bdf6-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Slider> control.</span></span> <span data-ttu-id="0bdf6-104">Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement eine unverwechselbare Darstellung verleihen.</span><span class="sxs-lookup"><span data-stu-id="0bdf6-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="0bdf6-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="0bdf6-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="slider-parts"></a><span data-ttu-id="0bdf6-106">Slider-Teile</span><span class="sxs-lookup"><span data-stu-id="0bdf6-106">Slider Parts</span></span>  
 <span data-ttu-id="0bdf6-107">Die folgende Tabelle enthält die benannten Teile für den <xref:System.Windows.Controls.Slider> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0bdf6-107">The following table lists the named parts for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
|<span data-ttu-id="0bdf6-108">Segment</span><span class="sxs-lookup"><span data-stu-id="0bdf6-108">Part</span></span>|<span data-ttu-id="0bdf6-109">Typ</span><span class="sxs-lookup"><span data-stu-id="0bdf6-109">Type</span></span>|<span data-ttu-id="0bdf6-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0bdf6-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="0bdf6-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="0bdf6-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="0bdf6-112">Der Container für das Element, das die Position der gibt an die <xref:System.Windows.Controls.Slider>.</span><span class="sxs-lookup"><span data-stu-id="0bdf6-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Slider>.</span></span>|  
|<span data-ttu-id="0bdf6-113">PART_SelectionRange</span><span class="sxs-lookup"><span data-stu-id="0bdf6-113">PART_SelectionRange</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="0bdf6-114">Das Element, das einen Auswahlbereich anzeigt der <xref:System.Windows.Controls.Slider>.</span><span class="sxs-lookup"><span data-stu-id="0bdf6-114">The element that displays a selection range along the <xref:System.Windows.Controls.Slider>.</span></span>  <span data-ttu-id="0bdf6-115">Auswahlbereich sichtbar ist nur möglich, wenn die <xref:System.Windows.Controls.Slider.IsSelectionRangeEnabled%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="0bdf6-115">The selection range is visible only if the <xref:System.Windows.Controls.Slider.IsSelectionRangeEnabled%2A> property is `true`.</span></span>|  
  
## <a name="slider-states"></a><span data-ttu-id="0bdf6-116">Slider-Zustände</span><span class="sxs-lookup"><span data-stu-id="0bdf6-116">Slider States</span></span>  
 <span data-ttu-id="0bdf6-117">Die folgende Tabelle enthält die visuellen Zustände für die <xref:System.Windows.Controls.Slider> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0bdf6-117">The following table lists the visual states for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
|<span data-ttu-id="0bdf6-118">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="0bdf6-118">VisualState Name</span></span>|<span data-ttu-id="0bdf6-119">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="0bdf6-119">VisualStateGroup Name</span></span>|<span data-ttu-id="0bdf6-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0bdf6-120">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="0bdf6-121">Normal</span><span class="sxs-lookup"><span data-stu-id="0bdf6-121">Normal</span></span>|<span data-ttu-id="0bdf6-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="0bdf6-122">CommonStates</span></span>|<span data-ttu-id="0bdf6-123">Der Standardzustand</span><span class="sxs-lookup"><span data-stu-id="0bdf6-123">The default state.</span></span>|  
|<span data-ttu-id="0bdf6-124">MouseOver</span><span class="sxs-lookup"><span data-stu-id="0bdf6-124">MouseOver</span></span>|<span data-ttu-id="0bdf6-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="0bdf6-125">CommonStates</span></span>|<span data-ttu-id="0bdf6-126">Der Mauszeiger befindet sich auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0bdf6-126">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="0bdf6-127">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="0bdf6-127">Disabled</span></span>|<span data-ttu-id="0bdf6-128">CommonStates</span><span class="sxs-lookup"><span data-stu-id="0bdf6-128">CommonStates</span></span>|<span data-ttu-id="0bdf6-129">Das Steuerelement ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="0bdf6-129">The control is disabled.</span></span>|  
|<span data-ttu-id="0bdf6-130">Focused</span><span class="sxs-lookup"><span data-stu-id="0bdf6-130">Focused</span></span>|<span data-ttu-id="0bdf6-131">FocusStates</span><span class="sxs-lookup"><span data-stu-id="0bdf6-131">FocusStates</span></span>|<span data-ttu-id="0bdf6-132">Der Fokus liegt auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0bdf6-132">The control has focus.</span></span>|  
|<span data-ttu-id="0bdf6-133">Ohne Fokus</span><span class="sxs-lookup"><span data-stu-id="0bdf6-133">Unfocused</span></span>|<span data-ttu-id="0bdf6-134">FocusStates</span><span class="sxs-lookup"><span data-stu-id="0bdf6-134">FocusStates</span></span>|<span data-ttu-id="0bdf6-135">Der Fokus liegt nicht auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0bdf6-135">The control does not have focus.</span></span>|  
|<span data-ttu-id="0bdf6-136">Gültig</span><span class="sxs-lookup"><span data-stu-id="0bdf6-136">Valid</span></span>|<span data-ttu-id="0bdf6-137">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0bdf6-137">ValidationStates</span></span>|<span data-ttu-id="0bdf6-138">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="0bdf6-138">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="0bdf6-139">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="0bdf6-139">InvalidFocused</span></span>|<span data-ttu-id="0bdf6-140">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0bdf6-140">ValidationStates</span></span>|<span data-ttu-id="0bdf6-141">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="0bdf6-141">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="0bdf6-142">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="0bdf6-142">InvalidUnfocused</span></span>|<span data-ttu-id="0bdf6-143">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0bdf6-143">ValidationStates</span></span>|<span data-ttu-id="0bdf6-144">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement keinen Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="0bdf6-144">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="slider-controltemplate-example"></a><span data-ttu-id="0bdf6-145">Schieberegler-ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="0bdf6-145">Slider ControlTemplate Example</span></span>  
 <span data-ttu-id="0bdf6-146">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.Slider> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0bdf6-146">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Slider](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#slider)]  
  
 <span data-ttu-id="0bdf6-147">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="0bdf6-147">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="0bdf6-148">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="0bdf6-148">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bdf6-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0bdf6-149">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="0bdf6-150">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="0bdf6-150">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="0bdf6-151">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="0bdf6-151">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="0bdf6-152">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="0bdf6-152">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="0bdf6-153">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="0bdf6-153">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
