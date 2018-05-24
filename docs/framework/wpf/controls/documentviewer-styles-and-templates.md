---
title: DocumentViewer-Stile und -Vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- templates [WPF], DocumentViewer
- DocumentViewer [WPF], styles and templates
- states [WPF], DocumentViewer
- ControlTemplate [WPF], DocumentViewer
- parts [WPF], DocumentViewer
- styles [WPF], DocumentViewer
ms.assetid: 6bd4ff8f-ea6a-4084-ac58-e7a67446ce1c
ms.openlocfilehash: 217fa0ff7b8c34de817a269effbf64311bbea7f2
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2018
---
# <a name="documentviewer-styles-and-templates"></a><span data-ttu-id="ba6c8-102">DocumentViewer-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="ba6c8-102">DocumentViewer Styles and Templates</span></span>
<span data-ttu-id="ba6c8-103">In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.DocumentViewer> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ba6c8-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span> <span data-ttu-id="ba6c8-104">Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement ein einzigartiges aussehen zu verleihen.</span><span class="sxs-lookup"><span data-stu-id="ba6c8-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="ba6c8-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="ba6c8-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="documentviewer-parts"></a><span data-ttu-id="ba6c8-106">DocumentViewer-Teile</span><span class="sxs-lookup"><span data-stu-id="ba6c8-106">DocumentViewer Parts</span></span>  
 <span data-ttu-id="ba6c8-107">Die folgende Tabelle enthält die benannten Teile für die <xref:System.Windows.Controls.DocumentViewer> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ba6c8-107">The following table lists the named parts for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="ba6c8-108">Segment</span><span class="sxs-lookup"><span data-stu-id="ba6c8-108">Part</span></span>|<span data-ttu-id="ba6c8-109">Typ</span><span class="sxs-lookup"><span data-stu-id="ba6c8-109">Type</span></span>|<span data-ttu-id="ba6c8-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ba6c8-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="ba6c8-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="ba6c8-111">PART_ContentHost</span></span>|<xref:System.Windows.Controls.ScrollViewer>|<span data-ttu-id="ba6c8-112">Der Inhalt und Durchführen eines Bildlaufs Bereich.</span><span class="sxs-lookup"><span data-stu-id="ba6c8-112">The content and scrolling area.</span></span>|  
|<span data-ttu-id="ba6c8-113">PART_FindToolBarHost</span><span class="sxs-lookup"><span data-stu-id="ba6c8-113">PART_FindToolBarHost</span></span>|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="ba6c8-114">Das Suchfeld am unteren standardmäßig.</span><span class="sxs-lookup"><span data-stu-id="ba6c8-114">The search box, at the bottom by default.</span></span>|  
  
## <a name="documentviewer-states"></a><span data-ttu-id="ba6c8-115">DocumentViewer-Zustände</span><span class="sxs-lookup"><span data-stu-id="ba6c8-115">DocumentViewer States</span></span>  
 <span data-ttu-id="ba6c8-116">Die folgende Tabelle enthält die visueller Zustände für die <xref:System.Windows.Controls.DocumentViewer> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ba6c8-116">The following table lists the visual states for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="ba6c8-117">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="ba6c8-117">VisualState Name</span></span>|<span data-ttu-id="ba6c8-118">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="ba6c8-118">VisualStateGroup Name</span></span>|<span data-ttu-id="ba6c8-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ba6c8-119">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="ba6c8-120">Gültig</span><span class="sxs-lookup"><span data-stu-id="ba6c8-120">Valid</span></span>|<span data-ttu-id="ba6c8-121">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ba6c8-121">ValidationStates</span></span>|<span data-ttu-id="ba6c8-122">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="ba6c8-122">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="ba6c8-123">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="ba6c8-123">InvalidFocused</span></span>|<span data-ttu-id="ba6c8-124">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ba6c8-124">ValidationStates</span></span>|<span data-ttu-id="ba6c8-125">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` weist das Steuerelement den Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="ba6c8-125">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="ba6c8-126">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="ba6c8-126">InvalidUnfocused</span></span>|<span data-ttu-id="ba6c8-127">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ba6c8-127">ValidationStates</span></span>|<span data-ttu-id="ba6c8-128">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement verfügt nicht über den Fokus.</span><span class="sxs-lookup"><span data-stu-id="ba6c8-128">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="documentviewer-controltemplate-example"></a><span data-ttu-id="ba6c8-129">Beispiel für DocumentViewer-ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="ba6c8-129">DocumentViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="ba6c8-130">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.DocumentViewer> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ba6c8-130">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#DocumentViewer](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/documentviewer.xaml#documentviewer)]  
  
 <span data-ttu-id="ba6c8-131">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="ba6c8-131">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="ba6c8-132">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="ba6c8-132">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba6c8-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba6c8-133">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="ba6c8-134">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="ba6c8-134">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="ba6c8-135">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="ba6c8-135">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="ba6c8-136">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="ba6c8-136">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="ba6c8-137">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="ba6c8-137">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
