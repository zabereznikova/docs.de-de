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
ms.openlocfilehash: 3a1bea39ba9b6d2cff9937a3fee1d1de41daf16b
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459870"
---
# <a name="progressbar-styles-and-templates"></a><span data-ttu-id="2e6f6-102">ProgressBar-Formate und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="2e6f6-102">ProgressBar Styles and Templates</span></span>
<span data-ttu-id="2e6f6-103">In diesem Thema werden die Stile und Vorlagen für das <xref:System.Windows.Controls.ProgressBar>-Steuerelement beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2e6f6-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ProgressBar> control.</span></span> <span data-ttu-id="2e6f6-104">Sie können die Standard <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement eine eindeutige Darstellung zu verschaffen.</span><span class="sxs-lookup"><span data-stu-id="2e6f6-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="2e6f6-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="2e6f6-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="progressbar-parts"></a><span data-ttu-id="2e6f6-106">ProgressBar-Teile</span><span class="sxs-lookup"><span data-stu-id="2e6f6-106">ProgressBar Parts</span></span>  
 <span data-ttu-id="2e6f6-107">In der folgenden Tabelle sind die benannten Teile für das <xref:System.Windows.Controls.ProgressBar>-Steuerelement aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="2e6f6-107">The following table lists the named parts for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="2e6f6-108">Segment</span><span class="sxs-lookup"><span data-stu-id="2e6f6-108">Part</span></span>|<span data-ttu-id="2e6f6-109">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="2e6f6-109">Type</span></span>|<span data-ttu-id="2e6f6-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2e6f6-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="2e6f6-111">PART_Indicator</span><span class="sxs-lookup"><span data-stu-id="2e6f6-111">PART_Indicator</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="2e6f6-112">Das Objekt, das den Fortschritt angibt.</span><span class="sxs-lookup"><span data-stu-id="2e6f6-112">The object that indicates progress.</span></span>|  
|<span data-ttu-id="2e6f6-113">PART_Track</span><span class="sxs-lookup"><span data-stu-id="2e6f6-113">PART_Track</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="2e6f6-114">Das-Objekt, das den Pfad der Statusanzeige definiert.</span><span class="sxs-lookup"><span data-stu-id="2e6f6-114">The object that defines the path of the progress indicator.</span></span>|  
|<span data-ttu-id="2e6f6-115">PART_GlowRect</span><span class="sxs-lookup"><span data-stu-id="2e6f6-115">PART_GlowRect</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="2e6f6-116">Ein-Objekt, das die Statusanzeige verschönert.</span><span class="sxs-lookup"><span data-stu-id="2e6f6-116">An object that embellishes the progress bar.</span></span>|  
  
## <a name="progressbar-states"></a><span data-ttu-id="2e6f6-117">ProgressBar-Zustände</span><span class="sxs-lookup"><span data-stu-id="2e6f6-117">ProgressBar States</span></span>  
 <span data-ttu-id="2e6f6-118">In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Controls.ProgressBar>-Steuerelement aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="2e6f6-118">The following table lists the visual states for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="2e6f6-119">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="2e6f6-119">VisualState Name</span></span>|<span data-ttu-id="2e6f6-120">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="2e6f6-120">VisualStateGroup Name</span></span>|<span data-ttu-id="2e6f6-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2e6f6-121">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="2e6f6-122">Bestimmte</span><span class="sxs-lookup"><span data-stu-id="2e6f6-122">Determinate</span></span>|<span data-ttu-id="2e6f6-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="2e6f6-123">CommonStates</span></span>|<span data-ttu-id="2e6f6-124"><xref:System.Windows.Controls.ProgressBar> meldet den Fortschritt basierend auf der <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="2e6f6-124"><xref:System.Windows.Controls.ProgressBar> reports progress based on the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> property.</span></span>|  
|<span data-ttu-id="2e6f6-125">Unbestimmten</span><span class="sxs-lookup"><span data-stu-id="2e6f6-125">Indeterminate</span></span>|<span data-ttu-id="2e6f6-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="2e6f6-126">CommonStates</span></span>|<span data-ttu-id="2e6f6-127"><xref:System.Windows.Controls.ProgressBar> meldet den generischen Fortschritt mit einem sich wiederholenden Muster.</span><span class="sxs-lookup"><span data-stu-id="2e6f6-127"><xref:System.Windows.Controls.ProgressBar> reports generic progress with a repeating pattern.</span></span>|  
|<span data-ttu-id="2e6f6-128">Gültig</span><span class="sxs-lookup"><span data-stu-id="2e6f6-128">Valid</span></span>|<span data-ttu-id="2e6f6-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="2e6f6-129">ValidationStates</span></span>|<span data-ttu-id="2e6f6-130">Das-Steuerelement verwendet die <xref:System.Windows.Controls.Validation>-Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false`.</span><span class="sxs-lookup"><span data-stu-id="2e6f6-130">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="2e6f6-131">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="2e6f6-131">InvalidFocused</span></span>|<span data-ttu-id="2e6f6-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="2e6f6-132">ValidationStates</span></span>|<span data-ttu-id="2e6f6-133">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true` hat, dass das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="2e6f6-133">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="2e6f6-134">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="2e6f6-134">InvalidUnfocused</span></span>|<span data-ttu-id="2e6f6-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="2e6f6-135">ValidationStates</span></span>|<span data-ttu-id="2e6f6-136">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, wenn das Steuerelement keinen Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="2e6f6-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="progressbar-controltemplate-example"></a><span data-ttu-id="2e6f6-137">ProgressBar ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="2e6f6-137">ProgressBar ControlTemplate Example</span></span>  
 <span data-ttu-id="2e6f6-138">Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.ControlTemplate> für das <xref:System.Windows.Controls.ProgressBar>-Steuerelement definiert wird.</span><span class="sxs-lookup"><span data-stu-id="2e6f6-138">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ProgressBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/progressbar.xaml#progressbar)]  
  
 <span data-ttu-id="2e6f6-139">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="2e6f6-139">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="2e6f6-140">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="2e6f6-140">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e6f6-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e6f6-141">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="2e6f6-142">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="2e6f6-142">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="2e6f6-143">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="2e6f6-143">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="2e6f6-144">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="2e6f6-144">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="2e6f6-145">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="2e6f6-145">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
