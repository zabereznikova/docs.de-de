---
title: ScrollViewer-Stile und -Vorlagen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parts [WPF], ScrollViewer
- states [WPF], ScrollViewer
- styles [WPF], ScrollViewer
- templates [WPF], ScrollViewer
- ControlTemplate [WPF], ScrollViewer
- ScrollViewer [WPF], styles and templates
ms.assetid: dffdd822-ae69-4946-abaf-710860cd65b2
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 74f8a693a143e1c6788dd79a1c1bbd1954f8cfd0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="scrollviewer-styles-and-templates"></a><span data-ttu-id="5e24d-102">ScrollViewer-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="5e24d-102">ScrollViewer Styles and Templates</span></span>
<span data-ttu-id="5e24d-103">In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.ScrollViewer> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="5e24d-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span> <span data-ttu-id="5e24d-104">Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement ein einzigartiges aussehen zu verleihen.</span><span class="sxs-lookup"><span data-stu-id="5e24d-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="5e24d-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="5e24d-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="scrollviewer-parts"></a><span data-ttu-id="5e24d-106">ScrollViewer-Teile</span><span class="sxs-lookup"><span data-stu-id="5e24d-106">ScrollViewer Parts</span></span>  
 <span data-ttu-id="5e24d-107">Die folgende Tabelle enthält die benannten Teile für die <xref:System.Windows.Controls.ScrollViewer> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="5e24d-107">The following table lists the named parts for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="5e24d-108">Segment</span><span class="sxs-lookup"><span data-stu-id="5e24d-108">Part</span></span>|<span data-ttu-id="5e24d-109">Typ</span><span class="sxs-lookup"><span data-stu-id="5e24d-109">Type</span></span>|<span data-ttu-id="5e24d-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5e24d-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="5e24d-111">PART_ScrollContentPresenter</span><span class="sxs-lookup"><span data-stu-id="5e24d-111">PART_ScrollContentPresenter</span></span>|<xref:System.Windows.Controls.ScrollContentPresenter>|<span data-ttu-id="5e24d-112">Der Platzhalter für den Inhalt in die <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="5e24d-112">The placeholder for content in the <xref:System.Windows.Controls.ScrollViewer>.</span></span>|  
|<span data-ttu-id="5e24d-113">"PART_HorizontalScrollBar"</span><span class="sxs-lookup"><span data-stu-id="5e24d-113">PART_HorizontalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="5e24d-114">Die <xref:System.Windows.Controls.Primitives.ScrollBar> verwendet, um den Inhalt einen horizontalen Bildlauf durchführen.</span><span class="sxs-lookup"><span data-stu-id="5e24d-114">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content horizontally.</span></span>|  
|<span data-ttu-id="5e24d-115">"PART_VerticalScrollBar"</span><span class="sxs-lookup"><span data-stu-id="5e24d-115">PART_VerticalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="5e24d-116">Die <xref:System.Windows.Controls.Primitives.ScrollBar> verwendet, um den Inhalt vertikaler Bildlauf durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5e24d-116">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content vertically.</span></span>|  
  
## <a name="scrollviewer-states"></a><span data-ttu-id="5e24d-117">ScrollViewer-Zustände</span><span class="sxs-lookup"><span data-stu-id="5e24d-117">ScrollViewer States</span></span>  
 <span data-ttu-id="5e24d-118">Die folgende Tabelle enthält die visueller Zustände für die <xref:System.Windows.Controls.ScrollViewer> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="5e24d-118">The following table lists the visual states for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="5e24d-119">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="5e24d-119">VisualState Name</span></span>|<span data-ttu-id="5e24d-120">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="5e24d-120">VisualStateGroup Name</span></span>|<span data-ttu-id="5e24d-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5e24d-121">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="5e24d-122">Gültig</span><span class="sxs-lookup"><span data-stu-id="5e24d-122">Valid</span></span>|<span data-ttu-id="5e24d-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5e24d-123">ValidationStates</span></span>|<span data-ttu-id="5e24d-124">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="5e24d-124">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="5e24d-125">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="5e24d-125">InvalidFocused</span></span>|<span data-ttu-id="5e24d-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5e24d-126">ValidationStates</span></span>|<span data-ttu-id="5e24d-127">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` weist das Steuerelement den Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="5e24d-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="5e24d-128">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="5e24d-128">InvalidUnfocused</span></span>|<span data-ttu-id="5e24d-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5e24d-129">ValidationStates</span></span>|<span data-ttu-id="5e24d-130">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement verfügt nicht über den Fokus.</span><span class="sxs-lookup"><span data-stu-id="5e24d-130">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="scrollviewer-controltemplate-example"></a><span data-ttu-id="5e24d-131">Beispiel für ScrollViewer-ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="5e24d-131">ScrollViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="5e24d-132">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.ScrollViewer> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="5e24d-132">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollViewer](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollviewer.xaml#scrollviewer)]  
  
 <span data-ttu-id="5e24d-133">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="5e24d-133">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="5e24d-134">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="5e24d-134">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e24d-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e24d-135">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="5e24d-136">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="5e24d-136">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="5e24d-137">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="5e24d-137">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="5e24d-138">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="5e24d-138">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="5e24d-139">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="5e24d-139">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
