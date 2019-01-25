---
title: 'Vorgehensweise: Erstellen einer Textdekoration'
ms.date: 03/30/2017
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
ms.openlocfilehash: b85bbaed13d9406f85c62a9a5bc5ca220d90b0b2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54607945"
---
# <a name="how-to-create-a-text-decoration"></a><span data-ttu-id="716e3-102">Vorgehensweise: Erstellen einer Textdekoration</span><span class="sxs-lookup"><span data-stu-id="716e3-102">How to: Create a Text Decoration</span></span>
<span data-ttu-id="716e3-103">Ein <xref:System.Windows.TextDecoration> Objekt ist eine visuelle Verzierung, können Sie Text hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="716e3-103">A <xref:System.Windows.TextDecoration> object is a visual ornamentation you can add to text.</span></span> <span data-ttu-id="716e3-104">Es gibt vier Arten von Textdekorationen: Unterstreichung, Baseline, durchgestrichen und Überstrichen.</span><span class="sxs-lookup"><span data-stu-id="716e3-104">There are four types of text decorations: underline, baseline, strikethrough, and overline.</span></span> <span data-ttu-id="716e3-105">Das folgende Beispiel zeigt die Speicherorte der Textdekorationen relativ zum Text.</span><span class="sxs-lookup"><span data-stu-id="716e3-105">The following example shows the locations of the text decorations relative to the text.</span></span>  
  
 <span data-ttu-id="716e3-106">![Diagramm der Textergänzungsstellen](../../../../docs/framework/wpf/advanced/media/textdecoration01.gif "TextDecoration01")</span><span class="sxs-lookup"><span data-stu-id="716e3-106">![Diagram of text decoration locations](../../../../docs/framework/wpf/advanced/media/textdecoration01.gif "TextDecoration01")</span></span>  
<span data-ttu-id="716e3-107">Beispiel für Text-Decoration-Typen</span><span class="sxs-lookup"><span data-stu-id="716e3-107">Example of text decoration types</span></span>  
  
 <span data-ttu-id="716e3-108">Erstellen Sie zum Hinzufügen einer Textdekorations Text eine <xref:System.Windows.TextDecoration> Objekt, und ändern Sie seine Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="716e3-108">To add a text decoration to text, create a <xref:System.Windows.TextDecoration> object and modify its properties.</span></span> <span data-ttu-id="716e3-109">Verwenden der <xref:System.Windows.TextDecoration.Location%2A> Eigenschaft, um anzugeben, wo die Textdekoration angezeigt wird, z. B. unterstrichen.</span><span class="sxs-lookup"><span data-stu-id="716e3-109">Use the <xref:System.Windows.TextDecoration.Location%2A> property to specify where the text decoration appears, such as underline.</span></span> <span data-ttu-id="716e3-110">Verwenden der <xref:System.Windows.TextDecoration.Pen%2A> Eigenschaft, um die Darstellung der Textdekoration, z. B. eine durchgehende Füllung oder den Farbverlauf anzugeben.</span><span class="sxs-lookup"><span data-stu-id="716e3-110">Use the <xref:System.Windows.TextDecoration.Pen%2A> property to specify the appearance of the text decoration, such as a solid fill or gradient color.</span></span> <span data-ttu-id="716e3-111">Wenn Sie einen Wert für nicht angeben der <xref:System.Windows.TextDecoration.Pen%2A> die Dekorationen standardmäßig die gleiche Farbe wie der Text-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="716e3-111">If you do not specify a value for the <xref:System.Windows.TextDecoration.Pen%2A> property, the decorations defaults to the same color as the text.</span></span> <span data-ttu-id="716e3-112">Nachdem Sie definiert haben eine <xref:System.Windows.TextDecoration> Objekt, das Hinzufügen der <xref:System.Windows.TextDecorations> Auflistung mit den gewünschten Text-Objekt.</span><span class="sxs-lookup"><span data-stu-id="716e3-112">Once you have defined a <xref:System.Windows.TextDecoration> object, add it to the <xref:System.Windows.TextDecorations> collection of the desired text object.</span></span>  
  
 <span data-ttu-id="716e3-113">Das folgende Beispiel zeigt einen Text-Decoration, die mit einem linearen Farbverlaufspinsel und ein gestrichelten Stift formatiert wurde.</span><span class="sxs-lookup"><span data-stu-id="716e3-113">The following example shows a text decoration that has been styled with a linear gradient brush and a dashed pen.</span></span>  
  
 <span data-ttu-id="716e3-114">![Textergänzung mit linearer farbverlaufsunterstreichung](../../../../docs/framework/wpf/advanced/media/textdecoration02.png "TextDecoration02")</span><span class="sxs-lookup"><span data-stu-id="716e3-114">![Text decoration with linear gradient underline](../../../../docs/framework/wpf/advanced/media/textdecoration02.png "TextDecoration02")</span></span>  
