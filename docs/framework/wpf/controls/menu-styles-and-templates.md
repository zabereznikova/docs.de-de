---
title: Menu-Stile und -Vorlagen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- styles [WPF], Menu
- ControlTemplate [WPF], Menu
- Menu [WPF], styles and templates
- states [WPF], Menu
- templates [WPF], Menu
- parts [WPF], Menu
ms.assetid: b89da183-9b87-42c6-ac53-731a42c7b09e
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d3b93de0089db58ed0a91aad4150432f8e7a1019
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="menu-styles-and-templates"></a><span data-ttu-id="ea32d-102">Menu-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="ea32d-102">Menu Styles and Templates</span></span>
<span data-ttu-id="ea32d-103">In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.Menu> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ea32d-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Menu> control.</span></span> <span data-ttu-id="ea32d-104">Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement ein einzigartiges aussehen zu verleihen.</span><span class="sxs-lookup"><span data-stu-id="ea32d-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="ea32d-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="ea32d-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="menu-parts"></a><span data-ttu-id="ea32d-106">Menu-Teile</span><span class="sxs-lookup"><span data-stu-id="ea32d-106">Menu Parts</span></span>  
 <span data-ttu-id="ea32d-107">Die <xref:System.Windows.Controls.Menu> Steuerelement enthält keine benannten Teile.</span><span class="sxs-lookup"><span data-stu-id="ea32d-107">The <xref:System.Windows.Controls.Menu> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="ea32d-108">Beim Erstellen einer <xref:System.Windows.Controls.ControlTemplate> für eine <xref:System.Windows.Controls.Menu>, Ihrer Vorlage enthalten möglicherweise eine <xref:System.Windows.Controls.ItemsPresenter> innerhalb einer <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="ea32d-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.Menu>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="ea32d-109">(Die <xref:System.Windows.Controls.ItemsPresenter> wird jedes Element in der <xref:System.Windows.Controls.Menu>; das <xref:System.Windows.Controls.ScrollViewer> Bildlauf im Steuerelement aktiviert).</span><span class="sxs-lookup"><span data-stu-id="ea32d-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.Menu>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="ea32d-110">Wenn die <xref:System.Windows.Controls.ItemsPresenter> ist kein direkte untergeordnetes Element von der <xref:System.Windows.Controls.ScrollViewer>, geben Sie die <xref:System.Windows.Controls.ItemsPresenter> den Namen `ItemsPresenter`.</span><span class="sxs-lookup"><span data-stu-id="ea32d-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="menu-states"></a><span data-ttu-id="ea32d-111">Menüzustände</span><span class="sxs-lookup"><span data-stu-id="ea32d-111">Menu States</span></span>  
 <span data-ttu-id="ea32d-112">Die folgende Tabelle enthält die visueller Zustände für die <xref:System.Windows.Controls.Menu> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ea32d-112">The following table lists the visual states for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
