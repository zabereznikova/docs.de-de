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
ms.openlocfilehash: de853198c97c99319bea4a816c9a6eca5dc5d917
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283736"
---
# <a name="frame-styles-and-templates"></a><span data-ttu-id="b03e8-102">Frame-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="b03e8-102">Frame Styles and Templates</span></span>
<span data-ttu-id="b03e8-103">In diesem Thema werden die Stile und Vorlagen für das <xref:System.Windows.Controls.Frame>-Steuerelement beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b03e8-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Frame> control.</span></span> <span data-ttu-id="b03e8-104">Sie können die Standard <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement eine eindeutige Darstellung zu verschaffen.</span><span class="sxs-lookup"><span data-stu-id="b03e8-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="b03e8-105">Weitere Informationen finden Sie unter [Erstellen einer Vorlage für ein-Steuer](../../../desktop-wpf/themes/how-to-create-apply-template.md)Element.</span><span class="sxs-lookup"><span data-stu-id="b03e8-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="frame-parts"></a><span data-ttu-id="b03e8-106">Frame Teile</span><span class="sxs-lookup"><span data-stu-id="b03e8-106">Frame Parts</span></span>  
 <span data-ttu-id="b03e8-107">In der folgenden Tabelle sind die benannten Teile für das <xref:System.Windows.Controls.Frame>-Steuerelement aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="b03e8-107">The following table lists the named parts for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="b03e8-108">-Komponente</span><span class="sxs-lookup"><span data-stu-id="b03e8-108">Part</span></span>|<span data-ttu-id="b03e8-109">Typ</span><span class="sxs-lookup"><span data-stu-id="b03e8-109">Type</span></span>|<span data-ttu-id="b03e8-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b03e8-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="b03e8-111">PART_FrameCP</span><span class="sxs-lookup"><span data-stu-id="b03e8-111">PART_FrameCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="b03e8-112">Der Inhalts Bereich.</span><span class="sxs-lookup"><span data-stu-id="b03e8-112">The content area.</span></span>|  
  
## <a name="frame-states"></a><span data-ttu-id="b03e8-113">Frame Zustände</span><span class="sxs-lookup"><span data-stu-id="b03e8-113">Frame States</span></span>  
 <span data-ttu-id="b03e8-114">In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Controls.Frame>-Steuerelement aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="b03e8-114">The following table lists the visual states for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="b03e8-115">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="b03e8-115">VisualState Name</span></span>|<span data-ttu-id="b03e8-116">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="b03e8-116">VisualStateGroup Name</span></span>|<span data-ttu-id="b03e8-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b03e8-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="b03e8-118">Gültig</span><span class="sxs-lookup"><span data-stu-id="b03e8-118">Valid</span></span>|<span data-ttu-id="b03e8-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b03e8-119">ValidationStates</span></span>|<span data-ttu-id="b03e8-120">Das-Steuerelement verwendet die <xref:System.Windows.Controls.Validation>-Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false`.</span><span class="sxs-lookup"><span data-stu-id="b03e8-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="b03e8-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="b03e8-121">InvalidFocused</span></span>|<span data-ttu-id="b03e8-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b03e8-122">ValidationStates</span></span>|<span data-ttu-id="b03e8-123">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true` hat, dass das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="b03e8-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="b03e8-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="b03e8-124">InvalidUnfocused</span></span>|<span data-ttu-id="b03e8-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b03e8-125">ValidationStates</span></span>|<span data-ttu-id="b03e8-126">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, wenn das Steuerelement keinen Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="b03e8-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="frame-controltemplate-example"></a><span data-ttu-id="b03e8-127">Frame ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="b03e8-127">Frame ControlTemplate Example</span></span>  
 <span data-ttu-id="b03e8-128">Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.ControlTemplate> für das <xref:System.Windows.Controls.Frame>-Steuerelement definiert wird.</span><span class="sxs-lookup"><span data-stu-id="b03e8-128">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Frame](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/frame.xaml#frame)]  
  
 <span data-ttu-id="b03e8-129">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="b03e8-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="b03e8-130">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="b03e8-130">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b03e8-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b03e8-131">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="b03e8-132">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="b03e8-132">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="b03e8-133">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="b03e8-133">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="b03e8-134">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="b03e8-134">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="b03e8-135">Erstellen einer Vorlage für ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="b03e8-135">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
