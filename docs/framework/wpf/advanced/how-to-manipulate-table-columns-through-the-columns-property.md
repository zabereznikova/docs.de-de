---
title: 'Vorgehensweise: Bearbeiten eine Tabelle&#39;s Spalten durch die Spalten-Eigenschaft'
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
ms.openlocfilehash: 916764c621738ddc651580f1232e1f579a17e6f0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545297"
---
# <a name="how-to-manipulate-a-table39s-columns-through-the-columns-property"></a>Vorgehensweise: Bearbeiten eine Tabelle&#39;s Spalten durch die Spalten-Eigenschaft
Dieses Beispiel zeigt einige der häufigeren Vorgänge, die auf Spalten einer Tabelle mit ausgeführt werden, können die <xref:System.Windows.Documents.Table.Columns%2A> Eigenschaft.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine neue Tabelle erstellt und verwendet dann die <xref:System.Windows.Documents.TableColumnCollection.Add%2A> Methode, um die Tabelle Spalten hinzugefügt <xref:System.Windows.Documents.Table.Columns%2A> Auflistung.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Add](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_add)]
 [!code-vb[TableSnippets2#_Table_Columns_Add](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_add)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel fügt eine neue <xref:System.Windows.Documents.TableColumn>.  Die neue Spalte wird an Indexposition 0, wodurch die erste neue Spalte in der Tabelle eingefügt.  
  
> [!NOTE]
>  Die <xref:System.Windows.Documents.TableColumnCollection> Auflistung verwendet standardmäßige nullbasierter Indizierung.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Insert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_insert)]
 [!code-vb[TableSnippets2#_Table_Columns_Insert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_insert)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel greift auf einige beliebigen Eigenschaften für Spalten in der <xref:System.Windows.Documents.TableColumnCollection> Auflistung, die auf bestimmte Spalten über einen Index verwiesen.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Manip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_manip)]
 [!code-vb[TableSnippets2#_Table_Columns_Manip](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_manip)]  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel ruft die Anzahl der derzeit von der Tabelle gehosteten Spalten ab.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Count](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_count)]
 [!code-vb[TableSnippets2#_Table_Columns_Count](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_count)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine bestimmte Spalte als Verweis an.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelRef](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delref)]
 [!code-vb[TableSnippets2#_Table_Columns_DelRef](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delref)]  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird eine bestimmte Spalte nach Index entfernt.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelIndex](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delindex)]
 [!code-vb[TableSnippets2#_Table_Columns_DelIndex](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delindex)]  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel entfernt alle Spalten aus der Tabelle Columns-Auflistung.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Clear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_clear)]
 [!code-vb[TableSnippets2#_Table_Columns_Clear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_clear)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Tabellen](../../../../docs/framework/wpf/advanced/table-overview.md)  
 [Definieren einer Tabelle mit XAML](../../../../docs/framework/wpf/advanced/how-to-define-a-table-with-xaml.md)  
 [Programmgesteuertes Erstellen einer Tabelle](../../../../docs/framework/wpf/advanced/how-to-build-a-table-programmatically.md)  
 [Bearbeiten der Zeilengruppen einer Tabelle mit der RowGroups-Eigenschaft](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)  
 [Bearbeiten von einem FlowDocument mit der Blocks-Eigenschaft](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)  
 [Bearbeiten der Zeilengruppen einer Tabelle mit der RowGroups-Eigenschaft](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
