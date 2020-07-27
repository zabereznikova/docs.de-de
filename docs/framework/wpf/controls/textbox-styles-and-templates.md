---
title: TextBox-Stile und -Vorlagen
description: Erfahren Sie mehr über Stile und Vorlagen für das Windows Presentation Foundation TextBox-Steuerelement. Ändern Sie ControlTemplate, um dem Steuerelement eine eindeutige Darstellung zu verschaffen.
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], TextBox
- parts [WPF], TextBox
- states [WPF], TextBox
- styles [WPF], TextBox
- templates [WPF], TextBox
- TextBox [WPF], styles and templates
ms.assetid: aa99130c-43a1-450f-9b46-c40ae0db0cca
ms.openlocfilehash: 0e15fd40f5590ee46da49cc6c0d5fb30e051f7e4
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164724"
---
# <a name="textbox-styles-and-templates"></a><span data-ttu-id="9c07f-104">TextBox-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="9c07f-104">TextBox Styles and Templates</span></span>
<span data-ttu-id="9c07f-105">In diesem Thema werden die Stile und Vorlagen für das-Steuerelement beschrieben <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="9c07f-105">This topic describes the styles and templates for the <xref:System.Windows.Controls.TextBox> control.</span></span> <span data-ttu-id="9c07f-106">Sie können die Standardeinstellung ändern <xref:System.Windows.Controls.ControlTemplate> , um dem Steuerelement eine eindeutige Darstellung zu verschaffen.</span><span class="sxs-lookup"><span data-stu-id="9c07f-106">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="9c07f-107">Weitere Informationen finden Sie unter [Erstellen einer Vorlage für ein-Steuer](../../../desktop-wpf/themes/how-to-create-apply-template.md)Element.</span><span class="sxs-lookup"><span data-stu-id="9c07f-107">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="textbox-parts"></a><span data-ttu-id="9c07f-108">Text Feld Teile</span><span class="sxs-lookup"><span data-stu-id="9c07f-108">TextBox Parts</span></span>  
 <span data-ttu-id="9c07f-109">In der folgenden Tabelle sind die benannten Teile für das-Steuerelement aufgeführt <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="9c07f-109">The following table lists the named parts for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="9c07f-110">Teil</span><span class="sxs-lookup"><span data-stu-id="9c07f-110">Part</span></span>|<span data-ttu-id="9c07f-111">type</span><span class="sxs-lookup"><span data-stu-id="9c07f-111">Type</span></span>|<span data-ttu-id="9c07f-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9c07f-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="9c07f-113">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="9c07f-113">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="9c07f-114">Ein visuelles Element, das ein enthalten kann <xref:System.Windows.FrameworkElement> .</span><span class="sxs-lookup"><span data-stu-id="9c07f-114">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="9c07f-115">Der Text des <xref:System.Windows.Controls.TextBox> wird in diesem Element angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9c07f-115">The text of the <xref:System.Windows.Controls.TextBox> is displayed in this element.</span></span>|  
  
## <a name="textbox-states"></a><span data-ttu-id="9c07f-116">TextBox-Zustände</span><span class="sxs-lookup"><span data-stu-id="9c07f-116">TextBox States</span></span>  
 <span data-ttu-id="9c07f-117">In der folgenden Tabelle werden die visuellen Zustände für das-Steuerelement aufgelistet <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="9c07f-117">The following table lists the visual states for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="9c07f-118">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="9c07f-118">VisualState Name</span></span>|<span data-ttu-id="9c07f-119">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="9c07f-119">VisualStateGroup Name</span></span>|<span data-ttu-id="9c07f-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9c07f-120">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="9c07f-121">Normal</span><span class="sxs-lookup"><span data-stu-id="9c07f-121">Normal</span></span>|<span data-ttu-id="9c07f-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="9c07f-122">CommonStates</span></span>|<span data-ttu-id="9c07f-123">Der Standardzustand</span><span class="sxs-lookup"><span data-stu-id="9c07f-123">The default state.</span></span>|  
