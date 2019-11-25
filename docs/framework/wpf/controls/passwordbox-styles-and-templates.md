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
ms.openlocfilehash: 4ba90182468466773644c7375059f0cc01675b33
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283467"
---
# <a name="passwordbox-styles-and-templates"></a><span data-ttu-id="4b47b-102">PasswordBox-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="4b47b-102">PasswordBox Styles and Templates</span></span>

<span data-ttu-id="4b47b-103">In diesem Thema werden die Stile und Vorlagen für das <xref:System.Windows.Controls.PasswordBox>-Steuerelement beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4b47b-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.PasswordBox> control.</span></span> <span data-ttu-id="4b47b-104">Sie können die Standard <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement eine eindeutige Darstellung zu verschaffen.</span><span class="sxs-lookup"><span data-stu-id="4b47b-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="4b47b-105">Weitere Informationen finden Sie unter [Erstellen einer Vorlage für ein-Steuer](../../../desktop-wpf/themes/how-to-create-apply-template.md)Element.</span><span class="sxs-lookup"><span data-stu-id="4b47b-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>

## <a name="passwordbox-parts"></a><span data-ttu-id="4b47b-106">PasswordBox-Teile</span><span class="sxs-lookup"><span data-stu-id="4b47b-106">PasswordBox Parts</span></span>

<span data-ttu-id="4b47b-107">In der folgenden Tabelle sind die benannten Teile für das <xref:System.Windows.Controls.PasswordBox>-Steuerelement aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="4b47b-107">The following table lists the named parts for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

|<span data-ttu-id="4b47b-108">Segment</span><span class="sxs-lookup"><span data-stu-id="4b47b-108">Part</span></span>|<span data-ttu-id="4b47b-109">Typ</span><span class="sxs-lookup"><span data-stu-id="4b47b-109">Type</span></span>|<span data-ttu-id="4b47b-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4b47b-110">Description</span></span>|
|-|-|-|
|<span data-ttu-id="4b47b-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="4b47b-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="4b47b-112">Ein visuelles Element, das ein <xref:System.Windows.FrameworkElement>enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="4b47b-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="4b47b-113">Der Text des <xref:System.Windows.Controls.PasswordBox> wird in diesem Element angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4b47b-113">The text of the <xref:System.Windows.Controls.PasswordBox> is displayed in this element.</span></span>|

## <a name="passwordbox-states"></a><span data-ttu-id="4b47b-114">PasswordBox-Zustände</span><span class="sxs-lookup"><span data-stu-id="4b47b-114">PasswordBox States</span></span>

<span data-ttu-id="4b47b-115">In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Controls.PasswordBox>-Steuerelement aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="4b47b-115">The following table lists the visual states for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

|<span data-ttu-id="4b47b-116">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="4b47b-116">VisualState Name</span></span>|<span data-ttu-id="4b47b-117">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="4b47b-117">VisualStateGroup Name</span></span>|<span data-ttu-id="4b47b-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4b47b-118">Description</span></span>|
|-|-|-|
|<span data-ttu-id="4b47b-119">Normal</span><span class="sxs-lookup"><span data-stu-id="4b47b-119">Normal</span></span>|<span data-ttu-id="4b47b-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="4b47b-120">CommonStates</span></span>|<span data-ttu-id="4b47b-121">Der Standardzustand</span><span class="sxs-lookup"><span data-stu-id="4b47b-121">The default state.</span></span>|
|<span data-ttu-id="4b47b-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="4b47b-122">MouseOver</span></span>|<span data-ttu-id="4b47b-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="4b47b-123">CommonStates</span></span>|<span data-ttu-id="4b47b-124">Der Mauszeiger ist über dem Steuerelement positioniert.</span><span class="sxs-lookup"><span data-stu-id="4b47b-124">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="4b47b-125">Disabled</span><span class="sxs-lookup"><span data-stu-id="4b47b-125">Disabled</span></span>|<span data-ttu-id="4b47b-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="4b47b-126">CommonStates</span></span>|<span data-ttu-id="4b47b-127">Das Steuerelement ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="4b47b-127">The control is disabled.</span></span>|
|<span data-ttu-id="4b47b-128">Mit Fokus</span><span class="sxs-lookup"><span data-stu-id="4b47b-128">Focused</span></span>|<span data-ttu-id="4b47b-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="4b47b-129">FocusStates</span></span>|<span data-ttu-id="4b47b-130">Der Fokus liegt auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="4b47b-130">The control has focus.</span></span>|
|<span data-ttu-id="4b47b-131">Ohne Fokus</span><span class="sxs-lookup"><span data-stu-id="4b47b-131">Unfocused</span></span>|<span data-ttu-id="4b47b-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="4b47b-132">FocusStates</span></span>|<span data-ttu-id="4b47b-133">Der Fokus liegt nicht auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="4b47b-133">The control does not have focus.</span></span>|
|<span data-ttu-id="4b47b-134">Gültig</span><span class="sxs-lookup"><span data-stu-id="4b47b-134">Valid</span></span>|<span data-ttu-id="4b47b-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4b47b-135">ValidationStates</span></span>|<span data-ttu-id="4b47b-136">Das-Steuerelement verwendet die <xref:System.Windows.Controls.Validation>-Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false`.</span><span class="sxs-lookup"><span data-stu-id="4b47b-136">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="4b47b-137">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="4b47b-137">InvalidFocused</span></span>|<span data-ttu-id="4b47b-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4b47b-138">ValidationStates</span></span>|<span data-ttu-id="4b47b-139">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true` hat, dass das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="4b47b-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="4b47b-140">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="4b47b-140">InvalidUnfocused</span></span>|<span data-ttu-id="4b47b-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4b47b-141">ValidationStates</span></span>|<span data-ttu-id="4b47b-142">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, wenn das Steuerelement keinen Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="4b47b-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="passwordbox-controltemplate-example"></a><span data-ttu-id="4b47b-143">Beispiel für eine PasswordBox-ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="4b47b-143">PasswordBox ControlTemplate Example</span></span>

<span data-ttu-id="4b47b-144">Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.ControlTemplate> für das <xref:System.Windows.Controls.PasswordBox>-Steuerelement definiert wird.</span><span class="sxs-lookup"><span data-stu-id="4b47b-144">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

[!code-xaml[ControlTemplateExamples#PasswordBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#passwordbox)]

<span data-ttu-id="4b47b-145">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="4b47b-145">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="4b47b-146">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="4b47b-146">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="4b47b-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b47b-147">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="4b47b-148">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="4b47b-148">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="4b47b-149">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="4b47b-149">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="4b47b-150">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="4b47b-150">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="4b47b-151">Erstellen einer Vorlage für ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="4b47b-151">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
