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
ms.openlocfilehash: fbe49ae98e0fe281500ae37d53a3d47ff1d0b03a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54700268"
---
# <a name="frame-styles-and-templates"></a><span data-ttu-id="a947a-102">Frame-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="a947a-102">Frame Styles and Templates</span></span>
<span data-ttu-id="a947a-103">In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.Frame> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="a947a-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Frame> control.</span></span> <span data-ttu-id="a947a-104">Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement eine unverwechselbare Darstellung verleihen.</span><span class="sxs-lookup"><span data-stu-id="a947a-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="a947a-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="a947a-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="frame-parts"></a><span data-ttu-id="a947a-106">Frame-Teile</span><span class="sxs-lookup"><span data-stu-id="a947a-106">Frame Parts</span></span>  
 <span data-ttu-id="a947a-107">Die folgende Tabelle enthält die benannten Teile für den <xref:System.Windows.Controls.Frame> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="a947a-107">The following table lists the named parts for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="a947a-108">Segment</span><span class="sxs-lookup"><span data-stu-id="a947a-108">Part</span></span>|<span data-ttu-id="a947a-109">Typ</span><span class="sxs-lookup"><span data-stu-id="a947a-109">Type</span></span>|<span data-ttu-id="a947a-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a947a-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="a947a-111">PART_FrameCP</span><span class="sxs-lookup"><span data-stu-id="a947a-111">PART_FrameCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="a947a-112">Der Inhaltsbereich.</span><span class="sxs-lookup"><span data-stu-id="a947a-112">The content area.</span></span>|  
  
## <a name="frame-states"></a><span data-ttu-id="a947a-113">Frame-Zustände</span><span class="sxs-lookup"><span data-stu-id="a947a-113">Frame States</span></span>  
 <span data-ttu-id="a947a-114">Die folgende Tabelle enthält die visuellen Zustände für die <xref:System.Windows.Controls.Frame> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="a947a-114">The following table lists the visual states for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="a947a-115">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="a947a-115">VisualState Name</span></span>|<span data-ttu-id="a947a-116">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="a947a-116">VisualStateGroup Name</span></span>|<span data-ttu-id="a947a-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a947a-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="a947a-118">Gültig</span><span class="sxs-lookup"><span data-stu-id="a947a-118">Valid</span></span>|<span data-ttu-id="a947a-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a947a-119">ValidationStates</span></span>|<span data-ttu-id="a947a-120">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="a947a-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="a947a-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="a947a-121">InvalidFocused</span></span>|<span data-ttu-id="a947a-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a947a-122">ValidationStates</span></span>|<span data-ttu-id="a947a-123">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="a947a-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="a947a-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="a947a-124">InvalidUnfocused</span></span>|<span data-ttu-id="a947a-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a947a-125">ValidationStates</span></span>|<span data-ttu-id="a947a-126">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement keinen Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="a947a-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="frame-controltemplate-example"></a><span data-ttu-id="a947a-127">Frame-ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="a947a-127">Frame ControlTemplate Example</span></span>  
 <span data-ttu-id="a947a-128">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.Frame> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="a947a-128">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Frame](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/frame.xaml#frame)]  
  
 <span data-ttu-id="a947a-129">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="a947a-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="a947a-130">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="a947a-130">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a947a-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a947a-131">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="a947a-132">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="a947a-132">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)
- [<span data-ttu-id="a947a-133">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="a947a-133">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)
- [<span data-ttu-id="a947a-134">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="a947a-134">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)
- [<span data-ttu-id="a947a-135">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="a947a-135">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
