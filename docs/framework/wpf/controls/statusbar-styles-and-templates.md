---
title: StatusBar-Stile und -Vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], StatusBar
- styles [WPF], StatusBar
- templates [WPF], StatusBar
- states [WPF], StatusBar
- parts [WPF], StatusBar
- StatusBar [WPF], styles and templates
ms.assetid: 9f5e1c25-81eb-4756-a0ac-d9e1fbe33ee2
ms.openlocfilehash: 843c9003edbe94115719a63a968eda3833515a85
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283376"
---
# <a name="statusbar-styles-and-templates"></a><span data-ttu-id="fc2ac-102">StatusBar-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="fc2ac-102">StatusBar Styles and Templates</span></span>
<span data-ttu-id="fc2ac-103">In diesem Thema werden die Stile und Vorlagen für das <xref:System.Windows.Controls.Primitives.StatusBar>-Steuerelement beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fc2ac-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span> <span data-ttu-id="fc2ac-104">Sie können die Standard <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement eine eindeutige Darstellung zu verschaffen.</span><span class="sxs-lookup"><span data-stu-id="fc2ac-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="fc2ac-105">Weitere Informationen finden Sie unter [Erstellen einer Vorlage für ein-Steuer](../../../desktop-wpf/themes/how-to-create-apply-template.md)Element.</span><span class="sxs-lookup"><span data-stu-id="fc2ac-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="statusbar-parts"></a><span data-ttu-id="fc2ac-106">StatusBar-Teile</span><span class="sxs-lookup"><span data-stu-id="fc2ac-106">StatusBar Parts</span></span>  
 <span data-ttu-id="fc2ac-107">Das <xref:System.Windows.Controls.Primitives.StatusBar>-Steuerelement verfügt über keine benannten Teile.</span><span class="sxs-lookup"><span data-stu-id="fc2ac-107">The <xref:System.Windows.Controls.Primitives.StatusBar> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="fc2ac-108">StatusBar-Zustände</span><span class="sxs-lookup"><span data-stu-id="fc2ac-108">StatusBar States</span></span>  
 <span data-ttu-id="fc2ac-109">In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Controls.Primitives.StatusBar>-Steuerelement aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="fc2ac-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
|<span data-ttu-id="fc2ac-110">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="fc2ac-110">VisualState Name</span></span>|<span data-ttu-id="fc2ac-111">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="fc2ac-111">VisualStateGroup Name</span></span>|<span data-ttu-id="fc2ac-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fc2ac-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="fc2ac-113">Gültig</span><span class="sxs-lookup"><span data-stu-id="fc2ac-113">Valid</span></span>|<span data-ttu-id="fc2ac-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fc2ac-114">ValidationStates</span></span>|<span data-ttu-id="fc2ac-115">Das-Steuerelement verwendet die <xref:System.Windows.Controls.Validation>-Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false`.</span><span class="sxs-lookup"><span data-stu-id="fc2ac-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="fc2ac-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="fc2ac-116">InvalidFocused</span></span>|<span data-ttu-id="fc2ac-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fc2ac-117">ValidationStates</span></span>|<span data-ttu-id="fc2ac-118">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true` hat, dass das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="fc2ac-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="fc2ac-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="fc2ac-119">InvalidUnfocused</span></span>|<span data-ttu-id="fc2ac-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fc2ac-120">ValidationStates</span></span>|<span data-ttu-id="fc2ac-121">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, wenn das Steuerelement keinen Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="fc2ac-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbaritem-parts"></a><span data-ttu-id="fc2ac-122">Status Element Teile</span><span class="sxs-lookup"><span data-stu-id="fc2ac-122">StatusBarItem Parts</span></span>  
 <span data-ttu-id="fc2ac-123">Das <xref:System.Windows.Controls.Primitives.StatusBarItem>-Steuerelement verfügt über keine benannten Teile.</span><span class="sxs-lookup"><span data-stu-id="fc2ac-123">The <xref:System.Windows.Controls.Primitives.StatusBarItem> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="fc2ac-124">StatusBar-Zustände</span><span class="sxs-lookup"><span data-stu-id="fc2ac-124">StatusBar States</span></span>  
 <span data-ttu-id="fc2ac-125">In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Controls.Primitives.StatusBarItem>-Steuerelement aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="fc2ac-125">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBarItem> control.</span></span>  
  
|<span data-ttu-id="fc2ac-126">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="fc2ac-126">VisualState Name</span></span>|<span data-ttu-id="fc2ac-127">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="fc2ac-127">VisualStateGroup Name</span></span>|<span data-ttu-id="fc2ac-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fc2ac-128">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="fc2ac-129">Gültig</span><span class="sxs-lookup"><span data-stu-id="fc2ac-129">Valid</span></span>|<span data-ttu-id="fc2ac-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fc2ac-130">ValidationStates</span></span>|<span data-ttu-id="fc2ac-131">Das-Steuerelement verwendet die <xref:System.Windows.Controls.Validation>-Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false`.</span><span class="sxs-lookup"><span data-stu-id="fc2ac-131">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="fc2ac-132">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="fc2ac-132">InvalidFocused</span></span>|<span data-ttu-id="fc2ac-133">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fc2ac-133">ValidationStates</span></span>|<span data-ttu-id="fc2ac-134">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true` hat, dass das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="fc2ac-134">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="fc2ac-135">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="fc2ac-135">InvalidUnfocused</span></span>|<span data-ttu-id="fc2ac-136">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fc2ac-136">ValidationStates</span></span>|<span data-ttu-id="fc2ac-137">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, wenn das Steuerelement keinen Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="fc2ac-137">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbar-controltemplate-example"></a><span data-ttu-id="fc2ac-138">StatusBar ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="fc2ac-138">StatusBar ControlTemplate Example</span></span>  
 <span data-ttu-id="fc2ac-139">Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.ControlTemplate> für das <xref:System.Windows.Controls.Primitives.StatusBar>-Steuerelement definiert wird.</span><span class="sxs-lookup"><span data-stu-id="fc2ac-139">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#StatusBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/statusbar.xaml#statusbar)]  
  
 <span data-ttu-id="fc2ac-140">Der <xref:System.Windows.Controls.ControlTemplate> verwendet mindestens eine der folgenden Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="fc2ac-140">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="fc2ac-141">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="fc2ac-141">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc2ac-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc2ac-142">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="fc2ac-143">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="fc2ac-143">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="fc2ac-144">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="fc2ac-144">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="fc2ac-145">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="fc2ac-145">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="fc2ac-146">Erstellen einer Vorlage für ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="fc2ac-146">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
