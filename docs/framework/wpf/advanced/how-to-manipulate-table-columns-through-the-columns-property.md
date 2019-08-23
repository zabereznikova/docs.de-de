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
ms.openlocfilehash: 18a26c76688ebf668293cb1254404d6d2cf15208
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913594"
---
# <a name="how-to-manipulate-a-tables-columns-through-the-columns-property"></a>Vorgehensweise: Bearbeiten der Spalten einer Tabelle mit der Columns-Eigenschaft
In diesem Beispiel werden einige der gängigeren Vorgänge veranschaulicht, die über die <xref:System.Windows.Documents.Table.Columns%2A> -Eigenschaft für die Spalten einer Tabelle ausgeführt werden können.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine neue Tabelle erstellt, und anschließend <xref:System.Windows.Documents.TableColumnCollection.Add%2A> wird die-Methode verwendet, um der <xref:System.Windows.Documents.Table.Columns%2A> -Auflistung der Tabelle Spalten hinzuzufügen.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Add](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_add)]
 [!code-vb[TableSnippets2#_Table_Columns_Add](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_add)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine neue <xref:System.Windows.Documents.TableColumn>eingefügt.  Die neue Spalte wird an der Indexposition 0 eingefügt, sodass Sie die neue erste Spalte in der Tabelle ist.  
  
> [!NOTE]
> Die <xref:System.Windows.Documents.TableColumnCollection> -Auflistung verwendet die standardmäßige NULL basierte Indizierung.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Insert](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_insert)]
 [!code-vb[TableSnippets2#_Table_Columns_Insert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_insert)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird auf einige beliebige Eigenschaften von Spalten in <xref:System.Windows.Documents.TableColumnCollection> der-Auflistung zugegriffen, die auf bestimmte Spalten nach Index verweisen.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Manip](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_manip)]
 [!code-vb[TableSnippets2#_Table_Columns_Manip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_manip)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Anzahl der Spalten abgerufen, die derzeit von der-Tabelle gehostet werden.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Count](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_count)]
 [!code-vb[TableSnippets2#_Table_Columns_Count](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_count)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine bestimmte Spalte als Verweis entfernt.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelRef](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delref)]
 [!code-vb[TableSnippets2#_Table_Columns_DelRef](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delref)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine bestimmte Spalte nach dem Index entfernt.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelIndex](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delindex)]
 [!code-vb[TableSnippets2#_Table_Columns_DelIndex](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delindex)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden alle Spalten aus der Columns-Auflistung der Tabelle entfernt.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Clear](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_clear)]
 [!code-vb[TableSnippets2#_Table_Columns_Clear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_clear)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Tabellen](table-overview.md)
- [Definieren einer Tabelle mit XAML](how-to-define-a-table-with-xaml.md)
- [Programmgesteuertes Erstellen einer Tabelle](how-to-build-a-table-programmatically.md)
- [Bearbeiten der Zeilengruppen einer Tabelle mit der RowGroups-Eigenschaft](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
- [Bearbeiten von einem FlowDocument mit der Blocks-Eigenschaft](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [Bearbeiten der Zeilengruppen einer Tabelle mit der RowGroups-Eigenschaft](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