<span data-ttu-id="716e3-115">Beispiel für eine Unterstreichung formatiert mit einem linearen Farbverlauf Pinsel und gestrichelten Stift</span><span class="sxs-lookup"><span data-stu-id="716e3-115">Example of an underline styled with a linear gradient brush and dashed pen</span></span>  
  
 <span data-ttu-id="716e3-116">Die <xref:System.Windows.Documents.Hyperlink> Objekt ist ein fortlaufendes Inhaltselement, das Ihnen das Hosten von links im fortlaufenden Inhalt ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="716e3-116">The <xref:System.Windows.Documents.Hyperlink> object is an inline-level flow content element that allows you to host hyperlinks within the flow content.</span></span> <span data-ttu-id="716e3-117">In der Standardeinstellung <xref:System.Windows.Documents.Hyperlink> verwendet eine <xref:System.Windows.TextDecoration> Objekt, das eine Unterstreichung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="716e3-117">By default, <xref:System.Windows.Documents.Hyperlink> uses a <xref:System.Windows.TextDecoration> object to display an underline.</span></span> <span data-ttu-id="716e3-118"><xref:System.Windows.TextDecoration> Objekte können ressourcenintensiv sein, zu instanziieren, insbesondere wenn Sie viele <xref:System.Windows.Documents.Hyperlink> Objekte.</span><span class="sxs-lookup"><span data-stu-id="716e3-118"><xref:System.Windows.TextDecoration> objects can be performance intensive to instantiate, particularly if you have many <xref:System.Windows.Documents.Hyperlink> objects.</span></span> <span data-ttu-id="716e3-119">Wenn Sie umfassenden Gebrauch von machen <xref:System.Windows.Documents.Hyperlink> Elemente, Sie möchten könnten eine Unterstreichung nur, wenn ein Ereignis auslösen, z. B. die <xref:System.Windows.ContentElement.MouseEnter> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="716e3-119">If you make extensive use of <xref:System.Windows.Documents.Hyperlink> elements, you may want to consider showing an underline only when triggering an event, such as the <xref:System.Windows.ContentElement.MouseEnter> event.</span></span>  
  
 <span data-ttu-id="716e3-120">Im folgenden Beispiel wird die Unterstreichung für den Link "Meine MSN" dynamische – es nur angezeigt, wenn die <xref:System.Windows.ContentElement.MouseEnter> Ereignis wird ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="716e3-120">In the following example, the underline for the "My MSN" link is dynamic—it only appears when the <xref:System.Windows.ContentElement.MouseEnter> event is triggered.</span></span>  
  
 <span data-ttu-id="716e3-121">![Links mit TextDecorations](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")</span><span class="sxs-lookup"><span data-stu-id="716e3-121">![Hyperlinks displaying TextDecorations](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")</span></span>  
<span data-ttu-id="716e3-122">Links mit TextDecorations definiert</span><span class="sxs-lookup"><span data-stu-id="716e3-122">Hyperlinks defined with TextDecorations</span></span>  
  
 <span data-ttu-id="716e3-123">Weitere Informationen finden Sie unter [Specify Whether a Hyperlink is Underlined (Angeben, ob ein Link unterstrichen wird)](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md).</span><span class="sxs-lookup"><span data-stu-id="716e3-123">For more information, see [Specify Whether a Hyperlink is Underlined](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="716e3-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="716e3-124">Example</span></span>  
 <span data-ttu-id="716e3-125">Im folgenden Codebeispiel verwendet eine Textdekoration "Unterstreichen" den Standardwert für die Schriftart.</span><span class="sxs-lookup"><span data-stu-id="716e3-125">In the following code example, an underline text decoration uses the default font value.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets1)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets1)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets1)]  
  
 <span data-ttu-id="716e3-126">Im folgenden Codebeispiel wird eine Unterstreichung Textdekoration mit Pinsel mit Volltonfarbe für den Stift erstellt.</span><span class="sxs-lookup"><span data-stu-id="716e3-126">In the following code example, an underline text decoration is created with a solid color brush for the pen.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets2)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets2)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets2)]  
  
 <span data-ttu-id="716e3-127">Das folgende Codebeispiel zeigt wird ein "Unterstreichen" Text-Decoration mit einem linearen Farbverlaufspinsel für den Stift gestrichelte erstellt.</span><span class="sxs-lookup"><span data-stu-id="716e3-127">In the following code example, an underline text decoration is created with a linear gradient brush for the dashed pen.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets3)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets3)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets3)]  
  
## <a name="see-also"></a><span data-ttu-id="716e3-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="716e3-128">See also</span></span>
- <xref:System.Windows.TextDecoration>
- <xref:System.Windows.Documents.Hyperlink>
- [<span data-ttu-id="716e3-129">Angeben, ob ein Hyperlink unterstrichen wird</span><span class="sxs-lookup"><span data-stu-id="716e3-129">Specify Whether a Hyperlink is Underlined</span></span>](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md)
