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
ms.openlocfilehash: 6650d5a7be8ebe8fc2dcd7af7c854da669de87f3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59123044"
---
# <a name="contextmenu-styles-and-templates"></a><span data-ttu-id="d5cae-102">ContextMenu-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="d5cae-102">ContextMenu Styles and Templates</span></span>
<span data-ttu-id="d5cae-103">In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.ContextMenu> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="d5cae-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ContextMenu> control.</span></span> <span data-ttu-id="d5cae-104">Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement eine unverwechselbare Darstellung verleihen.</span><span class="sxs-lookup"><span data-stu-id="d5cae-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="d5cae-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="d5cae-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="contextmenu-parts"></a><span data-ttu-id="d5cae-106">ContextMenu-Teile</span><span class="sxs-lookup"><span data-stu-id="d5cae-106">ContextMenu Parts</span></span>  
 <span data-ttu-id="d5cae-107">Die <xref:System.Windows.Controls.ContextMenu> Steuerelement enthält keine benannten Teile.</span><span class="sxs-lookup"><span data-stu-id="d5cae-107">The <xref:System.Windows.Controls.ContextMenu> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="d5cae-108">Bei der Erstellung einer <xref:System.Windows.Controls.ControlTemplate> für eine <xref:System.Windows.Controls.ContextMenu>, Ihrer Vorlage enthalten möglicherweise ein <xref:System.Windows.Controls.ItemsPresenter> innerhalb einer <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="d5cae-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ContextMenu>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="d5cae-109">(Die <xref:System.Windows.Controls.ItemsPresenter> stellt jedes Element in der <xref:System.Windows.Controls.ContextMenu>; die <xref:System.Windows.Controls.ScrollViewer> ermöglicht das Scrollen innerhalb des Steuerelements).</span><span class="sxs-lookup"><span data-stu-id="d5cae-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ContextMenu>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="d5cae-110">Wenn die <xref:System.Windows.Controls.ItemsPresenter> ist kein direkte untergeordnetes Element von der <xref:System.Windows.Controls.ScrollViewer>, geben Sie die <xref:System.Windows.Controls.ItemsPresenter> den Namen, `ItemsPresenter`.</span><span class="sxs-lookup"><span data-stu-id="d5cae-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="contextmenu-states"></a><span data-ttu-id="d5cae-111">ContextMenu-Zustände</span><span class="sxs-lookup"><span data-stu-id="d5cae-111">ContextMenu States</span></span>  
 <span data-ttu-id="d5cae-112">Die folgende Tabelle enthält die visuellen Zustände für die <xref:System.Windows.Controls.ContextMenu> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="d5cae-112">The following table lists the visual states for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
|<span data-ttu-id="d5cae-113">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="d5cae-113">VisualState Name</span></span>|<span data-ttu-id="d5cae-114">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="d5cae-114">VisualStateGroup Name</span></span>|<span data-ttu-id="d5cae-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d5cae-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="d5cae-116">Gültig</span><span class="sxs-lookup"><span data-stu-id="d5cae-116">Valid</span></span>|<span data-ttu-id="d5cae-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d5cae-117">ValidationStates</span></span>|<span data-ttu-id="d5cae-118">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="d5cae-118">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="d5cae-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="d5cae-119">InvalidFocused</span></span>|<span data-ttu-id="d5cae-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d5cae-120">ValidationStates</span></span>|<span data-ttu-id="d5cae-121">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="d5cae-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="d5cae-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="d5cae-122">InvalidUnfocused</span></span>|<span data-ttu-id="d5cae-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d5cae-123">ValidationStates</span></span>|<span data-ttu-id="d5cae-124">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement keinen Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="d5cae-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="contextmenu-controltemplate-example"></a><span data-ttu-id="d5cae-125">ContextMenu-ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="d5cae-125">ContextMenu ControlTemplate Example</span></span>  
 <span data-ttu-id="d5cae-126">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.ContextMenu> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="d5cae-126">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ContextMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#contextmenu)]  
  
 <span data-ttu-id="d5cae-127">Die <xref:System.Windows.Controls.ControlTemplate> werden die folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="d5cae-127">The <xref:System.Windows.Controls.ControlTemplate> uses the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="d5cae-128">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="d5cae-128">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5cae-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d5cae-129">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="d5cae-130">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="d5cae-130">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="d5cae-131">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="d5cae-131">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="d5cae-132">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="d5cae-132">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="d5cae-133">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="d5cae-133">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
