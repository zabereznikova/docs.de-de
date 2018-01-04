---
title: 'Gewusst wie: Bearbeiten von fortlaufenden Inhaltselementen mit der Inlines-Eigenschaft'
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
- flow content elements [WPF], manipulating through Inlines property
- documents [WPF], manipulating flow Content elements through Inlines property
- Inlines property [WPF], manipulating flow Content elements
- properties [WPF], Inlines [WPF], manipulating flow Content elements
ms.assetid: 510780d2-3da1-4360-8763-7054bda22ea3
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c5d90756ee200ba091f2f9e15e9e7d5632984ba9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-manipulate-flow-content-elements-through-the-inlines-property"></a><span data-ttu-id="0936c-102">Gewusst wie: Bearbeiten von fortlaufenden Inhaltselementen mit der Inlines-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="0936c-102">How to: Manipulate Flow Content Elements through the Inlines Property</span></span>
<span data-ttu-id="0936c-103">Diese Beispiele zeigen einige der häufigeren Vorgänge, die für den Inline-Inhaltselemente ausgeführt werden können (und Container von solchen Elementen, z. B. <xref:System.Windows.Controls.TextBlock>) über die **Inlines** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="0936c-103">These examples demonstrate some of the more common operations that can be performed on inline flow content elements (and containers of such elements, such as <xref:System.Windows.Controls.TextBlock>) through the **Inlines** property.</span></span> <span data-ttu-id="0936c-104">Diese Eigenschaft dient zum Hinzufügen und Entfernen von Elementen aus <xref:System.Windows.Documents.InlineCollection>.</span><span class="sxs-lookup"><span data-stu-id="0936c-104">This property is used to add and remove items from <xref:System.Windows.Documents.InlineCollection>.</span></span> <span data-ttu-id="0936c-105">Fortlaufenden Inhaltselemente mit einer **Inlines** -Eigenschaft enthalten:</span><span class="sxs-lookup"><span data-stu-id="0936c-105">Flow content elements that feature an **Inlines** property include:</span></span>  
  
-   <xref:System.Windows.Documents.Bold>  
  
-   <xref:System.Windows.Documents.Hyperlink>  
  
-   <xref:System.Windows.Documents.Italic>  
  
-   <xref:System.Windows.Documents.Paragraph>  
  
-   <xref:System.Windows.Documents.Span>  
  
-   <xref:System.Windows.Documents.Underline>  
  
 <span data-ttu-id="0936c-106">Diese Beispiele verwenden geschehen <xref:System.Windows.Documents.Span> abfrageausführungsprozess, während die Content-Element, aber diese Verfahren beziehen sich auf alle Elemente oder Steuerelemente, die Hosten einer <xref:System.Windows.Documents.InlineCollection> Auflistung.</span><span class="sxs-lookup"><span data-stu-id="0936c-106">These examples happen to use <xref:System.Windows.Documents.Span> as the flow content element, but these techniques are applicable to all elements or controls that host an <xref:System.Windows.Documents.InlineCollection> collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0936c-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0936c-107">Example</span></span>  
 <span data-ttu-id="0936c-108">Das folgende Beispiel erstellt ein neues <xref:System.Windows.Documents.Span> Objekt zugewiesen und dann verwendet der **hinzufügen** Methode zum Hinzufügen von zwei Text ausgeführt wird als Inhalt untergeordnete Elemente von der <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="0936c-108">The following example creates a new <xref:System.Windows.Documents.Span> object, and then uses the **Add** method to add two text runs as content children of the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
## <a name="example"></a><span data-ttu-id="0936c-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0936c-109">Example</span></span>  
 <span data-ttu-id="0936c-110">Das folgende Beispiel erstellt ein neues <xref:System.Windows.Documents.Run> Element und fügt es am Anfang der <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="0936c-110">The following example creates a new <xref:System.Windows.Documents.Run> element and inserts it at the beginning of the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
## <a name="example"></a><span data-ttu-id="0936c-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0936c-111">Example</span></span>  
 <span data-ttu-id="0936c-112">Im folgenden Beispiel wird die Anzahl der obersten Ebene <xref:System.Windows.Documents.Inline> Elemente in der <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="0936c-112">The following example gets the number of top-level <xref:System.Windows.Documents.Inline> elements contained in the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesCount](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinescount)]
 [!code-vb[SpanSnippets#_SpanInlinesCount](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinescount)]  
  
## <a name="example"></a><span data-ttu-id="0936c-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0936c-113">Example</span></span>  
 <span data-ttu-id="0936c-114">Das folgende Beispiel löscht die letzte <xref:System.Windows.Documents.Inline> Element in der <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="0936c-114">The following example deletes the last <xref:System.Windows.Documents.Inline> element in the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
## <a name="example"></a><span data-ttu-id="0936c-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0936c-115">Example</span></span>  
 <span data-ttu-id="0936c-116">Das folgende Beispiel löscht den Inhalt (<xref:System.Windows.Documents.Inline> Elemente) aus dem <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="0936c-116">The following example clears all of the contents (<xref:System.Windows.Documents.Inline> elements) from the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
## <a name="see-also"></a><span data-ttu-id="0936c-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0936c-117">See Also</span></span>  
 <xref:System.Windows.Documents.BlockCollection>  
 <xref:System.Windows.Documents.InlineCollection>  
 <xref:System.Windows.Documents.ListItemCollection>  
 [<span data-ttu-id="0936c-118">Übersicht über Flussdokumente</span><span class="sxs-lookup"><span data-stu-id="0936c-118">Flow Document Overview</span></span>](../../../../docs/framework/wpf/advanced/flow-document-overview.md)  
 [<span data-ttu-id="0936c-119">Bearbeiten von einem FlowDocument mit der Blocks-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="0936c-119">Manipulate a FlowDocument through the Blocks Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)  
 [<span data-ttu-id="0936c-120">Bearbeiten der Spalten einer Tabelle mit der Columns-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="0936c-120">Manipulate a Table's Columns through the Columns Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)  
 [<span data-ttu-id="0936c-121">Bearbeiten der Zeilengruppen einer Tabelle mit der RowGroups-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="0936c-121">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
