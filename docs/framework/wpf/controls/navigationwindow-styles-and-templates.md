---
title: NavigationWindow-Stile und -Vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], NavigationWindow
- NavigationWindow [WPF], styles and templates
- ControlTemplate [WPF], NavigationWindow
- parts [WPF], NavigationWindow
- styles [WPF], NavigationWindow
- templates [WPF], NavigationWindow
ms.assetid: 3656055e-3222-43c8-b868-fd0c90cc31a3
ms.openlocfilehash: 5cc504956ce036505ac9261ea1438c7881fa2790
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283495"
---
# <a name="navigationwindow-styles-and-templates"></a><span data-ttu-id="1c864-102">NavigationWindow-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="1c864-102">NavigationWindow Styles and Templates</span></span>
<span data-ttu-id="1c864-103">In diesem Thema werden die Stile und Vorlagen für das <xref:System.Windows.Navigation.NavigationWindow>-Steuerelement beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1c864-103">This topic describes the styles and templates for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span> <span data-ttu-id="1c864-104">Sie können die Standard <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement eine eindeutige Darstellung zu verschaffen.</span><span class="sxs-lookup"><span data-stu-id="1c864-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="1c864-105">Weitere Informationen finden Sie unter [Erstellen einer Vorlage für ein-Steuer](../../../desktop-wpf/themes/how-to-create-apply-template.md)Element.</span><span class="sxs-lookup"><span data-stu-id="1c864-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="navigationwindow-parts"></a><span data-ttu-id="1c864-106">NavigationWindow-Teile</span><span class="sxs-lookup"><span data-stu-id="1c864-106">NavigationWindow Parts</span></span>  
 <span data-ttu-id="1c864-107">In der folgenden Tabelle sind die benannten Teile für das <xref:System.Windows.Navigation.NavigationWindow>-Steuerelement aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="1c864-107">The following table lists the named parts for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span>  
  
|<span data-ttu-id="1c864-108">Segment</span><span class="sxs-lookup"><span data-stu-id="1c864-108">Part</span></span>|<span data-ttu-id="1c864-109">Typ</span><span class="sxs-lookup"><span data-stu-id="1c864-109">Type</span></span>|<span data-ttu-id="1c864-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1c864-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="1c864-111">PART_NavWinCP</span><span class="sxs-lookup"><span data-stu-id="1c864-111">PART_NavWinCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="1c864-112">Der Bereich für den Inhalt.</span><span class="sxs-lookup"><span data-stu-id="1c864-112">The area for the content.</span></span>|  
  
## <a name="navigationwindow-states"></a><span data-ttu-id="1c864-113">NavigationWindow-Zustände</span><span class="sxs-lookup"><span data-stu-id="1c864-113">NavigationWindow States</span></span>  
 <span data-ttu-id="1c864-114">In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Navigation.NavigationWindow>-Steuerelement aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="1c864-114">The following table lists the visual states for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span>  
  
|<span data-ttu-id="1c864-115">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="1c864-115">VisualState Name</span></span>|<span data-ttu-id="1c864-116">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="1c864-116">VisualStateGroup Name</span></span>|<span data-ttu-id="1c864-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1c864-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="1c864-118">Gültig</span><span class="sxs-lookup"><span data-stu-id="1c864-118">Valid</span></span>|<span data-ttu-id="1c864-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="1c864-119">ValidationStates</span></span>|<span data-ttu-id="1c864-120">Das-Steuerelement verwendet die <xref:System.Windows.Controls.Validation>-Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false`.</span><span class="sxs-lookup"><span data-stu-id="1c864-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="1c864-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="1c864-121">InvalidFocused</span></span>|<span data-ttu-id="1c864-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="1c864-122">ValidationStates</span></span>|<span data-ttu-id="1c864-123">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true` hat, dass das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="1c864-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="1c864-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="1c864-124">InvalidUnfocused</span></span>|<span data-ttu-id="1c864-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="1c864-125">ValidationStates</span></span>|<span data-ttu-id="1c864-126">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, wenn das Steuerelement keinen Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="1c864-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="navigationwindow-controltemplate-example"></a><span data-ttu-id="1c864-127">Beispiel für NavigationWindow ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="1c864-127">NavigationWindow ControlTemplate Example</span></span>  
 <span data-ttu-id="1c864-128">Obwohl dieses Beispiel alle Elemente enthält, die standardmäßig im <xref:System.Windows.Controls.ControlTemplate> eines <xref:System.Windows.Navigation.NavigationWindow> definiert sind, sollten die spezifischen Werte als Beispiele betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="1c864-128">Although this example contains all of the elements that are defined in the <xref:System.Windows.Controls.ControlTemplate> of a <xref:System.Windows.Navigation.NavigationWindow> by default, the specific values should be thought of as examples.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#NavigationWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/navigationwindow.xaml#navigationwindow)]  
  
 <span data-ttu-id="1c864-129">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="1c864-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="1c864-130">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="1c864-130">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c864-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c864-131">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="1c864-132">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="1c864-132">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="1c864-133">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="1c864-133">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="1c864-134">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="1c864-134">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="1c864-135">Erstellen einer Vorlage für ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="1c864-135">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
