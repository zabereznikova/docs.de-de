---
title: 'Vorgehensweise: Bearbeiten eine Tabelle&#39;s Zeilengruppen mit der RowGroups-Eigenschaft'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- row groups [WPF], manipulating through RowGroups property
- RowGroups property [WPF], manipulating row groups
- documents [WPF], manipulating row groups through RowGroups property
- properties [WPF], RowGroups [WPF], manipulating row groups
ms.assetid: ea61440f-08ae-44ed-b314-5716aaaae3ed
ms.openlocfilehash: 8cdf3b74fa5bf5a566c541ba035a1c7da7dd6949
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545164"
---
# <a name="how-to-manipulate-a-table39s-row-groups-through-the-rowgroups-property"></a><span data-ttu-id="affd7-102">Vorgehensweise: Bearbeiten eine Tabelle&#39;s Zeilengruppen mit der RowGroups-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="affd7-102">How to: Manipulate a Table&#39;s Row Groups through the RowGroups Property</span></span>
<span data-ttu-id="affd7-103">Dieses Beispiel zeigt einige der häufigeren Vorgänge, die für eine Tabelle Zeilengruppen über ausgeführt werden können die <xref:System.Windows.Documents.Table.RowGroups%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="affd7-103">This example demonstrates some of the more common operations that can be performed on a table's row groups through the <xref:System.Windows.Documents.Table.RowGroups%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="affd7-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="affd7-104">Example</span></span>  
 <span data-ttu-id="affd7-105">Im folgenden Beispiel wird eine neue Tabelle erstellt und verwendet dann die <xref:System.Windows.Documents.TableRowGroupCollection.Add%2A> Methode, um die Tabelle Spalten hinzugefügt <xref:System.Windows.Documents.Table.RowGroups%2A> Auflistung.</span><span class="sxs-lookup"><span data-stu-id="affd7-105">The following example creates a new table and then uses the <xref:System.Windows.Documents.TableRowGroupCollection.Add%2A> method to add columns to the table's <xref:System.Windows.Documents.Table.RowGroups%2A> collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Add](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_add)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Add](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_add)]  
  
## <a name="example"></a><span data-ttu-id="affd7-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="affd7-106">Example</span></span>  
 <span data-ttu-id="affd7-107">Das folgende Beispiel fügt eine neue <xref:System.Windows.Documents.TableRowGroup>.</span><span class="sxs-lookup"><span data-stu-id="affd7-107">The following example inserts a new <xref:System.Windows.Documents.TableRowGroup>.</span></span>  <span data-ttu-id="affd7-108">Die neue Spalte wird eingefügt, an Indexposition 0, somit wird die neue erste Zeile in der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="affd7-108">The new column is inserted at index position 0, making it the new first row group in the table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="affd7-109">Die <xref:System.Windows.Documents.TableRowGroupCollection> Auflistung verwendet standardmäßige nullbasierter Indizierung.</span><span class="sxs-lookup"><span data-stu-id="affd7-109">The <xref:System.Windows.Documents.TableRowGroupCollection> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Insert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_insert)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Insert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_insert)]  
  
