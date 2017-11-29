---
title: CheckBox-Stile und -Vorlagen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- states [WPF], CheckBox
- templates [WPF], CheckBox
- parts [WPF], CheckBox
- ControlTemplate [WPF], CheckBox
- CheckBox [WPF], styles and templates
- styles [WPF], CheckBox
ms.assetid: bfdaec96-d101-4d3d-864d-c27e6b621d03
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9c901d710e96cd111104b9fef2219b157377adc3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="checkbox-styles-and-templates"></a><span data-ttu-id="d669d-102">CheckBox-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="d669d-102">CheckBox Styles and Templates</span></span>
<span data-ttu-id="d669d-103">In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.CheckBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="d669d-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.CheckBox> control.</span></span> <span data-ttu-id="d669d-104">Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement ein einzigartiges aussehen zu verleihen.</span><span class="sxs-lookup"><span data-stu-id="d669d-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="d669d-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="d669d-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="checkbox-parts"></a><span data-ttu-id="d669d-106">CheckBox-Teile</span><span class="sxs-lookup"><span data-stu-id="d669d-106">CheckBox Parts</span></span>  
 <span data-ttu-id="d669d-107">Die <xref:System.Windows.Controls.CheckBox> Steuerelement enthält keine benannten Teile.</span><span class="sxs-lookup"><span data-stu-id="d669d-107">The <xref:System.Windows.Controls.CheckBox> control does not have any named parts.</span></span>  
  
## <a name="checkbox-states"></a><span data-ttu-id="d669d-108">CheckBox-Zustände</span><span class="sxs-lookup"><span data-stu-id="d669d-108">CheckBox States</span></span>  
 <span data-ttu-id="d669d-109">Die folgende Tabelle enthält die visueller Zustände für die <xref:System.Windows.Controls.CheckBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="d669d-109">The following table lists the visual states for the <xref:System.Windows.Controls.CheckBox> control.</span></span>  
  
|<span data-ttu-id="d669d-110">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="d669d-110">VisualState Name</span></span>|<span data-ttu-id="d669d-111">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="d669d-111">VisualStateGroup Name</span></span>|<span data-ttu-id="d669d-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d669d-112">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="d669d-113">Normal</span><span class="sxs-lookup"><span data-stu-id="d669d-113">Normal</span></span>|<span data-ttu-id="d669d-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="d669d-114">CommonStates</span></span>|<span data-ttu-id="d669d-115">Der Standardzustand</span><span class="sxs-lookup"><span data-stu-id="d669d-115">The default state.</span></span>|  
|<span data-ttu-id="d669d-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="d669d-116">MouseOver</span></span>|<span data-ttu-id="d669d-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="d669d-117">CommonStates</span></span>|<span data-ttu-id="d669d-118">Der Mauszeiger ist über dem Steuerelement positioniert.</span><span class="sxs-lookup"><span data-stu-id="d669d-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="d669d-119">Gedrückt</span><span class="sxs-lookup"><span data-stu-id="d669d-119">Pressed</span></span>|<span data-ttu-id="d669d-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="d669d-120">CommonStates</span></span>|<span data-ttu-id="d669d-121">Das Steuerelement wird gedrückt.</span><span class="sxs-lookup"><span data-stu-id="d669d-121">The control is pressed.</span></span>|  
|<span data-ttu-id="d669d-122">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="d669d-122">Disabled</span></span>|<span data-ttu-id="d669d-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="d669d-123">CommonStates</span></span>|<span data-ttu-id="d669d-124">Das Steuerelement ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="d669d-124">The control is disabled.</span></span>|  
|<span data-ttu-id="d669d-125">Focused</span><span class="sxs-lookup"><span data-stu-id="d669d-125">Focused</span></span>|<span data-ttu-id="d669d-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="d669d-126">FocusStates</span></span>|<span data-ttu-id="d669d-127">Der Fokus liegt auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="d669d-127">The control has focus.</span></span>|  
|<span data-ttu-id="d669d-128">Ohne Fokus</span><span class="sxs-lookup"><span data-stu-id="d669d-128">Unfocused</span></span>|<span data-ttu-id="d669d-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="d669d-129">FocusStates</span></span>|<span data-ttu-id="d669d-130">Der Fokus liegt nicht auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="d669d-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="d669d-131">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="d669d-131">Checked</span></span>|<span data-ttu-id="d669d-132">CheckStates</span><span class="sxs-lookup"><span data-stu-id="d669d-132">CheckStates</span></span>|<span data-ttu-id="d669d-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> ist `true`.</span><span class="sxs-lookup"><span data-stu-id="d669d-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|  
|<span data-ttu-id="d669d-134">deaktiviert</span><span class="sxs-lookup"><span data-stu-id="d669d-134">Unchecked</span></span>|<span data-ttu-id="d669d-135">CheckStates</span><span class="sxs-lookup"><span data-stu-id="d669d-135">CheckStates</span></span>|<span data-ttu-id="d669d-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> ist `false`.</span><span class="sxs-lookup"><span data-stu-id="d669d-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|  
|<span data-ttu-id="d669d-137">Unbestimmt</span><span class="sxs-lookup"><span data-stu-id="d669d-137">Indeterminate</span></span>|<span data-ttu-id="d669d-138">CheckStates</span><span class="sxs-lookup"><span data-stu-id="d669d-138">CheckStates</span></span>|<span data-ttu-id="d669d-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A>ist `true`, und <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> ist `null`.</span><span class="sxs-lookup"><span data-stu-id="d669d-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|  
|<span data-ttu-id="d669d-140">Gültig</span><span class="sxs-lookup"><span data-stu-id="d669d-140">Valid</span></span>|<span data-ttu-id="d669d-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d669d-141">ValidationStates</span></span>|<span data-ttu-id="d669d-142">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="d669d-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="d669d-143">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="d669d-143">InvalidUnfocused</span></span>|<span data-ttu-id="d669d-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d669d-144">ValidationStates</span></span>|<span data-ttu-id="d669d-145">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` weist das Steuerelement den Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="d669d-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="d669d-146">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="d669d-146">InvalidFocused</span></span>|<span data-ttu-id="d669d-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d669d-147">ValidationStates</span></span>|<span data-ttu-id="d669d-148">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement verfügt nicht über den Fokus.</span><span class="sxs-lookup"><span data-stu-id="d669d-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="checkbox-controltemplate-example"></a><span data-ttu-id="d669d-149">Beispiel für Kontrollkästchen-ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="d669d-149">CheckBox ControlTemplate Example</span></span>  
 <span data-ttu-id="d669d-150">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.CheckBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="d669d-150">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.CheckBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#CheckBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/checkbox.xaml#checkbox)]  
  
 <span data-ttu-id="d669d-151">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="d669d-151">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="d669d-152">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="d669d-152">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d669d-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d669d-153">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="d669d-154">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="d669d-154">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="d669d-155">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="d669d-155">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="d669d-156">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="d669d-156">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="d669d-157">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="d669d-157">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
