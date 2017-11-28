---
title: 'Gewusst wie: Angeben, ob ein Hyperlink unterstrichen wird'
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
helpviewer_keywords: Hyperlink control type [WPF]
ms.assetid: 3996cfe6-1dac-4835-aeb3-c719ce9cfee5
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7914b3b3332b7ea0abe05b3048b5016888e2d93e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-whether-a-hyperlink-is-underlined"></a><span data-ttu-id="e711f-102">Gewusst wie: Angeben, ob ein Hyperlink unterstrichen wird</span><span class="sxs-lookup"><span data-stu-id="e711f-102">How to: Specify Whether a Hyperlink is Underlined</span></span>
<span data-ttu-id="e711f-103">Die <xref:System.Windows.Documents.Hyperlink> Objekt ist ein Inhaltselement Inlineebene, der Ihnen das Hosten von links im fortlaufenden Inhalt ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="e711f-103">The <xref:System.Windows.Documents.Hyperlink> object is an inline-level flow content element that allows you to host hyperlinks within the flow content.</span></span> <span data-ttu-id="e711f-104">Standardmäßig <xref:System.Windows.Documents.Hyperlink> verwendet ein <xref:System.Windows.TextDecoration> Objekt, das eine Unterstreichung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e711f-104">By default, <xref:System.Windows.Documents.Hyperlink> uses a <xref:System.Windows.TextDecoration> object to display an underline.</span></span> <span data-ttu-id="e711f-105"><xref:System.Windows.TextDecoration>Objekte können ressourcenintensiv sein zu instanziieren, insbesondere, wenn Sie viele haben <xref:System.Windows.Documents.Hyperlink> Objekte.</span><span class="sxs-lookup"><span data-stu-id="e711f-105"><xref:System.Windows.TextDecoration> objects can be performance intensive to instantiate, particularly if you have many <xref:System.Windows.Documents.Hyperlink> objects.</span></span> <span data-ttu-id="e711f-106">Wenn Sie eine umfangreiche nutzen <xref:System.Windows.Documents.Hyperlink> Elemente, Sie sollten in Betracht ziehen einen Unterstrich nur, wenn ein Ereignis auslösen, z. B. Anzeigen der <xref:System.Windows.ContentElement.MouseEnter> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="e711f-106">If you make extensive use of <xref:System.Windows.Documents.Hyperlink> elements, you may want to consider showing an underline only when triggering an event, such as the <xref:System.Windows.ContentElement.MouseEnter> event.</span></span>  
  
 <span data-ttu-id="e711f-107">Im folgenden Beispiel wird die Unterstreichung für den Link "My MSN" dynamische – es wird nur angezeigt, wenn die <xref:System.Windows.ContentElement.MouseEnter> Ereignis wird ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="e711f-107">In the following example, the underline for the "My MSN" link is dynamic—it only appears when the <xref:System.Windows.ContentElement.MouseEnter> event is triggered.</span></span>  
  
 <span data-ttu-id="e711f-108">![Links mit TextDecorations](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")</span><span class="sxs-lookup"><span data-stu-id="e711f-108">![Hyperlinks displaying TextDecorations](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")</span></span>  
<span data-ttu-id="e711f-109">Links mit TextDecorations definiert</span><span class="sxs-lookup"><span data-stu-id="e711f-109">Hyperlinks defined with TextDecorations</span></span>  
  
## <a name="example"></a><span data-ttu-id="e711f-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e711f-110">Example</span></span>  
 <span data-ttu-id="e711f-111">Das folgende Markup-Beispiel zeigt eine <xref:System.Windows.Documents.Hyperlink> mit und ohne Unterstreichung definiert:</span><span class="sxs-lookup"><span data-stu-id="e711f-111">The following markup sample shows a <xref:System.Windows.Documents.Hyperlink> defined with and without an underline:</span></span>  
  
 [!code-xaml[Performance#PerformanceSnippet11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]  
  
 <span data-ttu-id="e711f-112">Im folgenden Codebeispiel wird gezeigt, wie zum Erstellen einer Unterstreichung für die <xref:System.Windows.Documents.Hyperlink> auf die <xref:System.Windows.ContentElement.MouseEnter> Ereignis, und entfernen Sie es auf die <xref:System.Windows.ContentElement.MouseLeave> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="e711f-112">The following code sample shows how to create an underline for the <xref:System.Windows.Documents.Hyperlink> on the <xref:System.Windows.ContentElement.MouseEnter> event, and remove it on the <xref:System.Windows.ContentElement.MouseLeave> event.</span></span>  
  
 [!code-csharp[Performance#PerformanceSnippet15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml.cs#performancesnippet15)]
 [!code-vb[Performance#PerformanceSnippet15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/hyperlink.xaml.vb#performancesnippet15)]  
  
## <a name="see-also"></a><span data-ttu-id="e711f-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e711f-113">See Also</span></span>  
 <xref:System.Windows.TextDecoration>  
 <xref:System.Windows.Documents.Hyperlink>  
 [<span data-ttu-id="e711f-114">Optimieren der WPF-Anwendungsleistung</span><span class="sxs-lookup"><span data-stu-id="e711f-114">Optimizing WPF Application Performance</span></span>](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
 [<span data-ttu-id="e711f-115">Erstellen einer Textdekoration</span><span class="sxs-lookup"><span data-stu-id="e711f-115">Create a Text Decoration</span></span>](../../../../docs/framework/wpf/advanced/how-to-create-a-text-decoration.md)
