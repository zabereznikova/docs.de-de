---
title: "Gewusst wie: Bearbeiten der Spalten einer Tabelle mit der Columns-Eigenschaft | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Columns-Eigenschaft"
  - "Dokumente, Bearbeiten von Tabellenspalten"
  - "Eigenschaften, Spalten, Bearbeiten von Tabellenspalten"
  - "Tabellen, Bearbeiten von Spalten"
ms.assetid: 3f8884f4-7e1f-456b-be06-fbd3cf469bf3
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Gewusst wie: Bearbeiten der Spalten einer Tabelle mit der Columns-Eigenschaft
In diesem Beispiel werden einige Routinevorgänge veranschaulicht, die für die Spalten einer Tabelle mit der <xref:System.Windows.Documents.Table.Columns%2A>\-Eigenschaft ausgeführt werden können.  
  
## Beispiel  
 Im folgenden Beispiel wird eine neue Tabelle erstellt. Anschließend wird die <xref:System.Windows.Documents.TableColumnCollection.Add%2A>\-Methode verwendet, um Spalten zur <xref:System.Windows.Documents.Table.Columns%2A>\-Auflistung der Tabelle hinzuzufügen.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Add](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_add)]
 [!code-vb[TableSnippets2#_Table_Columns_Add](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_add)]  
  
## Beispiel  
 Im folgenden Beispiel wird eine neue <xref:System.Windows.Documents.TableColumn> eingefügt.  Die neue Spalte wird an Indexposition 0 eingefügt, wodurch sie zur neuen ersten Spalte in der Tabelle wird.  
  
> [!NOTE]
>  Die <xref:System.Windows.Documents.TableColumnCollection>\-Auflistung verwendet die nullbasierte Standardindizierung.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Insert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_insert)]
 [!code-vb[TableSnippets2#_Table_Columns_Insert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_insert)]  
  
## Beispiel  
 Im folgenden Beispiel wird auf einige beliebige Eigenschaften in Spalten in der <xref:System.Windows.Documents.TableColumnCollection>\-Auflistung zugriffen, wobei auf bestimmte Spalten über den Index verwiesen wird.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Manip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_manip)]
 [!code-vb[TableSnippets2#_Table_Columns_Manip](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_manip)]  
  
## Beispiel  
 Im folgenden Beispiel wird die Anzahl der momentan von der Tabelle gehosteten Spalten abgerufen.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Count](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_count)]
 [!code-vb[TableSnippets2#_Table_Columns_Count](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_count)]  
  
## Beispiel  
 Im folgenden Beispiel wird eine bestimmte Spalte nach Verweis entfernt.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelRef](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delref)]
 [!code-vb[TableSnippets2#_Table_Columns_DelRef](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delref)]  
  
## Beispiel  
 Im folgenden Beispiel wird eine bestimmte Spalte nach Index entfernt.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelIndex](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delindex)]
 [!code-vb[TableSnippets2#_Table_Columns_DelIndex](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delindex)]  
  
## Beispiel  
 Im folgenden Beispiel werden alle Spalten aus der Spaltenauflistung der Tabelle entfernt.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Clear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_clear)]
 [!code-vb[TableSnippets2#_Table_Columns_Clear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_clear)]  
  
## Siehe auch  
 [Übersicht über Tabellen](../../../../docs/framework/wpf/advanced/table-overview.md)   
 [Definieren einer Tabelle mit XAML](../../../../docs/framework/wpf/advanced/how-to-define-a-table-with-xaml.md)   
 [Programmgesteuertes Erstellen einer Tabelle](../../../../docs/framework/wpf/advanced/how-to-build-a-table-programmatically.md)   
 [Bearbeiten der Zeilengruppen einer Tabelle mit der RowGroups\-Eigenschaft](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)   
 [Bearbeiten von einem FlowDocument mit der Blocks\-Eigenschaft](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)   
 [Bearbeiten der Zeilengruppen einer Tabelle mit der RowGroups\-Eigenschaft](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)