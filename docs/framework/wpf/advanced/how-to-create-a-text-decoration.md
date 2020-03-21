---
title: 'Gewusst wie: Erstellen einer Textdekoration'
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
ms.openlocfilehash: cf3b3c3bcb75153a0be4f7ced03b38134b79a930
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185922"
---
# <a name="how-to-create-a-text-decoration"></a><span data-ttu-id="ca8b4-102">Gewusst wie: Erstellen einer Textdekoration</span><span class="sxs-lookup"><span data-stu-id="ca8b4-102">How to: Create a Text Decoration</span></span>
<span data-ttu-id="ca8b4-103">Ein <xref:System.Windows.TextDecoration> Objekt ist eine visuelle Verzierung, die Sie dem Text hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-103">A <xref:System.Windows.TextDecoration> object is a visual ornamentation you can add to text.</span></span> <span data-ttu-id="ca8b4-104">Es gibt vier Arten von Textdekorationen: Unterstreichung, Baseline, Durchstreichen und Überlinie.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-104">There are four types of text decorations: underline, baseline, strikethrough, and overline.</span></span> <span data-ttu-id="ca8b4-105">Das folgende Beispiel zeigt die Positionen der Textdekorationen relativ zum Text.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-105">The following example shows the locations of the text decorations relative to the text.</span></span>  
  
 ![Diagramm der Textdekorationstypen](./media/how-to-create-a-text-decoration/text-decoration-types.gif)  
  
 <span data-ttu-id="ca8b4-107">Um Text eine Textdekoration hinzuzufügen, erstellen Sie ein <xref:System.Windows.TextDecoration> Objekt, und ändern Sie dessen Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-107">To add a text decoration to text, create a <xref:System.Windows.TextDecoration> object and modify its properties.</span></span> <span data-ttu-id="ca8b4-108">Verwenden <xref:System.Windows.TextDecoration.Location%2A> Sie die Eigenschaft, um anzugeben, wo die Textdekoration angezeigt wird, z. B. unterstreichen.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-108">Use the <xref:System.Windows.TextDecoration.Location%2A> property to specify where the text decoration appears, such as underline.</span></span> <span data-ttu-id="ca8b4-109">Verwenden <xref:System.Windows.TextDecoration.Pen%2A> Sie die Eigenschaft, um die Darstellung der Textdekoration anzugeben, z. B. eine Volumenkörperfüllung oder Farbverlaufsfarbe.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-109">Use the <xref:System.Windows.TextDecoration.Pen%2A> property to specify the appearance of the text decoration, such as a solid fill or gradient color.</span></span> <span data-ttu-id="ca8b4-110">Wenn Sie keinen Wert für <xref:System.Windows.TextDecoration.Pen%2A> die Eigenschaft angeben, werden die Dekorationen standardmäßig auf die gleiche Farbe wie der Text festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-110">If you do not specify a value for the <xref:System.Windows.TextDecoration.Pen%2A> property, the decorations defaults to the same color as the text.</span></span> <span data-ttu-id="ca8b4-111">Nachdem Sie ein <xref:System.Windows.TextDecoration> Objekt definiert haben, fügen Sie es der <xref:System.Windows.TextDecorations> Auflistung des gewünschten Textobjekts hinzu.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-111">Once you have defined a <xref:System.Windows.TextDecoration> object, add it to the <xref:System.Windows.TextDecorations> collection of the desired text object.</span></span>  
  
 <span data-ttu-id="ca8b4-112">Das folgende Beispiel zeigt eine Textdekoration, die mit einem linearen Farbverlaufspinsel und einem gestrichelten Stift formatiert wurde.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-112">The following example shows a text decoration that has been styled with a linear gradient brush and a dashed pen.</span></span>  
  
 ![Textergänzung mit linearer Farbverlaufsunterstreichung](./media/how-to-create-a-text-decoration/text-decoration-gradient.png)  
  
 <span data-ttu-id="ca8b4-114">Das <xref:System.Windows.Documents.Hyperlink> Objekt ist ein Flow-Inhaltselement auf Inlineebene, mit dem Sie Hyperlinks innerhalb des Flow-Inhalts hosten können.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-114">The <xref:System.Windows.Documents.Hyperlink> object is an inline-level flow content element that allows you to host hyperlinks within the flow content.</span></span> <span data-ttu-id="ca8b4-115">Verwendet standardmäßig <xref:System.Windows.Documents.Hyperlink> ein <xref:System.Windows.TextDecoration> Objekt, um eine Unterstreichung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-115">By default, <xref:System.Windows.Documents.Hyperlink> uses a <xref:System.Windows.TextDecoration> object to display an underline.</span></span> <span data-ttu-id="ca8b4-116"><xref:System.Windows.TextDecoration>Objekte können leistungsintensiv zu instanziieren sein, <xref:System.Windows.Documents.Hyperlink> insbesondere wenn Sie viele Objekte haben.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-116"><xref:System.Windows.TextDecoration> objects can be performance intensive to instantiate, particularly if you have many <xref:System.Windows.Documents.Hyperlink> objects.</span></span> <span data-ttu-id="ca8b4-117">Wenn Sie <xref:System.Windows.Documents.Hyperlink> Elemente ausgiebig verwenden, sollten Sie nur beim Auslösen eines Ereignisses, <xref:System.Windows.ContentElement.MouseEnter> z. B. des Ereignisses, eine Unterstreichung anzeigen.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-117">If you make extensive use of <xref:System.Windows.Documents.Hyperlink> elements, you may want to consider showing an underline only when triggering an event, such as the <xref:System.Windows.ContentElement.MouseEnter> event.</span></span>  
  
 <span data-ttu-id="ca8b4-118">Im folgenden Beispiel ist die Unterstreichung für die Verknüpfung "Mein MSN" dynamisch – sie wird nur angezeigt, wenn das <xref:System.Windows.ContentElement.MouseEnter> Ereignis ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-118">In the following example, the underline for the "My MSN" link is dynamic—it only appears when the <xref:System.Windows.ContentElement.MouseEnter> event is triggered.</span></span>  
  
 ![Links mit TextDecorations](./media/how-to-create-a-text-decoration/text-decorations-hyperlinks.png)  

 <span data-ttu-id="ca8b4-120">Weitere Informationen finden Sie unter [Specify Whether a Hyperlink is Underlined (Angeben, ob ein Link unterstrichen wird)](how-to-specify-whether-a-hyperlink-is-underlined.md).</span><span class="sxs-lookup"><span data-stu-id="ca8b4-120">For more information, see [Specify Whether a Hyperlink is Underlined](how-to-specify-whether-a-hyperlink-is-underlined.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca8b4-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ca8b4-121">Example</span></span>  
 <span data-ttu-id="ca8b4-122">Im folgenden Codebeispiel verwendet eine Unterstreichungstextdekoration den Standardschriftwert.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-122">In the following code example, an underline text decoration uses the default font value.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets1)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets1)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets1)]  
  
 <span data-ttu-id="ca8b4-123">Im folgenden Codebeispiel wird eine Unterstreichungstextdekoration mit einem einfarbigen Pinsel für den Stift erstellt.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-123">In the following code example, an underline text decoration is created with a solid color brush for the pen.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets2)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets2)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets2)]  
  
 <span data-ttu-id="ca8b4-124">Im folgenden Codebeispiel wird eine Unterstreichungstextdekoration mit einem linearen Farbverlaufspinsel für den gestrichelten Stift erstellt.</span><span class="sxs-lookup"><span data-stu-id="ca8b4-124">In the following code example, an underline text decoration is created with a linear gradient brush for the dashed pen.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets3)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets3)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets3)]  
  
## <a name="see-also"></a><span data-ttu-id="ca8b4-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ca8b4-125">See also</span></span>

- <xref:System.Windows.TextDecoration>
- <xref:System.Windows.Documents.Hyperlink>
- [<span data-ttu-id="ca8b4-126">Angeben, ob ein Hyperlink unterstrichen wird</span><span class="sxs-lookup"><span data-stu-id="ca8b4-126">Specify Whether a Hyperlink is Underlined</span></span>](how-to-specify-whether-a-hyperlink-is-underlined.md)
