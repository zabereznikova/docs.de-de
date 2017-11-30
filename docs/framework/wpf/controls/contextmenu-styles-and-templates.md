---
title: ContextMenu-Stile und -Vorlagen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- templates [WPF], ContextMenu
- parts [WPF], ContextMenu
- ContextMenu [WPF], styles and templates
- styles [WPF], ContextMenu
- ControlTemplate [WPF], ContextMenu
- states [WPF], ContextMenu
ms.assetid: 342d1f17-c406-4f94-8f55-867c5f3ea511
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a51860b21c21f8ce21510b04e817ec75d0e3b4fc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="contextmenu-styles-and-templates"></a><span data-ttu-id="a2bb9-102">ContextMenu-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="a2bb9-102">ContextMenu Styles and Templates</span></span>
<span data-ttu-id="a2bb9-103">In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.ContextMenu> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="a2bb9-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ContextMenu> control.</span></span> <span data-ttu-id="a2bb9-104">Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement ein einzigartiges aussehen zu verleihen.</span><span class="sxs-lookup"><span data-stu-id="a2bb9-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="a2bb9-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="a2bb9-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="contextmenu-parts"></a><span data-ttu-id="a2bb9-106">ContextMenu-Teile</span><span class="sxs-lookup"><span data-stu-id="a2bb9-106">ContextMenu Parts</span></span>  
 <span data-ttu-id="a2bb9-107">Die <xref:System.Windows.Controls.ContextMenu> Steuerelement enthält keine benannten Teile.</span><span class="sxs-lookup"><span data-stu-id="a2bb9-107">The <xref:System.Windows.Controls.ContextMenu> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="a2bb9-108">Beim Erstellen einer <xref:System.Windows.Controls.ControlTemplate> für eine <xref:System.Windows.Controls.ContextMenu>, Ihrer Vorlage enthalten möglicherweise eine <xref:System.Windows.Controls.ItemsPresenter> innerhalb einer <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="a2bb9-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ContextMenu>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="a2bb9-109">(Die <xref:System.Windows.Controls.ItemsPresenter> wird jedes Element in der <xref:System.Windows.Controls.ContextMenu>; das <xref:System.Windows.Controls.ScrollViewer> Bildlauf im Steuerelement aktiviert).</span><span class="sxs-lookup"><span data-stu-id="a2bb9-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ContextMenu>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="a2bb9-110">Wenn die <xref:System.Windows.Controls.ItemsPresenter> ist kein direkte untergeordnetes Element von der <xref:System.Windows.Controls.ScrollViewer>, geben Sie die <xref:System.Windows.Controls.ItemsPresenter> den Namen `ItemsPresenter`.</span><span class="sxs-lookup"><span data-stu-id="a2bb9-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="contextmenu-states"></a><span data-ttu-id="a2bb9-111">ContextMenu-Zustände</span><span class="sxs-lookup"><span data-stu-id="a2bb9-111">ContextMenu States</span></span>  
 <span data-ttu-id="a2bb9-112">Die folgende Tabelle enthält die visueller Zustände für die <xref:System.Windows.Controls.ContextMenu> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="a2bb9-112">The following table lists the visual states for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
|<span data-ttu-id="a2bb9-113">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="a2bb9-113">VisualState Name</span></span>|<span data-ttu-id="a2bb9-114">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="a2bb9-114">VisualStateGroup Name</span></span>|<span data-ttu-id="a2bb9-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a2bb9-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="a2bb9-116">Gültig</span><span class="sxs-lookup"><span data-stu-id="a2bb9-116">Valid</span></span>|<span data-ttu-id="a2bb9-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a2bb9-117">ValidationStates</span></span>|<span data-ttu-id="a2bb9-118">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="a2bb9-118">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="a2bb9-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="a2bb9-119">InvalidFocused</span></span>|<span data-ttu-id="a2bb9-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a2bb9-120">ValidationStates</span></span>|<span data-ttu-id="a2bb9-121">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` weist das Steuerelement den Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="a2bb9-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="a2bb9-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="a2bb9-122">InvalidUnfocused</span></span>|<span data-ttu-id="a2bb9-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a2bb9-123">ValidationStates</span></span>|<span data-ttu-id="a2bb9-124">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement verfügt nicht über den Fokus.</span><span class="sxs-lookup"><span data-stu-id="a2bb9-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="contextmenu-controltemplate-example"></a><span data-ttu-id="a2bb9-125">ContextMenu-ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="a2bb9-125">ContextMenu ControlTemplate Example</span></span>  
 <span data-ttu-id="a2bb9-126">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.ContextMenu> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="a2bb9-126">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ContextMenu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#contextmenu)]  
  
 <span data-ttu-id="a2bb9-127">Die <xref:System.Windows.Controls.ControlTemplate> verwendet die folgenden Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="a2bb9-127">The <xref:System.Windows.Controls.ControlTemplate> uses the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="a2bb9-128">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="a2bb9-128">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2bb9-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2bb9-129">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="a2bb9-130">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="a2bb9-130">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="a2bb9-131">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="a2bb9-131">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="a2bb9-132">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="a2bb9-132">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="a2bb9-133">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="a2bb9-133">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
