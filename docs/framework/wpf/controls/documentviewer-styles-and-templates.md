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
ms.openlocfilehash: 7a812ff913703e3aa8408da8a11d28ee5adfa7fd
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460348"
---
# <a name="documentviewer-styles-and-templates"></a><span data-ttu-id="b3941-102">DocumentViewer-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="b3941-102">DocumentViewer Styles and Templates</span></span>
<span data-ttu-id="b3941-103">In diesem Thema werden die Stile und Vorlagen für das <xref:System.Windows.Controls.DocumentViewer>-Steuerelement beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b3941-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span> <span data-ttu-id="b3941-104">Sie können die Standard <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement eine eindeutige Darstellung zu verschaffen.</span><span class="sxs-lookup"><span data-stu-id="b3941-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="b3941-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="b3941-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="documentviewer-parts"></a><span data-ttu-id="b3941-106">DocumentViewer-Teile</span><span class="sxs-lookup"><span data-stu-id="b3941-106">DocumentViewer Parts</span></span>  
 <span data-ttu-id="b3941-107">In der folgenden Tabelle sind die benannten Teile für das <xref:System.Windows.Controls.DocumentViewer>-Steuerelement aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="b3941-107">The following table lists the named parts for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="b3941-108">Segment</span><span class="sxs-lookup"><span data-stu-id="b3941-108">Part</span></span>|<span data-ttu-id="b3941-109">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="b3941-109">Type</span></span>|<span data-ttu-id="b3941-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b3941-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="b3941-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="b3941-111">PART_ContentHost</span></span>|<xref:System.Windows.Controls.ScrollViewer>|<span data-ttu-id="b3941-112">Der Inhalt und der scrollbereich.</span><span class="sxs-lookup"><span data-stu-id="b3941-112">The content and scrolling area.</span></span>|  
|<span data-ttu-id="b3941-113">PART_FindToolBarHost</span><span class="sxs-lookup"><span data-stu-id="b3941-113">PART_FindToolBarHost</span></span>|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="b3941-114">Das Suchfeld, das standardmäßig unten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b3941-114">The search box, at the bottom by default.</span></span>|  
  
## <a name="documentviewer-states"></a><span data-ttu-id="b3941-115">DocumentViewer-Zustände</span><span class="sxs-lookup"><span data-stu-id="b3941-115">DocumentViewer States</span></span>  
 <span data-ttu-id="b3941-116">In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Controls.DocumentViewer>-Steuerelement aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="b3941-116">The following table lists the visual states for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="b3941-117">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="b3941-117">VisualState Name</span></span>|<span data-ttu-id="b3941-118">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="b3941-118">VisualStateGroup Name</span></span>|<span data-ttu-id="b3941-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b3941-119">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="b3941-120">Gültig</span><span class="sxs-lookup"><span data-stu-id="b3941-120">Valid</span></span>|<span data-ttu-id="b3941-121">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b3941-121">ValidationStates</span></span>|<span data-ttu-id="b3941-122">Das-Steuerelement verwendet die <xref:System.Windows.Controls.Validation>-Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false`.</span><span class="sxs-lookup"><span data-stu-id="b3941-122">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="b3941-123">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="b3941-123">InvalidFocused</span></span>|<span data-ttu-id="b3941-124">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b3941-124">ValidationStates</span></span>|<span data-ttu-id="b3941-125">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true` hat, dass das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="b3941-125">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="b3941-126">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="b3941-126">InvalidUnfocused</span></span>|<span data-ttu-id="b3941-127">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b3941-127">ValidationStates</span></span>|<span data-ttu-id="b3941-128">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, wenn das Steuerelement keinen Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="b3941-128">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="documentviewer-controltemplate-example"></a><span data-ttu-id="b3941-129">DocumentViewer ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="b3941-129">DocumentViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="b3941-130">Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.ControlTemplate> für das <xref:System.Windows.Controls.DocumentViewer>-Steuerelement definiert wird.</span><span class="sxs-lookup"><span data-stu-id="b3941-130">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#DocumentViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/documentviewer.xaml#documentviewer)]  
  
 <span data-ttu-id="b3941-131">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="b3941-131">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="b3941-132">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="b3941-132">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3941-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b3941-133">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="b3941-134">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="b3941-134">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="b3941-135">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="b3941-135">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="b3941-136">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="b3941-136">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="b3941-137">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="b3941-137">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
