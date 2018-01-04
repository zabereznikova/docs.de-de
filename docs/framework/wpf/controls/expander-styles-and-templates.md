---
title: Expander-Stile und -Vorlagen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- styles [WPF], Expander
- ControlTemplate [WPF], Expander
- templates [WPF], Expander
- Expander [WPF], styles and templates
- states [WPF], Expander
- parts [WPF], Expander
ms.assetid: da2e5a1c-5230-4c21-98a5-59c7895facd7
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 999b081d80680069d4c6fdf908814889afa60870
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="expander-styles-and-templates"></a><span data-ttu-id="e8335-102">Expander-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="e8335-102">Expander Styles and Templates</span></span>
<span data-ttu-id="e8335-103">In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.Expander> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="e8335-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Expander> control.</span></span> <span data-ttu-id="e8335-104">Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement ein einzigartiges aussehen zu verleihen.</span><span class="sxs-lookup"><span data-stu-id="e8335-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="e8335-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="e8335-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="expander-parts"></a><span data-ttu-id="e8335-106">Expander-Teile</span><span class="sxs-lookup"><span data-stu-id="e8335-106">Expander Parts</span></span>  
 <span data-ttu-id="e8335-107">Die <xref:System.Windows.Controls.Expander> Steuerelement enthält keine benannten Teile.</span><span class="sxs-lookup"><span data-stu-id="e8335-107">The <xref:System.Windows.Controls.Expander> control does not have any named parts.</span></span>  
  
## <a name="expander-states"></a><span data-ttu-id="e8335-108">Expander-Zustände</span><span class="sxs-lookup"><span data-stu-id="e8335-108">Expander States</span></span>  
 <span data-ttu-id="e8335-109">Die folgende Tabelle enthält die visueller Zustände für die <xref:System.Windows.Controls.Expander> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="e8335-109">The following table lists the visual states for the <xref:System.Windows.Controls.Expander> control.</span></span>  
  
