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
ms.openlocfilehash: f948cf2b4f4cd2a4cb73b0cd5fc754240c850b83
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61770525"
---
# <a name="progressbar-styles-and-templates"></a><span data-ttu-id="f1929-102">ProgressBar-Formate und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="f1929-102">ProgressBar Styles and Templates</span></span>
<span data-ttu-id="f1929-103">In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.ProgressBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="f1929-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ProgressBar> control.</span></span> <span data-ttu-id="f1929-104">Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement eine unverwechselbare Darstellung verleihen.</span><span class="sxs-lookup"><span data-stu-id="f1929-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="f1929-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="f1929-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="progressbar-parts"></a><span data-ttu-id="f1929-106">ProgressBar-Teile</span><span class="sxs-lookup"><span data-stu-id="f1929-106">ProgressBar Parts</span></span>  
 <span data-ttu-id="f1929-107">Die folgende Tabelle enthält die benannten Teile für den <xref:System.Windows.Controls.ProgressBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="f1929-107">The following table lists the named parts for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="f1929-108">Segment</span><span class="sxs-lookup"><span data-stu-id="f1929-108">Part</span></span>|<span data-ttu-id="f1929-109">Typ</span><span class="sxs-lookup"><span data-stu-id="f1929-109">Type</span></span>|<span data-ttu-id="f1929-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f1929-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="f1929-111">PART_Indicator</span><span class="sxs-lookup"><span data-stu-id="f1929-111">PART_Indicator</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="f1929-112">Das Objekt, das Status angibt.</span><span class="sxs-lookup"><span data-stu-id="f1929-112">The object that indicates progress.</span></span>|  
|<span data-ttu-id="f1929-113">PART_Track</span><span class="sxs-lookup"><span data-stu-id="f1929-113">PART_Track</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="f1929-114">Das Objekt, das den Pfad der Statusanzeige definiert.</span><span class="sxs-lookup"><span data-stu-id="f1929-114">The object that defines the path of the progress indicator.</span></span>|  
|<span data-ttu-id="f1929-115">PART_GlowRect</span><span class="sxs-lookup"><span data-stu-id="f1929-115">PART_GlowRect</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="f1929-116">Ein Objekt, das Darstellung der Statusanzeige verbessert.</span><span class="sxs-lookup"><span data-stu-id="f1929-116">An object that embellishes the progress bar.</span></span>|  
  
## <a name="progressbar-states"></a><span data-ttu-id="f1929-117">ProgressBar-Zustände</span><span class="sxs-lookup"><span data-stu-id="f1929-117">ProgressBar States</span></span>  
 <span data-ttu-id="f1929-118">Die folgende Tabelle enthält die visuellen Zustände für die <xref:System.Windows.Controls.ProgressBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="f1929-118">The following table lists the visual states for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="f1929-119">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="f1929-119">VisualState Name</span></span>|<span data-ttu-id="f1929-120">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="f1929-120">VisualStateGroup Name</span></span>|<span data-ttu-id="f1929-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f1929-121">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="f1929-122">Bestimmte</span><span class="sxs-lookup"><span data-stu-id="f1929-122">Determinate</span></span>|<span data-ttu-id="f1929-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="f1929-123">CommonStates</span></span>|<span data-ttu-id="f1929-124"><xref:System.Windows.Controls.ProgressBar> meldet den Fortschritt basierend auf den <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="f1929-124"><xref:System.Windows.Controls.ProgressBar> reports progress based on the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> property.</span></span>|  
|<span data-ttu-id="f1929-125">Unbestimmt</span><span class="sxs-lookup"><span data-stu-id="f1929-125">Indeterminate</span></span>|<span data-ttu-id="f1929-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="f1929-126">CommonStates</span></span>|<span data-ttu-id="f1929-127"><xref:System.Windows.Controls.ProgressBar> meldet den generischen Fortschritt mit einer sich wiederholenden.</span><span class="sxs-lookup"><span data-stu-id="f1929-127"><xref:System.Windows.Controls.ProgressBar> reports generic progress with a repeating pattern.</span></span>|  
|<span data-ttu-id="f1929-128">Gültig</span><span class="sxs-lookup"><span data-stu-id="f1929-128">Valid</span></span>|<span data-ttu-id="f1929-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f1929-129">ValidationStates</span></span>|<span data-ttu-id="f1929-130">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="f1929-130">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="f1929-131">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="f1929-131">InvalidFocused</span></span>|<span data-ttu-id="f1929-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f1929-132">ValidationStates</span></span>|<span data-ttu-id="f1929-133">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="f1929-133">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="f1929-134">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="f1929-134">InvalidUnfocused</span></span>|<span data-ttu-id="f1929-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f1929-135">ValidationStates</span></span>|<span data-ttu-id="f1929-136">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement keinen Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="f1929-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="progressbar-controltemplate-example"></a><span data-ttu-id="f1929-137">ProgressBar-ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="f1929-137">ProgressBar ControlTemplate Example</span></span>  
 <span data-ttu-id="f1929-138">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.ProgressBar> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="f1929-138">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ProgressBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/progressbar.xaml#progressbar)]  
  
 <span data-ttu-id="f1929-139">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="f1929-139">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="f1929-140">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="f1929-140">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1929-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f1929-141">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="f1929-142">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="f1929-142">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="f1929-143">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="f1929-143">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="f1929-144">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="f1929-144">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="f1929-145">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="f1929-145">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
