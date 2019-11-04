---
title: ToolBar-Stile und -Vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], ToolBar
- styles [WPF], ToolBar
- ControlTemplate [WPF], ToolBar
- parts [WPF], ToolBar
- ToolBar [WPF], styles and templates
- templates [WPF], ToolBar
ms.assetid: bd875f46-4690-46f5-81e0-f11a9822484f
ms.openlocfilehash: b782e62500edd14b40b1267c3b7f92758210a5c0
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458209"
---
# <a name="toolbar-styles-and-templates"></a><span data-ttu-id="2827a-102">ToolBar-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="2827a-102">ToolBar Styles and Templates</span></span>
<span data-ttu-id="2827a-103">In diesem Thema werden die Stile und Vorlagen für das <xref:System.Windows.Controls.ToolBar>-Steuerelement beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2827a-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ToolBar> control.</span></span> <span data-ttu-id="2827a-104">Sie können die Standard <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement eine eindeutige Darstellung zu verschaffen.</span><span class="sxs-lookup"><span data-stu-id="2827a-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="2827a-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="2827a-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="toolbar-parts"></a><span data-ttu-id="2827a-106">Symbolleisten Teile</span><span class="sxs-lookup"><span data-stu-id="2827a-106">ToolBar Parts</span></span>  
 <span data-ttu-id="2827a-107">In der folgenden Tabelle sind die benannten Teile für das <xref:System.Windows.Controls.ToolBar>-Steuerelement aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="2827a-107">The following table lists the named parts for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
|<span data-ttu-id="2827a-108">Segment</span><span class="sxs-lookup"><span data-stu-id="2827a-108">Part</span></span>|<span data-ttu-id="2827a-109">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="2827a-109">Type</span></span>|<span data-ttu-id="2827a-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2827a-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="2827a-111">PART_ToolBarPanel</span><span class="sxs-lookup"><span data-stu-id="2827a-111">PART_ToolBarPanel</span></span>|<xref:System.Windows.Controls.Primitives.ToolBarPanel>|<span data-ttu-id="2827a-112">Das-Objekt, das die Steuerelemente auf dem <xref:System.Windows.Controls.ToolBar>enthält.</span><span class="sxs-lookup"><span data-stu-id="2827a-112">The object that contains the controls on the <xref:System.Windows.Controls.ToolBar>.</span></span>|  
|<span data-ttu-id="2827a-113">PART_ToolBarOverflowPanel</span><span class="sxs-lookup"><span data-stu-id="2827a-113">PART_ToolBarOverflowPanel</span></span>|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|<span data-ttu-id="2827a-114">Das-Objekt, das die Steuerelemente enthält, die sich im Überlauf Bereich der <xref:System.Windows.Controls.ToolBar>befinden.</span><span class="sxs-lookup"><span data-stu-id="2827a-114">The object that contains the controls that are in the overflow area of the <xref:System.Windows.Controls.ToolBar>.</span></span>|  
  
 <span data-ttu-id="2827a-115">Wenn Sie einen <xref:System.Windows.Controls.ControlTemplate> für eine <xref:System.Windows.Controls.ToolBar>erstellen, enthält die Vorlage möglicherweise eine <xref:System.Windows.Controls.ItemsPresenter> innerhalb eines <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="2827a-115">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ToolBar>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="2827a-116">(Die <xref:System.Windows.Controls.ItemsPresenter> zeigt jedes Element in der <xref:System.Windows.Controls.ToolBar>an; das <xref:System.Windows.Controls.ScrollViewer> ermöglicht das Scrollen im Steuerelement).</span><span class="sxs-lookup"><span data-stu-id="2827a-116">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ToolBar>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="2827a-117">Wenn das <xref:System.Windows.Controls.ItemsPresenter> nicht das direkt untergeordnete Element des <xref:System.Windows.Controls.ScrollViewer>ist, müssen Sie dem <xref:System.Windows.Controls.ItemsPresenter> den Namen `ItemsPresenter`.</span><span class="sxs-lookup"><span data-stu-id="2827a-117">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="toolbar-states"></a><span data-ttu-id="2827a-118">Symbolleisten Zustände</span><span class="sxs-lookup"><span data-stu-id="2827a-118">ToolBar States</span></span>  
 <span data-ttu-id="2827a-119">In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Controls.ToolBar>-Steuerelement aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="2827a-119">The following table lists the visual states for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
|<span data-ttu-id="2827a-120">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="2827a-120">VisualState Name</span></span>|<span data-ttu-id="2827a-121">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="2827a-121">VisualStateGroup Name</span></span>|<span data-ttu-id="2827a-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2827a-122">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="2827a-123">Gültig</span><span class="sxs-lookup"><span data-stu-id="2827a-123">Valid</span></span>|<span data-ttu-id="2827a-124">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="2827a-124">ValidationStates</span></span>|<span data-ttu-id="2827a-125">Das-Steuerelement verwendet die <xref:System.Windows.Controls.Validation>-Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false`.</span><span class="sxs-lookup"><span data-stu-id="2827a-125">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="2827a-126">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="2827a-126">InvalidFocused</span></span>|<span data-ttu-id="2827a-127">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="2827a-127">ValidationStates</span></span>|<span data-ttu-id="2827a-128">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true` hat, dass das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="2827a-128">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="2827a-129">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="2827a-129">InvalidUnfocused</span></span>|<span data-ttu-id="2827a-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="2827a-130">ValidationStates</span></span>|<span data-ttu-id="2827a-131">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, wenn das Steuerelement keinen Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="2827a-131">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="toolbar-controltemplate-example"></a><span data-ttu-id="2827a-132">Symbolleisten-ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="2827a-132">ToolBar ControlTemplate Example</span></span>  
 <span data-ttu-id="2827a-133">Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.ControlTemplate> für das <xref:System.Windows.Controls.ToolBar>-Steuerelement definiert wird.</span><span class="sxs-lookup"><span data-stu-id="2827a-133">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToolBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/toolbar.xaml#toolbar)]  
  
 <span data-ttu-id="2827a-134">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="2827a-134">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="2827a-135">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="2827a-135">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2827a-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2827a-136">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="2827a-137">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="2827a-137">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="2827a-138">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="2827a-138">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="2827a-139">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="2827a-139">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="2827a-140">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="2827a-140">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
