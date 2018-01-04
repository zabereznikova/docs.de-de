---
title: "Übersicht über die QuickInfo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolTip control [WPF], about ToolTip control
- controls [WPF], ToolTip
ms.assetid: f06c1603-e9cb-4809-8a62-234607fc52f7
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a3dee3d94063a94869869a9d94ab3cc2bc0a26fb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="tooltip-overview"></a><span data-ttu-id="9c6ac-102">Übersicht über die QuickInfo</span><span class="sxs-lookup"><span data-stu-id="9c6ac-102">ToolTip Overview</span></span>
<span data-ttu-id="9c6ac-103">Eine QuickInfo ist ein kleines Popupfenster, das angezeigt wird, wenn ein Benutzer den Mauszeiger über ein Element, z. B. über hält eine <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="9c6ac-103">A tooltip is a small pop-up window that appears when a user pauses the mouse pointer over an element, such as over a <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="9c6ac-104">In diesem Thema wird die QuickInfo vorgestellt und das Erstellen und Anpassen von QuickInfo-Inhalten erläutert.</span><span class="sxs-lookup"><span data-stu-id="9c6ac-104">This topic introduces the tooltip and discusses how to create and customize tooltip content.</span></span>  
  
 
  
<a name="what_is_a_tooltip"></a>   
## <a name="what-is-a-tooltip"></a><span data-ttu-id="9c6ac-105">Was ist eine QuickInfo?</span><span class="sxs-lookup"><span data-stu-id="9c6ac-105">What Is a Tooltip?</span></span>  
 <span data-ttu-id="9c6ac-106">Wenn ein Benutzer den Mauszeiger über ein Element mit einer QuickInfo bewegt, wird für einen festgelegten Zeitraum ein Fenster mit dem Inhalt dieser QuickInfo angezeigt. Dabei kann es sich z.B. um Text handeln, der die Funktion eines Steuerelements beschreibt.</span><span class="sxs-lookup"><span data-stu-id="9c6ac-106">When a user moves the mouse pointer over an element that has a tooltip, a window that contains tooltip content (for example, text content that describes the function of a control) appears for a specified amount of time.</span></span> <span data-ttu-id="9c6ac-107">Wenn der Benutzer den Mauszeiger vom Steuerelement wegbewegt, wird das Fenster nicht mehr angezeigt, da der Inhalt der QuickInfo keinen Fokus erhalten kann.</span><span class="sxs-lookup"><span data-stu-id="9c6ac-107">If the user moves the mouse pointer away from the control, the window disappears because the tooltip content cannot receive focus.</span></span>  
  
 <span data-ttu-id="9c6ac-108">Der Inhalt einer QuickInfo kann eine oder mehrere Zeilen Text, Bilder, Formen oder andere visuelle Inhalte enthalten.</span><span class="sxs-lookup"><span data-stu-id="9c6ac-108">The content of a tooltip can contain one or more lines of text, images, shapes, or other visual content.</span></span> <span data-ttu-id="9c6ac-109">Um eine QuickInfo für ein Steuerelement zu definieren, legen Sie für deren Inhalt eine der folgenden Eigenschaften fest.</span><span class="sxs-lookup"><span data-stu-id="9c6ac-109">You define a tooltip for a control by setting one of the following properties to the tooltip content.</span></span>  
  
-   <xref:System.Windows.FrameworkContentElement.ToolTip%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="9c6ac-110">Die Eigenschaft, die Sie verwenden, hängt davon ab, ob das Steuerelement, das die QuickInfo definiert erbt die <xref:System.Windows.FrameworkContentElement> oder <xref:System.Windows.FrameworkElement> Klasse.</span><span class="sxs-lookup"><span data-stu-id="9c6ac-110">Which property you use depends on whether the control that defines the tooltip inherits from the <xref:System.Windows.FrameworkContentElement> or <xref:System.Windows.FrameworkElement> class.</span></span>  
  
