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
ms.openlocfilehash: 990642d288481fff8eeef900a86070d54790f151
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59336186"
---
# <a name="textelement-content-model-overview"></a>Übersicht über das TextElement-Inhaltsmodell
Dieser Inhaltsmodellübersicht beschreibt die unterstützte Inhalte für eine <xref:System.Windows.Documents.TextElement>. Die <xref:System.Windows.Documents.Paragraph> Klasse ist eine Art von <xref:System.Windows.Documents.TextElement>. Ein Inhaltsmodell beschreibt, welche Objekte/Elemente in anderen enthalten sein können. Diese Übersicht fasst das Inhaltsmodell für abgeleitete Objekte verwendet <xref:System.Windows.Documents.TextElement>. Weitere Informationen finden Sie unter [Übersicht über Flussdokumente](flow-document-overview.md).  

<a name="text_element_classes"></a>   
## <a name="content-model-diagram"></a>Inhaltsmodelldiagramm  
 Das folgende Diagramm fasst das Inhaltsmodell für Klassen von abgeleitete <xref:System.Windows.Documents.TextElement> sowie wie andere nicht- `TextElement` Klassen, die in dieses Modell passen.  
  
 ![Diagramm: Flussinhalt-einschlussschema](./media/flow-content-schema.png "Flow_Content_Schema")  
  
 Wie aus dem vorherigen Diagramm ersichtlich ist, die für ein Element zulässigen untergeordneten Elemente werden nicht zwingend davon bestimmt, ob von eine Klasse abgeleitet ist die <xref:System.Windows.Documents.Block> Klasse oder ein <xref:System.Windows.Documents.Inline> Klasse. Z. B. eine <xref:System.Windows.Documents.Span> (ein <xref:System.Windows.Documents.Inline>-abgeleitete Klasse) nur möglich, <xref:System.Windows.Documents.Inline> untergeordnete Elemente, aber ein <xref:System.Windows.Documents.Figure> (auch ein <xref:System.Windows.Documents.Inline>-abgeleitete Klasse) nur möglich, <xref:System.Windows.Documents.Block> untergeordnete Elemente. Aus diesem Grund ist ein Diagramm nützlich, um schnell zu bestimmen, welches Element in einem anderen eingeschlossen sein kann. Als Beispiel verwenden Sie wir das Diagramm, um zu bestimmen, wie den fortlaufende Inhalt einer <xref:System.Windows.Controls.RichTextBox>.  
  
1. Ein <xref:System.Windows.Controls.RichTextBox> darf eine <xref:System.Windows.Documents.FlowDocument> muss wiederum eine <xref:System.Windows.Documents.Block>-abgeleitetes Objekt. Im Folgenden wird das entsprechende Segment aus dem vorherigen Diagramm dargestellt.  
  
     ![Diagramm: RichTextBox-Kapselungsregeln](./media/flow-ovw-schemawalkthrough1.png "Flow_Ovw_SchemaWalkThrough1")  
  
     Bis jetzt könnte das Markup wie folgt aussehen.  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough1](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]  
  
2. Gemäß dem Diagramm stehen verschiedene <xref:System.Windows.Documents.Block> zu wählen, darunter Elemente <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.List>, und <xref:System.Windows.Documents.BlockUIContainer> (Siehe blockabgeleitete Klassen in der obigen Abbildung). Nehmen wir eine <xref:System.Windows.Documents.Table>. Gemäß dem vorherigen Diagramm eine <xref:System.Windows.Documents.Table> enthält eine <xref:System.Windows.Documents.TableRowGroup> mit <xref:System.Windows.Documents.TableRow> Elemente, die enthalten <xref:System.Windows.Documents.TableCell> Elemente beinhalten eine <xref:System.Windows.Documents.Block>-abgeleitetes Objekt. Im folgenden werden das entsprechende Segment für <xref:System.Windows.Documents.Table> aus dem vorherigen Diagramm erstellt.  
  
     ![Diagramm: Übergeordnete&#47;untergeordnetes Schema für Tabelle](./media/flow-ovw-schemawalkthrough2.png "Flow_Ovw_SchemaWalkThrough2")  
  
     Im Folgenden wird das entsprechende Markup dargestellt.  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough2](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]  
  
