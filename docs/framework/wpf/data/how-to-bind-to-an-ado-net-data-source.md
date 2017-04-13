---
title: "Gewusst wie: Binden an eine ADO.NET-Datenquelle | Microsoft Docs"
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
  - "ADO.NET-Datenquellen, Binden an"
  - "Bindung, An ADO.NET-Datenquellen"
  - "Datenbindung, Bindung an ADO.NET-Datenquellen"
ms.assetid: a70c6d7b-7b38-4fdf-b655-4804db7c8315
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Binden an eine ADO.NET-Datenquelle
In diesem Beispiel wird gezeigt, wie ein [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.ListBox>\-Steuerelement an ein [!INCLUDE[TLA#tla_adonet](../../../../includes/tlasharptla-adonet-md.md)] `DataSet`\-Objekt gebunden wird.  
  
## Beispiel  
 In diesem Beispiel wird ein `OleDbConnection`\-Objekt zum Herstellen der Verbindung mit der Datenquelle verwendet, die als `Access MDB`\-Datei in der Verbindungszeichenfolge angegeben ist.  Nach dem Herstellen der Verbindung wird ein `OleDbDataAdpater`\-Objekt erstellt.  Das `OleDbDataAdpater`\-Objekt führt eine Select\-[!INCLUDE[TLA#tla_sql](../../../../includes/tlasharptla-sql-md.md)]\-Anweisung aus, um das Recordset aus der Datenbank abzurufen.  Die Ergebnisse des [!INCLUDE[TLA2#tla_sql](../../../../includes/tla2sharptla-sql-md.md)]\-Befehls werden in einer `DataTable` für das `DataSet` gespeichert, indem die `Fill`\-Methode für den `OleDbDataAdapter` aufgerufen wird.  Die `DataTable` in diesem Beispiel hat den Namen `BookTable`.  Im Beispiel wird dann die <xref:System.Windows.FrameworkElement.DataContext%2A>\-Eigenschaft für das <xref:System.Windows.Controls.ListBox>\-Element auf das `DataSet`\-Objekt festgelegt.  
  
 [!code-csharp[ADODataSet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 Dann kann die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>\-Eigenschaft für das <xref:System.Windows.Controls.ListBox> an die `BookTable` für das `DataSet` gebunden werden:  
  
 [!code-xml[ADODataSet#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#2)]  
  
 `BookItemTemplate` ist die <xref:System.Windows.DataTemplate>, die definiert, wie die Daten angezeigt werden:  
  
 [!code-xml[ADODataSet#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#3)]  
  
 Der `IntColorConverter` konvertiert `int` in eine Farbe.  Mithilfe dieses Konverters wird als <xref:System.Windows.Controls.TextBlock.Background%2A>\-Farbe für den dritten <xref:System.Windows.Controls.TextBlock> Grün verwendet, wenn der Wert für `NumPages` kleiner als 350 ist. Andernfalls wird Rot verwendet.  Die Implementierung des Konverters wird hier nicht erläutert.  
  
## Siehe auch  
 <xref:System.Windows.Data.BindingListCollectionView>   
 [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)