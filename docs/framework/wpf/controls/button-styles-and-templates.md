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
ms.openlocfilehash: 64764d43191d30c191c5d6519982b16cfc86d26e
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460956"
---
# <a name="button-styles-and-templates"></a><span data-ttu-id="64f14-102">Button-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="64f14-102">Button Styles and Templates</span></span>
<span data-ttu-id="64f14-103">In diesem Thema werden die Stile und Vorlagen für das <xref:System.Windows.Controls.Button>-Steuerelement beschrieben.</span><span class="sxs-lookup"><span data-stu-id="64f14-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="64f14-104">Sie können die Standard <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement eine eindeutige Darstellung zu verschaffen.</span><span class="sxs-lookup"><span data-stu-id="64f14-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="64f14-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="64f14-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="button-parts"></a><span data-ttu-id="64f14-106">Schaltflächen Teile</span><span class="sxs-lookup"><span data-stu-id="64f14-106">Button Parts</span></span>  
 <span data-ttu-id="64f14-107">Das <xref:System.Windows.Controls.Button>-Steuerelement verfügt über keine benannten Teile.</span><span class="sxs-lookup"><span data-stu-id="64f14-107">The <xref:System.Windows.Controls.Button> control does not have any named parts.</span></span>  
  
## <a name="button-states"></a><span data-ttu-id="64f14-108">Schaltflächen Zustände</span><span class="sxs-lookup"><span data-stu-id="64f14-108">Button States</span></span>  
 <span data-ttu-id="64f14-109">In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Controls.Button>-Steuerelement aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="64f14-109">The following table lists the visual states for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
|<span data-ttu-id="64f14-110">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="64f14-110">VisualState Name</span></span>|<span data-ttu-id="64f14-111">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="64f14-111">VisualStateGroup Name</span></span>|<span data-ttu-id="64f14-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="64f14-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="64f14-113">Normal</span><span class="sxs-lookup"><span data-stu-id="64f14-113">Normal</span></span>|<span data-ttu-id="64f14-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="64f14-114">CommonStates</span></span>|<span data-ttu-id="64f14-115">Der Standardzustand</span><span class="sxs-lookup"><span data-stu-id="64f14-115">The default state.</span></span>|  
|<span data-ttu-id="64f14-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="64f14-116">MouseOver</span></span>|<span data-ttu-id="64f14-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="64f14-117">CommonStates</span></span>|<span data-ttu-id="64f14-118">Der Mauszeiger befindet sich auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="64f14-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="64f14-119">Gedrückt</span><span class="sxs-lookup"><span data-stu-id="64f14-119">Pressed</span></span>|<span data-ttu-id="64f14-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="64f14-120">CommonStates</span></span>|<span data-ttu-id="64f14-121">Das Steuerelement wird gedrückt.</span><span class="sxs-lookup"><span data-stu-id="64f14-121">The control is pressed.</span></span>|  
|<span data-ttu-id="64f14-122">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="64f14-122">Disabled</span></span>|<span data-ttu-id="64f14-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="64f14-123">CommonStates</span></span>|<span data-ttu-id="64f14-124">Das Steuerelement ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="64f14-124">The control is disabled.</span></span>|  
|<span data-ttu-id="64f14-125">Mit Fokus</span><span class="sxs-lookup"><span data-stu-id="64f14-125">Focused</span></span>|<span data-ttu-id="64f14-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="64f14-126">FocusStates</span></span>|<span data-ttu-id="64f14-127">Der Fokus liegt auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="64f14-127">The control has focus.</span></span>|  
|<span data-ttu-id="64f14-128">Ohne Fokus</span><span class="sxs-lookup"><span data-stu-id="64f14-128">Unfocused</span></span>|<span data-ttu-id="64f14-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="64f14-129">FocusStates</span></span>|<span data-ttu-id="64f14-130">Der Fokus liegt nicht auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="64f14-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="64f14-131">Gültig</span><span class="sxs-lookup"><span data-stu-id="64f14-131">Valid</span></span>|<span data-ttu-id="64f14-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="64f14-132">ValidationStates</span></span>|<span data-ttu-id="64f14-133">Das-Steuerelement verwendet die <xref:System.Windows.Controls.Validation>-Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false`.</span><span class="sxs-lookup"><span data-stu-id="64f14-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="64f14-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="64f14-134">InvalidFocused</span></span>|<span data-ttu-id="64f14-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="64f14-135">ValidationStates</span></span>|<span data-ttu-id="64f14-136">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, und das Steuerelement besitzt den Fokus.</span><span class="sxs-lookup"><span data-stu-id="64f14-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="64f14-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="64f14-137">InvalidUnfocused</span></span>|<span data-ttu-id="64f14-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="64f14-138">ValidationStates</span></span>|<span data-ttu-id="64f14-139">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, und das Steuerelement besitzt keinen Fokus.</span><span class="sxs-lookup"><span data-stu-id="64f14-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="button-controltemplate-example"></a><span data-ttu-id="64f14-140">Schaltflächen-ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="64f14-140">Button ControlTemplate Example</span></span>  
 <span data-ttu-id="64f14-141">Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.ControlTemplate> für das <xref:System.Windows.Controls.Button>-Steuerelement definiert wird.</span><span class="sxs-lookup"><span data-stu-id="64f14-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Button](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#button)]  
  
 <span data-ttu-id="64f14-142">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="64f14-142">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="64f14-143">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="64f14-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64f14-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="64f14-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="64f14-145">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="64f14-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="64f14-146">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="64f14-146">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="64f14-147">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="64f14-147">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="64f14-148">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="64f14-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
