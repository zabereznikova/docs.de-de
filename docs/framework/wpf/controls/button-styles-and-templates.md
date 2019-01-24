---
title: Button-Stile und -Vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], Button
- parts [WPF], Button
- styles [WPF], Button
- Button [WPF], styles and templates
- templates [WPF], Button
- ControlTemplate [WPF], Button
ms.assetid: e223c759-f8c4-4717-acfb-b1e40bdf5f3b
ms.openlocfilehash: af9ea902cba2c8be0fbee621297af3198bbec150
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54620473"
---
# <a name="button-styles-and-templates"></a><span data-ttu-id="6944e-102">Button-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="6944e-102">Button Styles and Templates</span></span>
<span data-ttu-id="6944e-103">In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.Button> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="6944e-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="6944e-104">Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement eine unverwechselbare Darstellung verleihen.</span><span class="sxs-lookup"><span data-stu-id="6944e-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="6944e-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="6944e-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="button-parts"></a><span data-ttu-id="6944e-106">Schaltfläche Teilen</span><span class="sxs-lookup"><span data-stu-id="6944e-106">Button Parts</span></span>  
 <span data-ttu-id="6944e-107">Die <xref:System.Windows.Controls.Button> Steuerelement enthält keine benannten Teile.</span><span class="sxs-lookup"><span data-stu-id="6944e-107">The <xref:System.Windows.Controls.Button> control does not have any named parts.</span></span>  
  
## <a name="button-states"></a><span data-ttu-id="6944e-108">Schaltflächenzustände</span><span class="sxs-lookup"><span data-stu-id="6944e-108">Button States</span></span>  
 <span data-ttu-id="6944e-109">Die folgende Tabelle enthält die visuellen Zustände für die <xref:System.Windows.Controls.Button> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="6944e-109">The following table lists the visual states for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
|<span data-ttu-id="6944e-110">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="6944e-110">VisualState Name</span></span>|<span data-ttu-id="6944e-111">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="6944e-111">VisualStateGroup Name</span></span>|<span data-ttu-id="6944e-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6944e-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="6944e-113">Normal</span><span class="sxs-lookup"><span data-stu-id="6944e-113">Normal</span></span>|<span data-ttu-id="6944e-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="6944e-114">CommonStates</span></span>|<span data-ttu-id="6944e-115">Der Standardzustand</span><span class="sxs-lookup"><span data-stu-id="6944e-115">The default state.</span></span>|  
|<span data-ttu-id="6944e-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="6944e-116">MouseOver</span></span>|<span data-ttu-id="6944e-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="6944e-117">CommonStates</span></span>|<span data-ttu-id="6944e-118">Der Mauszeiger ist über dem Steuerelement positioniert.</span><span class="sxs-lookup"><span data-stu-id="6944e-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="6944e-119">Gedrückt</span><span class="sxs-lookup"><span data-stu-id="6944e-119">Pressed</span></span>|<span data-ttu-id="6944e-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="6944e-120">CommonStates</span></span>|<span data-ttu-id="6944e-121">Das Steuerelement wird gedrückt.</span><span class="sxs-lookup"><span data-stu-id="6944e-121">The control is pressed.</span></span>|  
|<span data-ttu-id="6944e-122">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="6944e-122">Disabled</span></span>|<span data-ttu-id="6944e-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="6944e-123">CommonStates</span></span>|<span data-ttu-id="6944e-124">Das Steuerelement ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="6944e-124">The control is disabled.</span></span>|  
|<span data-ttu-id="6944e-125">Focused</span><span class="sxs-lookup"><span data-stu-id="6944e-125">Focused</span></span>|<span data-ttu-id="6944e-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="6944e-126">FocusStates</span></span>|<span data-ttu-id="6944e-127">Der Fokus liegt auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="6944e-127">The control has focus.</span></span>|  
|<span data-ttu-id="6944e-128">Ohne Fokus</span><span class="sxs-lookup"><span data-stu-id="6944e-128">Unfocused</span></span>|<span data-ttu-id="6944e-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="6944e-129">FocusStates</span></span>|<span data-ttu-id="6944e-130">Der Fokus liegt nicht auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="6944e-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="6944e-131">Gültig</span><span class="sxs-lookup"><span data-stu-id="6944e-131">Valid</span></span>|<span data-ttu-id="6944e-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6944e-132">ValidationStates</span></span>|<span data-ttu-id="6944e-133">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="6944e-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="6944e-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="6944e-134">InvalidFocused</span></span>|<span data-ttu-id="6944e-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6944e-135">ValidationStates</span></span>|<span data-ttu-id="6944e-136">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` und das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="6944e-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="6944e-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="6944e-137">InvalidUnfocused</span></span>|<span data-ttu-id="6944e-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6944e-138">ValidationStates</span></span>|<span data-ttu-id="6944e-139">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` und das Steuerelement keinen Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="6944e-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="button-controltemplate-example"></a><span data-ttu-id="6944e-140">Schaltfläche "ControlTemplate"-Beispiel</span><span class="sxs-lookup"><span data-stu-id="6944e-140">Button ControlTemplate Example</span></span>  
 <span data-ttu-id="6944e-141">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.Button> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="6944e-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Button](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#button)]  
  
 <span data-ttu-id="6944e-142">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="6944e-142">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="6944e-143">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="6944e-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6944e-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6944e-144">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="6944e-145">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="6944e-145">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)
- [<span data-ttu-id="6944e-146">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="6944e-146">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)
- [<span data-ttu-id="6944e-147">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="6944e-147">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)
- [<span data-ttu-id="6944e-148">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="6944e-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
