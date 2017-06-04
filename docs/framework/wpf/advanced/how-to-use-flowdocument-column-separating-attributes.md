---
title: "Gewusst wie: Verwenden von FlowDocument-Attributen f&#252;r die Trennung von Spalten | Microsoft Docs"
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
  - "Attribute für die Trennung von Spalten"
  - "Dokumente, FlowDocument-Attribute für die Trennung von Spalten"
  - "FlowDocument-Attribute für die Trennung von Spalten"
ms.assetid: c7a822f8-aeca-45bd-a258-2852ff28005c
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Gewusst wie: Verwenden von FlowDocument-Attributen f&#252;r die Trennung von Spalten
Dieses Beispiel zeigt, wie die <xref:System.Windows.Documents.FlowDocument>\-Features für das Trennen von Spalten verwendet werden.  
  
## Beispiel  
 Im folgenden Beispiel wird ein <xref:System.Windows.Documents.FlowDocument> definiert. Anschließend werden die Attribute <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A> und <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> festgelegt.  Das <xref:System.Windows.Documents.FlowDocument> enthält einen einzelnen Absatz mit Beispielinhalt.  
  
 [!code-xml[FlowDocumentSnippets#_FlowDocumentColumnStuffXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml#_flowdocumentcolumnstuffxaml)]  
  
 Die folgende Abbildung zeigt die Auswirkungen der Attribute <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A> und <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> in einem gerenderten <xref:System.Windows.Documents.FlowDocument>.  
  
 ![Bildschirmabbildung: FlowDocument Intra&#45;Spalte](../../../../docs/framework/wpf/advanced/media/flowdocumentintracolumn.png "FlowDocumentIntraColumn")