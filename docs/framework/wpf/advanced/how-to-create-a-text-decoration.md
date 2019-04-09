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
ms.openlocfilehash: d586eef8d1308070da38a0a54c63c3ba64d30c8b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59133834"
---
# <a name="how-to-create-a-text-decoration"></a><span data-ttu-id="74124-102">Vorgehensweise: Erstellen einer Textdekoration</span><span class="sxs-lookup"><span data-stu-id="74124-102">How to: Create a Text Decoration</span></span>
<span data-ttu-id="74124-103">Ein <xref:System.Windows.TextDecoration> Objekt ist eine visuelle Verzierung, können Sie Text hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="74124-103">A <xref:System.Windows.TextDecoration> object is a visual ornamentation you can add to text.</span></span> <span data-ttu-id="74124-104">Es gibt vier Arten von Textdekorationen: Unterstreichung, Baseline, durchgestrichen und Überstrichen.</span><span class="sxs-lookup"><span data-stu-id="74124-104">There are four types of text decorations: underline, baseline, strikethrough, and overline.</span></span> <span data-ttu-id="74124-105">Das folgende Beispiel zeigt die Speicherorte der Textdekorationen relativ zum Text.</span><span class="sxs-lookup"><span data-stu-id="74124-105">The following example shows the locations of the text decorations relative to the text.</span></span>  
  
 ![Diagramm der Text-Decoration-Typen](./media/how-to-create-a-text-decoration/text-decoration-types.gif)  
  
 <span data-ttu-id="74124-107">Erstellen Sie zum Hinzufügen einer Textdekorations Text eine <xref:System.Windows.TextDecoration> Objekt, und ändern Sie seine Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="74124-107">To add a text decoration to text, create a <xref:System.Windows.TextDecoration> object and modify its properties.</span></span> <span data-ttu-id="74124-108">Verwenden der <xref:System.Windows.TextDecoration.Location%2A> Eigenschaft, um anzugeben, wo die Textdekoration angezeigt wird, z. B. unterstrichen.</span><span class="sxs-lookup"><span data-stu-id="74124-108">Use the <xref:System.Windows.TextDecoration.Location%2A> property to specify where the text decoration appears, such as underline.</span></span> <span data-ttu-id="74124-109">Verwenden der <xref:System.Windows.TextDecoration.Pen%2A> Eigenschaft, um die Darstellung der Textdekoration, z. B. eine durchgehende Füllung oder den Farbverlauf anzugeben.</span><span class="sxs-lookup"><span data-stu-id="74124-109">Use the <xref:System.Windows.TextDecoration.Pen%2A> property to specify the appearance of the text decoration, such as a solid fill or gradient color.</span></span> <span data-ttu-id="74124-110">Wenn Sie einen Wert für nicht angeben der <xref:System.Windows.TextDecoration.Pen%2A> die Dekorationen standardmäßig die gleiche Farbe wie der Text-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="74124-110">If you do not specify a value for the <xref:System.Windows.TextDecoration.Pen%2A> property, the decorations defaults to the same color as the text.</span></span> <span data-ttu-id="74124-111">Nachdem Sie definiert haben eine <xref:System.Windows.TextDecoration> Objekt, das Hinzufügen der <xref:System.Windows.TextDecorations> Auflistung mit den gewünschten Text-Objekt.</span><span class="sxs-lookup"><span data-stu-id="74124-111">Once you have defined a <xref:System.Windows.TextDecoration> object, add it to the <xref:System.Windows.TextDecorations> collection of the desired text object.</span></span>  
  
 <span data-ttu-id="74124-112">Das folgende Beispiel zeigt einen Text-Decoration, die mit einem linearen Farbverlaufspinsel und ein gestrichelten Stift formatiert wurde.</span><span class="sxs-lookup"><span data-stu-id="74124-112">The following example shows a text decoration that has been styled with a linear gradient brush and a dashed pen.</span></span>  
  
 ![Textergänzung mit linearer Farbverlaufsunterstreichung](./media/how-to-create-a-text-decoration/text-decoration-gradient.png)  
  
 <span data-ttu-id="74124-114">Die <xref:System.Windows.Documents.Hyperlink> Objekt ist ein fortlaufendes Inhaltselement, das Ihnen das Hosten von links im fortlaufenden Inhalt ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="74124-114">The <xref:System.Windows.Documents.Hyperlink> object is an inline-level flow content element that allows you to host hyperlinks within the flow content.</span></span> <span data-ttu-id="74124-115">In der Standardeinstellung <xref:System.Windows.Documents.Hyperlink> verwendet eine <xref:System.Windows.TextDecoration> Objekt, das eine Unterstreichung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="74124-115">By default, <xref:System.Windows.Documents.Hyperlink> uses a <xref:System.Windows.TextDecoration> object to display an underline.</span></span> <xref:System.Windows.TextDecoration> <span data-ttu-id="74124-116">Objekte können ressourcenintensiv sein, zu instanziieren, insbesondere wenn Sie viele <xref:System.Windows.Documents.Hyperlink> Objekte.</span><span class="sxs-lookup"><span data-stu-id="74124-116">objects can be performance intensive to instantiate, particularly if you have many <xref:System.Windows.Documents.Hyperlink> objects.</span></span> <span data-ttu-id="74124-117">Wenn Sie umfassenden Gebrauch von machen <xref:System.Windows.Documents.Hyperlink> Elemente, Sie möchten könnten eine Unterstreichung nur, wenn ein Ereignis auslösen, z. B. die <xref:System.Windows.ContentElement.MouseEnter> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="74124-117">If you make extensive use of <xref:System.Windows.Documents.Hyperlink> elements, you may want to consider showing an underline only when triggering an event, such as the <xref:System.Windows.ContentElement.MouseEnter> event.</span></span>  
  
 <span data-ttu-id="74124-118">Im folgenden Beispiel wird die Unterstreichung für den Link "Meine MSN" dynamische – es nur angezeigt, wenn die <xref:System.Windows.ContentElement.MouseEnter> Ereignis wird ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="74124-118">In the following example, the underline for the "My MSN" link is dynamic—it only appears when the <xref:System.Windows.ContentElement.MouseEnter> event is triggered.</span></span>  
  
 ![Links mit TextDecorations](./media/how-to-create-a-text-decoration/text-decorations-hyperlinks.png)  
   
 <span data-ttu-id="74124-120">Weitere Informationen finden Sie unter [Specify Whether a Hyperlink is Underlined (Angeben, ob ein Link unterstrichen wird)](how-to-specify-whether-a-hyperlink-is-underlined.md).</span><span class="sxs-lookup"><span data-stu-id="74124-120">For more information, see [Specify Whether a Hyperlink is Underlined](how-to-specify-whether-a-hyperlink-is-underlined.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="74124-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="74124-121">Example</span></span>  
 <span data-ttu-id="74124-122">Im folgenden Codebeispiel verwendet eine Textdekoration "Unterstreichen" den Standardwert für die Schriftart.</span><span class="sxs-lookup"><span data-stu-id="74124-122">In the following code example, an underline text decoration uses the default font value.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets1)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets1)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets1)]  
  
 <span data-ttu-id="74124-123">Im folgenden Codebeispiel wird eine Unterstreichung Textdekoration mit Pinsel mit Volltonfarbe für den Stift erstellt.</span><span class="sxs-lookup"><span data-stu-id="74124-123">In the following code example, an underline text decoration is created with a solid color brush for the pen.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets2)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets2)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets2)]  
  
 <span data-ttu-id="74124-124">Das folgende Codebeispiel zeigt wird ein "Unterstreichen" Text-Decoration mit einem linearen Farbverlaufspinsel für den Stift gestrichelte erstellt.</span><span class="sxs-lookup"><span data-stu-id="74124-124">In the following code example, an underline text decoration is created with a linear gradient brush for the dashed pen.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets3)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets3)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets3)]  
  
## <a name="see-also"></a><span data-ttu-id="74124-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74124-125">See also</span></span>

- <xref:System.Windows.TextDecoration>
- <xref:System.Windows.Documents.Hyperlink>
- [<span data-ttu-id="74124-126">Angeben, ob ein Hyperlink unterstrichen wird</span><span class="sxs-lookup"><span data-stu-id="74124-126">Specify Whether a Hyperlink is Underlined</span></span>](how-to-specify-whether-a-hyperlink-is-underlined.md)
