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
ms.openlocfilehash: 4112306dab648d022e171401f5b9b362f2c91fdc
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460765"
---
# <a name="contextmenu-styles-and-templates"></a><span data-ttu-id="be45a-102">ContextMenu-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="be45a-102">ContextMenu Styles and Templates</span></span>
<span data-ttu-id="be45a-103">In diesem Thema werden die Stile und Vorlagen für das <xref:System.Windows.Controls.ContextMenu>-Steuerelement beschrieben.</span><span class="sxs-lookup"><span data-stu-id="be45a-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ContextMenu> control.</span></span> <span data-ttu-id="be45a-104">Sie können die Standard <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement eine eindeutige Darstellung zu verschaffen.</span><span class="sxs-lookup"><span data-stu-id="be45a-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="be45a-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="be45a-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="contextmenu-parts"></a><span data-ttu-id="be45a-106">ContextMenu-Teile</span><span class="sxs-lookup"><span data-stu-id="be45a-106">ContextMenu Parts</span></span>  
 <span data-ttu-id="be45a-107">Das <xref:System.Windows.Controls.ContextMenu>-Steuerelement verfügt über keine benannten Teile.</span><span class="sxs-lookup"><span data-stu-id="be45a-107">The <xref:System.Windows.Controls.ContextMenu> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="be45a-108">Wenn Sie einen <xref:System.Windows.Controls.ControlTemplate> für eine <xref:System.Windows.Controls.ContextMenu>erstellen, enthält die Vorlage möglicherweise eine <xref:System.Windows.Controls.ItemsPresenter> innerhalb eines <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="be45a-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ContextMenu>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="be45a-109">(Die <xref:System.Windows.Controls.ItemsPresenter> zeigt jedes Element in der <xref:System.Windows.Controls.ContextMenu>an; das <xref:System.Windows.Controls.ScrollViewer> ermöglicht das Scrollen im Steuerelement).</span><span class="sxs-lookup"><span data-stu-id="be45a-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ContextMenu>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="be45a-110">Wenn das <xref:System.Windows.Controls.ItemsPresenter> nicht das direkt untergeordnete Element des <xref:System.Windows.Controls.ScrollViewer>ist, müssen Sie dem <xref:System.Windows.Controls.ItemsPresenter> den Namen `ItemsPresenter`.</span><span class="sxs-lookup"><span data-stu-id="be45a-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="contextmenu-states"></a><span data-ttu-id="be45a-111">ContextMenu-Zustände</span><span class="sxs-lookup"><span data-stu-id="be45a-111">ContextMenu States</span></span>  
 <span data-ttu-id="be45a-112">In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Controls.ContextMenu>-Steuerelement aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="be45a-112">The following table lists the visual states for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
|<span data-ttu-id="be45a-113">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="be45a-113">VisualState Name</span></span>|<span data-ttu-id="be45a-114">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="be45a-114">VisualStateGroup Name</span></span>|<span data-ttu-id="be45a-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="be45a-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="be45a-116">Gültig</span><span class="sxs-lookup"><span data-stu-id="be45a-116">Valid</span></span>|<span data-ttu-id="be45a-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="be45a-117">ValidationStates</span></span>|<span data-ttu-id="be45a-118">Das-Steuerelement verwendet die <xref:System.Windows.Controls.Validation>-Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false`.</span><span class="sxs-lookup"><span data-stu-id="be45a-118">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="be45a-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="be45a-119">InvalidFocused</span></span>|<span data-ttu-id="be45a-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="be45a-120">ValidationStates</span></span>|<span data-ttu-id="be45a-121">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true` hat, dass das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="be45a-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="be45a-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="be45a-122">InvalidUnfocused</span></span>|<span data-ttu-id="be45a-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="be45a-123">ValidationStates</span></span>|<span data-ttu-id="be45a-124">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, wenn das Steuerelement keinen Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="be45a-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="contextmenu-controltemplate-example"></a><span data-ttu-id="be45a-125">ContextMenu ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="be45a-125">ContextMenu ControlTemplate Example</span></span>  
 <span data-ttu-id="be45a-126">Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.ControlTemplate> für das <xref:System.Windows.Controls.ContextMenu>-Steuerelement definiert wird.</span><span class="sxs-lookup"><span data-stu-id="be45a-126">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ContextMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#contextmenu)]  
  
 <span data-ttu-id="be45a-127">Der <xref:System.Windows.Controls.ControlTemplate> verwendet die folgenden Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="be45a-127">The <xref:System.Windows.Controls.ControlTemplate> uses the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="be45a-128">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="be45a-128">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be45a-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be45a-129">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="be45a-130">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="be45a-130">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="be45a-131">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="be45a-131">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="be45a-132">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="be45a-132">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="be45a-133">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="be45a-133">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
