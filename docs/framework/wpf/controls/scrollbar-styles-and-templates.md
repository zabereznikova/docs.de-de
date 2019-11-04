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
ms.openlocfilehash: f30a0abb3e4252737e513b531b8d5f49a0d47f0b
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458444"
---
# <a name="scrollbar-styles-and-templates"></a><span data-ttu-id="cc9a2-102">ScrollBar-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="cc9a2-102">ScrollBar Styles and Templates</span></span>
<span data-ttu-id="cc9a2-103">In diesem Thema werden die Stile und Vorlagen für das <xref:System.Windows.Controls.Primitives.ScrollBar>-Steuerelement beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cc9a2-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span> <span data-ttu-id="cc9a2-104">Sie können die Standard <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement eine eindeutige Darstellung zu verschaffen.</span><span class="sxs-lookup"><span data-stu-id="cc9a2-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="cc9a2-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="cc9a2-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="scrollbar-parts"></a><span data-ttu-id="cc9a2-106">ScrollBar-Teile</span><span class="sxs-lookup"><span data-stu-id="cc9a2-106">ScrollBar Parts</span></span>  
 <span data-ttu-id="cc9a2-107">In der folgenden Tabelle sind die benannten Teile für das <xref:System.Windows.Controls.Primitives.ScrollBar>-Steuerelement aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="cc9a2-107">The following table lists the named parts for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="cc9a2-108">Segment</span><span class="sxs-lookup"><span data-stu-id="cc9a2-108">Part</span></span>|<span data-ttu-id="cc9a2-109">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="cc9a2-109">Type</span></span>|<span data-ttu-id="cc9a2-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cc9a2-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="cc9a2-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="cc9a2-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="cc9a2-112">Der Container für das Element, das die Position des <xref:System.Windows.Controls.Primitives.ScrollBar>angibt.</span><span class="sxs-lookup"><span data-stu-id="cc9a2-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>|  
  
## <a name="scrollbar-states"></a><span data-ttu-id="cc9a2-113">ScrollBar-Zustände</span><span class="sxs-lookup"><span data-stu-id="cc9a2-113">ScrollBar States</span></span>  
 <span data-ttu-id="cc9a2-114">In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Controls.Primitives.ScrollBar>-Steuerelement aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="cc9a2-114">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="cc9a2-115">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="cc9a2-115">VisualState Name</span></span>|<span data-ttu-id="cc9a2-116">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="cc9a2-116">VisualStateGroup Name</span></span>|<span data-ttu-id="cc9a2-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cc9a2-117">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="cc9a2-118">Normal</span><span class="sxs-lookup"><span data-stu-id="cc9a2-118">Normal</span></span>|<span data-ttu-id="cc9a2-119">CommonStates</span><span class="sxs-lookup"><span data-stu-id="cc9a2-119">CommonStates</span></span>|<span data-ttu-id="cc9a2-120">Der Standardzustand</span><span class="sxs-lookup"><span data-stu-id="cc9a2-120">The default state.</span></span>|  
|<span data-ttu-id="cc9a2-121">MouseOver</span><span class="sxs-lookup"><span data-stu-id="cc9a2-121">MouseOver</span></span>|<span data-ttu-id="cc9a2-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="cc9a2-122">CommonStates</span></span>|<span data-ttu-id="cc9a2-123">Der Mauszeiger befindet sich auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="cc9a2-123">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="cc9a2-124">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="cc9a2-124">Disabled</span></span>|<span data-ttu-id="cc9a2-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="cc9a2-125">CommonStates</span></span>|<span data-ttu-id="cc9a2-126">Das Steuerelement ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="cc9a2-126">The control is disabled.</span></span>|  
|<span data-ttu-id="cc9a2-127">Gültig</span><span class="sxs-lookup"><span data-stu-id="cc9a2-127">Valid</span></span>|<span data-ttu-id="cc9a2-128">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="cc9a2-128">ValidationStates</span></span>|<span data-ttu-id="cc9a2-129">Das-Steuerelement verwendet die <xref:System.Windows.Controls.Validation>-Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false`.</span><span class="sxs-lookup"><span data-stu-id="cc9a2-129">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="cc9a2-130">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="cc9a2-130">InvalidFocused</span></span>|<span data-ttu-id="cc9a2-131">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="cc9a2-131">ValidationStates</span></span>|<span data-ttu-id="cc9a2-132">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, und das Steuerelement besitzt den Fokus.</span><span class="sxs-lookup"><span data-stu-id="cc9a2-132">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="cc9a2-133">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="cc9a2-133">InvalidUnfocused</span></span>|<span data-ttu-id="cc9a2-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="cc9a2-134">ValidationStates</span></span>|<span data-ttu-id="cc9a2-135">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, und das Steuerelement besitzt keinen Fokus.</span><span class="sxs-lookup"><span data-stu-id="cc9a2-135">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="scrollbar-controltemplate-example"></a><span data-ttu-id="cc9a2-136">ScrollBar ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="cc9a2-136">ScrollBar ControlTemplate Example</span></span>  
 <span data-ttu-id="cc9a2-137">Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.ControlTemplate> für das <xref:System.Windows.Controls.Primitives.ScrollBar>-Steuerelement definiert wird.</span><span class="sxs-lookup"><span data-stu-id="cc9a2-137">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#scrollbar)]  
  
 <span data-ttu-id="cc9a2-138">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="cc9a2-138">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="cc9a2-139">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="cc9a2-139">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc9a2-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cc9a2-140">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="cc9a2-141">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="cc9a2-141">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="cc9a2-142">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="cc9a2-142">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="cc9a2-143">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="cc9a2-143">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="cc9a2-144">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="cc9a2-144">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
