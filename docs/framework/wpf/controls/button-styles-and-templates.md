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
ms.openlocfilehash: ec64c7c2051b12cba01135054a90e54864b7386a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59116336"
---
# <a name="button-styles-and-templates"></a><span data-ttu-id="590db-102">Button-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="590db-102">Button Styles and Templates</span></span>
<span data-ttu-id="590db-103">In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.Button> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="590db-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="590db-104">Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement eine unverwechselbare Darstellung verleihen.</span><span class="sxs-lookup"><span data-stu-id="590db-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="590db-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="590db-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="button-parts"></a><span data-ttu-id="590db-106">Schaltfläche Teilen</span><span class="sxs-lookup"><span data-stu-id="590db-106">Button Parts</span></span>  
 <span data-ttu-id="590db-107">Die <xref:System.Windows.Controls.Button> Steuerelement enthält keine benannten Teile.</span><span class="sxs-lookup"><span data-stu-id="590db-107">The <xref:System.Windows.Controls.Button> control does not have any named parts.</span></span>  
  
## <a name="button-states"></a><span data-ttu-id="590db-108">Schaltflächenzustände</span><span class="sxs-lookup"><span data-stu-id="590db-108">Button States</span></span>  
 <span data-ttu-id="590db-109">Die folgende Tabelle enthält die visuellen Zustände für die <xref:System.Windows.Controls.Button> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="590db-109">The following table lists the visual states for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
|<span data-ttu-id="590db-110">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="590db-110">VisualState Name</span></span>|<span data-ttu-id="590db-111">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="590db-111">VisualStateGroup Name</span></span>|<span data-ttu-id="590db-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="590db-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="590db-113">Normal</span><span class="sxs-lookup"><span data-stu-id="590db-113">Normal</span></span>|<span data-ttu-id="590db-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="590db-114">CommonStates</span></span>|<span data-ttu-id="590db-115">Der Standardzustand</span><span class="sxs-lookup"><span data-stu-id="590db-115">The default state.</span></span>|  
|<span data-ttu-id="590db-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="590db-116">MouseOver</span></span>|<span data-ttu-id="590db-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="590db-117">CommonStates</span></span>|<span data-ttu-id="590db-118">Der Mauszeiger ist über dem Steuerelement positioniert.</span><span class="sxs-lookup"><span data-stu-id="590db-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="590db-119">Gedrückt</span><span class="sxs-lookup"><span data-stu-id="590db-119">Pressed</span></span>|<span data-ttu-id="590db-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="590db-120">CommonStates</span></span>|<span data-ttu-id="590db-121">Das Steuerelement wird gedrückt.</span><span class="sxs-lookup"><span data-stu-id="590db-121">The control is pressed.</span></span>|  
|<span data-ttu-id="590db-122">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="590db-122">Disabled</span></span>|<span data-ttu-id="590db-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="590db-123">CommonStates</span></span>|<span data-ttu-id="590db-124">Das Steuerelement ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="590db-124">The control is disabled.</span></span>|  
|<span data-ttu-id="590db-125">Focused</span><span class="sxs-lookup"><span data-stu-id="590db-125">Focused</span></span>|<span data-ttu-id="590db-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="590db-126">FocusStates</span></span>|<span data-ttu-id="590db-127">Der Fokus liegt auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="590db-127">The control has focus.</span></span>|  
|<span data-ttu-id="590db-128">Ohne Fokus</span><span class="sxs-lookup"><span data-stu-id="590db-128">Unfocused</span></span>|<span data-ttu-id="590db-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="590db-129">FocusStates</span></span>|<span data-ttu-id="590db-130">Der Fokus liegt nicht auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="590db-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="590db-131">Gültig</span><span class="sxs-lookup"><span data-stu-id="590db-131">Valid</span></span>|<span data-ttu-id="590db-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="590db-132">ValidationStates</span></span>|<span data-ttu-id="590db-133">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="590db-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="590db-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="590db-134">InvalidFocused</span></span>|<span data-ttu-id="590db-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="590db-135">ValidationStates</span></span>|<span data-ttu-id="590db-136">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` und das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="590db-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="590db-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="590db-137">InvalidUnfocused</span></span>|<span data-ttu-id="590db-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="590db-138">ValidationStates</span></span>|<span data-ttu-id="590db-139">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` und das Steuerelement keinen Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="590db-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="button-controltemplate-example"></a><span data-ttu-id="590db-140">Schaltfläche "ControlTemplate"-Beispiel</span><span class="sxs-lookup"><span data-stu-id="590db-140">Button ControlTemplate Example</span></span>  
 <span data-ttu-id="590db-141">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.Button> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="590db-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Button](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#button)]  
  
 <span data-ttu-id="590db-142">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="590db-142">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="590db-143">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="590db-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="590db-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="590db-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="590db-145">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="590db-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="590db-146">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="590db-146">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="590db-147">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="590db-147">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="590db-148">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="590db-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
