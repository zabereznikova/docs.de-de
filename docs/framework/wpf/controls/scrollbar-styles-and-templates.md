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
ms.openlocfilehash: 22b2206067302f621a94a1e9abca1607792b3393
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052884"
---
# <a name="scrollbar-styles-and-templates"></a><span data-ttu-id="88bb5-102">ScrollBar-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="88bb5-102">ScrollBar Styles and Templates</span></span>
<span data-ttu-id="88bb5-103">In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.Primitives.ScrollBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="88bb5-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span> <span data-ttu-id="88bb5-104">Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement eine unverwechselbare Darstellung verleihen.</span><span class="sxs-lookup"><span data-stu-id="88bb5-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="88bb5-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="88bb5-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="scrollbar-parts"></a><span data-ttu-id="88bb5-106">ScrollBar-Teile</span><span class="sxs-lookup"><span data-stu-id="88bb5-106">ScrollBar Parts</span></span>  
 <span data-ttu-id="88bb5-107">Die folgende Tabelle enthält die benannten Teile für den <xref:System.Windows.Controls.Primitives.ScrollBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="88bb5-107">The following table lists the named parts for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="88bb5-108">Segment</span><span class="sxs-lookup"><span data-stu-id="88bb5-108">Part</span></span>|<span data-ttu-id="88bb5-109">Typ</span><span class="sxs-lookup"><span data-stu-id="88bb5-109">Type</span></span>|<span data-ttu-id="88bb5-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="88bb5-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="88bb5-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="88bb5-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="88bb5-112">Der Container für das Element, das die Position der gibt an die <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="88bb5-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>|  
  
## <a name="scrollbar-states"></a><span data-ttu-id="88bb5-113">ScrollBar-Zustände</span><span class="sxs-lookup"><span data-stu-id="88bb5-113">ScrollBar States</span></span>  
 <span data-ttu-id="88bb5-114">Die folgende Tabelle enthält die visuellen Zustände für die <xref:System.Windows.Controls.Primitives.ScrollBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="88bb5-114">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="88bb5-115">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="88bb5-115">VisualState Name</span></span>|<span data-ttu-id="88bb5-116">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="88bb5-116">VisualStateGroup Name</span></span>|<span data-ttu-id="88bb5-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="88bb5-117">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="88bb5-118">Normal</span><span class="sxs-lookup"><span data-stu-id="88bb5-118">Normal</span></span>|<span data-ttu-id="88bb5-119">CommonStates</span><span class="sxs-lookup"><span data-stu-id="88bb5-119">CommonStates</span></span>|<span data-ttu-id="88bb5-120">Der Standardzustand</span><span class="sxs-lookup"><span data-stu-id="88bb5-120">The default state.</span></span>|  
|<span data-ttu-id="88bb5-121">MouseOver</span><span class="sxs-lookup"><span data-stu-id="88bb5-121">MouseOver</span></span>|<span data-ttu-id="88bb5-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="88bb5-122">CommonStates</span></span>|<span data-ttu-id="88bb5-123">Der Mauszeiger befindet sich auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="88bb5-123">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="88bb5-124">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="88bb5-124">Disabled</span></span>|<span data-ttu-id="88bb5-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="88bb5-125">CommonStates</span></span>|<span data-ttu-id="88bb5-126">Das Steuerelement ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="88bb5-126">The control is disabled.</span></span>|  
|<span data-ttu-id="88bb5-127">Gültig</span><span class="sxs-lookup"><span data-stu-id="88bb5-127">Valid</span></span>|<span data-ttu-id="88bb5-128">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="88bb5-128">ValidationStates</span></span>|<span data-ttu-id="88bb5-129">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="88bb5-129">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="88bb5-130">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="88bb5-130">InvalidFocused</span></span>|<span data-ttu-id="88bb5-131">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="88bb5-131">ValidationStates</span></span>|<span data-ttu-id="88bb5-132">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="88bb5-132">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="88bb5-133">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="88bb5-133">InvalidUnfocused</span></span>|<span data-ttu-id="88bb5-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="88bb5-134">ValidationStates</span></span>|<span data-ttu-id="88bb5-135">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement keinen Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="88bb5-135">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="scrollbar-controltemplate-example"></a><span data-ttu-id="88bb5-136">ScrollBar-ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="88bb5-136">ScrollBar ControlTemplate Example</span></span>  
 <span data-ttu-id="88bb5-137">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.Primitives.ScrollBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="88bb5-137">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#scrollbar)]  
  
 <span data-ttu-id="88bb5-138">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="88bb5-138">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="88bb5-139">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="88bb5-139">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88bb5-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="88bb5-140">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="88bb5-141">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="88bb5-141">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="88bb5-142">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="88bb5-142">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="88bb5-143">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="88bb5-143">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="88bb5-144">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="88bb5-144">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
