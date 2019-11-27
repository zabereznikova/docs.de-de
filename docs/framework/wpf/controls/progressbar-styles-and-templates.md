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
ms.openlocfilehash: 6551701e86dd6abcd42f143f146c7bdadfeabbcf
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283457"
---
# <a name="progressbar-styles-and-templates"></a><span data-ttu-id="c938d-102">ProgressBar-Formate und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="c938d-102">ProgressBar Styles and Templates</span></span>
<span data-ttu-id="c938d-103">In diesem Thema werden die Stile und Vorlagen für das <xref:System.Windows.Controls.ProgressBar>-Steuerelement beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c938d-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ProgressBar> control.</span></span> <span data-ttu-id="c938d-104">Sie können die Standard <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement eine eindeutige Darstellung zu verschaffen.</span><span class="sxs-lookup"><span data-stu-id="c938d-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="c938d-105">Weitere Informationen finden Sie unter [Erstellen einer Vorlage für ein-Steuer](../../../desktop-wpf/themes/how-to-create-apply-template.md)Element.</span><span class="sxs-lookup"><span data-stu-id="c938d-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="progressbar-parts"></a><span data-ttu-id="c938d-106">ProgressBar-Teile</span><span class="sxs-lookup"><span data-stu-id="c938d-106">ProgressBar Parts</span></span>  
 <span data-ttu-id="c938d-107">In der folgenden Tabelle sind die benannten Teile für das <xref:System.Windows.Controls.ProgressBar>-Steuerelement aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="c938d-107">The following table lists the named parts for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="c938d-108">-Komponente</span><span class="sxs-lookup"><span data-stu-id="c938d-108">Part</span></span>|<span data-ttu-id="c938d-109">Typ</span><span class="sxs-lookup"><span data-stu-id="c938d-109">Type</span></span>|<span data-ttu-id="c938d-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c938d-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="c938d-111">PART_Indicator</span><span class="sxs-lookup"><span data-stu-id="c938d-111">PART_Indicator</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="c938d-112">Das Objekt, das den Fortschritt angibt.</span><span class="sxs-lookup"><span data-stu-id="c938d-112">The object that indicates progress.</span></span>|  
|<span data-ttu-id="c938d-113">PART_Track</span><span class="sxs-lookup"><span data-stu-id="c938d-113">PART_Track</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="c938d-114">Das-Objekt, das den Pfad der Statusanzeige definiert.</span><span class="sxs-lookup"><span data-stu-id="c938d-114">The object that defines the path of the progress indicator.</span></span>|  
|<span data-ttu-id="c938d-115">PART_GlowRect</span><span class="sxs-lookup"><span data-stu-id="c938d-115">PART_GlowRect</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="c938d-116">Ein-Objekt, das die Statusanzeige verschönert.</span><span class="sxs-lookup"><span data-stu-id="c938d-116">An object that embellishes the progress bar.</span></span>|  
  
## <a name="progressbar-states"></a><span data-ttu-id="c938d-117">ProgressBar-Zustände</span><span class="sxs-lookup"><span data-stu-id="c938d-117">ProgressBar States</span></span>  
 <span data-ttu-id="c938d-118">In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Controls.ProgressBar>-Steuerelement aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="c938d-118">The following table lists the visual states for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="c938d-119">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="c938d-119">VisualState Name</span></span>|<span data-ttu-id="c938d-120">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="c938d-120">VisualStateGroup Name</span></span>|<span data-ttu-id="c938d-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c938d-121">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="c938d-122">Bestimmte</span><span class="sxs-lookup"><span data-stu-id="c938d-122">Determinate</span></span>|<span data-ttu-id="c938d-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="c938d-123">CommonStates</span></span>|<span data-ttu-id="c938d-124"><xref:System.Windows.Controls.ProgressBar> meldet den Fortschritt basierend auf der <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="c938d-124"><xref:System.Windows.Controls.ProgressBar> reports progress based on the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> property.</span></span>|  
|<span data-ttu-id="c938d-125">Unbestimmten</span><span class="sxs-lookup"><span data-stu-id="c938d-125">Indeterminate</span></span>|<span data-ttu-id="c938d-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="c938d-126">CommonStates</span></span>|<span data-ttu-id="c938d-127"><xref:System.Windows.Controls.ProgressBar> meldet den generischen Fortschritt mit einem sich wiederholenden Muster.</span><span class="sxs-lookup"><span data-stu-id="c938d-127"><xref:System.Windows.Controls.ProgressBar> reports generic progress with a repeating pattern.</span></span>|  
|<span data-ttu-id="c938d-128">Gültig</span><span class="sxs-lookup"><span data-stu-id="c938d-128">Valid</span></span>|<span data-ttu-id="c938d-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="c938d-129">ValidationStates</span></span>|<span data-ttu-id="c938d-130">Das-Steuerelement verwendet die <xref:System.Windows.Controls.Validation>-Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false`.</span><span class="sxs-lookup"><span data-stu-id="c938d-130">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="c938d-131">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="c938d-131">InvalidFocused</span></span>|<span data-ttu-id="c938d-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="c938d-132">ValidationStates</span></span>|<span data-ttu-id="c938d-133">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true` hat, dass das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="c938d-133">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="c938d-134">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="c938d-134">InvalidUnfocused</span></span>|<span data-ttu-id="c938d-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="c938d-135">ValidationStates</span></span>|<span data-ttu-id="c938d-136">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, wenn das Steuerelement keinen Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="c938d-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="progressbar-controltemplate-example"></a><span data-ttu-id="c938d-137">ProgressBar ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="c938d-137">ProgressBar ControlTemplate Example</span></span>  
 <span data-ttu-id="c938d-138">Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.ControlTemplate> für das <xref:System.Windows.Controls.ProgressBar>-Steuerelement definiert wird.</span><span class="sxs-lookup"><span data-stu-id="c938d-138">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ProgressBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/progressbar.xaml#progressbar)]  
  
 <span data-ttu-id="c938d-139">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="c938d-139">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="c938d-140">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="c938d-140">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c938d-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c938d-141">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="c938d-142">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="c938d-142">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="c938d-143">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="c938d-143">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="c938d-144">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="c938d-144">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="c938d-145">Erstellen einer Vorlage für ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="c938d-145">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
