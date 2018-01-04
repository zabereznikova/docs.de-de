---
title: 'Gewusst wie: Erstellen einer Textdekoration'
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
- fonts [WPF], baseline
- text [WPF], decorations
- fonts [WPF], underline
- fonts [WPF], overline
- strikethrough type [WPF]
- fonts [WPF], strikethrough
- overline type [WPF]
- underline type [WPF]
- typography [WPF], text decorations
- baseline type [WPF]
ms.assetid: cf3cb4e7-782a-4be7-b2d4-e0935e21e4e0
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0beb22ba78c6fc99951bc2d780c1c5defa32e637
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-text-decoration"></a><span data-ttu-id="6d7d5-102">Gewusst wie: Erstellen einer Textdekoration</span><span class="sxs-lookup"><span data-stu-id="6d7d5-102">How to: Create a Text Decoration</span></span>
<span data-ttu-id="6d7d5-103">Ein <xref:System.Windows.TextDecoration> Objekt ist eine visuelle Verzierung können Sie Text hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6d7d5-103">A <xref:System.Windows.TextDecoration> object is a visual ornamentation you can add to text.</span></span> <span data-ttu-id="6d7d5-104">Es gibt vier Arten von Textdekorationen: "Unterstreichen", die Baseline, durchgestrichen und Überstrichen.</span><span class="sxs-lookup"><span data-stu-id="6d7d5-104">There are four types of text decorations: underline, baseline, strikethrough, and overline.</span></span> <span data-ttu-id="6d7d5-105">Das folgende Beispiel zeigt die Speicherorte der Textdekorationen relativ zu dem Text.</span><span class="sxs-lookup"><span data-stu-id="6d7d5-105">The following example shows the locations of the text decorations relative to the text.</span></span>  
  
 <span data-ttu-id="6d7d5-106">![Diagramm der Textergänzungsstellen](../../../../docs/framework/wpf/advanced/media/textdecoration01.gif "TextDecoration01")</span><span class="sxs-lookup"><span data-stu-id="6d7d5-106">![Diagram of text decoration locations](../../../../docs/framework/wpf/advanced/media/textdecoration01.gif "TextDecoration01")</span></span>  
<span data-ttu-id="6d7d5-107">Beispiel für die Text-Decoration-Typen</span><span class="sxs-lookup"><span data-stu-id="6d7d5-107">Example of text decoration types</span></span>  
  
 <span data-ttu-id="6d7d5-108">Ein Text-Decoration Text hinzufügen, erstellen Sie ein <xref:System.Windows.TextDecoration> -Objekt und dessen Eigenschaften ändern.</span><span class="sxs-lookup"><span data-stu-id="6d7d5-108">To add a text decoration to text, create a <xref:System.Windows.TextDecoration> object and modify its properties.</span></span> <span data-ttu-id="6d7d5-109">Verwenden der <xref:System.Windows.TextDecoration.Location%2A> Eigenschaft, um anzugeben, wo die Textdekoration angezeigt wird, z. B. "Unterstreichen".</span><span class="sxs-lookup"><span data-stu-id="6d7d5-109">Use the <xref:System.Windows.TextDecoration.Location%2A> property to specify where the text decoration appears, such as underline.</span></span> <span data-ttu-id="6d7d5-110">Verwenden der <xref:System.Windows.TextDecoration.Pen%2A> Eigenschaft, um die Darstellung der Textdekoration, z. B. einer einfarbigen Füllung oder Verlaufsfarbe anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6d7d5-110">Use the <xref:System.Windows.TextDecoration.Pen%2A> property to specify the appearance of the text decoration, such as a solid fill or gradient color.</span></span> <span data-ttu-id="6d7d5-111">Wenn Sie einen Wert für nicht angeben der <xref:System.Windows.TextDecoration.Pen%2A> -Eigenschaft, die standardmäßig Ergänzungen, die die gleiche Farbe wie der Text.</span><span class="sxs-lookup"><span data-stu-id="6d7d5-111">If you do not specify a value for the <xref:System.Windows.TextDecoration.Pen%2A> property, the decorations defaults to the same color as the text.</span></span> <span data-ttu-id="6d7d5-112">Sobald Sie definiert haben, eine <xref:System.Windows.TextDecoration> Objekt, fügen Sie diese der <xref:System.Windows.TextDecorations> Auflistung des gewünschten Text-Objekts.</span><span class="sxs-lookup"><span data-stu-id="6d7d5-112">Once you have defined a <xref:System.Windows.TextDecoration> object, add it to the <xref:System.Windows.TextDecorations> collection of the desired text object.</span></span>  
  
 <span data-ttu-id="6d7d5-113">Das folgende Beispiel zeigt einen Text-Decoration, die mit einem linearen Farbverlaufspinsel und einem gestrichelten Stift formatiert wurde.</span><span class="sxs-lookup"><span data-stu-id="6d7d5-113">The following example shows a text decoration that has been styled with a linear gradient brush and a dashed pen.</span></span>  
  
 <span data-ttu-id="6d7d5-114">![Textergänzung mit linearer farbverlaufsunterstreichung](../../../../docs/framework/wpf/advanced/media/textdecoration02.png "TextDecoration02")</span><span class="sxs-lookup"><span data-stu-id="6d7d5-114">![Text decoration with linear gradient underline](../../../../docs/framework/wpf/advanced/media/textdecoration02.png "TextDecoration02")</span></span>  
