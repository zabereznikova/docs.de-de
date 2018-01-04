---
title: ScrollBar-Stile und -Vorlagen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- styles [WPF], ScrollBar
- ControlTemplate [WPF], ScrollBar
- states [WPF], ScrollBar
- ScrollBar [WPF], styles and templates
- templates [WPF], ScrollBar
- parts [WPF], ScrollBar
ms.assetid: 066ea45a-e27d-43b0-adfe-cce6934c22f5
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 14b40a458b271a4f8b88c167367771235f25c7a3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="scrollbar-styles-and-templates"></a><span data-ttu-id="61da7-102">ScrollBar-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="61da7-102">ScrollBar Styles and Templates</span></span>
<span data-ttu-id="61da7-103">In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.Primitives.ScrollBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="61da7-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span> <span data-ttu-id="61da7-104">Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement ein einzigartiges aussehen zu verleihen.</span><span class="sxs-lookup"><span data-stu-id="61da7-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="61da7-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="61da7-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="scrollbar-parts"></a><span data-ttu-id="61da7-106">ScrollBar-Teile</span><span class="sxs-lookup"><span data-stu-id="61da7-106">ScrollBar Parts</span></span>  
 <span data-ttu-id="61da7-107">Die folgende Tabelle enthält die benannten Teile für die <xref:System.Windows.Controls.Primitives.ScrollBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="61da7-107">The following table lists the named parts for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="61da7-108">Segment</span><span class="sxs-lookup"><span data-stu-id="61da7-108">Part</span></span>|<span data-ttu-id="61da7-109">Typ</span><span class="sxs-lookup"><span data-stu-id="61da7-109">Type</span></span>|<span data-ttu-id="61da7-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="61da7-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="61da7-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="61da7-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="61da7-112">Der Container für das Element, das die Position des gibt an, die <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="61da7-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>|  
  
## <a name="scrollbar-states"></a><span data-ttu-id="61da7-113">ScrollBar-Zustände</span><span class="sxs-lookup"><span data-stu-id="61da7-113">ScrollBar States</span></span>  
 <span data-ttu-id="61da7-114">Die folgende Tabelle enthält die visueller Zustände für die <xref:System.Windows.Controls.Primitives.ScrollBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="61da7-114">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="61da7-115">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="61da7-115">VisualState Name</span></span>|<span data-ttu-id="61da7-116">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="61da7-116">VisualStateGroup Name</span></span>|<span data-ttu-id="61da7-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="61da7-117">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="61da7-118">Normal</span><span class="sxs-lookup"><span data-stu-id="61da7-118">Normal</span></span>|<span data-ttu-id="61da7-119">CommonStates</span><span class="sxs-lookup"><span data-stu-id="61da7-119">CommonStates</span></span>|<span data-ttu-id="61da7-120">Der Standardzustand</span><span class="sxs-lookup"><span data-stu-id="61da7-120">The default state.</span></span>|  
|<span data-ttu-id="61da7-121">MouseOver</span><span class="sxs-lookup"><span data-stu-id="61da7-121">MouseOver</span></span>|<span data-ttu-id="61da7-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="61da7-122">CommonStates</span></span>|<span data-ttu-id="61da7-123">Der Mauszeiger befindet sich auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="61da7-123">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="61da7-124">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="61da7-124">Disabled</span></span>|<span data-ttu-id="61da7-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="61da7-125">CommonStates</span></span>|<span data-ttu-id="61da7-126">Das Steuerelement ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="61da7-126">The control is disabled.</span></span>|  
|<span data-ttu-id="61da7-127">Gültig</span><span class="sxs-lookup"><span data-stu-id="61da7-127">Valid</span></span>|<span data-ttu-id="61da7-128">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="61da7-128">ValidationStates</span></span>|<span data-ttu-id="61da7-129">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="61da7-129">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="61da7-130">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="61da7-130">InvalidFocused</span></span>|<span data-ttu-id="61da7-131">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="61da7-131">ValidationStates</span></span>|<span data-ttu-id="61da7-132">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` weist das Steuerelement den Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="61da7-132">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="61da7-133">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="61da7-133">InvalidUnfocused</span></span>|<span data-ttu-id="61da7-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="61da7-134">ValidationStates</span></span>|<span data-ttu-id="61da7-135">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement verfügt nicht über den Fokus.</span><span class="sxs-lookup"><span data-stu-id="61da7-135">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="scrollbar-controltemplate-example"></a><span data-ttu-id="61da7-136">Beispiel für ScrollBar-ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="61da7-136">ScrollBar ControlTemplate Example</span></span>  
 <span data-ttu-id="61da7-137">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.Primitives.ScrollBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="61da7-137">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollBar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#scrollbar)]  
  
 <span data-ttu-id="61da7-138">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="61da7-138">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="61da7-139">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="61da7-139">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61da7-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="61da7-140">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="61da7-141">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="61da7-141">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="61da7-142">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="61da7-142">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="61da7-143">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="61da7-143">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="61da7-144">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="61da7-144">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
