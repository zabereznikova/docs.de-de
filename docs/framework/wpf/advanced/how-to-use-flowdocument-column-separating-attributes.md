---
title: 'Gewusst wie: Verwenden von FlowDocument-Attributen für die Trennung von Spalten'
ms.date: 03/30/2017
helpviewer_keywords:
- FlowDocument column-separating attributes
- column-separating attributes
- documents [WPF], FlowDocument column-separating attributes
ms.assetid: c7a822f8-aeca-45bd-a258-2852ff28005c
ms.openlocfilehash: 678e01a35c286ea03f0385291d64f2f900f068c5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543770"
---
# <a name="how-to-use-flowdocument-column-separating-attributes"></a>Gewusst wie: Verwenden von FlowDocument-Attributen für die Trennung von Spalten
In diesem Beispiel wird gezeigt, wie die Trennung von Spalten Funktionen verwendet einen <xref:System.Windows.Documents.FlowDocument>.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel definiert eine <xref:System.Windows.Documents.FlowDocument>, und legt die <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, und <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> Attribute.  Die <xref:System.Windows.Documents.FlowDocument> enthält einen einzelnen Textabsatz Beispielinhalte.  
  
 [!code-xaml[FlowDocumentSnippets#_FlowDocumentColumnStuffXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml#_flowdocumentcolumnstuffxaml)]  
  
 Die folgende Abbildung zeigt die Auswirkungen der <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, und <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> Attribute in einem gerenderten <xref:System.Windows.Documents.FlowDocument>.  
  
 ![Bildschirmabbildung: FlowDocument Intra-Spalte](../../../../docs/framework/wpf/advanced/media/flowdocumentintracolumn.png "FlowDocumentIntraColumn")
