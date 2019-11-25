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
ms.openlocfilehash: 7093a78555aefd73f9bb05c0a7b5fab6b66176fc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283418"
---
# <a name="scrollbar-styles-and-templates"></a><span data-ttu-id="7a9fe-102">ScrollBar-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="7a9fe-102">ScrollBar Styles and Templates</span></span>
<span data-ttu-id="7a9fe-103">In diesem Thema werden die Stile und Vorlagen für das <xref:System.Windows.Controls.Primitives.ScrollBar>-Steuerelement beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7a9fe-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span> <span data-ttu-id="7a9fe-104">Sie können die Standard <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement eine eindeutige Darstellung zu verschaffen.</span><span class="sxs-lookup"><span data-stu-id="7a9fe-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="7a9fe-105">Weitere Informationen finden Sie unter [Erstellen einer Vorlage für ein-Steuer](../../../desktop-wpf/themes/how-to-create-apply-template.md)Element.</span><span class="sxs-lookup"><span data-stu-id="7a9fe-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="scrollbar-parts"></a><span data-ttu-id="7a9fe-106">ScrollBar-Teile</span><span class="sxs-lookup"><span data-stu-id="7a9fe-106">ScrollBar Parts</span></span>  
 <span data-ttu-id="7a9fe-107">In der folgenden Tabelle sind die benannten Teile für das <xref:System.Windows.Controls.Primitives.ScrollBar>-Steuerelement aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="7a9fe-107">The following table lists the named parts for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="7a9fe-108">Segment</span><span class="sxs-lookup"><span data-stu-id="7a9fe-108">Part</span></span>|<span data-ttu-id="7a9fe-109">Typ</span><span class="sxs-lookup"><span data-stu-id="7a9fe-109">Type</span></span>|<span data-ttu-id="7a9fe-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7a9fe-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="7a9fe-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="7a9fe-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="7a9fe-112">Der Container für das Element, das die Position des <xref:System.Windows.Controls.Primitives.ScrollBar>angibt.</span><span class="sxs-lookup"><span data-stu-id="7a9fe-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>|  
  
## <a name="scrollbar-states"></a><span data-ttu-id="7a9fe-113">ScrollBar-Zustände</span><span class="sxs-lookup"><span data-stu-id="7a9fe-113">ScrollBar States</span></span>  
 <span data-ttu-id="7a9fe-114">In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Controls.Primitives.ScrollBar>-Steuerelement aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="7a9fe-114">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="7a9fe-115">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="7a9fe-115">VisualState Name</span></span>|<span data-ttu-id="7a9fe-116">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="7a9fe-116">VisualStateGroup Name</span></span>|<span data-ttu-id="7a9fe-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7a9fe-117">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="7a9fe-118">Normal</span><span class="sxs-lookup"><span data-stu-id="7a9fe-118">Normal</span></span>|<span data-ttu-id="7a9fe-119">CommonStates</span><span class="sxs-lookup"><span data-stu-id="7a9fe-119">CommonStates</span></span>|<span data-ttu-id="7a9fe-120">Der Standardzustand</span><span class="sxs-lookup"><span data-stu-id="7a9fe-120">The default state.</span></span>|  
|<span data-ttu-id="7a9fe-121">MouseOver</span><span class="sxs-lookup"><span data-stu-id="7a9fe-121">MouseOver</span></span>|<span data-ttu-id="7a9fe-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="7a9fe-122">CommonStates</span></span>|<span data-ttu-id="7a9fe-123">Der Mauszeiger ist über dem Steuerelement positioniert.</span><span class="sxs-lookup"><span data-stu-id="7a9fe-123">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="7a9fe-124">Disabled</span><span class="sxs-lookup"><span data-stu-id="7a9fe-124">Disabled</span></span>|<span data-ttu-id="7a9fe-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="7a9fe-125">CommonStates</span></span>|<span data-ttu-id="7a9fe-126">Das Steuerelement ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="7a9fe-126">The control is disabled.</span></span>|  
|<span data-ttu-id="7a9fe-127">Gültig</span><span class="sxs-lookup"><span data-stu-id="7a9fe-127">Valid</span></span>|<span data-ttu-id="7a9fe-128">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="7a9fe-128">ValidationStates</span></span>|<span data-ttu-id="7a9fe-129">Das-Steuerelement verwendet die <xref:System.Windows.Controls.Validation>-Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false`.</span><span class="sxs-lookup"><span data-stu-id="7a9fe-129">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="7a9fe-130">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="7a9fe-130">InvalidFocused</span></span>|<span data-ttu-id="7a9fe-131">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="7a9fe-131">ValidationStates</span></span>|<span data-ttu-id="7a9fe-132">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, und das Steuerelement besitzt den Fokus.</span><span class="sxs-lookup"><span data-stu-id="7a9fe-132">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="7a9fe-133">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="7a9fe-133">InvalidUnfocused</span></span>|<span data-ttu-id="7a9fe-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="7a9fe-134">ValidationStates</span></span>|<span data-ttu-id="7a9fe-135">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, und das Steuerelement besitzt keinen Fokus.</span><span class="sxs-lookup"><span data-stu-id="7a9fe-135">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="scrollbar-controltemplate-example"></a><span data-ttu-id="7a9fe-136">ScrollBar ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="7a9fe-136">ScrollBar ControlTemplate Example</span></span>  
 <span data-ttu-id="7a9fe-137">Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.ControlTemplate> für das <xref:System.Windows.Controls.Primitives.ScrollBar>-Steuerelement definiert wird.</span><span class="sxs-lookup"><span data-stu-id="7a9fe-137">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#scrollbar)]  
  
 <span data-ttu-id="7a9fe-138">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="7a9fe-138">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="7a9fe-139">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="7a9fe-139">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a9fe-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7a9fe-140">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="7a9fe-141">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="7a9fe-141">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="7a9fe-142">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="7a9fe-142">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="7a9fe-143">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="7a9fe-143">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="7a9fe-144">Erstellen einer Vorlage für ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="7a9fe-144">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
