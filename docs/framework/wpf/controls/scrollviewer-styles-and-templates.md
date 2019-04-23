---
title: ScrollViewer-Stile und -Vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], ScrollViewer
- states [WPF], ScrollViewer
- styles [WPF], ScrollViewer
- templates [WPF], ScrollViewer
- ControlTemplate [WPF], ScrollViewer
- ScrollViewer [WPF], styles and templates
ms.assetid: dffdd822-ae69-4946-abaf-710860cd65b2
ms.openlocfilehash: 9c0edfd7ab4772eb9a1f5ecdd3db611fa36bf8d3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59226832"
---
# <a name="scrollviewer-styles-and-templates"></a><span data-ttu-id="ec13f-102">ScrollViewer-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="ec13f-102">ScrollViewer Styles and Templates</span></span>
<span data-ttu-id="ec13f-103">In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.ScrollViewer> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ec13f-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span> <span data-ttu-id="ec13f-104">Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement eine unverwechselbare Darstellung verleihen.</span><span class="sxs-lookup"><span data-stu-id="ec13f-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="ec13f-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="ec13f-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="scrollviewer-parts"></a><span data-ttu-id="ec13f-106">Teile der ScrollViewer-Element</span><span class="sxs-lookup"><span data-stu-id="ec13f-106">ScrollViewer Parts</span></span>  
 <span data-ttu-id="ec13f-107">Die folgende Tabelle enthält die benannten Teile für den <xref:System.Windows.Controls.ScrollViewer> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ec13f-107">The following table lists the named parts for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="ec13f-108">Segment</span><span class="sxs-lookup"><span data-stu-id="ec13f-108">Part</span></span>|<span data-ttu-id="ec13f-109">Typ</span><span class="sxs-lookup"><span data-stu-id="ec13f-109">Type</span></span>|<span data-ttu-id="ec13f-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ec13f-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="ec13f-111">PART_ScrollContentPresenter</span><span class="sxs-lookup"><span data-stu-id="ec13f-111">PART_ScrollContentPresenter</span></span>|<xref:System.Windows.Controls.ScrollContentPresenter>|<span data-ttu-id="ec13f-112">Der Platzhalter für Inhalte in der <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="ec13f-112">The placeholder for content in the <xref:System.Windows.Controls.ScrollViewer>.</span></span>|  
|<span data-ttu-id="ec13f-113">PART_HorizontalScrollBar</span><span class="sxs-lookup"><span data-stu-id="ec13f-113">PART_HorizontalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="ec13f-114">Die <xref:System.Windows.Controls.Primitives.ScrollBar> verwendet, um den Inhalt einen horizontalen Bildlauf durchführen.</span><span class="sxs-lookup"><span data-stu-id="ec13f-114">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content horizontally.</span></span>|  
|<span data-ttu-id="ec13f-115">PART_VerticalScrollBar</span><span class="sxs-lookup"><span data-stu-id="ec13f-115">PART_VerticalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="ec13f-116">Die <xref:System.Windows.Controls.Primitives.ScrollBar> verwendet, um den Inhalt vertikal scrollen.</span><span class="sxs-lookup"><span data-stu-id="ec13f-116">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content vertically.</span></span>|  
  
## <a name="scrollviewer-states"></a><span data-ttu-id="ec13f-117">ScrollViewer-Element-Zustände</span><span class="sxs-lookup"><span data-stu-id="ec13f-117">ScrollViewer States</span></span>  
 <span data-ttu-id="ec13f-118">Die folgende Tabelle enthält die visuellen Zustände für die <xref:System.Windows.Controls.ScrollViewer> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ec13f-118">The following table lists the visual states for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="ec13f-119">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="ec13f-119">VisualState Name</span></span>|<span data-ttu-id="ec13f-120">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="ec13f-120">VisualStateGroup Name</span></span>|<span data-ttu-id="ec13f-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ec13f-121">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="ec13f-122">Gültig</span><span class="sxs-lookup"><span data-stu-id="ec13f-122">Valid</span></span>|<span data-ttu-id="ec13f-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ec13f-123">ValidationStates</span></span>|<span data-ttu-id="ec13f-124">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="ec13f-124">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="ec13f-125">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="ec13f-125">InvalidFocused</span></span>|<span data-ttu-id="ec13f-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ec13f-126">ValidationStates</span></span>|<span data-ttu-id="ec13f-127">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="ec13f-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="ec13f-128">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="ec13f-128">InvalidUnfocused</span></span>|<span data-ttu-id="ec13f-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ec13f-129">ValidationStates</span></span>|<span data-ttu-id="ec13f-130">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement keinen Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="ec13f-130">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="scrollviewer-controltemplate-example"></a><span data-ttu-id="ec13f-131">ScrollViewer-ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="ec13f-131">ScrollViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="ec13f-132">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.ScrollViewer> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ec13f-132">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollviewer.xaml#scrollviewer)]  
  
 <span data-ttu-id="ec13f-133">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="ec13f-133">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="ec13f-134">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="ec13f-134">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec13f-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ec13f-135">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="ec13f-136">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="ec13f-136">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="ec13f-137">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="ec13f-137">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="ec13f-138">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="ec13f-138">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="ec13f-139">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="ec13f-139">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
