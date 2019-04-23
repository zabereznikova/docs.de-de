---
title: 'Vorgehensweise: Bearbeiten der Spalten einer Tabelle mit der Columns-Eigenschaft'
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
ms.openlocfilehash: d379d1a98bff614ff9e16cdd340bb69644988743
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59078420"
---
# <a name="how-to-manipulate-a-tables-columns-through-the-columns-property"></a>Vorgehensweise: Bearbeiten der Spalten einer Tabelle mit der Columns-Eigenschaft
Dieses Beispiel veranschaulicht einige der häufigsten Vorgänge, die für die Spalten einer Tabelle über ausgeführt werden können die <xref:System.Windows.Documents.Table.Columns%2A> Eigenschaft.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine neue Tabelle erstellt und verwendet dann die <xref:System.Windows.Documents.TableColumnCollection.Add%2A> Methode, um die Spalten der Tabelle hinzufügen <xref:System.Windows.Documents.Table.Columns%2A> Auflistung.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Add](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_add)]
 [!code-vb[TableSnippets2#_Table_Columns_Add](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_add)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel fügt eine neue <xref:System.Windows.Documents.TableColumn>.  Die neue Spalte wird an Indexposition 0 (null), die somit in der Tabelle der ersten neuen Spalte eingefügt.  
  
> [!NOTE]
>  Die <xref:System.Windows.Documents.TableColumnCollection> Auflistung standardmäßige nullbasierte Indizierung verwendet.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Insert](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_insert)]
 [!code-vb[TableSnippets2#_Table_Columns_Insert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_insert)]  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel greift auf eine beliebigen Eigenschaften für Spalten in der <xref:System.Windows.Documents.TableColumnCollection> Auflistung, die auf bestimmte Spalten nach Index verwiesen.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Manip](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_manip)]
 [!code-vb[TableSnippets2#_Table_Columns_Manip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_manip)]  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel ruft die Anzahl der derzeit von der Tabelle gehosteten Spalten ab.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Count](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_count)]
 [!code-vb[TableSnippets2#_Table_Columns_Count](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_count)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine bestimmte Spalte als Verweis.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelRef](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delref)]
 [!code-vb[TableSnippets2#_Table_Columns_DelRef](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delref)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine bestimmte Spalte anhand des Indexes an.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelIndex](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delindex)]
 [!code-vb[TableSnippets2#_Table_Columns_DelIndex](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delindex)]  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel entfernt alle Spalten aus der Tabelle Columns-Auflistung.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Clear](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_clear)]
 [!code-vb[TableSnippets2#_Table_Columns_Clear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_clear)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Tabellen](table-overview.md)
- [Definieren einer Tabelle mit XAML](how-to-define-a-table-with-xaml.md)
- [Programmgesteuertes Erstellen einer Tabelle](how-to-build-a-table-programmatically.md)
- [Bearbeiten der Zeilengruppen einer Tabelle mit der RowGroups-Eigenschaft](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
- [Bearbeiten von einem FlowDocument mit der Blocks-Eigenschaft](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [Bearbeiten der Zeilengruppen einer Tabelle mit der RowGroups-Eigenschaft](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