<a name="create_tooltip"></a>   
## <a name="creating-a-tooltip"></a><span data-ttu-id="9c6ac-111">Erstellen einer QuickInfo</span><span class="sxs-lookup"><span data-stu-id="9c6ac-111">Creating a ToolTip</span></span>  
 <span data-ttu-id="9c6ac-112">Im folgende Beispiel wird gezeigt, wie zum Erstellen einer einfachen QuickInfo durch Festlegen der <xref:System.Windows.FrameworkElement.ToolTip%2A> -Eigenschaft für eine <xref:System.Windows.Controls.Button> Steuerelement in eine Textzeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="9c6ac-112">The following example shows how to create a simple tooltip by setting the <xref:System.Windows.FrameworkElement.ToolTip%2A> property for a <xref:System.Windows.Controls.Button> control to a text string.</span></span>  
  
 [!code-xaml[GroupBoxSnippet#ToolTipString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#tooltipstring)]  
  
 <span data-ttu-id="9c6ac-113">Sie können auch eine QuickInfo als definieren eine <xref:System.Windows.Controls.ToolTip> Objekt.</span><span class="sxs-lookup"><span data-stu-id="9c6ac-113">You can also define a tooltip as a <xref:System.Windows.Controls.ToolTip> object.</span></span> <span data-ttu-id="9c6ac-114">Im folgenden Beispiel wird [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] an eine <xref:System.Windows.Controls.ToolTip> Objekt als die QuickInfo eines ein <xref:System.Windows.Controls.TextBox> Element.</span><span class="sxs-lookup"><span data-stu-id="9c6ac-114">The following example uses [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] to specify a <xref:System.Windows.Controls.ToolTip> object as the tooltip of a <xref:System.Windows.Controls.TextBox> element.</span></span> <span data-ttu-id="9c6ac-115">Beachten Sie, die im Beispiel wird die <xref:System.Windows.Controls.ToolTip> durch Festlegen der <xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=nameWithType> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="9c6ac-115">Note that the example specifies the <xref:System.Windows.Controls.ToolTip> by setting the <xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=nameWithType> property.</span></span>  
  
 [!code-xaml[ToolTipSimple#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml#tooltip)]  
  
 <span data-ttu-id="9c6ac-116">Im folgenden Beispiel wird Code zum Generieren einer <xref:System.Windows.Controls.ToolTip> Objekt.</span><span class="sxs-lookup"><span data-stu-id="9c6ac-116">The following example uses code to generate a <xref:System.Windows.Controls.ToolTip> object.</span></span> <span data-ttu-id="9c6ac-117">Das Beispiel erstellt eine <xref:System.Windows.Controls.ToolTip> (`tt`) und ordnet sie einer <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="9c6ac-117">The example creates a <xref:System.Windows.Controls.ToolTip> (`tt`) and associates it with a <xref:System.Windows.Controls.Button>.</span></span>  
  
 [!code-csharp[ToolTipSimple#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ToolTipSimple#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipSimple/VisualBasic/Window1.xaml.vb#2)]  
  
 <span data-ttu-id="9c6ac-118">Sie können auch nicht als definierten QuickInfo-Inhalt erstellen eine <xref:System.Windows.Controls.ToolTip> Objekt vom einschließenden des QuickInfo-Inhalts in einem Layoutelement, z. B. eine <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="9c6ac-118">You can also create tooltip content that is not defined as a <xref:System.Windows.Controls.ToolTip> object by enclosing the tooltip content in a layout element, such as a <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="9c6ac-119">Das folgende Beispiel zeigt, wie Sie festlegen der <xref:System.Windows.FrameworkElement.ToolTip%2A> Eigenschaft eine <xref:System.Windows.Controls.TextBox> auf Inhalte, die in eingeschlossen ist ein <xref:System.Windows.Controls.DockPanel> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="9c6ac-119">The following example shows how to set the <xref:System.Windows.FrameworkElement.ToolTip%2A> property of a <xref:System.Windows.Controls.TextBox> to content that is enclosed in a <xref:System.Windows.Controls.DockPanel> control.</span></span>  
  
 [!code-xaml[GroupBoxSnippet#ToolTipDockPanel](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#tooltipdockpanel)]  
  
<a name="Using_the_ToolTip_and_ToolTipService_Properties"></a>   
## <a name="using-the-properties-of-the-tooltip-and-tooltipservice-classes"></a><span data-ttu-id="9c6ac-120">Verwenden der Eigenschaften der Klassen ToolTip und ToolTipService</span><span class="sxs-lookup"><span data-stu-id="9c6ac-120">Using the Properties of the ToolTip and ToolTipService Classes</span></span>  
 <span data-ttu-id="9c6ac-121">Sie können den Inhalt einer QuickInfo anpassen, indem Sie Eigenschaften für das Erscheinungsbild festlegen und Stile anwenden.</span><span class="sxs-lookup"><span data-stu-id="9c6ac-121">You can customize tooltip content by setting visual properties and applying styles.</span></span> <span data-ttu-id="9c6ac-122">Wenn Sie den Inhalt als QuickInfo definieren eine <xref:System.Windows.Controls.ToolTip> -Objekt können Sie die visuellen Eigenschaften des Festlegen der <xref:System.Windows.Controls.ToolTip> Objekt.</span><span class="sxs-lookup"><span data-stu-id="9c6ac-122">If you define the tooltip content as a <xref:System.Windows.Controls.ToolTip> object, you can set the visual properties of the <xref:System.Windows.Controls.ToolTip> object.</span></span> <span data-ttu-id="9c6ac-123">Andernfalls müssen Sie entsprechende angefügte Eigenschaften festlegen, auf die <xref:System.Windows.Controls.ToolTipService> Klasse.</span><span class="sxs-lookup"><span data-stu-id="9c6ac-123">Otherwise, you must set equivalent attached properties on the <xref:System.Windows.Controls.ToolTipService> class.</span></span>  
  
 <span data-ttu-id="9c6ac-124">Ein Beispiel zum Festlegen von Eigenschaften, um die Position des QuickInfo-Inhalte mithilfe von angeben der <xref:System.Windows.Controls.ToolTip> und <xref:System.Windows.Controls.ToolTipService> Eigenschaften finden Sie in [platzieren eine QuickInfo](../../../../docs/framework/wpf/controls/how-to-position-a-tooltip.md).</span><span class="sxs-lookup"><span data-stu-id="9c6ac-124">For an example of how to set properties in order to specify the position of tooltip content by using the <xref:System.Windows.Controls.ToolTip> and <xref:System.Windows.Controls.ToolTipService> properties, see [Position a ToolTip](../../../../docs/framework/wpf/controls/how-to-position-a-tooltip.md).</span></span>  
  
<a name="StylingToolTip"></a>   
## <a name="styling-a-tooltip"></a><span data-ttu-id="9c6ac-125">Formatieren einer QuickInfo</span><span class="sxs-lookup"><span data-stu-id="9c6ac-125">Styling a ToolTip</span></span>  
 <span data-ttu-id="9c6ac-126">Sie können Formatieren einer <xref:System.Windows.Controls.ToolTip> durch Definieren einer benutzerdefiniertes <xref:System.Windows.Style>.</span><span class="sxs-lookup"><span data-stu-id="9c6ac-126">You can style a <xref:System.Windows.Controls.ToolTip> by defining a custom <xref:System.Windows.Style>.</span></span> <span data-ttu-id="9c6ac-127">Das folgende Beispiel definiert eine <xref:System.Windows.Style> aufgerufen `Simple` veranschaulicht, wie die Platzierung der offset der <xref:System.Windows.Controls.ToolTip> und ändern Sie seine Darstellung durch Festlegen der <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>, <xref:System.Windows.Controls.Control.FontSize%2A>, und <xref:System.Windows.Controls.Control.FontWeight%2A>.</span><span class="sxs-lookup"><span data-stu-id="9c6ac-127">The following example defines a <xref:System.Windows.Style> called `Simple` that shows how to offset the placement of the <xref:System.Windows.Controls.ToolTip> and change its appearance by setting the <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>, <xref:System.Windows.Controls.Control.FontSize%2A>, and <xref:System.Windows.Controls.Control.FontWeight%2A>.</span></span>  
  
 [!code-xaml[ToolTipSimple#Style](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml#style)]  
  
<a name="UsingtheToolTipServiceTimeIntervalProperties"></a>   
## <a name="using-the-time-interval-properties-of-tooltipservice"></a><span data-ttu-id="9c6ac-128">Verwenden der Eigenschaften von ToolTipService für Zeitintervalle</span><span class="sxs-lookup"><span data-stu-id="9c6ac-128">Using the Time Interval Properties of ToolTipService</span></span>  
 <span data-ttu-id="9c6ac-129">Die <xref:System.Windows.Controls.ToolTipService> Klasse enthält die folgenden Eigenschaften zum Festlegen der QuickInfo anzuzeigen, wie oft: <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A>, <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A>, und <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A>.</span><span class="sxs-lookup"><span data-stu-id="9c6ac-129">The <xref:System.Windows.Controls.ToolTipService> class provides the following properties for you to set tooltip display times: <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A>, <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A>, and <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A>.</span></span>  
  
 <span data-ttu-id="9c6ac-130">Verwenden der <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> und <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A> Eigenschaften zur Angabe einer Verzögerung in der Regel eine kurze, bevor eine <xref:System.Windows.Controls.ToolTip> angezeigt wird und auch, um anzugeben, wie lange eine <xref:System.Windows.Controls.ToolTip> weiterhin angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9c6ac-130">Use the <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> and <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A> properties to specify a delay, typically brief, before a <xref:System.Windows.Controls.ToolTip> appears and also to specify how long a <xref:System.Windows.Controls.ToolTip> remains visible.</span></span> <span data-ttu-id="9c6ac-131">Weitere Informationen finden Sie unter [Vorgehensweise: Verzögern der Anzeige einer QuickInfo](http://msdn.microsoft.com/en-us/618e05ef-f2bf-4a53-a0f4-aacb49918bd7).</span><span class="sxs-lookup"><span data-stu-id="9c6ac-131">For more information, see [How to: Delay the Display of a ToolTip](http://msdn.microsoft.com/en-us/618e05ef-f2bf-4a53-a0f4-aacb49918bd7).</span></span>  
  
 <span data-ttu-id="9c6ac-132">Die <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> Eigenschaft bestimmt, ob QuickInfos für verschiedene Steuerelemente ohne eine Verzögerung angezeigt, wenn Sie den Mauszeiger schnell dazwischen verschieben.</span><span class="sxs-lookup"><span data-stu-id="9c6ac-132">The <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> property determines if tooltips for different controls appear without an initial delay when you move the mouse pointer quickly between them.</span></span> <span data-ttu-id="9c6ac-133">Weitere Informationen zu den <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> -Eigenschaft, finden Sie unter [verwenden Sie die Eigenschaft BetweenShowDelay](../../../../docs/framework/wpf/controls/how-to-use-the-betweenshowdelay-property.md).</span><span class="sxs-lookup"><span data-stu-id="9c6ac-133">For more information about the <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> property, see [Use the BetweenShowDelay Property](../../../../docs/framework/wpf/controls/how-to-use-the-betweenshowdelay-property.md).</span></span>  
  
 <span data-ttu-id="9c6ac-134">Das nachstehende Beispiel zeigt, wie Sie diese Eigenschaften für eine QuickInfo festlegen.</span><span class="sxs-lookup"><span data-stu-id="9c6ac-134">The following example shows how to set these properties for a tooltip.</span></span>  
  
 [!code-xaml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
## <a name="see-also"></a><span data-ttu-id="9c6ac-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c6ac-135">See Also</span></span>  
 <xref:System.Windows.Controls.ToolTipService>  
 <xref:System.Windows.Controls.ToolTip>  
 <xref:System.Windows.Controls.ToolTipEventArgs>  
 <xref:System.Windows.Controls.ToolTipEventHandler>  
 [<span data-ttu-id="9c6ac-136">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="9c6ac-136">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)
