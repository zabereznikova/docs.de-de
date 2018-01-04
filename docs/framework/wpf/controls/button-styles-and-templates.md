---
title: Button-Stile und -Vorlagen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- states [WPF], Button
- parts [WPF], Button
- styles [WPF], Button
- Button [WPF], styles and templates
- templates [WPF], Button
- ControlTemplate [WPF], Button
ms.assetid: e223c759-f8c4-4717-acfb-b1e40bdf5f3b
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7bea309cea0ed6d21b747f31794f1ebb440bf102
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="button-styles-and-templates"></a><span data-ttu-id="f3c90-102">Button-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="f3c90-102">Button Styles and Templates</span></span>
<span data-ttu-id="f3c90-103">In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.Button> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="f3c90-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="f3c90-104">Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement ein einzigartiges aussehen zu verleihen.</span><span class="sxs-lookup"><span data-stu-id="f3c90-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="f3c90-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="f3c90-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="button-parts"></a><span data-ttu-id="f3c90-106">Button-Teile</span><span class="sxs-lookup"><span data-stu-id="f3c90-106">Button Parts</span></span>  
 <span data-ttu-id="f3c90-107">Die <xref:System.Windows.Controls.Button> Steuerelement enthält keine benannten Teile.</span><span class="sxs-lookup"><span data-stu-id="f3c90-107">The <xref:System.Windows.Controls.Button> control does not have any named parts.</span></span>  
  
## <a name="button-states"></a><span data-ttu-id="f3c90-108">Schaltflächenzustände</span><span class="sxs-lookup"><span data-stu-id="f3c90-108">Button States</span></span>  
 <span data-ttu-id="f3c90-109">Die folgende Tabelle enthält die visueller Zustände für die <xref:System.Windows.Controls.Button> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="f3c90-109">The following table lists the visual states for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
|<span data-ttu-id="f3c90-110">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="f3c90-110">VisualState Name</span></span>|<span data-ttu-id="f3c90-111">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="f3c90-111">VisualStateGroup Name</span></span>|<span data-ttu-id="f3c90-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f3c90-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="f3c90-113">Normal</span><span class="sxs-lookup"><span data-stu-id="f3c90-113">Normal</span></span>|<span data-ttu-id="f3c90-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="f3c90-114">CommonStates</span></span>|<span data-ttu-id="f3c90-115">Der Standardzustand</span><span class="sxs-lookup"><span data-stu-id="f3c90-115">The default state.</span></span>|  
|<span data-ttu-id="f3c90-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="f3c90-116">MouseOver</span></span>|<span data-ttu-id="f3c90-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="f3c90-117">CommonStates</span></span>|<span data-ttu-id="f3c90-118">Der Mauszeiger ist über dem Steuerelement positioniert.</span><span class="sxs-lookup"><span data-stu-id="f3c90-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="f3c90-119">Gedrückt</span><span class="sxs-lookup"><span data-stu-id="f3c90-119">Pressed</span></span>|<span data-ttu-id="f3c90-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="f3c90-120">CommonStates</span></span>|<span data-ttu-id="f3c90-121">Das Steuerelement wird gedrückt.</span><span class="sxs-lookup"><span data-stu-id="f3c90-121">The control is pressed.</span></span>|  
|<span data-ttu-id="f3c90-122">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="f3c90-122">Disabled</span></span>|<span data-ttu-id="f3c90-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="f3c90-123">CommonStates</span></span>|<span data-ttu-id="f3c90-124">Das Steuerelement ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f3c90-124">The control is disabled.</span></span>|  
|<span data-ttu-id="f3c90-125">Focused</span><span class="sxs-lookup"><span data-stu-id="f3c90-125">Focused</span></span>|<span data-ttu-id="f3c90-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="f3c90-126">FocusStates</span></span>|<span data-ttu-id="f3c90-127">Der Fokus liegt auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="f3c90-127">The control has focus.</span></span>|  
|<span data-ttu-id="f3c90-128">Ohne Fokus</span><span class="sxs-lookup"><span data-stu-id="f3c90-128">Unfocused</span></span>|<span data-ttu-id="f3c90-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="f3c90-129">FocusStates</span></span>|<span data-ttu-id="f3c90-130">Der Fokus liegt nicht auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="f3c90-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="f3c90-131">Gültig</span><span class="sxs-lookup"><span data-stu-id="f3c90-131">Valid</span></span>|<span data-ttu-id="f3c90-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f3c90-132">ValidationStates</span></span>|<span data-ttu-id="f3c90-133">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="f3c90-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="f3c90-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="f3c90-134">InvalidFocused</span></span>|<span data-ttu-id="f3c90-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f3c90-135">ValidationStates</span></span>|<span data-ttu-id="f3c90-136">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` weist das Steuerelement den Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="f3c90-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="f3c90-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="f3c90-137">InvalidUnfocused</span></span>|<span data-ttu-id="f3c90-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f3c90-138">ValidationStates</span></span>|<span data-ttu-id="f3c90-139">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement verfügt nicht über den Fokus.</span><span class="sxs-lookup"><span data-stu-id="f3c90-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="button-controltemplate-example"></a><span data-ttu-id="f3c90-140">Beispiel zum Button-ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="f3c90-140">Button ControlTemplate Example</span></span>  
 <span data-ttu-id="f3c90-141">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.Button> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="f3c90-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Button](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#button)]  
  
 <span data-ttu-id="f3c90-142">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="f3c90-142">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="f3c90-143">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="f3c90-143">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3c90-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f3c90-144">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="f3c90-145">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="f3c90-145">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="f3c90-146">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="f3c90-146">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="f3c90-147">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="f3c90-147">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="f3c90-148">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="f3c90-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
