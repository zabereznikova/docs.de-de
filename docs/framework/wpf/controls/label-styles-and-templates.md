---
title: Bezeichnungsformate und -vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- templates [WPF], Label
- parts [WPF], Label
- ControlTemplate [WPF], Label
- styles [WPF], Label
- Label [WPF], styles and templates
- states [WPF], Label
ms.assetid: c1d5359a-8e4a-4925-ab3e-e92bf6694859
ms.openlocfilehash: fb143bc44e8c7bad1c16507b03249e3c62e5b71f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54694112"
---
# <a name="label-styles-and-templates"></a><span data-ttu-id="a6fb8-102">Bezeichnungsformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="a6fb8-102">Label Styles and Templates</span></span>
<span data-ttu-id="a6fb8-103">In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.Label> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="a6fb8-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Label> control.</span></span> <span data-ttu-id="a6fb8-104">Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement eine unverwechselbare Darstellung verleihen.</span><span class="sxs-lookup"><span data-stu-id="a6fb8-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="a6fb8-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="a6fb8-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="label-parts"></a><span data-ttu-id="a6fb8-106">Bezeichnung Teilen</span><span class="sxs-lookup"><span data-stu-id="a6fb8-106">Label Parts</span></span>  
 <span data-ttu-id="a6fb8-107">Die <xref:System.Windows.Controls.Label> Steuerelement enthält keine benannten Teile.</span><span class="sxs-lookup"><span data-stu-id="a6fb8-107">The <xref:System.Windows.Controls.Label> control does not have any named parts.</span></span>  
  
## <a name="label-states"></a><span data-ttu-id="a6fb8-108">Label-Status</span><span class="sxs-lookup"><span data-stu-id="a6fb8-108">Label States</span></span>  
 <span data-ttu-id="a6fb8-109">Die folgende Tabelle enthält die visuellen Zustände für die <xref:System.Windows.Controls.Label> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="a6fb8-109">The following table lists the visual states for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
|<span data-ttu-id="a6fb8-110">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="a6fb8-110">VisualState Name</span></span>|<span data-ttu-id="a6fb8-111">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="a6fb8-111">VisualStateGroup Name</span></span>|<span data-ttu-id="a6fb8-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a6fb8-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="a6fb8-113">Gültig</span><span class="sxs-lookup"><span data-stu-id="a6fb8-113">Valid</span></span>|<span data-ttu-id="a6fb8-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a6fb8-114">ValidationStates</span></span>|<span data-ttu-id="a6fb8-115">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="a6fb8-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="a6fb8-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="a6fb8-116">InvalidFocused</span></span>|<span data-ttu-id="a6fb8-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a6fb8-117">ValidationStates</span></span>|<span data-ttu-id="a6fb8-118">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="a6fb8-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="a6fb8-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="a6fb8-119">InvalidUnfocused</span></span>|<span data-ttu-id="a6fb8-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a6fb8-120">ValidationStates</span></span>|<span data-ttu-id="a6fb8-121">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement keinen Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="a6fb8-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="label-controltemplate-example"></a><span data-ttu-id="a6fb8-122">Label-ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="a6fb8-122">Label ControlTemplate Example</span></span>  
 <span data-ttu-id="a6fb8-123">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.Label> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="a6fb8-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Label](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/label.xaml#label)]  
  
 <span data-ttu-id="a6fb8-124">Die <xref:System.Windows.Controls.ControlTemplate> verwendet wird, eine oder mehrere der folgenden Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="a6fb8-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="a6fb8-125">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="a6fb8-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6fb8-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a6fb8-126">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="a6fb8-127">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="a6fb8-127">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)
- [<span data-ttu-id="a6fb8-128">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="a6fb8-128">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)
- [<span data-ttu-id="a6fb8-129">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="a6fb8-129">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)
- [<span data-ttu-id="a6fb8-130">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="a6fb8-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
