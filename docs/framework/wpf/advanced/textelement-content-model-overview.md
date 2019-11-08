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
ms.openlocfilehash: acd67dd870c6912eddc368bf674804d98dba2db8
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740755"
---
# <a name="textelement-content-model-overview"></a>Übersicht über das TextElement-Inhaltsmodell
In dieser Übersicht über das Inhalts Modell werden die unterstützten Inhalte für eine <xref:System.Windows.Documents.TextElement>beschrieben. Die <xref:System.Windows.Documents.Paragraph>-Klasse ist ein Typ von <xref:System.Windows.Documents.TextElement>. Ein Inhaltsmodell beschreibt, welche Objekte/Elemente in anderen enthalten sein können. In dieser Übersicht wird das Inhalts Modell für Objekte zusammengefasst, die von <xref:System.Windows.Documents.TextElement>abgeleitet werden. Weitere Informationen finden Sie unter [Übersicht über Fluss Dokumente](flow-document-overview.md).  

<a name="text_element_classes"></a>   
## <a name="content-model-diagram"></a>Inhaltsmodelldiagramm  
 Im folgenden Diagramm ist das Inhalts Modell für Klassen zusammengefasst, die von <xref:System.Windows.Documents.TextElement> abgeleitet sind, sowie die Art und Weise, wie andere nicht `TextElement` Klassen in dieses Modell passen.  
  
 ![Diagramm: Fluss Inhalt-Einschluss Schema](./media/flow-content-schema.png "Flow_Content_Schema")  
  
 Wie aus dem vorangehenden Diagramm ersichtlich ist, werden die untergeordneten Elemente, die für ein Element zulässig sind, nicht notwendigerweise bestimmt, ob eine Klasse von der <xref:System.Windows.Documents.Block> Klasse oder einer <xref:System.Windows.Documents.Inline> Klasse abgeleitet ist. Beispielsweise kann ein <xref:System.Windows.Documents.Span> (eine <xref:System.Windows.Documents.Inline>abgeleitete Klasse) nur <xref:System.Windows.Documents.Inline> untergeordneten Elementen aufweisen, aber ein <xref:System.Windows.Documents.Figure> (auch eine <xref:System.Windows.Documents.Inline>abgeleitete Klasse) kann nur <xref:System.Windows.Documents.Block> untergeordnete Elemente aufweisen. Aus diesem Grund ist ein Diagramm nützlich, um schnell zu bestimmen, welches Element in einem anderen eingeschlossen sein kann. Als Beispiel verwenden wir das Diagramm, um zu bestimmen, wie der fortlaufende Inhalt einer <xref:System.Windows.Controls.RichTextBox>erstellt wird.  
  
1. Ein <xref:System.Windows.Controls.RichTextBox> muss ein <xref:System.Windows.Documents.FlowDocument> enthalten, das wiederum ein <xref:System.Windows.Documents.Block>von abgeleitetes Objekt enthalten muss. Im Folgenden wird das entsprechende Segment aus dem vorherigen Diagramm dargestellt.  
  
     ![Diagramm: RichTextBox-Containment-Regeln](./media/flow-ovw-schemawalkthrough1.png "Flow_Ovw_SchemaWalkThrough1")  
  
     Bis jetzt könnte das Markup wie folgt aussehen.  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough1](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]  
  
2. Gemäß dem Diagramm gibt es mehrere <xref:System.Windows.Documents.Block> Elemente, die Sie auswählen können, einschließlich <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.List>und <xref:System.Windows.Documents.BlockUIContainer> (siehe von Block abgeleitete Klassen im vorangehenden Diagramm). Nehmen wir an, wir möchten eine <xref:System.Windows.Documents.Table>. Gemäß dem vorangehenden Diagramm enthält eine <xref:System.Windows.Documents.Table> eine <xref:System.Windows.Documents.TableRowGroup>, die <xref:System.Windows.Documents.TableRow> Elemente enthält, die <xref:System.Windows.Documents.TableCell> Elemente enthalten, die ein <xref:System.Windows.Documents.Block>von abgeleitetes Objekt enthalten. Im folgenden finden Sie das entsprechende Segment für <xref:System.Windows.Documents.Table> aus dem vorangehenden Diagramm.  
  
     ![Diagramm: über&#47;geordnetes untergeordnetes Schema für Tabelle](./media/flow-ovw-schemawalkthrough2.png "Flow_Ovw_SchemaWalkThrough2")  
  
     Im Folgenden wird das entsprechende Markup dargestellt.  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough2](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]  
  