|<span data-ttu-id="e8335-110">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="e8335-110">VisualState Name</span></span>|<span data-ttu-id="e8335-111">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="e8335-111">VisualStateGroup Name</span></span>|<span data-ttu-id="e8335-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e8335-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="e8335-113">Normal</span><span class="sxs-lookup"><span data-stu-id="e8335-113">Normal</span></span>|<span data-ttu-id="e8335-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="e8335-114">CommonStates</span></span>|<span data-ttu-id="e8335-115">Der Standardzustand</span><span class="sxs-lookup"><span data-stu-id="e8335-115">The default state.</span></span>|  
|<span data-ttu-id="e8335-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="e8335-116">MouseOver</span></span>|<span data-ttu-id="e8335-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="e8335-117">CommonStates</span></span>|<span data-ttu-id="e8335-118">Der Mauszeiger befindet sich auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="e8335-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="e8335-119">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="e8335-119">Disabled</span></span>|<span data-ttu-id="e8335-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="e8335-120">CommonStates</span></span>|<span data-ttu-id="e8335-121">Das Steuerelement ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="e8335-121">The control is disabled.</span></span>|  
|<span data-ttu-id="e8335-122">Focused</span><span class="sxs-lookup"><span data-stu-id="e8335-122">Focused</span></span>|<span data-ttu-id="e8335-123">FocusStates</span><span class="sxs-lookup"><span data-stu-id="e8335-123">FocusStates</span></span>|<span data-ttu-id="e8335-124">Der Fokus liegt auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="e8335-124">The control has focus.</span></span>|  
|<span data-ttu-id="e8335-125">Ohne Fokus</span><span class="sxs-lookup"><span data-stu-id="e8335-125">Unfocused</span></span>|<span data-ttu-id="e8335-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="e8335-126">FocusStates</span></span>|<span data-ttu-id="e8335-127">Der Fokus liegt nicht auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="e8335-127">The control does not have focus.</span></span>|  
|<span data-ttu-id="e8335-128">Erweitert</span><span class="sxs-lookup"><span data-stu-id="e8335-128">Expanded</span></span>|<span data-ttu-id="e8335-129">ExpansionStates</span><span class="sxs-lookup"><span data-stu-id="e8335-129">ExpansionStates</span></span>|<span data-ttu-id="e8335-130">Das Steuerelement erweitert ist.</span><span class="sxs-lookup"><span data-stu-id="e8335-130">The control is expanded.</span></span>|  
|<span data-ttu-id="e8335-131">Reduziert</span><span class="sxs-lookup"><span data-stu-id="e8335-131">Collapsed</span></span>|<span data-ttu-id="e8335-132">ExpansionStates</span><span class="sxs-lookup"><span data-stu-id="e8335-132">ExpansionStates</span></span>|<span data-ttu-id="e8335-133">Das Steuerelement wird nicht erweitert.</span><span class="sxs-lookup"><span data-stu-id="e8335-133">The control is not expanded.</span></span>|  
|<span data-ttu-id="e8335-134">ExpandDown</span><span class="sxs-lookup"><span data-stu-id="e8335-134">ExpandDown</span></span>|<span data-ttu-id="e8335-135">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="e8335-135">ExpandDirectionStates</span></span>|<span data-ttu-id="e8335-136">Das Steuerelement wird nach unten erweitert.</span><span class="sxs-lookup"><span data-stu-id="e8335-136">The control expands down.</span></span>|  
|<span data-ttu-id="e8335-137">ExpandUp</span><span class="sxs-lookup"><span data-stu-id="e8335-137">ExpandUp</span></span>|<span data-ttu-id="e8335-138">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="e8335-138">ExpandDirectionStates</span></span>|<span data-ttu-id="e8335-139">Das Steuerelement erweitert einrichten.</span><span class="sxs-lookup"><span data-stu-id="e8335-139">The control expands up.</span></span>|  
|<span data-ttu-id="e8335-140">ExpandLeft</span><span class="sxs-lookup"><span data-stu-id="e8335-140">ExpandLeft</span></span>|<span data-ttu-id="e8335-141">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="e8335-141">ExpandDirectionStates</span></span>|<span data-ttu-id="e8335-142">Das Steuerelement ist nach links erweitert.</span><span class="sxs-lookup"><span data-stu-id="e8335-142">The control expands left.</span></span>|  
|<span data-ttu-id="e8335-143">ExpandRight</span><span class="sxs-lookup"><span data-stu-id="e8335-143">ExpandRight</span></span>|<span data-ttu-id="e8335-144">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="e8335-144">ExpandDirectionStates</span></span>|<span data-ttu-id="e8335-145">Das Steuerelement wird nach rechts erweitert.</span><span class="sxs-lookup"><span data-stu-id="e8335-145">The control expands right.</span></span>|  
|<span data-ttu-id="e8335-146">Gültig</span><span class="sxs-lookup"><span data-stu-id="e8335-146">Valid</span></span>|<span data-ttu-id="e8335-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e8335-147">ValidationStates</span></span>|<span data-ttu-id="e8335-148">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="e8335-148">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="e8335-149">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="e8335-149">InvalidFocused</span></span>|<span data-ttu-id="e8335-150">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e8335-150">ValidationStates</span></span>|<span data-ttu-id="e8335-151">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` weist das Steuerelement den Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="e8335-151">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="e8335-152">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="e8335-152">InvalidUnfocused</span></span>|<span data-ttu-id="e8335-153">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e8335-153">ValidationStates</span></span>|<span data-ttu-id="e8335-154">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement verfügt nicht über den Fokus.</span><span class="sxs-lookup"><span data-stu-id="e8335-154">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="expander-controltemplate-example"></a><span data-ttu-id="e8335-155">Expander-ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="e8335-155">Expander ControlTemplate Example</span></span>  
 <span data-ttu-id="e8335-156">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.Expander> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="e8335-156">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Expander> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Expander](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/expander.xaml#expander)]  
  
 <span data-ttu-id="e8335-157">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="e8335-157">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="e8335-158">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="e8335-158">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8335-159">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8335-159">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="e8335-160">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="e8335-160">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="e8335-161">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="e8335-161">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="e8335-162">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="e8335-162">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="e8335-163">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="e8335-163">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
