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
ms.openlocfilehash: 41e390c261836909240cc146a48729d48c4a410e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283703"
---
# <a name="textbox-styles-and-templates"></a><span data-ttu-id="a702d-102">TextBox-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="a702d-102">TextBox Styles and Templates</span></span>
<span data-ttu-id="a702d-103">In diesem Thema werden die Stile und Vorlagen für das <xref:System.Windows.Controls.TextBox>-Steuerelement beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a702d-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.TextBox> control.</span></span> <span data-ttu-id="a702d-104">Sie können die Standard <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement eine eindeutige Darstellung zu verschaffen.</span><span class="sxs-lookup"><span data-stu-id="a702d-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="a702d-105">Weitere Informationen finden Sie unter [Erstellen einer Vorlage für ein-Steuer](../../../desktop-wpf/themes/how-to-create-apply-template.md)Element.</span><span class="sxs-lookup"><span data-stu-id="a702d-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="textbox-parts"></a><span data-ttu-id="a702d-106">Text Feld Teile</span><span class="sxs-lookup"><span data-stu-id="a702d-106">TextBox Parts</span></span>  
 <span data-ttu-id="a702d-107">In der folgenden Tabelle sind die benannten Teile für das <xref:System.Windows.Controls.TextBox>-Steuerelement aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="a702d-107">The following table lists the named parts for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="a702d-108">-Komponente</span><span class="sxs-lookup"><span data-stu-id="a702d-108">Part</span></span>|<span data-ttu-id="a702d-109">Typ</span><span class="sxs-lookup"><span data-stu-id="a702d-109">Type</span></span>|<span data-ttu-id="a702d-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a702d-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="a702d-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="a702d-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="a702d-112">Ein visuelles Element, das ein <xref:System.Windows.FrameworkElement>enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="a702d-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="a702d-113">Der Text des <xref:System.Windows.Controls.TextBox> wird in diesem Element angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a702d-113">The text of the <xref:System.Windows.Controls.TextBox> is displayed in this element.</span></span>|  
  
## <a name="textbox-states"></a><span data-ttu-id="a702d-114">TextBox-Zustände</span><span class="sxs-lookup"><span data-stu-id="a702d-114">TextBox States</span></span>  
 <span data-ttu-id="a702d-115">In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Controls.TextBox>-Steuerelement aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="a702d-115">The following table lists the visual states for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="a702d-116">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="a702d-116">VisualState Name</span></span>|<span data-ttu-id="a702d-117">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="a702d-117">VisualStateGroup Name</span></span>|<span data-ttu-id="a702d-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a702d-118">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="a702d-119">Normal</span><span class="sxs-lookup"><span data-stu-id="a702d-119">Normal</span></span>|<span data-ttu-id="a702d-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a702d-120">CommonStates</span></span>|<span data-ttu-id="a702d-121">Der Standardstatus.</span><span class="sxs-lookup"><span data-stu-id="a702d-121">The default state.</span></span>|  
|<span data-ttu-id="a702d-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="a702d-122">MouseOver</span></span>|<span data-ttu-id="a702d-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a702d-123">CommonStates</span></span>|<span data-ttu-id="a702d-124">Der Mauszeiger ist über dem Steuerelement positioniert.</span><span class="sxs-lookup"><span data-stu-id="a702d-124">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="a702d-125">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="a702d-125">Disabled</span></span>|<span data-ttu-id="a702d-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a702d-126">CommonStates</span></span>|<span data-ttu-id="a702d-127">Das Steuerelement ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="a702d-127">The control is disabled.</span></span>|  
|<span data-ttu-id="a702d-128">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="a702d-128">ReadOnly</span></span>|<span data-ttu-id="a702d-129">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a702d-129">CommonStates</span></span>|<span data-ttu-id="a702d-130">Der Benutzer kann den Text im <xref:System.Windows.Controls.TextBox>nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="a702d-130">The user cannot change the text in the <xref:System.Windows.Controls.TextBox>.</span></span>|  
|<span data-ttu-id="a702d-131">Mit Fokus</span><span class="sxs-lookup"><span data-stu-id="a702d-131">Focused</span></span>|<span data-ttu-id="a702d-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="a702d-132">FocusStates</span></span>|<span data-ttu-id="a702d-133">Der Fokus liegt auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="a702d-133">The control has focus.</span></span>|  
|<span data-ttu-id="a702d-134">Ohne Fokus</span><span class="sxs-lookup"><span data-stu-id="a702d-134">Unfocused</span></span>|<span data-ttu-id="a702d-135">FocusStates</span><span class="sxs-lookup"><span data-stu-id="a702d-135">FocusStates</span></span>|<span data-ttu-id="a702d-136">Der Fokus liegt nicht auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="a702d-136">The control does not have focus.</span></span>|  
|<span data-ttu-id="a702d-137">Gültig</span><span class="sxs-lookup"><span data-stu-id="a702d-137">Valid</span></span>|<span data-ttu-id="a702d-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a702d-138">ValidationStates</span></span>|<span data-ttu-id="a702d-139">Das-Steuerelement verwendet die <xref:System.Windows.Controls.Validation>-Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false`.</span><span class="sxs-lookup"><span data-stu-id="a702d-139">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="a702d-140">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="a702d-140">InvalidFocused</span></span>|<span data-ttu-id="a702d-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a702d-141">ValidationStates</span></span>|<span data-ttu-id="a702d-142">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true` hat, dass das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="a702d-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="a702d-143">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="a702d-143">InvalidUnfocused</span></span>|<span data-ttu-id="a702d-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a702d-144">ValidationStates</span></span>|<span data-ttu-id="a702d-145">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, wenn das Steuerelement keinen Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="a702d-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="textbox-controltemplate-example"></a><span data-ttu-id="a702d-146">TextBox-ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="a702d-146">TextBox ControlTemplate Example</span></span>  
 <span data-ttu-id="a702d-147">Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.ControlTemplate> für das <xref:System.Windows.Controls.TextBox>-Steuerelement definiert wird.</span><span class="sxs-lookup"><span data-stu-id="a702d-147">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#TextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#textbox)]  
  
 <span data-ttu-id="a702d-148">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="a702d-148">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="a702d-149">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="a702d-149">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a702d-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a702d-150">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="a702d-151">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="a702d-151">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="a702d-152">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="a702d-152">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="a702d-153">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="a702d-153">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="a702d-154">Erstellen einer Vorlage für ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="a702d-154">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