## <a name="example"></a><span data-ttu-id="affd7-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="affd7-110">Example</span></span>  
 <span data-ttu-id="affd7-111">Das folgende Beispiel fügt mehrere Zeilen zu einem bestimmten <xref:System.Windows.Documents.TableRowGroup> (angegeben durch Index) in der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="affd7-111">The following example adds several rows to a particular <xref:System.Windows.Documents.TableRowGroup> (specified by index) in the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_AddRows](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_addrows)]
 [!code-vb[TableSnippets2#_Table_RowGroups_AddRows](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_addrows)]  
  
## <a name="example"></a><span data-ttu-id="affd7-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="affd7-112">Example</span></span>  
 <span data-ttu-id="affd7-113">Das folgende Beispiel greift auf einige beliebigen Eigenschaften in Zeilen in der ersten Zeilengruppe in der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="affd7-113">The following example accesses some arbitrary properties on rows in the first row group in the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_ManipRows](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_maniprows)]
 [!code-vb[TableSnippets2#_Table_RowGroups_ManipRows](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_maniprows)]  
  
## <a name="example"></a><span data-ttu-id="affd7-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="affd7-114">Example</span></span>  
 <span data-ttu-id="affd7-115">Das folgende Beispiel fügt mehrere Zellen zu einem bestimmten <xref:System.Windows.Documents.TableRow> (angegeben durch Index) in der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="affd7-115">The following example adds several cells to a particular <xref:System.Windows.Documents.TableRow> (specified by index) in the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_AddCells](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_addcells)]
 [!code-vb[TableSnippets2#_Table_RowGroups_AddCells](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_addcells)]  
  
## <a name="example"></a><span data-ttu-id="affd7-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="affd7-116">Example</span></span>  
 <span data-ttu-id="affd7-117">Im folgenden Beispiel wird Zugriff auf einige beliebige Methoden und Eigenschaften für Zellen in der ersten Zeile in der ersten Zeilengruppe.</span><span class="sxs-lookup"><span data-stu-id="affd7-117">The following example access some arbitrary methods and properties on cells in the first row in the first row group.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_ManipCells](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_manipcells)]
 [!code-vb[TableSnippets2#_Table_RowGroups_ManipCells](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_manipcells)]  
  
## <a name="example"></a><span data-ttu-id="affd7-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="affd7-118">Example</span></span>  
 <span data-ttu-id="affd7-119">Im folgende Beispiel gibt die Anzahl der <xref:System.Windows.Documents.TableRowGroup> Elemente, die von der Tabelle gehosteten.</span><span class="sxs-lookup"><span data-stu-id="affd7-119">The following example returns the number of <xref:System.Windows.Documents.TableRowGroup> elements hosted by the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Count](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_count)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Count](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_count)]  
  
## <a name="example"></a><span data-ttu-id="affd7-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="affd7-120">Example</span></span>  
 <span data-ttu-id="affd7-121">Im folgenden Beispiel wird eine bestimmte Zeilengruppe nach Verweis.</span><span class="sxs-lookup"><span data-stu-id="affd7-121">The following example removes a particular row group by reference.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_DelRef](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_delref)]
 [!code-vb[TableSnippets2#_Table_RowGroups_DelRef](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_delref)]  
  
## <a name="example"></a><span data-ttu-id="affd7-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="affd7-122">Example</span></span>  
 <span data-ttu-id="affd7-123">Im folgende Beispiel wird eine bestimmten Zeilengruppe nach Index entfernt.</span><span class="sxs-lookup"><span data-stu-id="affd7-123">The following example removes a particular row group by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_DelIndex](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_delindex)]
 [!code-vb[TableSnippets2#_Table_RowGroups_DelIndex](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_delindex)]  
  
## <a name="example"></a><span data-ttu-id="affd7-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="affd7-124">Example</span></span>  
 <span data-ttu-id="affd7-125">Im folgende Beispiel entfernt alle Zeilengruppen aus Gruppen-zeilenauflistung der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="affd7-125">The following example removes all row groups from the table's row groups collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Clear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_clear)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Clear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_clear)]  
  
## <a name="see-also"></a><span data-ttu-id="affd7-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="affd7-126">See Also</span></span>  
 [<span data-ttu-id="affd7-127">Gewusst wie: Bearbeiten von Inhaltselemente durch die Inlines-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="affd7-127">How-to: Manipulate Flow Content Elements through the Inlines Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)  
 [<span data-ttu-id="affd7-128">Bearbeiten von einem FlowDocument mit der Blocks-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="affd7-128">Manipulate a FlowDocument through the Blocks Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)  
 [<span data-ttu-id="affd7-129">Bearbeiten der Spalten einer Tabelle mit der Columns-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="affd7-129">Manipulate a Table's Columns through the Columns Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)
