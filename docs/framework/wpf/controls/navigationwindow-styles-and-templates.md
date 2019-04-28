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
ms.openlocfilehash: 32d8aac99d40693e66c7b52a6c7d2c116d2f3baf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61770655"
---
# <a name="navigationwindow-styles-and-templates"></a><span data-ttu-id="2306d-102">NavigationWindow-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="2306d-102">NavigationWindow Styles and Templates</span></span>
<span data-ttu-id="2306d-103">In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Navigation.NavigationWindow> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="2306d-103">This topic describes the styles and templates for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span> <span data-ttu-id="2306d-104">Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement eine unverwechselbare Darstellung verleihen.</span><span class="sxs-lookup"><span data-stu-id="2306d-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="2306d-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="2306d-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="navigationwindow-parts"></a><span data-ttu-id="2306d-106">NavigationWindow-Teile</span><span class="sxs-lookup"><span data-stu-id="2306d-106">NavigationWindow Parts</span></span>  
 <span data-ttu-id="2306d-107">Die folgende Tabelle enthält die benannten Teile für den <xref:System.Windows.Navigation.NavigationWindow> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="2306d-107">The following table lists the named parts for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span>  
  
|<span data-ttu-id="2306d-108">Segment</span><span class="sxs-lookup"><span data-stu-id="2306d-108">Part</span></span>|<span data-ttu-id="2306d-109">Typ</span><span class="sxs-lookup"><span data-stu-id="2306d-109">Type</span></span>|<span data-ttu-id="2306d-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2306d-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="2306d-111">PART_NavWinCP</span><span class="sxs-lookup"><span data-stu-id="2306d-111">PART_NavWinCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="2306d-112">Der Bereich für den Inhalt.</span><span class="sxs-lookup"><span data-stu-id="2306d-112">The area for the content.</span></span>|  
  
## <a name="navigationwindow-states"></a><span data-ttu-id="2306d-113">NavigationWindow-Zustände</span><span class="sxs-lookup"><span data-stu-id="2306d-113">NavigationWindow States</span></span>  
 <span data-ttu-id="2306d-114">Die folgende Tabelle enthält die visuellen Zustände für die <xref:System.Windows.Navigation.NavigationWindow> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="2306d-114">The following table lists the visual states for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span>  
  
|<span data-ttu-id="2306d-115">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="2306d-115">VisualState Name</span></span>|<span data-ttu-id="2306d-116">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="2306d-116">VisualStateGroup Name</span></span>|<span data-ttu-id="2306d-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2306d-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="2306d-118">Gültig</span><span class="sxs-lookup"><span data-stu-id="2306d-118">Valid</span></span>|<span data-ttu-id="2306d-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="2306d-119">ValidationStates</span></span>|<span data-ttu-id="2306d-120">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="2306d-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="2306d-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="2306d-121">InvalidFocused</span></span>|<span data-ttu-id="2306d-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="2306d-122">ValidationStates</span></span>|<span data-ttu-id="2306d-123">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="2306d-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="2306d-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="2306d-124">InvalidUnfocused</span></span>|<span data-ttu-id="2306d-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="2306d-125">ValidationStates</span></span>|<span data-ttu-id="2306d-126">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement keinen Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="2306d-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="navigationwindow-controltemplate-example"></a><span data-ttu-id="2306d-127">NavigationWindow-ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="2306d-127">NavigationWindow ControlTemplate Example</span></span>  
 <span data-ttu-id="2306d-128">Obwohl in diesem Beispiel enthält alle Elemente, die definiert sind die <xref:System.Windows.Controls.ControlTemplate> von einer <xref:System.Windows.Navigation.NavigationWindow> standardmäßig die spezifischen Werte sollten als betrachtet werden Beispiele.</span><span class="sxs-lookup"><span data-stu-id="2306d-128">Although this example contains all of the elements that are defined in the <xref:System.Windows.Controls.ControlTemplate> of a <xref:System.Windows.Navigation.NavigationWindow> by default, the specific values should be thought of as examples.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#NavigationWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/navigationwindow.xaml#navigationwindow)]  
  
 <span data-ttu-id="2306d-129">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="2306d-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="2306d-130">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="2306d-130">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2306d-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2306d-131">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="2306d-132">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="2306d-132">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="2306d-133">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="2306d-133">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="2306d-134">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="2306d-134">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="2306d-135">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="2306d-135">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
