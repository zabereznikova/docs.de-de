---
title: 'Vorgehensweise: Verwenden von FlowDocument-Attributen für die Trennung von Spalten'
ms.date: 03/30/2017
helpviewer_keywords:
- FlowDocument column-separating attributes
- column-separating attributes
- documents [WPF], FlowDocument column-separating attributes
ms.assetid: c7a822f8-aeca-45bd-a258-2852ff28005c
ms.openlocfilehash: 27491b21da587fa198061ba52d8daed5d3f28de3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032048"
---
# <a name="how-to-use-flowdocument-column-separating-attributes"></a>Vorgehensweise: Verwenden von FlowDocument-Attributen für die Trennung von Spalten
Dieses Beispiel zeigt, wie Sie mit die Trennung von Spalten Features von einem <xref:System.Windows.Documents.FlowDocument>.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel definiert eine <xref:System.Windows.Documents.FlowDocument>, und legt die <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, und <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> Attribute.  Die <xref:System.Windows.Documents.FlowDocument> enthält einen einzelnen Absatz des Inhalts des Beispiels.  
  
 [!code-xaml[FlowDocumentSnippets#_FlowDocumentColumnStuffXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml#_flowdocumentcolumnstuffxaml)]  
  
 Die folgende Abbildung zeigt die Auswirkungen der <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, und <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> Attribute in einem gerenderten <xref:System.Windows.Documents.FlowDocument>.  
  
 ![Screenshot mit dem Attribut FlowDocument Intra-Spalte.](./media/how-to-use-flowdocument-column-separating-attributes/flowdocument-intra-column.png)
