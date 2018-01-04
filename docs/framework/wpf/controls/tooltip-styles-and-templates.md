---
title: ToolTip-Formate und Vorlagen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parts [WPF], ToolTip
- styles [WPF], ToolTip
- states [WPF], ToolTip
- ToolTip [WPF], styles and templates
- ControlTemplate [WPF], ToolTip
- templates [WPF], ToolTip
ms.assetid: 405fe385-4de9-49ee-a448-d8f4d1f740dd
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4e39372083ede5649addee4b493f2425116ec2aa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="tooltip-styles-and-templates"></a><span data-ttu-id="de922-102">ToolTip-Formate und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="de922-102">ToolTip Styles and Templates</span></span>
<span data-ttu-id="de922-103">In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.ToolTip> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="de922-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ToolTip> control.</span></span> <span data-ttu-id="de922-104">Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement ein einzigartiges aussehen zu verleihen.</span><span class="sxs-lookup"><span data-stu-id="de922-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="de922-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="de922-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="tooltip-parts"></a><span data-ttu-id="de922-106">ToolTip-Teile</span><span class="sxs-lookup"><span data-stu-id="de922-106">ToolTip Parts</span></span>  
 <span data-ttu-id="de922-107">Die <xref:System.Windows.Controls.ToolTip> Steuerelement enthält keine benannten Teile.</span><span class="sxs-lookup"><span data-stu-id="de922-107">The <xref:System.Windows.Controls.ToolTip> control does not have any named parts.</span></span>  
  
## <a name="tooltip-states"></a><span data-ttu-id="de922-108">QuickInfo-Zustände</span><span class="sxs-lookup"><span data-stu-id="de922-108">ToolTip States</span></span>  
 <span data-ttu-id="de922-109">Die folgende Tabelle enthält die visueller Zustände für die <xref:System.Windows.Controls.ToolTip> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="de922-109">The following table lists the visual states for the <xref:System.Windows.Controls.ToolTip> control.</span></span>  
  
|<span data-ttu-id="de922-110">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="de922-110">VisualState Name</span></span>|<span data-ttu-id="de922-111">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="de922-111">VisualStateGroup Name</span></span>|<span data-ttu-id="de922-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="de922-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="de922-113">Geschlossen</span><span class="sxs-lookup"><span data-stu-id="de922-113">Closed</span></span>|<span data-ttu-id="de922-114">OpenStates</span><span class="sxs-lookup"><span data-stu-id="de922-114">OpenStates</span></span>|<span data-ttu-id="de922-115">Der Standardzustand</span><span class="sxs-lookup"><span data-stu-id="de922-115">The default state.</span></span>|  
|<span data-ttu-id="de922-116">Öffnen</span><span class="sxs-lookup"><span data-stu-id="de922-116">Open</span></span>|<span data-ttu-id="de922-117">OpenStates</span><span class="sxs-lookup"><span data-stu-id="de922-117">OpenStates</span></span>|<span data-ttu-id="de922-118">Die <xref:System.Windows.Controls.ToolTip> sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="de922-118">The <xref:System.Windows.Controls.ToolTip> is visible.</span></span>|  
|<span data-ttu-id="de922-119">Gültig</span><span class="sxs-lookup"><span data-stu-id="de922-119">Valid</span></span>|<span data-ttu-id="de922-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="de922-120">ValidationStates</span></span>|<span data-ttu-id="de922-121">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="de922-121">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="de922-122">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="de922-122">InvalidFocused</span></span>|<span data-ttu-id="de922-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="de922-123">ValidationStates</span></span>|<span data-ttu-id="de922-124">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` weist das Steuerelement den Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="de922-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="de922-125">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="de922-125">InvalidUnfocused</span></span>|<span data-ttu-id="de922-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="de922-126">ValidationStates</span></span>|<span data-ttu-id="de922-127">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement verfügt nicht über den Fokus.</span><span class="sxs-lookup"><span data-stu-id="de922-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="tooltip-controltemplate-example"></a><span data-ttu-id="de922-128">Beispiel für QuickInfo-ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="de922-128">ToolTip ControlTemplate Example</span></span>  
 <span data-ttu-id="de922-129">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.ToolTip> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="de922-129">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ToolTip> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/tooltip.xaml#tooltip)]  
  
 <span data-ttu-id="de922-130">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="de922-130">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="de922-131">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="de922-131">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de922-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="de922-132">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="de922-133">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="de922-133">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="de922-134">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="de922-134">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="de922-135">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="de922-135">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="de922-136">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="de922-136">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