|<span data-ttu-id="ea32d-113">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="ea32d-113">VisualState Name</span></span>|<span data-ttu-id="ea32d-114">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="ea32d-114">VisualStateGroup Name</span></span>|<span data-ttu-id="ea32d-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ea32d-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="ea32d-116">Gültig</span><span class="sxs-lookup"><span data-stu-id="ea32d-116">Valid</span></span>|<span data-ttu-id="ea32d-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ea32d-117">ValidationStates</span></span>|<span data-ttu-id="ea32d-118">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="ea32d-118">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="ea32d-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="ea32d-119">InvalidFocused</span></span>|<span data-ttu-id="ea32d-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ea32d-120">ValidationStates</span></span>|<span data-ttu-id="ea32d-121">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` weist das Steuerelement den Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="ea32d-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="ea32d-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="ea32d-122">InvalidUnfocused</span></span>|<span data-ttu-id="ea32d-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ea32d-123">ValidationStates</span></span>|<span data-ttu-id="ea32d-124">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement verfügt nicht über den Fokus.</span><span class="sxs-lookup"><span data-stu-id="ea32d-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="menuitem-parts"></a><span data-ttu-id="ea32d-125">"MenuItem"-Teile</span><span class="sxs-lookup"><span data-stu-id="ea32d-125">MenuItem Parts</span></span>  
 <span data-ttu-id="ea32d-126">Die folgende Tabelle enthält die benannten Teile für die <xref:System.Windows.Controls.Menu> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ea32d-126">The following table lists the named parts for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
|<span data-ttu-id="ea32d-127">Segment</span><span class="sxs-lookup"><span data-stu-id="ea32d-127">Part</span></span>|<span data-ttu-id="ea32d-128">Typ</span><span class="sxs-lookup"><span data-stu-id="ea32d-128">Type</span></span>|<span data-ttu-id="ea32d-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ea32d-129">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="ea32d-130">PART_Popup</span><span class="sxs-lookup"><span data-stu-id="ea32d-130">PART_Popup</span></span>|<xref:System.Windows.Controls.Primitives.Popup>|<span data-ttu-id="ea32d-131">Der Bereich für das Untermenü.</span><span class="sxs-lookup"><span data-stu-id="ea32d-131">The area for the submenu.</span></span>|  
  
 <span data-ttu-id="ea32d-132">Beim Erstellen einer <xref:System.Windows.Controls.ControlTemplate> für eine <xref:System.Windows.Controls.MenuItem>, Ihrer Vorlage enthalten möglicherweise eine <xref:System.Windows.Controls.ItemsPresenter> innerhalb einer <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="ea32d-132">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.MenuItem>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="ea32d-133">(Die <xref:System.Windows.Controls.ItemsPresenter> wird jedes Element in der <xref:System.Windows.Controls.MenuItem>; das <xref:System.Windows.Controls.ScrollViewer> Bildlauf im Steuerelement aktiviert).</span><span class="sxs-lookup"><span data-stu-id="ea32d-133">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.MenuItem>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="ea32d-134">Wenn die <xref:System.Windows.Controls.ItemsPresenter> ist kein direkte untergeordnetes Element von der <xref:System.Windows.Controls.ScrollViewer>, geben Sie die <xref:System.Windows.Controls.ItemsPresenter> den Namen `ItemsPresenter`.</span><span class="sxs-lookup"><span data-stu-id="ea32d-134">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="menuitem-states"></a><span data-ttu-id="ea32d-135">Status "MenuItem"</span><span class="sxs-lookup"><span data-stu-id="ea32d-135">MenuItem States</span></span>  
 <span data-ttu-id="ea32d-136">Die folgende Tabelle enthält die visueller Zustände für die <xref:System.Windows.Controls.MenuItem> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ea32d-136">The following table lists the visual states for the <xref:System.Windows.Controls.MenuItem> control.</span></span>  
  
|<span data-ttu-id="ea32d-137">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="ea32d-137">VisualState Name</span></span>|<span data-ttu-id="ea32d-138">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="ea32d-138">VisualStateGroup Name</span></span>|<span data-ttu-id="ea32d-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ea32d-139">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="ea32d-140">Gültig</span><span class="sxs-lookup"><span data-stu-id="ea32d-140">Valid</span></span>|<span data-ttu-id="ea32d-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ea32d-141">ValidationStates</span></span>|<span data-ttu-id="ea32d-142">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="ea32d-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="ea32d-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="ea32d-143">InvalidFocused</span></span>|<span data-ttu-id="ea32d-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ea32d-144">ValidationStates</span></span>|<span data-ttu-id="ea32d-145">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` weist das Steuerelement den Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="ea32d-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="ea32d-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="ea32d-146">InvalidUnfocused</span></span>|<span data-ttu-id="ea32d-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ea32d-147">ValidationStates</span></span>|<span data-ttu-id="ea32d-148">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement verfügt nicht über den Fokus.</span><span class="sxs-lookup"><span data-stu-id="ea32d-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="menu-and-menuitem-controltemplate-example"></a><span data-ttu-id="ea32d-149">Menü- und "MenuItem" ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="ea32d-149">Menu and MenuItem ControlTemplate Example</span></span>  
 <span data-ttu-id="ea32d-150">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.Menu> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ea32d-150">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Menu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menu)]  
  
 <span data-ttu-id="ea32d-151">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.MenuItem> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ea32d-151">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.MenuItem> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#MenuItem](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menuitem)]  
  
 <span data-ttu-id="ea32d-152">Das folgende Beispiel definiert die `MenuScrollViewer`, der im vorherigen Beispiel verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ea32d-152">The following example defines the `MenuScrollViewer`, which is used in the previous example.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#MenuScrollViewer](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menuscrollviewer)]  
  
 <span data-ttu-id="ea32d-153">Die <xref:System.Windows.Controls.ControlTemplate> Beispiele verwenden eine oder mehrere der folgenden Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="ea32d-153">The <xref:System.Windows.Controls.ControlTemplate> examples use one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="ea32d-154">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="ea32d-154">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea32d-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ea32d-155">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="ea32d-156">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="ea32d-156">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="ea32d-157">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="ea32d-157">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="ea32d-158">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="ea32d-158">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="ea32d-159">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="ea32d-159">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
