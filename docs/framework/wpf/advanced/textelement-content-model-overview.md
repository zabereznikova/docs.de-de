---
title: "Übersicht über das TextElement-Inhaltsmodell"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- documents [WPF], flow documents
- TextElement content model [WPF]
- flow content elements [WPF], TextElement content model
ms.assetid: d0a7791c-b090-438c-812f-b9d009d83ee9
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 95d25ff6819ba913b7e9270bc2d87dd77032c5c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="textelement-content-model-overview"></a>Übersicht über das TextElement-Inhaltsmodell
In dieser Übersicht Inhaltsmodell beschreibt die unterstützten Inhalte für eine <xref:System.Windows.Documents.TextElement>. Die <xref:System.Windows.Documents.Paragraph> Klasse ist eine Art von <xref:System.Windows.Documents.TextElement>. Ein Inhaltsmodell beschreibt, welche Objekte/Elemente in anderen enthalten sein können. In dieser Übersicht werden zusammengefasst, das Inhaltsmodell für Objekte, die von abgeleiteten verwendet <xref:System.Windows.Documents.TextElement>. Weitere Informationen finden Sie unter [Flow Document Overview](../../../../docs/framework/wpf/advanced/flow-document-overview.md).  
  
  
<a name="text_element_classes"></a>   
## <a name="content-model-diagram"></a>Inhaltsmodelldiagramm  
 Das folgende Diagramm fasst das Inhaltsmodell für Klassen abgeleitete <xref:System.Windows.Documents.TextElement> sowie andere nicht- `TextElement` Klassen, die in dieses Modell passen.  
  
 ![Diagramm: Flussinhalt-Einschlussschema](../../../../docs/framework/wpf/advanced/media/flow-content-schema.png "Flow_Content_Schema")  
  
 Wie aus dem vorherigen Diagramm ersichtlich, die nach einem Element zulässigen untergeordneten Elemente sind nicht unbedingt bestimmt, ob von eine Klasse abgeleitet ist die <xref:System.Windows.Documents.Block> Klasse oder eine <xref:System.Windows.Documents.Inline> Klasse. Z. B. eine <xref:System.Windows.Documents.Span> (ein <xref:System.Windows.Documents.Inline>-abgeleitete Klasse) ist nur zulässig <xref:System.Windows.Documents.Inline> untergeordnete Elemente, aber ein <xref:System.Windows.Documents.Figure> (auch eine <xref:System.Windows.Documents.Inline>-abgeleitete Klasse) ist nur zulässig <xref:System.Windows.Documents.Block> untergeordnete Elemente. Aus diesem Grund ist ein Diagramm nützlich, um schnell zu bestimmen, welches Element in einem anderen eingeschlossen sein kann. Beispielsweise ermöglicht die Verwendung des Diagramms bestimmen, wie zum Erstellen von fortlaufenden Inhalt von einem <xref:System.Windows.Controls.RichTextBox>.  
  
1.  Ein <xref:System.Windows.Controls.RichTextBox> darf eine <xref:System.Windows.Documents.FlowDocument> enthalten wiederum müssen eine <xref:System.Windows.Documents.Block>-abgeleitetes Objekt. Im Folgenden wird das entsprechende Segment aus dem vorherigen Diagramm dargestellt.  
  
     ![Diagramm: RichTextBox-Einschlussregeln](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough1.png "Flow_Ovw_SchemaWalkThrough1")  
  
     Bis jetzt könnte das Markup wie folgt aussehen.  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]  
  
2.  Gemäß dem Diagramm stehen verschiedene <xref:System.Windows.Documents.Block> Elemente einschließlich auswählbarer <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.List>, und <xref:System.Windows.Documents.BlockUIContainer> (Siehe Block abgeleitete Klassen in der obigen Abbildung). Angenommen, wir möchten einen <xref:System.Windows.Documents.Table>. Gemäß der obigen Abbildung eine <xref:System.Windows.Documents.Table> enthält eine <xref:System.Windows.Documents.TableRowGroup> mit <xref:System.Windows.Documents.TableRow> Elemente, die enthalten <xref:System.Windows.Documents.TableCell> -Elemente enthalten eine <xref:System.Windows.Documents.Block>-abgeleitetes Objekt. Im folgenden finden Sie die entsprechende Segment für <xref:System.Windows.Documents.Table> aus dem vorherigen Diagramm übernommen.  
  
     ![Diagramm: Übergeordnet&#47;Untergeordnet-Schema für Table](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough2.png "Flow_Ovw_SchemaWalkThrough2")  
  
     Im Folgenden wird das entsprechende Markup dargestellt.  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]  
  
