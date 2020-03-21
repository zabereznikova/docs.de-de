---
title: Übersicht über das TextElement-Inhaltsmodell
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- documents [WPF], flow documents
- TextElement content model [WPF]
- flow content elements [WPF], TextElement content model
ms.assetid: d0a7791c-b090-438c-812f-b9d009d83ee9
ms.openlocfilehash: ddb2613dc924424b5f4b9d90f06d44b45b7b5e77
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186906"
---
# <a name="textelement-content-model-overview"></a>Übersicht über das TextElement-Inhaltsmodell
Diese Inhaltsmodellübersicht beschreibt den <xref:System.Windows.Documents.TextElement>unterstützten Inhalt für eine . Die <xref:System.Windows.Documents.Paragraph> Klasse ist <xref:System.Windows.Documents.TextElement>ein Typ von . Ein Inhaltsmodell beschreibt, welche Objekte/Elemente in anderen enthalten sein können. Diese Übersicht fasst das Inhaltsmodell zusammen, das für Objekte verwendet wird, die von <xref:System.Windows.Documents.TextElement>abgeleitet wurden. Weitere Informationen finden Sie unter [Flussdokumentübersicht](flow-document-overview.md).  

<a name="text_element_classes"></a>
## <a name="content-model-diagram"></a>Inhaltsmodelldiagramm  
 Das folgende Diagramm fasst das Inhaltsmodell <xref:System.Windows.Documents.TextElement> für Klassen zusammen, `TextElement` die von diesem Modell abgeleitet wurden, sowie wie andere Nicht-Klassen in dieses Modell passen.  
  
 ![Diagramm: Flussinhalt-Kapselungsschema](./media/flow-content-schema.png "Flow_Content_Schema")  
  
 Wie aus dem obigen Diagramm hervorgeht, werden die untergeordneten Elemente, die für <xref:System.Windows.Documents.Block> ein <xref:System.Windows.Documents.Inline> Element zugelassen sind, nicht notwendigerweise davon bestimmt, ob eine Klasse von der Klasse oder einer Klasse abgeleitet wird. Beispielsweise kann <xref:System.Windows.Documents.Span> eine <xref:System.Windows.Documents.Inline>(eine -abgeleitete <xref:System.Windows.Documents.Inline> Klasse) nur <xref:System.Windows.Documents.Figure> untergeordnete Elemente <xref:System.Windows.Documents.Inline>haben, aber eine <xref:System.Windows.Documents.Block> (auch eine -abgeleitete Klasse) kann nur untergeordnete Elemente enthalten. Aus diesem Grund ist ein Diagramm nützlich, um schnell zu bestimmen, welches Element in einem anderen eingeschlossen sein kann. Als Beispiel verwenden wir das Diagramm, um zu bestimmen, <xref:System.Windows.Controls.RichTextBox>wie der Flussinhalt einer erstellt wird.  
  
1. A <xref:System.Windows.Controls.RichTextBox> muss <xref:System.Windows.Documents.FlowDocument> ein enthalten, das <xref:System.Windows.Documents.Block>wiederum ein -derived-Objekt enthalten muss. Im Folgenden wird das entsprechende Segment aus dem vorherigen Diagramm dargestellt.  
  
     ![Diagramm: RichTextBox-Kapselungsregeln](./media/flow-ovw-schemawalkthrough1.png "Flow_Ovw_SchemaWalkThrough1")  
  
     Bis jetzt könnte das Markup wie folgt aussehen.  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough1](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]  
  
2. Je nach Diagramm gibt <xref:System.Windows.Documents.Block> es mehrere Elemente <xref:System.Windows.Documents.Paragraph> <xref:System.Windows.Documents.Section>zur <xref:System.Windows.Documents.Table> <xref:System.Windows.Documents.List>Auswahl, <xref:System.Windows.Documents.BlockUIContainer> einschließlich , , , und (siehe Block-abgeleitete Klassen im vorherigen Diagramm). Nehmen wir an, <xref:System.Windows.Documents.Table>wir wollen eine . Nach dem vorhergehenden <xref:System.Windows.Documents.Table> Diagramm <xref:System.Windows.Documents.TableRowGroup> <xref:System.Windows.Documents.TableRow> enthält a <xref:System.Windows.Documents.TableCell> ein enthaltende <xref:System.Windows.Documents.Block>Elemente, die Elemente enthalten, die ein -derived-Objekt enthalten. Im Folgenden finden Sie <xref:System.Windows.Documents.Table> das entsprechende Segment für das vorhergehende Diagramm.  
  
     ![Diagramm: Übergeordnetes&#47;untergeordnetes Schema für Tabelle](./media/flow-ovw-schemawalkthrough2.png "Flow_Ovw_SchemaWalkThrough2")  
  
     Im Folgenden wird das entsprechende Markup dargestellt.  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough2](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]  
  
