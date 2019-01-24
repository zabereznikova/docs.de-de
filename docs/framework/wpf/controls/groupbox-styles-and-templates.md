---
title: GroupBox-Stile und -Vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], GroupBox
- parts [WPF], GroupBox
- GroupBox [WPF], styles and templates
- states [WPF], GroupBox
- styles [WPF], GroupBox
- templates [WPF], GroupBox
ms.assetid: 33df7037-0a1b-476f-b9d0-41566a777699
ms.openlocfilehash: c67dd3fe7163bc09c74fb62fc448005334a24395
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54685125"
---
# <a name="groupbox-styles-and-templates"></a><span data-ttu-id="63b9d-102">GroupBox-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="63b9d-102">GroupBox Styles and Templates</span></span>
<a name="introduction"></a> <span data-ttu-id="63b9d-103">In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.GroupBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="63b9d-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.GroupBox> control.</span></span> <span data-ttu-id="63b9d-104">Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement eine unverwechselbare Darstellung verleihen.</span><span class="sxs-lookup"><span data-stu-id="63b9d-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="63b9d-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="63b9d-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
<a name="groupbox_parts"></a>   
## <a name="groupbox-parts"></a><span data-ttu-id="63b9d-106">GroupBox-Teile</span><span class="sxs-lookup"><span data-stu-id="63b9d-106">GroupBox Parts</span></span>  
 <span data-ttu-id="63b9d-107">Die <xref:System.Windows.Controls.GroupBox> Steuerelement enthält keine benannten Teile.</span><span class="sxs-lookup"><span data-stu-id="63b9d-107">The <xref:System.Windows.Controls.GroupBox> control does not have any named parts.</span></span>  
  
<a name="groupbox_states"></a>   
## <a name="groupbox-states"></a><span data-ttu-id="63b9d-108">GroupBox-Zustände</span><span class="sxs-lookup"><span data-stu-id="63b9d-108">GroupBox States</span></span>  
 <span data-ttu-id="63b9d-109">Die folgende Tabelle enthält die visuellen Zustände für die <xref:System.Windows.Controls.GroupBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="63b9d-109">The following table lists the visual states for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
|<span data-ttu-id="63b9d-110">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="63b9d-110">VisualState Name</span></span>|<span data-ttu-id="63b9d-111">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="63b9d-111">VisualStateGroup Name</span></span>|<span data-ttu-id="63b9d-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="63b9d-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="63b9d-113">Gültig</span><span class="sxs-lookup"><span data-stu-id="63b9d-113">Valid</span></span>|<span data-ttu-id="63b9d-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="63b9d-114">ValidationStates</span></span>|<span data-ttu-id="63b9d-115">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="63b9d-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="63b9d-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="63b9d-116">InvalidFocused</span></span>|<span data-ttu-id="63b9d-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="63b9d-117">ValidationStates</span></span>|<span data-ttu-id="63b9d-118">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="63b9d-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="63b9d-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="63b9d-119">InvalidUnfocused</span></span>|<span data-ttu-id="63b9d-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="63b9d-120">ValidationStates</span></span>|<span data-ttu-id="63b9d-121">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement keinen Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="63b9d-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
<a name="groupbox_controltemplate_example"></a>   
## <a name="groupbox-controltemplate-example"></a><span data-ttu-id="63b9d-122">GroupBox-ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="63b9d-122">GroupBox ControlTemplate Example</span></span>  
 <span data-ttu-id="63b9d-123">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.GroupBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="63b9d-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#GroupBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/groupbox.xaml#groupbox)]  
  
 <span data-ttu-id="63b9d-124">Die <xref:System.Windows.Controls.ControlTemplate> verwendet wird, eine oder mehrere der folgenden Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="63b9d-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="63b9d-125">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="63b9d-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63b9d-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63b9d-126">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="63b9d-127">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="63b9d-127">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)
- [<span data-ttu-id="63b9d-128">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="63b9d-128">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)
- [<span data-ttu-id="63b9d-129">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="63b9d-129">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)
- [<span data-ttu-id="63b9d-130">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="63b9d-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
