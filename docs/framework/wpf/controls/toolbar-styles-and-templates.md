---
title: ToolBar-Stile und -Vorlagen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- states [WPF], ToolBar
- styles [WPF], ToolBar
- ControlTemplate [WPF], ToolBar
- parts [WPF], ToolBar
- ToolBar [WPF], styles and templates
- templates [WPF], ToolBar
ms.assetid: bd875f46-4690-46f5-81e0-f11a9822484f
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d56858f3785a4d4d49a0781fbf4c19397a3bb375
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="toolbar-styles-and-templates"></a><span data-ttu-id="d14ee-102">ToolBar-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="d14ee-102">ToolBar Styles and Templates</span></span>
<span data-ttu-id="d14ee-103">In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.ToolBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="d14ee-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ToolBar> control.</span></span> <span data-ttu-id="d14ee-104">Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement ein einzigartiges aussehen zu verleihen.</span><span class="sxs-lookup"><span data-stu-id="d14ee-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="d14ee-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="d14ee-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="toolbar-parts"></a><span data-ttu-id="d14ee-106">ToolBar-Teile</span><span class="sxs-lookup"><span data-stu-id="d14ee-106">ToolBar Parts</span></span>  
 <span data-ttu-id="d14ee-107">Die folgende Tabelle enthält die benannten Teile für die <xref:System.Windows.Controls.ToolBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="d14ee-107">The following table lists the named parts for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
|<span data-ttu-id="d14ee-108">Segment</span><span class="sxs-lookup"><span data-stu-id="d14ee-108">Part</span></span>|<span data-ttu-id="d14ee-109">Typ</span><span class="sxs-lookup"><span data-stu-id="d14ee-109">Type</span></span>|<span data-ttu-id="d14ee-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d14ee-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="d14ee-111">PART_ToolBarPanel</span><span class="sxs-lookup"><span data-stu-id="d14ee-111">PART_ToolBarPanel</span></span>|<xref:System.Windows.Controls.Primitives.ToolBarPanel>|<span data-ttu-id="d14ee-112">Das Objekt, das die Steuerelemente enthält, auf die <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="d14ee-112">The object that contains the controls on the <xref:System.Windows.Controls.ToolBar>.</span></span>|  
|<span data-ttu-id="d14ee-113">PART_ToolBarOverflowPanel</span><span class="sxs-lookup"><span data-stu-id="d14ee-113">PART_ToolBarOverflowPanel</span></span>|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|<span data-ttu-id="d14ee-114">Das Objekt, das die Steuerelemente enthält, der im Bereich "Überlauf" sind, die <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="d14ee-114">The object that contains the controls that are in the overflow area of the <xref:System.Windows.Controls.ToolBar>.</span></span>|  
  
 <span data-ttu-id="d14ee-115">Beim Erstellen einer <xref:System.Windows.Controls.ControlTemplate> für eine <xref:System.Windows.Controls.ToolBar>, Ihrer Vorlage enthalten möglicherweise eine <xref:System.Windows.Controls.ItemsPresenter> innerhalb einer <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="d14ee-115">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ToolBar>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="d14ee-116">(Die <xref:System.Windows.Controls.ItemsPresenter> wird jedes Element in der <xref:System.Windows.Controls.ToolBar>; das <xref:System.Windows.Controls.ScrollViewer> Bildlauf im Steuerelement aktiviert).</span><span class="sxs-lookup"><span data-stu-id="d14ee-116">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ToolBar>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="d14ee-117">Wenn die <xref:System.Windows.Controls.ItemsPresenter> ist kein direkte untergeordnetes Element von der <xref:System.Windows.Controls.ScrollViewer>, geben Sie die <xref:System.Windows.Controls.ItemsPresenter> den Namen `ItemsPresenter`.</span><span class="sxs-lookup"><span data-stu-id="d14ee-117">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="toolbar-states"></a><span data-ttu-id="d14ee-118">ToolBar-Zustände</span><span class="sxs-lookup"><span data-stu-id="d14ee-118">ToolBar States</span></span>  
 <span data-ttu-id="d14ee-119">Die folgende Tabelle enthält die visueller Zustände für die <xref:System.Windows.Controls.ToolBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="d14ee-119">The following table lists the visual states for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
|<span data-ttu-id="d14ee-120">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="d14ee-120">VisualState Name</span></span>|<span data-ttu-id="d14ee-121">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="d14ee-121">VisualStateGroup Name</span></span>|<span data-ttu-id="d14ee-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d14ee-122">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="d14ee-123">Gültig</span><span class="sxs-lookup"><span data-stu-id="d14ee-123">Valid</span></span>|<span data-ttu-id="d14ee-124">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d14ee-124">ValidationStates</span></span>|<span data-ttu-id="d14ee-125">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="d14ee-125">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="d14ee-126">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="d14ee-126">InvalidFocused</span></span>|<span data-ttu-id="d14ee-127">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d14ee-127">ValidationStates</span></span>|<span data-ttu-id="d14ee-128">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` weist das Steuerelement den Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="d14ee-128">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="d14ee-129">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="d14ee-129">InvalidUnfocused</span></span>|<span data-ttu-id="d14ee-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d14ee-130">ValidationStates</span></span>|<span data-ttu-id="d14ee-131">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement verfügt nicht über den Fokus.</span><span class="sxs-lookup"><span data-stu-id="d14ee-131">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="toolbar-controltemplate-example"></a><span data-ttu-id="d14ee-132">Symbolleiste ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="d14ee-132">ToolBar ControlTemplate Example</span></span>  
 <span data-ttu-id="d14ee-133">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.ToolBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="d14ee-133">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToolBar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/toolbar.xaml#toolbar)]  
  
 <span data-ttu-id="d14ee-134">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="d14ee-134">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="d14ee-135">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="d14ee-135">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d14ee-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d14ee-136">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="d14ee-137">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="d14ee-137">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="d14ee-138">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="d14ee-138">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="d14ee-139">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="d14ee-139">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="d14ee-140">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="d14ee-140">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
