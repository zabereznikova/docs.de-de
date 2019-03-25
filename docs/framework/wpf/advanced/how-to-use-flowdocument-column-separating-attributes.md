---
title: 'Vorgehensweise: Verwenden von FlowDocument-Attributen für die Trennung von Spalten'
ms.date: 03/30/2017
helpviewer_keywords:
- FlowDocument column-separating attributes
- column-separating attributes
- documents [WPF], FlowDocument column-separating attributes
ms.assetid: c7a822f8-aeca-45bd-a258-2852ff28005c
ms.openlocfilehash: 27491b21da587fa198061ba52d8daed5d3f28de3
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2019
ms.locfileid: "58410900"
---
# <a name="how-to-use-flowdocument-column-separating-attributes"></a><span data-ttu-id="34dbe-102">Vorgehensweise: Verwenden von FlowDocument-Attributen für die Trennung von Spalten</span><span class="sxs-lookup"><span data-stu-id="34dbe-102">How to: Use FlowDocument Column-Separating Attributes</span></span>
<span data-ttu-id="34dbe-103">Dieses Beispiel zeigt, wie Sie mit die Trennung von Spalten Features von einem <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="34dbe-103">This example shows how to use the column-separating features of a <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34dbe-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="34dbe-104">Example</span></span>  
 <span data-ttu-id="34dbe-105">Das folgende Beispiel definiert eine <xref:System.Windows.Documents.FlowDocument>, und legt die <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, und <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> Attribute.</span><span class="sxs-lookup"><span data-stu-id="34dbe-105">The following example defines a <xref:System.Windows.Documents.FlowDocument>, and sets the <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, and <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> attributes.</span></span>  <span data-ttu-id="34dbe-106">Die <xref:System.Windows.Documents.FlowDocument> enthält einen einzelnen Absatz des Inhalts des Beispiels.</span><span class="sxs-lookup"><span data-stu-id="34dbe-106">The <xref:System.Windows.Documents.FlowDocument> contains a single paragraph of sample content.</span></span>  
  
 [!code-xaml[FlowDocumentSnippets#_FlowDocumentColumnStuffXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml#_flowdocumentcolumnstuffxaml)]  
  
 <span data-ttu-id="34dbe-107">Die folgende Abbildung zeigt die Auswirkungen der <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, und <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> Attribute in einem gerenderten <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="34dbe-107">The following figure shows the effects of the <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, and <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> attributes in a rendered <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 ![Screenshot mit dem Attribut FlowDocument Intra-Spalte.](./media/how-to-use-flowdocument-column-separating-attributes/flowdocument-intra-column.png)
