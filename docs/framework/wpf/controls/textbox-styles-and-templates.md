---
title: TextBox-Stile und -Vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], TextBox
- parts [WPF], TextBox
- states [WPF], TextBox
- styles [WPF], TextBox
- templates [WPF], TextBox
- TextBox [WPF], styles and templates
ms.assetid: aa99130c-43a1-450f-9b46-c40ae0db0cca
ms.openlocfilehash: 16f087051e438fa0dbe248c46b0ec555c07cc06c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57367907"
---
# <a name="textbox-styles-and-templates"></a><span data-ttu-id="f8355-102">TextBox-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="f8355-102">TextBox Styles and Templates</span></span>
<span data-ttu-id="f8355-103">In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.TextBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="f8355-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.TextBox> control.</span></span> <span data-ttu-id="f8355-104">Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement eine unverwechselbare Darstellung verleihen.</span><span class="sxs-lookup"><span data-stu-id="f8355-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="f8355-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="f8355-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="textbox-parts"></a><span data-ttu-id="f8355-106">TextBox-Teile</span><span class="sxs-lookup"><span data-stu-id="f8355-106">TextBox Parts</span></span>  
 <span data-ttu-id="f8355-107">Die folgende Tabelle enthält die benannten Teile für den <xref:System.Windows.Controls.TextBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="f8355-107">The following table lists the named parts for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="f8355-108">Segment</span><span class="sxs-lookup"><span data-stu-id="f8355-108">Part</span></span>|<span data-ttu-id="f8355-109">Typ</span><span class="sxs-lookup"><span data-stu-id="f8355-109">Type</span></span>|<span data-ttu-id="f8355-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f8355-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="f8355-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="f8355-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="f8355-112">Ein visuelles Element, das enthalten einer <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="f8355-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="f8355-113">Der Text, der die <xref:System.Windows.Controls.TextBox> wird in diesem Element angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f8355-113">The text of the <xref:System.Windows.Controls.TextBox> is displayed in this element.</span></span>|  
  
## <a name="textbox-states"></a><span data-ttu-id="f8355-114">TextBox-Zustände</span><span class="sxs-lookup"><span data-stu-id="f8355-114">TextBox States</span></span>  
 <span data-ttu-id="f8355-115">Die folgende Tabelle enthält die visuellen Zustände für die <xref:System.Windows.Controls.TextBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="f8355-115">The following table lists the visual states for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="f8355-116">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="f8355-116">VisualState Name</span></span>|<span data-ttu-id="f8355-117">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="f8355-117">VisualStateGroup Name</span></span>|<span data-ttu-id="f8355-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f8355-118">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="f8355-119">Normal</span><span class="sxs-lookup"><span data-stu-id="f8355-119">Normal</span></span>|<span data-ttu-id="f8355-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="f8355-120">CommonStates</span></span>|<span data-ttu-id="f8355-121">Der Standardzustand</span><span class="sxs-lookup"><span data-stu-id="f8355-121">The default state.</span></span>|  
|<span data-ttu-id="f8355-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="f8355-122">MouseOver</span></span>|<span data-ttu-id="f8355-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="f8355-123">CommonStates</span></span>|<span data-ttu-id="f8355-124">Der Mauszeiger befindet sich auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="f8355-124">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="f8355-125">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="f8355-125">Disabled</span></span>|<span data-ttu-id="f8355-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="f8355-126">CommonStates</span></span>|<span data-ttu-id="f8355-127">Das Steuerelement ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f8355-127">The control is disabled.</span></span>|  
|<span data-ttu-id="f8355-128">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="f8355-128">ReadOnly</span></span>|<span data-ttu-id="f8355-129">CommonStates</span><span class="sxs-lookup"><span data-stu-id="f8355-129">CommonStates</span></span>|<span data-ttu-id="f8355-130">Der Benutzer kann nicht den Text im Ändern der <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="f8355-130">The user cannot change the text in the <xref:System.Windows.Controls.TextBox>.</span></span>|  
|<span data-ttu-id="f8355-131">Focused</span><span class="sxs-lookup"><span data-stu-id="f8355-131">Focused</span></span>|<span data-ttu-id="f8355-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="f8355-132">FocusStates</span></span>|<span data-ttu-id="f8355-133">Der Fokus liegt auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="f8355-133">The control has focus.</span></span>|  
|<span data-ttu-id="f8355-134">Ohne Fokus</span><span class="sxs-lookup"><span data-stu-id="f8355-134">Unfocused</span></span>|<span data-ttu-id="f8355-135">FocusStates</span><span class="sxs-lookup"><span data-stu-id="f8355-135">FocusStates</span></span>|<span data-ttu-id="f8355-136">Der Fokus liegt nicht auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="f8355-136">The control does not have focus.</span></span>|  
|<span data-ttu-id="f8355-137">Gültig</span><span class="sxs-lookup"><span data-stu-id="f8355-137">Valid</span></span>|<span data-ttu-id="f8355-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f8355-138">ValidationStates</span></span>|<span data-ttu-id="f8355-139">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="f8355-139">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="f8355-140">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="f8355-140">InvalidFocused</span></span>|<span data-ttu-id="f8355-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f8355-141">ValidationStates</span></span>|<span data-ttu-id="f8355-142">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="f8355-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="f8355-143">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="f8355-143">InvalidUnfocused</span></span>|<span data-ttu-id="f8355-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f8355-144">ValidationStates</span></span>|<span data-ttu-id="f8355-145">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement keinen Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="f8355-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="textbox-controltemplate-example"></a><span data-ttu-id="f8355-146">TextBox-ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="f8355-146">TextBox ControlTemplate Example</span></span>  
 <span data-ttu-id="f8355-147">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.TextBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="f8355-147">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#TextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#textbox)]  
  
 <span data-ttu-id="f8355-148">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="f8355-148">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="f8355-149">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="f8355-149">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8355-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8355-150">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="f8355-151">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="f8355-151">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="f8355-152">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="f8355-152">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="f8355-153">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="f8355-153">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="f8355-154">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="f8355-154">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
