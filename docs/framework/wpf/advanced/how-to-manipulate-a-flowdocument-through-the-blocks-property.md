---
title: 'Vorgehensweise: Bearbeiten von einem FlowDocument mit der Blocks-Eigenschaft'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 'documents [WPF], manipulating FlowDocuments through Blocks property [WPF], , '
- ', '
ms.assetid: cbb7291e-3f1b-433e-9e16-f4d93ced14e8
ms.openlocfilehash: c307d85bf24e2d8a20226856181e0758758d40c0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051506"
---
# <a name="how-to-manipulate-a-flowdocument-through-the-blocks-property"></a><span data-ttu-id="5c900-102">Vorgehensweise: Bearbeiten von einem FlowDocument mit der Blocks-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5c900-102">How to: Manipulate a FlowDocument through the Blocks Property</span></span>
<span data-ttu-id="5c900-103">Diese Beispiele veranschaulichen einige der häufigsten Vorgänge, die für ausgeführt werden können eine <xref:System.Windows.Documents.FlowDocument> über die <xref:System.Windows.Documents.FlowDocument.Blocks%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="5c900-103">These examples demonstrate some of the more common operations that can be performed on a <xref:System.Windows.Documents.FlowDocument> through the <xref:System.Windows.Documents.FlowDocument.Blocks%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c900-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5c900-104">Example</span></span>  
 <span data-ttu-id="5c900-105">Das folgende Beispiel erstellt ein neues <xref:System.Windows.Documents.FlowDocument> und fügt dann ein neues <xref:System.Windows.Documents.Paragraph> Element, das <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="5c900-105">The following example creates a new <xref:System.Windows.Documents.FlowDocument> and then appends a new <xref:System.Windows.Documents.Paragraph> element to the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblocksadd)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblocksadd)]  
  
## <a name="example"></a><span data-ttu-id="5c900-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5c900-106">Example</span></span>  
 <span data-ttu-id="5c900-107">Das folgende Beispiel erstellt ein neues <xref:System.Windows.Documents.Paragraph> Element und fügt es am Anfang der <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="5c900-107">The following example creates a new <xref:System.Windows.Documents.Paragraph> element and inserts it at the beginning of the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksInsert](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblocksinsert)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksInsert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblocksinsert)]  
  
## <a name="example"></a><span data-ttu-id="5c900-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5c900-108">Example</span></span>  
 <span data-ttu-id="5c900-109">Im folgenden Beispiel wird die Anzahl der obersten Ebene <xref:System.Windows.Documents.Block> Elemente in der <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="5c900-109">The following example gets the number of top-level <xref:System.Windows.Documents.Block> elements contained in the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksCount](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblockscount)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksCount](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblockscount)]  
  
## <a name="example"></a><span data-ttu-id="5c900-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5c900-110">Example</span></span>  
 <span data-ttu-id="5c900-111">Das folgende Beispiel löscht das letzte <xref:System.Windows.Documents.Block> Element in der <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="5c900-111">The following example deletes the last <xref:System.Windows.Documents.Block> element in the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblocksremovelast)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblocksremovelast)]  
  
## <a name="example"></a><span data-ttu-id="5c900-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5c900-112">Example</span></span>  
 <span data-ttu-id="5c900-113">Das folgende Beispiel löscht den Inhalt (<xref:System.Windows.Documents.Block> Elemente) aus der <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="5c900-113">The following example clears all of the contents (<xref:System.Windows.Documents.Block> elements) from the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksClear](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblocksclear)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblocksclear)]  
  
## <a name="see-also"></a><span data-ttu-id="5c900-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5c900-114">See also</span></span>

- [<span data-ttu-id="5c900-115">Bearbeiten der Zeilengruppen einer Tabelle mit der RowGroups-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5c900-115">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
- [<span data-ttu-id="5c900-116">Bearbeiten der Spalten einer Tabelle mit der Columns-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5c900-116">Manipulate a Table's Columns through the Columns Property</span></span>](how-to-manipulate-table-columns-through-the-columns-property.md)
- [<span data-ttu-id="5c900-117">Bearbeiten der Zeilengruppen einer Tabelle mit der RowGroups-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5c900-117">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
