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
ms.openlocfilehash: 21df7228f8dca884c5f36be23ae1aced7b31cc9a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942218"
---
# <a name="textelement-content-model-overview"></a>Übersicht über das TextElement-Inhaltsmodell
In dieser Übersicht über das Inhalts Modell werden die unter <xref:System.Windows.Documents.TextElement>stützten Inhalte für eine beschrieben. Die <xref:System.Windows.Documents.Paragraph> -Klasse ist ein Typ <xref:System.Windows.Documents.TextElement>von. Ein Inhaltsmodell beschreibt, welche Objekte/Elemente in anderen enthalten sein können. Diese Übersicht fasst das Inhalts Modell zusammen, das für von <xref:System.Windows.Documents.TextElement>abgeleitete Objekte verwendet wird. Weitere Informationen finden Sie unter [Übersicht über Fluss Dokumente](flow-document-overview.md).  

<a name="text_element_classes"></a>   
## <a name="content-model-diagram"></a>Inhaltsmodelldiagramm  
 Im folgenden Diagramm ist das Inhalts Modell für Klassen zusammengefasst <xref:System.Windows.Documents.TextElement> , die von abgeleitet sind, sowie `TextElement` die Art und Weise, wie andere nicht-Klassen in dieses Modell passen.  
  
 ![Diagra Einschluss Schema]für fortlaufenden Inhalt(./media/flow-content-schema.png "Flow_Content_Schema")  
  
 Wie aus dem vorangehenden Diagramm ersichtlich ist, werden die untergeordneten Elemente, die für ein Element zulässig sind, nicht notwendigerweise bestimmt, ob <xref:System.Windows.Documents.Block> eine Klasse von <xref:System.Windows.Documents.Inline> der-Klasse oder einer-Klasse abgeleitet ist. Beispielsweise kann eine <xref:System.Windows.Documents.Span> (eine <xref:System.Windows.Documents.Inline>von abgeleitete Klasse) nur unter <xref:System.Windows.Documents.Inline> geordnete Elemente aufweisen, aber <xref:System.Windows.Documents.Figure> eine (auch <xref:System.Windows.Documents.Inline>eine von abgeleitete Klasse) kann <xref:System.Windows.Documents.Block> nur untergeordnete Elemente aufweisen. Aus diesem Grund ist ein Diagramm nützlich, um schnell zu bestimmen, welches Element in einem anderen eingeschlossen sein kann. Als Beispiel verwenden wir das Diagramm, um zu bestimmen, wie der fortlaufende Inhalt <xref:System.Windows.Controls.RichTextBox>eines erstellt wird.  
  
1. Muss einen enthalten, der wiederum ein <xref:System.Windows.Documents.Block>von abgeleitetes Objekt enthalten muss. <xref:System.Windows.Documents.FlowDocument> <xref:System.Windows.Controls.RichTextBox> Im Folgenden wird das entsprechende Segment aus dem vorherigen Diagramm dargestellt.  
  
     ![Diagra RichTextBox-Containment]-Regeln(./media/flow-ovw-schemawalkthrough1.png "Flow_Ovw_SchemaWalkThrough1")  
  
     Bis jetzt könnte das Markup wie folgt aussehen.  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough1](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]  
  
2. Entsprechend dem Diagramm <xref:System.Windows.Documents.Block> stehen mehrere Elemente zur Auswahl <xref:System.Windows.Documents.Section> <xref:System.Windows.Documents.Table> <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.List>z. a.,,, und <xref:System.Windows.Documents.BlockUIContainer> (siehe von Block abgeleitete Klassen im vorangehenden Diagramm). Nehmen wir an, wir möchten <xref:System.Windows.Documents.Table>ein. Gemäß dem vorangehenden <xref:System.Windows.Documents.Table> Diagramm <xref:System.Windows.Documents.TableRowGroup> enthält eine eine enthaltende <xref:System.Windows.Documents.TableRow> Elemente, die Elemente <xref:System.Windows.Documents.TableCell> enthalten, die ein <xref:System.Windows.Documents.Block>von abgeleitetes Objekt enthalten. Im folgenden finden Sie das entsprechende Segment <xref:System.Windows.Documents.Table> , das aus dem vorherigen Diagramm entnommen wurde.  
  
     ![Diagra Über&#47;geordnetes untergeordnetes Schema]für Tabelle(./media/flow-ovw-schemawalkthrough2.png "Flow_Ovw_SchemaWalkThrough2")  
  
     Im Folgenden wird das entsprechende Markup dargestellt.  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough2](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]  
  
