---
title: ToggleButton-Stile und -Vorlagen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- states [WPF], ToggleButton
- ToggleButton [WPF], styles and templates
- ControlTemplate [WPF], ToggleButton
- styles [WPF], ToggleButton
- templates [WPF], ToggleButton
- parts [WPF], ToggleButton
ms.assetid: 54f23f30-4bcb-4f09-8ce4-376a13a255a1
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5c143717b691e79771fbaa55724d9d9748259e3f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="togglebutton-syles-and-templates"></a><span data-ttu-id="81dc7-102">ToggleButton-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="81dc7-102">ToggleButton Syles and Templates</span></span>
<span data-ttu-id="81dc7-103">In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.Primitives.ToggleButton> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="81dc7-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span> <span data-ttu-id="81dc7-104">Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement ein einzigartiges aussehen zu verleihen.</span><span class="sxs-lookup"><span data-stu-id="81dc7-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="81dc7-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="81dc7-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="togglebutton-parts"></a><span data-ttu-id="81dc7-106">ToggleButton-Teile</span><span class="sxs-lookup"><span data-stu-id="81dc7-106">ToggleButton Parts</span></span>  
 <span data-ttu-id="81dc7-107">Die <xref:System.Windows.Controls.Primitives.ToggleButton> Steuerelement enthält keine benannten Teile.</span><span class="sxs-lookup"><span data-stu-id="81dc7-107">The <xref:System.Windows.Controls.Primitives.ToggleButton> control does not have any named parts.</span></span>  
  
## <a name="togglebutton-states"></a><span data-ttu-id="81dc7-108">ToggleButton-Zustände</span><span class="sxs-lookup"><span data-stu-id="81dc7-108">ToggleButton States</span></span>  
 <span data-ttu-id="81dc7-109">Die folgende Tabelle enthält die visueller Zustände für die <xref:System.Windows.Controls.Primitives.ToggleButton> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="81dc7-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>  
  
|<span data-ttu-id="81dc7-110">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="81dc7-110">VisualState Name</span></span>|<span data-ttu-id="81dc7-111">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="81dc7-111">VisualStateGroup Name</span></span>|<span data-ttu-id="81dc7-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="81dc7-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="81dc7-113">Normal</span><span class="sxs-lookup"><span data-stu-id="81dc7-113">Normal</span></span>|<span data-ttu-id="81dc7-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="81dc7-114">CommonStates</span></span>|<span data-ttu-id="81dc7-115">Der Standardzustand</span><span class="sxs-lookup"><span data-stu-id="81dc7-115">The default state.</span></span>|  
|<span data-ttu-id="81dc7-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="81dc7-116">MouseOver</span></span>|<span data-ttu-id="81dc7-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="81dc7-117">CommonStates</span></span>|<span data-ttu-id="81dc7-118">Der Mauszeiger ist über dem Steuerelement positioniert.</span><span class="sxs-lookup"><span data-stu-id="81dc7-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="81dc7-119">Gedrückt</span><span class="sxs-lookup"><span data-stu-id="81dc7-119">Pressed</span></span>|<span data-ttu-id="81dc7-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="81dc7-120">CommonStates</span></span>|<span data-ttu-id="81dc7-121">Das Steuerelement wird gedrückt.</span><span class="sxs-lookup"><span data-stu-id="81dc7-121">The control is pressed.</span></span>|  
|<span data-ttu-id="81dc7-122">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="81dc7-122">Disabled</span></span>|<span data-ttu-id="81dc7-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="81dc7-123">CommonStates</span></span>|<span data-ttu-id="81dc7-124">Das Steuerelement ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="81dc7-124">The control is disabled.</span></span>|  
|<span data-ttu-id="81dc7-125">Focused</span><span class="sxs-lookup"><span data-stu-id="81dc7-125">Focused</span></span>|<span data-ttu-id="81dc7-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="81dc7-126">FocusStates</span></span>|<span data-ttu-id="81dc7-127">Der Fokus liegt auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="81dc7-127">The control has focus.</span></span>|  
|<span data-ttu-id="81dc7-128">Ohne Fokus</span><span class="sxs-lookup"><span data-stu-id="81dc7-128">Unfocused</span></span>|<span data-ttu-id="81dc7-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="81dc7-129">FocusStates</span></span>|<span data-ttu-id="81dc7-130">Der Fokus liegt nicht auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="81dc7-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="81dc7-131">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="81dc7-131">Checked</span></span>|<span data-ttu-id="81dc7-132">CheckStates</span><span class="sxs-lookup"><span data-stu-id="81dc7-132">CheckStates</span></span>|<span data-ttu-id="81dc7-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> ist `true`.</span><span class="sxs-lookup"><span data-stu-id="81dc7-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|  
|<span data-ttu-id="81dc7-134">deaktiviert</span><span class="sxs-lookup"><span data-stu-id="81dc7-134">Unchecked</span></span>|<span data-ttu-id="81dc7-135">CheckStates</span><span class="sxs-lookup"><span data-stu-id="81dc7-135">CheckStates</span></span>|<span data-ttu-id="81dc7-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> ist `false`.</span><span class="sxs-lookup"><span data-stu-id="81dc7-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|  
|<span data-ttu-id="81dc7-137">Unbestimmt</span><span class="sxs-lookup"><span data-stu-id="81dc7-137">Indeterminate</span></span>|<span data-ttu-id="81dc7-138">CheckStates</span><span class="sxs-lookup"><span data-stu-id="81dc7-138">CheckStates</span></span>|<span data-ttu-id="81dc7-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A>ist `true`, und <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> ist `null`.</span><span class="sxs-lookup"><span data-stu-id="81dc7-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|  
|<span data-ttu-id="81dc7-140">Gültig</span><span class="sxs-lookup"><span data-stu-id="81dc7-140">Valid</span></span>|<span data-ttu-id="81dc7-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="81dc7-141">ValidationStates</span></span>|<span data-ttu-id="81dc7-142">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="81dc7-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="81dc7-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="81dc7-143">InvalidFocused</span></span>|<span data-ttu-id="81dc7-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="81dc7-144">ValidationStates</span></span>|<span data-ttu-id="81dc7-145">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` weist das Steuerelement den Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="81dc7-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="81dc7-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="81dc7-146">InvalidUnfocused</span></span>|<span data-ttu-id="81dc7-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="81dc7-147">ValidationStates</span></span>|<span data-ttu-id="81dc7-148">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement verfügt nicht über den Fokus.</span><span class="sxs-lookup"><span data-stu-id="81dc7-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="81dc7-149">Wenn visual unbestimmte Zustand in der Steuerelementvorlage nicht vorhanden ist, wird die Unchecked visuellen Zustands als Standardeinstellung visuellen Zustands verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="81dc7-149">If the Indeterminate visual state does not exist in your control template, then the Unchecked visual state will be used as default visual state.</span></span>  
  
## <a name="togglebutton-controltemplate-example"></a><span data-ttu-id="81dc7-150">Beispiel für ToggleButton-ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="81dc7-150">ToggleButton ControlTemplate Example</span></span>  
 <span data-ttu-id="81dc7-151">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.Primitives.ToggleButton> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="81dc7-151">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToggleButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#togglebutton)]  
  
 <span data-ttu-id="81dc7-152">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="81dc7-152">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="81dc7-153">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="81dc7-153">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81dc7-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="81dc7-154">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="81dc7-155">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="81dc7-155">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="81dc7-156">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="81dc7-156">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="81dc7-157">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="81dc7-157">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="81dc7-158">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="81dc7-158">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
