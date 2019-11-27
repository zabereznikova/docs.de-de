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
ms.openlocfilehash: 01233c5d0179e1a6f9bed651cd1f18058bfac168
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283610"
---
# <a name="window-styles-and-templates"></a><span data-ttu-id="84522-102">Window-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="84522-102">Window Styles and Templates</span></span>
<span data-ttu-id="84522-103">In diesem Thema werden die Stile und Vorlagen für das <xref:System.Windows.Window>-Steuerelement beschrieben.</span><span class="sxs-lookup"><span data-stu-id="84522-103">This topic describes the styles and templates for the <xref:System.Windows.Window> control.</span></span> <span data-ttu-id="84522-104">Sie können die Standard <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement eine eindeutige Darstellung zu verschaffen.</span><span class="sxs-lookup"><span data-stu-id="84522-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="84522-105">Weitere Informationen finden Sie unter [Erstellen einer Vorlage für ein-Steuer](../../../desktop-wpf/themes/how-to-create-apply-template.md)Element.</span><span class="sxs-lookup"><span data-stu-id="84522-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="window-parts"></a><span data-ttu-id="84522-106">Fensterteile</span><span class="sxs-lookup"><span data-stu-id="84522-106">Window Parts</span></span>  
 <span data-ttu-id="84522-107">Das <xref:System.Windows.Window>-Steuerelement verfügt über keine benannten Teile.</span><span class="sxs-lookup"><span data-stu-id="84522-107">The <xref:System.Windows.Window> control does not have any named parts.</span></span>  
  
## <a name="window-states"></a><span data-ttu-id="84522-108">Fenster Zustände</span><span class="sxs-lookup"><span data-stu-id="84522-108">Window States</span></span>  
 <span data-ttu-id="84522-109">In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Window>-Steuerelement aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="84522-109">The following table lists the visual states for the <xref:System.Windows.Window> control.</span></span>  
  
|<span data-ttu-id="84522-110">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="84522-110">VisualState Name</span></span>|<span data-ttu-id="84522-111">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="84522-111">VisualStateGroup Name</span></span>|<span data-ttu-id="84522-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="84522-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="84522-113">Gültig</span><span class="sxs-lookup"><span data-stu-id="84522-113">Valid</span></span>|<span data-ttu-id="84522-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="84522-114">ValidationStates</span></span>|<span data-ttu-id="84522-115">Das-Steuerelement verwendet die <xref:System.Windows.Controls.Validation>-Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false`.</span><span class="sxs-lookup"><span data-stu-id="84522-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="84522-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="84522-116">InvalidFocused</span></span>|<span data-ttu-id="84522-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="84522-117">ValidationStates</span></span>|<span data-ttu-id="84522-118">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true` hat, dass das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="84522-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="84522-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="84522-119">InvalidUnfocused</span></span>|<span data-ttu-id="84522-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="84522-120">ValidationStates</span></span>|<span data-ttu-id="84522-121">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, wenn das Steuerelement keinen Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="84522-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="window-controltemplate-example"></a><span data-ttu-id="84522-122">Fenster ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="84522-122">Window ControlTemplate Example</span></span>  
 <span data-ttu-id="84522-123">Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.ControlTemplate> für das <xref:System.Windows.Window>-Steuerelement definiert wird.</span><span class="sxs-lookup"><span data-stu-id="84522-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Window> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Window](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/window.xaml#window)]  
  
 <span data-ttu-id="84522-124">Der <xref:System.Windows.Controls.ControlTemplate> verwendet mindestens eine der folgenden Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="84522-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="84522-125">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="84522-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84522-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="84522-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="84522-127">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="84522-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="84522-128">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="84522-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="84522-129">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="84522-129">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="84522-130">Erstellen einer Vorlage für ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="84522-130">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
