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
ms.openlocfilehash: 1cbb8d54a544b70b4a484c06c6bb2e9ca25029da
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790740"
---
# <a name="toolbar-styles-and-templates"></a><span data-ttu-id="44e52-102">ToolBar-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="44e52-102">ToolBar Styles and Templates</span></span>
<span data-ttu-id="44e52-103">In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.ToolBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="44e52-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ToolBar> control.</span></span> <span data-ttu-id="44e52-104">Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement eine unverwechselbare Darstellung verleihen.</span><span class="sxs-lookup"><span data-stu-id="44e52-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="44e52-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="44e52-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="toolbar-parts"></a><span data-ttu-id="44e52-106">ToolBar-Teile</span><span class="sxs-lookup"><span data-stu-id="44e52-106">ToolBar Parts</span></span>  
 <span data-ttu-id="44e52-107">Die folgende Tabelle enthält die benannten Teile für den <xref:System.Windows.Controls.ToolBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="44e52-107">The following table lists the named parts for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
|<span data-ttu-id="44e52-108">Segment</span><span class="sxs-lookup"><span data-stu-id="44e52-108">Part</span></span>|<span data-ttu-id="44e52-109">Typ</span><span class="sxs-lookup"><span data-stu-id="44e52-109">Type</span></span>|<span data-ttu-id="44e52-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="44e52-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="44e52-111">PART_ToolBarPanel</span><span class="sxs-lookup"><span data-stu-id="44e52-111">PART_ToolBarPanel</span></span>|<xref:System.Windows.Controls.Primitives.ToolBarPanel>|<span data-ttu-id="44e52-112">Das Objekt, das die Steuerelemente enthält, auf die <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="44e52-112">The object that contains the controls on the <xref:System.Windows.Controls.ToolBar>.</span></span>|  
|<span data-ttu-id="44e52-113">PART_ToolBarOverflowPanel</span><span class="sxs-lookup"><span data-stu-id="44e52-113">PART_ToolBarOverflowPanel</span></span>|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|<span data-ttu-id="44e52-114">Das Objekt, das die Steuerelemente enthält, die im Überlaufbereich des sind die <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="44e52-114">The object that contains the controls that are in the overflow area of the <xref:System.Windows.Controls.ToolBar>.</span></span>|  
  
 <span data-ttu-id="44e52-115">Bei der Erstellung einer <xref:System.Windows.Controls.ControlTemplate> für eine <xref:System.Windows.Controls.ToolBar>, Ihrer Vorlage enthalten möglicherweise ein <xref:System.Windows.Controls.ItemsPresenter> innerhalb einer <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="44e52-115">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ToolBar>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="44e52-116">(Die <xref:System.Windows.Controls.ItemsPresenter> stellt jedes Element in der <xref:System.Windows.Controls.ToolBar>; die <xref:System.Windows.Controls.ScrollViewer> ermöglicht das Scrollen innerhalb des Steuerelements).</span><span class="sxs-lookup"><span data-stu-id="44e52-116">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ToolBar>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="44e52-117">Wenn die <xref:System.Windows.Controls.ItemsPresenter> ist kein direkte untergeordnetes Element von der <xref:System.Windows.Controls.ScrollViewer>, geben Sie die <xref:System.Windows.Controls.ItemsPresenter> den Namen, `ItemsPresenter`.</span><span class="sxs-lookup"><span data-stu-id="44e52-117">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="toolbar-states"></a><span data-ttu-id="44e52-118">ToolBar-Zustände</span><span class="sxs-lookup"><span data-stu-id="44e52-118">ToolBar States</span></span>  
 <span data-ttu-id="44e52-119">Die folgende Tabelle enthält die visuellen Zustände für die <xref:System.Windows.Controls.ToolBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="44e52-119">The following table lists the visual states for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
|<span data-ttu-id="44e52-120">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="44e52-120">VisualState Name</span></span>|<span data-ttu-id="44e52-121">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="44e52-121">VisualStateGroup Name</span></span>|<span data-ttu-id="44e52-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="44e52-122">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="44e52-123">Gültig</span><span class="sxs-lookup"><span data-stu-id="44e52-123">Valid</span></span>|<span data-ttu-id="44e52-124">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="44e52-124">ValidationStates</span></span>|<span data-ttu-id="44e52-125">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="44e52-125">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="44e52-126">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="44e52-126">InvalidFocused</span></span>|<span data-ttu-id="44e52-127">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="44e52-127">ValidationStates</span></span>|<span data-ttu-id="44e52-128">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="44e52-128">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="44e52-129">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="44e52-129">InvalidUnfocused</span></span>|<span data-ttu-id="44e52-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="44e52-130">ValidationStates</span></span>|<span data-ttu-id="44e52-131">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement keinen Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="44e52-131">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="toolbar-controltemplate-example"></a><span data-ttu-id="44e52-132">Symbolleiste-ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="44e52-132">ToolBar ControlTemplate Example</span></span>  
 <span data-ttu-id="44e52-133">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.ToolBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="44e52-133">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToolBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/toolbar.xaml#toolbar)]  
  
 <span data-ttu-id="44e52-134">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="44e52-134">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="44e52-135">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="44e52-135">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44e52-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="44e52-136">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="44e52-137">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="44e52-137">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="44e52-138">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="44e52-138">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="44e52-139">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="44e52-139">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="44e52-140">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="44e52-140">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
