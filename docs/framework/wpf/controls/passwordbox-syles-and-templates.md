---
title: PasswordBox-Stile und -Vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], PasswordBox
- templates [WPF], PasswordBox
- ControlTemplate [WPF], PasswordBox
- states [WPF], PasswordBox
- PasswordBox [WPF], styles and templates
- parts [WPF], PasswordBox
ms.assetid: deb52107-959f-4a60-b303-d21a0a933060
ms.openlocfilehash: ddc0a2a01b78a01e8f90c26df9b91521ebfa9bf5
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377728"
---
# <a name="passwordbox-syles-and-templates"></a><span data-ttu-id="1b681-102">PasswordBox-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="1b681-102">PasswordBox Syles and Templates</span></span>
<span data-ttu-id="1b681-103">In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.PasswordBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="1b681-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.PasswordBox> control.</span></span> <span data-ttu-id="1b681-104">Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement eine unverwechselbare Darstellung verleihen.</span><span class="sxs-lookup"><span data-stu-id="1b681-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="1b681-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="1b681-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="passwordbox-parts"></a><span data-ttu-id="1b681-106">Teile der PasswordBox-Element</span><span class="sxs-lookup"><span data-stu-id="1b681-106">PasswordBox Parts</span></span>  
 <span data-ttu-id="1b681-107">Die folgende Tabelle enthält die benannten Teile für den <xref:System.Windows.Controls.PasswordBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="1b681-107">The following table lists the named parts for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>  
  
|<span data-ttu-id="1b681-108">Segment</span><span class="sxs-lookup"><span data-stu-id="1b681-108">Part</span></span>|<span data-ttu-id="1b681-109">Typ</span><span class="sxs-lookup"><span data-stu-id="1b681-109">Type</span></span>|<span data-ttu-id="1b681-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1b681-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="1b681-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="1b681-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="1b681-112">Ein visuelles Element, das enthalten einer <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="1b681-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="1b681-113">Der Text, der die <xref:System.Windows.Controls.PasswordBox> wird in diesem Element angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1b681-113">The text of the <xref:System.Windows.Controls.PasswordBox> is displayed in this element.</span></span>|  
  
## <a name="passwordbox-states"></a><span data-ttu-id="1b681-114">PasswordBox-Element-Zustände</span><span class="sxs-lookup"><span data-stu-id="1b681-114">PasswordBox States</span></span>  
 <span data-ttu-id="1b681-115">Die folgende Tabelle enthält die visuellen Zustände für die <xref:System.Windows.Controls.PasswordBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="1b681-115">The following table lists the visual states for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>  
  
|<span data-ttu-id="1b681-116">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="1b681-116">VisualState Name</span></span>|<span data-ttu-id="1b681-117">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="1b681-117">VisualStateGroup Name</span></span>|<span data-ttu-id="1b681-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1b681-118">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="1b681-119">Normal</span><span class="sxs-lookup"><span data-stu-id="1b681-119">Normal</span></span>|<span data-ttu-id="1b681-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="1b681-120">CommonStates</span></span>|<span data-ttu-id="1b681-121">Der Standardzustand</span><span class="sxs-lookup"><span data-stu-id="1b681-121">The default state.</span></span>|  
|<span data-ttu-id="1b681-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="1b681-122">MouseOver</span></span>|<span data-ttu-id="1b681-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="1b681-123">CommonStates</span></span>|<span data-ttu-id="1b681-124">Der Mauszeiger befindet sich auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="1b681-124">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="1b681-125">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="1b681-125">Disabled</span></span>|<span data-ttu-id="1b681-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="1b681-126">CommonStates</span></span>|<span data-ttu-id="1b681-127">Das Steuerelement ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="1b681-127">The control is disabled.</span></span>|  
|<span data-ttu-id="1b681-128">Focused</span><span class="sxs-lookup"><span data-stu-id="1b681-128">Focused</span></span>|<span data-ttu-id="1b681-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="1b681-129">FocusStates</span></span>|<span data-ttu-id="1b681-130">Der Fokus liegt auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="1b681-130">The control has focus.</span></span>|  
|<span data-ttu-id="1b681-131">Ohne Fokus</span><span class="sxs-lookup"><span data-stu-id="1b681-131">Unfocused</span></span>|<span data-ttu-id="1b681-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="1b681-132">FocusStates</span></span>|<span data-ttu-id="1b681-133">Der Fokus liegt nicht auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="1b681-133">The control does not have focus.</span></span>|  
|<span data-ttu-id="1b681-134">Gültig</span><span class="sxs-lookup"><span data-stu-id="1b681-134">Valid</span></span>|<span data-ttu-id="1b681-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="1b681-135">ValidationStates</span></span>|<span data-ttu-id="1b681-136">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="1b681-136">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="1b681-137">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="1b681-137">InvalidFocused</span></span>|<span data-ttu-id="1b681-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="1b681-138">ValidationStates</span></span>|<span data-ttu-id="1b681-139">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="1b681-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="1b681-140">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="1b681-140">InvalidUnfocused</span></span>|<span data-ttu-id="1b681-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="1b681-141">ValidationStates</span></span>|<span data-ttu-id="1b681-142">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement keinen Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="1b681-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="passwordbox-controltemplate-example"></a><span data-ttu-id="1b681-143">PasswordBox-ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="1b681-143">PasswordBox ControlTemplate Example</span></span>  
 <span data-ttu-id="1b681-144">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.PasswordBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="1b681-144">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#PasswordBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#passwordbox)]  
  
 <span data-ttu-id="1b681-145">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="1b681-145">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="1b681-146">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="1b681-146">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b681-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b681-147">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="1b681-148">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="1b681-148">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="1b681-149">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="1b681-149">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="1b681-150">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="1b681-150">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="1b681-151">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="1b681-151">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
