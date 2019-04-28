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
ms.openlocfilehash: ccc89e0e0c8977398ed162b246ff6cdede3b8351
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790870"
---
# <a name="textbox-styles-and-templates"></a><span data-ttu-id="f6142-102">TextBox-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="f6142-102">TextBox Styles and Templates</span></span>
<span data-ttu-id="f6142-103">In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.TextBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="f6142-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.TextBox> control.</span></span> <span data-ttu-id="f6142-104">Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement eine unverwechselbare Darstellung verleihen.</span><span class="sxs-lookup"><span data-stu-id="f6142-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="f6142-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="f6142-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="textbox-parts"></a><span data-ttu-id="f6142-106">TextBox-Teile</span><span class="sxs-lookup"><span data-stu-id="f6142-106">TextBox Parts</span></span>  
 <span data-ttu-id="f6142-107">Die folgende Tabelle enthält die benannten Teile für den <xref:System.Windows.Controls.TextBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="f6142-107">The following table lists the named parts for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="f6142-108">Segment</span><span class="sxs-lookup"><span data-stu-id="f6142-108">Part</span></span>|<span data-ttu-id="f6142-109">Typ</span><span class="sxs-lookup"><span data-stu-id="f6142-109">Type</span></span>|<span data-ttu-id="f6142-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f6142-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="f6142-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="f6142-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="f6142-112">Ein visuelles Element, das enthalten einer <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="f6142-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="f6142-113">Der Text, der die <xref:System.Windows.Controls.TextBox> wird in diesem Element angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f6142-113">The text of the <xref:System.Windows.Controls.TextBox> is displayed in this element.</span></span>|  
  
## <a name="textbox-states"></a><span data-ttu-id="f6142-114">TextBox-Zustände</span><span class="sxs-lookup"><span data-stu-id="f6142-114">TextBox States</span></span>  
 <span data-ttu-id="f6142-115">Die folgende Tabelle enthält die visuellen Zustände für die <xref:System.Windows.Controls.TextBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="f6142-115">The following table lists the visual states for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="f6142-116">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="f6142-116">VisualState Name</span></span>|<span data-ttu-id="f6142-117">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="f6142-117">VisualStateGroup Name</span></span>|<span data-ttu-id="f6142-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f6142-118">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="f6142-119">Normal</span><span class="sxs-lookup"><span data-stu-id="f6142-119">Normal</span></span>|<span data-ttu-id="f6142-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="f6142-120">CommonStates</span></span>|<span data-ttu-id="f6142-121">Der Standardzustand</span><span class="sxs-lookup"><span data-stu-id="f6142-121">The default state.</span></span>|  
|<span data-ttu-id="f6142-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="f6142-122">MouseOver</span></span>|<span data-ttu-id="f6142-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="f6142-123">CommonStates</span></span>|<span data-ttu-id="f6142-124">Der Mauszeiger befindet sich auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="f6142-124">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="f6142-125">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="f6142-125">Disabled</span></span>|<span data-ttu-id="f6142-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="f6142-126">CommonStates</span></span>|<span data-ttu-id="f6142-127">Das Steuerelement ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f6142-127">The control is disabled.</span></span>|  
|<span data-ttu-id="f6142-128">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="f6142-128">ReadOnly</span></span>|<span data-ttu-id="f6142-129">CommonStates</span><span class="sxs-lookup"><span data-stu-id="f6142-129">CommonStates</span></span>|<span data-ttu-id="f6142-130">Der Benutzer kann nicht den Text im Ändern der <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="f6142-130">The user cannot change the text in the <xref:System.Windows.Controls.TextBox>.</span></span>|  
|<span data-ttu-id="f6142-131">Focused</span><span class="sxs-lookup"><span data-stu-id="f6142-131">Focused</span></span>|<span data-ttu-id="f6142-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="f6142-132">FocusStates</span></span>|<span data-ttu-id="f6142-133">Der Fokus liegt auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="f6142-133">The control has focus.</span></span>|  
|<span data-ttu-id="f6142-134">Ohne Fokus</span><span class="sxs-lookup"><span data-stu-id="f6142-134">Unfocused</span></span>|<span data-ttu-id="f6142-135">FocusStates</span><span class="sxs-lookup"><span data-stu-id="f6142-135">FocusStates</span></span>|<span data-ttu-id="f6142-136">Der Fokus liegt nicht auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="f6142-136">The control does not have focus.</span></span>|  
|<span data-ttu-id="f6142-137">Gültig</span><span class="sxs-lookup"><span data-stu-id="f6142-137">Valid</span></span>|<span data-ttu-id="f6142-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f6142-138">ValidationStates</span></span>|<span data-ttu-id="f6142-139">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="f6142-139">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="f6142-140">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="f6142-140">InvalidFocused</span></span>|<span data-ttu-id="f6142-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f6142-141">ValidationStates</span></span>|<span data-ttu-id="f6142-142">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="f6142-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="f6142-143">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="f6142-143">InvalidUnfocused</span></span>|<span data-ttu-id="f6142-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f6142-144">ValidationStates</span></span>|<span data-ttu-id="f6142-145">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement keinen Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="f6142-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="textbox-controltemplate-example"></a><span data-ttu-id="f6142-146">TextBox-ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="f6142-146">TextBox ControlTemplate Example</span></span>  
 <span data-ttu-id="f6142-147">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.TextBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="f6142-147">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#TextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#textbox)]  
  
 <span data-ttu-id="f6142-148">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="f6142-148">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="f6142-149">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="f6142-149">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6142-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f6142-150">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="f6142-151">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="f6142-151">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="f6142-152">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="f6142-152">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="f6142-153">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="f6142-153">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="f6142-154">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="f6142-154">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
