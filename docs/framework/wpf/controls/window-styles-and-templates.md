---
title: Window-Stile und -Vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], Window
- templates [WPF], Window
- styles [WPF], Window
- ControlTemplate [WPF], Window
- Window [WPF], styles and templates
- states [WPF], Window
ms.assetid: 2dfdf025-347b-4342-bf28-95206c273f35
ms.openlocfilehash: 4704bc7e51c10af79d39e7c6ea9013e12ec22d4c
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2018
---
# <a name="window-styles-and-templates"></a><span data-ttu-id="fa104-102">Window-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="fa104-102">Window Styles and Templates</span></span>
<span data-ttu-id="fa104-103">In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Window> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="fa104-103">This topic describes the styles and templates for the <xref:System.Windows.Window> control.</span></span> <span data-ttu-id="fa104-104">Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement ein einzigartiges aussehen zu verleihen.</span><span class="sxs-lookup"><span data-stu-id="fa104-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="fa104-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="fa104-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="window-parts"></a><span data-ttu-id="fa104-106">Fenster teilen</span><span class="sxs-lookup"><span data-stu-id="fa104-106">Window Parts</span></span>  
 <span data-ttu-id="fa104-107">Die <xref:System.Windows.Window> Steuerelement enthält keine benannten Teile.</span><span class="sxs-lookup"><span data-stu-id="fa104-107">The <xref:System.Windows.Window> control does not have any named parts.</span></span>  
  
## <a name="window-states"></a><span data-ttu-id="fa104-108">Fenster-Zustände</span><span class="sxs-lookup"><span data-stu-id="fa104-108">Window States</span></span>  
 <span data-ttu-id="fa104-109">Die folgende Tabelle enthält die visueller Zustände für die <xref:System.Windows.Window> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="fa104-109">The following table lists the visual states for the <xref:System.Windows.Window> control.</span></span>  
  
|<span data-ttu-id="fa104-110">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="fa104-110">VisualState Name</span></span>|<span data-ttu-id="fa104-111">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="fa104-111">VisualStateGroup Name</span></span>|<span data-ttu-id="fa104-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fa104-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="fa104-113">Gültig</span><span class="sxs-lookup"><span data-stu-id="fa104-113">Valid</span></span>|<span data-ttu-id="fa104-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fa104-114">ValidationStates</span></span>|<span data-ttu-id="fa104-115">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="fa104-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="fa104-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="fa104-116">InvalidFocused</span></span>|<span data-ttu-id="fa104-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fa104-117">ValidationStates</span></span>|<span data-ttu-id="fa104-118">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` weist das Steuerelement den Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="fa104-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="fa104-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="fa104-119">InvalidUnfocused</span></span>|<span data-ttu-id="fa104-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fa104-120">ValidationStates</span></span>|<span data-ttu-id="fa104-121">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement verfügt nicht über den Fokus.</span><span class="sxs-lookup"><span data-stu-id="fa104-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="window-controltemplate-example"></a><span data-ttu-id="fa104-122">Beispiel für Fenster-ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="fa104-122">Window ControlTemplate Example</span></span>  
 <span data-ttu-id="fa104-123">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Window> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="fa104-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Window> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Window](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/window.xaml#window)]  
  
 <span data-ttu-id="fa104-124">Die <xref:System.Windows.Controls.ControlTemplate> verwendet wird, eine oder mehrere der folgenden Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="fa104-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="fa104-125">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="fa104-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa104-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa104-126">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="fa104-127">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="fa104-127">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="fa104-128">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="fa104-128">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="fa104-129">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="fa104-129">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="fa104-130">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="fa104-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
