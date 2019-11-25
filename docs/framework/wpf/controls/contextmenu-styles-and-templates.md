---
title: ContextMenu-Stile und -Vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- templates [WPF], ContextMenu
- parts [WPF], ContextMenu
- ContextMenu [WPF], styles and templates
- styles [WPF], ContextMenu
- ControlTemplate [WPF], ContextMenu
- states [WPF], ContextMenu
ms.assetid: 342d1f17-c406-4f94-8f55-867c5f3ea511
ms.openlocfilehash: fa192e20ea84e96c9f85ff84e16c63b7f56c8a98
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283540"
---
# <a name="contextmenu-styles-and-templates"></a><span data-ttu-id="3c796-102">ContextMenu-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="3c796-102">ContextMenu Styles and Templates</span></span>
<span data-ttu-id="3c796-103">In diesem Thema werden die Stile und Vorlagen für das <xref:System.Windows.Controls.ContextMenu>-Steuerelement beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3c796-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ContextMenu> control.</span></span> <span data-ttu-id="3c796-104">Sie können die Standard <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement eine eindeutige Darstellung zu verschaffen.</span><span class="sxs-lookup"><span data-stu-id="3c796-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="3c796-105">Weitere Informationen finden Sie unter [Erstellen einer Vorlage für ein-Steuer](../../../desktop-wpf/themes/how-to-create-apply-template.md)Element.</span><span class="sxs-lookup"><span data-stu-id="3c796-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="contextmenu-parts"></a><span data-ttu-id="3c796-106">ContextMenu-Teile</span><span class="sxs-lookup"><span data-stu-id="3c796-106">ContextMenu Parts</span></span>  
 <span data-ttu-id="3c796-107">Das <xref:System.Windows.Controls.ContextMenu>-Steuerelement verfügt über keine benannten Teile.</span><span class="sxs-lookup"><span data-stu-id="3c796-107">The <xref:System.Windows.Controls.ContextMenu> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="3c796-108">Wenn Sie einen <xref:System.Windows.Controls.ControlTemplate> für eine <xref:System.Windows.Controls.ContextMenu>erstellen, enthält die Vorlage möglicherweise eine <xref:System.Windows.Controls.ItemsPresenter> innerhalb eines <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="3c796-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ContextMenu>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="3c796-109">(Die <xref:System.Windows.Controls.ItemsPresenter> zeigt jedes Element in der <xref:System.Windows.Controls.ContextMenu>an; das <xref:System.Windows.Controls.ScrollViewer> ermöglicht das Scrollen im Steuerelement).</span><span class="sxs-lookup"><span data-stu-id="3c796-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ContextMenu>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="3c796-110">Wenn das <xref:System.Windows.Controls.ItemsPresenter> nicht das direkt untergeordnete Element des <xref:System.Windows.Controls.ScrollViewer>ist, müssen Sie dem <xref:System.Windows.Controls.ItemsPresenter> den Namen `ItemsPresenter`.</span><span class="sxs-lookup"><span data-stu-id="3c796-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="contextmenu-states"></a><span data-ttu-id="3c796-111">ContextMenu-Zustände</span><span class="sxs-lookup"><span data-stu-id="3c796-111">ContextMenu States</span></span>  
 <span data-ttu-id="3c796-112">In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Controls.ContextMenu>-Steuerelement aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="3c796-112">The following table lists the visual states for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
|<span data-ttu-id="3c796-113">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="3c796-113">VisualState Name</span></span>|<span data-ttu-id="3c796-114">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="3c796-114">VisualStateGroup Name</span></span>|<span data-ttu-id="3c796-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3c796-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="3c796-116">Gültig</span><span class="sxs-lookup"><span data-stu-id="3c796-116">Valid</span></span>|<span data-ttu-id="3c796-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3c796-117">ValidationStates</span></span>|<span data-ttu-id="3c796-118">Das-Steuerelement verwendet die <xref:System.Windows.Controls.Validation>-Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false`.</span><span class="sxs-lookup"><span data-stu-id="3c796-118">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="3c796-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="3c796-119">InvalidFocused</span></span>|<span data-ttu-id="3c796-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3c796-120">ValidationStates</span></span>|<span data-ttu-id="3c796-121">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true` hat, dass das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="3c796-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="3c796-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="3c796-122">InvalidUnfocused</span></span>|<span data-ttu-id="3c796-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3c796-123">ValidationStates</span></span>|<span data-ttu-id="3c796-124">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, wenn das Steuerelement keinen Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="3c796-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="contextmenu-controltemplate-example"></a><span data-ttu-id="3c796-125">ContextMenu ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="3c796-125">ContextMenu ControlTemplate Example</span></span>  
 <span data-ttu-id="3c796-126">Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.ControlTemplate> für das <xref:System.Windows.Controls.ContextMenu>-Steuerelement definiert wird.</span><span class="sxs-lookup"><span data-stu-id="3c796-126">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ContextMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#contextmenu)]  
  
 <span data-ttu-id="3c796-127">Der <xref:System.Windows.Controls.ControlTemplate> verwendet die folgenden Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="3c796-127">The <xref:System.Windows.Controls.ControlTemplate> uses the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="3c796-128">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="3c796-128">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c796-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c796-129">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="3c796-130">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="3c796-130">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="3c796-131">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="3c796-131">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="3c796-132">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="3c796-132">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="3c796-133">Erstellen einer Vorlage für ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="3c796-133">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
