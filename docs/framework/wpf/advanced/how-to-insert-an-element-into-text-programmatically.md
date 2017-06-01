---
title: "Gewusst wie: Programmgesteuertes Einf&#252;gen eines Elements in Text | Microsoft Docs"
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
  - "Elemente, Einfügen in Text"
  - "Einfügen von Elementen in Text"
  - "Beispiel zu Textanimation"
  - "Text, Einfügen von Elementen"
  - "TextPointer-Objekte"
ms.assetid: 97bd950a-25ac-4e42-a311-94b6420d4136
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# Gewusst wie: Programmgesteuertes Einf&#252;gen eines Elements in Text
Im folgenden Beispiel wird gezeigt, wie mit zwei <xref:System.Windows.Documents.TextPointer>\-Objekten ein Bereich innerhalb von Text angegeben wird, auf den ein <xref:System.Windows.Documents.Span>\-Element angewendet wird.  
  
## Beispiel  
 [!code-csharp[FlowMiscSnippets_procedural_snip#InsertInlineIntoTextExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowMiscSnippets_procedural_snip/CSharp/InsertInlineIntoTextExample.cs#insertinlineintotextexamplewholepage)]
 [!code-vb[FlowMiscSnippets_procedural_snip#InsertInlineIntoTextExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowMiscSnippets_procedural_snip/VisualBasic/InsertInlineIntoTextExample.vb#insertinlineintotextexamplewholepage)]  
  
 Die unten stehende Abbildung zeigt, wie dieses Beispiel aussieht.  
  
 ![Ein auf einen Textbereich angewandtes SPAN&#45;Element](../../../../docs/framework/wpf/advanced/media/flow-insertelementintotextprogrammatically.png "Flow\_InsertElementIntoTextProgrammatically")  
  
## Siehe auch  
 [Übersicht über Flussdokumente](../../../../docs/framework/wpf/advanced/flow-document-overview.md)