3. Auch hier sind <xref:System.Windows.Documents.Block> ein oder <xref:System.Windows.Documents.TableCell>mehrere Elemente unter einer erforderlich. Um es einfach zu gestalten, fügen wir Text in die Zelle ein. Wir können dies <xref:System.Windows.Documents.Paragraph> mit <xref:System.Windows.Documents.Run> einem mit einem Element tun. Im Folgenden sind die entsprechenden Segmente <xref:System.Windows.Documents.Paragraph> aus <xref:System.Windows.Documents.Inline> dem Diagramm <xref:System.Windows.Documents.Run> dargestellt, <xref:System.Windows.Documents.Inline> die zeigen, dass ein Element ein Element annehmen kann und dass ein (ein Element) nur Nur-Text verwenden kann.  
  
     ![Diagramm: Parent&#47;child schema for Paragraph](./media/flow-ovw-schemawalkthrough3.png "Flow_Ovw_SchemaWalkThrough3")  
  
     ![Diagramm: Übergeordnetes&#47;Untergeordnetes Schema für Die Ausführung](./media/flow-ovw-schemawalkthrough4.png "Flow_Ovw_SchemaWalkThrough4")  
  
 Nachstehend finden Sie das gesamte Beispiel im Markup.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]  
  
<a name="Using_the_Content_Property"></a>
## <a name="working-with-textelement-content-programmatically"></a>Programmgesteuertes Arbeiten mit TextElement-Inhalt  
 Der Inhalt <xref:System.Windows.Documents.TextElement> von a besteht aus Auflistungen und so <xref:System.Windows.Documents.TextElement> erfolgt die programmgesteuerte Manipulation des Inhalts von Objekten durch die Arbeit mit diesen Sammlungen. Es gibt drei verschiedene <xref:System.Windows.Documents.TextElement> Auflistungen, die von -derived-Klassen verwendet werden:  
  
- <xref:System.Windows.Documents.InlineCollection>: Stellt eine <xref:System.Windows.Documents.Inline> Auflistung von Elementen dar. <xref:System.Windows.Documents.InlineCollection> definiert den zulässigen untergeordneten Inhalt der Elemente <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Span> und <xref:System.Windows.Controls.TextBlock>.  
  
- <xref:System.Windows.Documents.BlockCollection>: Stellt eine <xref:System.Windows.Documents.Block> Auflistung von Elementen dar. <xref:System.Windows.Documents.BlockCollection> definiert den zulässigen untergeordneten Inhalt der Elemente <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.TableCell>, <xref:System.Windows.Documents.Floater> und <xref:System.Windows.Documents.Figure>.  
  
- <xref:System.Windows.Documents.ListItemCollection>: Ein Flow-Content-Element, das ein bestimmtes <xref:System.Windows.Documents.List>Inhaltselement in einem geordneten oder ungeordneten darstellt.  
  
 Sie können diese Auflistungen mithilfe der entsprechenden Eigenschaften von **Inlines**, **Blocks**und **ListItems**bearbeiten (hinzufügen oder entfernen). Die folgenden Beispiele zeigen, wie Sie den Inhalt eines Span mithilfe der **Inlines-Eigenschaft** bearbeiten.  
  
> [!NOTE]
> Table verwendet mehrere Auflistungen, um den Inhalt zu bearbeiten. Diese werden hier aber nicht aufgeführt. Weitere Informationen finden Sie unter [Tabellenübersicht](table-overview.md).  
  
 Im folgenden Beispiel <xref:System.Windows.Documents.Span> wird ein neues `Add` Objekt erstellt, und dann wird <xref:System.Windows.Documents.Span>die Methode zum Hinzufügen von zwei Textläufen als untergeordneter Inhalt der verwendet.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
 Im folgenden Beispiel <xref:System.Windows.Documents.Run> wird ein neues Element erstellt <xref:System.Windows.Documents.Span>und am Anfang der eingefügt.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
 Im folgenden Beispiel wird <xref:System.Windows.Documents.Inline> das <xref:System.Windows.Documents.Span>letzte Element im gelöscht.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
 Im folgenden Beispiel werden alle<xref:System.Windows.Documents.Inline> Inhalte (Elemente) aus der <xref:System.Windows.Documents.Span>gelöscht.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
<a name="Types_that_Share_this_Content_Model"></a>
## <a name="types-that-share-this-content-model"></a>Typen, für die dieses Inhaltsmodell freigegeben ist  
 Die folgenden Typen erben <xref:System.Windows.Documents.TextElement> von der Klasse und können verwendet werden, um den in dieser Übersicht beschriebenen Inhalt anzuzeigen.  
  
 <xref:System.Windows.Documents.Bold>, <xref:System.Windows.Documents.Figure>, <xref:System.Windows.Documents.Floater>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Documents.InlineUIContainer>, <xref:System.Windows.Documents.Italic>, <xref:System.Windows.Documents.LineBreak>, <xref:System.Windows.Documents.List>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Run>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Span>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.Underline>.  
  
 Beachten Sie, dass diese Liste nur nicht abstrakte Typen enthält, die mit dem Windows SDK verteilt sind. Sie können andere Typen verwenden, <xref:System.Windows.Documents.TextElement>die von erben.  
  
<a name="Types_that_Can_Contain_ContentControl_Objects"></a>
## <a name="types-that-can-contain-textelement-objects"></a>Typen, die TextElement-Objekte enthalten können  
 Siehe [WPF Content Model](../controls/wpf-content-model.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Bearbeiten von einem FlowDocument mit der Blocks-Eigenschaft](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [Bearbeiten von fortlaufenden Inhaltselementen mit der Blocks-Eigenschaft](how-to-manipulate-flow-content-elements-through-the-blocks-property.md)
- [Bearbeiten von einem FlowDocument mit der Blocks-Eigenschaft](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [Bearbeiten der Spalten einer Tabelle mit der Columns-Eigenschaft](how-to-manipulate-table-columns-through-the-columns-property.md)
- [Bearbeiten der Zeilengruppen einer Tabelle mit der RowGroups-Eigenschaft](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
