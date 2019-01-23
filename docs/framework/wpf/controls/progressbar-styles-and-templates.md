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
ms.openlocfilehash: 7e410642e6153ed8064b2ddfb38fddd9cce6f4de
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54525378"
---
# <a name="progressbar-styles-and-templates"></a><span data-ttu-id="bb1c9-102">ProgressBar-Formate und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="bb1c9-102">ProgressBar Styles and Templates</span></span>
<span data-ttu-id="bb1c9-103">In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.ProgressBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="bb1c9-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ProgressBar> control.</span></span> <span data-ttu-id="bb1c9-104">Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement eine unverwechselbare Darstellung verleihen.</span><span class="sxs-lookup"><span data-stu-id="bb1c9-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="bb1c9-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="bb1c9-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="progressbar-parts"></a><span data-ttu-id="bb1c9-106">ProgressBar-Teile</span><span class="sxs-lookup"><span data-stu-id="bb1c9-106">ProgressBar Parts</span></span>  
 <span data-ttu-id="bb1c9-107">Die folgende Tabelle enthält die benannten Teile für den <xref:System.Windows.Controls.ProgressBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="bb1c9-107">The following table lists the named parts for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="bb1c9-108">Segment</span><span class="sxs-lookup"><span data-stu-id="bb1c9-108">Part</span></span>|<span data-ttu-id="bb1c9-109">Typ</span><span class="sxs-lookup"><span data-stu-id="bb1c9-109">Type</span></span>|<span data-ttu-id="bb1c9-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bb1c9-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="bb1c9-111">PART_Indicator</span><span class="sxs-lookup"><span data-stu-id="bb1c9-111">PART_Indicator</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="bb1c9-112">Das Objekt, das Status angibt.</span><span class="sxs-lookup"><span data-stu-id="bb1c9-112">The object that indicates progress.</span></span>|  
|<span data-ttu-id="bb1c9-113">PART_Track</span><span class="sxs-lookup"><span data-stu-id="bb1c9-113">PART_Track</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="bb1c9-114">Das Objekt, das den Pfad der Statusanzeige definiert.</span><span class="sxs-lookup"><span data-stu-id="bb1c9-114">The object that defines the path of the progress indicator.</span></span>|  
|<span data-ttu-id="bb1c9-115">PART_GlowRect</span><span class="sxs-lookup"><span data-stu-id="bb1c9-115">PART_GlowRect</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="bb1c9-116">Ein Objekt, das Darstellung der Statusanzeige verbessert.</span><span class="sxs-lookup"><span data-stu-id="bb1c9-116">An object that embellishes the progress bar.</span></span>|  
  
## <a name="progressbar-states"></a><span data-ttu-id="bb1c9-117">ProgressBar-Zustände</span><span class="sxs-lookup"><span data-stu-id="bb1c9-117">ProgressBar States</span></span>  
 <span data-ttu-id="bb1c9-118">Die folgende Tabelle enthält die visuellen Zustände für die <xref:System.Windows.Controls.ProgressBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="bb1c9-118">The following table lists the visual states for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="bb1c9-119">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="bb1c9-119">VisualState Name</span></span>|<span data-ttu-id="bb1c9-120">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="bb1c9-120">VisualStateGroup Name</span></span>|<span data-ttu-id="bb1c9-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bb1c9-121">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="bb1c9-122">Bestimmte</span><span class="sxs-lookup"><span data-stu-id="bb1c9-122">Determinate</span></span>|<span data-ttu-id="bb1c9-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="bb1c9-123">CommonStates</span></span>|<span data-ttu-id="bb1c9-124"><xref:System.Windows.Controls.ProgressBar> meldet den Fortschritt basierend auf den <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="bb1c9-124"><xref:System.Windows.Controls.ProgressBar> reports progress based on the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> property.</span></span>|  
|<span data-ttu-id="bb1c9-125">Unbestimmt</span><span class="sxs-lookup"><span data-stu-id="bb1c9-125">Indeterminate</span></span>|<span data-ttu-id="bb1c9-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="bb1c9-126">CommonStates</span></span>|<span data-ttu-id="bb1c9-127"><xref:System.Windows.Controls.ProgressBar> meldet den generischen Fortschritt mit einer sich wiederholenden.</span><span class="sxs-lookup"><span data-stu-id="bb1c9-127"><xref:System.Windows.Controls.ProgressBar> reports generic progress with a repeating pattern.</span></span>|  
|<span data-ttu-id="bb1c9-128">Gültig</span><span class="sxs-lookup"><span data-stu-id="bb1c9-128">Valid</span></span>|<span data-ttu-id="bb1c9-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="bb1c9-129">ValidationStates</span></span>|<span data-ttu-id="bb1c9-130">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="bb1c9-130">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="bb1c9-131">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="bb1c9-131">InvalidFocused</span></span>|<span data-ttu-id="bb1c9-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="bb1c9-132">ValidationStates</span></span>|<span data-ttu-id="bb1c9-133">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="bb1c9-133">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="bb1c9-134">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="bb1c9-134">InvalidUnfocused</span></span>|<span data-ttu-id="bb1c9-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="bb1c9-135">ValidationStates</span></span>|<span data-ttu-id="bb1c9-136">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement keinen Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="bb1c9-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="progressbar-controltemplate-example"></a><span data-ttu-id="bb1c9-137">ProgressBar-ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="bb1c9-137">ProgressBar ControlTemplate Example</span></span>  
 <span data-ttu-id="bb1c9-138">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.ProgressBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="bb1c9-138">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ProgressBar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/progressbar.xaml#progressbar)]  
  
 <span data-ttu-id="bb1c9-139">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="bb1c9-139">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="bb1c9-140">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="bb1c9-140">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb1c9-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb1c9-141">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="bb1c9-142">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="bb1c9-142">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)
- [<span data-ttu-id="bb1c9-143">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="bb1c9-143">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)
- [<span data-ttu-id="bb1c9-144">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="bb1c9-144">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)
- [<span data-ttu-id="bb1c9-145">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="bb1c9-145">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
