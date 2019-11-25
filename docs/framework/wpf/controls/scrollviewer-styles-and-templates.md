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
ms.openlocfilehash: b54dcacf55a750d7c1253db20147d18de47d027e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283398"
---
# <a name="scrollviewer-styles-and-templates"></a><span data-ttu-id="9dc4d-102">ScrollViewer-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="9dc4d-102">ScrollViewer Styles and Templates</span></span>
<span data-ttu-id="9dc4d-103">In diesem Thema werden die Stile und Vorlagen für das <xref:System.Windows.Controls.ScrollViewer>-Steuerelement beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9dc4d-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span> <span data-ttu-id="9dc4d-104">Sie können die Standard <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement eine eindeutige Darstellung zu verschaffen.</span><span class="sxs-lookup"><span data-stu-id="9dc4d-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="9dc4d-105">Weitere Informationen finden Sie unter [Erstellen einer Vorlage für ein-Steuer](../../../desktop-wpf/themes/how-to-create-apply-template.md)Element.</span><span class="sxs-lookup"><span data-stu-id="9dc4d-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="scrollviewer-parts"></a><span data-ttu-id="9dc4d-106">ScrollViewer-Teile</span><span class="sxs-lookup"><span data-stu-id="9dc4d-106">ScrollViewer Parts</span></span>  
 <span data-ttu-id="9dc4d-107">In der folgenden Tabelle sind die benannten Teile für das <xref:System.Windows.Controls.ScrollViewer>-Steuerelement aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="9dc4d-107">The following table lists the named parts for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="9dc4d-108">Segment</span><span class="sxs-lookup"><span data-stu-id="9dc4d-108">Part</span></span>|<span data-ttu-id="9dc4d-109">Typ</span><span class="sxs-lookup"><span data-stu-id="9dc4d-109">Type</span></span>|<span data-ttu-id="9dc4d-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9dc4d-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="9dc4d-111">PART_ScrollContentPresenter</span><span class="sxs-lookup"><span data-stu-id="9dc4d-111">PART_ScrollContentPresenter</span></span>|<xref:System.Windows.Controls.ScrollContentPresenter>|<span data-ttu-id="9dc4d-112">Der Platzhalter für den Inhalt in der <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="9dc4d-112">The placeholder for content in the <xref:System.Windows.Controls.ScrollViewer>.</span></span>|  
|<span data-ttu-id="9dc4d-113">PART_HorizontalScrollBar</span><span class="sxs-lookup"><span data-stu-id="9dc4d-113">PART_HorizontalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="9dc4d-114">Der <xref:System.Windows.Controls.Primitives.ScrollBar>, der zum horizontalen Scrollen des Inhalts verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9dc4d-114">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content horizontally.</span></span>|  
|<span data-ttu-id="9dc4d-115">PART_VerticalScrollBar</span><span class="sxs-lookup"><span data-stu-id="9dc4d-115">PART_VerticalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="9dc4d-116">Der <xref:System.Windows.Controls.Primitives.ScrollBar>, der verwendet wird, um den Inhalt vertikal zu scrollen.</span><span class="sxs-lookup"><span data-stu-id="9dc4d-116">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content vertically.</span></span>|  
  
## <a name="scrollviewer-states"></a><span data-ttu-id="9dc4d-117">ScrollViewer-Zustände</span><span class="sxs-lookup"><span data-stu-id="9dc4d-117">ScrollViewer States</span></span>  
 <span data-ttu-id="9dc4d-118">In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Controls.ScrollViewer>-Steuerelement aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="9dc4d-118">The following table lists the visual states for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="9dc4d-119">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="9dc4d-119">VisualState Name</span></span>|<span data-ttu-id="9dc4d-120">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="9dc4d-120">VisualStateGroup Name</span></span>|<span data-ttu-id="9dc4d-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9dc4d-121">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="9dc4d-122">Gültig</span><span class="sxs-lookup"><span data-stu-id="9dc4d-122">Valid</span></span>|<span data-ttu-id="9dc4d-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9dc4d-123">ValidationStates</span></span>|<span data-ttu-id="9dc4d-124">Das-Steuerelement verwendet die <xref:System.Windows.Controls.Validation>-Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false`.</span><span class="sxs-lookup"><span data-stu-id="9dc4d-124">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="9dc4d-125">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="9dc4d-125">InvalidFocused</span></span>|<span data-ttu-id="9dc4d-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9dc4d-126">ValidationStates</span></span>|<span data-ttu-id="9dc4d-127">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true` hat, dass das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="9dc4d-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="9dc4d-128">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="9dc4d-128">InvalidUnfocused</span></span>|<span data-ttu-id="9dc4d-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9dc4d-129">ValidationStates</span></span>|<span data-ttu-id="9dc4d-130">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, wenn das Steuerelement keinen Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="9dc4d-130">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="scrollviewer-controltemplate-example"></a><span data-ttu-id="9dc4d-131">ScrollViewer-ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="9dc4d-131">ScrollViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="9dc4d-132">Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.ControlTemplate> für das <xref:System.Windows.Controls.ScrollViewer>-Steuerelement definiert wird.</span><span class="sxs-lookup"><span data-stu-id="9dc4d-132">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollviewer.xaml#scrollviewer)]  
  
 <span data-ttu-id="9dc4d-133">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="9dc4d-133">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="9dc4d-134">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="9dc4d-134">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dc4d-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9dc4d-135">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="9dc4d-136">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="9dc4d-136">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="9dc4d-137">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="9dc4d-137">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="9dc4d-138">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="9dc4d-138">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="9dc4d-139">Erstellen einer Vorlage für ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="9dc4d-139">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
