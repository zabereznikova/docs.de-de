---
title: "Gewusst wie: Verwenden von FlowDocument-Attributen für die Trennung von Spalten"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FlowDocument column-separating attributes
- column-separating attributes
- documents [WPF], FlowDocument column-separating attributes
ms.assetid: c7a822f8-aeca-45bd-a258-2852ff28005c
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7e4a300acccd0c6915844c988a4bbc81426f90f0
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-use-flowdocument-column-separating-attributes"></a>Gewusst wie: Verwenden von FlowDocument-Attributen für die Trennung von Spalten
In diesem Beispiel wird gezeigt, wie die Trennung von Spalten Funktionen verwendet einen <xref:System.Windows.Documents.FlowDocument>.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel definiert eine <xref:System.Windows.Documents.FlowDocument>, und legt die <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, und <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> Attribute.  Die <xref:System.Windows.Documents.FlowDocument> enthält einen einzelnen Textabsatz Beispielinhalte.  
  
 [!code-xaml[FlowDocumentSnippets#_FlowDocumentColumnStuffXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml#_flowdocumentcolumnstuffxaml)]  
  
 Die folgende Abbildung zeigt die Auswirkungen der <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, und <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> Attribute in einem gerenderten <xref:System.Windows.Documents.FlowDocument>.  
  
 ![Bildschirmabbildung: FlowDocument Intra-Spalte](../../../../docs/framework/wpf/advanced/media/flowdocumentintracolumn.png "FlowDocumentIntraColumn")