3. Ein oder mehrere <xref:System.Windows.Documents.Block> Elemente sind unterhalb einer <xref:System.Windows.Documents.TableCell>erforderlich. Um es einfach zu gestalten, fügen wir Text in die Zelle ein. Dies ist mit einem <xref:System.Windows.Documents.Paragraph> mit einem <xref:System.Windows.Documents.Run>-Element möglich. Im folgenden werden die entsprechenden Segmente aus dem Diagramm gezeigt, die zeigen, dass ein <xref:System.Windows.Documents.Paragraph> ein <xref:System.Windows.Documents.Inline> Element annehmen kann und dass ein <xref:System.Windows.Documents.Run> (ein <xref:System.Windows.Documents.Inline> Element) nur nur-Text annehmen kann.  
  
     ![Diagramm: über&#47;geordnetes untergeordnetes Schema für Absatz](./media/flow-ovw-schemawalkthrough3.png "Flow_Ovw_SchemaWalkThrough3")  
  
     ![Diagramm: über&#47;geordnetes Schema für den Testlauf](./media/flow-ovw-schemawalkthrough4.png "Flow_Ovw_SchemaWalkThrough4")  
  
 Nachstehend finden Sie das gesamte Beispiel im Markup.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]  
  
<a name="Using_the_Content_Property"></a>   
## <a name="working-with-textelement-content-programmatically"></a>Programmgesteuertes Arbeiten mit TextElement-Inhalt  
 Der Inhalt einer <xref:System.Windows.Documents.TextElement> wird durch Sammlungen erstellt, sodass die Inhalte <xref:System.Windows.Documents.TextElement> Objekte Programm gesteuert bearbeitet werden, indem Sie mit diesen Auflistungen arbeiten. Es gibt drei verschiedene Auflistungen, die von <xref:System.Windows.Documents.TextElement> von abgeleiteten Klassen verwendet werden:  
  
- <xref:System.Windows.Documents.InlineCollection>: stellt eine Auflistung von <xref:System.Windows.Documents.Inline> Elementen dar. <xref:System.Windows.Documents.InlineCollection> definiert den zulässigen untergeordneten Inhalt der Elemente <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Span> und <xref:System.Windows.Controls.TextBlock>.  
  
- <xref:System.Windows.Documents.BlockCollection>: stellt eine Auflistung von <xref:System.Windows.Documents.Block> Elementen dar. <xref:System.Windows.Documents.BlockCollection> definiert den zulässigen untergeordneten Inhalt der Elemente <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.TableCell>, <xref:System.Windows.Documents.Floater> und <xref:System.Windows.Documents.Figure>.  
  
- <xref:System.Windows.Documents.ListItemCollection>: ein fortlaufendes Inhalts Element, das ein bestimmtes Inhalts Element in einer geordneten oder ungeordneten <xref:System.Windows.Documents.List>darstellt.  
  
 Sie können diese Sammlungen mithilfe der entsprechenden Eigenschaften von **Inlines**, **Blocks**und **ListItems**bearbeiten (hinzufügen oder entfernen). In den folgenden Beispielen wird gezeigt, wie der Inhalt einer Spanne mithilfe der **Inlines** -Eigenschaft bearbeitet wird.  
  
> [!NOTE]
> Table verwendet mehrere Auflistungen, um den Inhalt zu bearbeiten. Diese werden hier aber nicht aufgeführt. Weitere Informationen finden Sie unter [Übersicht über Tabellen](table-overview.md).  
  
 Im folgenden Beispiel wird ein neues <xref:System.Windows.Documents.Span>-Objekt erstellt. Anschließend wird die `Add`-Methode verwendet, um zwei Textläufe als untergeordnete Elemente des <xref:System.Windows.Documents.Span>hinzuzufügen.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
 Im folgenden Beispiel wird ein neues <xref:System.Windows.Documents.Run>-Element erstellt und am Anfang der <xref:System.Windows.Documents.Span>eingefügt.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
 Im folgenden Beispiel wird das letzte <xref:System.Windows.Documents.Inline>-Element in der <xref:System.Windows.Documents.Span>gelöscht.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
 Im folgenden Beispiel werden alle Inhalte (<xref:System.Windows.Documents.Inline> Elemente) aus der <xref:System.Windows.Documents.Span>gelöscht.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
<a name="Types_that_Share_this_Content_Model"></a>   
## <a name="types-that-share-this-content-model"></a>Typen, für die dieses Inhaltsmodell freigegeben ist  
 Die folgenden Typen erben von der <xref:System.Windows.Documents.TextElement>-Klasse und können verwendet werden, um den in dieser Übersicht beschriebenen Inhalt anzuzeigen.  
  
 <xref:System.Windows.Documents.Bold>, <xref:System.Windows.Documents.Figure>, <xref:System.Windows.Documents.Floater>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Documents.InlineUIContainer>, <xref:System.Windows.Documents.Italic>, <xref:System.Windows.Documents.LineBreak>, <xref:System.Windows.Documents.List>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Run>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Span>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.Underline>.  
  
 Beachten Sie, dass diese Liste nur nicht abstrakte Typen umfasst, die mit dem Windows SDK verteilt sind. Sie können andere Typen verwenden, die von <xref:System.Windows.Documents.TextElement>erben.  
  
<a name="Types_that_Can_Contain_ContentControl_Objects"></a>   
## <a name="types-that-can-contain-textelement-objects"></a>Typen, die TextElement-Objekte enthalten können  
 Siehe [WPF-Inhalts Modell](../controls/wpf-content-model.md).  
  
## <a name="see-also"></a>Siehe auch

- [Bearbeiten von einem FlowDocument mit der Blocks-Eigenschaft](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [Bearbeiten von fortlaufenden Inhaltselementen mit der Blocks-Eigenschaft](how-to-manipulate-flow-content-elements-through-the-blocks-property.md)
- [Bearbeiten von einem FlowDocument mit der Blocks-Eigenschaft](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [Bearbeiten der Spalten einer Tabelle mit der Columns-Eigenschaft](how-to-manipulate-table-columns-through-the-columns-property.md)
- [Bearbeiten der Zeilengruppen einer Tabelle mit der RowGroups-Eigenschaft](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
