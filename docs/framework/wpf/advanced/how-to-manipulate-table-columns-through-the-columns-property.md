---
title: 'Vorgehensweise: Bearbeiten Sie eine Tabelle&#39;s-Spalten mit der Columns-Eigenschaft'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- documents [WPF], manipulating table columns
- properties [WPF], Columns [WPF], manipulating table columns
- tables [WPF], manipulating columns
- Columns property [WPF]
ms.assetid: 3f8884f4-7e1f-456b-be06-fbd3cf469bf3
ms.openlocfilehash: f560e85888b5617f545082d47d124163d492ec00
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54655811"
---
# <a name="how-to-manipulate-a-table39s-columns-through-the-columns-property"></a><span data-ttu-id="93e40-102">Vorgehensweise: Bearbeiten Sie eine Tabelle&#39;s-Spalten mit der Columns-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="93e40-102">How to: Manipulate a Table&#39;s Columns through the Columns Property</span></span>
<span data-ttu-id="93e40-103">Dieses Beispiel veranschaulicht einige der häufigsten Vorgänge, die für die Spalten einer Tabelle über ausgeführt werden können die <xref:System.Windows.Documents.Table.Columns%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="93e40-103">This example demonstrates some of the more common operations that can be performed on a table's columns through the <xref:System.Windows.Documents.Table.Columns%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93e40-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="93e40-104">Example</span></span>  
 <span data-ttu-id="93e40-105">Im folgenden Beispiel wird eine neue Tabelle erstellt und verwendet dann die <xref:System.Windows.Documents.TableColumnCollection.Add%2A> Methode, um die Spalten der Tabelle hinzufügen <xref:System.Windows.Documents.Table.Columns%2A> Auflistung.</span><span class="sxs-lookup"><span data-stu-id="93e40-105">The following example creates a new table and then uses the <xref:System.Windows.Documents.TableColumnCollection.Add%2A> method to add columns to the table's <xref:System.Windows.Documents.Table.Columns%2A> collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Add](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_add)]
 [!code-vb[TableSnippets2#_Table_Columns_Add](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_add)]  
  
## <a name="example"></a><span data-ttu-id="93e40-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="93e40-106">Example</span></span>  
 <span data-ttu-id="93e40-107">Das folgende Beispiel fügt eine neue <xref:System.Windows.Documents.TableColumn>.</span><span class="sxs-lookup"><span data-stu-id="93e40-107">The following example inserts a new <xref:System.Windows.Documents.TableColumn>.</span></span>  <span data-ttu-id="93e40-108">Die neue Spalte wird an Indexposition 0 (null), die somit in der Tabelle der ersten neuen Spalte eingefügt.</span><span class="sxs-lookup"><span data-stu-id="93e40-108">The new column is inserted at index position 0, making it the new first column in the table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="93e40-109">Die <xref:System.Windows.Documents.TableColumnCollection> Auflistung standardmäßige nullbasierte Indizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="93e40-109">The <xref:System.Windows.Documents.TableColumnCollection> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Insert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_insert)]
 [!code-vb[TableSnippets2#_Table_Columns_Insert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_insert)]  
  
## <a name="example"></a><span data-ttu-id="93e40-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="93e40-110">Example</span></span>  
 <span data-ttu-id="93e40-111">Im folgende Beispiel greift auf eine beliebigen Eigenschaften für Spalten in der <xref:System.Windows.Documents.TableColumnCollection> Auflistung, die auf bestimmte Spalten nach Index verwiesen.</span><span class="sxs-lookup"><span data-stu-id="93e40-111">The following example accesses some arbitrary properties on columns in the <xref:System.Windows.Documents.TableColumnCollection> collection, referring to particular columns by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Manip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_manip)]
 [!code-vb[TableSnippets2#_Table_Columns_Manip](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_manip)]  
  
## <a name="example"></a><span data-ttu-id="93e40-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="93e40-112">Example</span></span>  
 <span data-ttu-id="93e40-113">Im folgende Beispiel ruft die Anzahl der derzeit von der Tabelle gehosteten Spalten ab.</span><span class="sxs-lookup"><span data-stu-id="93e40-113">The following example gets the number of columns currently hosted by the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Count](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_count)]
 [!code-vb[TableSnippets2#_Table_Columns_Count](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_count)]  
  
## <a name="example"></a><span data-ttu-id="93e40-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="93e40-114">Example</span></span>  
 <span data-ttu-id="93e40-115">Im folgenden Beispiel wird eine bestimmte Spalte als Verweis.</span><span class="sxs-lookup"><span data-stu-id="93e40-115">The following example removes a particular column by reference.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelRef](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delref)]
 [!code-vb[TableSnippets2#_Table_Columns_DelRef](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delref)]  
  
## <a name="example"></a><span data-ttu-id="93e40-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="93e40-116">Example</span></span>  
 <span data-ttu-id="93e40-117">Im folgenden Beispiel wird eine bestimmte Spalte anhand des Indexes an.</span><span class="sxs-lookup"><span data-stu-id="93e40-117">The following example removes a particular column by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelIndex](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delindex)]
 [!code-vb[TableSnippets2#_Table_Columns_DelIndex](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delindex)]  
  
## <a name="example"></a><span data-ttu-id="93e40-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="93e40-118">Example</span></span>  
 <span data-ttu-id="93e40-119">Im folgende Beispiel entfernt alle Spalten aus der Tabelle Columns-Auflistung.</span><span class="sxs-lookup"><span data-stu-id="93e40-119">The following example removes all columns from the table's columns collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Clear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_clear)]
 [!code-vb[TableSnippets2#_Table_Columns_Clear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_clear)]  
  
## <a name="see-also"></a><span data-ttu-id="93e40-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="93e40-120">See also</span></span>
- [<span data-ttu-id="93e40-121">Übersicht über Tabellen</span><span class="sxs-lookup"><span data-stu-id="93e40-121">Table Overview</span></span>](../../../../docs/framework/wpf/advanced/table-overview.md)
- [<span data-ttu-id="93e40-122">Definieren einer Tabelle mit XAML</span><span class="sxs-lookup"><span data-stu-id="93e40-122">Define a Table with XAML</span></span>](../../../../docs/framework/wpf/advanced/how-to-define-a-table-with-xaml.md)
- [<span data-ttu-id="93e40-123">Programmgesteuertes Erstellen einer Tabelle</span><span class="sxs-lookup"><span data-stu-id="93e40-123">Build a Table Programmatically</span></span>](../../../../docs/framework/wpf/advanced/how-to-build-a-table-programmatically.md)
- [<span data-ttu-id="93e40-124">Bearbeiten der Zeilengruppen einer Tabelle mit der RowGroups-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="93e40-124">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
- [<span data-ttu-id="93e40-125">Bearbeiten von einem FlowDocument mit der Blocks-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="93e40-125">Manipulate a FlowDocument through the Blocks Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [<span data-ttu-id="93e40-126">Bearbeiten der Zeilengruppen einer Tabelle mit der RowGroups-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="93e40-126">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
