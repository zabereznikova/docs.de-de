---
title: 'Gewusst wie: Bearbeiten von fortlaufenden Inhaltselementen mit der Blocks-Eigenschaft'
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
- documents [WPF], manipulating flow content elements through Blocks property
- flow content elements [WPF], manipulating through Blocks property
- properties [WPF], Blocks [WPF], manipulating flow content elements
- Blocks property [WPF], manipulating flow content elements
ms.assetid: aeda4ece-b979-4818-a093-ef938e908751
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d995e9a3a50e733a87a203f94b97a937560a0141
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-manipulate-flow-content-elements-through-the-blocks-property"></a><span data-ttu-id="0b8a3-102">Gewusst wie: Bearbeiten von fortlaufenden Inhaltselementen mit der Blocks-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="0b8a3-102">How to: Manipulate Flow Content Elements through the Blocks Property</span></span>
<span data-ttu-id="0b8a3-103">Diese Beispiele zeigen einige der häufigeren Vorgänge, die für Inhaltselemente über ausgeführt werden, können die **Blöcke** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="0b8a3-103">These examples demonstrate some of the more common operations that can be performed on flow content elements through the **Blocks** property.</span></span> <span data-ttu-id="0b8a3-104">Diese Eigenschaft dient zum Hinzufügen und Entfernen von Elementen aus <xref:System.Windows.Documents.BlockCollection>.</span><span class="sxs-lookup"><span data-stu-id="0b8a3-104">This property is used to add and remove items from <xref:System.Windows.Documents.BlockCollection>.</span></span> <span data-ttu-id="0b8a3-105">Fortlaufenden Inhaltselemente mit einem **Blöcke** -Eigenschaft enthalten:</span><span class="sxs-lookup"><span data-stu-id="0b8a3-105">Flow content elements that feature a **Blocks** property include:</span></span>  
  
-   <xref:System.Windows.Documents.Figure>  
  
-   <xref:System.Windows.Documents.Floater>  
  
-   <xref:System.Windows.Documents.ListItem>  
  
-   <xref:System.Windows.Documents.Section>  
  
-   <xref:System.Windows.Documents.TableCell>  
  
 <span data-ttu-id="0b8a3-106">Diese Beispiele verwenden geschehen <xref:System.Windows.Documents.Section> abfrageausführungsprozess, während die Content-Element, aber diese Verfahren beziehen sich auf alle Elemente, die eine Auflistung der Datenfluss Inhaltselement hosten.</span><span class="sxs-lookup"><span data-stu-id="0b8a3-106">These examples happen to use <xref:System.Windows.Documents.Section> as the flow content element, but these techniques are applicable to all elements that host a flow content element collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b8a3-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0b8a3-107">Example</span></span>  
 <span data-ttu-id="0b8a3-108">Das folgende Beispiel erstellt ein neues <xref:System.Windows.Documents.Section> und verwendet dann die **hinzufügen** Methode, um einen neuen Absatz zum Hinzufügen der **Abschnitt** Inhalt.</span><span class="sxs-lookup"><span data-stu-id="0b8a3-108">The following example creates a new <xref:System.Windows.Documents.Section> and then uses the **Add** method to add a new Paragraph to the **Section** contents.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksadd)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksadd)]  
  
## <a name="example"></a><span data-ttu-id="0b8a3-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0b8a3-109">Example</span></span>  
 <span data-ttu-id="0b8a3-110">Das folgende Beispiel erstellt ein neues <xref:System.Windows.Documents.Paragraph> Element und fügt es am Anfang der <xref:System.Windows.Documents.Section>.</span><span class="sxs-lookup"><span data-stu-id="0b8a3-110">The following example creates a new <xref:System.Windows.Documents.Paragraph> element and inserts it at the beginning of the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksInsert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksinsert)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksInsert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksinsert)]  
  
## <a name="example"></a><span data-ttu-id="0b8a3-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0b8a3-111">Example</span></span>  
 <span data-ttu-id="0b8a3-112">Im folgenden Beispiel wird die Anzahl der obersten Ebene <xref:System.Windows.Documents.Block> Elemente in der <xref:System.Windows.Documents.Section>.</span><span class="sxs-lookup"><span data-stu-id="0b8a3-112">The following example gets the number of top-level <xref:System.Windows.Documents.Block> elements contained in the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksCount](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblockscount)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksCount](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblockscount)]  
  
## <a name="example"></a><span data-ttu-id="0b8a3-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0b8a3-113">Example</span></span>  
 <span data-ttu-id="0b8a3-114">Das folgende Beispiel löscht die letzte <xref:System.Windows.Documents.Block> Element in der <xref:System.Windows.Documents.Section>.</span><span class="sxs-lookup"><span data-stu-id="0b8a3-114">The following example deletes the last <xref:System.Windows.Documents.Block> element in the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksremovelast)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksremovelast)]  
  
## <a name="example"></a><span data-ttu-id="0b8a3-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0b8a3-115">Example</span></span>  
 <span data-ttu-id="0b8a3-116">Das folgende Beispiel löscht den Inhalt (<xref:System.Windows.Documents.Block> Elemente) aus dem <xref:System.Windows.Documents.Section>.</span><span class="sxs-lookup"><span data-stu-id="0b8a3-116">The following example clears all of the contents (<xref:System.Windows.Documents.Block> elements) from the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksclear)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksclear)]  
  
## <a name="see-also"></a><span data-ttu-id="0b8a3-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b8a3-117">See Also</span></span>  
 <xref:System.Windows.Documents.BlockCollection>  
 <xref:System.Windows.Documents.InlineCollection>  
 <xref:System.Windows.Documents.ListItemCollection>  
 [<span data-ttu-id="0b8a3-118">Übersicht über Flussdokumente</span><span class="sxs-lookup"><span data-stu-id="0b8a3-118">Flow Document Overview</span></span>](../../../../docs/framework/wpf/advanced/flow-document-overview.md)  
 [<span data-ttu-id="0b8a3-119">Bearbeiten der Zeilengruppen einer Tabelle mit der RowGroups-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="0b8a3-119">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)  
 [<span data-ttu-id="0b8a3-120">Bearbeiten der Spalten einer Tabelle mit der Columns-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="0b8a3-120">Manipulate a Table's Columns through the Columns Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)  
 [<span data-ttu-id="0b8a3-121">Bearbeiten der Zeilengruppen einer Tabelle mit der RowGroups-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="0b8a3-121">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
