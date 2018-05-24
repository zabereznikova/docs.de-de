---
title: ProgressBar-Formate und -Vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], ProgressBar
- ProgressBar [WPF], styles and templates
- styles [WPF], ProgressBar
- ControlTemplate [WPF], ProgressBar
- templates [WPF], ProgressBar
- states [WPF], ProgressBar
ms.assetid: 935aa600-16e6-4947-a905-37a189a583dd
ms.openlocfilehash: 89aea3e80fe17ece8a17f62f62290d34ddd55c60
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2018
---
# <a name="progressbar-styles-and-templates"></a><span data-ttu-id="41825-102">ProgressBar-Formate und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="41825-102">ProgressBar Styles and Templates</span></span>
<span data-ttu-id="41825-103">In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.ProgressBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="41825-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ProgressBar> control.</span></span> <span data-ttu-id="41825-104">Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement ein einzigartiges aussehen zu verleihen.</span><span class="sxs-lookup"><span data-stu-id="41825-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="41825-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="41825-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="progressbar-parts"></a><span data-ttu-id="41825-106">ProgressBar-Teile</span><span class="sxs-lookup"><span data-stu-id="41825-106">ProgressBar Parts</span></span>  
 <span data-ttu-id="41825-107">Die folgende Tabelle enthält die benannten Teile für die <xref:System.Windows.Controls.ProgressBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="41825-107">The following table lists the named parts for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="41825-108">Segment</span><span class="sxs-lookup"><span data-stu-id="41825-108">Part</span></span>|<span data-ttu-id="41825-109">Typ</span><span class="sxs-lookup"><span data-stu-id="41825-109">Type</span></span>|<span data-ttu-id="41825-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="41825-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="41825-111">PART_Indicator</span><span class="sxs-lookup"><span data-stu-id="41825-111">PART_Indicator</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="41825-112">Das Objekt, das Fortschritt angibt.</span><span class="sxs-lookup"><span data-stu-id="41825-112">The object that indicates progress.</span></span>|  
|<span data-ttu-id="41825-113">PART_Track</span><span class="sxs-lookup"><span data-stu-id="41825-113">PART_Track</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="41825-114">Das Objekt, das den Pfad der Statusanzeige definiert.</span><span class="sxs-lookup"><span data-stu-id="41825-114">The object that defines the path of the progress indicator.</span></span>|  
|<span data-ttu-id="41825-115">PART_GlowRect</span><span class="sxs-lookup"><span data-stu-id="41825-115">PART_GlowRect</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="41825-116">Ein Objekt, die Darstellung der Statusanzeige verbessert.</span><span class="sxs-lookup"><span data-stu-id="41825-116">An object that embellishes the progress bar.</span></span>|  
  
## <a name="progressbar-states"></a><span data-ttu-id="41825-117">ProgressBar-Zustände</span><span class="sxs-lookup"><span data-stu-id="41825-117">ProgressBar States</span></span>  
 <span data-ttu-id="41825-118">Die folgende Tabelle enthält die visueller Zustände für die <xref:System.Windows.Controls.ProgressBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="41825-118">The following table lists the visual states for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="41825-119">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="41825-119">VisualState Name</span></span>|<span data-ttu-id="41825-120">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="41825-120">VisualStateGroup Name</span></span>|<span data-ttu-id="41825-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="41825-121">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="41825-122">Bestimmte</span><span class="sxs-lookup"><span data-stu-id="41825-122">Determinate</span></span>|<span data-ttu-id="41825-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="41825-123">CommonStates</span></span>|<span data-ttu-id="41825-124"><xref:System.Windows.Controls.ProgressBar> meldet den Fortschritt basierend auf den <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="41825-124"><xref:System.Windows.Controls.ProgressBar> reports progress based on the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> property.</span></span>|  
|<span data-ttu-id="41825-125">Unbestimmt</span><span class="sxs-lookup"><span data-stu-id="41825-125">Indeterminate</span></span>|<span data-ttu-id="41825-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="41825-126">CommonStates</span></span>|<span data-ttu-id="41825-127"><xref:System.Windows.Controls.ProgressBar> generische Fortschrittsberichte mit einem sich wiederholenden Muster.</span><span class="sxs-lookup"><span data-stu-id="41825-127"><xref:System.Windows.Controls.ProgressBar> reports generic progress with a repeating pattern.</span></span>|  
|<span data-ttu-id="41825-128">Gültig</span><span class="sxs-lookup"><span data-stu-id="41825-128">Valid</span></span>|<span data-ttu-id="41825-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="41825-129">ValidationStates</span></span>|<span data-ttu-id="41825-130">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="41825-130">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="41825-131">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="41825-131">InvalidFocused</span></span>|<span data-ttu-id="41825-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="41825-132">ValidationStates</span></span>|<span data-ttu-id="41825-133">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` weist das Steuerelement den Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="41825-133">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="41825-134">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="41825-134">InvalidUnfocused</span></span>|<span data-ttu-id="41825-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="41825-135">ValidationStates</span></span>|<span data-ttu-id="41825-136">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement verfügt nicht über den Fokus.</span><span class="sxs-lookup"><span data-stu-id="41825-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="progressbar-controltemplate-example"></a><span data-ttu-id="41825-137">Beispiel für "ProgressBar" ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="41825-137">ProgressBar ControlTemplate Example</span></span>  
 <span data-ttu-id="41825-138">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.ProgressBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="41825-138">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ProgressBar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/progressbar.xaml#progressbar)]  
  
 <span data-ttu-id="41825-139">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="41825-139">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="41825-140">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="41825-140">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41825-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41825-141">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="41825-142">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="41825-142">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="41825-143">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="41825-143">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="41825-144">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="41825-144">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="41825-145">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="41825-145">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
