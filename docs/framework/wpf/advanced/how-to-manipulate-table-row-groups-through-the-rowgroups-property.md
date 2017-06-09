---
title: "Gewusst wie: Bearbeiten der Zeilengruppen einer Tabelle mit der RowGroups-Eigenschaft | Microsoft Docs"
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
  - "Dokumente, Bearbeiten von Zeilengruppen mit der RowGroups-Eigenschaft"
  - "Eigenschaften, RowGroups, Bearbeiten von Zeilengruppen"
  - "Zeilengruppen, Bearbeiten mit der RowGroups-Eigenschaft"
  - "RowGroups-Eigenschaft, Bearbeiten von Zeilengruppen"
ms.assetid: ea61440f-08ae-44ed-b314-5716aaaae3ed
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Bearbeiten der Zeilengruppen einer Tabelle mit der RowGroups-Eigenschaft
In diesem Beispiel werden einige Routinevorgänge veranschaulicht, die für die Zeilengruppen einer Tabelle mit der <xref:System.Windows.Documents.Table.RowGroups%2A>\-Eigenschaft ausgeführt werden können.  
  
## Beispiel  
 Im folgenden Beispiel wird eine neue Tabelle erstellt. Anschließend wird die <xref:System.Windows.Documents.TableRowGroupCollection.Add%2A>\-Methode verwendet, um Spalten zur <xref:System.Windows.Documents.Table.RowGroups%2A>\-Auflistung der Tabelle hinzuzufügen.  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Add](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_add)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Add](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_add)]  
  
## Beispiel  
 Im folgenden Beispiel wird eine neue <xref:System.Windows.Documents.TableRowGroup> eingefügt.  Die neue Spalte wird an Indexposition 0 eingefügt, wodurch sie zur neuen ersten Zeilengruppe in der Tabelle wird.  
  
> [!NOTE]
>  Die <xref:System.Windows.Documents.TableRowGroupCollection>\-Auflistung verwendet die nullbasierte Standardindizierung.  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Insert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_insert)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Insert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_insert)]  
  
## Beispiel  
 Im folgenden Beispiel werden mehrere Zeilen einer bestimmten \(vom Index angegebenen\) <xref:System.Windows.Documents.TableRowGroup> in der Tabelle hinzugefügt.  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_AddRows](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_addrows)]
 [!code-vb[TableSnippets2#_Table_RowGroups_AddRows](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_addrows)]  
  
## Beispiel  
 Das folgende Beispiel greift auf einige beliebige Eigenschaften in Zeilen in der ersten Zeilengruppe in der Tabelle zu.  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_ManipRows](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_maniprows)]
 [!code-vb[TableSnippets2#_Table_RowGroups_ManipRows](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_maniprows)]  
  
## Beispiel  
 Im folgenden Beispiel werden mehrere Zellen einer bestimmten \(vom Index angegebenen\) <xref:System.Windows.Documents.TableRow> in der Tabelle hinzugefügt.  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_AddCells](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_addcells)]
 [!code-vb[TableSnippets2#_Table_RowGroups_AddCells](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_addcells)]  
  
## Beispiel  
 Das folgende Beispiel greift auf einige beliebige Methoden und Eigenschaften in Zellen in der ersten Zeile in der ersten Zeilengruppe zu.  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_ManipCells](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_manipcells)]
 [!code-vb[TableSnippets2#_Table_RowGroups_ManipCells](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_manipcells)]  
  
## Beispiel  
 Im folgenden Beispiel wird die Zahl der von der Tabelle gehosteten <xref:System.Windows.Documents.TableRowGroup>\-Elemente zurückgegeben.  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Count](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_count)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Count](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_count)]  
  
## Beispiel  
 Im folgenden Beispiel wird eine bestimmte Zeilengruppe nach Verweis entfernt.  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_DelRef](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_delref)]
 [!code-vb[TableSnippets2#_Table_RowGroups_DelRef](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_delref)]  
  
## Beispiel  
 Im folgenden Beispiel wird eine bestimmte Zeilengruppe nach Index entfernt.  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_DelIndex](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_delindex)]
 [!code-vb[TableSnippets2#_Table_RowGroups_DelIndex](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_delindex)]  
  
## Beispiel  
 Im folgenden Beispiel werden alle Zeilengruppen aus der Zeilengruppenauflistung der Tabelle entfernt.  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Clear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_clear)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Clear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_clear)]  
  
## Siehe auch  
 [How\-to: Manipulate Flow Content Elements through the Inlines Property](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)   
 [Bearbeiten von einem FlowDocument mit der Blocks\-Eigenschaft](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)   
 [Bearbeiten der Spalten einer Tabelle mit der Columns\-Eigenschaft](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)