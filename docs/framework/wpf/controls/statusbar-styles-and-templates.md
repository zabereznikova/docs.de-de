---
title: StatusBar-Stile und -Vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], StatusBar
- styles [WPF], StatusBar
- templates [WPF], StatusBar
- states [WPF], StatusBar
- parts [WPF], StatusBar
- StatusBar [WPF], styles and templates
ms.assetid: 9f5e1c25-81eb-4756-a0ac-d9e1fbe33ee2
ms.openlocfilehash: 11fa3ab6edd62f0b5484d9ccf76c101d04be353c
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2018
ms.locfileid: "34457864"
---
# <a name="statusbar-styles-and-templates"></a><span data-ttu-id="14fec-102">StatusBar-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="14fec-102">StatusBar Styles and Templates</span></span>
<span data-ttu-id="14fec-103">In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.Primitives.StatusBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="14fec-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span> <span data-ttu-id="14fec-104">Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement ein einzigartiges aussehen zu verleihen.</span><span class="sxs-lookup"><span data-stu-id="14fec-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="14fec-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="14fec-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="statusbar-parts"></a><span data-ttu-id="14fec-106">StatusBar-Teile</span><span class="sxs-lookup"><span data-stu-id="14fec-106">StatusBar Parts</span></span>  
 <span data-ttu-id="14fec-107">Die <xref:System.Windows.Controls.Primitives.StatusBar> Steuerelement enthält keine benannten Teile.</span><span class="sxs-lookup"><span data-stu-id="14fec-107">The <xref:System.Windows.Controls.Primitives.StatusBar> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="14fec-108">StatusBar-Zustände</span><span class="sxs-lookup"><span data-stu-id="14fec-108">StatusBar States</span></span>  
 <span data-ttu-id="14fec-109">Die folgende Tabelle enthält die visueller Zustände für die <xref:System.Windows.Controls.Primitives.StatusBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="14fec-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
|<span data-ttu-id="14fec-110">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="14fec-110">VisualState Name</span></span>|<span data-ttu-id="14fec-111">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="14fec-111">VisualStateGroup Name</span></span>|<span data-ttu-id="14fec-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="14fec-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="14fec-113">Gültig</span><span class="sxs-lookup"><span data-stu-id="14fec-113">Valid</span></span>|<span data-ttu-id="14fec-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="14fec-114">ValidationStates</span></span>|<span data-ttu-id="14fec-115">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="14fec-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="14fec-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="14fec-116">InvalidFocused</span></span>|<span data-ttu-id="14fec-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="14fec-117">ValidationStates</span></span>|<span data-ttu-id="14fec-118">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` weist das Steuerelement den Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="14fec-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="14fec-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="14fec-119">InvalidUnfocused</span></span>|<span data-ttu-id="14fec-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="14fec-120">ValidationStates</span></span>|<span data-ttu-id="14fec-121">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement verfügt nicht über den Fokus.</span><span class="sxs-lookup"><span data-stu-id="14fec-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbaritem-parts"></a><span data-ttu-id="14fec-122">StatusBarItem-Teile</span><span class="sxs-lookup"><span data-stu-id="14fec-122">StatusBarItem Parts</span></span>  
 <span data-ttu-id="14fec-123">Die <xref:System.Windows.Controls.Primitives.StatusBarItem> Steuerelement enthält keine benannten Teile.</span><span class="sxs-lookup"><span data-stu-id="14fec-123">The <xref:System.Windows.Controls.Primitives.StatusBarItem> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="14fec-124">StatusBar-Zustände</span><span class="sxs-lookup"><span data-stu-id="14fec-124">StatusBar States</span></span>  
 <span data-ttu-id="14fec-125">Die folgende Tabelle enthält die visueller Zustände für die <xref:System.Windows.Controls.Primitives.StatusBarItem> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="14fec-125">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBarItem> control.</span></span>  
  
|<span data-ttu-id="14fec-126">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="14fec-126">VisualState Name</span></span>|<span data-ttu-id="14fec-127">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="14fec-127">VisualStateGroup Name</span></span>|<span data-ttu-id="14fec-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="14fec-128">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="14fec-129">Gültig</span><span class="sxs-lookup"><span data-stu-id="14fec-129">Valid</span></span>|<span data-ttu-id="14fec-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="14fec-130">ValidationStates</span></span>|<span data-ttu-id="14fec-131">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="14fec-131">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="14fec-132">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="14fec-132">InvalidFocused</span></span>|<span data-ttu-id="14fec-133">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="14fec-133">ValidationStates</span></span>|<span data-ttu-id="14fec-134">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` weist das Steuerelement den Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="14fec-134">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="14fec-135">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="14fec-135">InvalidUnfocused</span></span>|<span data-ttu-id="14fec-136">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="14fec-136">ValidationStates</span></span>|<span data-ttu-id="14fec-137">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement verfügt nicht über den Fokus.</span><span class="sxs-lookup"><span data-stu-id="14fec-137">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbar-controltemplate-example"></a><span data-ttu-id="14fec-138">Beispiel für StatusBar-ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="14fec-138">StatusBar ControlTemplate Example</span></span>  
 <span data-ttu-id="14fec-139">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.Primitives.StatusBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="14fec-139">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#StatusBar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/statusbar.xaml#statusbar)]  
  
 <span data-ttu-id="14fec-140">Die <xref:System.Windows.Controls.ControlTemplate> verwendet wird, eine oder mehrere der folgenden Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="14fec-140">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="14fec-141">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="14fec-141">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14fec-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="14fec-142">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="14fec-143">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="14fec-143">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="14fec-144">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="14fec-144">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="14fec-145">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="14fec-145">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="14fec-146">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="14fec-146">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