3. In diesem Fall eine oder mehrere <xref:System.Windows.Documents.Block> Elemente sind erforderlich, darunter eine <xref:System.Windows.Documents.TableCell>. Um es einfach zu gestalten, fügen wir Text in die Zelle ein. Wir erreichen das mithilfe einer <xref:System.Windows.Documents.Paragraph> mit einem <xref:System.Windows.Documents.Run> Element. Im folgenden werden die entsprechenden Segmente aus dem Diagramm zeigt, dass eine <xref:System.Windows.Documents.Paragraph> dauert ein <xref:System.Windows.Documents.Inline> -Element sowie eine <xref:System.Windows.Documents.Run> (ein <xref:System.Windows.Documents.Inline> Element) kann nur nur-Text annehmen.  
  
     ![Diagramm: Übergeordnete&#47;untergeordnetes Schema für Absatz](./media/flow-ovw-schemawalkthrough3.png "Flow_Ovw_SchemaWalkThrough3")  
  
     ![Diagramm: Übergeordnete&#47;untergeordnetes Schema für Ausführung](./media/flow-ovw-schemawalkthrough4.png "Flow_Ovw_SchemaWalkThrough4")  
  
 Nachstehend finden Sie das gesamte Beispiel im Markup.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]  
  
<a name="Using_the_Content_Property"></a>   
## <a name="working-with-textelement-content-programmatically"></a>Programmgesteuertes Arbeiten mit TextElement-Inhalt  
 Den Inhalt einer <xref:System.Windows.Documents.TextElement> besteht aus Sammlungen und daher programmgesteuert bearbeiten des Inhalts der <xref:System.Windows.Documents.TextElement> Objekte erfolgt durch die Arbeit mit diesen Sammlungen. Es gibt drei verschiedene Auflistungen von verwendeten <xref:System.Windows.Documents.TextElement> -abgeleitete Klassen:  
  
-   <xref:System.Windows.Documents.InlineCollection>: Stellt eine Auflistung von <xref:System.Windows.Documents.Inline>-Elementen dar. <xref:System.Windows.Documents.InlineCollection> definiert den zulässigen untergeordneten Inhalt, der die <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Span>, und <xref:System.Windows.Controls.TextBlock> Elemente.  
  
-   <xref:System.Windows.Documents.BlockCollection>: Stellt eine Auflistung von <xref:System.Windows.Documents.Block>-Elementen dar. <xref:System.Windows.Documents.BlockCollection> definiert den zulässigen untergeordneten Inhalt, der die <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.TableCell>, <xref:System.Windows.Documents.Floater>, und <xref:System.Windows.Documents.Figure> Elemente.  
  
-   <xref:System.Windows.Documents.ListItemCollection>: Ein fortlaufendes Inhaltselement, das ein bestimmtes Inhaltselement in einer geordneten darstellt oder die ungeordneten <xref:System.Windows.Documents.List>.  
  
 Sie können ändern (hinzufügen oder Entfernen von Elementen) diese Auflistungen mithilfe der entsprechenden Eigenschaften der **Inlines**, **Blöcke**, und **ListItems**. Die folgenden Beispiele zeigen, wie Sie den Inhalt eines Span-Element mit Bearbeiten der **Inlines** Eigenschaft.  
  
> [!NOTE]
>  Table verwendet mehrere Auflistungen, um den Inhalt zu bearbeiten. Diese werden hier aber nicht aufgeführt. Weitere Informationen finden Sie unter [Tabellenübersicht](table-overview.md).  
  
 Das folgende Beispiel erstellt ein neues <xref:System.Windows.Documents.Span> Objekt und verwendet dann die `Add` Methode zum Hinzufügen von zwei Text ausgeführt wird, als untergeordnete Inhaltselemente des der <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
 Das folgende Beispiel erstellt ein neues <xref:System.Windows.Documents.Run> Element und fügt es am Anfang der <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
 Das folgende Beispiel löscht das letzte <xref:System.Windows.Documents.Inline> Element in der <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
 Das folgende Beispiel löscht den Inhalt (<xref:System.Windows.Documents.Inline> Elemente) aus der <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
<a name="Types_that_Share_this_Content_Model"></a>   
## <a name="types-that-share-this-content-model"></a>Typen, für die dieses Inhaltsmodell freigegeben ist  
 Die folgenden Typen erben von der <xref:System.Windows.Documents.TextElement> Klasse und kann verwendet werden, um den in dieser Übersicht beschriebenen Inhalt anzuzeigen.  
  
 <xref:System.Windows.Documents.Bold>, <xref:System.Windows.Documents.Figure>, <xref:System.Windows.Documents.Floater>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Documents.InlineUIContainer>, <xref:System.Windows.Documents.Italic>, <xref:System.Windows.Documents.LineBreak>, <xref:System.Windows.Documents.List>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Run>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Span>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.Underline>.  
  
 Beachten Sie, dass diese Liste nur nicht abstrakte Typen, die zusammen enthält mit den [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)]. Sie können andere Typen, die von erben <xref:System.Windows.Documents.TextElement>.  
  
<a name="Types_that_Can_Contain_ContentControl_Objects"></a>   
## <a name="types-that-can-contain-textelement-objects"></a>Typen, die TextElement-Objekte enthalten können  
 Finden Sie unter [WPF-Inhaltsmodell](../controls/wpf-content-model.md).  
  
## <a name="see-also"></a>Siehe auch

- [Bearbeiten von einem FlowDocument mit der Blocks-Eigenschaft](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [Bearbeiten von fortlaufenden Inhaltselementen mit der Blocks-Eigenschaft](how-to-manipulate-flow-content-elements-through-the-blocks-property.md)
- [Bearbeiten von einem FlowDocument mit der Blocks-Eigenschaft](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [Bearbeiten der Spalten einer Tabelle mit der Columns-Eigenschaft](how-to-manipulate-table-columns-through-the-columns-property.md)
- [Bearbeiten der Zeilengruppen einer Tabelle mit der RowGroups-Eigenschaft](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
