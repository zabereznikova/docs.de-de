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
ms.openlocfilehash: 227ccbda8d570868258508935a5d95f0f40663ab
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458842"
---
# <a name="passwordbox-styles-and-templates"></a><span data-ttu-id="08bd1-102">PasswordBox-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="08bd1-102">PasswordBox Styles and Templates</span></span>

<span data-ttu-id="08bd1-103">In diesem Thema werden die Stile und Vorlagen für das <xref:System.Windows.Controls.PasswordBox>-Steuerelement beschrieben.</span><span class="sxs-lookup"><span data-stu-id="08bd1-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.PasswordBox> control.</span></span> <span data-ttu-id="08bd1-104">Sie können die Standard <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement eine eindeutige Darstellung zu verschaffen.</span><span class="sxs-lookup"><span data-stu-id="08bd1-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="08bd1-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="08bd1-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>

## <a name="passwordbox-parts"></a><span data-ttu-id="08bd1-106">PasswordBox-Teile</span><span class="sxs-lookup"><span data-stu-id="08bd1-106">PasswordBox Parts</span></span>

<span data-ttu-id="08bd1-107">In der folgenden Tabelle sind die benannten Teile für das <xref:System.Windows.Controls.PasswordBox>-Steuerelement aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="08bd1-107">The following table lists the named parts for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

|<span data-ttu-id="08bd1-108">Segment</span><span class="sxs-lookup"><span data-stu-id="08bd1-108">Part</span></span>|<span data-ttu-id="08bd1-109">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="08bd1-109">Type</span></span>|<span data-ttu-id="08bd1-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="08bd1-110">Description</span></span>|
|-|-|-|
|<span data-ttu-id="08bd1-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="08bd1-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="08bd1-112">Ein visuelles Element, das ein <xref:System.Windows.FrameworkElement>enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="08bd1-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="08bd1-113">Der Text des <xref:System.Windows.Controls.PasswordBox> wird in diesem Element angezeigt.</span><span class="sxs-lookup"><span data-stu-id="08bd1-113">The text of the <xref:System.Windows.Controls.PasswordBox> is displayed in this element.</span></span>|

## <a name="passwordbox-states"></a><span data-ttu-id="08bd1-114">PasswordBox-Zustände</span><span class="sxs-lookup"><span data-stu-id="08bd1-114">PasswordBox States</span></span>

<span data-ttu-id="08bd1-115">In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Controls.PasswordBox>-Steuerelement aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="08bd1-115">The following table lists the visual states for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

|<span data-ttu-id="08bd1-116">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="08bd1-116">VisualState Name</span></span>|<span data-ttu-id="08bd1-117">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="08bd1-117">VisualStateGroup Name</span></span>|<span data-ttu-id="08bd1-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="08bd1-118">Description</span></span>|
|-|-|-|
|<span data-ttu-id="08bd1-119">Normal</span><span class="sxs-lookup"><span data-stu-id="08bd1-119">Normal</span></span>|<span data-ttu-id="08bd1-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="08bd1-120">CommonStates</span></span>|<span data-ttu-id="08bd1-121">Der Standardzustand</span><span class="sxs-lookup"><span data-stu-id="08bd1-121">The default state.</span></span>|
|<span data-ttu-id="08bd1-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="08bd1-122">MouseOver</span></span>|<span data-ttu-id="08bd1-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="08bd1-123">CommonStates</span></span>|<span data-ttu-id="08bd1-124">Der Mauszeiger befindet sich auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="08bd1-124">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="08bd1-125">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="08bd1-125">Disabled</span></span>|<span data-ttu-id="08bd1-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="08bd1-126">CommonStates</span></span>|<span data-ttu-id="08bd1-127">Das Steuerelement ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="08bd1-127">The control is disabled.</span></span>|
|<span data-ttu-id="08bd1-128">Mit Fokus</span><span class="sxs-lookup"><span data-stu-id="08bd1-128">Focused</span></span>|<span data-ttu-id="08bd1-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="08bd1-129">FocusStates</span></span>|<span data-ttu-id="08bd1-130">Der Fokus liegt auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="08bd1-130">The control has focus.</span></span>|
|<span data-ttu-id="08bd1-131">Ohne Fokus</span><span class="sxs-lookup"><span data-stu-id="08bd1-131">Unfocused</span></span>|<span data-ttu-id="08bd1-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="08bd1-132">FocusStates</span></span>|<span data-ttu-id="08bd1-133">Der Fokus liegt nicht auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="08bd1-133">The control does not have focus.</span></span>|
|<span data-ttu-id="08bd1-134">Gültig</span><span class="sxs-lookup"><span data-stu-id="08bd1-134">Valid</span></span>|<span data-ttu-id="08bd1-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="08bd1-135">ValidationStates</span></span>|<span data-ttu-id="08bd1-136">Das-Steuerelement verwendet die <xref:System.Windows.Controls.Validation>-Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false`.</span><span class="sxs-lookup"><span data-stu-id="08bd1-136">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="08bd1-137">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="08bd1-137">InvalidFocused</span></span>|<span data-ttu-id="08bd1-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="08bd1-138">ValidationStates</span></span>|<span data-ttu-id="08bd1-139">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true` hat, dass das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="08bd1-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="08bd1-140">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="08bd1-140">InvalidUnfocused</span></span>|<span data-ttu-id="08bd1-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="08bd1-141">ValidationStates</span></span>|<span data-ttu-id="08bd1-142">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, wenn das Steuerelement keinen Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="08bd1-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="passwordbox-controltemplate-example"></a><span data-ttu-id="08bd1-143">Beispiel für eine PasswordBox-ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="08bd1-143">PasswordBox ControlTemplate Example</span></span>

<span data-ttu-id="08bd1-144">Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.ControlTemplate> für das <xref:System.Windows.Controls.PasswordBox>-Steuerelement definiert wird.</span><span class="sxs-lookup"><span data-stu-id="08bd1-144">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

[!code-xaml[ControlTemplateExamples#PasswordBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#passwordbox)]

<span data-ttu-id="08bd1-145">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="08bd1-145">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="08bd1-146">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="08bd1-146">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="08bd1-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="08bd1-147">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="08bd1-148">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="08bd1-148">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="08bd1-149">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="08bd1-149">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="08bd1-150">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="08bd1-150">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="08bd1-151">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="08bd1-151">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
