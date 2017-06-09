---
title: "Gewusst wie: Bearbeiten von fortlaufenden Inhaltselementen mit der Inlines-Eigenschaft | Microsoft Docs"
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
  - "Dokumente, Bearbeiten von fortlaufenden Inhaltselementen mit der Inlines-Eigenschaft"
  - "Fortlaufende Inhaltselemente, Bearbeiten mit der Inlines-Eigenschaft"
  - "Inlines-Eigenschaft, Bearbeiten der fortlaufenden Inhaltselemente"
  - "Eigenschaften, Inlines, Bearbeiten der fortlaufenden Inhaltselemente"
ms.assetid: 510780d2-3da1-4360-8763-7054bda22ea3
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Bearbeiten von fortlaufenden Inhaltselementen mit der Inlines-Eigenschaft
In diesen Beispielen werden einige Routinevorgänge veranschaulicht, die für fortlaufende Inlineinhaltselemente \(und Containern dieser Elemente wie <xref:System.Windows.Controls.TextBlock>\) über die **Inlines**\-Eigenschaft ausgeführt werden können.  Diese Eigenschaft wird verwendet, um Elemente zur <xref:System.Windows.Documents.InlineCollection> hinzuzufügen und daraus zu entfernen.  Fortlaufende Inhaltselemente mit einer **Inlines**\-Eigenschaft umfassen Folgendes:  
  
-   <xref:System.Windows.Documents.Bold>  
  
-   <xref:System.Windows.Documents.Hyperlink>  
  
-   <xref:System.Windows.Documents.Italic>  
  
-   <xref:System.Windows.Documents.Paragraph>  
  
-   <xref:System.Windows.Documents.Span>  
  
-   <xref:System.Windows.Documents.Underline>  
  
 In diesen Beispielen wird <xref:System.Windows.Documents.Span> als fortlaufendes Inhaltselement verwendet. Diese Techniken können jedoch auf alle Elemente oder Steuerelemente angewendet werden, die eine <xref:System.Windows.Documents.InlineCollection>\-Auflistung hosten.  
  
## Beispiel  
 Im folgenden Beispiel wird ein neues <xref:System.Windows.Documents.Span>\-Objekt erstellt. Danach werden mithilfe der **Add**\-Methode zwei Textausführungen als untergeordnete Inhaltselemente des <xref:System.Windows.Documents.Span>\-Objekts hinzugefügt.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
## Beispiel  
 Im folgenden Beispiel wird ein neues <xref:System.Windows.Documents.Run>\-Element erstellt und am Anfang von <xref:System.Windows.Documents.Span> eingefügt.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
## Beispiel  
 Im folgenden Beispiel wird die Anzahl der <xref:System.Windows.Documents.Inline>\-Elemente der obersten Ebene abgerufen, die im <xref:System.Windows.Documents.Span> enthalten sind.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesCount](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinescount)]
 [!code-vb[SpanSnippets#_SpanInlinesCount](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinescount)]  
  
## Beispiel  
 Im folgenden Beispiel wird das letzte <xref:System.Windows.Documents.Inline>\-Element in <xref:System.Windows.Documents.Span> gelöscht.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
## Beispiel  
 Im folgenden Beispiel wird der gesamte Inhalt \(<xref:System.Windows.Documents.Inline>\-Elemente\) aus <xref:System.Windows.Documents.Span> gelöscht.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
## Siehe auch  
 <xref:System.Windows.Documents.BlockCollection>   
 <xref:System.Windows.Documents.InlineCollection>   
 <xref:System.Windows.Documents.ListItemCollection>   
 [Übersicht über Flussdokumente](../../../../docs/framework/wpf/advanced/flow-document-overview.md)   
 [Bearbeiten von einem FlowDocument mit der Blocks\-Eigenschaft](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)   
 [Bearbeiten der Spalten einer Tabelle mit der Columns\-Eigenschaft](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)   
 [Bearbeiten der Zeilengruppen einer Tabelle mit der RowGroups\-Eigenschaft](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)