<span data-ttu-id="6d7d5-115">Beispiel einer Unterstreichung formatiert mit einem linearen Farbverlauf Pinsel und gestrichelt</span><span class="sxs-lookup"><span data-stu-id="6d7d5-115">Example of an underline styled with a linear gradient brush and dashed pen</span></span>  
  
 <span data-ttu-id="6d7d5-116">Die <xref:System.Windows.Documents.Hyperlink> Objekt ist ein Inhaltselement Inlineebene, der Ihnen das Hosten von links im fortlaufenden Inhalt ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="6d7d5-116">The <xref:System.Windows.Documents.Hyperlink> object is an inline-level flow content element that allows you to host hyperlinks within the flow content.</span></span> <span data-ttu-id="6d7d5-117">Standardmäßig <xref:System.Windows.Documents.Hyperlink> verwendet ein <xref:System.Windows.TextDecoration> Objekt, das eine Unterstreichung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6d7d5-117">By default, <xref:System.Windows.Documents.Hyperlink> uses a <xref:System.Windows.TextDecoration> object to display an underline.</span></span> <span data-ttu-id="6d7d5-118"><xref:System.Windows.TextDecoration>Objekte können ressourcenintensiv sein zu instanziieren, insbesondere, wenn Sie viele haben <xref:System.Windows.Documents.Hyperlink> Objekte.</span><span class="sxs-lookup"><span data-stu-id="6d7d5-118"><xref:System.Windows.TextDecoration> objects can be performance intensive to instantiate, particularly if you have many <xref:System.Windows.Documents.Hyperlink> objects.</span></span> <span data-ttu-id="6d7d5-119">Wenn Sie eine umfangreiche nutzen <xref:System.Windows.Documents.Hyperlink> Elemente, Sie sollten in Betracht ziehen einen Unterstrich nur, wenn ein Ereignis auslösen, z. B. Anzeigen der <xref:System.Windows.ContentElement.MouseEnter> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="6d7d5-119">If you make extensive use of <xref:System.Windows.Documents.Hyperlink> elements, you may want to consider showing an underline only when triggering an event, such as the <xref:System.Windows.ContentElement.MouseEnter> event.</span></span>  
  
 <span data-ttu-id="6d7d5-120">Im folgenden Beispiel wird die Unterstreichung für den Link "My MSN" dynamische – es wird nur angezeigt, wenn die <xref:System.Windows.ContentElement.MouseEnter> Ereignis wird ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="6d7d5-120">In the following example, the underline for the "My MSN" link is dynamic—it only appears when the <xref:System.Windows.ContentElement.MouseEnter> event is triggered.</span></span>  
  
 <span data-ttu-id="6d7d5-121">![Links mit TextDecorations](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")</span><span class="sxs-lookup"><span data-stu-id="6d7d5-121">![Hyperlinks displaying TextDecorations](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")</span></span>  
<span data-ttu-id="6d7d5-122">Links mit TextDecorations definiert</span><span class="sxs-lookup"><span data-stu-id="6d7d5-122">Hyperlinks defined with TextDecorations</span></span>  
  
 <span data-ttu-id="6d7d5-123">Weitere Informationen finden Sie unter [Specify Whether a Hyperlink is Underlined (Angeben, ob ein Link unterstrichen wird)](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md).</span><span class="sxs-lookup"><span data-stu-id="6d7d5-123">For more information, see [Specify Whether a Hyperlink is Underlined](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d7d5-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6d7d5-124">Example</span></span>  
 <span data-ttu-id="6d7d5-125">Im folgenden Codebeispiel wird ein "Unterstreichen" Text-Decoration den Standardwert für die Schriftart verwendet.</span><span class="sxs-lookup"><span data-stu-id="6d7d5-125">In the following code example, an underline text decoration uses the default font value.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets1)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets1)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets1)]  
  
 <span data-ttu-id="6d7d5-126">Im folgenden Codebeispiel wird ein "Unterstreichen" Text-Decoration mit einem Pinsel mit Volltonfarbe für den Stift erstellt.</span><span class="sxs-lookup"><span data-stu-id="6d7d5-126">In the following code example, an underline text decoration is created with a solid color brush for the pen.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets2)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets2)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets2)]  
  
 <span data-ttu-id="6d7d5-127">Im folgenden Codebeispiel wird ein "Unterstreichen" Text-Decoration mit einem linearen Farbverlaufspinsel für die gestrichelt erstellt.</span><span class="sxs-lookup"><span data-stu-id="6d7d5-127">In the following code example, an underline text decoration is created with a linear gradient brush for the dashed pen.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets3)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets3)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets3)]  
  
## <a name="see-also"></a><span data-ttu-id="6d7d5-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d7d5-128">See Also</span></span>  
 <xref:System.Windows.TextDecoration>  
 <xref:System.Windows.Documents.Hyperlink>  
 [<span data-ttu-id="6d7d5-129">Angeben, ob ein Hyperlink unterstrichen wird</span><span class="sxs-lookup"><span data-stu-id="6d7d5-129">Specify Whether a Hyperlink is Underlined</span></span>](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md)
