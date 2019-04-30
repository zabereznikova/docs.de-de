---
title: 'Vorgehensweise: Bearbeiten von fortlaufenden Inhaltselementen mit der Blocks-Eigenschaft'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- documents [WPF], manipulating flow content elements through Blocks property
- flow content elements [WPF], manipulating through Blocks property
- properties [WPF], Blocks [WPF], manipulating flow content elements
- Blocks property [WPF], manipulating flow content elements
ms.assetid: aeda4ece-b979-4818-a093-ef938e908751
ms.openlocfilehash: e0e1e1333a54946f3bdf474e353de0301eb42447
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942830"
---
# <a name="how-to-manipulate-flow-content-elements-through-the-blocks-property"></a><span data-ttu-id="8f64f-102">Vorgehensweise: Bearbeiten von fortlaufenden Inhaltselementen mit der Blocks-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="8f64f-102">How to: Manipulate Flow Content Elements through the Blocks Property</span></span>
<span data-ttu-id="8f64f-103">Diese Beispiele veranschaulichen einige der häufigsten Vorgänge, die für fortlaufenden Inhaltselementen mit ausgeführt werden können die **Blöcke** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8f64f-103">These examples demonstrate some of the more common operations that can be performed on flow content elements through the **Blocks** property.</span></span> <span data-ttu-id="8f64f-104">Diese Eigenschaft wird verwendet, um das Hinzufügen und Entfernen von Elementen <xref:System.Windows.Documents.BlockCollection>.</span><span class="sxs-lookup"><span data-stu-id="8f64f-104">This property is used to add and remove items from <xref:System.Windows.Documents.BlockCollection>.</span></span> <span data-ttu-id="8f64f-105">Fortlaufende Inhaltselemente, eine **Blöcke** -Eigenschaft enthalten:</span><span class="sxs-lookup"><span data-stu-id="8f64f-105">Flow content elements that feature a **Blocks** property include:</span></span>  
  
- <xref:System.Windows.Documents.Figure>  
  
- <xref:System.Windows.Documents.Floater>  
  
- <xref:System.Windows.Documents.ListItem>  
  
- <xref:System.Windows.Documents.Section>  
  
- <xref:System.Windows.Documents.TableCell>  
  
 <span data-ttu-id="8f64f-106">In diesen Beispielen auftreten, verwenden Sie <xref:System.Windows.Documents.Section> wie der Flow Content-Element, aber diese Verfahren gelten für alle Elemente, die eine Auflistung der Flow-Element für Inhalt zu hosten.</span><span class="sxs-lookup"><span data-stu-id="8f64f-106">These examples happen to use <xref:System.Windows.Documents.Section> as the flow content element, but these techniques are applicable to all elements that host a flow content element collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f64f-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8f64f-107">Example</span></span>  
 <span data-ttu-id="8f64f-108">Das folgende Beispiel erstellt ein neues <xref:System.Windows.Documents.Section> und verwendet dann die **hinzufügen** Methode, um einen neuen Absatz zum Hinzufügen der **Abschnitt** Inhalt.</span><span class="sxs-lookup"><span data-stu-id="8f64f-108">The following example creates a new <xref:System.Windows.Documents.Section> and then uses the **Add** method to add a new Paragraph to the **Section** contents.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksadd)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksadd)]  
  
## <a name="example"></a><span data-ttu-id="8f64f-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8f64f-109">Example</span></span>  
 <span data-ttu-id="8f64f-110">Das folgende Beispiel erstellt ein neues <xref:System.Windows.Documents.Paragraph> Element und fügt es am Anfang der <xref:System.Windows.Documents.Section>.</span><span class="sxs-lookup"><span data-stu-id="8f64f-110">The following example creates a new <xref:System.Windows.Documents.Paragraph> element and inserts it at the beginning of the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksInsert](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksinsert)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksInsert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksinsert)]  
  
## <a name="example"></a><span data-ttu-id="8f64f-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8f64f-111">Example</span></span>  
 <span data-ttu-id="8f64f-112">Im folgenden Beispiel wird die Anzahl der obersten Ebene <xref:System.Windows.Documents.Block> Elemente in der <xref:System.Windows.Documents.Section>.</span><span class="sxs-lookup"><span data-stu-id="8f64f-112">The following example gets the number of top-level <xref:System.Windows.Documents.Block> elements contained in the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksCount](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblockscount)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksCount](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblockscount)]  
  
## <a name="example"></a><span data-ttu-id="8f64f-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8f64f-113">Example</span></span>  
 <span data-ttu-id="8f64f-114">Das folgende Beispiel löscht das letzte <xref:System.Windows.Documents.Block> Element in der <xref:System.Windows.Documents.Section>.</span><span class="sxs-lookup"><span data-stu-id="8f64f-114">The following example deletes the last <xref:System.Windows.Documents.Block> element in the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksremovelast)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksremovelast)]  
  
## <a name="example"></a><span data-ttu-id="8f64f-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8f64f-115">Example</span></span>  
 <span data-ttu-id="8f64f-116">Das folgende Beispiel löscht den Inhalt (<xref:System.Windows.Documents.Block> Elemente) aus der <xref:System.Windows.Documents.Section>.</span><span class="sxs-lookup"><span data-stu-id="8f64f-116">The following example clears all of the contents (<xref:System.Windows.Documents.Block> elements) from the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksClear](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksclear)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksclear)]  
  
## <a name="see-also"></a><span data-ttu-id="8f64f-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f64f-117">See also</span></span>

- <xref:System.Windows.Documents.BlockCollection>
- <xref:System.Windows.Documents.InlineCollection>
- <xref:System.Windows.Documents.ListItemCollection>
- [<span data-ttu-id="8f64f-118">Übersicht über Flussdokumente</span><span class="sxs-lookup"><span data-stu-id="8f64f-118">Flow Document Overview</span></span>](flow-document-overview.md)
- [<span data-ttu-id="8f64f-119">Bearbeiten der Zeilengruppen einer Tabelle mit der RowGroups-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="8f64f-119">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
- [<span data-ttu-id="8f64f-120">Bearbeiten der Spalten einer Tabelle mit der Columns-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="8f64f-120">Manipulate a Table's Columns through the Columns Property</span></span>](how-to-manipulate-table-columns-through-the-columns-property.md)
- [<span data-ttu-id="8f64f-121">Bearbeiten der Zeilengruppen einer Tabelle mit der RowGroups-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="8f64f-121">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
