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
ms.openlocfilehash: 4e91a640b36e4793567c9e728fd71ec8ce596743
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61911767"
---
# <a name="documentviewer-styles-and-templates"></a><span data-ttu-id="0e7e5-102">DocumentViewer-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="0e7e5-102">DocumentViewer Styles and Templates</span></span>
<span data-ttu-id="0e7e5-103">In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.DocumentViewer> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0e7e5-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span> <span data-ttu-id="0e7e5-104">Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement eine unverwechselbare Darstellung verleihen.</span><span class="sxs-lookup"><span data-stu-id="0e7e5-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="0e7e5-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="0e7e5-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="documentviewer-parts"></a><span data-ttu-id="0e7e5-106">DocumentViewer-Teile</span><span class="sxs-lookup"><span data-stu-id="0e7e5-106">DocumentViewer Parts</span></span>  
 <span data-ttu-id="0e7e5-107">Die folgende Tabelle enthält die benannten Teile für den <xref:System.Windows.Controls.DocumentViewer> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0e7e5-107">The following table lists the named parts for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="0e7e5-108">Segment</span><span class="sxs-lookup"><span data-stu-id="0e7e5-108">Part</span></span>|<span data-ttu-id="0e7e5-109">Typ</span><span class="sxs-lookup"><span data-stu-id="0e7e5-109">Type</span></span>|<span data-ttu-id="0e7e5-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e7e5-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="0e7e5-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="0e7e5-111">PART_ContentHost</span></span>|<xref:System.Windows.Controls.ScrollViewer>|<span data-ttu-id="0e7e5-112">Der Inhalt und scrollbereich.</span><span class="sxs-lookup"><span data-stu-id="0e7e5-112">The content and scrolling area.</span></span>|  
|<span data-ttu-id="0e7e5-113">PART_FindToolBarHost</span><span class="sxs-lookup"><span data-stu-id="0e7e5-113">PART_FindToolBarHost</span></span>|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="0e7e5-114">Das Suchfeld im unteren Bereich wird standardmäßig.</span><span class="sxs-lookup"><span data-stu-id="0e7e5-114">The search box, at the bottom by default.</span></span>|  
  
## <a name="documentviewer-states"></a><span data-ttu-id="0e7e5-115">DocumentViewer-Zustände</span><span class="sxs-lookup"><span data-stu-id="0e7e5-115">DocumentViewer States</span></span>  
 <span data-ttu-id="0e7e5-116">Die folgende Tabelle enthält die visuellen Zustände für die <xref:System.Windows.Controls.DocumentViewer> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0e7e5-116">The following table lists the visual states for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="0e7e5-117">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="0e7e5-117">VisualState Name</span></span>|<span data-ttu-id="0e7e5-118">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="0e7e5-118">VisualStateGroup Name</span></span>|<span data-ttu-id="0e7e5-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e7e5-119">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="0e7e5-120">Gültig</span><span class="sxs-lookup"><span data-stu-id="0e7e5-120">Valid</span></span>|<span data-ttu-id="0e7e5-121">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0e7e5-121">ValidationStates</span></span>|<span data-ttu-id="0e7e5-122">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="0e7e5-122">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="0e7e5-123">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="0e7e5-123">InvalidFocused</span></span>|<span data-ttu-id="0e7e5-124">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0e7e5-124">ValidationStates</span></span>|<span data-ttu-id="0e7e5-125">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="0e7e5-125">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="0e7e5-126">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="0e7e5-126">InvalidUnfocused</span></span>|<span data-ttu-id="0e7e5-127">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0e7e5-127">ValidationStates</span></span>|<span data-ttu-id="0e7e5-128">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement keinen Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="0e7e5-128">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="documentviewer-controltemplate-example"></a><span data-ttu-id="0e7e5-129">DocumentViewer-ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="0e7e5-129">DocumentViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="0e7e5-130">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.DocumentViewer> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0e7e5-130">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#DocumentViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/documentviewer.xaml#documentviewer)]  
  
 <span data-ttu-id="0e7e5-131">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="0e7e5-131">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="0e7e5-132">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="0e7e5-132">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e7e5-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0e7e5-133">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="0e7e5-134">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="0e7e5-134">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="0e7e5-135">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="0e7e5-135">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="0e7e5-136">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="0e7e5-136">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="0e7e5-137">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="0e7e5-137">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
