---
title: "Gewusst wie: Bearbeiten von einem FlowDocument mit der Blocks-Eigenschaft | Microsoft Docs"
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
  - "Blocks-Eigenschaft, Bearbeiten von FlowDocuments"
  - "Dokumente, Bearbeiten von FlowDocuments mit der Blocks-Eigenschaft"
  - "FlowDocuments, Bearbeiten mit der Blocks-Eigenschaft"
  - "Eigenschaften, Blöcke, Bearbeiten von FlowDocuments"
ms.assetid: cbb7291e-3f1b-433e-9e16-f4d93ced14e8
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Gewusst wie: Bearbeiten von einem FlowDocument mit der Blocks-Eigenschaft
In diesen Beispielen werden einige Routinevorgänge veranschaulicht, die für ein <xref:System.Windows.Documents.FlowDocument> mit der <xref:System.Windows.Documents.FlowDocument.Blocks%2A>\-Eigenschaft ausgeführt werden können.  
  
## Beispiel  
 Im folgenden Beispiel wird ein neues <xref:System.Windows.Documents.FlowDocument> erstellt, und dann wird ein neues <xref:System.Windows.Documents.Paragraph>\-Element an das <xref:System.Windows.Documents.FlowDocument> angefügt.  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblocksadd)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblocksadd)]  
  
## Beispiel  
 Im folgenden Beispiel wird ein neues <xref:System.Windows.Documents.Paragraph>\-Element erstellt und am Anfang vom <xref:System.Windows.Documents.FlowDocument> eingefügt.  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksInsert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblocksinsert)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksInsert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblocksinsert)]  
  
## Beispiel  
 Im folgenden Beispiel wird die Anzahl der <xref:System.Windows.Documents.Block>\-Elemente der obersten Ebene abgerufen, die im <xref:System.Windows.Documents.FlowDocument> enthalten sind.  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksCount](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblockscount)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksCount](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblockscount)]  
  
## Beispiel  
 Im folgenden Beispiel wird das letzte <xref:System.Windows.Documents.Block>\-Element im <xref:System.Windows.Documents.FlowDocument> gelöscht.  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblocksremovelast)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblocksremovelast)]  
  
## Beispiel  
 Im folgenden Beispiel wird der gesamte Inhalt \(<xref:System.Windows.Documents.Block>\-Elemente\) aus dem <xref:System.Windows.Documents.FlowDocument> gelöscht.  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblocksclear)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblocksclear)]  
  
## Siehe auch  
 [Bearbeiten der Zeilengruppen einer Tabelle mit der RowGroups\-Eigenschaft](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)   
 [Bearbeiten der Spalten einer Tabelle mit der Columns\-Eigenschaft](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)   
 [Bearbeiten der Zeilengruppen einer Tabelle mit der RowGroups\-Eigenschaft](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)