---
title: ScrollBar-Stile und -Vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], ScrollBar
- ControlTemplate [WPF], ScrollBar
- states [WPF], ScrollBar
- ScrollBar [WPF], styles and templates
- templates [WPF], ScrollBar
- parts [WPF], ScrollBar
ms.assetid: 066ea45a-e27d-43b0-adfe-cce6934c22f5
ms.openlocfilehash: 016556fb825ddf60af7dc572d6fda7323b9bb09d
ms.sourcegitcommit: 3eeea78f52ca771087a6736c23f74600cc662658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/31/2019
ms.locfileid: "68671984"
---
# <a name="scrollbar-styles-and-templates"></a><span data-ttu-id="247ba-102">ScrollBar-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="247ba-102">ScrollBar Styles and Templates</span></span>
<span data-ttu-id="247ba-103">In diesem Thema werden die Stile und Vorlagen für <xref:System.Windows.Controls.Primitives.ScrollBar> das-Steuerelement beschrieben.</span><span class="sxs-lookup"><span data-stu-id="247ba-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span> <span data-ttu-id="247ba-104">Sie können die Standardeinstellung <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement eine eindeutige Darstellung zu verschaffen.</span><span class="sxs-lookup"><span data-stu-id="247ba-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="247ba-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="247ba-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="scrollbar-parts"></a><span data-ttu-id="247ba-106">ScrollBar-Teile</span><span class="sxs-lookup"><span data-stu-id="247ba-106">ScrollBar Parts</span></span>  
 <span data-ttu-id="247ba-107">In der folgenden Tabelle sind die benannten Teile für <xref:System.Windows.Controls.Primitives.ScrollBar> das-Steuerelement aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="247ba-107">The following table lists the named parts for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="247ba-108">Segment</span><span class="sxs-lookup"><span data-stu-id="247ba-108">Part</span></span>|<span data-ttu-id="247ba-109">Typ</span><span class="sxs-lookup"><span data-stu-id="247ba-109">Type</span></span>|<span data-ttu-id="247ba-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="247ba-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="247ba-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="247ba-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="247ba-112">Der Container für das Element, das die Position <xref:System.Windows.Controls.Primitives.ScrollBar>der angibt.</span><span class="sxs-lookup"><span data-stu-id="247ba-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>|  
  
## <a name="scrollbar-states"></a><span data-ttu-id="247ba-113">ScrollBar-Zustände</span><span class="sxs-lookup"><span data-stu-id="247ba-113">ScrollBar States</span></span>  
 <span data-ttu-id="247ba-114">In der folgenden Tabelle werden die visuellen Zustände für <xref:System.Windows.Controls.Primitives.ScrollBar> das-Steuerelement aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="247ba-114">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="247ba-115">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="247ba-115">VisualState Name</span></span>|<span data-ttu-id="247ba-116">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="247ba-116">VisualStateGroup Name</span></span>|<span data-ttu-id="247ba-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="247ba-117">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="247ba-118">Normal</span><span class="sxs-lookup"><span data-stu-id="247ba-118">Normal</span></span>|<span data-ttu-id="247ba-119">CommonStates</span><span class="sxs-lookup"><span data-stu-id="247ba-119">CommonStates</span></span>|<span data-ttu-id="247ba-120">Der Standardzustand</span><span class="sxs-lookup"><span data-stu-id="247ba-120">The default state.</span></span>|  
|<span data-ttu-id="247ba-121">MouseOver</span><span class="sxs-lookup"><span data-stu-id="247ba-121">MouseOver</span></span>|<span data-ttu-id="247ba-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="247ba-122">CommonStates</span></span>|<span data-ttu-id="247ba-123">Der Mauszeiger befindet sich auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="247ba-123">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="247ba-124">Disabled</span><span class="sxs-lookup"><span data-stu-id="247ba-124">Disabled</span></span>|<span data-ttu-id="247ba-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="247ba-125">CommonStates</span></span>|<span data-ttu-id="247ba-126">Das Steuerelement ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="247ba-126">The control is disabled.</span></span>|  
|<span data-ttu-id="247ba-127">Gültig</span><span class="sxs-lookup"><span data-stu-id="247ba-127">Valid</span></span>|<span data-ttu-id="247ba-128">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="247ba-128">ValidationStates</span></span>|<span data-ttu-id="247ba-129">Das Steuerelement verwendet <xref:System.Windows.Controls.Validation> die-Klasse <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> , und die `false`angefügte-Eigenschaft ist.</span><span class="sxs-lookup"><span data-stu-id="247ba-129">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="247ba-130">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="247ba-130">InvalidFocused</span></span>|<span data-ttu-id="247ba-131">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="247ba-131">ValidationStates</span></span>|<span data-ttu-id="247ba-132">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte- `true` Eigenschaft ist, und das Steuerelement besitzt den Fokus.</span><span class="sxs-lookup"><span data-stu-id="247ba-132">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="247ba-133">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="247ba-133">InvalidUnfocused</span></span>|<span data-ttu-id="247ba-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="247ba-134">ValidationStates</span></span>|<span data-ttu-id="247ba-135">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte- `true` Eigenschaft ist, und das Steuerelement besitzt keinen Fokus.</span><span class="sxs-lookup"><span data-stu-id="247ba-135">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="scrollbar-controltemplate-example"></a><span data-ttu-id="247ba-136">ScrollBar ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="247ba-136">ScrollBar ControlTemplate Example</span></span>  
 <span data-ttu-id="247ba-137">Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.ControlTemplate> für das <xref:System.Windows.Controls.Primitives.ScrollBar> -Steuerelement definiert wird.</span><span class="sxs-lookup"><span data-stu-id="247ba-137">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#scrollbar)]  
  
 <span data-ttu-id="247ba-138">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="247ba-138">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="247ba-139">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="247ba-139">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="247ba-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="247ba-140">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="247ba-141">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="247ba-141">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="247ba-142">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="247ba-142">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="247ba-143">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="247ba-143">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="247ba-144">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="247ba-144">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
