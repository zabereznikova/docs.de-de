---
title: Frame-Stile und -Vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], Frame
- templates [WPF], Frame
- ControlTemplate [WPF], Frame
- Frame [WPF], styles and templates
- states [WPF], Frame
- styles [WPF], Frame
ms.assetid: a01c32e2-c951-46a0-a82f-2614ca241f0b
ms.openlocfilehash: 89f4fc21637d20ca226507463093bc6bae2241fc
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460320"
---
# <a name="frame-styles-and-templates"></a><span data-ttu-id="66794-102">Frame-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="66794-102">Frame Styles and Templates</span></span>
<span data-ttu-id="66794-103">In diesem Thema werden die Stile und Vorlagen für das <xref:System.Windows.Controls.Frame>-Steuerelement beschrieben.</span><span class="sxs-lookup"><span data-stu-id="66794-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Frame> control.</span></span> <span data-ttu-id="66794-104">Sie können die Standard <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement eine eindeutige Darstellung zu verschaffen.</span><span class="sxs-lookup"><span data-stu-id="66794-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="66794-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="66794-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="frame-parts"></a><span data-ttu-id="66794-106">Frame Teile</span><span class="sxs-lookup"><span data-stu-id="66794-106">Frame Parts</span></span>  
 <span data-ttu-id="66794-107">In der folgenden Tabelle sind die benannten Teile für das <xref:System.Windows.Controls.Frame>-Steuerelement aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="66794-107">The following table lists the named parts for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="66794-108">Segment</span><span class="sxs-lookup"><span data-stu-id="66794-108">Part</span></span>|<span data-ttu-id="66794-109">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="66794-109">Type</span></span>|<span data-ttu-id="66794-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="66794-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="66794-111">PART_FrameCP</span><span class="sxs-lookup"><span data-stu-id="66794-111">PART_FrameCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="66794-112">Der Inhalts Bereich.</span><span class="sxs-lookup"><span data-stu-id="66794-112">The content area.</span></span>|  
  
## <a name="frame-states"></a><span data-ttu-id="66794-113">Frame Zustände</span><span class="sxs-lookup"><span data-stu-id="66794-113">Frame States</span></span>  
 <span data-ttu-id="66794-114">In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Controls.Frame>-Steuerelement aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="66794-114">The following table lists the visual states for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="66794-115">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="66794-115">VisualState Name</span></span>|<span data-ttu-id="66794-116">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="66794-116">VisualStateGroup Name</span></span>|<span data-ttu-id="66794-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="66794-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="66794-118">Gültig</span><span class="sxs-lookup"><span data-stu-id="66794-118">Valid</span></span>|<span data-ttu-id="66794-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="66794-119">ValidationStates</span></span>|<span data-ttu-id="66794-120">Das-Steuerelement verwendet die <xref:System.Windows.Controls.Validation>-Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false`.</span><span class="sxs-lookup"><span data-stu-id="66794-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="66794-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="66794-121">InvalidFocused</span></span>|<span data-ttu-id="66794-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="66794-122">ValidationStates</span></span>|<span data-ttu-id="66794-123">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true` hat, dass das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="66794-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="66794-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="66794-124">InvalidUnfocused</span></span>|<span data-ttu-id="66794-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="66794-125">ValidationStates</span></span>|<span data-ttu-id="66794-126">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, wenn das Steuerelement keinen Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="66794-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="frame-controltemplate-example"></a><span data-ttu-id="66794-127">Frame ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="66794-127">Frame ControlTemplate Example</span></span>  
 <span data-ttu-id="66794-128">Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.ControlTemplate> für das <xref:System.Windows.Controls.Frame>-Steuerelement definiert wird.</span><span class="sxs-lookup"><span data-stu-id="66794-128">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Frame](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/frame.xaml#frame)]  
  
 <span data-ttu-id="66794-129">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="66794-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="66794-130">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="66794-130">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66794-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="66794-131">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="66794-132">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="66794-132">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="66794-133">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="66794-133">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="66794-134">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="66794-134">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="66794-135">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="66794-135">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
