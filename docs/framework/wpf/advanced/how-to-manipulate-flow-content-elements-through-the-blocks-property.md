---
title: "Gewusst wie: Bearbeiten von fortlaufenden Inhaltselementen mit der Blocks-Eigenschaft | Microsoft Docs"
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
  - "Blocks-Eigenschaft, Bearbeiten von fortlaufenden Inhaltselementen"
  - "Dokumente, Bearbeiten von fortlaufenden Inhaltselementen mit der Blocks-Eigenschaft"
  - "Fortlaufende Inhaltselemente, Bearbeiten mit der Blocks-Eigenschaft"
  - "Eigenschaften, Blöcke, Bearbeiten von fortlaufenden Inhaltselementen"
ms.assetid: aeda4ece-b979-4818-a093-ef938e908751
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Gewusst wie: Bearbeiten von fortlaufenden Inhaltselementen mit der Blocks-Eigenschaft
In diesen Beispielen werden einige Routinevorgänge veranschaulicht, die für fortlaufende Inhaltselemente mit der **Blocks**\-Eigenschaft ausgeführt werden können.  Diese Eigenschaft wird verwendet, um Elemente zu <xref:System.Windows.Documents.BlockCollection> hinzuzufügen und daraus zu entfernen.  Fortlaufende Inhaltselemente mit einer **Blocks**\-Eigenschaft umfassen Folgendes:  
  
-   <xref:System.Windows.Documents.Figure>  
  
-   <xref:System.Windows.Documents.Floater>  
  
-   <xref:System.Windows.Documents.ListItem>  
  
-   <xref:System.Windows.Documents.Section>  
  
-   <xref:System.Windows.Documents.TableCell>  
  
 In diesen Beispielen wird <xref:System.Windows.Documents.Section> als fortlaufendes Inhaltselement verwendet. Diese Techniken können jedoch auf alle Elemente angewendet werden, die eine Auflistung von fortlaufenden Inhaltselementen hosten.  
  
## Beispiel  
 Im folgenden Beispiel wird ein neuer <xref:System.Windows.Documents.Section> erstellt und anschließend mit der **Add**\-Methode ein neuer Absatz zu den **Section**\-Inhalten hinzugefügt.  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksadd)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksadd)]  
  
## Beispiel  
 Im folgenden Beispiel wird ein neues <xref:System.Windows.Documents.Paragraph>\-Element erstellt und am Anfang vom <xref:System.Windows.Documents.Section> eingefügt.  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksInsert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksinsert)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksInsert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksinsert)]  
  
## Beispiel  
 Im folgenden Beispiel wird die Anzahl der <xref:System.Windows.Documents.Block>\-Elemente der obersten Ebene abgerufen, die im <xref:System.Windows.Documents.Section> enthalten sind.  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksCount](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblockscount)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksCount](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblockscount)]  
  
## Beispiel  
 Im folgenden Beispiel wird das letzte <xref:System.Windows.Documents.Block>\-Element im <xref:System.Windows.Documents.Section> gelöscht.  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksremovelast)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksremovelast)]  
  
## Beispiel  
 Im folgenden Beispiel wird der gesamte Inhalt \(<xref:System.Windows.Documents.Block>\-Elemente\) aus dem <xref:System.Windows.Documents.Section> gelöscht.  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksclear)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksclear)]  
  
## Siehe auch  
 <xref:System.Windows.Documents.BlockCollection>   
 <xref:System.Windows.Documents.InlineCollection>   
 <xref:System.Windows.Documents.ListItemCollection>   
 [Übersicht über Flussdokumente](../../../../docs/framework/wpf/advanced/flow-document-overview.md)   
 [Bearbeiten der Zeilengruppen einer Tabelle mit der RowGroups\-Eigenschaft](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)   
 [Bearbeiten der Spalten einer Tabelle mit der Columns\-Eigenschaft](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)   
 [Bearbeiten der Zeilengruppen einer Tabelle mit der RowGroups\-Eigenschaft](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)