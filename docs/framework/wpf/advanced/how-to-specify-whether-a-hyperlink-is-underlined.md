---
title: 'Vorgehensweise: Angeben, ob ein Hyperlink unterstrichen wird'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Hyperlink control type [WPF]
ms.assetid: 3996cfe6-1dac-4835-aeb3-c719ce9cfee5
ms.openlocfilehash: 1968e1b2730f08eb76670a477f1d2bdb0a9140bf
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2019
ms.locfileid: "58408703"
---
# <a name="how-to-specify-whether-a-hyperlink-is-underlined"></a><span data-ttu-id="a5725-102">Vorgehensweise: Angeben, ob ein Hyperlink unterstrichen wird</span><span class="sxs-lookup"><span data-stu-id="a5725-102">How to: Specify Whether a Hyperlink is Underlined</span></span>
<span data-ttu-id="a5725-103">Die <xref:System.Windows.Documents.Hyperlink> Objekt ist ein fortlaufendes Inhaltselement, das Ihnen das Hosten von links im fortlaufenden Inhalt ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="a5725-103">The <xref:System.Windows.Documents.Hyperlink> object is an inline-level flow content element that allows you to host hyperlinks within the flow content.</span></span> <span data-ttu-id="a5725-104">In der Standardeinstellung <xref:System.Windows.Documents.Hyperlink> verwendet eine <xref:System.Windows.TextDecoration> Objekt, das eine Unterstreichung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a5725-104">By default, <xref:System.Windows.Documents.Hyperlink> uses a <xref:System.Windows.TextDecoration> object to display an underline.</span></span> <span data-ttu-id="a5725-105"><xref:System.Windows.TextDecoration> Objekte können ressourcenintensiv sein, zu instanziieren, insbesondere wenn Sie viele <xref:System.Windows.Documents.Hyperlink> Objekte.</span><span class="sxs-lookup"><span data-stu-id="a5725-105"><xref:System.Windows.TextDecoration> objects can be performance intensive to instantiate, particularly if you have many <xref:System.Windows.Documents.Hyperlink> objects.</span></span> <span data-ttu-id="a5725-106">Wenn Sie umfassenden Gebrauch von machen <xref:System.Windows.Documents.Hyperlink> Elemente, Sie möchten könnten eine Unterstreichung nur, wenn ein Ereignis auslösen, z. B. die <xref:System.Windows.ContentElement.MouseEnter> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="a5725-106">If you make extensive use of <xref:System.Windows.Documents.Hyperlink> elements, you may want to consider showing an underline only when triggering an event, such as the <xref:System.Windows.ContentElement.MouseEnter> event.</span></span>  
  
 <span data-ttu-id="a5725-107">Im folgenden Beispiel wird die Unterstreichung für den Link "Meine MSN" dynamische, d. h. es nur angezeigt, wenn die <xref:System.Windows.ContentElement.MouseEnter> Ereignis wird ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="a5725-107">In the following example, the underline for the "My MSN" link is dynamic, that is, it only appears when the <xref:System.Windows.ContentElement.MouseEnter> event is triggered.</span></span>  
  
  ![Links mit TextDecorations](./media/how-to-specify-whether-a-hyperlink-is-underlined/text-decorations-hyperlinks.png)  
  
  
## <a name="example"></a><span data-ttu-id="a5725-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a5725-109">Example</span></span>  
 <span data-ttu-id="a5725-110">Das folgende Markup-Beispiel zeigt eine <xref:System.Windows.Documents.Hyperlink> mit und ohne Unterstreichung definiert:</span><span class="sxs-lookup"><span data-stu-id="a5725-110">The following markup sample shows a <xref:System.Windows.Documents.Hyperlink> defined with and without an underline:</span></span>  
  
 [!code-xaml[Performance#PerformanceSnippet11](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]  
  
 <span data-ttu-id="a5725-111">Das folgende Codebeispiel zeigt, wie eine Unterstreichung für die Erstellung der <xref:System.Windows.Documents.Hyperlink> auf die <xref:System.Windows.ContentElement.MouseEnter> -Ereignis, und entfernen Sie sie auf die <xref:System.Windows.ContentElement.MouseLeave> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="a5725-111">The following code sample shows how to create an underline for the <xref:System.Windows.Documents.Hyperlink> on the <xref:System.Windows.ContentElement.MouseEnter> event, and remove it on the <xref:System.Windows.ContentElement.MouseLeave> event.</span></span>  
  
 [!code-csharp[Performance#PerformanceSnippet15](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml.cs#performancesnippet15)]
 [!code-vb[Performance#PerformanceSnippet15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/hyperlink.xaml.vb#performancesnippet15)]  
  
## <a name="see-also"></a><span data-ttu-id="a5725-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a5725-112">See also</span></span>
- <xref:System.Windows.TextDecoration>
- <xref:System.Windows.Documents.Hyperlink>
- [<span data-ttu-id="a5725-113">Optimieren der WPF-Anwendungsleistung</span><span class="sxs-lookup"><span data-stu-id="a5725-113">Optimizing WPF Application Performance</span></span>](optimizing-wpf-application-performance.md)
- [<span data-ttu-id="a5725-114">Erstellen einer Textdekoration</span><span class="sxs-lookup"><span data-stu-id="a5725-114">Create a Text Decoration</span></span>](how-to-create-a-text-decoration.md)
