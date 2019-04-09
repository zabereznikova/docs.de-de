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
ms.openlocfilehash: 64b5b66f7f32ea31b51b4da990ceede4078c27cf
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59177722"
---
# <a name="statusbar-styles-and-templates"></a><span data-ttu-id="0e787-102">StatusBar-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="0e787-102">StatusBar Styles and Templates</span></span>
<span data-ttu-id="0e787-103">In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.Primitives.StatusBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0e787-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span> <span data-ttu-id="0e787-104">Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement eine unverwechselbare Darstellung verleihen.</span><span class="sxs-lookup"><span data-stu-id="0e787-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="0e787-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="0e787-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="statusbar-parts"></a><span data-ttu-id="0e787-106">StatusBar-Teile</span><span class="sxs-lookup"><span data-stu-id="0e787-106">StatusBar Parts</span></span>  
 <span data-ttu-id="0e787-107">Die <xref:System.Windows.Controls.Primitives.StatusBar> Steuerelement enthält keine benannten Teile.</span><span class="sxs-lookup"><span data-stu-id="0e787-107">The <xref:System.Windows.Controls.Primitives.StatusBar> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="0e787-108">StatusBar-Zustände</span><span class="sxs-lookup"><span data-stu-id="0e787-108">StatusBar States</span></span>  
 <span data-ttu-id="0e787-109">Die folgende Tabelle enthält die visuellen Zustände für die <xref:System.Windows.Controls.Primitives.StatusBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0e787-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
|<span data-ttu-id="0e787-110">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="0e787-110">VisualState Name</span></span>|<span data-ttu-id="0e787-111">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="0e787-111">VisualStateGroup Name</span></span>|<span data-ttu-id="0e787-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e787-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="0e787-113">Gültig</span><span class="sxs-lookup"><span data-stu-id="0e787-113">Valid</span></span>|<span data-ttu-id="0e787-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0e787-114">ValidationStates</span></span>|<span data-ttu-id="0e787-115">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="0e787-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="0e787-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="0e787-116">InvalidFocused</span></span>|<span data-ttu-id="0e787-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0e787-117">ValidationStates</span></span>|<span data-ttu-id="0e787-118">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="0e787-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="0e787-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="0e787-119">InvalidUnfocused</span></span>|<span data-ttu-id="0e787-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0e787-120">ValidationStates</span></span>|<span data-ttu-id="0e787-121">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement keinen Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="0e787-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbaritem-parts"></a><span data-ttu-id="0e787-122">StatusBarItem-Teile</span><span class="sxs-lookup"><span data-stu-id="0e787-122">StatusBarItem Parts</span></span>  
 <span data-ttu-id="0e787-123">Die <xref:System.Windows.Controls.Primitives.StatusBarItem> Steuerelement enthält keine benannten Teile.</span><span class="sxs-lookup"><span data-stu-id="0e787-123">The <xref:System.Windows.Controls.Primitives.StatusBarItem> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="0e787-124">StatusBar-Zustände</span><span class="sxs-lookup"><span data-stu-id="0e787-124">StatusBar States</span></span>  
 <span data-ttu-id="0e787-125">Die folgende Tabelle enthält die visuellen Zustände für die <xref:System.Windows.Controls.Primitives.StatusBarItem> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0e787-125">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBarItem> control.</span></span>  
  
|<span data-ttu-id="0e787-126">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="0e787-126">VisualState Name</span></span>|<span data-ttu-id="0e787-127">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="0e787-127">VisualStateGroup Name</span></span>|<span data-ttu-id="0e787-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e787-128">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="0e787-129">Gültig</span><span class="sxs-lookup"><span data-stu-id="0e787-129">Valid</span></span>|<span data-ttu-id="0e787-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0e787-130">ValidationStates</span></span>|<span data-ttu-id="0e787-131">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="0e787-131">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="0e787-132">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="0e787-132">InvalidFocused</span></span>|<span data-ttu-id="0e787-133">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0e787-133">ValidationStates</span></span>|<span data-ttu-id="0e787-134">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="0e787-134">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="0e787-135">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="0e787-135">InvalidUnfocused</span></span>|<span data-ttu-id="0e787-136">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0e787-136">ValidationStates</span></span>|<span data-ttu-id="0e787-137">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement keinen Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="0e787-137">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbar-controltemplate-example"></a><span data-ttu-id="0e787-138">StatusBar-ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="0e787-138">StatusBar ControlTemplate Example</span></span>  
 <span data-ttu-id="0e787-139">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.Primitives.StatusBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0e787-139">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#StatusBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/statusbar.xaml#statusbar)]  
  
 <span data-ttu-id="0e787-140">Die <xref:System.Windows.Controls.ControlTemplate> verwendet wird, eine oder mehrere der folgenden Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="0e787-140">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="0e787-141">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="0e787-141">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e787-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0e787-142">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="0e787-143">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="0e787-143">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="0e787-144">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="0e787-144">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="0e787-145">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="0e787-145">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="0e787-146">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="0e787-146">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
