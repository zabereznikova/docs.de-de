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
ms.openlocfilehash: ebd21829591b8fefe87aeba0b86280f18eff4f06
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59203729"
---
# <a name="window-styles-and-templates"></a><span data-ttu-id="58a99-102">Window-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="58a99-102">Window Styles and Templates</span></span>
<span data-ttu-id="58a99-103">In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Window> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="58a99-103">This topic describes the styles and templates for the <xref:System.Windows.Window> control.</span></span> <span data-ttu-id="58a99-104">Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement eine unverwechselbare Darstellung verleihen.</span><span class="sxs-lookup"><span data-stu-id="58a99-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="58a99-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="58a99-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="window-parts"></a><span data-ttu-id="58a99-106">Fenster teilen</span><span class="sxs-lookup"><span data-stu-id="58a99-106">Window Parts</span></span>  
 <span data-ttu-id="58a99-107">Die <xref:System.Windows.Window> Steuerelement enthält keine benannten Teile.</span><span class="sxs-lookup"><span data-stu-id="58a99-107">The <xref:System.Windows.Window> control does not have any named parts.</span></span>  
  
## <a name="window-states"></a><span data-ttu-id="58a99-108">Status für</span><span class="sxs-lookup"><span data-stu-id="58a99-108">Window States</span></span>  
 <span data-ttu-id="58a99-109">Die folgende Tabelle enthält die visuellen Zustände für die <xref:System.Windows.Window> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="58a99-109">The following table lists the visual states for the <xref:System.Windows.Window> control.</span></span>  
  
|<span data-ttu-id="58a99-110">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="58a99-110">VisualState Name</span></span>|<span data-ttu-id="58a99-111">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="58a99-111">VisualStateGroup Name</span></span>|<span data-ttu-id="58a99-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58a99-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="58a99-113">Gültig</span><span class="sxs-lookup"><span data-stu-id="58a99-113">Valid</span></span>|<span data-ttu-id="58a99-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="58a99-114">ValidationStates</span></span>|<span data-ttu-id="58a99-115">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="58a99-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="58a99-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="58a99-116">InvalidFocused</span></span>|<span data-ttu-id="58a99-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="58a99-117">ValidationStates</span></span>|<span data-ttu-id="58a99-118">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="58a99-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="58a99-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="58a99-119">InvalidUnfocused</span></span>|<span data-ttu-id="58a99-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="58a99-120">ValidationStates</span></span>|<span data-ttu-id="58a99-121">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement keinen Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="58a99-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="window-controltemplate-example"></a><span data-ttu-id="58a99-122">Fenster-ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="58a99-122">Window ControlTemplate Example</span></span>  
 <span data-ttu-id="58a99-123">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Window> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="58a99-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Window> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Window](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/window.xaml#window)]  
  
 <span data-ttu-id="58a99-124">Die <xref:System.Windows.Controls.ControlTemplate> verwendet wird, eine oder mehrere der folgenden Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="58a99-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="58a99-125">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="58a99-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58a99-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58a99-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="58a99-127">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="58a99-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="58a99-128">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="58a99-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="58a99-129">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="58a99-129">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="58a99-130">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="58a99-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
