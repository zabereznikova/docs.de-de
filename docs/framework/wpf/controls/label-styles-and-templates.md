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
ms.openlocfilehash: 9d2f5e4d886d8fc46ecb14dd4f1bda67debdae97
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2018
ms.locfileid: "34457643"
---
# <a name="label-styles-and-templates"></a><span data-ttu-id="b334c-102">Bezeichnungsformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="b334c-102">Label Styles and Templates</span></span>
<span data-ttu-id="b334c-103">In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.Label> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="b334c-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Label> control.</span></span> <span data-ttu-id="b334c-104">Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement ein einzigartiges aussehen zu verleihen.</span><span class="sxs-lookup"><span data-stu-id="b334c-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="b334c-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="b334c-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="label-parts"></a><span data-ttu-id="b334c-106">Label-Teile</span><span class="sxs-lookup"><span data-stu-id="b334c-106">Label Parts</span></span>  
 <span data-ttu-id="b334c-107">Die <xref:System.Windows.Controls.Label> Steuerelement enthält keine benannten Teile.</span><span class="sxs-lookup"><span data-stu-id="b334c-107">The <xref:System.Windows.Controls.Label> control does not have any named parts.</span></span>  
  
## <a name="label-states"></a><span data-ttu-id="b334c-108">Label-Zustände</span><span class="sxs-lookup"><span data-stu-id="b334c-108">Label States</span></span>  
 <span data-ttu-id="b334c-109">Die folgende Tabelle enthält die visueller Zustände für die <xref:System.Windows.Controls.Label> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="b334c-109">The following table lists the visual states for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
|<span data-ttu-id="b334c-110">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="b334c-110">VisualState Name</span></span>|<span data-ttu-id="b334c-111">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="b334c-111">VisualStateGroup Name</span></span>|<span data-ttu-id="b334c-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b334c-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="b334c-113">Gültig</span><span class="sxs-lookup"><span data-stu-id="b334c-113">Valid</span></span>|<span data-ttu-id="b334c-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b334c-114">ValidationStates</span></span>|<span data-ttu-id="b334c-115">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="b334c-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="b334c-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="b334c-116">InvalidFocused</span></span>|<span data-ttu-id="b334c-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b334c-117">ValidationStates</span></span>|<span data-ttu-id="b334c-118">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` weist das Steuerelement den Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="b334c-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="b334c-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="b334c-119">InvalidUnfocused</span></span>|<span data-ttu-id="b334c-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b334c-120">ValidationStates</span></span>|<span data-ttu-id="b334c-121">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement verfügt nicht über den Fokus.</span><span class="sxs-lookup"><span data-stu-id="b334c-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="label-controltemplate-example"></a><span data-ttu-id="b334c-122">Beispiel für Bezeichnung ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="b334c-122">Label ControlTemplate Example</span></span>  
 <span data-ttu-id="b334c-123">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.Label> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="b334c-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Label](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/label.xaml#label)]  
  
 <span data-ttu-id="b334c-124">Die <xref:System.Windows.Controls.ControlTemplate> verwendet wird, eine oder mehrere der folgenden Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="b334c-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="b334c-125">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="b334c-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b334c-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b334c-126">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="b334c-127">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="b334c-127">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="b334c-128">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="b334c-128">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="b334c-129">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="b334c-129">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="b334c-130">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="b334c-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