|<span data-ttu-id="9c07f-124">MouseOver</span><span class="sxs-lookup"><span data-stu-id="9c07f-124">MouseOver</span></span>|<span data-ttu-id="9c07f-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="9c07f-125">CommonStates</span></span>|<span data-ttu-id="9c07f-126">Der Mauszeiger ist über dem Steuerelement positioniert.</span><span class="sxs-lookup"><span data-stu-id="9c07f-126">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="9c07f-127">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="9c07f-127">Disabled</span></span>|<span data-ttu-id="9c07f-128">CommonStates</span><span class="sxs-lookup"><span data-stu-id="9c07f-128">CommonStates</span></span>|<span data-ttu-id="9c07f-129">Das Steuerelement ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="9c07f-129">The control is disabled.</span></span>|  
|<span data-ttu-id="9c07f-130">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="9c07f-130">ReadOnly</span></span>|<span data-ttu-id="9c07f-131">CommonStates</span><span class="sxs-lookup"><span data-stu-id="9c07f-131">CommonStates</span></span>|<span data-ttu-id="9c07f-132">Der Benutzer kann den Text in der nicht ändern <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="9c07f-132">The user cannot change the text in the <xref:System.Windows.Controls.TextBox>.</span></span>|  
|<span data-ttu-id="9c07f-133">Focused</span><span class="sxs-lookup"><span data-stu-id="9c07f-133">Focused</span></span>|<span data-ttu-id="9c07f-134">FocusStates</span><span class="sxs-lookup"><span data-stu-id="9c07f-134">FocusStates</span></span>|<span data-ttu-id="9c07f-135">Der Fokus liegt auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="9c07f-135">The control has focus.</span></span>|  
|<span data-ttu-id="9c07f-136">Ohne Fokus</span><span class="sxs-lookup"><span data-stu-id="9c07f-136">Unfocused</span></span>|<span data-ttu-id="9c07f-137">FocusStates</span><span class="sxs-lookup"><span data-stu-id="9c07f-137">FocusStates</span></span>|<span data-ttu-id="9c07f-138">Der Fokus liegt nicht auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="9c07f-138">The control does not have focus.</span></span>|  
|<span data-ttu-id="9c07f-139">Gültig</span><span class="sxs-lookup"><span data-stu-id="9c07f-139">Valid</span></span>|<span data-ttu-id="9c07f-140">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9c07f-140">ValidationStates</span></span>|<span data-ttu-id="9c07f-141">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> -Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false` .</span><span class="sxs-lookup"><span data-stu-id="9c07f-141">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="9c07f-142">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="9c07f-142">InvalidFocused</span></span>|<span data-ttu-id="9c07f-143">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9c07f-143">ValidationStates</span></span>|<span data-ttu-id="9c07f-144">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist, dass `true` das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="9c07f-144">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="9c07f-145">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="9c07f-145">InvalidUnfocused</span></span>|<span data-ttu-id="9c07f-146">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9c07f-146">ValidationStates</span></span>|<span data-ttu-id="9c07f-147">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist, wenn `true` das Steuerelement keinen Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="9c07f-147">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="textbox-controltemplate-example"></a><span data-ttu-id="9c07f-148">TextBox-ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="9c07f-148">TextBox ControlTemplate Example</span></span>  
 <span data-ttu-id="9c07f-149">Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.ControlTemplate> für das-Steuerelement definiert wird <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="9c07f-149">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#TextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#textbox)]  
  
 <span data-ttu-id="9c07f-150">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="9c07f-150">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="9c07f-151">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="9c07f-151">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c07f-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9c07f-152">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="9c07f-153">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="9c07f-153">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="9c07f-154">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="9c07f-154">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="9c07f-155">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="9c07f-155">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="9c07f-156">Erstellen einer Vorlage für ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="9c07f-156">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
