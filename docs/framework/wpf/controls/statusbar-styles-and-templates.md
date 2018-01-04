---
title: StatusBar-Stile und -Vorlagen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ControlTemplate [WPF], StatusBar
- styles [WPF], StatusBar
- templates [WPF], StatusBar
- states [WPF], StatusBar
- parts [WPF], StatusBar
- StatusBar [WPF], styles and templates
ms.assetid: 9f5e1c25-81eb-4756-a0ac-d9e1fbe33ee2
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 370f8f9bc61ffbdd3b98743d11f61613803e6d98
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="statusbar-styles-and-templates"></a><span data-ttu-id="7301e-102">StatusBar-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="7301e-102">StatusBar Styles and Templates</span></span>
<span data-ttu-id="7301e-103">In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.Primitives.StatusBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="7301e-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span> <span data-ttu-id="7301e-104">Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement ein einzigartiges aussehen zu verleihen.</span><span class="sxs-lookup"><span data-stu-id="7301e-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="7301e-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="7301e-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="statusbar-parts"></a><span data-ttu-id="7301e-106">StatusBar-Teile</span><span class="sxs-lookup"><span data-stu-id="7301e-106">StatusBar Parts</span></span>  
 <span data-ttu-id="7301e-107">Die <xref:System.Windows.Controls.Primitives.StatusBar> Steuerelement enthält keine benannten Teile.</span><span class="sxs-lookup"><span data-stu-id="7301e-107">The <xref:System.Windows.Controls.Primitives.StatusBar> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="7301e-108">StatusBar-Zustände</span><span class="sxs-lookup"><span data-stu-id="7301e-108">StatusBar States</span></span>  
 <span data-ttu-id="7301e-109">Die folgende Tabelle enthält die visueller Zustände für die <xref:System.Windows.Controls.Primitives.StatusBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="7301e-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
|<span data-ttu-id="7301e-110">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="7301e-110">VisualState Name</span></span>|<span data-ttu-id="7301e-111">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="7301e-111">VisualStateGroup Name</span></span>|<span data-ttu-id="7301e-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7301e-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="7301e-113">Gültig</span><span class="sxs-lookup"><span data-stu-id="7301e-113">Valid</span></span>|<span data-ttu-id="7301e-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="7301e-114">ValidationStates</span></span>|<span data-ttu-id="7301e-115">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="7301e-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="7301e-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="7301e-116">InvalidFocused</span></span>|<span data-ttu-id="7301e-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="7301e-117">ValidationStates</span></span>|<span data-ttu-id="7301e-118">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` weist das Steuerelement den Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="7301e-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="7301e-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="7301e-119">InvalidUnfocused</span></span>|<span data-ttu-id="7301e-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="7301e-120">ValidationStates</span></span>|<span data-ttu-id="7301e-121">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement verfügt nicht über den Fokus.</span><span class="sxs-lookup"><span data-stu-id="7301e-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbaritem-parts"></a><span data-ttu-id="7301e-122">StatusBarItem-Teile</span><span class="sxs-lookup"><span data-stu-id="7301e-122">StatusBarItem Parts</span></span>  
 <span data-ttu-id="7301e-123">Die <xref:System.Windows.Controls.Primitives.StatusBarItem> Steuerelement enthält keine benannten Teile.</span><span class="sxs-lookup"><span data-stu-id="7301e-123">The <xref:System.Windows.Controls.Primitives.StatusBarItem> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="7301e-124">StatusBar-Zustände</span><span class="sxs-lookup"><span data-stu-id="7301e-124">StatusBar States</span></span>  
 <span data-ttu-id="7301e-125">Die folgende Tabelle enthält die visueller Zustände für die <xref:System.Windows.Controls.Primitives.StatusBarItem> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="7301e-125">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBarItem> control.</span></span>  
  
|<span data-ttu-id="7301e-126">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="7301e-126">VisualState Name</span></span>|<span data-ttu-id="7301e-127">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="7301e-127">VisualStateGroup Name</span></span>|<span data-ttu-id="7301e-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7301e-128">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="7301e-129">Gültig</span><span class="sxs-lookup"><span data-stu-id="7301e-129">Valid</span></span>|<span data-ttu-id="7301e-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="7301e-130">ValidationStates</span></span>|<span data-ttu-id="7301e-131">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="7301e-131">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="7301e-132">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="7301e-132">InvalidFocused</span></span>|<span data-ttu-id="7301e-133">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="7301e-133">ValidationStates</span></span>|<span data-ttu-id="7301e-134">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` weist das Steuerelement den Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="7301e-134">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="7301e-135">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="7301e-135">InvalidUnfocused</span></span>|<span data-ttu-id="7301e-136">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="7301e-136">ValidationStates</span></span>|<span data-ttu-id="7301e-137">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement verfügt nicht über den Fokus.</span><span class="sxs-lookup"><span data-stu-id="7301e-137">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbar-controltemplate-example"></a><span data-ttu-id="7301e-138">Beispiel für StatusBar-ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="7301e-138">StatusBar ControlTemplate Example</span></span>  
 <span data-ttu-id="7301e-139">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.Primitives.StatusBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="7301e-139">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#StatusBar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/statusbar.xaml#statusbar)]  
  
 <span data-ttu-id="7301e-140">Die <xref:System.Windows.Controls.ControlTemplate> verwendet wird, eine oder mehrere der folgenden Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="7301e-140">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="7301e-141">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="7301e-141">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7301e-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7301e-142">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="7301e-143">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="7301e-143">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="7301e-144">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="7301e-144">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="7301e-145">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="7301e-145">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="7301e-146">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="7301e-146">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