3.  Erneut, eine oder mehrere <xref:System.Windows.Documents.Block> Elemente sind erforderlich, darunter eine <xref:System.Windows.Documents.TableCell>. Um es einfach zu gestalten, fügen wir Text in die Zelle ein. Wir können dazu eine <xref:System.Windows.Documents.Paragraph> mit einem <xref:System.Windows.Documents.Run> Element. Im folgenden finden Sie die entsprechenden Segmente aus dem Diagramm anzeigen, die eine <xref:System.Windows.Documents.Paragraph> dauert ein <xref:System.Windows.Documents.Inline> -Element und einem <xref:System.Windows.Documents.Run> (ein <xref:System.Windows.Documents.Inline> Element) dauert nur nur-Text.  
  
     ![Diagramm: Übergeordnet&#47;Untergeordnet-Schema für Paragraph](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough3.png "Flow_Ovw_SchemaWalkThrough3")  
  
     ![Diagramm: Übergeordnet&#47;Untergeordnet-Schema für Run](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough4.png "Flow_Ovw_SchemaWalkThrough4")  
  
 Nachstehend finden Sie das gesamte Beispiel im Markup.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]  
  
<a name="Using_the_Content_Property"></a>   
## <a name="working-with-textelement-content-programmatically"></a>Programmgesteuertes Arbeiten mit TextElement-Inhalt  
 Den Inhalt einer <xref:System.Windows.Documents.TextElement> von Sammlungen und daher die programmgesteuert ändern des Inhalts besteht <xref:System.Windows.Documents.TextElement> Objekte erfolgt durch arbeiten mit diesen Auflistungen. Es gibt drei verschiedene Sammlungen von verwendeten <xref:System.Windows.Documents.TextElement> -Klassen abgeleitet:  
  
-   <xref:System.Windows.Documents.InlineCollection>: Stellt eine Auflistung von <xref:System.Windows.Documents.Inline> Elemente. <xref:System.Windows.Documents.InlineCollection>definiert den zulässigen untergeordneten Inhalt, der die <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Span>, und <xref:System.Windows.Controls.TextBlock> Elemente.  
  
-   <xref:System.Windows.Documents.BlockCollection>: Stellt eine Auflistung von <xref:System.Windows.Documents.Block> Elemente. <xref:System.Windows.Documents.BlockCollection> definiert den zulässigen untergeordneten Inhalt der Elemente <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.TableCell>, <xref:System.Windows.Documents.Floater> und <xref:System.Windows.Documents.Figure>.  
  
-   <xref:System.Windows.Documents.ListItemCollection>: Ein fortlaufendes Inhaltselement, das ein bestimmtes Inhaltselement in einem geordneten darstellt oder ungeordnete <xref:System.Windows.Documents.List>.  
  
 Sie können bearbeiten (hinzufügen oder Entfernen von Elementen) aus diesen Auflistungen mit den jeweiligen Eigenschaften des **Inlines**, **Blöcke**, und **ListItems**. Den folgenden Beispielen wird veranschaulicht, wie der Inhalt einer Span mit bearbeitet die **Inlines** Eigenschaft.  
  
> [!NOTE]
>  Table verwendet mehrere Auflistungen, um den Inhalt zu bearbeiten. Diese werden hier aber nicht aufgeführt. Weitere Informationen finden Sie unter [Table Overview](../../../../docs/framework/wpf/advanced/table-overview.md).  
  
 Das folgende Beispiel erstellt ein neues <xref:System.Windows.Documents.Span> Objekt zugewiesen und dann verwendet der `Add` Methode zum Hinzufügen von zwei Text ausgeführt wird als Inhalt untergeordnete Elemente von der <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
 Das folgende Beispiel erstellt ein neues <xref:System.Windows.Documents.Run> Element und fügt es am Anfang der <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
 Das folgende Beispiel löscht die letzte <xref:System.Windows.Documents.Inline> Element in der <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
 Das folgende Beispiel löscht den Inhalt (<xref:System.Windows.Documents.Inline> Elemente) aus dem <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
<a name="Types_that_Share_this_Content_Model"></a>   
## <a name="types-that-share-this-content-model"></a>Typen, für die dieses Inhaltsmodell freigegeben ist  
 Die folgenden Typen erben die <xref:System.Windows.Documents.TextElement> Klasse und kann verwendet werden, um den Inhalt in dieser Übersicht beschriebene anzuzeigen.  
  
 <xref:System.Windows.Documents.Bold>, <xref:System.Windows.Documents.Figure>, <xref:System.Windows.Documents.Floater>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Documents.InlineUIContainer>, <xref:System.Windows.Documents.Italic>, <xref:System.Windows.Documents.LineBreak>, <xref:System.Windows.Documents.List>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Run>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Span>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.Underline>.  
  
 Beachten Sie, dass diese Liste nur nicht abstrakte Typen, die mit distributed enthält die [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)]. Sie können andere Typen, die von erben <xref:System.Windows.Documents.TextElement>.  
  
<a name="Types_that_Can_Contain_ContentControl_Objects"></a>   
## <a name="types-that-can-contain-textelement-objects"></a>Typen, die TextElement-Objekte enthalten können  
 Finden Sie unter [WPF-Inhaltsmodell](../../../../docs/framework/wpf/controls/wpf-content-model.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Bearbeiten von einem FlowDocument mit der Blocks-Eigenschaft](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)  
 [Bearbeiten von fortlaufenden Inhaltselementen mit der Blocks-Eigenschaft](../../../../docs/framework/wpf/advanced/how-to-manipulate-flow-content-elements-through-the-blocks-property.md)  
 [Bearbeiten von einem FlowDocument mit der Blocks-Eigenschaft](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)  
 [Bearbeiten der Spalten einer Tabelle mit der Columns-Eigenschaft](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)  
 [Bearbeiten der Zeilengruppen einer Tabelle mit der RowGroups-Eigenschaft](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