3. Ein oder mehrere <xref:System.Windows.Documents.Block> -Elemente sind <xref:System.Windows.Documents.TableCell>unterhalb von erforderlich. Um es einfach zu gestalten, fügen wir Text in die Zelle ein. Dies <xref:System.Windows.Documents.Paragraph> ist<xref:System.Windows.Documents.Run> mit einem-Element möglich. Im folgenden finden <xref:System.Windows.Documents.Inline> Sie die entsprechenden Segmente aus dem Diagramm, die <xref:System.Windows.Documents.Paragraph> zeigen, dass ein-Element akzeptiert <xref:System.Windows.Documents.Run> und ein <xref:System.Windows.Documents.Inline> (ein-Element) nur nur-Text annehmen kann.  
  
     ![Diagra Über&#47;geordnetes untergeordnetes Schema]für Absatz(./media/flow-ovw-schemawalkthrough3.png "Flow_Ovw_SchemaWalkThrough3")  
  
     ![Diagra Über&#47;geordnetes untergeordnetes Schema]für Run(./media/flow-ovw-schemawalkthrough4.png "Flow_Ovw_SchemaWalkThrough4")  
  
 Nachstehend finden Sie das gesamte Beispiel im Markup.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]  
  
<a name="Using_the_Content_Property"></a>   
## <a name="working-with-textelement-content-programmatically"></a>Programmgesteuertes Arbeiten mit TextElement-Inhalt  
 Der Inhalt <xref:System.Windows.Documents.TextElement> eines wird durch Auflistungen erstellt, sodass der Inhalt von <xref:System.Windows.Documents.TextElement> Objekten Programm gesteuert bearbeitet wird, indem er mit diesen Auflistungen arbeitet. Es gibt drei verschiedene Auflistungen <xref:System.Windows.Documents.TextElement> , die von abgeleiteten Klassen verwendet werden:  
  
- <xref:System.Windows.Documents.InlineCollection>: Stellt eine Auflistung von <xref:System.Windows.Documents.Inline>-Elementen dar. <xref:System.Windows.Documents.InlineCollection> definiert den zulässigen untergeordneten Inhalt der Elemente <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Span> und <xref:System.Windows.Controls.TextBlock>.  
  
- <xref:System.Windows.Documents.BlockCollection>: Stellt eine Auflistung von <xref:System.Windows.Documents.Block>-Elementen dar. <xref:System.Windows.Documents.BlockCollection> definiert den zulässigen untergeordneten Inhalt der Elemente <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.TableCell>, <xref:System.Windows.Documents.Floater> und <xref:System.Windows.Documents.Figure>.  
  
- <xref:System.Windows.Documents.ListItemCollection>: Ein fortlaufendes Inhalts Element, das ein bestimmtes Inhalts Element in einer geordneten oder <xref:System.Windows.Documents.List>ungeordneten darstellt.  
  
 Sie können diese Sammlungen mithilfe der entsprechenden Eigenschaften von **Inlines**, **Blocks**und **ListItems**bearbeiten (hinzufügen oder entfernen). In den folgenden Beispielen wird gezeigt, wie der Inhalt einer Spanne mithilfe der **Inlines** -Eigenschaft bearbeitet wird.  
  
> [!NOTE]
> Table verwendet mehrere Auflistungen, um den Inhalt zu bearbeiten. Diese werden hier aber nicht aufgeführt. Weitere Informationen finden Sie unter [Übersicht über Tabellen](table-overview.md).  
  
 Im folgenden Beispiel wird ein neues <xref:System.Windows.Documents.Span> -Objekt erstellt, und anschließend `Add` wird die-Methode verwendet, um zwei Textläufe <xref:System.Windows.Documents.Span>als untergeordnete Elemente des hinzuzufügen.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
 Im folgenden Beispiel wird ein neues <xref:System.Windows.Documents.Run> -Element erstellt, das am Anfang <xref:System.Windows.Documents.Span>der eingefügt wird.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
 Im folgenden Beispiel wird das letzte <xref:System.Windows.Documents.Inline> -Element <xref:System.Windows.Documents.Span>in gelöscht.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
 Im folgenden Beispiel wird der gesamte Inhalt (<xref:System.Windows.Documents.Inline> -Elemente) aus dem <xref:System.Windows.Documents.Span>gelöscht.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
<a name="Types_that_Share_this_Content_Model"></a>   
## <a name="types-that-share-this-content-model"></a>Typen, für die dieses Inhaltsmodell freigegeben ist  
 Die folgenden Typen erben von der <xref:System.Windows.Documents.TextElement> -Klasse und können verwendet werden, um den in dieser Übersicht beschriebenen Inhalt anzuzeigen.  
  
 <xref:System.Windows.Documents.Bold>, <xref:System.Windows.Documents.Figure>, <xref:System.Windows.Documents.Floater>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Documents.InlineUIContainer>, <xref:System.Windows.Documents.Italic>, <xref:System.Windows.Documents.LineBreak>, <xref:System.Windows.Documents.List>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Run>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Span>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.Underline>.  
  
 Beachten Sie, dass diese Liste nur nicht abstrakte Typen umfasst, [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)]die mit dem verteilt werden. Sie können andere Typen verwenden, die von <xref:System.Windows.Documents.TextElement>erben.  
  
<a name="Types_that_Can_Contain_ContentControl_Objects"></a>   
## <a name="types-that-can-contain-textelement-objects"></a>Typen, die TextElement-Objekte enthalten können  
 Siehe [WPF-Inhalts Modell](../controls/wpf-content-model.md).  
  
## <a name="see-also"></a>Siehe auch

- [Bearbeiten von einem FlowDocument mit der Blocks-Eigenschaft](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [Bearbeiten von fortlaufenden Inhaltselementen mit der Blocks-Eigenschaft](how-to-manipulate-flow-content-elements-through-the-blocks-property.md)
- [Bearbeiten von einem FlowDocument mit der Blocks-Eigenschaft](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [Bearbeiten der Spalten einer Tabelle mit der Columns-Eigenschaft](how-to-manipulate-table-columns-through-the-columns-property.md)
- [Bearbeiten der Zeilengruppen einer Tabelle mit der RowGroups-Eigenschaft](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
